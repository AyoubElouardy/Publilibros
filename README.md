<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publibros - Comparte y Lee Libros</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* TODO el CSS original que tenías en el <DOCUMENT> - lo copio completo para que funcione */
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

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f9f9f9;
            color: var(--text);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background-color: var(--primary);
            color: white;
            padding: 1rem 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }

        .logo i {
            color: var(--secondary);
            margin-right: 10px;
        }

        .logo span {
            color: var(--secondary);
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 1.5rem;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            transition: var(--transition);
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 20px;
        }

        nav ul li a:hover, nav ul li a.active {
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--secondary);
        }

        .user-actions {
            display: flex;
            align-items: center;
        }

        .user-actions button {
            background: transparent;
            border: none;
            color: white;
            margin-left: 15px;
            cursor: pointer;
            font-size: 1.1rem;
            transition: var(--transition);
        }

        .user-actions button:hover {
            color: var(--secondary);
        }

        /* Secciones principales */
        .main-section {
            display: none;
            padding: 2rem 0;
            min-height: calc(100vh - 200px);
        }

        .main-section.active {
            display: block;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.85), rgba(44, 62, 80, 0.85)), url('https://source.unsplash.com/random/1200x600/?library');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 5rem 0;
            text-align: center;
            border-radius: 12px;
            margin-bottom: 3rem;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            background-color: var(--secondary);
            color: white;
            padding: 0.8rem 1.8rem;
            border: none;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow);
        }

        .btn:hover {
            background-color: #2980b9;
            transform: translateY(-3px);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid white;
            margin-left: 10px;
        }

        .btn-outline:hover {
            background: white;
            color: var(--primary);
        }

        .btn-secondary {
            background-color: var(--primary);
        }

        .btn-secondary:hover {
            background-color: #1a252f;
        }

        /* Secciones */
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary);
            position: relative;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--secondary);
            margin: 10px auto;
            border-radius: 2px;
        }

        /* Biblioteca de libros */
        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .book-card {
            background-color: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .book-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.15);
        }

        .book-cover {
            height: 220px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
            position: relative;
        }

        .book-actions {
            position: absolute;
            top: 15px;
            right: 15px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .book-action {
            background: rgba(255, 255, 255, 0.9);
            width: 36px;
            height: 36px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
            color: var(--primary);
        }

        .book-action:hover {
            background: white;
            transform: scale(1.1);
        }

        .book-action.liked {
            color: var(--accent);
        }

        .book-info {
            padding: 1.5rem;
        }

        .book-title {
            font-weight: bold;
            margin-bottom: 0.5rem;
            font-size: 1.2rem;
        }

        .book-author {
            color: var(--text-light);
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
        }

        .book-author a {
            color: var(--secondary);
            text-decoration: none;
            margin-left: 5px;
            transition: var(--transition);
        }

        .book-author a:hover {
            text-decoration: underline;
        }

        .book-stats {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            font-size: 0.9rem;
            color: var(--text-light);
        }

        .book-stat {
            display: flex;
            align-items: center;
        }

        .book-stat i {
            margin-right: 5px;
        }

        .book-description {
            font-size: 0.9rem;
            margin-bottom: 1rem;
            height: 60px;
            overflow: hidden;
        }

        .book-genre {
            display: inline-block;
            background-color: #f1f2f6;
            color: var(--text);
            padding: 0.2rem 0.6rem;
            border-radius: 12px;
            font-size: 0.7rem;
            margin-top: 0.5rem;
            text-transform: uppercase;
            font-weight: 500;
        }

        /* Estados vacíos */
        .empty-state {
            text-align: center;
            padding: 3rem;
            background: white;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .empty-state i {
            font-size: 4rem;
            color: var(--text-light);
            margin-bottom: 1.5rem;
        }

        .empty-state h3 {
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .empty-state p {
            color: var(--text-light);
            max-width: 500px;
            margin: 0 auto 2rem;
        }

        /* Recomendaciones */
        .recommendation-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background: var(--accent);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 1;
        }

        /* Formulario de subida */
        .upload-form {
            max-width: 700px;
            margin: 0 auto;
            background-color: white;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: var(--primary);
        }

        .form-control {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-control:focus {
            border-color: var(--secondary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Lector de libros */
        .reader-container {
            max-width: 900px;
            margin: 0 auto;
            background-color: white;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .reader-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .reader-content {
            line-height: 1.8;
            font-size: 1.1rem;
            min-height: 400px;
            white-space: pre-line;
        }

        .reader-controls {
            display: flex;
            justify-content: space-between;
            margin-top: 2rem;
            align-items: center;
        }

        /* Reseñas */
        .reviews-section {
            margin-top: 3rem;
        }

        .review-form {
            background: #f8f9fa;
            padding: 1.5rem;
            border-radius: 8px;
            margin-bottom: 2rem;
        }

        .review {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            margin-bottom: 1rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        .review-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }

        .review-author {
            font-weight: bold;
        }

        .review-date {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .review-rating {
            color: #f39c12;
            margin-bottom: 0.5rem;
        }

        /* Perfil de usuario */
        .user-profile {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            background: white;
            padding: 1.5rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .user-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2.5rem;
            margin-right: 1.5rem;
            overflow: hidden;
            position: relative;
            cursor: pointer;
        }

        .user-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .user-avatar .avatar-placeholder {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            height: 100%;
        }

        .user-avatar .edit-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: var(--transition);
        }

        .user-avatar:hover .edit-overlay {
            opacity: 1;
        }

        .user-avatar .edit-overlay i {
            color: white;
            font-size: 1.5rem;
        }

        .user-info {
            flex: 1;
        }

        .user-name {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .user-email {
            color: var(--text-light);
            margin-bottom: 0.5rem;
        }

        .user-bio {
            color: var(--text-light);
            margin-bottom: 1rem;
        }

        .user-stats {
            display: flex;
            gap: 1.5rem;
        }

        .user-stat {
            text-align: center;
        }

        .stat-value {
            font-size: 1.2rem;
            font-weight: bold;
            color: var(--primary);
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--text-light);
        }

        /* Pestañas del perfil */
        .profile-tabs {
            margin-top: 3rem;
        }

        .tabs-header {
            display: flex;
            border-bottom: 1px solid #ddd;
            margin-bottom: 2rem;
        }

        .tab-btn {
            background: none;
            border: none;
            padding: 1rem 2rem;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 500;
            color: var(--text-light);
            border-bottom: 3px solid transparent;
            transition: var(--transition);
        }

        .tab-btn:hover {
            color: var(--primary);
        }

        .tab-btn.active {
            color: var(--secondary);
            border-bottom: 3px solid var(--secondary);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* Footer */
        footer {
            background-color: var(--primary);
            color: white;
            padding: 3rem 0 2rem;
            margin-top: 3rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-section h3:after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 3px;
            background: var(--secondary);
        }

        .footer-section p {
            margin-bottom: 1rem;
            opacity: 0.8;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            opacity: 0.7;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            max-width: 500px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            background: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .modal-header h3 {
            color: var(--primary);
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text-light);
        }

        .auth-tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid #eee;
        }

        .auth-tab {
            padding: 0.8rem 1.5rem;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 500;
            color: var(--text-light);
            border-bottom: 3px solid transparent;
            transition: var(--transition);
        }

        .auth-tab.active {
            color: var(--secondary);
            border-bottom: 3px solid var(--secondary);
        }

        .auth-form {
            display: none;
        }

        .auth-form.active {
            display: block;
        }

        .form-footer {
            margin-top: 1.5rem;
            text-align: center;
            color: var(--text-light);
        }

        .form-footer a {
            color: var(--secondary);
            text-decoration: none;
            cursor: pointer;
        }

        .form-footer a:hover {
            text-decoration: underline;
        }

        .error-message {
            color: var(--accent);
            font-size: 0.9rem;
            margin-top: 0.5rem;
            display: none;
        }

        /* Géneros */
        .genre-filter {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .genre-chip {
            background-color: #e0e0e0;
            color: var(--text);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            cursor: pointer;
            transition: var(--transition);
            border: 2px solid transparent;
        }

        .genre-chip:hover {
            background-color: #d5d5d5;
        }

        .genre-chip.active {
            background-color: var(--secondary);
            color: white;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }

            nav ul {
                margin-top: 1rem;
                justify-content: center;
            }

            nav ul li {
                margin: 0 0.5rem;
            }

            .user-actions {
                margin-top: 1rem;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .books-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }

            .user-profile {
                flex-direction: column;
                text-align: center;
            }

            .user-avatar {
                margin-right: 0;
                margin-bottom: 1rem;
            }

            .tabs-header {
                flex-direction: column;
            }

            .tab-btn {
                width: 100%;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-book-open"></i>Publi<span>libros</span>
            </div>
            <nav>
                <ul>
                    <li><a href="#" class="nav-link active" data-section="inicio">Inicio</a></li>
                    <li><a href="#" class="nav-link" data-section="biblioteca">Biblioteca</a></li>
                    <li><a href="#" class="nav-link" data-section="perfil">Mi Perfil</a></li>
                </ul>
            </nav>
            <div class="user-actions">
                <button id="auth-btn"><i class="fas fa-user"></i> <span id="auth-status">Iniciar Sesión</span></button>
                <button id="theme-toggle"><i class="fas fa-moon"></i></button>
            </div>
        </div>
    </header>

    <!-- Sección Inicio -->
    <section id="inicio" class="main-section active">
        <div class="container">
            <div class="hero">
                <h1>Descubre y Comparte Historias Únicas</h1>
                <p>Publibros es una plataforma elegante donde autores y lectores se conectan. Comparte tus creaciones, descubre nuevos talentos y forma parte de una comunidad literaria vibrante.</p>
                <button class="btn" id="explore-library">Explorar Biblioteca</button>
                <button class="btn btn-outline" id="upload-first-book">Publica tu Primer Libro</button>
            </div>

            <div class="featured-books">
                <h2 class="section-title">Libros Destacados</h2>
                <div class="books-grid" id="featured-books-container">
                    <!-- Los libros destacados se cargarán aquí -->
                </div>
            </div>

            <!-- Nueva sección: Libros Recomendados -->
            <div class="recommended-books" id="recommended-section">
                <h2 class="section-title">Libros Recomendados para Ti</h2>
                <div class="books-grid" id="recommended-books-container">
                    <!-- Los libros recomendados se cargarán aquí -->
                </div>
            </div>

            <div class="stats-section">
                <div class="stats-grid" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 2rem; margin-top: 3rem;">
                    <div class="stat-card" style="background: white; padding: 2rem; border-radius: 12px; text-align: center; box-shadow: var(--shadow);">
                        <div class="stat-icon" style="font-size: 2.5rem; color: var(--secondary); margin-bottom: 1rem;">
                            <i class="fas fa-book"></i>
                        </div>
                        <div class="stat-value" id="total-books" style="font-size: 2rem; font-weight: bold; color: var(--primary);">0</div>
                        <div class="stat-label" style="color: var(--text-light);">Libros Publicados</div>
                    </div>
                    <div class="stat-card" style="background: white; padding: 2rem; border-radius: 12px; text-align: center; box-shadow: var(--shadow);">
                        <div class="stat-icon" style="font-size: 2.5rem; color: var(--secondary); margin-bottom: 1rem;">
                            <i class="fas fa-users"></i>
                        </div>
                        <div class="stat-value" id="total-authors" style="font-size: 2rem; font-weight: bold; color: var(--primary);">0</div>
                        <div class="stat-label" style="color: var(--text-light);">Autores Registrados</div>
                    </div>
                    <div class="stat-card" style="background: white; padding: 2rem; border-radius: 12px; text-align: center; box-shadow: var(--shadow);">
                        <div class="stat-icon" style="font-size: 2.5rem; color: var(--secondary); margin-bottom: 1rem;">
                            <i class="fas fa-heart"></i>
                        </div>
                        <div class="stat-value" id="total-likes" style="font-size: 2rem; font-weight: bold; color: var(--primary);">0</div>
                        <div class="stat-label" style="color: var(--text-light);">Likes Totales</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Sección Biblioteca -->
    <section id="biblioteca" class="main-section">
        <div class="container">
            <h2 class="section-title">Biblioteca de Libros</h2>
            
            <div class="library-actions" style="display: flex; justify-content: space-between; margin-bottom: 2rem; flex-wrap: wrap; gap: 1rem;">
                <button class="btn" id="upload-book-btn">
                    <i class="fas fa-plus"></i> Subir Nuevo Libro
                </button>
                <div class="search-filter" style="display: flex; gap: 1rem; flex-wrap: wrap;">
                    <input type="text" id="search-books" class="form-control" placeholder="Buscar libros..." style="min-width: 200px;">
                    <select id="filter-books" class="form-control" style="min-width: 150px;">
                        <option value="all">Todos</option>
                        <option value="liked">Me gusta</option>
                        <option value="my-books">Mis libros</option>
                    </select>
                </div>
            </div>
            
            <!-- Filtros de género -->
            <div class="genre-filter" id="genre-filter-container">
                <!-- Los filtros de género se cargarán aquí -->
            </div>

            <div class="books-grid" id="books-container">
                <!-- Los libros se cargarán aquí -->
            </div>
        </div>
    </section>

    <!-- Sección Perfil -->
    <section id="perfil" class="main-section">
        <div class="container">
            <h2 class="section-title">Mi Perfil</h2>
            
            <div class="user-profile">
                <div class="user-avatar" id="user-avatar">
                    <div class="avatar-placeholder" id="avatar-placeholder">
                        <i class="fas fa-user"></i>
                    </div>
                    <div class="edit-overlay" id="edit-avatar-overlay">
                        <i class="fas fa-camera"></i>
                    </div>
                </div>
                <div class="user-info">
                    <h2 class="user-name" id="profile-user-name">Usuario</h2>
                    <p class="user-email" id="profile-user-email">email@ejemplo.com</p>
                    <p class="user-bio" id="profile-user-bio">Aquí puedes agregar una breve biografía sobre ti.</p>
                    <div class="user-stats">
                        <div class="user-stat">
                            <div class="stat-value" id="profile-books">0</div>
                            <div class="stat-label">Libros Publicados</div>
                        </div>
                        <div class="user-stat">
                            <div class="stat-value" id="profile-likes">0</div>
                            <div class="stat-label">Likes Recibidos</div>
                        </div>
                        <div class="user-stat">
                            <div class="stat-value" id="profile-reviews">0</div>
                            <div class="stat-label">Reseñas Escritas</div>
                        </div>
                    </div>
                </div>
                <button class="btn" id="edit-profile-btn">Editar Perfil</button>
            </div>

            <div class="profile-tabs">
                <div class="tabs-header">
                    <button class="tab-btn active" data-tab="my-books">Mis Libros</button>
                    <button class="tab-btn" data-tab="liked-books">Libros que Me Gustan</button>
                    <button class="tab-btn" data-tab="my-reviews">Mis Reseñas</button>
                </div>
                
                <div class="tab-content active" id="my-books-tab">
                    <h3 style="margin-bottom: 1.5rem;">Mis Libros Publicados</h3>
                    <div class="books-grid" id="my-books-container">
                        <!-- Los libros del usuario se cargarán aquí -->
                    </div>
                </div>
                
                <div class="tab-content" id="liked-books-tab">
                    <h3 style="margin-bottom: 1.5rem;">Libros que Me Gustan</h3>
                    <div class="books-grid" id="liked-books-container">
                        <!-- Los libros que le gustan al usuario se cargarán aquí -->
                    </div>
                </div>
                
                <div class="tab-content" id="my-reviews-tab">
                    <h3 style="margin-bottom: 1.5rem;">Mis Reseñas</h3>
                    <div id="my-reviews-container">
                        <!-- Las reseñas del usuario se cargarán aquí -->
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Modal para autenticación -->
    <div id="auth-modal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="auth-modal-title">Iniciar Sesión</h3>
                <button class="close-modal" id="close-auth-modal">&times;</button>
            </div>
            
            <div class="auth-tabs">
                <button class="auth-tab active" data-form="login">Iniciar Sesión</button>
                <button class="auth-tab" data-form="register">Registrarse</button>
            </div>
            
            <form id="login-form" class="auth-form active">
                <div class="form-group">
                    <label for="login-email">Email</label>
                    <input type="email" id="login-email" class="form-control" required>
                    <div class="error-message" id="login-email-error"></div>
                </div>
                <div class="form-group">
                    <label for="login-password">Contraseña</label>
                    <input type="password" id="login-password" class="form-control" required>
                    <div class="error-message" id="login-password-error"></div>
                </div>
                <button type="submit" class="btn" style="width: 100%;">Iniciar Sesión</button>
                <div class="form-footer">
                    ¿No tienes cuenta? <a id="switch-to-register">Regístrate aquí</a>
                </div>
            </form>
            
            <form id="register-form" class="auth-form">
                <div class="form-group">
                    <label for="register-name">Nombre</label>
                    <input type="text" id="register-name" class="form-control" required>
                    <div class="error-message" id="register-name-error"></div>
                </div>
                <div class="form-group">
                    <label for="register-email">Email</label>
                    <input type="email" id="register-email" class="form-control" required>
                    <div class="error-message" id="register-email-error"></div>
                </div>
                <div class="form-group">
                    <label for="register-password">Contraseña</label>
                    <input type="password" id="register-password" class="form-control" required>
                    <div class="error-message" id="register-password-error"></div>
                </div>
                <div class="form-group">
                    <label for="register-confirm-password">Confirmar Contraseña</label>
                    <input type="password" id="register-confirm-password" class="form-control" required>
                    <div class="error-message" id="register-confirm-password-error"></div>
                </div>
                <button type="submit" class="btn" style="width: 100%;">Registrarse</button>
                <div class="form-footer">
                    ¿Ya tienes cuenta? <a id="switch-to-login">Inicia sesión aquí</a>
                </div>
            </form>
        </div>
    </div>

    <!-- Modal para subir libro -->
    <div id="upload-modal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Publicar Nuevo Libro</h3>
                <button class="close-modal" id="close-upload-modal">&times;</button>
            </div>
            <form id="upload-form">
                <div class="form-group">
                    <label for="book-title">Título del Libro</label>
                    <input type="text" id="book-title" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="book-author">Autor</label>
                    <input type="text" id="book-author" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="book-genre">Género</label>
                    <select id="book-genre" class="form-control" required>
                        <option value="">Selecciona un género</option>
                        <option value="romance">Romance</option>
                        <option value="thriller">Thriller</option>
                        <option value="terror">Terror</option>
                        <option value="fantasia">Fantasía</option>
                        <option value="ciencia-ficcion">Ciencia Ficción</option>
                        <option value="misterio">Misterio</option>
                        <option value="aventura">Aventura</option>
                        <option value="drama">Drama</option>
                        <option value="poesia">Poesía</option>
                        <option value="biografia">Biografía</option>
                        <option value="historico">Histórico</option>
                        <option value="infantil">Infantil</option>
                        <option value="juvenil">Juvenil</option>
                        <option value="autoayuda">Autoayuda</option>
                        <option value="otros">Otros</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="book-description">Descripción</label>
                    <textarea id="book-description" class="form-control" required></textarea>
                </div>
                <div class="form-group">
                    <label for="book-content">Contenido del Libro</label>
                    <textarea id="book-content" class="form-control" placeholder="Escribe o pega el contenido de tu libro aquí..." required></textarea>
                </div>
                <button type="submit" class="btn" style="width: 100%;">Publicar Libro</button>
            </form>
        </div>
    </div>

    <!-- Modal para editar perfil -->
    <div id="edit-profile-modal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Editar Perfil</h3>
                <button class="close-modal" id="close-edit-profile-modal">&times;</button>
            </div>
            <form id="edit-profile-form">
                <div class="form-group">
                    <label for="edit-user-name">Nombre</label>
                    <input type="text" id="edit-user-name" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="edit-user-bio">Biografía</label>
                    <textarea id="edit-user-bio" class="form-control" placeholder="Cuéntanos sobre ti..."></textarea>
                </div>
                <div class="form-group">
                    <label for="edit-user-avatar">Foto de Perfil</label>
                    <input type="file" id="edit-user-avatar" class="form-control" accept="image/*">
                    <small style="color: var(--text-light);">Selecciona una imagen para tu perfil (máx. 2MB)</small>
                </div>
                <button type="submit" class="btn" style="width: 100%;">Guardar Cambios</button>
            </form>
        </div>
    </div>

    <!-- Lector de Libros (oculto inicialmente) -->
    <section id="reader" style="display: none;">
        <div class="container">
            <div class="reader-container">
                <div class="reader-header">
                    <h2 id="reader-title">Título del Libro</h2>
                    <button id="close-reader" class="btn">Cerrar</button>
                </div>
                <div class="reader-content" id="reader-content">
                    <!-- El contenido del libro se cargará aquí -->
                </div>
                <div class="reader-controls">
                    <button id="prev-page" class="btn"><i class="fas fa-chevron-left"></i> Anterior</button>
                    <span id="page-info">Página 1 de 1</span>
                    <button id="next-page" class="btn">Siguiente <i class="fas fa-chevron-right"></i></button>
                </div>

                <!-- Sección de reseñas -->
                <div class="reviews-section">
                    <h3>Reseñas</h3>
                    <div class="review-form">
                        <h4>Deja tu reseña</h4>
                        <div class="form-group">
                            <label for="review-rating">Calificación</label>
                            <select id="review-rating" class="form-control">
                                <option value="5">★★★★★ Excelente</option>
                                <option value="4">★★★★ Muy Bueno</option>
                                <option value="3">★★★ Bueno</option>
                                <option value="2">★★ Regular</option>
                                <option value="1">★ Malo</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="review-content">Tu reseña</label>
                            <textarea id="review-content" class="form-control" placeholder="Comparte tu opinión sobre este libro..."></textarea>
                        </div>
                        <button id="submit-review" class="btn">Enviar Reseña</button>
                    </div>
                    <div id="reviews-container">
                        <!-- Las reseñas se cargarán aquí dinámicamente -->
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Publibros</h3>
                    <p>Una plataforma elegante para compartir y descubrir libros de autores emergentes y establecidos.</p>
                    <p>Conectamos a lectores y escritores en una comunidad literaria vibrante.</p>
                </div>
                <div class="footer-section">
                    <h3>Enlaces Rápidos</h3>
                    <p><a href="#" class="nav-link-footer" data-section="inicio" style="color: white; text-decoration: none;">Inicio</a></p>
                    <p><a href="#" class="nav-link-footer" data-section="biblioteca" style="color: white; text-decoration: none;">Biblioteca</a></p>
                    <p><a href="#" class="nav-link-footer" data-section="perfil" style="color: white; text-decoration: none;">Mi Perfil</a></p>
                </div>
                <div class="footer-section">
                    <h3>Sobre Nosotros</h3>
                    <p>Publibros nació con la misión de crear un espacio donde los amantes de la literatura puedan compartir sus creaciones y descubrir nuevas voces.</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 Publibros. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        // TODO el JavaScript original del <DOCUMENT> - lo copio completo (sistema con localStorage)
        // Géneros disponibles
        const genres = [
            "romance", "thriller", "terror", "fantasia", "ciencia-ficcion", 
            "misterio", "aventura", "drama", "poesia", "biografia", 
            "historico", "infantil", "juvenil", "autoayuda", "otros"
        ];

        // Nombres de géneros para mostrar
        const genreNames = {
            "romance": "Romance",
            "thriller": "Thriller",
            "terror": "Terror",
            "fantasia": "Fantasía",
            "ciencia-ficcion": "Ciencia Ficción",
            "misterio": "Misterio",
            "aventura": "Aventura",
            "drama": "Drama",
            "poesia": "Poesía",
            "biografia": "Biografía",
            "historico": "Histórico",
            "infantil": "Infantil",
            "juvenil": "Juvenil",
            "autoayuda": "Autoayuda",
            "otros": "Otros"
        };

        // Sistema de autenticación simulado
        class Auth {
            constructor() {
                this.users = JSON.parse(localStorage.getItem('publibros-users')) || [];
                this.currentUser = JSON.parse(localStorage.getItem('publibros-current-user')) || null;
                this.listeners = [];
                
                // Escuchar cambios en la autenticación
                this.addStateDidChangeListener();
            }
            
            // Añadir listener para cambios de estado de autenticación
            addStateDidChangeListener() {
                // Este método simula el comportamiento de Firebase Auth
                // En una implementación real, esto se conectaría con Firebase
                window.addEventListener('storage', () => {
                    const user = JSON.parse(localStorage.getItem('publibros-current-user'));
                    this.currentUser = user;
                    this.notifyListeners(user);
                });
                
                // También notificamos cuando cambiamos el usuario desde esta instancia
                this.notifyListeners(this.currentUser);
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
            
            // Iniciar sesión con email y contraseña
            signInWithEmailAndPassword(email, password) {
                return new Promise((resolve, reject) => {
                    // Simular latencia de red
                    setTimeout(() => {
                        const user = this.users.find(u => u.email === email && u.password === password);
                        if (user) {
                            // No almacenar la contraseña en el objeto de usuario actual
                            const { password, ...userWithoutPassword } = user;
                            this.currentUser = userWithoutPassword;
                            localStorage.setItem('publibros-current-user', JSON.stringify(this.currentUser));
                            this.notifyListeners(this.currentUser);
                            resolve({ user: this.currentUser });
                        } else {
                            reject({ 
                                code: 'auth/wrong-password',
                                message: 'El email o la contraseña son incorrectos.' 
                            });
                        }
                    }, 1000);
                });
            }
            
            // Registrar un nuevo usuario
            createUserWithEmailAndPassword(email, password, name) {
                return new Promise((resolve, reject) => {
                    // Simular latencia de red
                    setTimeout(() => {
                        // Verificar si el usuario ya existe
                        if (this.users.find(u => u.email === email)) {
                            reject({ 
                                code: 'auth/email-already-in-use',
                                message: 'Este email ya está registrado.' 
                            });
                            return;
                        }
                        
                        // Crear nuevo usuario
                        const newUser = {
                            id: this.users.length > 0 ? Math.max(...this.users.map(u => u.id)) + 1 : 1,
                            email,
                            password,
                            name,
                            bio: '',
                            avatar: null,
                            likedBooks: [],
                            myReviews: [],
                            favoriteGenres: [],
                            createdAt: new Date().toISOString()
                        };
                        
                        this.users.push(newUser);
                        localStorage.setItem('publibros-users', JSON.stringify(this.users));
                        
                        // No almacenar la contraseña en el objeto de usuario actual
                        const { password: pwd, ...userWithoutPassword } = newUser;
                        this.currentUser = userWithoutPassword;
                        localStorage.setItem('publibros-current-user', JSON.stringify(this.currentUser));
                        this.notifyListeners(this.currentUser);
                        
                        resolve({ user: this.currentUser });
                    }, 1000);
                });
            }
            
            // Cerrar sesión
            signOut() {
                this.currentUser = null;
                localStorage.removeItem('publibros-current-user');
                this.notifyListeners(null);
            }
            
            // Obtener usuario actual
            getCurrentUser() {
                return this.currentUser;
            }
        }

        // Instancia global de autenticación
        const auth = new Auth();

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

        // Función para guardar datos en localStorage
        function saveData() {
            localStorage.setItem('publibros-books', JSON.stringify(books));
            localStorage.setItem('publibros-authors', JSON.stringify(authors));
            
            // Actualizar datos del usuario en la lista de usuarios
            if (auth.currentUser) {
                const users = JSON.parse(localStorage.getItem('publibros-users')) || [];
                const userIndex = users.findIndex(u => u.id === auth.currentUser.id);
                if (userIndex !== -1) {
                    // Mantener la contraseña del usuario
                    const password = users[userIndex].password;
                    users[userIndex] = { ...auth.currentUser, password };
                    localStorage.setItem('publibros-users', JSON.stringify(users));
                }
            }
        }

        // Función para cargar avatar de usuario
        function loadUserAvatar() {
            const userAvatar = document.getElementById('user-avatar');
            const avatarPlaceholder = document.getElementById('avatar-placeholder');
            
            if (auth.currentUser && auth.currentUser.avatar) {
                avatarPlaceholder.style.display = 'none';
                if (userAvatar.querySelector('img')) {
                    userAvatar.querySelector('img').src = auth.currentUser.avatar;
                } else {
                    const img = document.createElement('img');
                    img.src = auth.currentUser.avatar;
                    img.alt = 'Avatar de ' + auth.currentUser.name;
                    userAvatar.insertBefore(img, avatarPlaceholder);
                }
            } else {
                avatarPlaceholder.style.display = 'flex';
                const existingImg = userAvatar.querySelector('img');
                if (existingImg) {
                    existingImg.remove();
                }
                avatarPlaceholder.innerHTML = `<i class="fas fa-user"></i>`;
            }
        }

        // Función para mostrar filtros de género
        function displayGenreFilters() {
            const genreContainer = document.getElementById('genre-filter-container');
            genreContainer.innerHTML = '';
            
            // Botón para mostrar todos los géneros
            const allChip = document.createElement('div');
            allChip.className = `genre-chip ${selectedGenre === 'all' ? 'active' : ''}`;
            allChip.textContent = 'Todos';
            allChip.setAttribute('data-genre', 'all');
            allChip.addEventListener('click', function() {
                selectedGenre = 'all';
                displayBooks();
                updateGenreFilters();
            });
            genreContainer.appendChild(allChip);
            
            // Botones para cada género
            genres.forEach(genre => {
                const genreChip = document.createElement('div');
                genreChip.className = `genre-chip ${selectedGenre === genre ? 'active' : ''}`;
                genreChip.textContent = genreNames[genre];
                genreChip.setAttribute('data-genre', genre);
                genreChip.addEventListener('click', function() {
                    selectedGenre = genre;
                    displayBooks();
                    updateGenreFilters();
                });
                genreContainer.appendChild(genreChip);
            });
        }
        
        // Función para actualizar la apariencia de los filtros de género
        function updateGenreFilters() {
            document.querySelectorAll('.genre-chip').forEach(chip => {
                if (chip.getAttribute('data-genre') === selectedGenre) {
                    chip.classList.add('active');
                } else {
                    chip.classList.remove('active');
                }
            });
        }

        // Algoritmo de recomendación de libros
        function getRecommendedBooks() {
            if (!auth.currentUser) {
                return [];
            }
            
            const user = auth.currentUser;
            const likedBooks = books.filter(book => user.likedBooks.includes(book.id));
            
            // Si el usuario no tiene libros que le gusten, devolver libros populares
            if (likedBooks.length === 0) {
                return books
                    .filter(book => book.author !== user.name) // Excluir los libros del usuario
                    .sort((a, b) => b.likes - a.likes)
                    .slice(0, 6);
            }
            
            // Algoritmo de recomendación basado en:
            // 1. Autores que le gustan al usuario
            // 2. Géneros favoritos del usuario
            // 3. Libros con descripciones similares
            // 4. Libros populares que aún no ha likeado
            
            const likedAuthors = [...new Set(likedBooks.map(book => book.author))];
            const likedGenres = [...new Set(likedBooks.map(book => book.genre))];
            
            // Obtener palabras clave de los libros que le gustan
            const keywords = extractKeywords(likedBooks);
            
            // Calcular puntuación para cada libro
            const scoredBooks = books.map(book => {
                if (user.likedBooks.includes(book.id) || book.author === user.name) {
                    return { ...book, score: 0 }; // Excluir libros que ya le gustan o son del usuario
                }
                
                let score = 0;
                
                // Puntos por autor favorito
                if (likedAuthors.includes(book.author)) {
                    score += 3;
                }
                
                // Puntos por género favorito
                if (likedGenres.includes(book.genre)) {
                    score += 4;
                }
                
                // Puntos por palabras clave en el título
                keywords.forEach(keyword => {
                    if (book.title.toLowerCase().includes(keyword)) {
                        score += 2;
                    }
                });
                
                // Puntos por palabras clave en la descripción
                keywords.forEach(keyword => {
                    if (book.description.toLowerCase().includes(keyword)) {
                        score += 1;
                    }
                });
                
                // Puntos por popularidad (likes)
                score += book.likes * 0.1;
                
                return { ...book, score };
            });
            
            // Ordenar por puntuación y devolver los mejores
            return scoredBooks
                .filter(book => book.score > 0)
                .sort((a, b) => b.score - a.score)
                .slice(0, 6);
        }
        
        // Función para extraer palabras clave de los libros
        function extractKeywords(likedBooks) {
            const commonWords = ['el', 'la', 'los', 'las', 'de', 'del', 'y', 'en', 'un', 'una', 'unos', 'unas', 'con', 'para', 'por', 'sin', 'sobre', 'entre', 'hacia', 'hasta', 'desde', 'que', 'como', 'cuando', 'donde', 'quien', 'cual', 'cuyo', 'cuyos', 'cuyas', 'cuyo', 'cuyas', 'su', 'sus', 'se', 'lo', 'le', 'les', 'me', 'te', 'nos', 'os', 'mi', 'tu', 'nuestro', 'vuestro', 'mío', 'tuyo', 'suyo', 'este', 'ese', 'aquel', 'esto', 'eso', 'aquello', 'algo', 'nada', 'todo', 'alguien', 'nadie', 'cada', 'cualquier', 'otro', 'mismo', 'tal', 'tanto', 'mucho', 'poco', 'alguno', 'ninguno', 'varios', 'varias', 'demasiado', 'bastante', 'más', 'menos', 'muy', 'tan', 'tanto', 'como', 'así', 'aquí', 'allí', 'ahí', 'allá', 'acá', 'ahora', 'antes', 'después', 'luego', 'siempre', 'nunca', 'jamás', 'también', 'tampoco', 'además', 'incluso', 'hasta', 'inclusive', 'excepto', 'salvo', 'menos', 'aunque', 'pero', 'mas', 'sino', 'sin embargo', 'no obstante', 'porque', 'pues', 'puesto que', 'ya que', 'como', 'así que', 'por tanto', 'por consiguiente', 'entonces', 'luego', 'así', 'de este modo', 'de esta manera', 'por ejemplo', 'es decir', 'o sea', 'esto es', 'a saber', 'en otras palabras', 'en resumen', 'en conclusión', 'finalmente', 'por último', 'para terminar', 'en fin'];
            
            const allText = likedBooks.map(book => 
                `${book.title} ${book.description}`
            ).join(' ').toLowerCase();
            
            const words = allText.split(/\W+/).filter(word => 
                word.length > 3 && !commonWords.includes(word)
            );
            
            // Contar frecuencia de palabras
            const wordCount = {};
            words.forEach(word => {
                wordCount[word] = (wordCount[word] || 0) + 1;
            });
            
            // Ordenar por frecuencia y tomar las 10 más comunes
            return Object.entries(wordCount)
                .sort((a, b) => b[1] - a[1])
                .slice(0, 10)
                .map(entry => entry[0]);
        }

        // Función para mostrar libros recomendados
        function displayRecommendedBooks() {
            const recommendedContainer = document.getElementById('recommended-books-container');
            const recommendedSection = document.getElementById('recommended-section');
            
            if (!auth.currentUser) {
                recommendedSection.innerHTML = `
                    <h2 class="section-title">Libros Recomendados para Ti</h2>
                    <div class="empty-state">
                        <i class="fas fa-user-plus"></i>
                        <h3>Inicia sesión para obtener recomendaciones personalizadas</h3>
                        <p>Al iniciar sesión, nuestro sistema analizará tus gustos y te sugerirá libros que podrían interesarte.</p>
                        <button class="btn" id="login-from-recommendations">Iniciar Sesión</button>
                    </div>
                `;
                
                document.getElementById('login-from-recommendations').addEventListener('click', function() {
                    document.getElementById('auth-modal').style.display = 'flex';
                });
                
                return;
            }
            
            const recommendedBooks = getRecommendedBooks();
            
            if (recommendedBooks.length === 0) {
                recommendedContainer.innerHTML = `
                    <div class="empty-state" style="grid-column: 1 / -1;">
                        <i class="fas fa-book"></i>
                        <h3>No hay suficientes datos para recomendaciones</h3>
                        <p>Likea algunos libros para que podamos entender tus preferencias y recomendarte contenido similar.</p>
                        <button class="btn" onclick="switchSection('biblioteca')">Explorar Biblioteca</button>
                    </div>
                `;
                return;
            }
            
            recommendedContainer.innerHTML = '';
            
            recommendedBooks.forEach(book => {
                const isLiked = auth.currentUser.likedBooks.includes(book.id);
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                bookCard.innerHTML = `
                    <div class="book-cover">
                        ${book.title.split(' ').map(word => word[0]).join('')}
                        <div class="recommendation-badge">Recomendado</div>
                        <div class="book-actions">
                            <div class="book-action like-btn ${isLiked ? 'liked' : ''}" data-id="${book.id}">
                                <i class="fas fa-heart"></i>
                            </div>
                        </div>
                    </div>
                    <div class="book-info">
                        <div class="book-title">${book.title}</div>
                        <div class="book-author">por ${book.author}</div>
                        <div class="book-description">${book.description}</div>
                        <div class="book-genre">${genreNames[book.genre]}</div>
                        <div class="book-stats">
                            <div class="book-stat">
                                <i class="fas fa-heart"></i> <span class="like-count">${book.likes}</span>
                            </div>
                            <div class="book-stat">
                                <i class="fas fa-comment"></i> ${book.reviews.length}
                            </div>
                        </div>
                        <button class="btn read-book" style="width: 100%; margin-top: 10px;" data-id="${book.id}">Leer Libro</button>
                    </div>
                `;
                recommendedContainer.appendChild(bookCard);
            });

            // Agregar event listeners
            document.querySelectorAll('#recommended-books-container .read-book').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    openBook(bookId);
                });
            });

            document.querySelectorAll('#recommended-books-container .like-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    toggleLike(bookId);
                });
            });
        }

        // Función para cambiar entre secciones
        function switchSection(sectionId) {
            // Ocultar todas las secciones
            document.querySelectorAll('.main-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Mostrar la sección seleccionada
            document.getElementById(sectionId).classList.add('active');
            
            // Actualizar navegación activa
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            document.querySelector(`.nav-link[data-section="${sectionId}"]`).classList.add('active');
            
            // Actualizar contenido específico de la sección
            if (sectionId === 'inicio') {
                updateHomeStats();
                displayFeaturedBooks();
                displayRecommendedBooks();
            } else if (sectionId === 'biblioteca') {
                displayBooks();
                displayGenreFilters();
            } else if (sectionId === 'perfil') {
                updateProfile();
            }
        }

        // Función para mostrar libros en la biblioteca
        function displayBooks() {
            const booksContainer = document.getElementById('books-container');
            
            // Aplicar filtros
            let filteredBooks = [...books];
            
            // Filtrar por búsqueda
            if (searchTerm) {
                filteredBooks = filteredBooks.filter(book => 
                    book.title.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    book.author.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    book.description.toLowerCase().includes(searchTerm.toLowerCase())
                );
            }
            
            // Filtrar por género
            if (selectedGenre !== 'all') {
                filteredBooks = filteredBooks.filter(book => book.genre === selectedGenre);
            }
            
            // Aplicar filtro adicional (liked, my-books)
            const filterType = document.getElementById('filter-books').value;
            if (filterType === 'liked' && auth.currentUser) {
                filteredBooks = filteredBooks.filter(book => 
                    auth.currentUser.likedBooks.includes(book.id)
                );
            } else if (filterType === 'my-books' && auth.currentUser) {
                filteredBooks = filteredBooks.filter(book => 
                    book.author === auth.currentUser.name
                );
            }
            
            if (filteredBooks.length === 0) {
                booksContainer.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-book-open"></i>
                        <h3>No se encontraron libros</h3>
                        <p>Prueba a cambiar los filtros de búsqueda para ver más resultados.</p>
                    </div>
                `;
                return;
            }
            
            booksContainer.innerHTML = '';
            
            filteredBooks.forEach(book => {
                const author = authors.find(a => a.id === book.authorId) || { name: book.author, followers: 0, isFollowed: false };
                const isLiked = auth.currentUser && auth.currentUser.likedBooks.includes(book.id);
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                bookCard.innerHTML = `
                    <div class="book-cover">
                        ${book.title.split(' ').map(word => word[0]).join('')}
                        <div class="book-actions">
                            <div class="book-action like-btn ${isLiked ? 'liked' : ''}" data-id="${book.id}">
                                <i class="fas fa-heart"></i>
                            </div>
                        </div>
                    </div>
                    <div class="book-info">
                        <div class="book-title">${book.title}</div>
                        <div class="book-author">por ${book.author}</div>
                        <div class="book-description">${book.description}</div>
                        <div class="book-genre">${genreNames[book.genre]}</div>
                        <div class="book-stats">
                            <div class="book-stat">
                                <i class="fas fa-heart"></i> <span class="like-count">${book.likes}</span>
                            </div>
                            <div class="book-stat">
                                <i class="fas fa-comment"></i> ${book.reviews.length}
                            </div>
                        </div>
                        <button class="btn read-book" style="width: 100%; margin-top: 10px;" data-id="${book.id}">Leer Libro</button>
                    </div>
                `;
                booksContainer.appendChild(bookCard);
            });

            // Agregar event listeners a los botones de leer
            document.querySelectorAll('.read-book').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    openBook(bookId);
                });
            });

            // Agregar event listeners a los botones de like
            document.querySelectorAll('.like-btn').forEach(button => {
                button.addEventListener('click', function() {
                    if (!auth.currentUser) {
                        document.getElementById('auth-modal').style.display = 'flex';
                        return;
                    }
                    
                    const bookId = parseInt(this.getAttribute('data-id'));
                    toggleLike(bookId);
                });
            });
        }

        // Función para mostrar libros destacados en el inicio
        function displayFeaturedBooks() {
            const featuredContainer = document.getElementById('featured-books-container');
            
            if (books.length === 0) {
                featuredContainer.innerHTML = `
                    <div class="empty-state" style="grid-column: 1 / -1;">
                        <i class="fas fa-book"></i>
                        <h3>Aún no hay libros publicados</h3>
                        <p>Sé el primero en compartir tu obra con la comunidad.</p>
                    </div>
                `;
                return;
            }
            
            // Mostrar hasta 3 libros más populares
            const featuredBooks = [...books]
                .sort((a, b) => b.likes - a.likes)
                .slice(0, 3);
                
            featuredContainer.innerHTML = '';
            
            featuredBooks.forEach(book => {
                const isLiked = auth.currentUser && auth.currentUser.likedBooks.includes(book.id);
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                bookCard.innerHTML = `
                    <div class="book-cover">
                        ${book.title.split(' ').map(word => word[0]).join('')}
                        <div class="book-actions">
                            <div class="book-action like-btn ${isLiked ? 'liked' : ''}" data-id="${book.id}">
                                <i class="fas fa-heart"></i>
                            </div>
                        </div>
                    </div>
                    <div class="book-info">
                        <div class="book-title">${book.title}</div>
                        <div class="book-author">por ${book.author}</div>
                        <div class="book-description">${book.description}</div>
                        <div class="book-genre">${genreNames[book.genre]}</div>
                        <div class="book-stats">
                            <div class="book-stat">
                                <i class="fas fa-heart"></i> <span class="like-count">${book.likes}</span>
                            </div>
                        </div>
                        <button class="btn read-book" style="width: 100%; margin-top: 10px;" data-id="${book.id}">Leer Libro</button>
                    </div>
                `;
                featuredContainer.appendChild(bookCard);
            });

            // Agregar event listeners
            document.querySelectorAll('#featured-books-container .read-book').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    openBook(bookId);
                });
            });

            document.querySelectorAll('#featured-books-container .like-btn').forEach(button => {
                button.addEventListener('click', function() {
                    if (!auth.currentUser) {
                        document.getElementById('auth-modal').style.display = 'flex';
                        return;
                    }
                    
                    const bookId = parseInt(this.getAttribute('data-id'));
                    toggleLike(bookId);
                });
            });
        }

        // Función para actualizar estadísticas del inicio
        function updateHomeStats() {
            document.getElementById('total-books').textContent = books.length;
            document.getElementById('total-authors').textContent = authors.length;
            document.getElementById('total-likes').textContent = books.reduce((sum, book) => sum + book.likes, 0);
        }

        // Función para actualizar perfil de usuario
        function updateProfile() {
            if (!auth.currentUser) {
                document.getElementById('perfil').innerHTML = `
                    <div class="container">
                        <div class="empty-state">
                            <i class="fas fa-user"></i>
                            <h3>Inicia sesión para ver tu perfil</h3>
                            <p>Necesitas tener una cuenta para acceder a esta sección.</p>
                            <button class="btn" id="login-from-profile">Iniciar Sesión</button>
                        </div>
                    </div>
                `;
                
                document.getElementById('login-from-profile').addEventListener('click', function() {
                    document.getElementById('auth-modal').style.display = 'flex';
                });
                
                return;
            }
            
            document.getElementById('profile-user-name').textContent = auth.currentUser.name;
            document.getElementById('profile-user-email').textContent = auth.currentUser.email;
            document.getElementById('profile-user-bio').textContent = auth.currentUser.bio || "Aquí puedes agregar una breve biografía sobre ti.";
            
            // Actualizar avatar
            loadUserAvatar();
            
            // Actualizar estadísticas del perfil
            const userBooks = books.filter(book => book.author === auth.currentUser.name);
            const userLikes = userBooks.reduce((sum, book) => sum + book.likes, 0);
            const userReviews = auth.currentUser.myReviews.length;
            
            document.getElementById('profile-books').textContent = userBooks.length;
            document.getElementById('profile-likes').textContent = userLikes;
            document.getElementById('profile-reviews').textContent = userReviews;
            
            // Actualizar pestañas del perfil
            displayMyBooks();
            displayLikedBooks();
            displayMyReviews();
        }

        // Función para mostrar libros del usuario en el perfil
        function displayMyBooks() {
            const myBooksContainer = document.getElementById('my-books-container');
            const userBooks = books.filter(book => book.author === auth.currentUser.name);
            
            if (userBooks.length === 0) {
                myBooksContainer.innerHTML = `
                    <div class="empty-state" style="grid-column: 1 / -1;">
                        <i class="fas fa-book"></i>
                        <h3>Aún no has publicado libros</h3>
                        <p>Comparte tu primera obra con la comunidad.</p>
                        <button class="btn" id="upload-first-profile">Publicar Mi Primer Libro</button>
                    </div>
                `;
                
                document.getElementById('upload-first-profile').addEventListener('click', function() {
                    document.getElementById('upload-modal').style.display = 'flex';
                });
                
                return;
            }
            
            myBooksContainer.innerHTML = '';
            
            userBooks.forEach(book => {
                const isLiked = auth.currentUser.likedBooks.includes(book.id);
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                bookCard.innerHTML = `
                    <div class="book-cover">
                        ${book.title.split(' ').map(word => word[0]).join('')}
                        <div class="book-actions">
                            <div class="book-action like-btn ${isLiked ? 'liked' : ''}" data-id="${book.id}">
                                <i class="fas fa-heart"></i>
                            </div>
                        </div>
                    </div>
                    <div class="book-info">
                        <div class="book-title">${book.title}</div>
                        <div class="book-author">por ${book.author}</div>
                        <div class="book-description">${book.description}</div>
                        <div class="book-genre">${genreNames[book.genre]}</div>
                        <div class="book-stats">
                            <div class="book-stat">
                                <i class="fas fa-heart"></i> <span class="like-count">${book.likes}</span>
                            </div>
                            <div class="book-stat">
                                <i class="fas fa-comment"></i> ${book.reviews.length}
                            </div>
                        </div>
                        <button class="btn read-book" style="width: 100%; margin-top: 10px;" data-id="${book.id}">Leer Libro</button>
                    </div>
                `;
                myBooksContainer.appendChild(bookCard);
            });

            // Agregar event listeners
            document.querySelectorAll('#my-books-container .read-book').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    openBook(bookId);
                });
            });

            document.querySelectorAll('#my-books-container .like-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    toggleLike(bookId);
                });
            });
        }

        // Función para mostrar libros que le gustan al usuario
        function displayLikedBooks() {
            const likedBooksContainer = document.getElementById('liked-books-container');
            const likedBooks = books.filter(book => auth.currentUser.likedBooks.includes(book.id));
            
            if (likedBooks.length === 0) {
                likedBooksContainer.innerHTML = `
                    <div class="empty-state" style="grid-column: 1 / -1;">
                        <i class="fas fa-heart"></i>
                        <h3>Aún no te gusta ningún libro</h3>
                        <p>Explora la biblioteca y marca los libros que te gusten.</p>
                        <button class="btn" onclick="switchSection('biblioteca')">Explorar Biblioteca</button>
                    </div>
                `;
                return;
            }
            
            likedBooksContainer.innerHTML = '';
            
            likedBooks.forEach(book => {
                const bookCard = document.createElement('div');
                bookCard.className = 'book-card';
                bookCard.innerHTML = `
                    <div class="book-cover">
                        ${book.title.split(' ').map(word => word[0]).join('')}
                        <div class="book-actions">
                            <div class="book-action like-btn liked" data-id="${book.id}">
                                <i class="fas fa-heart"></i>
                            </div>
                        </div>
                    </div>
                    <div class="book-info">
                        <div class="book-title">${book.title}</div>
                        <div class="book-author">por ${book.author}</div>
                        <div class="book-description">${book.description}</div>
                        <div class="book-genre">${genreNames[book.genre]}</div>
                        <div class="book-stats">
                            <div class="book-stat">
                                <i class="fas fa-heart"></i> <span class="like-count">${book.likes}</span>
                            </div>
                            <div class="book-stat">
                                <i class="fas fa-comment"></i> ${book.reviews.length}
                            </div>
                        </div>
                        <button class="btn read-book" style="width: 100%; margin-top: 10px;" data-id="${book.id}">Leer Libro</button>
                    </div>
                `;
                likedBooksContainer.appendChild(bookCard);
            });

            // Agregar event listeners
            document.querySelectorAll('#liked-books-container .read-book').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    openBook(bookId);
                });
            });

            document.querySelectorAll('#liked-books-container .like-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const bookId = parseInt(this.getAttribute('data-id'));
                    toggleLike(bookId);
                });
            });
        }

        // Función para mostrar reseñas del usuario
        function displayMyReviews() {
            const myReviewsContainer = document.getElementById('my-reviews-container');
            
            if (auth.currentUser.myReviews.length === 0) {
                myReviewsContainer.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-comment"></i>
                        <h3>Aún no has escrito reseñas</h3>
                        <p>Lee algunos libros y comparte tus opiniones con la comunidad.</p>
                    </div>
                `;
                return;
            }
            
            myReviewsContainer.innerHTML = '';
            
            auth.currentUser.myReviews.forEach(review => {
                const reviewElement = document.createElement('div');
                reviewElement.className = 'review';
                reviewElement.innerHTML = `
                    <div class="review-header">
                        <div class="review-author">Para: ${review.bookTitle}</div>
                        <div class="review-date">${review.date}</div>
                    </div>
                    <div class="review-rating">${'★'.repeat(review.rating)}${'☆'.repeat(5-review.rating)}</div>
                    <div class="review-content">${review.content}</div>
                `;
                myReviewsContainer.appendChild(reviewElement);
            });
        }

        // Función para abrir un libro en el lector
        function openBook(bookId) {
            currentBook = books.find(book => book.id === bookId);
            if (!currentBook) return;

            document.getElementById('reader-title').textContent = currentBook.title;
            
            // Mostrar el lector y ocultar otras secciones
            document.getElementById('reader').style.display = 'block';
            document.querySelectorAll('.main-section').forEach(section => {
                section.style.display = 'none';
            });
            document.querySelector('header').style.display = 'none';
            document.querySelector('footer').style.display = 'none';

            // Mostrar la primera página
            currentPage = 0;
            displayPage();

            // Mostrar reseñas
            displayReviews();
        }

        // Función para mostrar la página actual
        function displayPage() {
            if (!currentBook) return;

            const content = currentBook.content;
            const words = content.split(' ');
            const startIndex = currentPage * wordsPerPage;
            const endIndex = Math.min(startIndex + wordsPerPage, words.length);
            
            const pageContent = words.slice(startIndex, endIndex).join(' ');
            document.getElementById('reader-content').textContent = pageContent;
            
            // Actualizar información de página
            const totalPages = Math.ceil(words.length / wordsPerPage);
            document.getElementById('page-info').textContent = `Página ${currentPage + 1} de ${totalPages}`;
            
            // Habilitar/deshabilitar botones según la página
            document.getElementById('prev-page').disabled = currentPage === 0;
            document.getElementById('next-page').disabled = currentPage >= totalPages - 1;
        }

        // Función para mostrar reseñas
        function displayReviews() {
            if (!currentBook) return;
            
            const reviewsContainer = document.getElementById('reviews-container');
            reviewsContainer.innerHTML = '';
            
            if (currentBook.reviews.length === 0) {
                reviewsContainer.innerHTML = '<p>Aún no hay reseñas para este libro. ¡Sé el primero en opinar!</p>';
                return;
            }
            
            currentBook.reviews.forEach(review => {
                const reviewElement = document.createElement('div');
                reviewElement.className = 'review';
                reviewElement.innerHTML = `
                    <div class="review-header">
                        <div class="review-author">${review.user}</div>
                        <div class="review-date">${review.date}</div>
                    </div>
                    <div class="review-rating">${'★'.repeat(review.rating)}${'☆'.repeat(5-review.rating)}</div>
                    <div class="review-content">${review.content}</div>
                `;
                reviewsContainer.appendChild(reviewElement);
            });
        }

        // Función para alternar like en un libro
        function toggleLike(bookId) {
            const book = books.find(b => b.id === bookId);
            if (!book) return;
            
            const isLiked = auth.currentUser.likedBooks.includes(bookId);
            
            if (isLiked) {
                // Quitar like
                auth.currentUser.likedBooks = auth.currentUser.likedBooks.filter(id => id !== bookId);
                book.likes--;
            } else {
                // Agregar like
                auth.currentUser.likedBooks.push(bookId);
                book.likes++;
            }
            
            saveData();
            
            // Actualizar todas las vistas
            displayBooks();
            displayFeaturedBooks();
            displayRecommendedBooks();
            if (document.getElementById('perfil').classList.contains('active')) {
                updateProfile();
            }
        }

        // Función para cerrar el lector
        function closeReader() {
            document.getElementById('reader').style.display = 'none';
            document.querySelectorAll('.main-section').forEach(section => {
                section.style.display = 'block';
            });
            document.querySelector('header').style.display = 'block';
            document.querySelector('footer').style.display = 'block';
            
            // Mostrar la sección activa
            const activeSection = document.querySelector('.main-section.active');
            if (activeSection) {
                activeSection.style.display = 'block';
            }
            
            currentBook = null;
        }

        // Función para manejar el envío del formulario de libro
        function handleFormSubmit(e) {
            e.preventDefault();
            
            if (!auth.currentUser) {
                alert('Debes iniciar sesión para publicar un libro.');
                document.getElementById('auth-modal').style.display = 'flex';
                return;
            }
            
            const title = document.getElementById('book-title').value;
            const authorName = auth.currentUser.name;
            const genre = document.getElementById('book-genre').value;
            const description = document.getElementById('book-description').value;
            const content = document.getElementById('book-content').value;
            
            // Verificar si el autor ya existe
            let authorId;
            const existingAuthor = authors.find(a => a.name === authorName);
            if (existingAuthor) {
                authorId = existingAuthor.id;
            } else {
                authorId = authors.length > 0 ? Math.max(...authors.map(a => a.id)) + 1 : 1;
                authors.push({
                    id: authorId,
                    name: authorName,
                    bio: auth.currentUser.bio,
                    followers: 0,
                    isFollowed: false
                });
            }
            
            // Crear nuevo libro
            const newBook = {
                id: books.length > 0 ? Math.max(...books.map(b => b.id)) + 1 : 1,
                title,
                author: authorName,
                authorId,
                genre,
                description,
                content,
                likes: 0,
                reviews: []
            };
            
            // Agregar a la lista de libros
            books.push(newBook);
            
            // Guardar datos
            saveData();
            
            // Actualizar todas las vistas
            displayBooks();
            displayFeaturedBooks();
            displayRecommendedBooks();
            updateHomeStats();
            if (document.getElementById('perfil').classList.contains('active')) {
                updateProfile();
            }
            
            // Cerrar modal y limpiar formulario
            document.getElementById('upload-modal').style.display = 'none';
            document.getElementById('upload-form').reset();
            
            // Mostrar mensaje de éxito
            alert('¡Libro publicado exitosamente!');
        }

        // Función para manejar el envío del formulario de perfil
        function handleProfileFormSubmit(e) {
            e.preventDefault();
            
            const newName = document.getElementById('edit-user-name').value;
            const newBio = document.getElementById('edit-user-bio').value;
            const avatarFile = document.getElementById('edit-user-avatar').files[0];
            
            // Actualizar datos del usuario
            auth.currentUser.name = newName;
            auth.currentUser.bio = newBio;
            
            // Procesar avatar si se seleccionó un archivo
            if (avatarFile) {
                if (avatarFile.size > 2 * 1024 * 1024) {
                    alert('La imagen es demasiado grande. Por favor, selecciona una imagen de menos de 2MB.');
                    return;
                }
                
                const reader = new FileReader();
                reader.onload = function(e) {
                    auth.currentUser.avatar = e.target.result;
                    saveData();
                    updateProfile();
                    document.getElementById('edit-profile-modal').style.display = 'none';
                    alert('Perfil actualizado correctamente');
                };
                reader.readAsDataURL(avatarFile);
            } else {
                saveData();
                updateProfile();
                document.getElementById('edit-profile-modal').style.display = 'none';
                alert('Perfil actualizado correctamente');
            }
        }

        // Función para manejar el envío del formulario de inicio de sesión
        function handleLoginFormSubmit(e) {
            e.preventDefault();
            
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            // Limpiar mensajes de error
            document.querySelectorAll('#login-form .error-message').forEach(el => {
                el.style.display = 'none';
                el.textContent = '';
            });
            
            auth.signInWithEmailAndPassword(email, password)
                .then((result) => {
                    document.getElementById('auth-modal').style.display = 'none';
                    document.getElementById('login-form').reset();
                    alert(`¡Bienvenido/a de nuevo, ${result.user.name}!`);
                })
                .catch((error) => {
                    // Mostrar mensaje de error
                    if (error.code === 'auth/wrong-password') {
                        document.getElementById('login-password-error').textContent = error.message;
                        document.getElementById('login-password-error').style.display = 'block';
                    } else {
                        document.getElementById('login-email-error').textContent = error.message;
                        document.getElementById('login-email-error').style.display = 'block';
                    }
                });
        }

        // Función para manejar el envío del formulario de registro
        function handleRegisterFormSubmit(e) {
            e.preventDefault();
            
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            const confirmPassword = document.getElementById('register-confirm-password').value;
            
            // Limpiar mensajes de error
            document.querySelectorAll('#register-form .error-message').forEach(el => {
                el.style.display = 'none';
                el.textContent = '';
            });
            
            // Validar contraseñas
            if (password !== confirmPassword) {
                document.getElementById('register-confirm-password-error').textContent = 'Las contraseñas no coinciden.';
                document.getElementById('register-confirm-password-error').style.display = 'block';
                return;
            }
            
            // Validar longitud de contraseña
            if (password.length < 6) {
                document.getElementById('register-password-error').textContent = 'La contraseña debe tener al menos 6 caracteres.';
                document.getElementById('register-password-error').style.display = 'block';
                return;
            }
            
            auth.createUserWithEmailAndPassword(email, password, name)
                .then((result) => {
                    document.getElementById('auth-modal').style.display = 'none';
                    document.getElementById('register-form').reset();
                    alert(`¡Bienvenido/a a Publibros, ${result.user.name}!`);
                })
                .catch((error) => {
                    // Mostrar mensaje de error
                    if (error.code === 'auth/email-already-in-use') {
                        document.getElementById('register-email-error').textContent = error.message;
                        document.getElementById('register-email-error').style.display = 'block';
                    } else {
                        document.getElementById('register-name-error').textContent = error.message;
                        document.getElementById('register-name-error').style.display = 'block';
                    }
                });
        }

        // Inicialización cuando se carga la página
        document.addEventListener('DOMContentLoaded', function() {
            // Configurar listener para cambios de autenticación
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
            
            // Configurar navegación
            document.querySelectorAll('.nav-link, .nav-link-footer').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const sectionId = this.getAttribute('data-section');
                    switchSection(sectionId);
                });
            });
            
            // Configurar botones de la página de inicio
            document.getElementById('explore-library').addEventListener('click', function() {
                switchSection('biblioteca');
            });
            
            document.getElementById('upload-first-book').addEventListener('click', function() {
                if (auth.currentUser) {
                    document.getElementById('upload-modal').style.display = 'flex';
                } else {
                    document.getElementById('auth-modal').style.display = 'flex';
                }
            });
            
            // Configurar botón de subir libro en biblioteca
            document.getElementById('upload-book-btn').addEventListener('click', function() {
                if (auth.currentUser) {
                    document.getElementById('upload-modal').style.display = 'flex';
                } else {
                    document.getElementById('auth-modal').style.display = 'flex';
                }
            });
            
            // Configurar búsqueda de libros
            document.getElementById('search-books').addEventListener('input', function() {
                searchTerm = this.value;
                displayBooks();
            });
            
            // Configurar filtro de libros
            document.getElementById('filter-books').addEventListener('change', function() {
                displayBooks();
            });
            
            // Configurar modal de autenticación
            document.getElementById('auth-btn').addEventListener('click', function() {
                if (auth.currentUser) {
                    // Si ya está autenticado, mostrar menú de usuario
                    if (confirm('¿Deseas cerrar sesión?')) {
                        auth.signOut();
                    }
                } else {
                    document.getElementById('auth-modal').style.display = 'flex';
                }
            });
            
            document.getElementById('close-auth-modal').addEventListener('click', function() {
                document.getElementById('auth-modal').style.display = 'none';
                // Limpiar formularios
                document.getElementById('login-form').reset();
                document.getElementById('register-form').reset();
                // Limpiar mensajes de error
                document.querySelectorAll('.error-message').forEach(el => {
                    el.style.display = 'none';
                });
            });
            
            // Configurar pestañas de autenticación
            document.querySelectorAll('.auth-tab').forEach(tab => {
                tab.addEventListener('click', function() {
                    // Remover clase active de todas las pestañas
                    document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
                    // Agregar clase active a la pestaña clickeada
                    this.classList.add('active');
                    
                    // Mostrar el formulario correspondiente
                    const formId = this.getAttribute('data-form') + '-form';
                    document.querySelectorAll('.auth-form').forEach(form => {
                        form.classList.remove('active');
                    });
                    document.getElementById(formId).classList.add('active');
                    
                    // Actualizar título del modal
                    document.getElementById('auth-modal-title').textContent = 
                        this.getAttribute('data-form') === 'login' ? 'Iniciar Sesión' : 'Registrarse';
                });
            });
            
            // Configurar switches entre formularios
            document.getElementById('switch-to-register').addEventListener('click', function() {
                document.querySelector('.auth-tab[data-form="register"]').click();
            });
            
            document.getElementById('switch-to-login').addEventListener('click', function() {
                document.querySelector('.auth-tab[data-form="login"]').click();
            });
            
            // Configurar formularios de autenticación
            document.getElementById('login-form').addEventListener('submit', handleLoginFormSubmit);
            document.getElementById('register-form').addEventListener('submit', handleRegisterFormSubmit);
            
            // Configurar modal de subida
            document.getElementById('close-upload-modal').addEventListener('click', function() {
                document.getElementById('upload-modal').style.display = 'none';
            });
            
            // Configurar formulario de subida
            document.getElementById('upload-form').addEventListener('submit', handleFormSubmit);
            
            // Configurar modal de edición de perfil
            document.getElementById('edit-profile-btn').addEventListener('click', function() {
                if (!auth.currentUser) {
                    document.getElementById('auth-modal').style.display = 'flex';
                    return;
                }
                
                document.getElementById('edit-user-name').value = auth.currentUser.name;
                document.getElementById('edit-user-bio').value = auth.currentUser.bio || '';
                document.getElementById('edit-user-avatar').value = '';
                document.getElementById('edit-profile-modal').style.display = 'flex';
            });
            
            document.getElementById('close-edit-profile-modal').addEventListener('click', function() {
                document.getElementById('edit-profile-modal').style.display = 'none';
            });
            
            // Configurar formulario de edición de perfil
            document.getElementById('edit-profile-form').addEventListener('submit', handleProfileFormSubmit);
            
            // Configurar avatar para edición
            document.getElementById('edit-avatar-overlay').addEventListener('click', function() {
                if (!auth.currentUser) {
                    document.getElementById('auth-modal').style.display = 'flex';
                    return;
                }
                
                document.getElementById('edit-profile-modal').style.display = 'flex';
            });
            
            // Configurar lector de libros
            document.getElementById('close-reader').addEventListener('click', closeReader);
            document.getElementById('prev-page').addEventListener('click', function() {
                if (currentPage > 0) {
                    currentPage--;
                    displayPage();
                }
            });
            document.getElementById('next-page').addEventListener('click', function() {
                const totalPages = Math.ceil(currentBook.content.split(' ').length / wordsPerPage);
                if (currentPage < totalPages - 1) {
                    currentPage++;
                    displayPage();
                }
            });
            
            // Configurar pestañas del perfil
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    // Remover clase active de todos los botones y contenidos
                    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
                    document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
                    
                    // Agregar clase active al botón clickeado
                    this.classList.add('active');
                    
                    // Mostrar el contenido correspondiente
                    const tabId = this.getAttribute('data-tab') + '-tab';
                    document.getElementById(tabId).classList.add('active');
                });
            });
            
            // Configurar envío de reseñas
            document.getElementById('submit-review').addEventListener('click', function() {
                if (!auth.currentUser) {
                    alert('Debes iniciar sesión para enviar una reseña.');
                    document.getElementById('auth-modal').style.display = 'flex';
                    return;
                }
                
                if (!currentBook) return;
                
                const rating = parseInt(document.getElementById('review-rating').value);
                const content = document.getElementById('review-content').value;
                
                if (!content.trim()) {
                    alert('Por favor, escribe tu reseña antes de enviarla.');
                    return;
                }
                
                const newReview = {
                    user: auth.currentUser.name,
                    rating,
                    content,
                    date: new Date().toISOString().split('T')[0]
                };
                
                // Agregar reseña al libro
                currentBook.reviews.push(newReview);
                
                // Agregar reseña al perfil del usuario
                auth.currentUser.myReviews.push({
                    bookTitle: currentBook.title,
                    bookId: currentBook.id,
                    rating,
                    content,
                    date: newReview.date
                });
                
                displayReviews();
                
                // Guardar datos
                saveData();
                
                // Limpiar el formulario de reseña
                document.getElementById('review-content').value = '';
                alert('¡Reseña enviada con éxito!');
            });
            
            // Tema oscuro/claro
            document.getElementById('theme-toggle').addEventListener('click', function() {
                document.body.classList.toggle('dark-theme');
                const icon = this.querySelector('i');
                if (document.body.classList.contains('dark-theme')) {
                    icon.className = 'fas fa-sun';
                    // Aquí podrías agregar más lógica para cambiar a tema oscuro
                } else {
                    icon.className = 'fas fa-moon';
                }
            });
            
            // Inicializar vistas
            updateHomeStats();
            displayFeaturedBooks();
            displayRecommendedBooks();
            displayBooks();
            displayGenreFilters();
            updateProfile();
        });
    </script>
</body>
</html>
