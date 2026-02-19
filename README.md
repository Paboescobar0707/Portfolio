<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mon Portfolio - Pentester</title>
    <link rel="icon" href="Nouhoum logo.png" type="image/png">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #05a6eb;
            --secondary-color: #ba0d1c;
            --accent-color: #f59e0b;
            --text-color: #334155;
            --light-bg: #f8fafc;
            --white: #ffffff;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            scroll-behavior: smooth;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: var(--white);
            box-shadow: var(--shadow);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }

        .nav-logo a {
            font-size: 1.5rem;
            font-weight: bold;
            background: linear-gradient(90deg, #05a6eb, #ba0d1c, #f59e0b, #10b981, #7c3aed, #ff1493, #05a6eb);
            background-size: 200% 100%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: lightshow 4s ease infinite;
            text-decoration: none;
        }

        .nav-menu {
            display: flex;
            gap: 2rem;
        }

        .nav-link {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-link:hover {
            color: var(--primary-color);
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: var(--text-color);
            margin: 3px 0;
            transition: 0.3s;
        }

        .hamburger.active span:nth-child(1) {
            transform: rotate(-45deg) translate(-5px, 6px);
        }

        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }

        .hamburger.active span:nth-child(3) {
            transform: rotate(45deg) translate(-5px, -6px);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 100px 20px 50px;
            background: linear-gradient(135deg, var(--light-bg) 0%, var(--white) 100%);
        }

        .hero-content {
            flex: 1;
            max-width: 600px;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--secondary-color);
        }

        .highlight {
            background: linear-gradient(90deg, #05a6eb, #ba0d1c, #f59e0b, #10b981, #7c3aed, #ff1493, #05a6eb);
            background-size: 200% 100%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: lightshow 4s ease infinite;
            font-weight: 700;
        }

        @keyframes lightshow {
            0% {
                background-position: 0% center;
            }
            50% {
                background-position: 100% center;
            }
            100% {
                background-position: 0% center;
            }
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: var(--text-color);
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
        }

        .btn {
            padding: 12px 30px;
            text-decoration: none;
            border-radius: 5px;
            font-weight: 600;
            transition: all 0.3s;
            display: inline-block;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background: var(--primary-color);
            color: var(--white);
        }

        .btn-primary:hover {
            background: #1d4ed8;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: transparent;
            color: var(--primary-color);
            border: 2px solid var(--primary-color);
        }

        .btn-secondary:hover {
            background: var(--primary-color);
            color: var(--white);
        }

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .image-placeholder {
            width: 300px;
            height: 300px;
            background: var(--primary-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 5rem;
            overflow: hidden;
            cursor: pointer;
        }

        .image-placeholder img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s ease, filter 0.4s ease;
        }

        .image-placeholder:hover img {
            transform: scale(1.15) rotate(3deg);
            filter: brightness(1.1);
        }

        /* Sections communes */
        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--secondary-color);
        }

        /* À propos */
        .about {
            background: var(--white);
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .about-info {
            display: flex;
            justify-content: center;
            gap: 3rem;
            flex-wrap: wrap;
        }

        .info-item {
            text-align: center;
        }

        /* Compétences */
        .skills {
            background: var(--light-bg);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-item {
            background: var(--white);
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: transform 0.3s;
            opacity: 0;
            transform: translateY(20px);
        }

        .skill-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .skill-item:hover {
            transform: translateY(-5px);
        }

        .skill-item i {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }

        .skill-item h3 {
            margin-bottom: 1rem;
            color: var(--secondary-color);
        }

        /* Projets */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s;
            opacity: 0;
            transform: translateY(20px);
        }

        .project-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        .project-image img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            margin-bottom: 1rem;
            color: var(--secondary-color);
        }

        .project-tech {
            display: flex;
            gap: 0.5rem;
            margin: 1rem 0;
            flex-wrap: wrap;
        }

        .project-tech span {
            background: var(--light-bg);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            color: var(--primary-color);
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .btn-link {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s;
        }

        .btn-link:hover {
            color: #1d4ed8;
        }

        /* Contact */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: start;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .contact-item i {
            font-size: 1.5rem;
            color: var(--primary-color);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .contact-form input,
        .contact-form textarea {
            padding: 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            font-family: inherit;
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        /* Footer */
        .footer {
            background: var(--secondary-color);
            color: var(--white);
            text-align: center;
            padding: 2rem 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .social-links a {
            color: var(--white);
            font-size: 1.5rem;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: var(--accent-color);
        }

        /* Admin Panel */
        .admin-panel {
            background: var(--light-bg);
            min-height: 100vh;
            padding-top: 70px;
        }

        .admin-header {
            background: var(--secondary-color);
            color: var(--white);
            padding: 1rem 0;
            margin-bottom: 2rem;
        }

        .admin-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: var(--white);
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: var(--shadow);
            text-align: center;
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary-color);
        }

        .emails-table {
            background: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        th {
            background: var(--light-bg);
            font-weight: 600;
        }

        .email-non-lu {
            font-weight: bold;
            color: var(--primary-color);
        }

        .admin-actions {
            display: flex;
            gap: 0.5rem;
        }

        .btn-small {
            padding: 5px 10px;
            font-size: 0.8rem;
        }

        .btn-success {
            background: #10b981;
            color: white;
        }

        .btn-danger {
            background: #ef4444;
            color: white;
        }

        .login-container {
            max-width: 400px;
            margin: 100px auto;
            padding: 2rem;
            background: var(--white);
            border-radius: 8px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--text-color);
        }

        .form-group input {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }

        .error-message {
            color: #ef4444;
            text-align: center;
            margin-top: 1rem;
        }

        .success-message {
            color: #10b981;
            text-align: center;
            margin-top: 1rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hamburger {
                display: flex;
            }

            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: var(--white);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
                padding: 2rem 0;
            }

            .nav-menu.active {
                left: 0;
            }

            .nav-link {
                padding: 1rem;
                display: block;
            }

            .hero {
                flex-direction: column;
                text-align: center;
                padding: 120px 20px 50px;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-buttons {
                justify-content: center;
                flex-wrap: wrap;
            }

            .contact-content {
                grid-template-columns: 1fr;
            }

            .about-info {
                flex-direction: column;
                gap: 1rem;
            }
           
            .image-placeholder {
                width: 200px;
                height: 200px;
                font-size: 3rem;
                margin-top: 2rem;
            }

            .admin-stats {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <div class="nav-logo">
                <a href="#accueil">Mon Portfolio</a>
            </div>
            <div class="nav-menu">
                <a href="#accueil" class="nav-link">Accueil</a>
                <a href="#apropos" class="nav-link">À propos</a>
                <a href="#competences" class="nav-link">Compétences</a>
                <a href="#projets" class="nav-link">Projets</a>
                <a href="#contact" class="nav-link">Contact</a>
            </div>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Section Accueil -->
    <section id="accueil" class="hero">
        <div class="hero-content">
            <h1>Bonjour, je suis <span class="highlight">SOUMAHORO TIA NOUHOUM</span></h1>
            <p>Technicien en Cybersécurité Option Pentest</p>
            <div class="hero-buttons">
                <a href="#projets" class="btn btn-primary">Voir mes projets</a>
                <a href="#contact" class="btn btn-secondary">Me contacter</a>
            </div>
        </div>
        <div class="hero-image">
            <div class="image-placeholder">
                <img src="Nouhoum logo.png" alt="Nouhoum Logo">
            </div>
        </div>
    </section>

    <!-- Section À propos -->
    <section id="apropos" class="about">
        <div class="container">
            <h2 class="section-title">À propos de moi</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>
                        Passionné par la protection des données et
                         l'intégrité des systèmes, j'évolue dans
                          le domaine de la cybersécurité avec une approche
                           axée sur la résilience. Mon objectif est de transformer 
                           les vulnérabilités en forces à travers une veille constante et une analyse rigoureuse. De la sécurisation réseau à
                         la sensibilisation des utilisateurs, 
                         je m'efforce de bâtir des environnements 
                         numériques où la confiance est la priorité.
                    </p>
                    <div class="about-info">
                        <div class="info-item">
                            <strong>TryHackMe/HackTheBox:</strong> nouhoumsoumahoro
                        </div>
                        <div class="info-item">
                            <strong>Soft Skills:</strong> La cybersécurité, c'est aussi savoir expliquer un risque technique à un non-technicien. Mentionne ta capacité de communication si c'est le cas.
                        </div>
                        <div class="info-item">
                            <strong>Certifications:</strong> CompTIA Security+, CEH, OSCP, CCNA
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section Compétences -->
    <section id="competences" class="skills">
        <div class="container">
            <h2 class="section-title">Mes Compétences</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-html5"></i>
                    <h3>HTML/CSS</h3>
                    <p>Maîtrise des standards web modernes</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js"></i>
                    <h3>JavaScript</h3>
                    <p>Développement frontend et backend</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-react"></i>
                    <h3>React</h3>
                    <p>Applications web interactives</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-node-js"></i>
                    <h3>Node.js</h3>
                    <p>Développement backend</p>
                </div>
                <div class="skill-item">
                    <i class="fas fa-shield-alt"></i>
                    <h3>Cybersécurité</h3>
                    <p>Tests de pénétration et sécurité applicative</p>
                </div>
                <div class="skill-item">
                    <i class="fas fa-network-wired"></i>
                    <h3>Sécurité Réseau</h3>
                    <p>Audit et hardening d'infrastructure</p>
                </div>
                <div class="skill-item">
                    <i class="fas fa-lock"></i>
                    <h3>Cryptographie</h3>
                    <p>Chiffrement et gestion des clés</p>
                </div>
                <div class="skill-item">
                    <i class="fas fa-bug"></i>
                    <h3>Vulnerability Assessment</h3>
                    <p>Identification et analyse des vulnérabilités</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Section Projets -->
    <section id="projets" class="projects">
        <div class="container">
            <h2 class="section-title">Mes Projets</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=400&h=250&fit=crop" alt="Pentest Application Web">
                    </div>
                    <div class="project-content">
                        <h3>Pentest Application Web - OWASP Top 10</h3>
                        <p>Test de pénétration complet d'une application web. Identification des vulnérabilités critiques incluant injection SQL, XSS, CSRF et gestion de session.</p>
                        <div class="project-tech">
                            <span>Burp Suite</span>
                            <span>OWASP ZAP</span>
                            <span>Metasploit</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn-link">Voir le rapport</a>
                            <a href="#" class="btn-link">POC Video</a>
                        </div>
                    </div>
                </div>
               
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1550355291-bbee04a92027?w=400&h=250&fit=crop" alt="Red Team Assessment">
                    </div>
                    <div class="project-content">
                        <h3>Red Team Assessment - Infrastructure</h3>
                        <p>Simulation d'attaque multi-vecteurs sur infrastructure complète. Exploitation de vulnérabilités réseau, escalade de privilèges et exfiltration de données.</p>
                        <div class="project-tech">
                            <span>Nmap</span>
                            <span>Metasploit</span>
                            <span>Privilege Escalation</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn-link">Voir le rapport</a>
                            <a href="#" class="btn-link">Code source</a>
                        </div>
                    </div>
                </div>
               
                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=400&h=250&fit=crop" alt="Analyse Malwares">
                    </div>
                    <div class="project-content">
                        <h3>Analyse Dynamique & Statique de Malwares</h3>
                        <p>Analyse complète de malwares en environnement sandboxé. Reverse engineering, extraction d'IOCs et rédaction de rapports de menaces détaillés.</p>
                        <div class="project-tech">
                            <span>Cuckoo Sandbox</span>
                            <span>IDA Pro</span>
                            <span>Wireshark</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn-link">Voir le rapport</a>
                            <a href="#" class="btn-link">Indicateurs</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=400&h=250&fit=crop" alt="Audit API">
                    </div>
                    <div class="project-content">
                        <h3>Audit Sécurité API REST</h3>
                        <p>Audit complet d'une API REST. Vérification de l'authentification, autorisation, rate limiting, transmission des données sensibles et conformité aux standards.</p>
                        <div class="project-tech">
                            <span>Postman</span>
                            <span>JWT Security</span>
                            <span>OWASP API</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn-link">Voir le rapport</a>
                            <a href="#" class="btn-link">Tests Automatisés</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1504384308090-c894fdcc538d?w=400&h=250&fit=crop" alt="Forensique Numérique">
                    </div>
                    <div class="project-content">
                        <h3>Forensique Numérique - Incident Response</h3>
                        <p>Investigation post-incident complète. Collecte de preuves numériques, analyse des artefacts système, timeline reconstruction et rapport judiciaire.</p>
                        <div class="project-tech">
                            <span>Volatility</span>
                            <span>FTK Imager</span>
                            <span>EnCase</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn-link">Voir le rapport</a>
                            <a href="#" class="btn-link">Timeline</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=400&h=250&fit=crop" alt="Secure Code Review">
                    </div>
                    <div class="project-content">
                        <h3>Secure Code Review & SAST</h3>
                        <p>Revue de code de sécurité approfondie. Détection des vulnérabilités de codage (injection, buffer overflow, hardcoded secrets), recommandations de remédiation.</p>
                        <div class="project-tech">
                            <span>SonarQube</span>
                            <span>Checkmarx</span>
                            <span>SEMGREP</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn-link">Voir le rapport</a>
                            <a href="#" class="btn-link">Dashboard</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section Contact -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Contactez-moi</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div>
                            <h3>Email</h3>
                            <p>Nouhoumsoumahoro9@gmail.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <div>
                            <h3>Téléphone</h3>
                            <p>+225 0747774066</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <div>
                            <h3>Localisation</h3>
                            <p>Korhogo, Côte d'Ivoire</p>
                        </div>
                    </div>
                </div>
                <form class="contact-form" id="contactForm">
                    <input type="text" name="nom" placeholder="Votre nom" required>
                    <input type="email" name="email" placeholder="Votre email" required>
                    <input type="text" name="sujet" placeholder="Sujet du message" required>
                    <textarea name="message" placeholder="Votre message" rows="5" required></textarea>
                    <button type="submit" class="btn btn-primary">Envoyer le message</button>
                    <div id="formMessage"></div>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="social-links">
                <a href="https://www.linkedin.com/in/zied-jemal/" title="LinkedIn" aria-label="LinkedIn" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin"></i></a>
                <a href="https://github.com/Paboescobar0707" title="GitHub" aria-label="GitHub" target="_blank" rel="noopener noreferrer"><i class="fab fa-github"></i></a>
                <a href="https://x.com/?lang=fr" title="Twitter" aria-label="Twitter" target="_blank" rel="noopener noreferrer"><i class="fab fa-twitter"></i></a>
            </div>
            <p>&copy; 2025 Nouhoum Soumahoro. Tous droits réservés.</p>
        </div>
    </footer>

    <script>
        // Navigation mobile
        const hamburger = document.querySelector('.hamburger');
        const navMenu = document.querySelector('.nav-menu');

        hamburger.addEventListener('click', () => {
            hamburger.classList.toggle('active');
            navMenu.classList.toggle('active');
        });

        // Fermer le menu en cliquant sur un lien
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                hamburger.classList.remove('active');
                navMenu.classList.remove('active');
            });
        });

        // Animation au scroll
        function checkVisibility() {
            const elements = document.querySelectorAll('.skill-item, .project-card');
           
            elements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
               
                if (elementTop < window.innerHeight - elementVisible) {
                    element.classList.add('visible');
                }
            });
        }

        // Observer les éléments à animer
        window.addEventListener('scroll', checkVisibility);
        window.addEventListener('load', checkVisibility);

        // Smooth scroll pour les liens d'ancrage
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(255, 255, 255, 0.95)';
                navbar.style.backdropFilter = 'blur(10px)';
            } else {
                navbar.style.background = 'var(--white)';
                navbar.style.backdropFilter = 'none';
            }
        });

        // Gestion du formulaire de contact
        const contactForm = document.getElementById('contactForm');
        if (contactForm) {
            contactForm.addEventListener('submit', function(e) {
                e.preventDefault();
               
                const formData = new FormData(this);
                const messageDiv = document.getElementById('formMessage');
               
                // Afficher le message de succès
                messageDiv.style.color = 'green';
                messageDiv.textContent = 'Message envoyé avec succès!';
                messageDiv.className = 'success-message';
               
                // Réinitialiser le formulaire
                this.reset();

                // Réinitialiser le message après 3 secondes
                setTimeout(() => {
                    messageDiv.textContent = '';
                }, 3000);
            });
        }

        // Initialiser les animations au chargement
        window.addEventListener('load', function() {
            checkVisibility();
        });
    </script>
</body>
</html>
