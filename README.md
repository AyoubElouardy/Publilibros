<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publibros - Comparte y Lee Libros</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #7B68EE;
            --secondary: #FF6B6B;
            --accent: #4ECDC4;
            --light: #F7F9FC;
            --dark: #2D3748;
            --text: #2D3748;
            --text-light: #718096;
            --shadow: 0 8px 20px rgba(123, 104, 238, 0.15);
            --transition: all 0.3s ease;
            --gradient: linear-gradient(135deg, var(--primary), var(--accent));
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--light);
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
            background-color: white;
            color: var(--dark);
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
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .logo i {
            margin-right: 10px;
            -webkit-text-fill-color: var(--primary);
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 1.5rem;
        }

        nav ul li a {
            color: var(--dark);
            text-decoration: none;
            transition: var(--transition);
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 30px;
        }

        nav ul li a:hover, nav ul li a.active {
            background-color: rgba(123, 104, 238, 0.1);
            color: var(--primary);
        }

        .user-actions {
            display: flex;
            align-items: center;
        }

        .user-actions button {
            background: transparent;
            border: none;
            color: var(--dark);
            margin-left: 15px;
            cursor: pointer;
            font-size: 1.1rem;
            transition: var(--transition);
        }

        .user-actions button:hover {
            color: var(--primary);
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
            background: var(--gradient);
            color: white;
            padding: 5rem 0;
            text-align: center;
            border-radius: 20px;
            margin-bottom: 3rem;
            position: relative;
            overflow: hidden;
        }

        .hero:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: cover;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
            position: relative;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            opacity: 0.9;
            position: relative;
        }

        .btn {
            display: inline-block;
            background-color: white;
            color: var(--primary);
            padding: 0.8rem 1.8rem;
            border: none;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow);
            position: relative;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(0,0,0,0.15);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid white;
            color: white;
            margin-left: 10px;
        }

        .btn-outline:hover {
            background: white;
            color: var(--primary);
        }

        .btn-secondary {
            background-color: var(--primary);
            color: white;
        }

        .btn-secondary:hover {
            background-color: #6A5ACD;
        }

        .btn-danger {
            background-color: var(--secondary);
            color: white;
        }

        .btn-danger:hover {
            background-color: #FF5252;
        }

        /* Secciones */
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary);
            position: relative;
            font-size: 2.2rem;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--gradient);
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
            border-radius: 16px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .book-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }

        .book-cover {
            height: 220px;
            background: var(--gradient);
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
            color: var(--secondary);
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
            background-color: rgba(123, 104, 238, 0.1);
            color: var(--primary);
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
            border-radius: 16px;
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
            background: var(--secondary);
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
            border-radius: 16px;
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
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(123, 104, 238, 0.2);
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
            border-radius: 16px;
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
            border-radius: 12px;
            margin-bottom: 2rem;
        }

        .review {
            background: white;
            padding: 1.5rem;
            border-radius: 12px;
            margin-bottom: 1rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
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
            border-radius: 16px;
            box-shadow: var(--shadow);
        }

        .user-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: var(--gradient);
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
            color: var(--primary);
            border-bottom: 3px solid var(--primary);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
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
            background: var(--accent);
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
            border-radius: 16px;
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
            margin-top: 1.5rem;
            text-align: center;
            color: var(--text-light);
        }

        .form-footer a {
            color: var(--primary);
            text-decoration: none;
            cursor: pointer;
        }

        .form-footer a:hover {
            text-decoration: underline;
        }

        .error-message {
            color: var(--secondary);
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
            background-color: var(--primary);
            color: white;
        }

        /* Panel de administración */
        .admin-panel {
            background: white;
            padding: 2rem;
            border-radius: 16px;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
        }

        .admin-badge {
            background: var(--secondary);
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
            border-radius: 16px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-icon {
            font-size: 2.5rem;
            color: var(--primary);
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

        /* Nuevos estilos para el editor mejorado */
        .editor-container {
            background: white;
            border-radius: 16px;
            box-shadow: var(--shadow);
            overflow: hidden;
            margin-bottom: 2rem;
        }
        
        .editor-toolbar {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
            padding: 1rem;
            border-bottom: 1px solid #eee;
            background: #f8f9fa;
        }
        
        .editor-btn {
            background: white;
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 0.5rem 0.8rem;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .editor-btn:hover {
            background: #e9ecef;
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
        }
        
        .editor-stats {
            padding: 1rem 1.5rem;
            border-top: 1px solid #eee;
            background: #f8f9fa;
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: var(--text-light);
        }
        
        /* Estilos para el sistema de portadas */
        .cover-upload-section {
            margin-bottom: 2rem;
        }
        
        .cover-preview {
            width: 200px;
            height: 280px;
            border: 2px dashed #ddd;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1rem;
            overflow: hidden;
            background: #f8f9fa;
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
            border: 2px solid #ddd;
            border-radius: 12px;
            padding: 1rem;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .cover-option:hover {
            border-color: var(--primary);
        }
        
        .cover-option.selected {
            border-color: var(--primary);
            background: rgba(123, 104, 238, 0.1);
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
        }
        
        /* Estilos para el sistema de capítulos */
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
            padding: 1rem;
            border: 1px solid #eee;
            border-radius: 12px;
            margin-bottom: 0.5rem;
            background: white;
        }
        
        .chapter-item:hover {
            background: #f8f9fa;
        }
        
        .chapter-actions {
            display: flex;
            gap: 0.5rem;
        }
        
        .chapter-btn {
            background: none;
            border: none;
            cursor: pointer;
            color: var(--text-light);
            transition: var(--transition);
        }
        
        .chapter-btn:hover {
            color: var(--primary);
        }
        
        /* Estilos para el modal de escritura mejorado */
        .writing-modal .modal-content {
            max-width: 900px;
            width: 95%;
        }
        
        .writing-tabs {
            display: flex;
            border-bottom: 1px solid #eee;
            margin-bottom: 1.5rem;
        }
        
        .writing-tab {
            padding: 1rem 1.5rem;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 500;
            color: var(--text-light);
            border-bottom: 3px solid transparent;
            transition: var(--transition);
        }
        
        .writing-tab.active {
            color: var(--primary);
            border-bottom: 3px solid var(--primary);
        }
        
        .tab-panel {
            display: none;
        }
        
        .tab-panel.active {
            display: block;
        }
        
        /* Estilos para vista previa de portada en tarjetas */
        .book-card .book-cover {
            background-size: cover;
            background-position: center;
        }
        
        .book-card .book-cover .cover-text {
            background: rgba(0, 0, 0, 0.6);
            padding: 0.5rem;
            border-radius: 8px;
            text-align: center;
        }
        
        .book-status {
            position: absolute;
            top: 15px;
            left: 15px;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 1;
        }
        
        .status-pending {
            background: #f39c12;
            color: white;
        }
        
        .status-approved {
            background: #27ae60;
            color: white;
        }
        
        .status-rejected {
            background: #e74c3c;
            color: white;
        }
        
        .admin-actions {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }
        
        .user-management-item {
            background: white;
            padding: 1.5rem;
            border-radius: 12px;
            margin-bottom: 1rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
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
                font-size: 2.5rem;
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
            
            .writing-tabs {
                flex-direction: column;
            }
            
            .writing-tab {
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
              <!-- Sección Inicio -->
    <section id="inicio" class="main-section active">
        <div class="container">
            <div class="hero">
                <h1>Descubre y Comparte Historias Únicas</h1>
                <p>Publibros es una plataforma vibrante donde autores y lectores se conectan. Comparte tus creaciones, descubre nuevos talentos y forma parte de una comunidad literaria única.</p>
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
        <!-- Modal para subir libro MEJORADO -->
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
                <!-- Pestaña 1: Información Básica -->
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
                
                <!-- Pestaña 2: Diseño de Portada -->
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
                                <i class="fas fa-book fa-3x" style="color: #7f8c8d;"></i>
                                <p style="margin-top: 10px; color: #7f8c8d;">Vista previa de portada</p>
                            </div>
                        </div>
                        
                        <h5>O elige un diseño prediseñado:</h5>
                        <div class="cover-options" id="cover-options">
                            <!-- Los diseños de portada se generarán dinámicamente -->
                        </div>
                    </div>
                    
                    <div class="form-group" style="display: flex; justify-content: space-between; margin-top: 2rem;">
                        <button type="button" class="btn btn-secondary" id="back-to-basic">Anterior: Información</button>
                        <button type="button" class="btn btn-secondary" id="next-to-content">Siguiente: Contenido</button>
                    </div>
                </div>
                
                <!-- Pestaña 3: Editor de Contenido -->
                <div class="tab-panel" id="content-editor-panel">
                    <div class="form-group">
                        <label>Editor de Contenido</label>
                        <div class="editor-container">
                            <div class="editor-toolbar" id="editor-toolbar">
                                <button type="button" class="editor-btn" data-command="bold" title="Negrita"><i class="fas fa-bold"></i></button>
                                <button type="button" class="editor-btn" data-command="italic" title="Itálica"><i class="fas fa-italic"></i></button>
                                <button type="button" class="editor-btn" data-command="underline" title="Subrayado"><i class="fas fa-underline"></i></button>
                                <button type="button" class="editor-btn" data-command="insertUnorderedList" title="Lista"><i class="fas fa-list-ul"></i></button>
                                <button type="button" class="editor-btn" data-command="formatBlock" data-value="H1" title="Título 1">T1</button>
                                <button type="button" class="editor-btn" data-command="formatBlock" data-value="H2" title="Título 2">T2</button>
                                <button type="button" class="editor-btn" data-command="formatBlock" data-value="P" title="Párrafo">P</button>
                                <button type="button" class="editor-btn" id="add-chapter-btn" title="Añadir capítulo"><i class="fas fa-bookmark"></i> Capítulo</button>
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
                            <!-- Los capítulos se añadirán aquí dinámicamente -->
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
                
                <!-- Pestaña 4: Vista Previa -->
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
                            <div class="preview-text" id="preview-content-text" style="
                                background: #f8f9fa; 
                                padding: 1rem; 
                                border-radius: 8px; 
                                max-height: 200px; 
                                overflow-y: auto;
                                white-space: pre-line;
                            "></div>
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
                    <p>Una plataforma vibrante para compartir y descubrir libros de autores emergentes y establecidos.</p>
                    <p>Conectamos a lectores y escritores en una comunidad literaria única.</p>
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

        // Referencias a colecciones de Firestore
        const usersRef = db.collection("users");
        const booksRef = db.collection("books");
        const reviewsRef = db.collection("reviews");

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

        // Variables para el sistema de escritura mejorado
        let currentBookData = {
            title: '',
            author: '',
            genre: '',
            description: '',
            content: '',
            coverType: 'custom', // 'custom' o 'generated'
            coverImage: null,
            coverDesign: null,
            chapters: [],
            wordCount: 0,
            pageCount: 0
        };

        let selectedCoverDesign = null;
        let autoSaveInterval = null;

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
        // SISTEMA DE ESCRITURA MEJORADO
        // ============================

        function initWritingSystem() {
            // Configurar pestañas del modal de escritura
            document.querySelectorAll('.writing-tab').forEach(tab => {
                tab.addEventListener('click', function() {
                    const tabId = this.getAttribute('data-tab');
                    switchWritingTab(tabId);
                });
            });

            // Navegación entre pestañas
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

            // Configurar el editor de texto
            initTextEditor();

            // Configurar el sistema de portadas
            initCoverSystem();

            // Configurar el sistema de capítulos
            initChapterSystem();

            // Configurar el guardado automático
            initAutoSave();
        }

        function switchWritingTab(tabId) {
            // Actualizar pestañas activas
            document.querySelectorAll('.writing-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            document.querySelector(`.writing-tab[data-tab="${tabId}"]`).classList.add('active');

            // Actualizar paneles activos
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

            // Guardar datos básicos
            currentBookData.title = title;
            currentBookData.author = author;
            currentBookData.genre = genre;
            currentBookData.description = description;

            return true;
        }

        function initTextEditor() {
            const editor = document.getElementById('book-content');
            const toolbar = document.getElementById('editor-toolbar');

            // Configurar botones de formato
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

            // Actualizar estadísticas
            editor.addEventListener('input', updateEditorStats);

            // Inicializar estadísticas
            updateEditorStats();
        }

        function updateEditorStats() {
            const editor = document.getElementById('book-content');
            const text = editor.textContent || editor.innerText;
            
            // Contar palabras
            const wordCount = text.trim() ? text.trim().split(/\s+/).length : 0;
            document.getElementById('word-count').textContent = `${wordCount} palabras`;
            
            // Calcular páginas (aproximadamente 300 palabras por página)
            const pageCount = Math.ceil(wordCount / 300);
            document.getElementById('page-count').textContent = `${pageCount} páginas`;
            
            // Actualizar datos del libro
            currentBookData.content = editor.innerHTML;
            currentBookData.wordCount = wordCount;
            currentBookData.pageCount = pageCount;
        }

        function initCoverSystem() {
            const coverUpload = document.getElementById('book-cover-upload');
            const coverPreview = document.getElementById('cover-preview');
            
            // Configurar subida de imagen
            coverUpload.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    // Validar tipo y tamaño
                    if (!file.type.match('image.*')) {
                        alert('Por favor, selecciona un archivo de imagen válido.');
                        return;
                    }
                    
                    if (file.size > 2 * 1024 * 1024) {
                        alert('La imagen no puede ser mayor a 2MB.');
                        return;
                    }
                    
                    // Mostrar previsualización
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        coverPreview.innerHTML = `<img src="${e.target.result}" alt="Portada del libro">`;
                        currentBookData.coverType = 'custom';
                        currentBookData.coverImage = file;
                    };
                    reader.readAsDataURL(file);
                }
            });
            
            // Generar opciones de portadas prediseñadas
            generateCoverOptions();
        }

        function generateCoverOptions() {
            const coverOptions = document.getElementById('cover-options');
            const designs = [
                { id: 'design1', bgColor: '#7B68EE', textColor: '#ffffff', pattern: 'solid' },
                { id: 'design2', bgColor: '#FF6B6B', textColor: '#ffffff', pattern: 'stripes' },
                { id: 'design3', bgColor: '#4ECDC4', textColor: '#ffffff', pattern: 'dots' },
                { id: 'design4', bgColor: '#FFD166', textColor: '#333333', pattern: 'gradient' },
                { id: 'design5', bgColor: '#06D6A0', textColor: '#ffffff', pattern: 'lines' },
                { id: 'design6', bgColor: '#118AB2', textColor: '#ffffff', pattern: 'grid' }
            ];
            
            coverOptions.innerHTML = '';
            
            designs.forEach(design => {
                const option = document.createElement('div');
                option.className = 'cover-option';
                option.setAttribute('data-design', design.id);
                
                // Crear diseño visual
                const designElement = document.createElement('div');
                designElement.className = 'cover-design';
                designElement.style.backgroundColor = design.bgColor;
                designElement.innerHTML = '<i class="fas fa-book"></i>';
                
                option.appendChild(designElement);
                option.appendChild(document.createTextNode('Diseño ' + design.id.replace('design', '')));
                
                option.addEventListener('click', function() {
                    // Quitar selección anterior
                    document.querySelectorAll('.cover-option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    
                    // Seleccionar este diseño
                    this.classList.add('selected');
                    selectedCoverDesign = design;
                    currentBookData.coverType = 'generated';
                    currentBookData.coverDesign = design;
                    
                    // Actualizar previsualización
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
                        // Crear un nuevo capítulo
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
            
            // Botón para gestionar capítulos
            document.getElementById('manage-chapters-btn').addEventListener('click', function() {
                showChapterManager();
            });
        }

        function addChapter(title, range) {
            // Crear marcador de capítulo
            const chapterMarker = document.createElement('span');
            chapterMarker.className = 'chapter-marker';
            chapterMarker.setAttribute('data-chapter-title', title);
            chapterMarker.innerHTML = `[CAPÍTULO: ${title}]`;
            chapterMarker.style.backgroundColor = '#ffeaa7';
            chapterMarker.style.padding = '2px 4px';
            chapterMarker.style.borderRadius = '3px';
            chapterMarker.style.fontSize = '0.8rem';
            
            // Insertar el marcador
            range.insertNode(chapterMarker);
            
            // Añadir a la lista de capítulos
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
                        <button class="chapter-btn edit-chapter" data-index="${index}" title="Editar">
                            <i class="fas fa-edit"></i>
                        </button>
                        <button class="chapter-btn delete-chapter" data-index="${index}" title="Eliminar">
                            <i class="fas fa-trash"></i>
                        </button>
                    </div>
                `;
                
                chapterList.appendChild(chapterItem);
            });
            
            // Configurar eventos para los botones de capítulo
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
            // Implementar un modal más avanzado para gestión de capítulos
            alert('Funcionalidad de gestión avanzada de capítulos en desarrollo.');
        }

        function editChapter(index) {
            const newTitle = prompt('Nuevo título del capítulo:', currentBookData.chapters[index].title);
            if (newTitle) {
                currentBookData.chapters[index].title = newTitle;
                updateChapterList();
                
                // También actualizar los marcadores en el editor
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
            // Esta función actualizaría los marcadores en el editor
            // Implementación simplificada por ahora
        }

        function initAutoSave() {
            // Guardar automáticamente cada 30 segundos
            autoSaveInterval = setInterval(function() {
                if (currentBookData.content) {
                    localStorage.setItem('publibros_draft', JSON.stringify(currentBookData));
                    console.log('Borrador guardado automáticamente');
                }
            }, 30000);
            
            // Cargar borrador guardado si existe
            const savedDraft = localStorage.getItem('publibros_draft');
            if (savedDraft) {
                if (confirm('Tienes un borrador guardado. ¿Quieres continuar donde lo dejaste?')) {
                    currentBookData = JSON.parse(savedDraft);
                    loadDraftData();
                }
            }
        }

        function loadDraftData() {
            // Cargar datos del borrador en el formulario
            document.getElementById('book-title').value = currentBookData.title;
            document.getElementById('book-author').value = currentBookData.author;
            document.getElementById('book-genre').value = currentBookData.genre;
            document.getElementById('book-description').value = currentBookData.description;
            document.getElementById('book-content').innerHTML = currentBookData.content;
            
            updateEditorStats();
            updateChapterList();
        }

        function updatePreview() {
            // Actualizar vista previa con los datos actuales
            document.getElementById('preview-title').textContent = currentBookData.title;
            document.getElementById('preview-author').textContent = `por ${currentBookData.author}`;
            document.getElementById('preview-book-title').textContent = currentBookData.title;
            document.getElementById('preview-book-author').textContent = `por ${currentBookData.author}`;
            document.getElementById('preview-description').textContent = currentBookData.description;
            document.getElementById('preview-genre').textContent = genreNames[currentBookData.genre] || currentBookData.genre;
            
            // Mostrar contenido (primeras 500 palabras)
            const contentText = document.getElementById('book-content').textContent || '';
            const previewText = contentText.substring(0, 500) + (contentText.length > 500 ? '...' : '');
            document.getElementById('preview-content-text').textContent = previewText;
            
            // Actualizar portada en vista previa
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
                previewCover.style.background = 'var(--gradient)';
                previewCover.querySelector('.cover-text').style.display = 'block';
                previewCover.querySelector('.cover-text').style.color = 'white';
            }
        }
                // ============================
        // LECTOR DE LIBROS MEJORADO
        // ============================

        function openReader(book) {
            currentBook = book;
            currentPage = 0;
            
            // Ocultar todas las secciones principales
            document.querySelectorAll('.main-section').forEach(section => {
                section.style.display = 'none';
            });
            
            // Mostrar el lector
            document.getElementById('reader').style.display = 'block';
            
            // Configurar información del libro
            document.getElementById('reader-title').textContent = book.title;
            
            // Preparar el contenido para paginación
            prepareBookContent(book.content);
            
            // Mostrar la primera página
            displayCurrentPage();
            
            // Cargar reseñas existentes
            loadReviews(book.id);
            
            // Actualizar contador de vistas
            updateBookViews(book.id);
        }

        function prepareBookContent(content) {
            // Dividir el contenido en páginas
            const words = content.split(' ');
            bookPages = [];
            
            for (let i = 0; i < words.length; i += wordsPerPage) {
                const pageWords = words.slice(i, i + wordsPerPage);
                bookPages.push(pageWords.join(' '));
            }
            
            // Si no hay páginas (contenido vacío), crear una página vacía
            if (bookPages.length === 0) {
                bookPages.push('Este libro no tiene contenido aún.');
            }
        }

        function displayCurrentPage() {
            const readerContent = document.getElementById('reader-content');
            const pageInfo = document.getElementById('page-info');
            
            readerContent.textContent = bookPages[currentPage];
            pageInfo.textContent = `Página ${currentPage + 1} de ${bookPages.length}`;
            
            // Habilitar/deshabilitar botones según la página actual
            document.getElementById('prev-page').disabled = currentPage === 0;
            document.getElementById('next-page').disabled = currentPage === bookPages.length - 1;
        }

        function closeReader() {
            document.getElementById('reader').style.display = 'none';
            switchSection('biblioteca');
        }

        // ============================
        // SISTEMA DE RESEÑAS COMPLETO
        // ============================

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
                // Obtener datos del usuario
                const userData = await getUserData(currentUser.uid);
                
                // Guardar la reseña
                await reviewsRef.add({
                    bookId: currentBook.id,
                    userId: currentUser.uid,
                    userName: userData?.name || currentUser.displayName || currentUser.email,
                    userEmail: currentUser.email,
                    rating: parseInt(rating),
                    content: content,
                    createdAt: firebase.firestore.FieldValue.serverTimestamp()
                });
                
                // Limpiar el formulario
                document.getElementById('review-content').value = '';
                
                // Recargar las reseñas
                await loadReviews(currentBook.id);
                
                // Actualizar estadísticas del usuario
                updateProfileStats();
                
                alert('¡Reseña enviada correctamente!');
            } catch (error) {
                console.error("Error enviando reseña:", error);
                alert('Error al enviar la reseña. Intenta nuevamente.');
            }
        }

        // ============================
        // PANEL DE ADMINISTRACIÓN COMPLETO
        // ============================

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

        // Funciones de administración
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
                // Eliminar también las reseñas asociadas
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
                // Eliminar libros del usuario
                const userBooksSnapshot = await booksRef
                    .where('authorId', '==', userId)
                    .get();
                
                const batch = db.batch();
                userBooksSnapshot.forEach(doc => {
                    batch.delete(doc.ref);
                });
                
                // Eliminar reseñas del usuario
                const userReviewsSnapshot = await reviewsRef
                    .where('userId', '==', userId)
                    .get();
                
                userReviewsSnapshot.forEach(doc => {
                    batch.delete(doc.ref);
                });
                
                // Eliminar usuario
                batch.delete(usersRef.doc(userId));
                
                await batch.commit();
                
                alert('Usuario y contenido asociado eliminados correctamente.');
                await loadUsersForManagement();
            } catch (error) {
                console.error("Error eliminando usuario:", error);
                alert('Error al eliminar el usuario.');
            }
        }

        // ============================
        // FUNCIONES DE FIREBASE
        // ============================

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
        // MANEJO MEJORADO DEL FORMULARIO DE SUBIDA
        // ============================

        async function handleUploadFormSubmit(e) {
            e.preventDefault();
            
            const currentUser = auth.currentUser;
            if (!currentUser) {
                alert('Debes iniciar sesión para publicar un libro.');
                return;
            }

            // Validar datos mínimos
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

            // Mostrar indicador de carga
            const publishBtn = document.getElementById('publish-book-btn');
            const originalText = publishBtn.innerHTML;
            publishBtn.innerHTML = '<span class="loading"></span> Publicando...';
            publishBtn.disabled = true;

            try {
                let coverUrl = null;
                
                // Subir portada si es personalizada
                if (currentBookData.coverType === 'custom' && currentBookData.coverImage) {
                    coverUrl = await uploadCoverImage(currentBookData.coverImage, currentUser.uid);
                }
                
                // Preparar datos del libro
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
                    // Limpiar borrador
                    localStorage.removeItem('publibros_draft');
                    clearInterval(autoSaveInterval);
                    
                    // Resetear formulario
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
                    
                    // Cerrar modal y mostrar mensaje
                    document.getElementById('upload-modal').style.display = 'none';
                    alert('¡Libro publicado correctamente! Estará disponible después de la moderación.');
                } else {
                    throw new Error('Error al guardar el libro en la base de datos');
                }
            } catch (error) {
                console.error("Error publicando libro:", error);
                alert('Error al publicar el libro. Intenta nuevamente.');
            } finally {
                // Restaurar botón
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
                // ============================
        // ACTUALIZAR LA FUNCIÓN createBookCard PARA MOSTRAR PORTADAS
        // ============================

        function createBookCard(book) {
            const bookCard = document.createElement('div');
            bookCard.className = 'book-card';
            
            // Determinar el estilo de la portada
            let coverStyle = '';
            let coverContent = '';
            
            if (book.coverUrl) {
                // Usar imagen de portada personalizada
                coverStyle = `background-image: url('${book.coverUrl}');`;
                coverContent = `<div class="cover-text" style="display: none;"></div>`;
            } else if (book.coverDesign) {
                // Usar diseño generado
                coverStyle = `background: ${book.coverDesign.bgColor}; color: ${book.coverDesign.textColor};`;
                coverContent = `
                    <div class="cover-text">
                        <h3>${book.title.split(' ').map(word => word[0]).join('')}</h3>
                        <p>${book.author}</p>
                    </div>
                `;
            } else {
                // Usar diseño por defecto
                coverStyle = 'background: var(--gradient); color: white;';
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

        // ============================
        // FUNCIONES AUXILIARES MEJORADAS
        // ============================

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

        // ============================
        // LISTENERS DE TIEMPO REAL
        // ============================

        function startRealTimeListeners() {
            // Listener para libros
            booksListener = booksRef.orderBy('createdAt', 'desc').onSnapshot(
                (snapshot) => {
                    console.log("Actualización en tiempo real de libros recibida");
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
                    console.log("Actualización en tiempo real de usuarios recibida");
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

        // ============================
        // ACTUALIZACIONES DE ESTADÍSTICAS EN TIEMPO REAL
        // ============================

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
                
                console.log(`Estadísticas actualizadas: ${totalBooks} libros, ${totalLikes} likes`);
            } catch (error) {
                console.error("Error actualizando estadísticas de libros:", error);
            }
        }

        async function updateUsersStats() {
            try {
                const snapshot = await usersRef.get();
                const totalAuthors = snapshot.size;
                
                document.getElementById('total-authors').textContent = totalAuthors;
                
                console.log(`Estadísticas actualizadas: ${totalAuthors} autores`);
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
                
                console.log(`Perfil actualizado: ${userBooksCount} libros, ${userLikesCount} likes`);
            } catch (error) {
                console.error("Error actualizando estadísticas del perfil:", error);
            }
        }

        // ============================
        // FUNCIONES DE NAVEGACIÓN Y UI
        // ============================

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

        // ============================
        // VERIFICACIÓN DE EMAIL
        // ============================

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

        // ============================
        // RECUPERACIÓN DE CONTRASEÑA
        // ============================

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
                
                console.log(`Like ${isLiked ? 'quitado' : 'agregado'} al libro ${bookId}`);
            } catch (error) {
                console.error("Error manejando like:", error);
                alert('Error al procesar el like. Intenta nuevamente.');
            }
        }

        // ============================
        // FUNCIONES DE INTERFAZ
        // ============================

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
            
            loadUserAvatar(currentUser.uid);
            
            checkEmailVerification();
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

            document.querySelectorAll('.nav-link-footer').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const sectionId = this.getAttribute('data-section');
                    switchSection(sectionId);
                });
            });

            // Configurar botones de modales
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

            // Cerrar modales al hacer clic fuera
            window.addEventListener('click', function(event) {
                if (event.target.classList.contains('modal')) {
                    event.target.style.display = 'none';
                }
            });

            // Tabs de autenticación
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

            // Switch entre login y registro
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

            // Recuperación de contraseña
            document.getElementById('forgot-password').addEventListener('click', function(e) {
                e.preventDefault();
                handlePasswordReset();
            });

            // Envío de formularios
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

            // Filtros y búsqueda
            document.getElementById('search-books').addEventListener('input', function(e) {
                searchTerm = e.target.value;
                displayBooks();
            });

            document.getElementById('filter-books').addEventListener('change', function(e) {
                currentFilter = e.target.value;
                displayBooks();
            });

            // Reenviar verificación
            document.getElementById('resend-verification').addEventListener('click', function() {
                resendEmailVerification();
            });

            // Configurar el lector de libros
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
            
            // Configurar el envío de reseñas
            document.getElementById('submit-review').addEventListener('click', submitReview);
            
            // Configurar tabs del panel de administración
            document.querySelectorAll('.tab-btn[data-tab]').forEach(btn => {
                btn.addEventListener('click', function() {
                    const tabId = this.getAttribute('data-tab');
                    
                    // Actualizar botones activos
                    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Mostrar contenido activo
                    document.querySelectorAll('.tab-content').forEach(content => {
                        content.classList.remove('active');
                    });
                    document.getElementById(`${tabId}-tab`).classList.add('active');
                });
            });

            // Inicializar el sistema de escritura mejorado
            initWritingSystem();

            // Configurar listener para cambios de autenticación
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

            // Iniciar en la sección de inicio
            switchSection('inicio');
        });

        // Limpiar listeners cuando se cierre la página
        window.addEventListener('beforeunload', function() {
            stopRealTimeListeners();
        });

        // ============================
        // MANEJO DE FORMULARIOS
        // ============================

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
                
                // Verificar si es el primer usuario y hacerlo admin
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
    </script>
</body>
</html>
        </div>
    </header>
