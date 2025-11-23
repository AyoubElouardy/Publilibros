<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publibros - Comparte y Lee Libros</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --text: #333;
            --text-light: #7f8c8d;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }
        /* TODO el CSS que ya tenías (lo mantengo igual, solo lo abrevio aquí por espacio) */
        /* ... (el mismo CSS que ya tenías, no lo modifico) ... */
        body { background-color: #f9f9f9; color: var(--text); line-height: 1.6; }
        /* ... resto del CSS original ... */
    </style>
</head>
<body>
    <!-- TODO el HTML que ya tenías (header, secciones, modales, etc.) -->
    <!-- ... (exactamente el mismo HTML que ya tenías) ... -->

    <!-- Firebase SDKs -->
    <script type="module">
        // Import the functions you need from the Firebase SDKs
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js";
        import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-analytics.js";
        import { getAuth, onAuthStateChanged, signInWithEmailAndPassword, createUserWithEmailAndPassword, signOut } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-auth.js";
        import { getFirestore, collection, addDoc, setDoc, doc, getDocs, getDoc, updateDoc, arrayUnion, arrayRemove, query, where, orderBy, limit, onSnapshot } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore.js";
        import { getStorage, ref, uploadBytes, getDownloadURL } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-storage.js";

        // Tu configuración de Firebase
        const firebaseConfig = {
            apiKey: "AIzaSyDjwZHNY-q6kp67MzUOMQ4olOW3CgtNL0U",
            authDomain: "publilibros01.firebaseapp.com",
            projectId: "publilibros01",
            storageBucket: "publilibros01.firebasestorage.app",
            messagingSenderId: "242974271454",
            appId: "1:242974271454:web:ae939c47d714ccb6185f4f",
            measurementId: "G-CSLWHDQ3Q6"
        };

        // Inicializar Firebase
        const app = initializeApp(firebaseConfig);
        const analytics = getAnalytics(app);
        const auth = getAuth(app);
        const db = getFirestore(app);
        const storage = getStorage(app);

        // Variables globales
        let booksUnsubscribe = null;
        let currentBook = null;
        let currentPage = 0;
        const wordsPerPage = 300;
        let selectedGenre = 'all';
        let searchTerm = '';

        const genres = ["romance","thriller","terror","fantasia","ciencia-ficcion","misterio","aventura","drama","poesia","biografia","historico","infantil","juvenil","autoayuda","otros"];
        const genreNames = { "romance":"Romance", "thriller":"Thriller", "terror":"Terror", "fantasia":"Fantasía", "ciencia-ficcion":"Ciencia Ficción", "misterio":"Misterio", "aventura":"Aventura", "drama":"Drama", "poesia":"Poesía", "biografia":"Biografía", "historico":"Histórico", "infantil":"Infantil", "juvenil":"Juvenil", "autoayuda":"Autoayuda", "otros":"Otros" };

        // ==================== AUTENTICACIÓN ====================
        onAuthStateChanged(auth, (user) => {
            const authStatus = document.getElementById('auth-status');
            if (user) {
                authStatus.textContent = user.displayName || user.email.split('@')[0];
                document.getElementById('auth-btn').innerHTML = `<i class="fas fa-user"></i> ${user.displayName || user.email.split('@')[0]}`;
                loadUserData(user);
            } else {
                authStatus.textContent = 'Iniciar Sesión';
                document.getElementById('auth-btn').innerHTML = `<i class="fas fa-user"></i> Iniciar Sesión`;
            }
            updateAllViews();
        });

        // Login
        document.getElementById('login-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            try {
                await signInWithEmailAndPassword(auth, email, password);
                document.getElementById('auth-modal').style.display = 'none';
            } catch (error) {
                alert("Error al iniciar sesión: " + error.message);
            }
        });

        // Registro
        document.getElementById('register-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            try {
                const cred = await createUserWithEmailAndPassword(auth, email, password);
                await updateDoc(doc(db, "users", cred.user.uid), { name, bio: "", likedBooks: [], myReviews: [] });
                document.getElementById('auth-modal').style.display = 'none';
            } catch (error) {
                alert("Error al registrarse: " + error.message);
            }
        });

        // Cerrar sesión
        document.getElementById('auth-btn').addEventListener('click', () => {
            if (auth.currentUser) {
                if (confirm('¿Cerrar sesión?')) signOut(auth);
            } else {
                document.getElementById('auth-modal').style.display = 'flex';
            }
        });

        // ==================== CARGA DE DATOS DEL USUARIO ====================
        async function loadUserData(user) {
            const userDoc = await getDoc(doc(db, "users", user.uid));
            if (userDoc.exists()) {
                window.currentUserData = userDoc.data();
            } else {
                window.currentUserData = { name: user.displayName || user.email.split('@')[0], bio: "", likedBooks: [], myReviews: [] };
            }
            loadUserAvatar();
        }

        function loadUserAvatar() {
            const avatarEl = document.getElementById('user-avatar');
            const placeholder = document.getElementById('avatar-placeholder');
            if (auth.currentUser && auth.currentUser.photoURL) {
                if (!avatarEl.querySelector('img')) {
                    const img = document.createElement('img');
                    img.src = auth.currentUser.photoURL;
                    avatarEl.insertBefore(img, placeholder);
                } else {
                    avatarEl.querySelector('img').src = auth.currentUser.photoURL;
                }
                placeholder.style.display = 'none';
            }
        }

        // ==================== LIBROS EN TIEMPO REAL ====================
        function listenToBooks() {
            if (booksUnsubscribe) booksUnsubscribe();
            const q = query(collection(db, "books"), orderBy("likes", "desc"));
            booksUnsubscribe = onSnapshot(q, (snapshot) => {
                window.books = [];
                snapshot.forEach(doc => {
                    window.books.push({ id: doc.id, ...doc.data() });
                });
                updateAllViews();
            });
        }

        // ==================== SUBIR LIBRO ====================
        document.getElementById('upload-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            if (!auth.currentUser) return alert("Debes iniciar sesión");

            const title = document.getElementById('book-title').value;
            const genre = document.getElementById('book-genre').value;
            const description = document.getElementById('book-description').value;
            const content = document.getElementById('book-content').value;

            try {
                await addDoc(collection(db, "books"), {
                    title,
                    author: window.currentUserData.name,
                    authorId: auth.currentUser.uid,
                    genre,
                    description,
                    content,
                    likes: 0,
                    reviews: [],
                    createdAt: new Date()
                });
                document.getElementById('upload-modal').style.display = 'none';
                e.target.reset();
                alert("¡Libro publicado con éxito!");
            } catch (err) {
                alert("Error al publicar: " + err.message);
            }
        });

        // ==================== LIKE ====================
        async function toggleLike(bookId) {
            if (!auth.currentUser) return document.getElementById('auth-modal').style.display = 'flex';

            const liked = window.currentUserData.likedBooks.includes(bookId);
            const bookRef = doc(db, "books", bookId);
            const userRef = doc(db, "users", auth.currentUser.uid);

            if (liked) {
                await updateDoc(bookRef, { likes: window.books.find(b => b.id === bookId).likes - 1 });
                await updateDoc(userRef, { likedBooks: arrayRemove(bookId) });
            } else {
                await updateDoc(bookRef, { likes: window.books.find(b => b.id === bookId).likes + 1 });
                await updateDoc(userRef, { likedBooks: arrayUnion(bookId) });
            }
            window.currentUserData.likedBooks = liked 
                ? window.currentUserData.likedBooks.filter(id => id !== bookId)
                : [...window.currentUserData.likedBooks, bookId];
        }

        // ==================== RESEÑAS ====================
        document.getElementById('submit-review').addEventListener('click', async () => {
            if (!auth.currentUser) return alert("Inicia sesión para reseñar");
            const rating = document.getElementById('review-rating').value;
            const content = document.getElementById('review-content').value.trim();
            if (!content) return alert("Escribe tu reseña");

            await updateDoc(doc(db, "books", currentBook.id), {
                reviews: arrayUnion({
                    user: window.currentUserData.name,
                    rating: parseInt(rating),
                    content,
                    date: new Date().toISOString().split('T')[0]
                })
            });

            await updateDoc(doc(db, "users", auth.currentUser.uid), {
                myReviews: arrayUnion({
                    bookId: currentBook.id,
                    bookTitle: currentBook.title,
                    rating: parseInt(rating),
                    content,
                    date: new Date().toISOString().split('T')[0]
                })
            });

            document.getElementById('review-content').value = '';
            alert("¡Reseña enviada!");
        });

        // ==================== EDITAR PERFIL (con foto) ====================
        document.getElementById('edit-profile-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const name = document.getElementById('edit-user-name').value;
            const bio = document.getElementById('edit-user-bio').value;
            const file = document.getElementById('edit-user-avatar').files[0];

            let photoURL = auth.currentUser.photoURL;
            if (file) {
                const storageRef = ref(storage, 'avatars/' + auth.currentUser.uid);
                await uploadBytes(storageRef, file);
                photoURL = await getDownloadURL(storageRef);
            }

            await updateDoc(doc(db, "users", auth.currentUser.uid), { name, bio });
            if (photoURL) await auth.currentUser.updateProfile({ displayName: name, photoURL });

            document.getElementById('edit-profile-modal').style.display = 'none';
            alert("Perfil actualizado");
        });

        // ==================== VISTAS (las mismas funciones que ya tenías, solo adaptadas) ====================
        function updateAllViews() {
            updateHomeStats();
            displayFeaturedBooks();
            displayRecommendedBooks();
            displayBooks();
            displayGenreFilters();
            if (document.getElementById('perfil').classList.contains('active')) updateProfile();
        }

        // ... (todas las funciones displayBooks, displayRecommendedBooks, openBook, etc. 
        //     solo cambian las referencias de window.books y window.currentUserData en vez de localStorage)

        // Inicialización
        document.addEventListener('DOMContentLoaded', () => {
            listenToBooks();
            // ... resto de event listeners que ya tenías (navegación, modales, etc.)
            // (los mantengo exactamente iguales, solo usan las nuevas funciones globales)
        });
    </script>

    <!-- TODO el HTML original (header, secciones, footer, etc.) permanece igual -->
</body>
</html>
