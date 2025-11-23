<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publibros - Comparte y Lee Libros</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Firebase SDK v9 -->
    <script type="module">
        // Import the functions you need from the SDKs you need
        import { initializeApp } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-app.js";
        import { getAnalytics } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-analytics.js";
        import { 
            getAuth, 
            onAuthStateChanged, 
            signInWithEmailAndPassword, 
            createUserWithEmailAndPassword,
            updateProfile,
            signOut 
        } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-auth.js";

        // Your web app's Firebase configuration
        const firebaseConfig = {
            apiKey: "AIzaSyDjwZHNY-q6kp67MzUOMQ4olOW3CgtNL0U",
            authDomain: "publilibros01.firebaseapp.com",
            projectId: "publilibros01",
            storageBucket: "publilibros01.firebasestorage.app",
            messagingSenderId: "242974271454",
            appId: "1:242974271454:web:ae939c47d714ccb6185f4f",
            measurementId: "G-CSLWHDQ3Q6"
        };

        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const analytics = getAnalytics(app);
        const auth = getAuth(app);

        // Sistema de autenticación con Firebase v9
        class FirebaseAuth {
            constructor() {
                this.currentUser = JSON.parse(localStorage.getItem('publibros-current-user')) || null;
                this.listeners = [];
                
                // Escuchar cambios en la autenticación de Firebase
                this.addFirebaseAuthListener();
            }
            
            // Añadir listener para cambios de estado de autenticación de Firebase
            addFirebaseAuthListener() {
                onAuthStateChanged(auth, (user) => {
                    if (user) {
                        // User is signed in
                        console.log("Usuario autenticado:", user);
                        
                        // Si es un usuario nuevo o no tenemos sus datos completos
                        if (!this.currentUser || this.currentUser.uid !== user.uid) {
                            // Crear o actualizar objeto de usuario
                            this.currentUser = {
                                uid: user.uid,
                                email: user.email,
                                name: user.displayName || user.email.split('@')[0],
                                bio: this.currentUser?.bio || '',
                                avatar: this.currentUser?.avatar || null,
                                likedBooks: this.currentUser?.likedBooks || [],
                                myReviews: this.currentUser?.myReviews || [],
                                favoriteGenres: this.currentUser?.favoriteGenres || [],
                                createdAt: this.currentUser?.createdAt || new Date().toISOString()
                            };
                        }
                        
                        localStorage.setItem('publibros-current-user', JSON.stringify(this.currentUser));
                        this.notifyListeners(this.currentUser);
                    } else {
                        // User is signed out
                        console.log("Usuario no autenticado");
                        this.currentUser = null;
                        localStorage.removeItem('publibros-current-user');
                        this.notifyListeners(null);
                    }
                });
            }
            
            // Notificar a los listeners
            notifyListeners(user) {
                this.listeners.forEach(listener => {
                    listener(user);
                });
            }
            
            // Registrar un listener
            onAuthStateChanged(listener) {
                this.listeners.push(listener);
                // Llamar inmediatamente con el estado actual
                listener(this.currentUser);
            }
            
            // Iniciar sesión con email y contraseña usando Firebase
            async signInWithEmailAndPassword(email, password) {
                try {
                    const userCredential = await signInWithEmailAndPassword(auth, email, password);
                    // Signed in
                    const user = userCredential.user;
                    return { user: this.currentUser };
                } catch (error) {
                    let errorMessage = 'Error al iniciar sesión.';
                    
                    switch (error.code) {
                        case 'auth/invalid-email':
                            errorMessage = 'El formato del email no es válido.';
                            break;
                        case 'auth/user-disabled':
                            errorMessage = 'Esta cuenta ha sido deshabilitada.';
                            break;
                        case 'auth/user-not-found':
                            errorMessage = 'No existe una cuenta con este email.';
                            break;
                        case 'auth/wrong-password':
                            errorMessage = 'La contraseña es incorrecta.';
                            break;
                        default:
                            errorMessage = error.message;
                    }
                    
                    throw { code: error.code, message: errorMessage };
                }
            }
            
            // Registrar un nuevo usuario con Firebase
            async createUserWithEmailAndPassword(email, password, name) {
                try {
                    const userCredential = await createUserWithEmailAndPassword(auth, email, password);
                    // Signed up
                    const user = userCredential.user;
                    
                    // Actualizar el perfil del usuario con el nombre
                    await updateProfile(user, {
                        displayName: name
                    });
                    
                    // Crear objeto de usuario para nuestra aplicación
                    this.currentUser = {
                        uid: user.uid,
                        email: user.email,
                        name: name,
                        bio: '',
                        avatar: null,
                        likedBooks: [],
                        myReviews: [],
                        favoriteGenres: [],
                        createdAt: new Date().toISOString()
                    };
                    
                    localStorage.setItem('publibros-current-user', JSON.stringify(this.currentUser));
                    this.notifyListeners(this.currentUser);
                    
                    return { user: this.currentUser };
                } catch (error) {
                    let errorMessage = 'Error al crear la cuenta.';
                    
                    switch (error.code) {
                        case 'auth/email-already-in-use':
                            errorMessage = 'Este email ya está registrado.';
                            break;
                        case 'auth/invalid-email':
                            errorMessage = 'El formato del email no es válido.';
                            break;
                        case 'auth/operation-not-allowed':
                            errorMessage = 'La operación no está permitida.';
                            break;
                        case 'auth/weak-password':
                            errorMessage = 'La contraseña es demasiado débil.';
                            break;
                        default:
                            errorMessage = error.message;
                    }
                    
                    throw { code: error.code, message: errorMessage };
                }
            }
            
            // Cerrar sesión
            async signOut() {
                try {
                    await signOut(auth);
                    this.currentUser = null;
                    localStorage.removeItem('publibros-current-user');
                    this.notifyListeners(null);
                } catch (error) {
                    console.error('Error al cerrar sesión:', error);
                }
            }
            
            // Obtener usuario actual
            getCurrentUser() {
                return this.currentUser;
            }
        }

        // Hacer la clase disponible globalmente
        window.FirebaseAuth = FirebaseAuth;
        window.firebaseAuthInstance = new FirebaseAuth();
    </script>

    <style>
        /* Todos los estilos CSS anteriores se mantienen igual */
        /* ... (todo el CSS existente) ... */
    </style>
</head>
<body>
    <!-- Todo el HTML existente se mantiene igual -->
    <!-- ... (todo el HTML existente) ... -->

    <script>
        // Ahora usamos la instancia global de FirebaseAuth
        const auth = window.firebaseAuthInstance;

        // El resto del código JavaScript permanece igual
        // Solo necesitamos reemplazar la clase Auth anterior por la nueva instancia

        // Almacenamiento de datos
        let books = JSON.parse(localStorage.getItem('publibros-books')) || [];
        let authors = JSON.parse(localStorage.getItem('publibros-authors')) || [];

        // Variables para el lector
        let currentBook = null;
        let currentPage = 0;
        const wordsPerPage = 300;

        // Variables para filtros
        let selectedGenre = 'all';
        let searchTerm = '';

        // Géneros disponibles (se mantiene igual)
        const genres = [
            "romance", "thriller", "terror", "fantasia", "ciencia-ficcion", 
            // ... (todos los géneros)
        ];

        // Nombres de géneros para mostrar (se mantiene igual)
        const genreNames = {
            "romance": "Romance",
            "thriller": "Thriller",
            // ... (todos los nombres de géneros)
        };

        // El resto de las funciones permanecen exactamente igual
        // ... (todo el código JavaScript existente)

        // Solo necesitamos actualizar la inicialización para usar la instancia de FirebaseAuth
        document.addEventListener('DOMContentLoaded', function() {
            // Cargar el tema guardado
            loadTheme();
            
            // Configurar listener para cambios de autenticación
            // Ahora usamos la instancia global de FirebaseAuth
            auth.onAuthStateChanged((user) => {
                const authStatus = document.getElementById('auth-status');
                const authBtn = document.getElementById('auth-btn');
                
                if (user) {
                    authStatus.textContent = user.name;
                    authBtn.innerHTML = `<i class="fas fa-user"></i> <span id="auth-status">${user.name}</span>`;
                    
                    // Actualizar perfil si está activo
                    if (document.getElementById('perfil').classList.contains('active')) {
                        updateProfile();
                    }
                    
                    // Actualizar recomendaciones si estamos en inicio
                    if (document.getElementById('inicio').classList.contains('active')) {
                        displayRecommendedBooks();
                    }
                } else {
                    authStatus.textContent = 'Iniciar Sesión';
                    authBtn.innerHTML = `<i class="fas fa-user"></i> <span id="auth-status">Iniciar Sesión</span>`;
                    
                    // Si estamos en la sección de perfil, actualizar
                    if (document.getElementById('perfil').classList.contains('active')) {
                        updateProfile();
                    }
                    
                    // Actualizar recomendaciones si estamos en inicio
                    if (document.getElementById('inicio').classList.contains('active')) {
                        displayRecommendedBooks();
                    }
                }
            });

            // El resto de la inicialización permanece igual
            // ... (todo el código de inicialización existente)
        });
    </script>
</body>
</html>
