<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Khaled Helmy - Software Engineer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #f75c7e;
            --secondary: #58a6ff;
            --accent: #1f6feb;
            --dark: #0d1117;
            --darker: #010409;
            --light: #30363d;
            --lighter: #484f58;
            --text: #c9d1d9;
            --text-secondary: #8b949e;
            --success: #3fb950;
            --warning: #d29922;
        }

        body {
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 50%, #0a0e27 100%);
            color: var(--text);
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Helvetica Neue', sans-serif;
            line-height: 1.6;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated background elements */
        body::before {
            content: '';
            position: fixed;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(247, 92, 126, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: moveBackground 20s linear infinite;
            pointer-events: none;
            z-index: -1;
        }

        @keyframes moveBackground {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        /* Floating blobs */
        body::after {
            content: '';
            position: fixed;
            top: 20%;
            right: -10%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(88, 166, 255, 0.05) 0%, transparent 70%);
            border-radius: 50%;
            filter: blur(40px);
            animation: float 8s ease-in-out infinite;
            pointer-events: none;
            z-index: -1;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(30px, -30px); }
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 60px 30px;
        }

        /* ===== HEADER / HERO ===== */
        header {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            margin-bottom: 80px;
            perspective: 1000px;
        }

        .hero-content {
            z-index: 1;
        }

        .hero-content h1 {
            font-size: 4.5rem;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 15px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 50%, #7ee8ff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: slideInLeft 0.8s ease-out;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .hero-subtitle {
            font-size: 1.3rem;
            color: var(--secondary);
            font-weight: 500;
            margin-bottom: 10px;
            animation: slideInLeft 0.8s ease-out 0.1s both;
        }

        .hero-title {
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 25px;
            line-height: 1.8;
            animation: slideInLeft 0.8s ease-out 0.2s both;
        }

        .hero-description {
            font-size: 0.95rem;
            color: var(--text-secondary);
            margin-bottom: 35px;
            line-height: 1.8;
            animation: slideInLeft 0.8s ease-out 0.3s both;
        }

        .cta-buttons {
            display: flex;
            gap: 15px;
            margin-bottom: 40px;
            animation: slideInLeft 0.8s ease-out 0.4s both;
            flex-wrap: wrap;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 10px;
            border: none;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
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
            background: rgba(255, 255, 255, 0.1);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), #ff1744);
            color: white;
            box-shadow: 0 8px 24px rgba(247, 92, 126, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 32px rgba(247, 92, 126, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: var(--secondary);
            border: 2px solid var(--secondary);
        }

        .btn-secondary:hover {
            background: rgba(88, 166, 255, 0.1);
            transform: translateY(-3px);
        }

        .stats-mini {
            display: flex;
            gap: 30px;
            animation: slideInLeft 0.8s ease-out 0.5s both;
        }

        .stat-mini {
            display: flex;
            flex-direction: column;
        }

        .stat-mini-number {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
        }

        .stat-mini-label {
            font-size: 0.85rem;
            color: var(--text-secondary);
            margin-top: 5px;
        }

        /* ===== AVATAR SECTION ===== */
        .avatar-section {
            display: flex;
            justify-content: center;
            align-items: center;
            animation: slideInRight 0.8s ease-out;
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .avatar-container {
            position: relative;
            width: 320px;
            height: 320px;
        }

        .avatar-wrapper {
            position: relative;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 4px;
            animation: rotateGradient 8s linear infinite;
        }

        @keyframes rotateGradient {
            0% { filter: hue-rotate(0deg); }
            100% { filter: hue-rotate(360deg); }
        }

        .avatar-inner {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: var(--dark);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .avatar-svg {
            width: 280px;
            height: 280px;
            filter: drop-shadow(0 0 20px rgba(247, 92, 126, 0.2));
        }

        /* Floating particles around avatar */
        .avatar-particles {
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
        }

        .particle {
            position: absolute;
            width: 8px;
            height: 8px;
            background: var(--secondary);
            border-radius: 50%;
            animation: orbit 6s linear infinite;
        }

        @keyframes orbit {
            from { transform: rotate(0deg) translateX(140px) rotate(0deg); }
            to { transform: rotate(360deg) translateX(140px) rotate(-360deg); }
        }

        /* ===== FLOATING CARDS ===== */
        .floating-cards {
            position: absolute;
            width: 100%;
            height: 100%;
        }

        .floating-card {
            position: absolute;
            background: rgba(48, 54, 61, 0.6);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(88, 166, 255, 0.2);
            border-radius: 12px;
            padding: 15px 20px;
            font-size: 0.85rem;
            color: var(--text);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            animation: float-card 4s ease-in-out infinite;
        }

        @keyframes float-card {
            0%, 100% { transform: translateY(0px) translateX(0px); }
            50% { transform: translateY(-15px) translateX(5px); }
        }

        .card-1 {
            top: -20px;
            left: -60px;
            animation-delay: 0s;
        }

        .card-2 {
            bottom: -30px;
            right: -50px;
            animation-delay: 1s;
        }

        /* ===== MAIN SECTIONS ===== */
        section {
            margin: 80px 0;
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 40px;
            color: var(--text);
            display: flex;
            align-items: center;
            gap: 15px;
            position: relative;
        }

        h2::after {
            content: '';
            flex: 1;
            height: 1px;
            background: linear-gradient(90deg, var(--primary), transparent);
        }

        /* ===== STATS GRID ===== */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 60px;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(88, 166, 255, 0.05), rgba(247, 92, 126, 0.05));
            border: 1px solid rgba(88, 166, 255, 0.1);
            border-radius: 16px;
            padding: 30px;
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(247, 92, 126, 0.1) 0%, transparent 70%);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            border-color: var(--primary);
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(247, 92, 126, 0.15);
        }

        .stat-card:hover::before {
            top: -20%;
            right: -20%;
        }

        .stat-icon {
            font-size: 2rem;
            margin-bottom: 15px;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--text-secondary);
            margin-bottom: 10px;
        }

        .stat-value {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .stat-description {
            font-size: 0.85rem;
            color: var(--text-secondary);
        }

        /* ===== ABOUT SECTION ===== */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .about-card {
            background: linear-gradient(135deg, rgba(88, 166, 255, 0.08), rgba(247, 92, 126, 0.08));
            border: 1px solid rgba(88, 166, 255, 0.15);
            border-radius: 16px;
            padding: 40px;
            backdrop-filter: blur(10px);
        }

        .about-card h3 {
            font-size: 1.4rem;
            color: var(--secondary);
            margin-bottom: 20px;
        }

        .about-card ul {
            list-style: none;
        }

        .about-card li {
            padding: 12px 0;
            display: flex;
            align-items: flex-start;
            gap: 12px;
            border-bottom: 1px solid rgba(88, 166, 255, 0.1);
            transition: all 0.3s ease;
        }

        .about-card li:hover {
            padding-left: 10px;
            color: var(--primary);
        }

        .about-card li::before {
            content: "→";
            color: var(--primary);
            font-weight: bold;
            font-size: 1.2em;
            flex-shrink: 0;
            margin-top: 2px;
        }

        /* ===== SKILLS SECTION ===== */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 15px;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(31, 111, 235, 0.1), rgba(247, 92, 126, 0.1));
            border: 1px solid rgba(88, 166, 255, 0.2);
            border-radius: 12px;
            padding: 20px 15px;
            text-align: center;
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s ease;
        }

        .skill-card:hover::before {
            transform: scaleX(1);
        }

        .skill-card:hover {
            transform: translateY(-8px);
            border-color: var(--primary);
            box-shadow: 0 15px 35px rgba(247, 92, 126, 0.2);
            background: linear-gradient(135deg, rgba(31, 111, 235, 0.15), rgba(247, 92, 126, 0.15));
        }

        .skill-icon {
            font-size: 2rem;
            margin-bottom: 10px;
            transition: transform 0.3s ease;
        }

        .skill-card:hover .skill-icon {
            transform: scale(1.2) rotate(5deg);
        }

        .skill-name {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--text);
        }

        /* ===== SOCIAL SECTION ===== */
        .social-section {
            text-align: center;
            margin: 80px 0;
        }

        .social-grid {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .social-link {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(88, 166, 255, 0.1), rgba(247, 92, 126, 0.1));
            border: 2px solid rgba(88, 166, 255, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            text-decoration: none;
            color: var(--secondary);
        }

        .social-link:hover {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-color: var(--primary);
            transform: translateY(-8px) rotate(10deg);
            box-shadow: 0 15px 35px rgba(247, 92, 126, 0.3);
            color: white;
        }

        /* ===== TIMELINE / EXPERIENCE ===== */
        .timeline {
            position: relative;
            padding: 40px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 100%;
            background: linear-gradient(180deg, var(--primary), transparent);
        }

        .timeline-item {
            margin-bottom: 40px;
            width: 45%;
            position: relative;
        }

        .timeline-item:nth-child(odd) {
            margin-left: 0;
            margin-right: auto;
            text-align: right;
        }

        .timeline-item:nth-child(even) {
            margin-left: auto;
            margin-right: 0;
            text-align: left;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            top: 20px;
            width: 16px;
            height: 16px;
            background: var(--primary);
            border-radius: 50%;
            right: -42px;
            border: 3px solid var(--dark);
            transition: all 0.3s ease;
        }

        .timeline-item:nth-child(even)::before {
            left: -42px;
            right: auto;
        }

        .timeline-item:hover::before {
            width: 24px;
            height: 24px;
            top: 16px;
            box-shadow: 0 0 20px var(--primary);
        }

        .timeline-content {
            background: linear-gradient(135deg, rgba(88, 166, 255, 0.08), rgba(247, 92, 126, 0.08));
            border: 1px solid rgba(88, 166, 255, 0.15);
            border-radius: 12px;
            padding: 25px;
            transition: all 0.3s ease;
        }

        .timeline-content:hover {
            border-color: var(--primary);
            box-shadow: 0 10px 30px rgba(247, 92, 126, 0.1);
        }

        .timeline-date {
            color: var(--primary);
            font-weight: 600;
            font-size: 0.9rem;
        }

        .timeline-title {
            color: var(--text);
            font-weight: 600;
            margin: 10px 0;
        }

        /* ===== FOOTER ===== */
        footer {
            text-align: center;
            margin-top: 100px;
            padding: 40px 0;
            border-top: 1px solid rgba(88, 166, 255, 0.1);
            color: var(--text-secondary);
        }

        footer a {
            color: var(--primary);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        footer a:hover {
            color: var(--secondary);
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 1024px) {
            header {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .avatar-container {
                width: 250px;
                height: 250px;
            }

            .avatar-svg {
                width: 220px;
                height: 220px;
            }

            .about-grid {
                grid-template-columns: 1fr;
            }

            .timeline::before {
                left: 0;
            }

            .timeline-item,
            .timeline-item:nth-child(odd),
            .timeline-item:nth-child(even) {
                width: 100%;
                padding-left: 60px;
                text-align: left;
            }

            .timeline-item::before,
            .timeline-item:nth-child(even)::before {
                left: 0;
                right: auto;
            }
        }

        @media (max-width: 768px) {
            .container {
                padding: 30px 15px;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            h2 {
                font-size: 1.8rem;
            }

            .stats-mini {
                flex-wrap: wrap;
                gap: 20px;
            }

            .skills-container {
                grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            }

            .stat-card {
                padding: 20px;
            }

            .floating-cards {
                display: none;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- HERO SECTION -->
        <header>
            <div class="hero-content">
                <p class="hero-subtitle">Welcome to my portfolio</p>
                <h1>Khaled Helmy</h1>
                <p class="hero-subtitle" style="background: linear-gradient(135deg, var(--secondary), var(--primary)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Full Stack Developer</p>
                
                <p class="hero-title">
                    🚀 Software Engineer | Backend Node.js Developer<br>
                    💻 MERN Stack Developer | NestJS Enthusiast<br>
                    📚 IT Student • Always Learning
                </p>

                <p class="hero-description">
                    Passionate about building scalable, high-performance applications. Currently at <strong>Md Soft</strong>, transforming ideas into elegant code. Specializing in modern backend architectures and full-stack development with a focus on clean, maintainable solutions.
                </p>

                <div class="cta-buttons">
                    <a href="https://github.com/khaledelmyg" class="btn btn-primary">
                        💻 View My Code
                    </a>
                    <a href="https://wa.me/message/VCR6S7GI4C3MA1" class="btn btn-secondary">
                        💬 Let's Talk
                    </a>
                </div>

                <div class="stats-mini">
                    <div class="stat-mini">
                        <div class="stat-mini-number">36</div>
                        <div class="stat-mini-label">Stars Earned</div>
                    </div>
                    <div class="stat-mini">
                        <div class="stat-mini-number">150+</div>
                        <div class="stat-mini-label">Commits</div>
                    </div>
                    <div class="stat-mini">
                        <div class="stat-mini-number">8</div>
                        <div class="stat-mini-label">Pull Requests</div>
                    </div>
                </div>
            </div>

            <div class="avatar-section">
                <div class="avatar-container">
                    <div class="avatar-wrapper">
                        <div class="avatar-inner">
                            <svg class="avatar-svg" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
                                <defs>
                                    <linearGradient id="head-grad" x1="0%" y1="0%" x2="100%" y2="100%">
                                        <stop offset="0%" style="stop-color:#f75c7e;stop-opacity:1" />
                                        <stop offset="100%" style="stop-color:#58a6ff;stop-opacity:1" />
                                    </linearGradient>
                                </defs>
                                <!-- Head -->
                                <circle cx="100" cy="80" r="50" fill="url(#head-grad)"/>
                                <!-- Eyes -->
                                <circle cx="85" cy="70" r="6" fill="white"/>
                                <circle cx="115" cy="70" r="6" fill="white"/>
                                <circle cx="86" cy="68" r="3" fill="black"/>
                                <circle cx="116" cy="68" r="3" fill="black"/>
                                <!-- Smile -->
                                <path d="M 85 90 Q 100 105 115 90" stroke="white" stroke-width="4" fill="none" stroke-linecap="round"/>
                                <!-- Body -->
                                <rect x="75" y="130" width="50" height="60" rx="10" fill="url(#head-grad)"/>
                                <!-- Arms -->
                                <rect x="30" y="135" width="45" height="15" rx="7" fill="url(#head-grad)"/>
                                <rect x="125" y="135" width="45" height="15" rx="7" fill="url(#head-grad)"/>
                            </svg>
                        </div>
                    </div>
                    <div class="avatar-particles">
                        <div class="particle" style="animation-delay: 0s;"></div>
                        <div class="particle" style="animation-delay: 2s;"></div>
                        <div class="particle" style="animation-delay: 4s;"></div>
                    </div>
                    <div class="floating-cards">
                        <div class="floating-card card-1">
                            💡 Innovative Solutions
                        </div>
                        <div class="floating-card card-2">
                            🚀 High Performance
                        </div>
                    </div>
                </div>
            </div>
        </header>

        <!-- STATS SECTION -->
        <section>
            <h2>📊 Statistics</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-icon">⭐</div>
                    <div class="stat-label">Stars Earned</div>
                    <div class="stat-value">36</div>
                    <div class="stat-description">Community recognition on GitHub</div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon">📝</div>
                    <div class="stat-label">Total Commits</div>
                    <div class="stat-value">150+</div>
                    <div class="stat-description">Year of consistent development</div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon">🔀</div>
                    <div class="stat-label">Pull Requests</div>
                    <div class="stat-value">8</div>
                    <div class="stat-description">Contributions to projects</div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon">🐛</div>
                    <div class="stat-label">Issues Reported</div>
                    <div class="stat-value">1</div>
                    <div class="stat-description">Quality improvement initiatives</div>
                </div>
            </div>
        </section>

        <!-- ABOUT SECTION -->
        <section>
            <h2>👋 About Me</h2>
            <div class="about-grid">
                <div class="about-card">
                    <h3>Who I Am</h3>
                    <ul>
                        <li>🔭 Working at <strong>Md Soft</strong></li>
                        <li>👨‍💻 IT Student & Tech Enthusiast</li>
                        <li>🌱 Mastering <strong>NestJS</strong></li>
                        <li>💡 Problem Solver & Innovator</li>
                        <li>🎯 Passionate about Clean Code</li>
                    </ul>
                </div>
                <div class="about-card">
                    <h3>What I Do</h3>
                    <ul>
                        <li>🏗️ Build scalable backend systems</li>
                        <li>⚡ Optimize performance & UX</li>
                        <li>🔐 Design secure architectures</li>
                        <li>📚 Write maintai
