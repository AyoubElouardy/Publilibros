<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publibros - Comparte y Lee Libros</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6C63FF;
            --secondary: #FF6584;
            --accent: #36D1DC;
            --light: #F8F9FA;
            --dark: #2D2B55;
            --text: #333344;
            --text-light: #888899;
            --shadow: 0 8px 25px rgba(108, 99, 255, 0.15);
            --transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            --gradient: linear-gradient(135deg, var(--primary), var(--accent));
            --gradient-secondary: linear-gradient(135deg, var(--secondary), #FF8E53);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--text);
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            color: var(--dark);
            padding: 1rem 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2rem;
            font-weight: 800;
            display: flex;
            align-items: center;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 2px 10px rgba(108, 99, 255, 0.2);
        }

        .logo i {
            margin-right: 12px;
            font-size: 2.2rem;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 1rem;
        }

        nav ul li a {
            color: var(--dark);
            text-decoration: none;
            transition: var(--transition);
            font-weight: 600;
            padding: 0.7rem 1.5rem;
            border-radius: 50px;
            position: relative;
            overflow: hidden;
        }

        nav ul li a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            transition: var(--transition);
            z-index: -1;
        }

        nav ul li a:hover::before,
        nav ul li a.active::before {
            left: 0;
        }

        nav ul li a:hover,
        nav ul li a.active {
            color: white;
            transform: translateY(-2px);
        }

        .user-actions {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .user-actions button {
            background: var(--gradient);
            border: none;
            color: white;
            padding: 0.7rem 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: 0 4px 15px rgba(108, 99, 255, 0.3);
        }

        .user-actions button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(108, 99, 255, 0.4);
        }

        .main-section {
            display: none;
            padding: 2rem 0;
            min-height: calc(100vh - 200px);
            animation: fadeInUp 0.6s ease-out;
        }

        .main-section.active {
            display: block;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero {
            background: var(--gradient);
            color: white;
            padding: 5rem 0;
            text-align: center;
            border-radius: 20px;
            margin-bottom: 3rem;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><polygon fill="rgba(255,255,255,0.05)" points="0,1000 1000,0 1000,1000"/></svg>');
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            font-weight: 800;
            text-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 2.5rem;
            opacity: 0.95;
            font-weight: 300;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: var(--gradient);
            color: white;
            padding: 1rem 2.2rem;
            border: none;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 6px 20px rgba(108, 99, 255, 0.3);
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            transform: translateY(-4px) scale(1.02);
            box-shadow: 0 10px 30px rgba(108, 99, 255, 0.4);
        }

        .btn-outline {
            background: transparent;
            border: 3px solid white;
            margin-left: 15px;
        }

        .btn-outline:hover {
            background: white;
            color: var(--primary);
        }

        .btn-secondary {
            background: var(--gradient-secondary);
        }

        .btn-danger {
            background: linear-gradient(135deg, #FF416C, #FF4B2B);
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--dark);
            position: relative;
            font-size: 2.5rem;
            font-weight: 800;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 100px;
            height: 6px;
            background: var(--gradient);
            margin: 15px auto;
            border-radius: 3px;
        }

        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }

        .book-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .book-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(108, 99, 255, 0.25);
        }

        .book-cover {
            height: 250px;
            background: var(--gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2.5rem;
            position: relative;
            overflow: hidden;
        }

        .book-cover::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(255,255,255,0.1) 0%, transparent 100%);
        }

        .book-actions {
            position: absolute;
            top: 15px;
            right: 15px;
            display: flex;
            flex-direction: column;
            gap: 10px;
            z-index: 2;
        }

        .book-action {
            background: rgba(255, 255, 255, 0.9);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
            color: var(--primary);
            backdrop-filter: blur(10px);
        }

        .book-action:hover {
            background: white;
            transform: scale(1.15) rotate(5deg);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .book-info {
            padding: 1.8rem;
        }

        .book-title {
            font-weight: 700;
            margin-bottom: 0.7rem;
            font-size: 1.3rem;
            color: var(--dark);
        }

        .book-author {
            color: var(--text-light);
            font-size: 1rem;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
        }

        .book-description {
            font-size: 0.95rem;
            margin-bottom: 1.2rem;
            line-height: 1.5;
            color: var(--text);
        }

        .book-genre {
            display: inline-block;
            background: var(--gradient);
            color: white;
            padding: 0.4rem 1rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .book-stats {
            display: flex;
            justify-content: space-between;
            margin-top: 1.2rem;
            font-size: 0.9rem;
            color: var(--text-light);
        }

        .book-stat {
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        .empty-state {
            text-align: center;
            padding: 4rem 2rem;
            background: white;
            border-radius: 20px;
            box-shadow: var(--shadow);
        }

        .empty-state i {
            font-size: 5rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 1.5rem;
        }

        .empty-state h3 {
            color: var(--dark);
            margin-bottom: 1rem;
            font-size: 1.8rem;
        }

        .empty-state p {
            color: var(--text-light);
            max-width: 500px;
            margin: 0 auto 2rem;
            font-size: 1.1rem;
        }

        .recommendation-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background: var(--gradient-secondary);
            color: white;
            padding: 0.4rem 1rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 1;
            box-shadow: 0 4px 15px rgba(255, 101, 132, 0.3);
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-book-sparkles"></i>Publi<span>libros</span>
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

    <section id="inicio" class="main-section active">
        <div class="container">
            <div class="hero">
                <h1>Descubre y Comparte Historias Únicas</h1>
                <p>Publibros es la plataforma donde autores y lectores se conectan. Comparte tus creaciones, descubre nuevos talentos y únete a la comunidad literaria más vibrante.</p>
                <button class="btn" id="explore-library">
                    <i class="fas fa-rocket"></i> Explorar Biblioteca
                </button>
                <button class="btn btn-outline" id="upload-first-book">
                    <i class="fas fa-plus"></i> Publica tu Primer Libro
                </button>
            </div>

            <div class="featured-books">
                <h2 class="section-title">Libros Destacados</h2>
                <div class="books-grid" id="featured-books-container">
                </div>
            </div>

            <div class="recommended-books" id="recommended-section">
                <h2 class="section-title">Recomendados para Ti</h2>
                <div class="books-grid" id="recommended-books-container">
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
        <section id="biblioteca" class="main-section">
        <div class="container">
            <h2 class="section-title">Biblioteca de Libros</h2>
            
            <div class="library-actions">
                <button class="btn" id="upload-book-btn">
                    <i class="fas fa-plus"></i> Subir Nuevo Libro
                </button>
                <div class="search-filter">
                    <div class="search-box">
                        <i class="fas fa-search"></i>
                        <input type="text" id="search-books" class="form-control" placeholder="Buscar libros...">
                    </div>
                    <select id="filter-books" class="form-control">
                        <option value="all">Todos los libros</option>
                        <option value="liked">Mis favoritos</option>
                        <option value="my-books">Mis libros</option>
                    </select>
                </div>
            </div>
            
            <div class="genre-filter" id="genre-filter-container">
            </div>

            <div class="books-grid" id="books-container">
            </div>
        </div>
    </section>

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
                    <p class="user-bio" id="profile-user-bio">¡Hola! Soy un apasionado de la lectura y la escritura.</p>
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
                <button class="btn" id="edit-profile-btn">
                    <i class="fas fa-edit"></i> Editar Perfil
                </button>
                <button class="btn btn-secondary" id="resend-verification" style="display: none;">
                    <i class="fas fa-envelope"></i> Reenviar Verificación
                </button>
            </div>

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
                    </div>
                </div>
                
                <div class="tab-content" id="reported-books-tab">
                    <h3>Libros Reportados</h3>
                    <div id="reported-books-container">
                    </div>
                </div>
                
                <div class="tab-content" id="user-management-tab">
                    <h3>Gestión de Usuarios</h3>
                    <div id="users-container">
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
                    </div>
                </div>
                
                <div class="tab-content" id="liked-books-tab">
                    <h3>Libros que Me Gustan</h3>
                    <div class="books-grid" id="liked-books-container">
                    </div>
                </div>
                
                <div class="tab-content" id="my-reviews-tab">
                    <h3>Mis Reseñas</h3>
                    <div id="my-reviews-container">
                    </div>
                </div>
            </div>
        </div>
    </section>

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

<style>
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin-top: 3rem;
}

.stat-card {
    background: white;
    padding: 2.5rem 2rem;
    border-radius: 20px;
    text-align: center;
    box-shadow: var(--shadow);
    transition: var(--transition);
    border: 1px solid rgba(255, 255, 255, 0.2);
    position: relative;
    overflow: hidden;
}

.stat-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 4px;
    background: var(--gradient);
}

.stat-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 40px rgba(108, 99, 255, 0.2);
}

.stat-icon {
    font-size: 3rem;
    margin-bottom: 1.5rem;
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.stat-value {
    font-size: 2.5rem;
    font-weight: 800;
    color: var(--dark);
    margin-bottom: 0.5rem;
}

.stat-label {
    font-size: 1rem;
    color: var(--text-light);
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.library-actions {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2.5rem;
    flex-wrap: wrap;
    gap: 1.5rem;
    background: white;
    padding: 2rem;
    border-radius: 20px;
    box-shadow: var(--shadow);
}

.search-filter {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
}

.search-box {
    position: relative;
    flex: 1;
}

.search-box i {
    position: absolute;
    left: 1rem;
    top: 50%;
    transform: translateY(-50%);
    color: var(--text-light);
}

.search-box input {
    padding-left: 3rem;
}

.upload-form {
    max-width: 800px;
    margin: 0 auto;
    background: white;
    padding: 3rem;
    border-radius: 25px;
    box-shadow: var(--shadow);
    border: 1px solid rgba(255, 255, 255, 0.2);
}

.form-group {
    margin-bottom: 2rem;
    position: relative;
}

.form-group label {
    display: block;
    margin-bottom: 0.8rem;
    font-weight: 700;
    color: var(--dark);
    font-size: 1.1rem;
}

.form-control {
    width: 100%;
    padding: 1.2rem 1.5rem;
    border: 2px solid #e0e0e0;
    border-radius: 15px;
    font-size: 1rem;
    transition: var(--transition);
    background: #f8f9ff;
    font-family: 'Poppins', sans-serif;
}

.form-control:focus {
    border-color: var(--primary);
    outline: none;
    box-shadow: 0 0 0 4px rgba(108, 99, 255, 0.1);
    background: white;
    transform: translateY(-2px);
}

textarea.form-control {
    min-height: 180px;
    resize: vertical;
    line-height: 1.6;
}

.genre-filter {
    display: flex;
    flex-wrap: wrap;
    gap: 0.8rem;
    margin-bottom: 2rem;
    padding: 1.5rem;
    background: white;
    border-radius: 15px;
    box-shadow: var(--shadow);
}

.genre-chip {
    background: #f0f2ff;
    color: var(--primary);
    padding: 0.7rem 1.5rem;
    border-radius: 25px;
    font-size: 0.9rem;
    cursor: pointer;
    transition: var(--transition);
    border: 2px solid transparent;
    font-weight: 600;
}

.genre-chip:hover {
    background: var(--primary);
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(108, 99, 255, 0.3);
}

.genre-chip.active {
    background: var(--gradient);
    color: white;
    border-color: var(--primary);
    box-shadow: 0 5px 15px rgba(108, 99, 255, 0.3);
}

.user-profile {
    display: flex;
    align-items: center;
    margin-bottom: 3rem;
    background: white;
    padding: 2.5rem;
    border-radius: 25px;
    box-shadow: var(--shadow);
    border: 1px solid rgba(255, 255, 255, 0.2);
    position: relative;
    overflow: hidden;
}

.user-profile::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 4px;
    background: var(--gradient);
}

.user-avatar {
    width: 140px;
    height: 140px;
    border-radius: 50%;
    background: var(--gradient);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 3rem;
    margin-right: 2rem;
    overflow: hidden;
    position: relative;
    cursor: pointer;
    border: 4px solid white;
    box-shadow: 0 8px 25px rgba(108, 99, 255, 0.3);
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
    background: rgba(108, 99, 255, 0.8);
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: var(--transition);
    backdrop-filter: blur(5px);
}

.user-avatar:hover .edit-overlay {
    opacity: 1;
}

.user-avatar .edit-overlay i {
    color: white;
    font-size: 1.8rem;
}

.user-info {
    flex: 1;
}

.user-name {
    font-size: 2rem;
    font-weight: 800;
    margin-bottom: 0.5rem;
    color: var(--dark);
    display: flex;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
}

.user-email {
    color: var(--text-light);
    margin-bottom: 1rem;
    font-size: 1.1rem;
}

.user-bio {
    color: var(--text);
    margin-bottom: 1.5rem;
    line-height: 1.6;
    font-size: 1.05rem;
}

.user-stats {
    display: flex;
    gap: 2.5rem;
}

.user-stat {
    text-align: center;
}

.verification-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: #d4ffd4;
    color: #00a800;
    padding: 0.5rem 1.2rem;
    border-radius: 25px;
    font-size: 0.8rem;
    font-weight: 700;
}

.verification-badge.unverified {
    background: #ffe0e0;
    color: #ff4444;
}

.admin-badge {
    background: var(--gradient-secondary);
    color: white;
    padding: 0.5rem 1.2rem;
    border-radius: 25px;
    font-size: 0.8rem;
    font-weight: bold;
    box-shadow: 0 4px 15px rgba(255, 101, 132, 0.3);
}

.tabs-header {
    display: flex;
    border-bottom: 2px solid #f0f0f0;
    margin-bottom: 2.5rem;
    background: white;
    padding: 0.5rem;
    border-radius: 15px;
    box-shadow: var(--shadow);
}

.tab-btn {
    background: none;
    border: none;
    padding: 1.2rem 2rem;
    cursor: pointer;
    font-size: 1rem;
    font-weight: 600;
    color: var(--text-light);
    border-radius: 12px;
    transition: var(--transition);
    position: relative;
    overflow: hidden;
}

.tab-btn:hover {
    color: var(--primary);
    background: rgba(108, 99, 255, 0.1);
    transform: translateY(-2px);
}

.tab-btn.active {
    color: var(--primary);
    background: rgba(108, 99, 255, 0.15);
    box-shadow: 0 4px 15px rgba(108, 99, 255, 0.2);
}

.tab-content {
    display: none;
    animation: fadeIn 0.5s ease-in;
}

.tab-content.active {
    display: block;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

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
    backdrop-filter: blur(5px);
}

.modal-content {
    max-width: 500px;
    width: 90%;
    max-height: 90vh;
    overflow-y: auto;
    background: white;
    padding: 2.5rem;
    border-radius: 25px;
    box-shadow: var(--shadow);
    border: 1px solid rgba(255, 255, 255, 0.2);
    animation: modalSlideIn 0.3s ease-out;
}

@keyframes modalSlideIn {
    from {
        opacity: 0;
        transform: translateY(-50px) scale(0.9);
    }
    to {
        opacity: 1;
        transform: translateY(0) scale(1);
    }
}

.modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
    padding-bottom: 1.5rem;
    border-bottom: 2px solid #f0f0f0;
}

.modal-header h3 {
    color: var(--dark);
    font-size: 1.8rem;
    font-weight: 800;
}

.close-modal {
    background: none;
    border: none;
    font-size: 2rem;
    cursor: pointer;
    color: var(--text-light);
    transition: var(--transition);
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.close-modal:hover {
    background: #f0f0f0;
    color: var(--primary);
}

.auth-tabs {
    display: flex;
    margin-bottom: 2rem;
    border-bottom: 2px solid #f0f0f0;
}

.auth-tab {
    padding: 1rem 2rem;
    background: none;
    border: none;
    cursor: pointer;
    font-weight: 600;
    color: var(--text-light);
    border-bottom: 3px solid transparent;
    transition: var(--transition);
    font-size: 1rem;
}

.auth-tab.active {
    color: var(--primary);
    border-bottom: 3px solid var(--primary);
}

.auth-form {
    display: none;
}

.auth-form.active {
    display: block;
}

.form-footer {
    margin-top: 2rem;
    text-align: center;
    color: var(--text-light);
    font-size: 0.9rem;
}

.form-footer a {
    color: var(--primary);
    text-decoration: none;
    cursor: pointer;
    font-weight: 600;
    transition: var(--transition);
}

.form-footer a:hover {
    color: var(--secondary);
}

.error-message {
    color: var(--secondary);
    font-size: 0.9rem;
    margin-top: 0.5rem;
    display: none;
    font-weight: 600;
}

.admin-panel {
    background: white;
    padding: 2.5rem;
    border-radius: 25px;
    box-shadow: var(--shadow);
    margin-bottom: 3rem;
    border: 1px solid rgba(255, 255, 255, 0.2);
}

.profile-tabs {
    margin-top: 3rem;
}
</style>
    <div id="upload-modal" class="modal writing-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Publicar Nuevo Libro</h3>
                <button class="close-modal" id="close-upload-modal">&times;</button>
            </div>
            
            <div class="writing-tabs">
                <button class="writing-tab active" data-tab="basic-info">Información Básica</button>
                <button class="writing-tab" data-tab="cover-design">Portada</button>
                <button class="writing-tab" data-tab="content-editor">Contenido</button>
                <button class="writing-tab" data-tab="preview">Vista Previa</button>
            </div>
            
            <form id="upload-form">
                <div class="tab-panel active" id="basic-info-panel">
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
                        <button type="button" class="btn btn-secondary" id="next-to-cover">Siguiente: Portada</button>
                    </div>
                </div>
                
                <div class="tab-panel" id="cover-design-panel">
                    <div class="cover-upload-section">
                        <h4>Portada del Libro</h4>
                        <p>Puedes subir una imagen personalizada o elegir uno de nuestros diseños.</p>
                        
                        <div class="form-group">
                            <label for="book-cover-upload">Subir Imagen de Portada</label>
                            <input type="file" id="book-cover-upload" class="form-control" accept="image/*">
                            <small>Formatos: JPG, PNG. Tamaño máximo: 2MB</small>
                        </div>
                        
                        <div class="cover-preview" id="cover-preview">
                            <div id="cover-placeholder">
                                <i class="fas fa-book fa-3x"></i>
                                <p>Vista previa de portada</p>
                            </div>
                        </div>
                        
                        <h5>O elige un diseño prediseñado:</h5>
                        <div class="cover-options" id="cover-options">
                        </div>
                    </div>
                    
                    <div class="form-group" style="display: flex; justify-content: space-between; margin-top: 2rem;">
                        <button type="button" class="btn btn-secondary" id="back-to-basic">Anterior: Información</button>
                        <button type="button" class="btn btn-secondary" id="next-to-content">Siguiente: Contenido</button>
                    </div>
                </div>
                
                <div class="tab-panel" id="content-editor-panel">
                    <div class="form-group">
                        <label>Editor de Contenido</label>
                        <div class="editor-container">
                            <div class="editor-toolbar" id="editor-toolbar">
                                <button type="button" class="editor-btn" data-command="bold"><i class="fas fa-bold"></i></button>
                                <button type="button" class="editor-btn" data-command="italic"><i class="fas fa-italic"></i></button>
                                <button type="button" class="editor-btn" data-command="underline"><i class="fas fa-underline"></i></button>
                                <button type="button" class="editor-btn" data-command="insertUnorderedList"><i class="fas fa-list-ul"></i></button>
                                <button type="button" class="editor-btn" data-command="formatBlock" data-value="H1">T1</button>
                                <button type="button" class="editor-btn" data-command="formatBlock" data-value="H2">T2</button>
                                <button type="button" class="editor-btn" data-command="formatBlock" data-value="P">P</button>
                                <button type="button" class="editor-btn" id="add-chapter-btn"><i class="fas fa-bookmark"></i> Capítulo</button>
                            </div>
                            <div class="editor-content" id="book-content" contenteditable="true"></div>
                            <div class="editor-stats">
                                <span id="word-count">0 palabras</span>
                                <span id="page-count">0 páginas</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="chapters-section">
                        <h4>Capítulos</h4>
                        <div class="chapter-list" id="chapter-list">
                        </div>
                        <button type="button" class="btn btn-secondary" id="manage-chapters-btn">
                            <i class="fas fa-cog"></i> Gestionar Capítulos
                        </button>
                    </div>
                    
                    <div class="form-group" style="display: flex; justify-content: space-between;">
                        <button type="button" class="btn btn-secondary" id="back-to-cover">Anterior: Portada</button>
                        <button type="button" class="btn btn-secondary" id="next-to-preview">Siguiente: Vista Previa</button>
                    </div>
                </div>
                
                <div class="tab-panel" id="preview-panel">
                    <div class="book-preview">
                        <h4>Vista Previa de tu Libro</h4>
                        <div class="book-card" style="max-width: 300px; margin: 0 auto 2rem;">
                            <div class="book-cover" id="preview-cover">
                                <div class="cover-text" id="preview-cover-text">
                                    <h3 id="preview-title">Título del Libro</h3>
                                    <p id="preview-author">por Autor</p>
                                </div>
                            </div>
                            <div class="book-info">
                                <div class="book-title" id="preview-book-title">Título del Libro</div>
                                <div class="book-author" id="preview-book-author">por Autor</div>
                                <div class="book-description" id="preview-description">Descripción del libro</div>
                                <div class="book-genre" id="preview-genre">Género</div>
                            </div>
                        </div>
                        
                        <div class="preview-content">
                            <h5>Contenido (primeras 500 palabras):</h5>
                            <div class="preview-text" id="preview-content-text"></div>
                        </div>
                    </div>
                    
                    <div class="form-group" style="display: flex; justify-content: space-between; margin-top: 2rem;">
                        <button type="button" class="btn btn-secondary" id="back-to-content">Anterior: Contenido</button>
                        <button type="submit" class="btn" id="publish-book-btn">Publicar Libro</button>
                    </div>
                </div>
            </form>
        </div>
    </div>

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

    <section id="reader" style="display: none;">
        <div class="container">
            <div class="reader-container">
                <div class="reader-header">
                    <h2 id="reader-title">Título del Libro</h2>
                    <button id="close-reader" class="btn">Cerrar</button>
                </div>
                <div class="reader-content" id="reader-content">
                </div>
                <div class="reader-controls">
                    <button id="prev-page" class="btn"><i class="fas fa-chevron-left"></i> Anterior</button>
                    <span id="page-info">Página 1 de 1</span>
                    <button id="next-page" class="btn">Siguiente <i class="fas fa-chevron-right"></i></button>
                </div>

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
                    </div>
                </div>
            </div>
        </div>
    </section>

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

<style>
.writing-modal .modal-content {
    max-width: 900px;
    width: 95%;
}

.writing-tabs {
    display: flex;
    border-bottom: 2px solid #f0f0f0;
    margin-bottom: 2rem;
    flex-wrap: wrap;
}

.writing-tab {
    padding: 1rem 1.5rem;
    background: none;
    border: none;
    cursor: pointer;
    font-weight: 600;
    color: var(--text-light);
    border-bottom: 3px solid transparent;
    transition: var(--transition);
    font-size: 0.9rem;
}

.writing-tab.active {
    color: var(--primary);
    border-bottom: 3px solid var(--primary);
}

.tab-panel {
    display: none;
    animation: fadeIn 0.3s ease-in;
}

.tab-panel.active {
    display: block;
}

.editor-container {
    background: white;
    border-radius: 15px;
    box-shadow: var(--shadow);
    overflow: hidden;
    margin-bottom: 2rem;
    border: 2px solid #f0f0f0;
}

.editor-toolbar {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    padding: 1rem;
    border-bottom: 2px solid #f0f0f0;
    background: #f8f9fa;
}

.editor-btn {
    background: white;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    padding: 0.6rem 0.8rem;
    cursor: pointer;
    transition: var(--transition);
    font-weight: 600;
}

.editor-btn:hover {
    background: var(--primary);
    color: white;
    border-color: var(--primary);
    transform: translateY(-2px);
}

.editor-btn.active {
    background: var(--primary);
    color: white;
    border-color: var(--primary);
}

.editor-content {
    min-height: 400px;
    padding: 1.5rem;
    font-size: 1rem;
    line-height: 1.6;
    outline: none;
    background: white;
}

.editor-stats {
    padding: 1rem 1.5rem;
    border-top: 2px solid #f0f0f0;
    background: #f8f9fa;
    display: flex;
    justify-content: space-between;
    font-size: 0.9rem;
    color: var(--text-light);
    font-weight: 600;
}

.cover-upload-section {
    margin-bottom: 2rem;
}

.cover-preview {
    width: 200px;
    height: 280px;
    border: 3px dashed #e0e0e0;
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 1rem auto;
    overflow: hidden;
    background: #f8f9fa;
    transition: var(--transition);
}

.cover-preview:hover {
    border-color: var(--primary);
}

.cover-preview img {
    max-width: 100%;
    max-height: 100%;
    object-fit: cover;
}

.cover-options {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 1rem;
    margin-top: 1rem;
}

.cover-option {
    border: 3px solid #e0e0e0;
    border-radius: 12px;
    padding: 1rem;
    text-align: center;
    cursor: pointer;
    transition: var(--transition);
    background: white;
}

.cover-option:hover {
    border-color: var(--primary);
    transform: translateY(-5px);
}

.cover-option.selected {
    border-color: var(--primary);
    background: rgba(108, 99, 255, 0.1);
    box-shadow: 0 5px 15px rgba(108, 99, 255, 0.2);
}

.cover-design {
    width: 100px;
    height: 140px;
    margin: 0 auto 0.5rem;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: bold;
    font-size: 1.2rem;
    background: var(--gradient);
}

.chapters-section {
    margin-bottom: 2rem;
}

.chapter-list {
    margin-bottom: 1rem;
}

.chapter-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.2rem;
    border: 2px solid #f0f0f0;
    border-radius: 12px;
    margin-bottom: 0.8rem;
    background: white;
    transition: var(--transition);
}

.chapter-item:hover {
    background: #f8f9fa;
    border-color: var(--primary);
    transform: translateX(5px);
}

.chapter-actions {
    display: flex;
    gap: 0.8rem;
}

.chapter-btn {
    background: none;
    border: none;
    cursor: pointer;
    color: var(--text-light);
    transition: var(--transition);
    padding: 0.5rem;
    border-radius: 6px;
}

.chapter-btn:hover {
    color: var(--primary);
    background: rgba(108, 99, 255, 0.1);
}

.reader-container {
    max-width: 900px;
    margin: 0 auto;
    background: white;
    padding: 2.5rem;
    border-radius: 25px;
    box-shadow: var(--shadow);
    border: 1px solid rgba(255, 255, 255, 0.2);
}

.reader-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2.5rem;
    padding-bottom: 1.5rem;
    border-bottom: 2px solid #f0f0f0;
}

.reader-content {
    line-height: 1.8;
    font-size: 1.1rem;
    min-height: 400px;
    white-space: pre-line;
    padding: 1rem;
    background: #f8f9fa;
    border-radius: 12px;
}

.reader-controls {
    display: flex;
    justify-content: space-between;
    margin-top: 2.5rem;
    align-items: center;
    padding-top: 1.5rem;
    border-top: 2px solid #f0f0f0;
}

.reviews-section {
    margin-top: 3rem;
}

.review-form {
    background: #f8f9fa;
    padding: 2rem;
    border-radius: 15px;
    margin-bottom: 2rem;
    border: 2px solid #e0e0e0;
}

.review {
    background: white;
    padding: 1.8rem;
    border-radius: 15px;
    margin-bottom: 1.2rem;
    box-shadow: var(--shadow);
    border: 1px solid rgba(255, 255, 255, 0.2);
}

.review-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 0.8rem;
}

.review-author {
    font-weight: 700;
    color: var(--dark);
}

.review-date {
    color: var(--text-light);
    font-size: 0.9rem;
}

.review-rating {
    color: #FFD700;
    margin-bottom: 0.8rem;
    font-size: 1.1rem;
}

.book-status {
    position: absolute;
    top: 15px;
    left: 15px;
    padding: 0.4rem 1rem;
    border-radius: 20px;
    font-size: 0.8rem;
    font-weight: bold;
    z-index: 1;
    color: white;
}

.status-pending {
    background: #FFA500;
}

.status-approved {
    background: #00C851;
}

.status-rejected {
    background: #ff4444;
}

.admin-actions {
    display: flex;
    gap: 10px;
    margin-top: 15px;
}

.user-management-item {
    background: white;
    padding: 1.8rem;
    border-radius: 15px;
    margin-bottom: 1.2rem;
    box-shadow: var(--shadow);
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 1px solid rgba(255, 255, 255, 0.2);
}

.user-actions {
    display: flex;
    gap: 10px;
}

.loading {
    display: inline-block;
    width: 20px;
    height: 20px;
    border: 3px solid rgba(255,255,255,.3);
    border-radius: 50%;
    border-top-color: #fff;
    animation: spin 1s ease-in-out infinite;
}

@keyframes spin {
    to { transform: rotate(360deg); }
}

.confirmation-modal {
    text-align: center;
}

.confirmation-buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    margin-top: 20px;
}

@media (max-width: 768px) {
    .header-content {
        flex-direction: column;
        text-align: center;
        gap: 1rem;
    }

    nav ul {
        margin-top: 1rem;
        justify-content: center;
        flex-wrap: wrap;
    }

    nav ul li {
        margin: 0 0.3rem;
    }

    .user-actions {
        margin-top: 1rem;
    }

    .hero h1 {
        font-size: 2.5rem;
    }

    .books-grid {
        grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    }

    .user-profile {
        flex-direction: column;
        text-align: center;
    }

    .user-avatar {
        margin-right: 0;
        margin-bottom: 1.5rem;
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
    
    .writing-tabs {
        flex-direction: column;
    }
    
    .writing-tab {
        width: 100%;
        text-align: center;
    }
    
    .reader-controls {
        flex-direction: column;
        gap: 1rem;
    }
    
    .user-management-item {
        flex-direction: column;
        gap: 1rem;
        text-align: center;
    }
    
    .modal-content {
        padding: 1.5rem;
    }
}
</style>

<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-storage-compat.js"></script>

<script>
const firebaseConfig = {
    apiKey: "AIzaSyDjwZHNY-q6kp67MzUOMQ4olOW3CgtNL0U",
    authDomain: "publilibros01.firebaseapp.com",
    projectId: "publilibros01",
    storageBucket: "publilibros01.firebasestorage.app",
    messagingSenderId: "242974271454",
    appId: "1:242974271454:web:ae939c47d714ccb6185f4f",
    measurementId: "G-CSLWHDQ3Q6"
};

let app, auth, db, storage;
try {
    app = firebase.initializeApp(firebaseConfig);
    auth = firebase.auth();
    db = firebase.firestore();
    storage = firebase.storage();
    console.log("Firebase inicializado correctamente");
} catch (error) {
    console.error("Error inicializando Firebase:", error);
}

const usersRef = db.collection("users");
const booksRef = db.collection("books");
const reviewsRef = db.collection("reviews");

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

let currentBookData = {
    title: '',
    author: '',
    genre: '',
    description: '',
    content: '',
    coverType: 'custom',
    coverImage: null,
    coverDesign: null,
    chapters: [],
    wordCount: 0,
    pageCount: 0
};

let selectedCoverDesign = null;
let autoSaveInterval = null;
let currentBook = null;
let currentPage = 0;
const wordsPerPage = 300;
let bookPages = [];
let selectedGenre = 'all';
let searchTerm = '';
let currentFilter = 'all';
let booksListener = null;
let usersListener = null;

function initWritingSystem() {
    document.querySelectorAll('.writing-tab').forEach(tab => {
        tab.addEventListener('click', function() {
            const tabId = this.getAttribute('data-tab');
            switchWritingTab(tabId);
        });
    });

    document.getElementById('next-to-cover').addEventListener('click', function() {
        if (validateBasicInfo()) {
            switchWritingTab('cover-design');
        }
    });

    document.getElementById('back-to-basic').addEventListener('click', function() {
        switchWritingTab('basic-info');
    });

    document.getElementById('next-to-content').addEventListener('click', function() {
        switchWritingTab('content-editor');
    });

    document.getElementById('back-to-cover').addEventListener('click', function() {
        switchWritingTab('cover-design');
    });

    document.getElementById('next-to-preview').addEventListener('click', function() {
        updatePreview();
        switchWritingTab('preview');
    });

    document.getElementById('back-to-content').addEventListener('click', function() {
        switchWritingTab('content-editor');
    });

    initTextEditor();
    initCoverSystem();
    initChapterSystem();
    initAutoSave();
}

function switchWritingTab(tabId) {
    document.querySelectorAll('.writing-tab').forEach(tab => {
        tab.classList.remove('active');
    });
    document.querySelector(`.writing-tab[data-tab="${tabId}"]`).classList.add('active');

    document.querySelectorAll('.tab-panel').forEach(panel => {
        panel.classList.remove('active');
    });
    document.getElementById(`${tabId}-panel`).classList.add('active');
}

function validateBasicInfo() {
    const title = document.getElementById('book-title').value.trim();
    const author = document.getElementById('book-author').value.trim();
    const genre = document.getElementById('book-genre').value;
    const description = document.getElementById('book-description').value.trim();

    if (!title) {
        alert('Por favor, ingresa un título para el libro.');
        return false;
    }

    if (!author) {
        alert('Por favor, ingresa el nombre del autor.');
        return false;
    }

    if (!genre) {
        alert('Por favor, selecciona un género para el libro.');
        return false;
    }

    if (!description) {
        alert('Por favor, escribe una descripción para el libro.');
        return false;
    }

    currentBookData.title = title;
    currentBookData.author = author;
    currentBookData.genre = genre;
    currentBookData.description = description;

    return true;
}

function initTextEditor() {
    const editor = document.getElementById('book-content');
    const toolbar = document.getElementById('editor-toolbar');

    toolbar.querySelectorAll('.editor-btn[data-command]').forEach(btn => {
        btn.addEventListener('click', function() {
            const command = this.getAttribute('data-command');
            const value = this.getAttribute('data-value');
            
            if (command === 'formatBlock' && value) {
                document.execCommand(command, false, value);
            } else {
                document.execCommand(command, false, null);
            }
            
            editor.focus();
        });
    });

    editor.addEventListener('input', updateEditorStats);
    updateEditorStats();
}

function updateEditorStats() {
    const editor = document.getElementById('book-content');
    const text = editor.textContent || editor.innerText;
    
    const wordCount = text.trim() ? text.trim().split(/\s+/).length : 0;
    document.getElementById('word-count').textContent = `${wordCount} palabras`;
    
    const pageCount = Math.ceil(wordCount / 300);
    document.getElementById('page-count').textContent = `${pageCount} páginas`;
    
    currentBookData.content = editor.innerHTML;
    currentBookData.wordCount = wordCount;
    currentBookData.pageCount = pageCount;
}

function initCoverSystem() {
    const coverUpload = document.getElementById('book-cover-upload');
    const coverPreview = document.getElementById('cover-preview');
    
    coverUpload.addEventListener('change', function(e) {
        const file = e.target.files[0];
        if (file) {
            if (!file.type.match('image.*')) {
                alert('Por favor, selecciona un archivo de imagen válido.');
                return;
            }
            
            if (file.size > 2 * 1024 * 1024) {
                alert('La imagen no puede ser mayor a 2MB.');
                return;
            }
            
            const reader = new FileReader();
            reader.onload = function(e) {
                coverPreview.innerHTML = `<img src="${e.target.result}" alt="Portada del libro">`;
                currentBookData.coverType = 'custom';
                currentBookData.coverImage = file;
            };
            reader.readAsDataURL(file);
        }
    });
    
    generateCoverOptions();
}

function generateCoverOptions() {
    const coverOptions = document.getElementById('cover-options');
    const designs = [
        { id: 'design1', bgColor: '#3498db', textColor: '#ffffff' },
        { id: 'design2', bgColor: '#e74c3c', textColor: '#ffffff' },
        { id: 'design3', bgColor: '#2ecc71', textColor: '#ffffff' },
        { id: 'design4', bgColor: '#f39c12', textColor: '#ffffff' },
        { id: 'design5', bgColor: '#9b59b6', textColor: '#ffffff' },
        { id: 'design6', bgColor: '#1abc9c', textColor: '#ffffff' }
    ];
    
    coverOptions.innerHTML = '';
    
    designs.forEach(design => {
        const option = document.createElement('div');
        option.className = 'cover-option';
        option.setAttribute('data-design', design.id);
        
        const designElement = document.createElement('div');
        designElement.className = 'cover-design';
        designElement.style.backgroundColor = design.bgColor;
        designElement.innerHTML = '<i class="fas fa-book"></i>';
        
        option.appendChild(designElement);
        option.appendChild(document.createTextNode('Diseño ' + design.id.replace('design', '')));
        
        option.addEventListener('click', function() {
            document.querySelectorAll('.cover-option').forEach(opt => {
                opt.classList.remove('selected');
            });
            
            this.classList.add('selected');
            selectedCoverDesign = design;
            currentBookData.coverType = 'generated';
            currentBookData.coverDesign = design;
            
            updateCoverPreview(design);
        });
        
        coverOptions.appendChild(option);
    });
}

function updateCoverPreview(design) {
    const coverPreview = document.getElementById('cover-preview');
    coverPreview.innerHTML = '';
    coverPreview.style.background = design.bgColor;
    coverPreview.style.display = 'flex';
    coverPreview.style.alignItems = 'center';
    coverPreview.style.justifyContent = 'center';
    coverPreview.style.color = design.textColor;
    coverPreview.style.fontWeight = 'bold';
    coverPreview.style.fontSize = '1.2rem';
    coverPreview.innerHTML = '<div style="text-align: center;"><i class="fas fa-book fa-2x"></i><p style="margin-top: 10px;">Portada Personalizada</p></div>';
}

function initChapterSystem() {
    const addChapterBtn = document.getElementById('add-chapter-btn');
    const chapterList = document.getElementById('chapter-list');
    
    addChapterBtn.addEventListener('click', function() {
        const editor = document.getElementById('book-content');
        const selection = window.getSelection();
        
        if (selection.rangeCount > 0) {
            const range = selection.getRangeAt(0);
            const selectedText = range.toString();
            
            if (selectedText) {
                const chapterTitle = prompt('Ingresa el título del capítulo:', selectedText.substring(0, 30) + '...');
                
                if (chapterTitle) {
                    addChapter(chapterTitle, range);
                }
            } else {
                alert('Selecciona un texto para marcar como inicio de capítulo.');
            }
        } else {
            alert('Selecciona un texto para marcar como inicio de capítulo.');
        }
    });
    
    document.getElementById('manage-chapters-btn').addEventListener('click', function() {
        showChapterManager();
    });
}

function addChapter(title, range) {
    const chapterMarker = document.createElement('span');
    chapterMarker.className = 'chapter-marker';
    chapterMarker.setAttribute('data-chapter-title', title);
    chapterMarker.innerHTML = `[CAPÍTULO: ${title}]`;
    chapterMarker.style.backgroundColor = '#ffeaa7';
    chapterMarker.style.padding = '2px 4px';
    chapterMarker.style.borderRadius = '3px';
    chapterMarker.style.fontSize = '0.8rem';
    
    range.insertNode(chapterMarker);
    
    currentBookData.chapters.push({
        title: title,
        position: currentBookData.chapters.length
    });
    
    updateChapterList();
}

function updateChapterList() {
    const chapterList = document.getElementById('chapter-list');
    chapterList.innerHTML = '';
    
    currentBookData.chapters.forEach((chapter, index) => {
        const chapterItem = document.createElement('div');
        chapterItem.className = 'chapter-item';
        chapterItem.innerHTML = `
            <div>
                <strong>Capítulo ${index + 1}:</strong> ${chapter.title}
            </div>
            <div class="chapter-actions">
                <button class="chapter-btn edit-chapter" data-index="${index}">
                    <i class="fas fa-edit"></i>
                </button>
                <button class="chapter-btn delete-chapter" data-index="${index}">
                    <i class="fas fa-trash"></i>
                </button>
            </div>
        `;
        
        chapterList.appendChild(chapterItem);
    });
    
    document.querySelectorAll('.edit-chapter').forEach(btn => {
        btn.addEventListener('click', function() {
            const index = parseInt(this.getAttribute('data-index'));
            editChapter(index);
        });
    });
    
    document.querySelectorAll('.delete-chapter').forEach(btn => {
        btn.addEventListener('click', function() {
            const index = parseInt(this.getAttribute('data-index'));
            deleteChapter(index);
        });
    });
}

function showChapterManager() {
    alert('Funcionalidad de gestión avanzada de capítulos en desarrollo.');
}

function editChapter(index) {
    const newTitle = prompt('Nuevo título del capítulo:', currentBookData.chapters[index].title);
    if (newTitle) {
        currentBookData.chapters[index].title = newTitle;
        updateChapterList();
        updateChapterMarkers();
    }
}

function deleteChapter(index) {
    if (confirm('¿Estás seguro de que quieres eliminar este capítulo?')) {
        currentBookData.chapters.splice(index, 1);
        updateChapterList();
        updateChapterMarkers();
    }
}

function updateChapterMarkers() {
}

function initAutoSave() {
    autoSaveInterval = setInterval(function() {
        if (currentBookData.content) {
            localStorage.setItem('publibros_draft', JSON.stringify(currentBookData));
        }
    }, 30000);
    
    const savedDraft = localStorage.getItem('publibros_draft');
    if (savedDraft) {
        if (confirm('Tienes un borrador guardado. ¿Quieres continuar donde lo dejaste?')) {
            currentBookData = JSON.parse(savedDraft);
            loadDraftData();
        }
    }
}

function loadDraftData() {
    document.getElementById('book-title').value = currentBookData.title;
    document.getElementById('book-author').value = currentBookData.author;
    document.getElementById('book-genre').value = currentBookData.genre;
    document.getElementById('book-description').value = currentBookData.description;
    document.getElementById('book-content').innerHTML = currentBookData.content;
    
    updateEditorStats();
    updateChapterList();
}

function updatePreview() {
    document.getElementById('preview-title').textContent = currentBookData.title;
    document.getElementById('preview-author').textContent = `por ${currentBookData.author}`;
    document.getElementById('preview-book-title').textContent = currentBookData.title;
    document.getElementById('preview-book-author').textContent = `por ${currentBookData.author}`;
    document.getElementById('preview-description').textContent = currentBookData.description;
    document.getElementById('preview-genre').textContent = genreNames[currentBookData.genre] || currentBookData.genre;
    
    const contentText = document.getElementById('book-content').textContent || '';
    const previewText = contentText.substring(0, 500) + (contentText.length > 500 ? '...' : '');
    document.getElementById('preview-content-text').textContent = previewText;
    
    const previewCover = document.getElementById('preview-cover');
    if (currentBookData.coverType === 'custom' && currentBookData.coverImage) {
        const reader = new FileReader();
        reader.onload = function(e) {
            previewCover.style.backgroundImage = `url(${e.target.result})`;
            previewCover.querySelector('.cover-text').style.display = 'none';
        };
        reader.readAsDataURL(currentBookData.coverImage);
    } else if (currentBookData.coverType === 'generated' && currentBookData.coverDesign) {
        previewCover.style.background = currentBookData.coverDesign.bgColor;
        previewCover.querySelector('.cover-text').style.display = 'block';
        previewCover.querySelector('.cover-text').style.color = currentBookData.coverDesign.textColor;
    } else {
        previewCover.style.background = 'linear-gradient(135deg, var(--primary), var(--secondary))';
        previewCover.querySelector('.cover-text').style.display = 'block';
        previewCover.querySelector('.cover-text').style.color = 'white';
    }
}

document.addEventListener('DOMContentLoaded', function() {
    document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', function(e) {
            e.preventDefault();
            const sectionId = this.getAttribute('data-section');
            switchSection(sectionId);
        });
    });

    document.querySelectorAll('.nav-link-footer').forEach(link => {
        link.addEventListener('click', function(e) {
            e.preventDefault();
            const sectionId = this.getAttribute('data-section');
            switchSection(sectionId);
        });
    });

    document.getElementById('auth-btn').addEventListener('click', function() {
        document.getElementById('auth-modal').style.display = 'flex';
    });

    document.getElementById('close-auth-modal').addEventListener('click', function() {
        document.getElementById('auth-modal').style.display = 'none';
    });

    document.getElementById('upload-book-btn').addEventListener('click', function() {
        document.getElementById('upload-modal').style.display = 'flex';
    });

    document.getElementById('close-upload-modal').addEventListener('click', function() {
        document.getElementById('upload-modal').style.display = 'none';
    });

    document.getElementById('edit-profile-btn').addEventListener('click', function() {
        document.getElementById('edit-profile-modal').style.display = 'flex';
    });

    document.getElementById('close-edit-profile-modal').addEventListener('click', function() {
        document.getElementById('edit-profile-modal').style.display = 'none';
    });

    window.addEventListener('click', function(event) {
        if (event.target.classList.contains('modal')) {
            event.target.style.display = 'none';
        }
    });

    document.querySelectorAll('.auth-tab').forEach(tab => {
        tab.addEventListener('click', function() {
            const formId = this.getAttribute('data-form');
            
            document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
            this.classList.add('active');
            
            document.querySelectorAll('.auth-form').forEach(form => {
                form.classList.remove('active');
            });
            document.getElementById(`${formId}-form`).classList.add('active');
        });
    });

    document.getElementById('switch-to-register').addEventListener('click', function(e) {
        e.preventDefault();
        document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
        document.querySelector('[data-form="register"]').classList.add('active');
        document.querySelectorAll('.auth-form').forEach(form => {
            form.classList.remove('active');
        });
        document.getElementById('register-form').classList.add('active');
    });

    document.getElementById('switch-to-login').addEventListener('click', function(e) {
        e.preventDefault();
        document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
        document.querySelector('[data-form="login"]').classList.add('active');
        document.querySelectorAll('.auth-form').forEach(form => {
            form.classList.remove('active');
        });
        document.getElementById('login-form').classList.add('active');
    });

    document.getElementById('forgot-password').addEventListener('click', function(e) {
        e.preventDefault();
        handlePasswordReset();
    });

    document.getElementById('login-form').addEventListener('submit', function(e) {
        e.preventDefault();
        handleLoginFormSubmit(e);
    });

    document.getElementById('register-form').addEventListener('submit', function(e) {
        e.preventDefault();
        handleRegisterFormSubmit(e);
    });

    document.getElementById('upload-form').addEventListener('submit', function(e) {
        e.preventDefault();
        handleUploadFormSubmit(e);
    });

    document.getElementById('edit-profile-form').addEventListener('submit', function(e) {
        e.preventDefault();
        handleEditProfileFormSubmit(e);
    });

    document.getElementById('search-books').addEventListener('input', function(e) {
        searchTerm = e.target.value;
        displayBooks();
    });

    document.getElementById('filter-books').addEventListener('change', function(e) {
        currentFilter = e.target.value;
        displayBooks();
    });

    document.getElementById('resend-verification').addEventListener('click', function() {
        resendEmailVerification();
    });

    document.getElementById('close-reader').addEventListener('click', closeReader);
    document.getElementById('prev-page').addEventListener('click', function() {
        if (currentPage > 0) {
            currentPage--;
            displayCurrentPage();
        }
    });
    document.getElementById('next-page').addEventListener('click', function() {
        if (currentPage < bookPages.length - 1) {
            currentPage++;
            displayCurrentPage();
        }
    });
    
    document.getElementById('submit-review').addEventListener('click', submitReview);
    
    document.querySelectorAll('.tab-btn[data-tab]').forEach(btn => {
        btn.addEventListener('click', function() {
            const tabId = this.getAttribute('data-tab');
            
            document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
            this.classList.add('active');
            
            document.querySelectorAll('.tab-content').forEach(content => {
                content.classList.remove('active');
            });
            document.getElementById(`${tabId}-tab`).classList.add('active');
        });
    });

    initWritingSystem();

    auth.onAuthStateChanged((user) => {
        const authStatus = document.getElementById('auth-status');
        const authBtn = document.getElementById('auth-btn');
        
        if (user) {
            authStatus.textContent = user.displayName || user.email;
            authBtn.innerHTML = `<i class="fas fa-user"></i> <span id="auth-status">${user.displayName || user.email}</span>`;
            
            checkEmailVerification();
            setInterval(checkEmailVerification, 30000);
            
            if (document.getElementById('perfil').classList.contains('active')) {
                updateProfile();
            }
        } else {
            authStatus.textContent = 'Iniciar Sesión';
            authBtn.innerHTML = `<i class="fas fa-user"></i> <span id="auth-status">Iniciar Sesión</span>`;
            
            if (document.getElementById('perfil').classList.contains('active')) {
                updateProfile();
            }
        }
    });

    switchSection('inicio');
});

window.addEventListener('beforeunload', function() {
    stopRealTimeListeners();
});

function switchSection(sectionId) {
    document.querySelectorAll('.main-section').forEach(section => {
        section.classList.remove('active');
    });
    
    document.getElementById(sectionId).classList.add('active');
    
    document.querySelectorAll('.nav-link').forEach(link => {
        link.classList.remove('active');
        if (link.getAttribute('data-section') === sectionId) {
            link.classList.add('active');
        }
    });
    
    stopRealTimeListeners();
    
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
        loadAdminPanel();
    }
}

function startRealTimeListeners() {
    booksListener = booksRef.orderBy('createdAt', 'desc').onSnapshot(
        (snapshot) => {
            updateBooksStats();
            updateProfileStats();
            
            if (document.getElementById('biblioteca').classList.contains('active')) {
                displayBooks();
            }
            
            if (document.getElementById('inicio').classList.contains('active')) {
                displayFeaturedBooks();
                displayRecommendedBooks();
            }
        },
        (error) => {
            console.error("Error en listener de libros:", error);
        }
    );
    
    usersListener = usersRef.onSnapshot(
        (snapshot) => {
            updateUsersStats();
        },
        (error) => {
            console.error("Error en listener de usuarios:", error);
        }
    );
}

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
        
        document.getElementById('total-books').textContent = totalBooks;
        document.getElementById('total-likes').textContent = totalLikes;
    } catch (error) {
        console.error("Error actualizando estadísticas de libros:", error);
    }
}

async function updateUsersStats() {
    try {
        const snapshot = await usersRef.get();
        const totalAuthors = snapshot.size;
        
        document.getElementById('total-authors').textContent = totalAuthors;
    } catch (error) {
        console.error("Error actualizando estadísticas de usuarios:", error);
    }
}

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
        
        document.getElementById('profile-books').textContent = userBooksCount;
        document.getElementById('profile-likes').textContent = userLikesCount;
    } catch (error) {
        console.error("Error actualizando estadísticas del perfil:", error);
    }
}

function createBookCard(book) {
    const bookCard = document.createElement('div');
    bookCard.className = 'book-card';
    
    let coverStyle = '';
    let coverContent = '';
    
    if (book.coverUrl) {
        coverStyle = `background-image: url('${book.coverUrl}');`;
        coverContent = `<div class="cover-text" style="display: none;"></div>`;
    } else if (book.coverDesign) {
        coverStyle = `background: ${book.coverDesign.bgColor}; color: ${book.coverDesign.textColor};`;
        coverContent = `
            <div class="cover-text">
                <h3>${book.title.split(' ').map(word => word[0]).join('')}</h3>
                <p>${book.author}</p>
            </div>
        `;
    } else {
        coverStyle = 'background: linear-gradient(135deg, var(--primary), var(--secondary)); color: white;';
        coverContent = `
            <div class="cover-text">
                <h3>${book.title.split(' ').map(word => word[0]).join('')}</h3>
                <p>${book.author}</p>
            </div>
        `;
    }
    
    bookCard.innerHTML = `
        <div class="book-cover" style="${coverStyle}">
            ${coverContent}
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
                <div class="book-stat">
                    <i class="fas fa-file-alt"></i> ${book.pageCount || 1}
                </div>
            </div>
        </div>
    `;
    
    bookCard.querySelector('.like-btn').addEventListener('click', function() {
        handleLikeBook(book.id);
    });
    
    bookCard.querySelector('.read-btn').addEventListener('click', function() {
        openReader(book);
    });
    
    return bookCard;
}

async function handleUploadFormSubmit(e) {
    e.preventDefault();
    
    const currentUser = auth.currentUser;
    if (!currentUser) {
        alert('Debes iniciar sesión para publicar un libro.');
        return;
    }

    if (!currentBookData.title || !currentBookData.author || !currentBookData.genre || !currentBookData.description) {
        alert('Por favor, completa toda la información básica del libro.');
        switchWritingTab('basic-info');
        return;
    }

    if (!currentBookData.content || currentBookData.wordCount < 100) {
        alert('El contenido del libro debe tener al menos 100 palabras.');
        switchWritingTab('content-editor');
        return;
    }

    const publishBtn = document.getElementById('publish-book-btn');
    const originalText = publishBtn.innerHTML;
    publishBtn.innerHTML = '<span class="loading"></span> Publicando...';
    publishBtn.disabled = true;

    try {
        let coverUrl = null;
        
        if (currentBookData.coverType === 'custom' && currentBookData.coverImage) {
            coverUrl = await uploadCoverImage(currentBookData.coverImage, currentUser.uid);
        }
        
        const bookData = {
            title: currentBookData.title,
            author: currentBookData.author,
            genre: currentBookData.genre,
            description: currentBookData.description,
            content: currentBookData.content,
            authorId: currentUser.uid,
            authorEmail: currentUser.email,
            likes: 0,
            views: 0,
            wordCount: currentBookData.wordCount,
            pageCount: currentBookData.pageCount,
            chapters: currentBookData.chapters,
            coverUrl: coverUrl,
            coverDesign: currentBookData.coverDesign,
            status: 'pending',
            reported: false,
            reportCount: 0,
            reports: [],
            createdAt: firebase.firestore.FieldValue.serverTimestamp(),
            updatedAt: firebase.firestore.FieldValue.serverTimestamp()
        };

        const bookId = await saveBook(bookData);
        
        if (bookId) {
            localStorage.removeItem('publibros_draft');
            clearInterval(autoSaveInterval);
            
            document.getElementById('upload-form').reset();
            document.getElementById('book-content').innerHTML = '';
            currentBookData = {
                title: '',
                author: '',
                genre: '',
                description: '',
                content: '',
                coverType: 'custom',
                coverImage: null,
                coverDesign: null,
                chapters: [],
                wordCount: 0,
                pageCount: 0
            };
            
            document.getElementById('upload-modal').style.display = 'none';
            alert('¡Libro publicado correctamente! Estará disponible después de la moderación.');
        } else {
            throw new Error('Error al guardar el libro en la base de datos');
        }
    } catch (error) {
        console.error("Error publicando libro:", error);
        alert('Error al publicar el libro. Intenta nuevamente.');
    } finally {
        publishBtn.innerHTML = originalText;
        publishBtn.disabled = false;
    }
}

async function uploadCoverImage(imageFile, userId) {
    try {
        const storageRef = storage.ref();
        const coverRef = storageRef.child(`covers/${userId}_${Date.now()}_${imageFile.name}`);
        const snapshot = await coverRef.put(imageFile);
        const downloadURL = await snapshot.ref.getDownloadURL();
        return downloadURL;
    } catch (error) {
        console.error("Error subiendo portada:", error);
        throw error;
    }
}

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

async function getAllBooks() {
    try {
        const snapshot = await booksRef.orderBy('createdAt', 'desc').get();
        const books = [];
        snapshot.forEach(doc => {
            const bookData = doc.data();
            books.push({
                id: doc.id,
                ...bookData,
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

async function handleLoginFormSubmit(e) {
    const email = document.getElementById('login-email').value;
    const password = document.getElementById('login-password').value;

    try {
        await auth.signInWithEmailAndPassword(email, password);
        document.getElementById('auth-modal').style.display = 'none';
        document.getElementById('login-form').reset();
    } catch (error) {
        let errorMessage = "Error al iniciar sesión";
        switch(error.code) {
            case 'auth/user-not-found':
                errorMessage = 'No existe una cuenta con este email.';
                break;
            case 'auth/wrong-password':
                errorMessage = 'Contraseña incorrecta.';
                break;
            case 'auth/invalid-email':
                errorMessage = 'El formato del email no es válido.';
                break;
            default:
                errorMessage = error.message;
        }
        alert(errorMessage);
    }
}

async function handleRegisterFormSubmit(e) {
    const name = document.getElementById('register-name').value;
    const email = document.getElementById('register-email').value;
    const password = document.getElementById('register-password').value;
    const confirmPassword = document.getElementById('register-confirm-password').value;
    
    if (password !== confirmPassword) {
        alert('Las contraseñas no coinciden.');
        return;
    }
    
    if (password.length < 6) {
        alert('La contraseña debe tener al menos 6 caracteres.');
        return;
    }
    
    try {
        const userCredential = await auth.createUserWithEmailAndPassword(email, password);
        const user = userCredential.user;
        
        await user.sendEmailVerification();
        
        await user.updateProfile({
            displayName: name
        });
        
        const usersSnapshot = await usersRef.get();
        const isFirstUser = usersSnapshot.empty;
        
        await saveUserData(user.uid, {
            name: name,
            email: email,
            bio: '',
            avatar: null,
            likedBooks: [],
            myReviews: [],
            favoriteGenres: [],
            emailVerified: false,
            role: isFirstUser ? 'admin' : 'user',
            createdAt: firebase.firestore.FieldValue.serverTimestamp()
        });
        
        document.getElementById('auth-modal').style.display = 'none';
        document.getElementById('register-form').reset();
        alert('¡Registro exitoso! Se ha enviado un email de verificación. Por favor, verifica tu cuenta.');
    } catch (error) {
        let errorMessage = "Error al registrar usuario";
        switch(error.code) {
            case 'auth/email-already-in-use':
                errorMessage = 'Este email ya está registrado.';
                break;
            case 'auth/invalid-email':
                errorMessage = 'El formato del email no es válido.';
                break;
            case 'auth/weak-password':
                errorMessage = 'La contraseña es demasiado débil.';
                break;
            default:
                errorMessage = error.message;
        }
        alert(errorMessage);
    }
}

async function saveUserData(userId, userData) {
    try {
        await usersRef.doc(userId).set(userData, { merge: true });
        return true;
    } catch (error) {
        console.error("Error guardando datos del usuario:", error);
        return false;
    }
}

async function getUserData(userId) {
    try {
        const doc = await usersRef.doc(userId).get();
        return doc.exists ? doc.data() : null;
    } catch (error) {
        console.error("Error obteniendo datos del usuario:", error);
        return null;
    }
}

async function handleEditProfileFormSubmit(e) {
    const currentUser = auth.currentUser;
    if (!currentUser) return;

    const name = document.getElementById('edit-user-name').value;
    const bio = document.getElementById('edit-user-bio').value;
    const avatarFile = document.getElementById('edit-user-avatar').files[0];

    try {
        await currentUser.updateProfile({
            displayName: name
        });

        const userData = {
            name: name,
            bio: bio
        };

        if (avatarFile) {
            const storageRef = storage.ref();
            const avatarRef = storageRef.child(`avatars/${currentUser.uid}`);
            await avatarRef.put(avatarFile);
            userData.avatar = await avatarRef.getDownloadURL();
        }

        await saveUserData(currentUser.uid, userData);

        document.getElementById('edit-profile-modal').style.display = 'none';
        updateProfile();
        alert('Perfil actualizado correctamente.');
    } catch (error) {
        console.error("Error actualizando perfil:", error);
        alert('Error al actualizar el perfil. Intenta nuevamente.');
    }
}

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
    document.getElementById('profile-user-bio').textContent = userData?.bio || "¡Hola! Soy un apasionado de la lectura y la escritura.";
    
    loadUserAvatar(currentUser.uid);
    
    checkEmailVerification();
}

async function loadUserAvatar(userId) {
    const userAvatar = document.getElementById('user-avatar');
    const avatarPlaceholder = document.getElementById('avatar-placeholder');
    
    try {
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
        avatarPlaceholder.style.display = 'flex';
        const existingImg = userAvatar.querySelector('img');
        if (existingImg) {
            existingImg.remove();
        }
        avatarPlaceholder.innerHTML = `<i class="fas fa-user"></i>`;
    }
}

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

function resendEmailVerification() {
    const user = auth.currentUser;
    if (!user) return;

    try {
        user.sendEmailVerification();
        alert('Se ha enviado un nuevo email de verificación. Por favor, revisa tu bandeja de entrada.');
    } catch (error) {
        console.error("Error reenviando verificación:", error);
        alert('Error al reenviar el email de verificación. Intenta nuevamente.');
    }
}

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
            likedBooks = likedBooks.filter(id => id !== bookId);
            currentLikes = Math.max(0, currentLikes - 1);
        } else {
            likedBooks.push(bookId);
            currentLikes += 1;
        }
        
        await booksRef.doc(bookId).update({
            likes: currentLikes
        });
        
        await saveUserData(currentUser.uid, {
            likedBooks: likedBooks
        });
    } catch (error) {
        console.error("Error manejando like:", error);
        alert('Error al procesar el like. Intenta nuevamente.');
    }
}

async function loadHomeData() {
    await displayFeaturedBooks();
    await displayRecommendedBooks();
}

async function displayFeaturedBooks() {
    const container = document.getElementById('featured-books-container');
    const books = await getAllBooks();
    
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

async function displayRecommendedBooks() {
    const container = document.getElementById('recommended-books-container');
    const books = await getAllBooks();
    
    const recommendedBooks = books.sort(() => 0.5 - Math.random()).slice(0, 3);
    
    if (recommendedBooks.length === 0) {
        container.innerHTML = '';
        document.getElementById('recommended-section').style.display = 'none';
        return;
    }
    
    container.innerHTML = '';
    recommendedBooks.forEach(book => {
        const bookCard = createBookCard(book);
        const badge = document.createElement('div');
        badge.className = 'recommendation-badge';
        badge.innerHTML = '<i class="fas fa-star"></i> Recomendado';
        bookCard.querySelector('.book-cover').appendChild(badge);
        container.appendChild(bookCard);
    });
}

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

function updateGenreFilters() {
    document.querySelectorAll('.genre-chip').forEach(chip => {
        chip.classList.remove('active');
        if (chip.getAttribute('data-genre') === selectedGenre) {
            chip.classList.add('active');
        }
    });
}

async function displayBooks() {
    const container = document.getElementById('books-container');
    const books = await getAllBooks();
    
    let filteredBooks = books;
    
    if (selectedGenre !== 'all') {
        filteredBooks = filteredBooks.filter(book => book.genre === selectedGenre);
    }
    
    if (searchTerm) {
        filteredBooks = filteredBooks.filter(book => 
            book.title.toLowerCase().includes(searchTerm.toLowerCase()) || 
            book.author.toLowerCase().includes(searchTerm.toLowerCase()) ||
            book.description.toLowerCase().includes(searchTerm.toLowerCase())
        );
    }
    
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

function openReader(book) {
    currentBook = book;
    currentPage = 0;
    
    document.querySelectorAll('.main-section').forEach(section => {
        section.style.display = 'none';
    });
    
    document.getElementById('reader').style.display = 'block';
    
    document.getElementById('reader-title').textContent = book.title;
    
    prepareBookContent(book.content);
    
    displayCurrentPage();
    
    loadReviews(book.id);
    
    updateBookViews(book.id);
}

function prepareBookContent(content) {
    const words = content.split(' ');
    bookPages = [];
    
    for (let i = 0; i < words.length; i += wordsPerPage) {
        const pageWords = words.slice(i, i + wordsPerPage);
        bookPages.push(pageWords.join(' '));
    }
    
    if (bookPages.length === 0) {
        bookPages.push('Este libro no tiene contenido aún.');
    }
}

function displayCurrentPage() {
    const readerContent = document.getElementById('reader-content');
    const pageInfo = document.getElementById('page-info');
    
    readerContent.textContent = bookPages[currentPage];
    pageInfo.textContent = `Página ${currentPage + 1} de ${bookPages.length}`;
    
    document.getElementById('prev-page').disabled = currentPage === 0;
    document.getElementById('next-page').disabled = currentPage === bookPages.length - 1;
}

function closeReader() {
    document.getElementById('reader').style.display = 'none';
    switchSection('biblioteca');
}

async function updateBookViews(bookId) {
    try {
        const bookDoc = await booksRef.doc(bookId).get();
        const currentViews = bookDoc.data().views || 0;
        
        await booksRef.doc(bookId).update({
            views: currentViews + 1,
            updatedAt: firebase.firestore.FieldValue.serverTimestamp()
        });
    } catch (error) {
        console.error("Error actualizando vistas:", error);
    }
}

async function loadReviews(bookId) {
    try {
        const reviewsContainer = document.getElementById('reviews-container');
        reviewsContainer.innerHTML = '<p>Cargando reseñas...</p>';
        
        const snapshot = await reviewsRef
            .where('bookId', '==', bookId)
            .orderBy('createdAt', 'desc')
            .get();
        
        if (snapshot.empty) {
            reviewsContainer.innerHTML = '<p>No hay reseñas para este libro aún. ¡Sé el primero en opinar!</p>';
            return;
        }
        
        reviewsContainer.innerHTML = '';
        snapshot.forEach(doc => {
            const review = doc.data();
            const reviewElement = createReviewElement(review);
            reviewsContainer.appendChild(reviewElement);
        });
    } catch (error) {
        console.error("Error cargando reseñas:", error);
        document.getElementById('reviews-container').innerHTML = 
            '<p>Error al cargar las reseñas. Intenta nuevamente.</p>';
    }
}

function createReviewElement(review) {
    const reviewDiv = document.createElement('div');
    reviewDiv.className = 'review';
    
    const stars = '★'.repeat(review.rating) + '☆'.repeat(5 - review.rating);
    
    reviewDiv.innerHTML = `
        <div class="review-header">
            <div class="review-author">${review.userName || 'Usuario Anónimo'}</div>
            <div class="review-date">${review.createdAt?.toDate?.().toLocaleDateString() || 'Fecha no disponible'}</div>
        </div>
        <div class="review-rating">${stars}</div>
        <div class="review-content">${review.content}</div>
    `;
    
    return reviewDiv;
}

async function submitReview() {
    const currentUser = auth.currentUser;
    if (!currentUser) {
        alert('Debes iniciar sesión para enviar una reseña.');
        return;
    }
    
    const rating = document.getElementById('review-rating').value;
    const content = document.getElementById('review-content').value.trim();
    
    if (!content) {
        alert('Por favor, escribe tu reseña antes de enviar.');
        return;
    }
    
    try {
        const userData = await getUserData(currentUser.uid);
        
        await reviewsRef.add({
            bookId: currentBook.id,
            userId: currentUser.uid,
            userName: userData?.name || currentUser.displayName || currentUser.email,
            userEmail: currentUser.email,
            rating: parseInt(rating),
            content: content,
            createdAt: firebase.firestore.FieldValue.serverTimestamp()
        });
        
        document.getElementById('review-content').value = '';
        
        await loadReviews(currentBook.id);
        
        updateProfileStats();
        
        alert('¡Reseña enviada correctamente!');
    } catch (error) {
        console.error("Error enviando reseña:", error);
        alert('Error al enviar la reseña. Intenta nuevamente.');
    }
}

async function loadAdminPanel() {
    const currentUser = auth.currentUser;
    if (!currentUser) return;
    
    const userData = await getUserData(currentUser.uid);
    const isAdmin = userData?.role === 'admin';
    
    const adminPanel = document.getElementById('admin-panel');
    if (isAdmin) {
        adminPanel.style.display = 'block';
        await loadPendingBooks();
        await loadReportedBooks();
        await loadUsersForManagement();
    } else {
        adminPanel.style.display = 'none';
    }
}

async function loadPendingBooks() {
    try {
        const container = document.getElementById('pending-books-container');
        container.innerHTML = '<p>Cargando libros pendientes...</p>';
        
        const snapshot = await booksRef
            .where('status', '==', 'pending')
            .get();
        
        if (snapshot.empty) {
            container.innerHTML = '<p>No hay libros pendientes de aprobación.</p>';
            return;
        }
        
        container.innerHTML = '';
        snapshot.forEach(doc => {
            const book = { id: doc.id, ...doc.data() };
            const bookCard = createAdminBookCard(book, 'pending');
            container.appendChild(bookCard);
        });
    } catch (error) {
        console.error("Error cargando libros pendientes:", error);
        document.getElementById('pending-books-container').innerHTML = 
            '<p>Error al cargar libros pendientes.</p>';
    }
}

async function loadReportedBooks() {
    try {
        const container = document.getElementById('reported-books-container');
        container.innerHTML = '<p>Cargando libros reportados...</p>';
        
        const snapshot = await booksRef
            .where('reported', '==', true)
            .get();
        
        if (snapshot.empty) {
            container.innerHTML = '<p>No hay libros reportados.</p>';
            return;
        }
        
        container.innerHTML = '';
        snapshot.forEach(doc => {
            const book = { id: doc.id, ...doc.data() };
            const bookCard = createAdminBookCard(book, 'reported');
            container.appendChild(bookCard);
        });
    } catch (error) {
        console.error("Error cargando libros reportados:", error);
        document.getElementById('reported-books-container').innerHTML = 
            '<p>Error al cargar libros reportados.</p>';
    }
}

function createAdminBookCard(book, type) {
    const card = document.createElement('div');
    card.className = 'book-card';
    
    let statusBadge = '';
    let adminActions = '';
    
    if (type === 'pending') {
        statusBadge = `<div class="book-status status-pending">Pendiente</div>`;
        adminActions = `
            <div class="admin-actions">
                <button class="btn" onclick="approveBook('${book.id}')">Aprobar</button>
                <button class="btn btn-danger" onclick="rejectBook('${book.id}')">Rechazar</button>
            </div>
        `;
    } else if (type === 'reported') {
        statusBadge = `<div class="book-status status-pending">Reportado</div>`;
        
        let reportsHtml = '';
        if (book.reports && book.reports.length > 0) {
            book.reports.forEach(report => {
                reportsHtml += `
                    <div class="report-reason">
                        <strong>Reportado por:</strong> ${report.userEmail}<br>
                        <strong>Razón:</strong> ${report.reason}
                    </div>
                `;
            });
        }
        
        adminActions = `
            <div class="admin-actions">
                <button class="btn" onclick="dismissReports('${book.id}')">Descartar Reportes</button>
                <button class="btn btn-danger" onclick="deleteBook('${book.id}')">Eliminar Libro</button>
            </div>
            ${reportsHtml}
        `;
    }
    
    card.innerHTML = `
        <div class="book-cover">
            ${book.title.split(' ').map(word => word[0]).join('')}
            ${statusBadge}
        </div>
        <div class="book-info">
            <div class="book-title">${book.title}</div>
            <div class="book-author">por ${book.author}</div>
            <div class="book-description">${book.description}</div>
            <div class="book-genre">${genreNames[book.genre]}</div>
            ${adminActions}
        </div>
    `;
    
    return card;
}

async function loadUsersForManagement() {
    try {
        const container = document.getElementById('users-container');
        container.innerHTML = '<p>Cargando usuarios...</p>';
        
        const snapshot = await usersRef.get();
        
        if (snapshot.empty) {
            container.innerHTML = '<p>No hay usuarios registrados.</p>';
            return;
        }
        
        container.innerHTML = '';
        snapshot.forEach(doc => {
            const user = { id: doc.id, ...doc.data() };
            const userElement = createUserManagementElement(user);
            container.appendChild(userElement);
        });
    } catch (error) {
        console.error("Error cargando usuarios:", error);
        document.getElementById('users-container').innerHTML = 
            '<p>Error al cargar usuarios.</p>';
    }
}

function createUserManagementElement(user) {
    const userDiv = document.createElement('div');
    userDiv.className = 'user-management-item';
    
    const isAdmin = user.role === 'admin';
    const isVerified = user.emailVerified;
    
    userDiv.innerHTML = `
        <div class="user-info">
            <div class="user-name">${user.name || 'Usuario'} 
                ${isAdmin ? '<span class="admin-badge">Admin</span>' : ''}
                <span class="verification-badge ${isVerified ? '' : 'unverified'}">
                    <i class="fas fa-${isVerified ? 'check' : 'times'}-circle"></i> 
                    ${isVerified ? 'Verificado' : 'No verificado'}
                </span>
            </div>
            <div class="user-email">${user.email}</div>
            <div class="user-stats">
                <span>Libros: ${user.booksCount || 0}</span>
                <span>Reseñas: ${user.reviewsCount || 0}</span>
            </div>
        </div>
        <div class="user-actions">
            ${!isAdmin ? `<button class="btn" onclick="makeAdmin('${user.id}')">Hacer Admin</button>` : ''}
            <button class="btn btn-danger" onclick="deleteUser('${user.id}')">Eliminar</button>
        </div>
    `;
    
    return userDiv;
}

async function approveBook(bookId) {
    if (!confirm('¿Estás seguro de que quieres aprobar este libro?')) return;
    
    try {
        await booksRef.doc(bookId).update({
            status: 'approved',
            updatedAt: firebase.firestore.FieldValue.serverTimestamp()
        });
        
        alert('Libro aprobado correctamente.');
        await loadPendingBooks();
    } catch (error) {
        console.error("Error aprobando libro:", error);
        alert('Error al aprobar el libro.');
    }
}

async function rejectBook(bookId) {
    if (!confirm('¿Estás seguro de que quieres rechazar este libro?')) return;
    
    try {
        await booksRef.doc(bookId).delete();
        alert('Libro rechazado y eliminado.');
        await loadPendingBooks();
    } catch (error) {
        console.error("Error rechazando libro:", error);
        alert('Error al rechazar el libro.');
    }
}

async function dismissReports(bookId) {
    if (!confirm('¿Estás seguro de que quieres descartar todos los reportes de este libro?')) return;
    
    try {
        await booksRef.doc(bookId).update({
            reported: false,
            reports: [],
            reportCount: 0,
            updatedAt: firebase.firestore.FieldValue.serverTimestamp()
        });
        
        alert('Reportes descartados correctamente.');
        await loadReportedBooks();
    } catch (error) {
        console.error("Error descartando reportes:", error);
        alert('Error al descartar los reportes.');
    }
}

async function deleteBook(bookId) {
    if (!confirm('¿Estás seguro de que quieres eliminar este libro? Esta acción no se puede deshacer.')) return;
    
    try {
        const reviewsSnapshot = await reviewsRef
            .where('bookId', '==', bookId)
            .get();
        
        const batch = db.batch();
        reviewsSnapshot.forEach(doc => {
            batch.delete(doc.ref);
        });
        batch.delete(booksRef.doc(bookId));
        
        await batch.commit();
        
        alert('Libro y reseñas asociadas eliminados correctamente.');
        await loadReportedBooks();
    } catch (error) {
        console.error("Error eliminando libro:", error);
        alert('Error al eliminar el libro.');
    }
}

async function makeAdmin(userId) {
    if (!confirm('¿Estás seguro de que quieres hacer admin a este usuario?')) return;
    
    try {
        await usersRef.doc(userId).update({
            role: 'admin',
            updatedAt: firebase.firestore.FieldValue.serverTimestamp()
        });
        
        alert('Usuario promovido a administrador.');
        await loadUsersForManagement();
    } catch (error) {
        console.error("Error haciendo admin:", error);
        alert('Error al hacer admin al usuario.');
    }
}

async function deleteUser(userId) {
    if (!confirm('¿Estás seguro de que quieres eliminar este usuario? Esta acción no se puede deshacer.')) return;
    
    try {
        const userBooksSnapshot = await booksRef
            .where('authorId', '==', userId)
            .get();
        
        const batch = db.batch();
        userBooksSnapshot.forEach(doc => {
            batch.delete(doc.ref);
        });
        
        const userReviewsSnapshot = await reviewsRef
            .where('userId', '==', userId)
            .get();
        
        userReviewsSnapshot.forEach(doc => {
            batch.delete(doc.ref);
        });
        
        batch.delete(usersRef.doc(userId));
        
        await batch.commit();
        
        alert('Usuario y contenido asociado eliminados correctamente.');
        await loadUsersForManagement();
    } catch (error) {
        console.error("Error eliminando usuario:", error);
        alert('Error al eliminar el usuario.');
    }
}
</script>
</body>
</html>
