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

        .btn-danger {
            background-color: var(--accent);
        }

        .btn-danger:hover {
            background-color: #c0392b;
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

        /* Panel de administración */
        .admin-panel {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
        }

        .admin-badge {
            background: var(--accent);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            margin-left: 10px;
        }

        .report-reason {
            background: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 8px;
            padding: 1rem;
            margin: 0.5rem 0;
        }

        .verification-badge {
            display: inline-flex;
            align-items: center;
            background: #d4edda;
            color: #155724;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-left: 10px;
        }

        .verification-badge.unverified {
            background: #f8d7da;
            color: #721c24;
        }

        /* Estadísticas */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .stat-card {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            text-align: center;
            box-shadow: var(--shadow);
        }

        .stat-icon {
            font-size: 2.5rem;
            color: var(--secondary);
            margin-bottom: 1rem;
        }

        /* Acciones de biblioteca */
        .library-actions {
            display: flex;
            justify-content: space-between;
            margin-bottom: 2rem;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .search-filter {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
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
            
            .library-actions {
                flex-direction: column;
            }
            
            .search-filter {
                width: 100%;
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
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-icon">
                            <i class="fas fa-book"></i>
                        </div>
                        <div class="stat-value" id="total-books">0</div>
                        <div class="stat-label">Libros Publicados</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-icon">
                            <i class="fas fa-users"></i>
                        </div>
                        <div class="stat-value" id="total-authors">0</div>
                        <div class="stat-label">Autores Registrados</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-icon">
                            <i class="fas fa-heart"></i>
                        </div>
                        <div class="stat-value" id="total-likes">0</div>
                        <div class="stat-label">Likes Totales</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Sección Biblioteca -->
    <section id="biblioteca" class="main-section">
        <div class="container">
            <h2 class="section-title">Biblioteca de Libros</h2>
            
            <div class="library-actions">
                <button class="btn" id="upload-book-btn">
                    <i class="fas fa-plus"></i> Subir Nuevo Libro
                </button>
                <div class="search-filter">
                    <input type="text" id="search-books" class="form-control" placeholder="Buscar libros...">
                    <select id="filter-books" class="form-control">
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
                    <h2 class="user-name" id="profile-user-name">Usuario
                        <span id="verification-badge" class="verification-badge unverified" style="display: none;">
                            <i class="fas fa-times-circle"></i> No verificado
                        </span>
                        <span id="admin-badge" class="admin-badge" style="display: none;">Admin</span>
                    </h2>
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
                <button class="btn btn-secondary" id="resend-verification" style="display: none;">
                    <i class="fas fa-envelope"></i> Reenviar Verificación
                </button>
            </div>

            <!-- Panel de Administración -->
            <div id="admin-panel" class="admin-panel" style="display: none;">
                <h3 class="section-title">Panel de Moderación</h3>
                
                <div class="tabs-header">
                    <button class="tab-btn active" data-tab="pending-books">Libros Pendientes</button>
                    <button class="tab-btn" data-tab="reported-books">Libros Reportados</button>
                    <button class="tab-btn" data-tab="user-management">Gestión de Usuarios</button>
                </div>
                
                <div class="tab-content active" id="pending-books-tab">
                    <h3>Libros Pendientes de Aprobación</h3>
                    <div class="books-grid" id="pending-books-container">
                        <!-- Los libros pendientes se cargarán aquí -->
                    </div>
                </div>
                
                <div class="tab-content" id="reported-books-tab">
                    <h3>Libros Reportados</h3>
                    <div id="reported-books-container">
                        <!-- Los libros reportados se cargarán aquí -->
                    </div>
                </div>
                
                <div class="tab-content" id="user-management-tab">
                    <h3>Gestión de Usuarios</h3>
                    <div id="users-container">
                        <!-- Los usuarios se cargarán aquí -->
                    </div>
                </div>
            </div>

            <div class="profile-tabs">
                <div class="tabs-header">
                    <button class="tab-btn active" data-tab="my-books">Mis Libros</button>
                    <button class="tab-btn" data-tab="liked-books">Libros que Me Gustan</button>
                    <button class="tab-btn" data-tab="my-reviews">Mis Reseñas</button>
                </div>
                
                <div class="tab-content active" id="my-books-tab">
                    <h3>Mis Libros Publicados</h3>
                    <div class="books-grid" id="my-books-container">
                        <!-- Los libros del usuario se cargarán aquí -->
                    </div>
                </div>
                
                <div class="tab-content" id="liked-books-tab">
                    <h3>Libros que Me Gustan</h3>
                    <div class="books-grid" id="liked-books-container">
                        <!-- Los libros que le gustan al usuario se cargarán aquí -->
                    </div>
                </div>
                
                <div class="tab-content" id="my-reviews-tab">
                    <h3>Mis Reseñas</h3>
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
                <button type="submit" class="btn">Iniciar Sesión</button>
                <div class="form-footer">
                    <a href="#" id="forgot-password">¿Olvidaste tu contraseña?</a>
                    <br>
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
                <button type="submit" class="btn">Registrarse</button>
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
                <button type="submit" class="btn">Publicar Libro</button>
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
                    <small>Selecciona una imagen para tu perfil (máx. 2MB)</small>
                </div>
                <button type="submit" class="btn">Guardar Cambios</button>
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
                    <p><a href="#" class="nav-link-footer" data-section="inicio">Inicio</a></p>
                    <p><a href="#" class="nav-link-footer" data-section="biblioteca">Biblioteca</a></p>
                    <p><a href="#" class="nav-link-footer" data-section="perfil">Mi Perfil</a></p>
                </div>
                <div class="footer-section">
                    <h3>Sobre Nosotros</h3>
                    <p>Publibros nació con la misión de crear un espacio donde los amantes de la literatura puedan compartir sus creaciones y descubrir nuevas voces.</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 Publibros. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-auth-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-storage-compat.js"></script>
    
    <!-- JavaScript -->
    <script>
        // Configuración de Firebase
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
        try {
            const app = firebase.initializeApp(firebaseConfig);
            const auth = firebase.auth();
            const db = firebase.firestore();
            const storage = firebase.storage();
            
            console.log("Firebase inicializado correctamente");
        } catch (error) {
            console.error("Error inicializando Firebase:", error);
        }

        // Referencias a colecciones de Firestore
        const usersRef = db.collection("users");
        const booksRef = db.collection("books");

        // Géneros disponibles
        const genres = [
            "romance", "thriller", "terror", "fantasia", "ciencia-ficcion", 
            "misterio", "aventura", "drama", "poesia", "biografia", 
            "historico", "infantil", "juvenil", "autoayuda", "otros"
        ];

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

        // Variables para el lector
        let currentBook = null;
        let currentPage = 0;
        const wordsPerPage = 300;
        let bookPages = [];

        // Variables para filtros
        let selectedGenre = 'all';
        let searchTerm = '';
        let currentFilter = 'all';

        // Listeners de tiempo real
        let booksListener = null;
        let usersListener = null;

        // ============================
        // LISTENERS DE TIEMPO REAL
        // ============================

        // Función para iniciar listeners de tiempo real
        function startRealTimeListeners() {
            // Listener para libros
            booksListener = booksRef.orderBy('createdAt', 'desc').onSnapshot(
                (snapshot) => {
                    console.log("Actualización en tiempo real de libros recibida");
                    updateBooksStats();
                    updateProfileStats();
                    
                    // Si estamos en la sección de biblioteca, actualizar la vista
                    if (document.getElementById('biblioteca').classList.contains('active')) {
                        displayBooks();
                    }
                    
                    // Si estamos en la sección de inicio, actualizar libros destacados y recomendados
                    if (document.getElementById('inicio').classList.contains('active')) {
                        displayFeaturedBooks();
                        displayRecommendedBooks();
                    }
                },
                (error) => {
                    console.error("Error en listener de libros:", error);
                }
            );
            
            // Listener para usuarios
            usersListener = usersRef.onSnapshot(
                (snapshot) => {
                    console.log("Actualización en tiempo real de usuarios recibida");
                    updateUsersStats();
                },
                (error) => {
                    console.error("Error en listener de usuarios:", error);
                }
            );
        }

        // Función para detener listeners de tiempo real
        function stopRealTimeListeners() {
            if (booksListener) {
                booksListener();
                booksListener = null;
            }
            if (usersListener) {
                usersListener();
                usersListener = null;
            }
        }

        // ============================
        // ACTUALIZACIONES DE ESTADÍSTICAS EN TIEMPO REAL
        // ============================

        // Función para actualizar estadísticas de libros
        async function updateBooksStats() {
            try {
                const snapshot = await booksRef.get();
                let totalBooks = 0;
                let totalLikes = 0;
                
                snapshot.forEach((doc) => {
                    totalBooks++;
                    const book = doc.data();
                    totalLikes += book.likes || 0;
                });
                
                // Actualizar DOM
                document.getElementById('total-books').textContent = totalBooks;
                document.getElementById('total-likes').textContent = totalLikes;
                
                console.log(`Estadísticas actualizadas: ${totalBooks} libros, ${totalLikes} likes`);
            } catch (error) {
                console.error("Error actualizando estadísticas de libros:", error);
            }
        }

        // Función para actualizar estadísticas de usuarios
        async function updateUsersStats() {
            try {
                const snapshot = await usersRef.get();
                const totalAuthors = snapshot.size;
                
                // Actualizar DOM
                document.getElementById('total-authors').textContent = totalAuthors;
                
                console.log(`Estadísticas actualizadas: ${totalAuthors} autores`);
            } catch (error) {
                console.error("Error actualizando estadísticas de usuarios:", error);
            }
        }

        // Función para actualizar estadísticas del perfil
        async function updateProfileStats() {
            const currentUser = auth.currentUser;
            if (!currentUser) return;
            
            try {
                const booksSnapshot = await booksRef.get();
                let userBooksCount = 0;
                let userLikesCount = 0;
                
                booksSnapshot.forEach((doc) => {
                    const book = doc.data();
                    if (book.authorId === currentUser.uid) {
                        userBooksCount++;
                        userLikesCount += book.likes || 0;
                    }
                });
                
                // Actualizar DOM
                document.getElementById('profile-books').textContent = userBooksCount;
                document.getElementById('profile-likes').textContent = userLikesCount;
                
                console.log(`Perfil actualizado: ${userBooksCount} libros, ${userLikesCount} likes`);
            } catch (error) {
                console.error("Error actualizando estadísticas del perfil:", error);
            }
        }

        // ============================
        // FUNCIONES DE NAVEGACIÓN Y UI
        // ============================

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
                if (link.getAttribute('data-section') === sectionId) {
                    link.classList.add('active');
                }
            });
            
            // Detener listeners anteriores y iniciar nuevos según la sección
            stopRealTimeListeners();
            
            // Cargar datos específicos de la sección
            if (sectionId === 'inicio') {
                startRealTimeListeners();
                loadHomeData();
            } else if (sectionId === 'biblioteca') {
                startRealTimeListeners();
                displayBooks();
                displayGenreFilters();
            } else if (sectionId === 'perfil') {
                startRealTimeListeners();
                updateProfile();
            }
        }

        // ============================
        // FUNCIONES DE FIREBASE
        // ============================

        // Función para cargar avatar de usuario desde Firebase Storage
        async function loadUserAvatar(userId) {
            const userAvatar = document.getElementById('user-avatar');
            const avatarPlaceholder = document.getElementById('avatar-placeholder');
            
            try {
                // Intentar cargar la imagen desde Firebase Storage
                const storageRef = storage.ref();
                const avatarRef = storageRef.child(`avatars/${userId}`);
                const avatarUrl = await avatarRef.getDownloadURL();
                
                avatarPlaceholder.style.display = 'none';
                let img = userAvatar.querySelector('img');
                if (!img) {
                    img = document.createElement('img');
                    userAvatar.insertBefore(img, avatarPlaceholder);
                }
                img.src = avatarUrl;
                img.alt = 'Avatar del usuario';
            } catch (error) {
                // Si no hay avatar, mostrar placeholder
                avatarPlaceholder.style.display = 'flex';
                const existingImg = userAvatar.querySelector('img');
                if (existingImg) {
                    existingImg.remove();
                }
                avatarPlaceholder.innerHTML = `<i class="fas fa-user"></i>`;
            }
        }

        // Función para guardar datos del usuario en Firestore
        async function saveUserData(userId, userData) {
            try {
                await usersRef.doc(userId).set(userData, { merge: true });
                return true;
            } catch (error) {
                console.error("Error guardando datos del usuario:", error);
                return false;
            }
        }

        // Función para obtener datos del usuario desde Firestore
        async function getUserData(userId) {
            try {
                const doc = await usersRef.doc(userId).get();
                return doc.exists ? doc.data() : null;
            } catch (error) {
                console.error("Error obteniendo datos del usuario:", error);
                return null;
            }
        }

        // Función para guardar un libro en Firestore
        async function saveBook(bookData) {
            try {
                const docRef = await booksRef.add({
                    ...bookData,
                    createdAt: firebase.firestore.FieldValue.serverTimestamp(),
                    updatedAt: firebase.firestore.FieldValue.serverTimestamp()
                });
                return docRef.id;
            } catch (error) {
                console.error("Error guardando libro:", error);
                return null;
            }
        }

        // Función para obtener todos los libros desde Firestore
        async function getAllBooks() {
            try {
                const snapshot = await booksRef.orderBy('createdAt', 'desc').get();
                const books = [];
                snapshot.forEach(doc => {
                    const bookData = doc.data();
                    books.push({
                        id: doc.id,
                        ...bookData,
                        // Asegurar que las fechas sean objetos Date
                        createdAt: bookData.createdAt ? bookData.createdAt.toDate() : new Date(),
                        updatedAt: bookData.updatedAt ? bookData.updatedAt.toDate() : new Date()
                    });
                });
                return books;
            } catch (error) {
                console.error("Error obteniendo libros:", error);
                return [];
            }
        }

        // Función para actualizar un libro en Firestore
        async function updateBook(bookId, updates) {
            try {
                await booksRef.doc(bookId).update({
                    ...updates,
                    updatedAt: firebase.firestore.FieldValue.serverTimestamp()
                });
                return true;
            } catch (error) {
                console.error("Error actualizando libro:", error);
                return false;
            }
        }

        // ============================
        // VERIFICACIÓN DE EMAIL
        // ============================

        // Función para reenviar verificación de email
        async function resendEmailVerification() {
            const user = auth.currentUser;
            if (!user) return;

            try {
                await user.sendEmailVerification();
                alert('Se ha enviado un nuevo email de verificación. Por favor, revisa tu bandeja de entrada.');
            } catch (error) {
                console.error("Error reenviando verificación:", error);
                alert('Error al reenviar el email de verificación. Intenta nuevamente.');
            }
        }

        // Verificar estado de verificación
        function checkEmailVerification() {
            const user = auth.currentUser;
            if (user) {
                user.reload().then(() => {
                    const verificationBadge = document.getElementById('verification-badge');
                    const resendButton = document.getElementById('resend-verification');
                    
                    if (user.emailVerified) {
                        verificationBadge.innerHTML = '<i class="fas fa-check-circle"></i> Verificado';
                        verificationBadge.className = 'verification-badge';
                        if (resendButton) resendButton.style.display = 'none';
                        
                        // Actualizar en Firestore
                        saveUserData(user.uid, { emailVerified: true });
                    } else {
                        verificationBadge.innerHTML = '<i class="fas fa-times-circle"></i> No verificado';
                        verificationBadge.className = 'verification-badge unverified';
                        if (resendButton) resendButton.style.display = 'inline-block';
                        verificationBadge.style.display = 'inline-flex';
                    }
                });
            }
        }

        // ============================
        // RECUPERACIÓN DE CONTRASEÑA
        // ============================

        // Función para recuperación de contraseña
        function handlePasswordReset() {
            const email = prompt('Por favor, ingresa tu email para restablecer la contraseña:');
            
            if (email) {
                auth.sendPasswordResetEmail(email)
                    .then(() => {
                        alert('Se ha enviado un email para restablecer tu contraseña. Revisa tu bandeja de entrada.');
                    })
                    .catch((error) => {
                        let errorMessage = "Error al enviar el email de recuperación";
                        switch(error.code) {
                            case 'auth/user-not-found':
                                errorMessage = 'No existe una cuenta con este email.';
                                break;
                            case 'auth/invalid-email':
                                errorMessage = 'El formato del email no es válido.';
                                break;
                            default:
                                errorMessage = error.message;
                        }
                        alert(errorMessage);
                    });
            }
        }

        // ============================
        // SISTEMA DE LIKES EN TIEMPO REAL
        // ============================

        // Función para manejar like/unlike de un libro
        async function handleLikeBook(bookId) {
            const currentUser = auth.currentUser;
            if (!currentUser) {
                alert('Debes iniciar sesión para dar like a un libro');
                return;
            }
            
            try {
                const bookDoc = await booksRef.doc(bookId).get();
                const book = bookDoc.data();
                const userData = await getUserData(currentUser.uid);
                
                let likedBooks = userData?.likedBooks || [];
                let currentLikes = book.likes || 0;
                let isLiked = likedBooks.includes(bookId);
                
                if (isLiked) {
                    // Quitar like
                    likedBooks = likedBooks.filter(id => id !== bookId);
                    currentLikes = Math.max(0, currentLikes - 1);
                } else {
                    // Agregar like
                    likedBooks.push(bookId);
                    currentLikes += 1;
                }
                
                // Actualizar libro
                await booksRef.doc(bookId).update({
                    likes: currentLikes
                });
                
                // Actualizar usuario
                await saveUserData(currentUser.uid, {
                    likedBooks: likedBooks
                });
                
                console.log(`Like ${isLiked ? 'quitado' : 'agregado'} al libro ${bookId}`);
            } catch (error) {
                console.error("Error manejando like:", error);
                alert('Error al procesar el like. Intenta nuevamente.');
            }
        }

        // ============================
        // FUNCIONES DE INTERFAZ
        // ============================

        // Función para cargar datos en la página de inicio
        async function loadHomeData() {
            await displayFeaturedBooks();
            await displayRecommendedBooks();
            // Las estadísticas se actualizan automáticamente por los listeners
        }

        // Función para mostrar libros destacados
        async function displayFeaturedBooks() {
            const container = document.getElementById('featured-books-container');
            const books = await getAllBooks();
            
            // Ordenar por likes y tomar los primeros 3
            const featuredBooks = books.sort((a, b) => (b.likes || 0) - (a.likes || 0)).slice(0, 3);
            
            if (featuredBooks.length === 0) {
                container.innerHTML = '<div class="empty-state"><i class="fas fa-book"></i><h3>No hay libros destacados</h3><p>Sé el primero en publicar un libro.</p></div>';
                return;
            }
            
            container.innerHTML = '';
            featuredBooks.forEach(book => {
                const bookCard = createBookCard(book);
                container.appendChild(bookCard);
            });
        }

        // Función para mostrar libros recomendados
        async function displayRecommendedBooks() {
            const container = document.getElementById('recommended-books-container');
            const books = await getAllBooks();
            
            // Por ahora, mostramos libros aleatorios como recomendados
            const recommendedBooks = books.sort(() => 0.5 - Math.random()).slice(0, 3);
            
            if (recommendedBooks.length === 0) {
                container.innerHTML = '';
                document.getElementById('recommended-section').style.display = 'none';
                return;
            }
            
            container.innerHTML = '';
            recommendedBooks.forEach(book => {
                const bookCard = createBookCard(book);
                // Agregar badge de recomendación
                const badge = document.createElement('div');
                badge.className = 'recommendation-badge';
                badge.innerHTML = '<i class="fas fa-star"></i> Recomendado';
                bookCard.querySelector('.book-cover').appendChild(badge);
                container.appendChild(bookCard);
            });
        }

        // Función para crear tarjeta de libro
        function createBookCard(book) {
            const bookCard = document.createElement('div');
            bookCard.className = 'book-card';
            bookCard.innerHTML = `
                <div class="book-cover">
                    ${book.title.split(' ').map(word => word[0]).join('')}
                </div>
                <div class="book-actions">
                    <div class="book-action like-btn" data-book-id="${book.id}">
                        <i class="fas fa-heart"></i>
                    </div>
                    <div class="book-action read-btn" data-book-id="${book.id}">
                        <i class="fas fa-book-open"></i>
                    </div>
                </div>
                <div class="book-info">
                    <div class="book-title">${book.title}</div>
                    <div class="book-author">por ${book.author}</div>
                    <div class="book-description">${book.description}</div>
                    <div class="book-genre">${genreNames[book.genre]}</div>
                    <div class="book-stats">
                        <div class="book-stat">
                            <i class="fas fa-heart"></i> <span class="like-count">${book.likes || 0}</span>
                        </div>
                        <div class="book-stat">
                            <i class="fas fa-eye"></i> ${book.views || 0}
                        </div>
                    </div>
                </div>
            `;
            
            // Event listeners para los botones
            bookCard.querySelector('.like-btn').addEventListener('click', function() {
                handleLikeBook(book.id);
            });
            
            bookCard.querySelector('.read-btn').addEventListener('click', function() {
                openReader(book);
            });
            
            return bookCard;
        }

        // Función para mostrar filtros de género
        function displayGenreFilters() {
            const genreContainer = document.getElementById('genre-filter-container');
            genreContainer.innerHTML = '';
            
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

        // Función para actualizar los filtros de género
        function updateGenreFilters() {
            document.querySelectorAll('.genre-chip').forEach(chip => {
                chip.classList.remove('active');
                if (chip.getAttribute('data-genre') === selectedGenre) {
                    chip.classList.add('active');
                }
            });
        }

        // Función para mostrar libros en la biblioteca
        async function displayBooks() {
            const container = document.getElementById('books-container');
            const books = await getAllBooks();
            
            // Aplicar filtros
            let filteredBooks = books;
            
            // Filtrar por género
            if (selectedGenre !== 'all') {
                filteredBooks = filteredBooks.filter(book => book.genre === selectedGenre);
            }
            
            // Filtrar por búsqueda
            if (searchTerm) {
                filteredBooks = filteredBooks.filter(book => 
                    book.title.toLowerCase().includes(searchTerm.toLowerCase()) || 
                    book.author.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    book.description.toLowerCase().includes(searchTerm.toLowerCase())
                );
            }
            
            // Filtrar por tipo (mis libros, me gusta, etc.)
            const currentUser = auth.currentUser;
            if (currentUser && currentFilter === 'my-books') {
                filteredBooks = filteredBooks.filter(book => book.authorId === currentUser.uid);
            } else if (currentUser && currentFilter === 'liked') {
                const userData = await getUserData(currentUser.uid);
                const likedBookIds = userData?.likedBooks || [];
                filteredBooks = filteredBooks.filter(book => likedBookIds.includes(book.id));
            }
            
            if (filteredBooks.length === 0) {
                container.innerHTML = '<div class="empty-state"><i class="fas fa-book"></i><h3>No se encontraron libros</h3><p>Intenta cambiar los filtros de búsqueda.</p></div>';
                return;
            }
            
            container.innerHTML = '';
            filteredBooks.forEach(book => {
                const bookCard = createBookCard(book);
                container.appendChild(bookCard);
            });
        }

        // Función para actualizar perfil de usuario
        async function updateProfile() {
            const currentUser = auth.currentUser;
            
            if (!currentUser) {
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
            
            const userData = await getUserData(currentUser.uid);
            
            document.getElementById('profile-user-name').textContent = userData?.name || currentUser.displayName || 'Usuario';
            document.getElementById('profile-user-email').textContent = currentUser.email;
            document.getElementById('profile-user-bio').textContent = userData?.bio || "Aquí puedes agregar una breve biografía sobre ti.";
            
            // Actualizar avatar
            loadUserAvatar(currentUser.uid);
            
            // Verificar estado de email
            checkEmailVerification();
            
            // Las estadísticas se actualizan automáticamente por los listeners
        }

        // ============================
        // INICIALIZACIÓN
        // ============================

        document.addEventListener('DOMContentLoaded', function() {
            // Configurar navegación
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const sectionId = this.getAttribute('data-section');
                    switchSection(sectionId);
                });
            });

            // Configurar navegación del footer
            document.querySelectorAll('.nav-link-footer').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const sectionId = this.getAttribute('data-section');
                    switchSection(sectionId);
                });
            });

            // Configurar listener para cambios de autenticación
            auth.onAuthStateChanged((user) => {
                const authStatus = document.getElementById('auth-status');
                const authBtn = document.getElementById('auth-btn');
                
                if (user) {
                    authStatus.textContent = user.displayName || user.email;
                    authBtn.innerHTML = `<i class="fas fa-user"></i> <span id="auth-status">${user.displayName || user.email}</span>`;
                    
                    // Verificar email periódicamente
                    checkEmailVerification();
                    setInterval(checkEmailVerification, 30000);
                    
                    // Si estamos en la sección de perfil, actualizar
                    if (document.getElementById('perfil').classList.contains('active')) {
                        updateProfile();
                    }
                } else {
                    authStatus.textContent = 'Iniciar Sesión';
                    authBtn.innerHTML = `<i class="fas fa-user"></i> <span id="auth-status">Iniciar Sesión</span>`;
                    
                    // Si estamos en la sección de perfil, actualizar
                    if (document.getElementById('perfil').classList.contains('active')) {
                        updateProfile();
                    }
                }
            });

            // Iniciar en la sección de inicio
            switchSection('inicio');
        });

        // Limpiar listeners cuando se cierre la página
        window.addEventListener('beforeunload', function() {
            stopRealTimeListeners();
        });
    </script>
</body>
</html>
