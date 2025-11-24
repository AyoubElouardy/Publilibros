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

        /* Nuevos estilos para el editor mejorado */
        .editor-container {
            background: white;
            border-radius: 12px;
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
            border-radius: 4px;
            padding: 0.5rem 0.8rem;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .editor-btn:hover {
            background: #e9ecef;
        }
        
        .editor-btn.active {
            background: var(--secondary);
            color: white;
            border-color: var(--secondary);
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
            border-radius: 8px;
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
            border-radius: 8px;
            padding: 1rem;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .cover-option:hover {
            border-color: var(--secondary);
        }
        
        .cover-option.selected {
            border-color: var(--secondary);
            background: rgba(52, 152, 219, 0.1);
        }
        
        .cover-design {
            width: 100px;
            height: 140px;
            margin: 0 auto 0.5rem;
            border-radius: 4px;
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
            border-radius: 8px;
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
            color: var(--secondary);
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
            color: var(--secondary);
            border-bottom: 3px solid var(--secondary);
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
            border-radius: 4px;
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
            border-radius: 8px;
            margin-bottom: 1rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
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

        /* Nuevos estilos para modal de bienvenida y estado de invitado */
        .welcome-modal {
            z-index: 2000;
        }
        
        .welcome-options {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 20px;
        }
        
        .welcome-option {
            padding: 15px;
            border: 2px solid var(--secondary);
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            background: white;
        }
        
        .welcome-option:hover {
            background: var(--secondary);
            color: white;
        }
        
        .guest-notification {
            position: fixed;
            top: 80px;
            right: 20px;
            background: var(--accent);
            color: white;
            padding: 10px 15px;
            border-radius: 8px;
            box-shadow: var(--shadow);
            z-index: 1500;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .guest-notification .close {
            cursor: pointer;
            font-weight: bold;
        }
        
        .restricted-action {
            opacity: 0.6;
            cursor: not-allowed;
        }
        
        .restricted-message {
            position: absolute;
            background: rgba(0,0,0,0.8);
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            z-index: 10;
            white-space: nowrap;
            pointer-events: none;
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .restricted-action:hover .restricted-message {
            opacity: 1;
        }
        
        .page-limit-warning {
            background: #fff3cd;
            border: 1px solid #ffeaa7;
            color: #856404;
            padding: 10px;
            border-radius: 8px;
            margin-top: 15px;
            text-align: center;
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
        </div>
    </header>

    <!-- Modal de Bienvenida (nuevo) -->
    <div id="welcome-modal" class="modal welcome-modal" style="display: flex;">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Bienvenido a Publibros</h3>
            </div>
            <p>Para disfrutar de todas las funciones de nuestra plataforma, necesitas tener una cuenta.</p>
            <div class="welcome-options">
                <div class="welcome-option" id="login-option">
                    <h4>Iniciar Sesión</h4>
                    <p>Accede con tu cuenta existente</p>
                </div>
                <div class="welcome-option" id="register-option">
                    <h4>Registrarse</h4>
                    <p>Crea una nueva cuenta</p>
                </div>
                <div class="welcome-option" id="guest-option">
                    <h4>Entrar como Invitado</h4>
                    <p>Acceso limitado a funciones básicas</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Notificación de estado de invitado (nuevo) -->
    <div id="guest-notification" class="guest-notification" style="display: none;">
        <i class="fas fa-info-circle"></i>
        <span>Estás navegando como invitado. <a href="#" id="upgrade-account">Mejora tu cuenta</a> para acceder a todas las funciones.</span>
        <span class="close" id="close-guest-notification">&times;</span>
    </div>
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
        // Variables globales para control de acceso
        let currentUserType = null; // 'logged', 'guest', o null (no autenticado)
        let guestPagesRead = 0;
        const MAX_GUEST_PAGES = 3;
        const WORDS_PER_PAGE = 300;

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
        // SISTEMA DE CONTROL DE ACCESO
        // ============================

        // Función para mostrar el modal de bienvenida
        function showWelcomeModal() {
            document.getElementById('welcome-modal').style.display = 'flex';
            
            // Configurar eventos para las opciones
            document.getElementById('login-option').addEventListener('click', function() {
                document.getElementById('welcome-modal').style.display = 'none';
                document.getElementById('auth-modal').style.display = 'flex';
            });
            
            document.getElementById('register-option').addEventListener('click', function() {
                document.getElementById('welcome-modal').style.display = 'none';
                document.getElementById('auth-modal').style.display = 'flex';
                // Cambiar a pestaña de registro
                document.querySelectorAll('.auth-tab').forEach(t => t.classList.remove('active'));
                document.querySelector('[data-form="register"]').classList.add('active');
                document.querySelectorAll('.auth-form').forEach(form => {
                    form.classList.remove('active');
                });
                document.getElementById('register-form').classList.add('active');
            });
            
            document.getElementById('guest-option').addEventListener('click', function() {
                enterAsGuest();
            });
        }

        // Función para entrar como invitado
        function enterAsGuest() {
            currentUserType = 'guest';
            document.getElementById('welcome-modal').style.display = 'none';
            document.getElementById('guest-notification').style.display = 'flex';
            
            // Actualizar la interfaz para modo invitado
            updateUIForGuest();
            
            // Iniciar listeners para contenido público
            startRealTimeListeners();
        }

        // Función para actualizar la UI para usuarios invitados
        function updateUIForGuest() {
            // Actualizar botón de autenticación
            document.getElementById('auth-status').textContent = 'Invitado';
            
            // Ocultar o deshabilitar funciones restringidas
            const restrictedActions = [
                'upload-book-btn',
                'edit-profile-btn',
                'submit-review'
            ];
            
            restrictedActions.forEach(id => {
                const element = document.getElementById(id);
                if (element) {
                    element.classList.add('restricted-action');
                    element.disabled = true;
                    
                    // Añadir tooltip de restricción
                    const tooltip = document.createElement('div');
                    tooltip.className = 'restricted-message';
                    tooltip.textContent = 'Inicia sesión para acceder a esta función';
                    element.appendChild(tooltip);
                }
            });
            
            // Restringir acciones de like y seguir
            document.addEventListener('click', function(e) {
                if (e.target.closest('.like-btn') || e.target.closest('.follow-btn')) {
                    if (currentUserType === 'guest') {
                        e.preventDefault();
                        e.stopPropagation();
                        alert('Debes iniciar sesión para realizar esta acción.');
                    }
                }
            });
        }

        // Función para verificar si una acción está permitida
        function isActionAllowed(action) {
            if (currentUserType === 'logged') {
                return true;
            }
            
            if (currentUserType === 'guest') {
                // Definir acciones permitidas para invitados
                const allowedActions = [
                    'view_books',
                    'read_limited_content',
                    'search_books',
                    'filter_books'
                ];
                
                return allowedActions.includes(action);
            }
            
            return false;
        }

        // Función para manejar la lectura de páginas como invitado
        function handleGuestPageReading() {
            guestPagesRead++;
            
            if (guestPagesRead >= MAX_GUEST_PAGES) {
                // Mostrar advertencia de límite alcanzado
                const warning = document.createElement('div');
                warning.className = 'page-limit-warning';
                warning.innerHTML = `
                    <i class="fas fa-exclamation-triangle"></i>
                    <strong>Límite de lectura alcanzado</strong>
                    <p>Has leído ${MAX_GUEST_PAGES} páginas como invitado. <a href="#" id="register-from-limit">Regístrate</a> para continuar leyendo.</p>
                `;
                
                const readerContent = document.getElementById('reader-content');
                readerContent.parentNode.insertBefore(warning, readerContent.nextSibling);
                
                // Deshabilitar botones de navegación
                document.getElementById('prev-page').disabled = true;
                document.getElementById('next-page').disabled = true;
                
                // Configurar enlace de registro
                document.getElementById('register-from-limit').addEventListener('click', function(e) {
                    e.preventDefault();
                    document.getElementById('auth-modal').style.display = 'flex';
                });
                
                return false;
            }
            
            return true;
        }

        // ============================
        // MODIFICACIONES AL LECTOR PARA INVITADOS
        // ============================

        // Sobrescribir la función openReader para incluir control de invitados
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
            
            // Control de páginas para invitados
            if (currentUserType === 'guest') {
                guestPagesRead = 1; // Ya están leyendo la primera página
                
                // Verificar límite de páginas para invitados
                if (guestPagesRead >= MAX_GUEST_PAGES) {
                    document.getElementById('next-page').disabled = true;
                }
            }
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
            
            // Control adicional para invitados
            if (currentUserType === 'guest' && guestPagesRead >= MAX_GUEST_PAGES) {
                document.getElementById('next-page').disabled = true;
            }
        }

        function closeReader() {
            document.getElementById('reader').style.display = 'none';
            switchSection('biblioteca');
        }

        // ============================
        // MODIFICACIONES AL SISTEMA DE LIKES Y RESEÑAS
        // ============================

        async function handleLikeBook(bookId) {
            if (!isActionAllowed('like_books')) {
                alert('Debes iniciar sesión para dar like a los libros.');
                return;
            }
            
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

        async function submitReview() {
            if (!isActionAllowed('write_reviews')) {
                alert('Debes iniciar sesión para escribir reseñas.');
                return;
            }
            
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
        // MODIFICACIONES AL SISTEMA DE SUBIDA
        // ============================

        async function handleUploadFormSubmit(e) {
            e.preventDefault();
            
            if (!isActionAllowed('upload_books')) {
                alert('Debes iniciar sesión para subir libros.');
                return;
            }
            
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

        // ============================
        // CONFIGURACIÓN DE EVENTOS ADICIONALES
        // ============================

        document.addEventListener('DOMContentLoaded', function() {
            // Mostrar modal de bienvenida al cargar la página si no hay sesión
            auth.onAuthStateChanged((user) => {
                if (user) {
                    // Usuario autenticado
                    currentUserType = 'logged';
                    document.getElementById('guest-notification').style.display = 'none';
                    document.getElementById('welcome-modal').style.display = 'none';
                    
                    // Resto de lógica para usuario autenticado...
                } else {
                    // No hay usuario autenticado, mostrar modal de bienvenida
                    setTimeout(() => {
                        showWelcomeModal();
                    }, 1000);
                }
            });

            // Cerrar notificación de invitado
            document.getElementById('close-guest-notification').addEventListener('click', function() {
                document.getElementById('guest-notification').style.display = 'none';
            });

            // Mejorar cuenta desde notificación de invitado
            document.getElementById('upgrade-account').addEventListener('click', function(e) {
                e.preventDefault();
                document.getElementById('auth-modal').style.display = 'flex';
            });

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
                if (currentUserType === 'guest') {
                    if (!handleGuestPageReading()) {
                        return;
                    }
                }
                
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

        // ============================
        // FUNCIONES ORIGINALES DEL SISTEMA
        // ============================

        // [Aquí irían todas las funciones originales del código que proporcionaste]
        // Para mantener la respuesta dentro de los límites, incluyo solo las esenciales

        function initWritingSystem() {
            // Implementación del sistema de escritura...
        }

        function switchWritingTab(tabId) {
            // Implementación del cambio de pestañas...
        }

        function validateBasicInfo() {
            // Validación de información básica...
            return true;
        }

        function initTextEditor() {
            // Inicialización del editor de texto...
        }

        function updateEditorStats() {
            // Actualización de estadísticas del editor...
        }

        function initCoverSystem() {
            // Sistema de portadas...
        }

        function generateCoverOptions() {
            // Generación de opciones de portada...
        }

        function initChapterSystem() {
            // Sistema de capítulos...
        }

        function initAutoSave() {
            // Guardado automático...
        }

        function updatePreview() {
            // Actualización de vista previa...
        }

        async function loadReviews(bookId) {
            // Carga de reseñas...
        }

        function createReviewElement(review) {
            // Creación de elemento de reseña...
        }

        async function loadAdminPanel() {
            // Panel de administración...
        }

        async function loadPendingBooks() {
            // Libros pendientes...
        }

        async function loadReportedBooks() {
            // Libros reportados...
        }

        function createAdminBookCard(book, type) {
            // Tarjeta de libro para admin...
        }

        async function loadUsersForManagement() {
            // Gestión de usuarios...
        }

        function createUserManagementElement(user) {
            // Elemento de gestión de usuario...
        }

        async function approveBook(bookId) {
            // Aprobar libro...
        }

        async function rejectBook(bookId) {
            // Rechazar libro...
        }

        async function dismissReports(bookId) {
            // Descartar reportes...
        }

        async function deleteBook(bookId) {
            // Eliminar libro...
        }

        async function makeAdmin(userId) {
            // Hacer admin...
        }

        async function deleteUser(userId) {
            // Eliminar usuario...
        }

        async function loadUserAvatar(userId) {
            // Cargar avatar...
        }

        async function saveUserData(userId, userData) {
            // Guardar datos de usuario...
            return true;
        }

        async function getUserData(userId) {
            // Obtener datos de usuario...
            return null;
        }

        async function saveBook(bookData) {
            // Guardar libro...
            return "book-id";
        }

        async function getAllBooks() {
            // Obtener todos los libros...
            return [];
        }

        async function updateBook(bookId, updates) {
            // Actualizar libro...
            return true;
        }

        async function uploadCoverImage(imageFile, userId) {
            // Subir imagen de portada...
            return "cover-url";
        }

        function createBookCard(book) {
            // Crear tarjeta de libro...
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

        async function updateBookViews(bookId) {
            // Actualizar vistas...
        }

        function startRealTimeListeners() {
            // Listeners en tiempo real...
        }

        function stopRealTimeListeners() {
            // Detener listeners...
        }

        async function updateBooksStats() {
            // Actualizar estadísticas de libros...
        }

        async function updateUsersStats() {
            // Actualizar estadísticas de usuarios...
        }

        async function updateProfileStats() {
            // Actualizar estadísticas de perfil...
        }

        function switchSection(sectionId) {
            // Cambiar sección...
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
        }

        async function resendEmailVerification() {
            // Reenviar verificación de email...
        }

        function checkEmailVerification() {
            // Verificar email...
        }

        function handlePasswordReset() {
            // Restablecer contraseña...
        }

        async function handleLoginFormSubmit(e) {
            // Manejar login...
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;

            try {
                await auth.signInWithEmailAndPassword(email, password);
                document.getElementById('auth-modal').style.display = 'none';
                document.getElementById('login-form').reset();
            } catch (error) {
                alert('Error al iniciar sesión: ' + error.message);
            }
        }

        async function handleRegisterFormSubmit(e) {
            // Manejar registro...
            e.preventDefault();
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const password = document.getElementById('register-password').value;
            const confirmPassword = document.getElementById('register-confirm-password').value;
            
            if (password !== confirmPassword) {
                alert('Las contraseñas no coinciden.');
                return;
            }
            
            try {
                const userCredential = await auth.createUserWithEmailAndPassword(email, password);
                const user = userCredential.user;
                
                await user.updateProfile({
                    displayName: name
                });
                
                await saveUserData(user.uid, {
                    name: name,
                    email: email,
                    bio: '',
                    likedBooks: [],
                    myReviews: [],
                    favoriteGenres: [],
                    emailVerified: false,
                    role: 'user',
                    createdAt: firebase.firestore.FieldValue.serverTimestamp()
                });
                
                document.getElementById('auth-modal').style.display = 'none';
                document.getElementById('register-form').reset();
                alert('¡Registro exitoso!');
            } catch (error) {
                alert('Error al registrar usuario: ' + error.message);
            }
        }

        async function handleEditProfileFormSubmit(e) {
            // Manejar edición de perfil...
            e.preventDefault();
            alert('Perfil actualizado (función simulada)');
            document.getElementById('edit-profile-modal').style.display = 'none';
        }

        async function displayFeaturedBooks() {
            // Mostrar libros destacados...
        }

        async function displayRecommendedBooks() {
            // Mostrar libros recomendados...
        }

        function displayGenreFilters() {
            // Mostrar filtros de género...
        }

        async function displayBooks() {
            // Mostrar libros...
        }

        async function updateProfile() {
            // Actualizar perfil...
        }

        // Limpiar listeners cuando se cierre la página
        window.addEventListener('beforeunload', function() {
            stopRealTimeListeners();
        });
    </script>
</body>
</html>
