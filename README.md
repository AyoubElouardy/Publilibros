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
            --text: #333;
            --text-light: #7f8c8d;
            --shadow: 0 4px 6px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }
        * { margin:0; padding:0; box-sizing:border-box; font-family:'Segoe UI',sans-serif; }
        body { background:#f9f9f9; color:var(--text); line-height:1.6; }
        .container { max-width:1200px; margin:0 auto; padding:0 20px; }
        header { background:var(--primary); color:white; padding:1rem 0; box-shadow:var(--shadow); position:sticky; top:0; z-index:100; }
        .header-content { display:flex; justify-content:space-between; align-items:center; }
        .logo { font-size:1.8rem; font-weight:bold; display:flex; align-items:center; }
        .logo i { color:var(--secondary); margin-right:10px; }
        .logo span { color:var(--secondary); }
        nav ul { display:flex; list-style:none; }
        nav ul li { margin-left:1.5rem; }
        nav ul li a { color:white; text-decoration:none; padding:0.5rem 1rem; border-radius:20px; transition:var(--transition); }
        nav ul li a:hover, nav ul li a.active { background:rgba(255,255,255,0.1); color:var(--secondary); }
        .user-actions button { background:transparent; border:none; color:white; margin-left:15px; cursor:pointer; font-size:1.3rem; }
        .main-section { display:none; padding:2rem 0; min-height:calc(100vh - 200px); }
        .main-section.active { display:block; }
        .hero { background:linear-gradient(rgba(44,62,80,0.85),rgba(44,62,80,0.85)), url('https://source.unsplash.com/random/1200x600/?library'); background-size:cover; color:white; padding:5rem 0; text-align:center; border-radius:12px; margin-bottom:3rem; }
        .hero h1 { font-size:3rem; margin-bottom:1rem; }
        .btn { display:inline-block; background:var(--secondary); color:white; padding:0.8rem 1.8rem; border:none; border-radius:30px; cursor:pointer; text-decoration:none; font-weight:bold; transition:var(--transition); }
        .btn:hover { background:#2980b9; transform:translateY(-3px); }
        .section-title { text-align:center; margin-bottom:3rem; color:var(--primary); position:relative; }
        .section-title:after { content:''; display:block; width:80px; height:4px; background:var(--secondary); margin:10px auto; border-radius:2px; }
        .books-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(280px,1fr)); gap:2rem; }
        .book-card { background:white; border-radius:12px; overflow:hidden; box-shadow:var(--shadow); transition:var(--transition); }
        .book-card:hover { transform:translateY(-10px); box-shadow:0 10px 20px rgba(0,0,0,0.15); }
        .book-cover { height:220px; background:linear-gradient(135deg,var(--primary),var(--secondary)); display:flex; align-items:center; justify-content:center; color:white; font-size:2rem; position:relative; }
        .book-actions { position:absolute; top:15px; right:15px; display:flex; flex-direction:column; gap:10px; }
        .book-action { background:rgba(255,255,255,0.9); width:36px; height:36px; border-radius:50%; display:flex; align-items:center; justify-content:center; cursor:pointer; color:var(--primary); }
        .book-action:hover { background:white; transform:scale(1.1); }
        .book-action.liked { color:var(--accent); }
        .book-info { padding:1.5rem; }
        .book-title { font-weight:bold; font-size:1.2rem; margin-bottom:0.5rem; }
        .book-author { color:var(--text-light); font-size:0.9rem; margin-bottom:0.5rem; }
        .book-genre { display:inline-block; background:#f1f2f6; padding:0.2rem 0.6rem; border-radius:12px; font-size:0.7rem; margin-top:0.5rem; text-transform:uppercase; }
        .empty-state { text-align:center; padding:3rem; background:white; border-radius:12px; box-shadow:var(--shadow); }
        .empty-state i { font-size:4rem; color:var(--text-light); margin-bottom:1.5rem; }
        .reader { display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:white; z-index:999; padding:2rem; overflow-y:auto; }
        .reader-header { display:flex; justify-content:space-between; align-items:center; margin-bottom:2rem; padding-bottom:1rem; border-bottom:1px solid #eee; }
        .reader-content { line-height:1.8; font-size:1.1rem; min-height:400px; white-space:pre-line; }
        .reader-controls { display:flex; justify-content:space-between; margin-top:2rem; align-items:center; }
        footer { background:var(--primary); color:white; padding:3rem 0 2rem; margin-top:3rem; text-align:center; }
    </style>
</head>
<body>

    <header>
        <div class="container header-content">
            <div class="logo"><i class="fas fa-book-open"></i>Publi<span>libros</span></div>
            <nav>
                <ul>
                    <li><a href="#" class="nav-link active" data-section="inicio">Inicio</a></li>
                    <li><a href="#" class="nav-link" data-section="biblioteca">Biblioteca</a></li>
                    <li><a href="#" class="nav-link" data-section="perfil">Mi Perfil</a></li>
                </ul>
            </nav>
            <div class="user-actions">
                <button id="auth-btn"><i class="fas fa-user"></i> <span id="auth-status">Iniciar con Google</span></button>
            </div>
        </div>
    </header>

    <!-- Secciones (igual que antes) -->
    <section id="inicio" class="main-section active">
        <div class="container">
            <div class="hero">
                <h1>Descubre y Comparte Historias Únicas</h1>
                <p>Publibros es la comunidad donde lees y publicas libros gratis con solo tu cuenta de Google.</p>
                <button class="btn" id="explore-library">Explorar Biblioteca</button>
            </div>
            <div class="books-grid" id="featured-books-container"></div>
        </div>
    </section>

    <section id="biblioteca" class="main-section">
        <div class="container">
            <h2 class="section-title">Biblioteca</h2>
            <button class="btn" id="upload-book-btn"><i class="fas fa-plus"></i> Subir Libro</button>
            <div class="books-grid" id="books-container"></div>
        </div>
    </section>

    <section id="perfil" class="main-section">
        <div class="container">
            <h2 class="section-title">Mi Perfil</h2>
            <div class="user-profile" style="background:white;padding:2rem;border-radius:12px;text-align:center;">
                <img id="profile-avatar" src="" alt="Avatar" style="width:120px;height:120px;border-radius:50%;object-fit:cover;margin-bottom:1rem;">
                <h2 id="profile-name">Cargando...</h2>
                <p id="profile-email"></p>
                <div class="user-stats">
                    <div><strong id="profile-books">0</strong> Libros</div>
                    <div><strong id="profile-likes">0</strong> Likes</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Lector -->
    <div id="reader" class="reader">
        <div class="reader-header">
            <h2 id="reader-title"></h2>
            <button class="close-modal" id="close-reader">×</button>
        </div>
        <div class="reader-content" id="reader-content"></div>
        <div class="reader-controls">
            <button id="prev-page">Anterior</button>
            <span id="page-info"></span>
            <button id="next-page">Siguiente</button>
        </div>
    </div>

    <!-- Firebase + Google Auth -->
    <script type="module">
      import { initializeApp } from "https://www.gstatic.com/firebasejs/10.13.1/firebase-app.js";
      import { getAuth, GoogleAuthProvider, signInWithPopup, onAuthStateChanged, signOut } from "https://www.gstatic.com/firebasejs/10.13.1/firebase-auth.js";

      const firebaseConfig = {
        apiKey: "AIzaSyDjwZHNY-q6kp67MzUOMQ4olOW3CgtNL0U",
        authDomain: "publilibros01.firebaseapp.com",
        projectId: "publilibros01",
        storageBucket: "publilibros01.firebasestorage.app",
        messagingSenderId: "242974271454",
        appId: "1:242974271454:web:ae939c47d714ccb6185f4f",
        measurementId: "G-CSLWHDQ3Q6"
      };

      const app = initializeApp(firebaseConfig);
      const auth = getAuth(app);
      const provider = new GoogleAuthProvider();

      let books = JSON.parse(localStorage.getItem('publibros-books') || '[]');
      let currentUserData = { likedBooks: [], myReviews: [] };
      let currentBook = null, currentPage = 0;
      const wordsPerPage = 300;

      function saveData() {
        localStorage.setItem('publibros-books', JSON.stringify(books));
        if (auth.currentUser) {
          localStorage.setItem(`user-${auth.currentUser.uid}`, JSON.stringify(currentUserData));
        }
      }

      onAuthStateChanged(auth, (user) => {
        const status = document.getElementById('auth-status');
        if (user) {
          status.textContent = user.displayName.split(' ')[0];
          document.getElementById('profile-name').textContent = user.displayName;
          document.getElementById('profile-email').textContent = user.email;
          document.getElementById('profile-avatar').src = user.photoURL || 'https://via.placeholder.com/120';
          currentUserData = JSON.parse(localStorage.getItem(`user-${user.uid}`) || '{"likedBooks":[],"myReviews":[]}');
          updateProfile();
        } else {
          status.textContent = 'Iniciar con Google';
        }
        displayBooks();
      });

      document.getElementById('auth-btn').addEventListener('click', () => {
        if (auth.currentUser) {
          if (confirm('¿Cerrar sesión?')) signOut(auth);
        } else {
          signInWithPopup(auth, provider)
            .then(() => console.log('¡Login exitoso!'))
            .catch(err => alert('Error: ' + err.message));
        }
      });

      function toggleLike(bookId) {
        if (!auth.currentUser) return alert('Inicia sesión con Google');
        const i = currentUserData.likedBooks.indexOf(bookId);
        if (i > -1) {
          currentUserData.likedBooks.splice(i, 1);
          books.find(b => b.id === bookId).likes--;
        } else {
          currentUserData.likedBooks.push(bookId);
          books.find(b => b.id === bookId).likes++;
        }
        saveData();
        displayBooks();
      }

      function displayBooks() {
        const container = document.getElementById('books-container') || document.getElementById('featured-books-container');
        container.innerHTML = books.map(book => `
          <div class="book-card">
            <div class="book-cover">${book.title[0]}</div>
            <div class="book-info">
              <div class="book-title">${book.title}</div>
              <div class="book-author">por ${book.author}</div>
              <button class="book-action ${currentUserData.likedBooks.includes(book.id) ? 'liked' : ''}" onclick="toggleLike(${book.id})">
                <i class="fas fa-heart"></i>
              </button>
              <button class="btn" style="margin-top:10px;width:100%" onclick="openBook(${book.id})">Leer</button>
            </div>
          </div>
        `).join('');
      }

      window.openBook = function(id) {
        currentBook = books.find(b => b.id === id);
        if (!currentBook) return;
        document.getElementById('reader-title').textContent = currentBook.title;
        document.getElementById('reader').style.display = 'block';
        currentPage = 0;
        showPage();
      };

      function showPage() {
        const words = currentBook.content.split(' ');
        const start = currentPage * wordsPerPage;
        document.getElementById('reader-content').textContent = words.slice(start, start + wordsPerPage).join(' ');
        document.getElementById('page-info').textContent = `Página ${currentPage + 1} de ${Math.ceil(words.length / wordsPerPage)}`;
      }

      document.getElementById('prev-page').onclick = () => { if (currentPage > 0) { currentPage--; showPage(); } };
      document.getElementById('next-page').onclick = () => { if ((currentPage + 1) * wordsPerPage < currentBook.content.split(' ').length) { currentPage++; showPage(); } };
      document.getElementById('close-reader').onclick = () => document.getElementById('reader').style.display = 'none';

      // Subir libro (ejemplo rápido)
      document.getElementById('upload-book-btn')?.addEventListener('click', () => {
        if (!auth.currentUser) return alert('Inicia sesión con Google');
        const title = prompt('Título del libro');
        const content = prompt('Pega aquí el contenido completo del libro');
        if (title && content) {
          books.push({
            id: Date.now(),
            title,
            author: auth.currentUser.displayName,
            content,
            likes: 0
          });
          saveData();
          displayBooks();
          alert('¡Libro publicado!');
        }
      });

      function updateProfile() {
        document.getElementById('profile-books').textContent = books.filter(b => b.author === auth.currentUser?.displayName).length;
        document.getElementById('profile-likes').textContent = currentUserData.likedBooks.length;
      }

      // Navegación
      document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', (e) => {
          e.preventDefault();
          document.querySelectorAll('.main-section').forEach(s => s.classList.remove('active'));
          document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
          document.getElementById(link.dataset.section).classList.add('active');
          link.classList.add('active');
        });
      });

      displayBooks();
    </script>
</body>
</html>
