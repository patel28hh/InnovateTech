<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InnovateTech Solutions - Digital Excellence</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Variables for Easy Customization */
        :root {
            --primary-color: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary-color: #f8fafc;
            --accent-color: #10b981;
            --text-dark: #1e293b;
            --text-light: #64748b;
            --text-lighter: #94a3b8;
            --white: #ffffff;
            --gradient-primary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-accent: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
            --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
            --shadow-xl: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
        }

        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            scroll-behavior: smooth;
            font-size: 16px;
            overflow-x: hidden;
        }

        /* Loading Animation */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            opacity: 1;
            transition: opacity 0.5s ease;
        }

        .loading-overlay.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .loader {
            width: 50px;
            height: 50px;
            border: 4px solid var(--secondary-color);
            border-top: 4px solid var(--primary-color);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Header and Navigation */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            box-shadow: var(--shadow-md);
            z-index: 1000;
            padding: 0;
            transition: all 0.3s ease;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
            padding: 1rem 2rem;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text-dark);
            text-decoration: none;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: var(--gradient-primary);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2.5rem;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 500;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-links a:before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s ease;
        }

        .nav-links a:hover:before,
        .nav-links a.active:before {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .nav-cta {
            background: var(--primary-color);
            color: white !important;
            padding: 0.75rem 1.5rem !important;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: var(--shadow-sm);
        }

        .nav-cta:hover {
            background: var(--primary-dark);
            transform: translateY(-1px);
            box-shadow: var(--shadow-md);
            color: white !important;
        }

        .nav-cta:before {
            display: none;
        }

        /* Mobile Menu Toggle */
        .menu-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
            gap: 4px;
            padding: 0.5rem;
        }

        .menu-toggle span {
            width: 25px;
            height: 3px;
            background: var(--text-dark);
            transition: 0.3s;
            border-radius: 2px;
        }

        /* Main Content Container */
        main {
            margin-top: 80px;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Section Styling */
        section {
            padding: 6rem 0;
            position: relative;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-subtitle {
            color: var(--primary-color);
            font-weight: 600;
            font-size: 0.95rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-bottom: 1rem;
        }

        h1, h2, h3 {
            color: var(--text-dark);
            font-weight: 700;
            line-height: 1.2;
        }

        h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 1.5rem;
        }

        h2 {
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 1rem;
        }

        h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        p {
            color: var(--text-light);
            font-size: 1.1rem;
            line-height: 1.7;
            margin-bottom: 1.5rem;
        }

        /* Hero Section */
        #home {
            min-height: 100vh;
            display: flex;
            align-items: center;
            background: var(--gradient-primary);
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1557804506-669a67965ba0?ixlib=rb-4.0.3&auto=format&fit=crop&w=2074&q=80') center/cover;
            opacity: 0.1;
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero-content h1 {
            color: white;
            font-size: clamp(3rem, 6vw, 4.5rem);
            margin-bottom: 1.5rem;
            font-weight: 800;
            letter-spacing: -0.02em;
        }

        .hero-content .lead {
            font-size: 1.3rem;
            margin-bottom: 3rem;
            opacity: 0.95;
            font-weight: 400;
            line-height: 1.6;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: white;
            color: var(--primary-color);
            box-shadow: var(--shadow-lg);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-xl);
        }

        .btn-outline {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-outline:hover {
            background: white;
            color: var(--primary-color);
            transform: translateY(-2px);
        }

        /* Stats Section */
        .stats-section {
            background: var(--white);
            padding: 4rem 0;
            margin-top: -2rem;
            position: relative;
            z-index: 3;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .stat-item {
            text-align: center;
            padding: 1.5rem;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--primary-color);
            margin-bottom: 0.5rem;
            display: block;
        }

        .stat-label {
            color: var(--text-light);
            font-weight: 500;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 0.05em;
        }

        /* About Section */
        #about {
            background: var(--secondary-color);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .about-features {
            list-style: none;
            margin: 2rem 0;
        }

        .about-features li {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            margin-bottom: 1rem;
            color: var(--text-light);
        }

        .about-features i {
            color: var(--accent-color);
            font-size: 1.2rem;
            width: 20px;
        }

        .about-image {
            position: relative;
        }

        .about-image img {
            width: 100%;
            height: 400px;
            object-fit: cover;
            border-radius: 20px;
            box-shadow: var(--shadow-xl);
        }

        .about-badge {
            position: absolute;
            top: -20px;
            right: -20px;
            background: var(--accent-color);
            color: white;
            padding: 1rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: var(--shadow-lg);
        }

        .about-badge .badge-number {
            font-size: 1.5rem;
            font-weight: 700;
            display: block;
        }

        .about-badge .badge-text {
            font-size: 0.8rem;
            opacity: 0.9;
        }

        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .service-card {
            background: var(--white);
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: var(--shadow-md);
            text-align: left;
            transition: all 0.3s ease;
            border: 1px solid rgba(0,0,0,0.05);
            position: relative;
            overflow: hidden;
        }

        .service-card:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--gradient-primary);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-xl);
        }

        .service-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .service-icon {
            width: 60px;
            height: 60px;
            background: var(--gradient-primary);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            flex-shrink: 0;
        }

        .service-card h3 {
            color: var(--text-dark);
            font-size: 1.3rem;
        }

        .service-card p {
            color: var(--text-light);
            margin-bottom: 1.5rem;
        }

        .service-features {
            list-style: none;
            margin-bottom: 2rem;
        }

        .service-features li {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.5rem;
            color: var(--text-light);
            font-size: 0.95rem;
        }

        .service-features i {
            color: var(--accent-color);
            font-size: 0.8rem;
        }

        .service-link {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.95rem;
            transition: all 0.3s ease;
        }

        .service-link:hover {
            gap: 0.75rem;
        }

        /* Contact Section */
        #contact {
            background: var(--white);
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: start;
        }

        .contact-form {
            background: var(--white);
            padding: 3rem;
            border-radius: 20px;
            box-shadow: var(--shadow-lg);
            border: 1px solid rgba(0,0,0,0.05);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--text-dark);
            font-size: 0.95rem;
        }

        input, textarea, select {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            font-size: 1rem;
            transition: all 0.3s ease;
            font-family: inherit;
        }

        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
        }

        textarea {
            resize: vertical;
            min-height: 120px;
        }

        .submit-btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .submit-btn:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .contact-info {
            padding: 1rem 0;
        }

        .contact-info h3 {
            color: var(--text-dark);
            margin-bottom: 2rem;
            font-size: 1.5rem;
        }

        .info-item {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
            margin-bottom: 2rem;
            padding: 1.5rem;
            background: var(--secondary-color);
            border-radius: 15px;
            transition: all 0.3s ease;
        }

        .info-item:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .info-icon {
            width: 50px;
            height: 50px;
            background: var(--primary-color);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            flex-shrink: 0;
            font-size: 1.2rem;
        }

        .info-content h4 {
            color: var(--text-dark);
            font-weight: 600;
            margin-bottom: 0.5rem;
            font-size: 1rem;
        }

        .info-content p {
            color: var(--text-light);
            margin: 0;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        /* Footer */
        footer {
            background: var(--text-dark);
            color: white;
            padding: 3rem 0 2rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 2rem;
        }

        .footer-section h4 {
            color: white;
            font-weight: 600;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .footer-section p,
        .footer-section a {
            color: var(--text-lighter);
            text-decoration: none;
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .footer-section a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-link {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background: var(--primary-color);
            transform: translateY(-2px);
        }

        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.1);
            padding-top: 2rem;
            text-align: center;
            color: var(--text-lighter);
        }

        /* Responsive Design */
        @media (max-width: 968px) {
            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            /* Mobile Navigation */
            .nav-links {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background: rgba(255, 255, 255, 0.98);
                backdrop-filter: blur(20px);
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 2rem;
                transition: left 0.3s ease;
                box-shadow: var(--shadow-lg);
            }

            .nav-links.active {
                left: 0;
            }

            .menu-toggle {
                display: flex;
            }

            .menu-toggle.active span:nth-child(1) {
                transform: rotate(-45deg) translate(-5px, 6px);
            }

            .menu-toggle.active span:nth-child(2) {
                opacity: 0;
            }

            .menu-toggle.active span:nth-child(3) {
                transform: rotate(45deg) translate(-5px, -6px);
            }

            /* Mobile Content Adjustments */
            section {
                padding: 4rem 0;
            }

            .container {
                padding: 0 1rem;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn {
                width: 100%;
                max-width: 280px;
                justify-content: center;
            }

            .contact-form {
                padding: 2rem;
            }

            .stats-grid {
                grid-template-columns: 1fr;
                gap: 1rem;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .service-card {
                padding: 2rem;
            }
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .slide-in-left {
            opacity: 0;
            transform: translateX(-50px);
            transition: all 0.8s ease;
        }

        .slide-in-left.visible {
            opacity: 1;
            transform: translateX(0);
        }

        .slide-in-right {
            opacity: 0;
            transform: translateX(50px);
            transition: all 0.8s ease;
        }

        .slide-in-right.visible {
            opacity: 1;
            transform: translateX(0);
        }

        /* Counter Animation */
        @keyframes countUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .stat-number.animate {
            animation: countUp 0.8s ease;
        }

        /* Scroll Progress Bar */
        .progress-bar {
            position: fixed;
            top: 80px;
            left: 0;
            width: 0%;
            height: 3px;
            background: var(--primary-color);
            z-index: 1001;
            transition: width 0.1s ease;
        }
    </style>
</head>
<body>
    <!-- Loading Overlay -->
    <div class="loading-overlay" id="loadingOverlay">
        <div class="loader"></div>
    </div>

    <!-- Scroll Progress Bar -->
    <div class="progress-bar" id="progressBar"></div>

    <!-- Header/Navigation -->
    <header id="header">
        <nav>
            <a href="#home" class="logo">
                <div class="logo-icon">
                    <i class="fas fa-rocket"></i>
                </div>
                InnovateTech
            </a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
                <li><a href="#contact" class="nav-cta">Get Started</a></li>
            </ul>
            <div class="menu-toggle" id="mobile-menu">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </nav>
    </header>

    <main>
        <!-- Hero Section -->
        <section id="home">
            <div class="hero-bg"></div>
            <div class="container">
                <div class="hero-content fade-in">
                    <h1>Digital Excellence for Modern Business</h1>
                    <p class="lead">We transform ideas into powerful digital solutions that drive growth, enhance user experience, and deliver exceptional results for businesses worldwide.</p>
                    <div class="hero-buttons">
                        <a href="#contact" class="btn btn-primary">
                            <i class="fas fa-rocket"></i>
                            Start Your Project
                        </a>
                        <a href="#about" class="btn btn-outline">
                            <i class="fas fa-play"></i>
                            Learn More
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="stats-section">
            <div class="container">
                <div class="stats-grid fade-in">
                    <div class="stat-item">
                        <span class="stat-number" data-count="500">0</span>
                        <div class="stat-label">Projects Completed</div>
                    </div>
                    <div class="stat-item">
                        <span class="stat-number" data-count="150">0</span>
                        <div class="stat-label">Happy Clients</div>
                    </div>
                    <div class="stat-item">
                        <span class="stat-number" data-count="10">0</span>
                        <div class="stat-label">Years Experience</div>
                    </div>
                    <div class="stat-item">
                        <span class="stat-number" data-count="25">0</span>
                        <div class="stat-label">Team Members</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about">
            <div class="container">
                <div class="section-header fade-in">
                    <div class="section-subtitle">About Us</div>
                    <h2>Building Tomorrow's Digital Solutions Today</h2>
                    <p>We combine innovative technology with creative design to deliver exceptional digital experiences that drive business growth.</p>
                </div>
                
                <div class="about-content">
                    <div class="about-text slide-in-left">
                        <h3>Our Mission</h3>
                        <p>At InnovateTech Solutions, we believe that exceptional digital experiences are the cornerstone of modern business success. Our team of skilled professionals combines cutting-edge technology with creative innovation to deliver solutions that not only meet but exceed expectations.</p>
                        
                        <p>We specialize in creating custom web applications, mobile solutions, and digital strategies that help businesses thrive in the digital age. Our approach is collaborative, transparent, and results-driven.</p>
                        
                        <ul class="about-features">
                            <li>
                                <i class="fas fa-check-circle"></i>
                                Award-winning design and development team
                            </li>
                            <li>
                                <i class="fas fa-check-circle"></i>
                                Proven track record with 500+ successful projects
                            </li>
                            <li>
                                <i class="fas fa-check-circle"></i>
                                24/7 support and maintenance services
                            </li>
                            <li>
                                <i class="fas fa-check-circle"></i>
                                Agile development methodology
                            </li>
                        </ul>
                    </div>
                    
                    <div class="about-image slide-in-right">
                        <img src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Our professional team working">
                        <div class="about-badge">
                            <span class="badge-number">10+</span>
                            <span class="badge-text">Years Experience</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section id="services">
            <div class="container">
                <div class="section-header fade-in">
                    <div class="section-subtitle">Our Services</div>
                    <h2>Comprehensive Digital Solutions</h2>
                    <p>From web development to digital marketing, we offer a full spectrum of services to help your business succeed online.</p>
                </div>
                
                <div class="services-grid">
                    <div class="service-card fade-in">
                        <div class="service-header">
                            <div class="service-icon">
                                <i class="fas fa-code"></i>
                            </div>
                            <h3>Web Development</h3>
                        </div>
                        <p>Custom websites and web applications built with cutting-edge technologies. We create responsive, fast, and secure digital solutions.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> Responsive Design</li>
                            <li><i class="fas fa-check"></i> Modern Frameworks</li>
                            <li><i class="fas fa-check"></i> SEO Optimized</li>
                            <li><i class="fas fa-check"></i> Performance Focused</li>
                        </ul>
                        <a href="#contact" class="service-link">
                            Learn More <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                    
                    <div class="service-card fade-in">
                        <div class="service-header">
                            <div class="service-icon">
                                <i class="fas fa-mobile-alt"></i>
                            </div>
                            <h3>Mobile Apps</h3>
                        </div>
                        <p>Native and cross-platform mobile applications that provide exceptional user experiences on iOS and Android devices.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> iOS & Android</li>
                            <li><i class="fas fa-check"></i> Cross-Platform</li>
                            <li><i class="fas fa-check"></i> Native Performance</li>
                            <li><i class="fas fa-check"></i> App Store Ready</li>
                        </ul>
                        <a href="#contact" class="service-link">
                            Learn More <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                    
                    <div class="service-card fade-in">
                        <div class="service-header">
                            <div class="service-icon">
                                <i class="fas fa-chart-line"></i>
                            </div>
                            <h3>Digital Marketing</h3>
                        </div>
                        <p>Strategic digital marketing campaigns that drive traffic, increase conversions, and grow your online presence effectively.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> SEO & SEM</li>
                            <li><i class="fas fa-check"></i> Social Media</li>
                            <li><i class="fas fa-check"></i> Content Marketing</li>
                            <li><i class="fas fa-check"></i> Analytics & Reports</li>
                        </ul>
                        <a href="#contact" class="service-link">
                            Learn More <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                    
                    <div class="service-card fade-in">
                        <div class="service-header">
                            <div class="service-icon">
                                <i class="fas fa-palette"></i>
                            </div>
                            <h3>UI/UX Design</h3>
                        </div>
                        <p>User-centered design solutions that create intuitive, engaging, and conversion-focused digital experiences for your users.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> User Research</li>
                            <li><i class="fas fa-check"></i> Wireframing</li>
                            <li><i class="fas fa-check"></i> Prototyping</li>
                            <li><i class="fas fa-check"></i> Design Systems</li>
                        </ul>
                        <a href="#contact" class="service-link">
                            Learn More <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                    
                    <div class="service-card fade-in">
                        <div class="service-header">
                            <div class="service-icon">
                                <i class="fas fa-cloud"></i>
                            </div>
                            <h3>Cloud Solutions</h3>
                        </div>
                        <p>Scalable cloud infrastructure and services that ensure your applications perform reliably and cost-effectively at any scale.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> AWS & Azure</li>
                            <li><i class="fas fa-check"></i> DevOps</li>
                            <li><i class="fas fa-check"></i> Auto Scaling</li>
                            <li><i class="fas fa-check"></i> 24/7 Monitoring</li>
                        </ul>
                        <a href="#contact" class="service-link">
                            Learn More <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                    
                    <div class="service-card fade-in">
                        <div class="service-header">
                            <div class="service-icon">
                                <i class="fas fa-headset"></i>
                            </div>
                            <h3>Consulting</h3>
                        </div>
                        <p>Expert technology consulting to help you make informed decisions, optimize processes, and achieve your digital transformation goals.</p>
                        <ul class="service-features">
                            <li><i class="fas fa-check"></i> Strategy Planning</li>
                            <li><i class="fas fa-check"></i> Technology Audit</li>
                            <li><i class="fas fa-check"></i> Process Optimization</li>
                            <li><i class="fas fa-check"></i> Training & Support</li>
                        </ul>
                        <a href="#contact" class="service-link">
                            Learn More <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact">
            <div class="container">
                <div class="section-header fade-in">
                    <div class="section-subtitle">Contact Us</div>
                    <h2>Ready to Start Your Project?</h2>
                    <p>Let's discuss how we can help transform your ideas into exceptional digital solutions.</p>
                </div>
                
                <div class="contact-content">
                    <div class="contact-form slide-in-left">
                        <form id="contactForm">
                            <div class="form-group">
                                <label for="name">Full Name *</label>
                                <input type="text" id="name" name="name" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Email Address *</label>
                                <input type="email" id="email" name="email" required>
                            </div>
                            <div class="form-group">
                                <label for="company">Company</label>
                                <input type="text" id="company" name="company">
                            </div>
                            <div class="form-group">
                                <label for="service">Service Interested In</label>
                                <select id="service" name="service">
                                    <option value="">Select a service</option>
                                    <option value="web-development">Web Development</option>
                                    <option value="mobile-apps">Mobile Apps</option>
                                    <option value="digital-marketing">Digital Marketing</option>
                                    <option value="ui-ux-design">UI/UX Design</option>
                                    <option value="cloud-solutions">Cloud Solutions</option>
                                    <option value="consulting">Consulting</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="budget">Project Budget</label>
                                <select id="budget" name="budget">
                                    <option value="">Select budget range</option>
                                    <option value="5k-10k">$5,000 - $10,000</option>
                                    <option value="10k-25k">$10,000 - $25,000</option>
                                    <option value="25k-50k">$25,000 - $50,000</option>
                                    <option value="50k+">$50,000+</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="message">Project Details *</label>
                                <textarea id="message" name="message" placeholder="Tell us about your project, goals, and requirements..." required></textarea>
                            </div>
                            <button type="submit" class="submit-btn">
                                <i class="fas fa-paper-plane"></i>
                                Send Message
                            </button>
                        </form>
                    </div>
                    
                    <div class="contact-info slide-in-right">
                        <h3>Get In Touch</h3>
                        <div class="info-item">
                            <div class="info-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <div class="info-content">
                                <h4>Our Office</h4>
                                <p>123 Innovation Drive<br>Tech District, Silicon Valley<br>CA 94025, United States</p>
                            </div>
                        </div>
                        
                        <div class="info-item">
                            <div class="info-icon">
                                <i class="fas fa-phone"></i>
                            </div>
                            <div class="info-content">
                                <h4>Phone</h4>
                                <p>+1 (555) 123-4567<br>+1 (555) 987-6543</p>
                            </div>
                        </div>
                        
                        <div class="info-item">
                            <div class="info-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <div class="info-content">
                                <h4>Email</h4>
                                <p>hello@innovatetech.com<br>support@innovatetech.com</p>
                            </div>
                        </div>
                        
                        <div class="info-item">
                            <div class="info-icon">
                                <i class="fas fa-clock"></i>
                            </div>
                            <div class="info-content">
                                <h4>Business Hours</h4>
                                <p>Monday - Friday: 9:00 AM - 6:00 PM<br>Saturday: 10:00 AM - 4:00 PM<br>Sunday: Closed</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h4>InnovateTech Solutions</h4>
                    <p>We transform ideas into powerful digital solutions that drive growth and deliver exceptional results for businesses worldwide.</p>
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                    </div>
                </div>
                
                <div class="footer-section">
                    <h4>Services</h4>
                    <p><a href="#services">Web Development</a></p>
                    <p><a href="#services">Mobile Apps</a></p>
                    <p><a href="#services">Digital Marketing</a></p>
                    <p><a href="#services">UI/UX Design</a></p>
                    <p><a href="#services">Cloud Solutions</a></p>
                </div>
                
                <div class="footer-section">
                    <h4>Company</h4>
                    <p><a href="#about">About Us</a></p>
                    <p><a href="#contact">Contact</a></p>
                    <p><a href="#">Careers</a></p>
                    <p><a href="#">Portfolio</a></p>
                    <p><a href="#">Blog</a></p>
                </div>
                
                <div class="footer-section">
                    <h4>Contact Info</h4>
                    <p>123 Innovation Drive<br>Silicon Valley, CA 94025</p>
                    <p>Phone: +1 (555) 123-4567</p>
                    <p>Email: hello@innovatetech.com</p>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2024 InnovateTech Solutions. All rights reserved. | Privacy Policy | Terms of Service</p>
            </div>
        </div>
    </footer>

    <script>
        // Loading Animation
        window.addEventListener('load', function() {
            setTimeout(() => {
                document.getElementById('loadingOverlay').classList.add('hidden');
            }, 1000);
        });

        // Scroll Progress Bar
        window.addEventListener('scroll', function() {
            const scrollTop = window.pageYOffset;
            const docHeight = document.documentElement.scrollHeight - window.innerHeight;
            const scrollPercent = (scrollTop / docHeight) * 100;
            document.getElementById('progressBar').style.width = scrollPercent + '%';
        });

        // Mobile Menu Toggle
        const mobileMenu = document.getElementById('mobile-menu');
        const navLinks = document.querySelector('.nav-links');

        mobileMenu.addEventListener('click', () => {
            mobileMenu.classList.toggle('active');
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.remove('active');
                navLinks.classList.remove('active');
            });
        });

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    const headerHeight = 80;
                    const targetPosition = target.offsetTop - headerHeight;
                    
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Intersection Observer for Animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    
                    // Animate counters when stats section is visible
                    if (entry.target.querySelector('.stat-number')) {
                        animateCounters();
                    }
                }
            });
        }, observerOptions);

        // Observe all animated elements
        document.querySelectorAll('.fade-in, .slide-in-left, .slide-in-right').forEach(el => {
            observer.observe(el);
        });

        // Counter Animation
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            counters.forEach(counter => {
                if (counter.classList.contains('counted')) return;
                
                const target = parseInt(counter.getAttribute('data-count'));
                const duration = 2000;
                const step = target / (duration / 16);
                let current = 0;
                
                const timer = setInterval(() => {
                    current += step;
                    if (current >= target) {
                        current = target;
                        clearInterval(timer);
                    }
                    counter.textContent = Math.floor(current) + (target >= 1000 ? '+' : '');
                }, 16);
                
                counter.classList.add('counted', 'animate');
            });
        }

        // Active Navigation Highlighting
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('.nav-links a:not(.nav-cta)');
            
            let current = '';
            const scrollPosition = window.pageYOffset + 100;
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                
                if (scrollPosition >= sectionTop && scrollPosition < sectionTop + sectionHeight) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('active');
                }
            });
        });

        // Header Background on Scroll
        const header = document.getElementById('header');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 4px 20px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = '0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1)';
            }
        });

        // Enhanced Contact Form Submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const formData = new FormData(this);
            const name = formData.get('name').trim();
            const email = formData.get('email').trim();
            const message = formData.get('message').trim();
            
            // Enhanced Validation
            if (!name || name.length < 2) {
                showNotification('Please enter your full name.', 'error');
                return;
            }
            
            if (!email || !isValidEmail(email)) {
                showNotification('Please enter a valid email address.', 'error');
                return;
            }
            
            if (!message || message.length < 10) {
                showNotification('Please provide more details about your project (minimum 10 characters).', 'error');
                return;
            }
            
            // Submit Animation
            const submitBtn = this.querySelector('.submit-btn');
            const originalContent = submitBtn.innerHTML;
            
            submitBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Sending...';
            submitBtn.disabled = true;
            
            // Simulate API call
            setTimeout(() => {
                showNotification('Thank you! Your message has been sent successfully. We\'ll get back to you within 24 hours.', 'success');
                this.reset();
                submitBtn.innerHTML = originalContent;
                submitBtn.disabled = false;
            }, 2000);
        });

        // Email Validation
        function isValidEmail(email) {
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
        }

        // Notification System
        function showNotification(message, type = 'info') {
            const notification = document.createElement('div');
            notification.className = `notification notification-${type}`;
            notification.style.cssText = `
                position: fixed;
                top: 100px;
                right: 20px;
                background: ${type === 'success' ? '#10b981' : type === 'error' ? '#ef4444' : '#3b82f6'};
                color: white;
                padding: 1rem 1.5rem;
                border-radius: 12px;
                box-shadow: 0 10px 25px rgba(0,0,0,0.2);
                z-index: 10000;
                transform: translateX(400px);
                transition: transform 0.3s ease;
                max-width: 350px;
                font-weight: 500;
            `;
            
            notification.innerHTML = `
                <div style="display: flex; align-items: center; gap: 0.5rem;">
                    <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'error' ? 'exclamation-circle' : 'info-circle'}"></i>
                    ${message}
                </div>
            `;
            
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.style.transform = 'translateX(0)';
            }, 100);
            
            setTimeout(() => {
                notification.style.transform = 'translateX(400px)';
                setTimeout(() => {
                    notification.remove();
                }, 300);
            }, 5000);
        }

        // Parallax Effect for Hero Section
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('#home');
            const rate = scrolled * -0.5;
            
            if (hero) {
                hero.style.transform = `translateY(${rate}px)`;
            }
        });

        // Service Cards Hover Effect Enhancement
        document.querySelectorAll('.service-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Initialize tooltips and additional interactions
        document.addEventListener('DOMContentLoaded', function() {
            // Add any additional initialization code here
            console.log('InnovateTech Solutions website loaded successfully!');
        });
    </script>
</body>
</html>
