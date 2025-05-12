<!DOCTYPE html>
<html lang="fr" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Portfolio expert de Safouane Lamkimel - Développeur Fullstack, UI/UX Designer & Consultant Tech">
    <meta name="keywords" content="Safouane Lamkimel, Développeur Fullstack, React, Node.js, Portfolio">
    <meta property="og:title" content="Safouane Lamkimel | Expert en Développement Web">
    <meta property="og:image" content="https://i.imgur.com/your-social-preview.jpg">
    <title>Safouane Lamkimel | Expert Fullstack</title>
    
    <!-- Preload CSS/JS -->
    <link rel="preload" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" as="style">
    <link rel="preload" href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" as="font">
    
    <!-- CSS Libraries -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    
    <!-- Favicon -->
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    
    <style>
        /* ===== VARIABLES & RESET ===== */
        :root {
            --primary: #6C63FF;
            --primary-dark: #564FD1;
            --secondary: #FF6584;
            --accent: #20C997;
            --dark-1: #121212;
            --dark-2: #1E1E1E;
            --light-1: #FFFFFF;
            --light-2: #F8F9FA;
            --text-dark: #2B2D42;
            --text-light: #E9ECEF;
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.1);
            --shadow-sm: 0 4px 6px rgba(0, 0, 0, 0.1);
            --shadow-md: 0 10px 15px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 20px 25px rgba(0, 0, 0, 0.15);
            --border-radius: 12px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Poppins', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.7;
            background-color: var(--light-1);
            color: var(--text-dark);
            overflow-x: hidden;
            position: relative;
        }
        
        body.dark-mode {
            background-color: var(--dark-1);
            color: var(--text-light);
        }
        
        /* ===== TYPOGRAPHY ===== */
        h1, h2, h3, h4 {
            font-weight: 700;
            line-height: 1.3;
        }
        
        h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
        }
        
        h2 {
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 2px;
        }
        
        p {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 700px;
        }
        
        /* ===== REUSABLE COMPONENTS ===== */
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        
        .btn {
            display: inline-block;
            padding: 0.8rem 1.8rem;
            border-radius: var(--border-radius);
            font-weight: 600;
            text-decoration: none;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            box-shadow: var(--shadow-sm);
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-md);
        }
        
        /* ===== HEADER ===== */
        header {
            padding: 6rem 0 4rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .header-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(108, 99, 255, 0.03) 0%, rgba(255, 101, 132, 0.03) 100%);
            z-index: -1;
        }
        
        .avatar-container {
            position: relative;
            width: 220px;
            height: 220px;
            margin: 0 auto 2rem;
        }
        
        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid var(--primary);
            box-shadow: 0 15px 35px rgba(108, 99, 255, 0.3);
            position: relative;
            z-index: 2;
            animation: float 6s ease-in-out infinite;
        }
        
        .avatar-ring {
            position: absolute;
            top: -15px;
            left: -15px;
            right: -15px;
            bottom: -15px;
            border: 3px dashed var(--primary);
            border-radius: 50%;
            animation: spin 25s linear infinite;
            opacity: 0.5;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        @keyframes spin {
            100% { transform: rotate(360deg); }
        }
        
        .name-highlight {
            display: inline-block;
            position: relative;
        }
        
        .name-highlight::after {
            content: '';
            position: absolute;
            bottom: 8px;
            left: 0;
            width: 100%;
            height: 12px;
            background: rgba(108, 99, 255, 0.2);
            z-index: -1;
            border-radius: 20px;
        }
        
        .tagline {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            opacity: 0.9;
        }
        
        /* ===== DISCORD CARD ===== */
        .discord-card {
            background: linear-gradient(135deg, #5865F2 0%, #3A45B4 100%);
            color: white;
            max-width: 320px;
            margin: 2rem auto;
            padding: 1.5rem;
            border-radius: var(--border-radius);
            display: flex;
            align-items: center;
            gap: 15px;
            box-shadow: var(--shadow-lg);
            transition: var(--transition);
            text-decoration: none;
        }
        
        .discord-card:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 15px 30px rgba(88, 101, 242, 0.4);
        }
        
        .discord-logo {
            font-size: 2.5rem;
            flex-shrink: 0;
        }
        
        .discord-info {
            line-height: 1.4;
            text-align: left;
        }
        
        .discord-username {
            font-weight: 600;
            font-size: 1.2rem;
        }
        
        .discord-click {
            font-size: 0.9rem;
            opacity: 0.8;
            margin-top: 5px;
        }
        
        /* ===== SOCIAL LINKS ===== */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 2.5rem 0;
            flex-wrap: wrap;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            color: white;
            text-decoration: none;
            transition: var(--transition);
            box-shadow: var(--shadow-sm);
        }
        
        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: var(--shadow-md);
        }
        
        .discord { background: #5865F2; }
        .github { background: #333333; }
        .linkedin { background: #0A66C2; }
        .twitter { background: #1DA1F2; }
        .email { background: #D44638; }
        
        /* ===== NAVIGATION ===== */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 1.5rem 0;
            z-index: 1000;
            transition: var(--transition);
        }
        
        nav.scrolled {
            background: rgba(255, 255, 255, 0.95);
            box-shadow: var(--shadow-sm);
            padding: 1rem 0;
        }
        
        body.dark-mode nav.scrolled {
            background: rgba(30, 30, 30, 0.95);
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-weight: 700;
            font-size: 1.3rem;
            text-decoration: none;
            color: var(--primary);
        }
        
        .nav-links {
            display: flex;
            gap: 2rem;
        }
        
        .nav-link {
            text-decoration: none;
            font-weight: 500;
            color: inherit;
            position: relative;
            transition: var(--transition);
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
        }
        
        .nav-link:hover::after {
            width: 100%;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: inherit;
            cursor: pointer;
        }
        
        /* ===== SECTIONS ===== */
        section {
            padding: 5rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        /* About Section */
        #about {
            background-color: var(--light-2);
        }
        
        body.dark-mode #about {
            background-color: var(--dark-2);
        }
        
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        
        .about-text p {
            margin-bottom: 1.5rem;
        }
        
        .skills-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 1rem;
        }
        
        .skill-item {
            background: rgba(108, 99, 255, 0.1);
            padding: 1rem;
            border-radius: 8px;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            transition: var(--transition);
        }
        
        .skill-item:hover {
            transform: translateY(-3px);
            background: rgba(108, 99, 255, 0.2);
        }
        
        .skill-icon {
            font-size: 1.2rem;
            color: var(--primary);
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background: var(--light-1);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }
        
        body.dark-mode .project-card {
            background: var(--dark-2);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
        }
        
        .project-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .project-info {
            padding: 1.5rem;
        }
        
        .project-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }
        
        .project-description {
            margin-bottom: 1rem;
            opacity: 0.8;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }
        
        .project-tag {
            background: rgba(108, 99, 255, 0.1);
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        /* Contact Section */
        #contact {
            background: linear-gradient(135deg, rgba(108, 99, 255, 0.03) 0%, rgba(255, 101, 132, 0.03) 100%);
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        
        .contact-method {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .contact-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }
        
        .contact-form {
            background: var(--light-1);
            padding: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
        }
        
        body.dark-mode .contact-form {
            background: var(--dark-2);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        input, textarea {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-family: inherit;
            transition: var(--transition);
        }
        
        body.dark-mode input,
        body.dark-mode textarea {
            background: var(--dark-1);
            border-color: #444;
            color: inherit;
        }
        
        textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background: var(--dark-1);
            color: var(--text-light);
            padding: 3rem 0;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1.5rem;
        }
        
        .footer-logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .footer-links {
            display: flex;
            gap: 2rem;
        }
        
        .footer-link {
            color: inherit;
            text-decoration: none;
            transition: var(--transition);
        }
        
        .footer-link:hover {
            color: var(--primary);
        }
        
        .copyright {
            opacity: 0.7;
            font-size: 0.9rem;
        }
        
        /* ===== DARK MODE TOGGLE ===== */
        .theme-toggle {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            box-shadow: var(--shadow-md);
            z-index: 100;
            transition: var(--transition);
        }
        
        .theme-toggle:hover {
            transform: scale(1.1) rotate(30deg);
        }
        
        /* ===== RESPONSIVE DESIGN ===== */
        @media (max-width: 992px) {
            .about-content,
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .about-image {
                order: -1;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
        
        /* ===== ANIMATIONS ===== */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .animate {
            animation: fadeInUp 0.8s ease-out forwards;
        }
        
        .delay-1 { animation-delay: 0.2s; }
        .delay-2 { animation-delay: 0.4s; }
        .delay-3 { animation-delay: 0.6s; }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="container nav-container">
            <a href="#" class="logo">Safouane.</a>
            <div class="nav-links">
                <a href="#about" class="nav-link">À Propos</a>
                <a href="#skills" class="nav-link">Compétences</a>
                <a href="#projects" class="nav-link">Projets</a>
                <a href="#contact" class="nav-link">Contact</a>
            </div>
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </nav>

    <!-- Header/Hero Section -->
    <header>
        <div class="header-bg"></div>
        <div class="container">
            <div class="avatar-container animate__animated animate__fadeIn">
                <div class="avatar-ring"></div>
                <img src="https://i.imgur.com/your-photo.jpg" alt="Safouane Lamkimel" class="avatar">
            </div>
            
            <h1 class="animate__animated animate__fadeIn animate__delay-1s">
                <span class="name-highlight">Safouane Lamkimel</span>
            </h1>
            
            <p class="tagline animate__animated animate__fadeIn animate__delay-2s">
                Développeur Fullstack | Expert UI/UX | Créateur de solutions digitales innovantes
            </p>
            
            <a href="https://discord.com/users/supersayan123." 
               class="discord-card animate__animated animate__fadeIn animate__delay-3s" 
               target="_blank">
                <div class="discord-logo">
                    <i class="fab fa-discord"></i>
                </div>
                <div class="discord-info">
                    <div class="discord-username">supersayan123</div>
                    <div class="discord-click">Discutons sur Discord</div>
                </div>
            </a>
            
            <div class="social-links">
                <a href="https://github.com/safouane" class="social-link github" target="_blank">
                    <i class="fab fa-github"></i>
                </a>
                <a href="https://linkedin.com/in/safouane-lamkimel" class="social-link linkedin" target="_blank">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="https://twitter.com/safouane" class="social-link twitter" target="_blank">
                    <i class="fab fa-twitter"></i>
                </a>
                <a href="mailto:contact@safouane.dev" class="social-link email">
                    <i class="fas fa-envelope"></i>
                </a>
            </div>
        </div>
    </header>

    <!-- About Section -->
    <section id="about" class="animate">
        <div class="container">
            <div class="section-title">
                <h2>À Propos de Moi</h2>
            </div>
            
            <div class="about-content">
                <div class="about-text">
                    <p>
                        Passionné par les technologies web depuis plus de 5 ans, je combine expertise technique 
                        et sens créatif pour concevoir des expériences digitales mémorables.
                    </p>
                    <p>
                        Spécialisé dans le développement Fullstack JavaScript (React.js, Node.js, TypeScript), 
                        j'ai accompagné plus de 15 clients dans la réalisation de leurs projets web.
                    </p>
                    <p>
                        Mon approche : écoute active, solutions sur-mesure et livraison de code robuste 
                        et maintenable.
                    </p>
                    <a href="#contact" class="btn btn-primary">Travaillons ensemble</a>
                </div>
                
                <div class="about-image">
                    <img src="https://i.imgur.com/about-image.jpg" alt="Safouane au travail" 
                         style="width:100%; border-radius: var(--border-radius); box-shadow: var(--shadow-md);">
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="animate delay-1">
        <div class="container">
            <div class="section-title">
                <h2>Mes Compétences</h2>
            </div>
            
            <div class="skills-list">
                <div class="skill-item">
                    <i class="fab fa-react skill-icon"></i>
                    <span>React.js</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-node-js skill-icon"></i>
                    <span>Node.js</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js skill-icon"></i>
                    <span>JavaScript</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-html5 skill-icon"></i>
                    <span>HTML5</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-css3-alt skill-icon"></i>
                    <span>CSS3</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-sass skill-icon"></i>
                    <span>Sass</span>
                </div>
                <div class="skill-item">
                    <i class="fas fa-database skill-icon"></i>
                    <span>MongoDB</span>
                </div>
                <div class="skill-item">
                    <i class="fas fa-database skill-icon"></i>
                    <span>PostgreSQL</span>
                </div>
                <div class="skill-item">
                    <i class="fab fa-git-alt skill-icon"></i>
                    <span>Git</span>
                </div>
                <div class="skill-item">
                    <i class="fas fa-mobile-alt skill-icon"></i>
                    <span>Responsive Design</span>
                </div>
                <div class="skill-item">
                    <i class="fas fa-bolt skill-icon"></i>
                    <span>Performance</span>
                </div>
                <div class="skill-item">
                    <i class="fas fa-paint-brush skill-icon"></i>
                    <span>UI/UX Design</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="animate delay-2">
        <div class="container">
            <div class="section-title">
                <h2>Mes Projets Récents</h2>
            </div>
            
            <div class="projects-grid">
                <div class="project-card">
                    <img src="https://i.imgur.com/project1.jpg" alt="Projet 1" class="project-image">
                    <div class="project-info">
                        <h3 class="project-title">Plateforme E-Learning</h3>
                        <p class="project-description">
                            Solution complète d'apprentissage en ligne avec système de cours, quiz et certifications.
                        </p>
                        <div class="project-tags">
                            <span class="project-tag">React</span>
                            <span class="project-tag">Node.js</span>
                            <span class="project-tag">MongoDB</span>
                        </div>
                        <a href="#" class="btn btn-primary">Voir le projet</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <img src="https://i.imgur.com/project2.jpg" alt="Projet 2" class="project-image">
                    <div class="project-info">
                        <h3 class="project-title">Application de Gestion</h3>
                        <p class="project-description">
                            Outil de gestion d'entreprise avec tableau de bord analytique et gestion des tâches.
                        </p>
                        <div class="project-tags">
                            <span class="project-tag">Vue.js</span>
                            <span class="project-tag">Firebase</span>
                            <span class="project-tag">Chart.js</span>
                        </div>
                        <a href="#" class="btn btn-primary">Voir le projet</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <img src="https://i.imgur.com/project3.jpg" alt="Projet 3" class="project-image">
                    <div class="project-info">
                        <h3 class="project-title">Portfolio Artistique</h3>
                        <p class="project-description">
                            Site vitrine moderne pour artiste avec galerie interactive et système de contact.
                        </p>
                        <div class="project-tags">
                            <span class="project-tag">GSAP</span>
                            <span class="project-tag">Three.js</span>
                            <span class="project-tag">CSS3</span>
                        </div>
                        <a href="#" class="btn btn-primary">Voir le projet</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="animate delay-3">
        <div class="container">
            <div class="section-title">
                <h2>Contactez-Moi</h2>
            </div>
            
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Travaillons ensemble</h3>
                    <p>
                        Vous avez un projet en tête ? Discutons-en ! Je suis disponible pour des collaborations 
                        freelance ou des opportunités à temps plein.
                    </p>
                    
                    <div class="contact-method">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <h4>Email</h4>
                            <a href="mailto:safwanlamkimel@gmail.com">safwanlamkimel@gmail.com</a>
                        </div>
                    </div>
                    
                    <div class="contact-method">
                        <div class="contact-icon">
                            <i class="fab fa-discord"></i>
                        </div>
                        <div>
                            <h4>Discord</h4>
                            <span>supersayan123</span>
                        </div>
                    </div>
                    
                    <div class="contact-method">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div>
                            <h4>Localisation</h4>
                            <span>morocco</span>
                        </div>
                    </div>
                </div>
                
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Nom Complet</label>
                        <input type="text" id="name" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="subject">Sujet</label>
                        <input type="text" id="subject" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" required></textarea>
                    </div>
                    
                    <button type="submit" class="btn btn-primary">Envoyer le message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <a href="#" class="footer-logo">Safouane.</a>
                
                <div class="footer-links">
                    <a href="#about" class="footer-link">À Propos</a>
                    <a href="#skills" class="footer-link">Compétences</a>
                    <a href="#projects" class="footer-link">Projets</a>
                    <a href="#contact" class="footer-link">Contact</a>
                </div>
                
                <div class="social-links">
                    <a href="https://github.com/safouane" class="social-link github" target="_blank">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="https://linkedin.com/in/safouane-lamkimel" class="social-link linkedin" target="_blank">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="https://twitter.com/safouane" class="social-link twitter" target="_blank">
                        <i class="fab fa-twitter"></i>
                    </a>
                </div>
                
                <p class="copyright">
                    &copy; 2023 Safouane Lamkimel. Tous droits réservés.
                </p>
            </div>
        </div>
    </footer>

    <!-- Dark Mode Toggle -->
    <button class="theme-toggle" aria-label="Toggle dark mode">
        <i class="fas fa-moon"></i>
    </button>

    <!-- JavaScript -->
    <script>
        // Dark Mode Toggle
        const themeToggle = document.querySelector('.theme-toggle');
        const body = document.body;
        const icon = themeToggle.querySelector('i');
        
        // Check for saved user preference or prefer color scheme
        const savedTheme = localStorage.getItem('theme');
        const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
        
        if (savedTheme === 'dark' || (!savedTheme && prefersDark)) {
            enableDarkMode();
        }
        
        themeToggle.addEventListener('click', () => {
            body.classList.contains('dark-mode') ? disableDarkMode() : enableDarkMode();
        });
        
        function enableDarkMode() {
            body.classList.add('dark-mode');
            icon.classList.replace('fa-moon', 'fa-sun');
            localStorage.setItem('theme', 'dark');
        }
        
        function disableDarkMode() {
            body.classList.remove('dark-mode');
            icon.classList.replace('fa-sun', 'fa-moon');
            localStorage.setItem('theme', 'light');
        }
        
        // Navbar scroll effect
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });
        
        // Mobile menu toggle
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const navLinks = document.querySelector('.nav-links');
        
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
        });
        
        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                if (window.innerWidth <= 768) {
                    navLinks.style.display = 'none';
                }
            });
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Animation on scroll
        const animateElements = document.querySelectorAll('.animate');
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = 1;
                    entry.target.style.transform = 'translateY(0)';
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.1 });
        
        animateElements.forEach(el => {
            el.style.opacity = 0;
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease-out, transform 0.6s ease-out';
            observer.observe(el);
        });
        
        // Form submission
        const contactForm = document.querySelector('.contact-form');
        if (contactForm) {
            contactForm.addEventListener('submit', (e) => {
                e.preventDefault();
                alert('Message envoyé avec succès ! Je vous répondrai dès que possible.');
                contactForm.reset();
            });
        }
    </script>
</body>
</html>
