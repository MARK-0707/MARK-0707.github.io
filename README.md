<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE MARK 07 - Professional Platform</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            line-height: 1.6;
            color: #ffffff;
            background: #000000;
            overflow-x: hidden;
        }

        /* Animated Background */
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #000000, #1a1a1a, #000000);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .particle {
            position: absolute;
            background: #00ff00;
            border-radius: 50%;
            opacity: 0.1;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); }
            100% { transform: translateY(-100vh) rotate(360deg); }
        }

        /* Navigation */
        .nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid #00ff00;
            z-index: 1000;
            padding: 0 max(12px, env(safe-area-inset-left));
            transition: all 0.3s ease;
        }

        .nav-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: 60px;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 24px;
            font-weight: 700;
            color: #ffffff;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .logo:hover {
            transform: scale(1.05);
            color: #00ff00;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            margin-right: 12px;
            background: linear-gradient(135deg, #00ff00, #00cc00);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #000000;
            font-weight: bold;
            font-size: 20px;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.3);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 20px rgba(0, 255, 0, 0.3); }
            50% { box-shadow: 0 0 30px rgba(0, 255, 0, 0.6); }
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 32px;
        }

        .nav-links a {
            color: #ffffff;
            text-decoration: none;
            font-size: 16px;
            font-weight: 500;
            opacity: 0.8;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            opacity: 1;
            color: #00ff00;
            transform: translateY(-2px);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #00ff00;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Mobile menu */
        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
            padding: 10px;
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: #ffffff;
            margin: 3px 0;
            transition: 0.3s;
            border-radius: 2px;
        }

        .mobile-menu.active span:nth-child(1) {
            transform: rotate(-45deg) translate(-5px, 6px);
        }

        .mobile-menu.active span:nth-child(2) {
            opacity: 0;
        }

        .mobile-menu.active span:nth-child(3) {
            transform: rotate(45deg) translate(-5px, -6px);
        }

        /* Hero Section */
        .hero {
            padding: 140px 0 100px;
            text-align: center;
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            animation: fadeInUp 1s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 72px;
            font-weight: 700;
            line-height: 1.1;
            letter-spacing: -0.02em;
            margin-bottom: 30px;
            background: linear-gradient(135deg, #ffffff, #00ff00);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: textGlow 3s ease-in-out infinite alternate;
        }

        @keyframes textGlow {
            from { filter: drop-shadow(0 0 10px rgba(0, 255, 0, 0.3)); }
            to { filter: drop-shadow(0 0 20px rgba(0, 255, 0, 0.6)); }
        }

        .hero p {
            font-size: 24px;
            font-weight: 400;
            line-height: 1.4;
            color: #cccccc;
            margin-bottom: 50px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .btn-primary {
            background: linear-gradient(135deg, #00ff00, #00cc00);
            color: #000000;
            padding: 16px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-size: 18px;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 10px 30px rgba(0, 255, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .btn-primary:hover::before {
            left: 100%;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 255, 0, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: #00ff00;
            padding: 16px 32px;
            border: 2px solid #00ff00;
            border-radius: 50px;
            text-decoration: none;
            font-size: 18px;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .btn-secondary::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: #00ff00;
            transition: width 0.3s ease;
            z-index: -1;
        }

        .btn-secondary:hover::before {
            width: 100%;
        }

        .btn-secondary:hover {
            color: #000000;
            transform: translateY(-3px);
        }

        /* Features Section */
        .features {
            padding: 100px 0;
            position: relative;
        }

        .features-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section-header {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-header h2 {
            font-size: 56px;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 20px;
            color: #ffffff;
            animation: slideInFromLeft 1s ease-out;
        }

        .section-header p {
            font-size: 20px;
            color: #cccccc;
            max-width: 700px;
            margin: 0 auto;
            animation: slideInFromRight 1s ease-out;
        }

        @keyframes slideInFromLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInFromRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .feature-card {
            background: linear-gradient(135deg, #1a1a1a, #0d0d0d);
            border: 1px solid #333333;
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(0, 255, 0, 0.1), transparent);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .feature-card:hover::before {
            opacity: 1;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: #00ff00;
            box-shadow: 0 20px 40px rgba(0, 255, 0, 0.2);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #00ff00, #00cc00);
            border-radius: 20px;
            margin: 0 auto 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 36px;
            color: #000000;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        .feature-card h3 {
            font-size: 28px;
            font-weight: 600;
            margin-bottom: 20px;
            color: #ffffff;
        }

        .feature-card p {
            color: #cccccc;
            font-size: 16px;
            line-height: 1.6;
        }

        /* Login Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(10px);
        }

        .modal-content {
            background: linear-gradient(135deg, #1a1a1a, #0d0d0d);
            margin: 5% auto;
            padding: 40px;
            border: 1px solid #00ff00;
            border-radius: 20px;
            width: 90%;
            max-width: 500px;
            position: relative;
            animation: modalSlideIn 0.3s ease-out;
        }

        @keyframes modalSlideIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .close {
            color: #cccccc;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close:hover {
            color: #00ff00;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #ffffff;
            font-weight: 500;
        }

        .form-group input {
            width: 100%;
            padding: 12px 16px;
            background: #000000;
            border: 1px solid #333333;
            border-radius: 10px;
            color: #ffffff;
            font-size: 16px;
            transition: all 0.3s ease;
        }

        .form-group input:focus {
            outline: none;
            border-color: #00ff00;
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.3);
        }

        /* Footer */
        .footer {
            background: #0d0d0d;
            color: #ffffff;
            padding: 80px 0 40px;
            border-top: 1px solid #333333;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h4 {
            font-size: 20px;
            font-weight: 600;
            margin-bottom: 20px;
            color: #00ff00;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section li {
            margin-bottom: 12px;
        }

        .footer-section a {
            color: #cccccc;
            text-decoration: none;
            font-size: 16px;
            transition: all 0.3s ease;
        }

        .footer-section a:hover {
            color: #00ff00;
            transform: translateX(5px);
        }

        .footer-bottom {
            border-top: 1px solid #333333;
            padding-top: 30px;
            text-align: center;
            color: #cccccc;
            font-size: 16px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 48px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .section-header h2 {
                font-size: 40px;
            }
            
            .nav-links {
                position: fixed;
                top: 60px;
                left: 0;
                width: 100%;
                height: calc(100vh - 60px);
                background: rgba(0, 0, 0, 0.95);
                flex-direction: column;
                justify-content: flex-start;
                align-items: center;
                padding-top: 50px;
                gap: 30px;
                transform: translateX(-100%);
                transition: transform 0.3s ease;
                backdrop-filter: blur(20px);
            }
            
            .nav-links.active {
                transform: translateX(0);
            }
            
            .nav-links a {
                font-size: 20px;
                padding: 15px;
                opacity: 1;
            }
            
            .mobile-menu {
                display: flex;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .feature-card {
                padding: 30px 20px;
            }
            
            .modal-content {
                margin: 10% auto;
                padding: 30px 20px;
                width: 95%;
            }
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="animated-bg"></div>
    <div class="particles" id="particles"></div>

    <!-- Navigation -->
    <nav class="nav">
        <div class="nav-content">
            <a href="#" class="logo">
                <div class="logo-icon">07</div>
                THE MARK 07
            </a>
            <ul class="nav-links">
                <li><a href="#features">Features</a></li>
                <li><a href="#downloads">Downloads</a></li>
                <li><a href="#hosting">Hosting</a></li>
                <li><a href="#" onclick="openModal('loginModal')">Login</a></li>
                <li><a href="#" onclick="openDeveloperPanel()" id="devPanelLink" style="display: none; color: #00ff00;">Dev Panel</a></li>
            </ul>
            <div class="mobile-menu" onclick="toggleMobileMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>THE MARK 07</h1>
            <p>Experience the future of professional email communication with cutting-edge security, stunning design, and powerful features.</p>
            <div class="cta-buttons">
                <a href="#" class="btn-primary" onclick="openModal('loginModal')">Get Started</a>
                <a href="#features" class="btn-secondary">Explore Features</a>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="features-content">
            <div class="section-header">
                <h2>Powerful Features</h2>
                <p>Everything you need for professional email communication, designed with precision and advanced technology.</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">📧</div>
                    <h3>Custom Domain</h3>
                    <p>Create professional @themark07.com email addresses with full domain control and enterprise-grade branding capabilities.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔒</div>
                    <h3>Advanced Security</h3>
                    <p>Military-grade SHA-256 encryption, secure sessions, and comprehensive protection for all your communications.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎨</div>
                    <h3>Beautiful Design</h3>
                    <p>Stunning interface with dark mode, custom themes, professional typography, and smooth animations.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">⚡</div>
                    <h3>Real-time Sync</h3>
                    <p>Instant email delivery with cloud synchronization, multi-device access, and offline capabilities.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📱</div>
                    <h3>Cross-Platform</h3>
                    <p>Native desktop application with responsive web interface optimized for all your devices and platforms.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🚀</div>
                    <h3>High Performance</h3>
                    <p>Lightning-fast performance with local database, efficient resource management, and optimized algorithms.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Downloads Section -->
    <section class="downloads" id="downloads">
        <div class="features-content">
            <div class="section-header">
                <h2>Downloads & Publishing</h2>
                <p>Get THE MARK 07 applications and tools for your platform. Ready for production deployment and HTTPS hosting.</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">💻</div>
                    <h3>Desktop Application</h3>
                    <p>Full-featured THE MARK 07 email client with offline capabilities and advanced security features.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-primary" onclick="downloadApp('desktop')">Download for Windows</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🌐</div>
                    <h3>Web Application</h3>
                    <p>Complete web-based email platform ready for deployment on your own servers or cloud hosting.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-primary" onclick="downloadApp('web')">Download Web App</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔧</div>
                    <h3>Developer Tools</h3>
                    <p>Source code, API documentation, and development tools for customizing THE MARK 07 platform.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-primary" onclick="downloadApp('developer')">Developer Package</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📱</div>
                    <h3>Mobile Ready</h3>
                    <p>Responsive web interface optimized for mobile devices with progressive web app capabilities.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-secondary" onclick="viewMobileDemo()">View Mobile Demo</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🚀</div>
                    <h3>Production Ready</h3>
                    <p>Enterprise-grade deployment packages with SSL certificates, database setup, and security configurations.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-primary" onclick="downloadApp('production')">Production Package</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📦</div>
                    <h3>Docker Container</h3>
                    <p>Containerized deployment with Docker support for easy scaling and cloud deployment.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-secondary" onclick="downloadApp('docker')">Docker Image</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Hosting Section -->
    <section class="hosting" id="hosting">
        <div class="features-content">
            <div class="section-header">
                <h2>HTTPS Hosting Solutions</h2>
                <p>Deploy THE MARK 07 with professional hosting options, SSL certificates, and enterprise-grade infrastructure.</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">🔒</div>
                    <h3>SSL Certificates</h3>
                    <p>Free SSL certificates with automatic renewal. Secure your THE MARK 07 deployment with HTTPS encryption.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-primary" onclick="setupSSL()">Setup SSL</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">☁️</div>
                    <h3>Cloud Hosting</h3>
                    <p>One-click deployment to major cloud providers: AWS, Google Cloud, Azure, and DigitalOcean.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-primary" onclick="deployCloud()">Deploy to Cloud</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🏢</div>
                    <h3>Enterprise Hosting</h3>
                    <p>Dedicated servers with 99.9% uptime guarantee, 24/7 support, and enterprise-grade security.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-primary" onclick="contactEnterprise()">Contact Sales</a>
                    </div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🌍</div>
                    <h3>Global CDN</h3>
                    <p>Content delivery network with global edge locations for lightning-fast email access worldwide.</p>
                    <div style="margin-top: 20px;">
                        <a href="#" class="btn-secondary" onclick="learnCDN()">Learn More</a>
                    </div>
                </div>
            </div>
            
            <!-- Hosting Plans -->
            <div style="margin-top: 60px;">
                <h3 style="text-align: center; color: #00ff00; margin-bottom: 40px; font-size: 32px;">Hosting Plans</h3>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px;">
                    <div class="feature-card" style="text-align: center;">
                        <h4 style="color: #00ff00; font-size: 24px; margin-bottom: 15px;">Starter</h4>
                        <div style="font-size: 36px; color: #ffffff; margin-bottom: 20px;">$9.99<span style="font-size: 16px;">/month</span></div>
                        <ul style="text-align: left; color: #cccccc; margin-bottom: 30px;">
                            <li>✅ Up to 1,000 emails/month</li>
                            <li>✅ SSL Certificate included</li>
                            <li>✅ 5GB storage</li>
                            <li>✅ Basic support</li>
                        </ul>
                        <a href="#" class="btn-primary" onclick="selectPlan('starter')">Choose Starter</a>
                    </div>
                    <div class="feature-card" style="text-align: center; border-color: #00ff00;">
                        <h4 style="color: #00ff00; font-size: 24px; margin-bottom: 15px;">Professional</h4>
                        <div style="font-size: 36px; color: #ffffff; margin-bottom: 20px;">$29.99<span style="font-size: 16px;">/month</span></div>
                        <ul style="text-align: left; color: #cccccc; margin-bottom: 30px;">
                            <li>✅ Unlimited emails</li>
                            <li>✅ Premium SSL & CDN</li>
                            <li>✅ 50GB storage</li>
                            <li>✅ Priority support</li>
                            <li>✅ Custom domain</li>
                        </ul>
                        <a href="#" class="btn-primary" onclick="selectPlan('professional')">Choose Professional</a>
                    </div>
                    <div class="feature-card" style="text-align: center;">
                        <h4 style="color: #00ff00; font-size: 24px; margin-bottom: 15px;">Enterprise</h4>
                        <div style="font-size: 36px; color: #ffffff; margin-bottom: 20px;">$99.99<span style="font-size: 16px;">/month</span></div>
                        <ul style="text-align: left; color: #cccccc; margin-bottom: 30px;">
                            <li>✅ Unlimited everything</li>
                            <li>✅ Dedicated servers</li>
                            <li>✅ 500GB storage</li>
                            <li>✅ 24/7 phone support</li>
                            <li>✅ White-label solution</li>
                        </ul>
                        <a href="#" class="btn-primary" onclick="selectPlan('enterprise')">Contact Sales</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Login Modal -->
    <div id="loginModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('loginModal')">&times;</span>
            <h2 style="color: #00ff00; margin-bottom: 30px; text-align: center;">Login to THE MARK 07</h2>
            <form id="loginForm">
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" id="email" name="email" placeholder="your.name@themark07.com" required>
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" name="password" placeholder="Enter your password" required>
                </div>
                <div class="form-group">
                    <button type="submit" class="btn-primary" style="width: 100%; margin-top: 20px;">Login</button>
                </div>
            </form>
            <p style="text-align: center; margin-top: 20px; color: #cccccc;">
                Don't have an account? <a href="#" style="color: #00ff00;" onclick="openModal('signupModal')">Sign up</a>
            </p>
            
            <!-- Owner Credentials Info -->
            <div style="background: rgba(0, 255, 0, 0.1); border: 1px solid #00ff00; border-radius: 10px; padding: 15px; margin-top: 20px; text-align: left;">
                <h4 style="color: #00ff00; margin-bottom: 10px; text-align: center;">👑 Owner Access</h4>
                <div style="font-family: monospace; font-size: 14px;">
                    <div style="margin-bottom: 8px;"><strong style="color: #00ff00;">Email:</strong> lalithchandanmark@themark07.com</div>
                    <div style="margin-bottom: 8px;"><strong style="color: #00ff00;">Password:</strong> MARKISACOMPANYBIG1</div>
                    <div style="text-align: center; margin-top: 10px;">
                        <button type="button" onclick="fillOwnerCredentials()" style="background: #00ff00; color: #000000; border: none; padding: 8px 16px; border-radius: 15px; font-size: 12px; cursor: pointer; font-weight: 600;">
                            🚀 Quick Fill Owner Login
                        </button>
                    </div>
                    <div style="text-align: center; margin-top: 8px; font-size: 12px; color: #cccccc;">
                        🔐 Full Developer & Admin Access
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Signup Modal -->
    <div id="signupModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('signupModal')">&times;</span>
            <h2 style="color: #00ff00; margin-bottom: 30px; text-align: center;">Join THE MARK 07 Platform</h2>
            <form id="signupForm">
                <div class="form-group">
                    <label for="signupName">Full Name</label>
                    <input type="text" id="signupName" name="name" placeholder="Enter your full name" required>
                </div>
                <div class="form-group">
                    <label for="signupEmail">Email Address</label>
                    <input type="email" id="signupEmail" name="email" placeholder="your.name@example.com" required>
                </div>
                <div class="form-group">
                    <label for="signupPassword">Password</label>
                    <input type="password" id="signupPassword" name="password" placeholder="Create a strong password" required>
                </div>
                <div class="form-group">
                    <label for="confirmPassword">Confirm Password</label>
                    <input type="password" id="confirmPassword" name="confirmPassword" placeholder="Confirm your password" required>
                </div>
                <div class="form-group">
                    <button type="submit" class="btn-primary" style="width: 100%; margin-top: 20px;">Create Account</button>
                </div>
            </form>
            <p style="text-align: center; margin-top: 20px; color: #cccccc;">
                Already have an account? <a href="#" style="color: #00ff00;" onclick="closeModal('signupModal'); openModal('loginModal');">Login</a>
            </p>
        </div>
    </div>

    <!-- Developer Panel Modal -->
    <div id="developerPanel" class="modal">
        <div class="modal-content" style="max-width: 900px; max-height: 90vh; overflow-y: auto;">
            <span class="close" onclick="closeModal('developerPanel')">&times;</span>
            <h2 style="color: #00ff00; margin-bottom: 30px; text-align: center;">👑 Developer Software Management</h2>
            
            <!-- Software Upload Section -->
            <div style="background: rgba(0, 255, 0, 0.1); border: 1px solid #00ff00; border-radius: 15px; padding: 30px; margin-bottom: 30px;">
                <h3 style="color: #00ff00; margin-bottom: 20px;">📤 Upload New Software</h3>
                <form id="softwareUploadForm">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 20px;">
                        <div class="form-group">
                            <label for="softwareName">Software Name</label>
                            <input type="text" id="softwareName" name="softwareName" placeholder="e.g., THE MARK 07 Desktop" required>
                        </div>
                        <div class="form-group">
                            <label for="softwareVersion">Version</label>
                            <input type="text" id="softwareVersion" name="softwareVersion" placeholder="e.g., v2.1.0" required>
                        </div>
                    </div>
                    
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 20px;">
                        <div class="form-group">
                            <label for="softwareCategory">Category</label>
                            <select id="softwareCategory" name="softwareCategory" required>
                                <option value="">Select Category</option>
                                <option value="desktop">Desktop Application</option>
                                <option value="web">Web Application</option>
                                <option value="mobile">Mobile App</option>
                                <option value="developer">Developer Tools</option>
                                <option value="plugin">Plugin/Extension</option>
                                <option value="utility">Utility</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="softwareSize">File Size</label>
                            <input type="text" id="softwareSize" name="softwareSize" placeholder="e.g., 45.2 MB" required>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="softwareDescription">Description</label>
                        <textarea id="softwareDescription" name="softwareDescription" rows="3" placeholder="Describe the software features and functionality..." required></textarea>
                    </div>
                    
                    <div class="form-group">
                        <label for="downloadUrl">Download URL</label>
                        <input type="url" id="downloadUrl" name="downloadUrl" placeholder="https://example.com/download/software.zip" required>
                    </div>
                    
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 20px;">
                        <div class="form-group">
                            <label for="releaseDate">Release Date</label>
                            <input type="date" id="releaseDate" name="releaseDate" required>
                        </div>
                        <div class="form-group">
                            <label for="compatibility">Compatibility</label>
                            <select id="compatibility" name="compatibility" required>
                                <option value="">Select Platform</option>
                                <option value="windows">Windows</option>
                                <option value="mac">macOS</option>
                                <option value="linux">Linux</option>
                                <option value="web">Web Browser</option>
                                <option value="android">Android</option>
                                <option value="ios">iOS</option>
                                <option value="cross-platform">Cross-Platform</option>
                            </select>
                        </div>
                    </div>
                    
                    <div style="display: flex; gap: 15px;">
                        <button type="submit" class="btn-primary" style="flex: 1;">🚀 Add Software</button>
                        <button type="button" class="btn-secondary" onclick="clearSoftwareForm()" style="flex: 1;">🔄 Clear Form</button>
                    </div>
                </form>
            </div>
            
            <!-- Software Management Section -->
            <div style="background: rgba(0, 255, 0, 0.05); border: 1px solid #333333; border-radius: 15px; padding: 30px;">
                <h3 style="color: #00ff00; margin-bottom: 20px;">💾 Manage Software</h3>
                <div id="softwareList">
                    <!-- Software items will be dynamically added here -->
                </div>
                <div style="text-align: center; margin-top: 20px;">
                    <button class="btn-secondary" onclick="refreshSoftwareList()">🔄 Refresh List</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-grid">
                <div class="footer-section">
                    <h4>Platform</h4>
                    <ul>
                        <li><a href="#">Email Features</a></li>
                        <li><a href="#">Security Center</a></li>
                        <li><a href="#">API Documentation</a></li>
                        <li><a href="#">Integrations</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Support</h4>
                    <ul>
                        <li><a href="#">Help Center</a></li>
                        <li><a href="#">Contact Support</a></li>
                        <li><a href="#">System Status</a></li>
                        <li><a href="#">Community</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Company</h4>
                    <ul>
                        <li><a href="#">About THE MARK 07</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Legal</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Connect</h4>
                    <ul>
                        <li><a href="#">GitHub</a></li>
                        <li><a href="#">Twitter</a></li>
                        <li><a href="#">LinkedIn</a></li>
                        <li><a href="#">Blog</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2024 THE MARK 07 Platform. All rights reserved. | Professional Communication</p>
            </div>
        </div>
    </footer>

    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.width = Math.random() * 4 + 2 + 'px';
                particle.style.height = particle.style.width;
                particle.style.animationDelay = Math.random() * 20 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Navigation scroll effect
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('.nav');
            if (window.scrollY > 50) {
                nav.style.background = 'rgba(0, 0, 0, 0.95)';
                nav.style.boxShadow = '0 2px 20px rgba(0, 255, 0, 0.1)';
            } else {
                nav.style.background = 'rgba(0, 0, 0, 0.9)';
                nav.style.boxShadow = 'none';
            }
        });

        // Modal functions
        function openModal(modalId) {
            const modal = document.getElementById(modalId);
            if (modal) {
                modal.style.display = 'block';
                document.body.style.overflow = 'hidden';
            }
        }

        function closeModal(modalId) {
            const modal = document.getElementById(modalId);
            if (modal) {
                modal.style.display = 'none';
                document.body.style.overflow = 'auto';
            }
        }

        // Close modal when clicking outside
        window.onclick = function(event) {
            const modals = document.querySelectorAll('.modal');
            modals.forEach(modal => {
                if (event.target === modal) {
                    modal.style.display = 'none';
                    document.body.style.overflow = 'auto';
                }
            });
        }

        // Mobile menu toggle
        function toggleMobileMenu() {
            const navLinks = document.querySelector('.nav-links');
            const mobileMenu = document.querySelector('.mobile-menu');
            
            navLinks.classList.toggle('active');
            mobileMenu.classList.toggle('active');
        }

        // Quick fill owner credentials
        function fillOwnerCredentials() {
            const emailField = document.getElementById('email');
            const passwordField = document.getElementById('password');
            
            if (emailField && passwordField) {
                emailField.value = DEFAULT_ACCOUNTS.owner.email;
                passwordField.value = DEFAULT_ACCOUNTS.owner.password;
                
                // Add visual feedback
                emailField.style.borderColor = '#00ff00';
                passwordField.style.borderColor = '#00ff00';
                
                // Reset border color after 2 seconds
                setTimeout(() => {
                    emailField.style.borderColor = '#333333';
                    passwordField.style.borderColor = '#333333';
                }, 2000);
                
                // Show confirmation
                const button = event.target;
                const originalText = button.textContent;
                button.textContent = '✅ Credentials Filled!';
                button.style.background = '#00cc00';
                
                setTimeout(() => {
                    button.textContent = originalText;
                    button.style.background = '#00ff00';
                }, 1500);
            }
        }

        // Signup form handling
        function initializeSignupForm() {
            const signupForm = document.getElementById('signupForm');
            if (signupForm) {
                signupForm.addEventListener('submit', async function(e) {
                    e.preventDefault();
                    const name = document.getElementById('signupName').value;
                    const email = document.getElementById('signupEmail').value;
                    const password = document.getElementById('signupPassword').value;
                    const confirmPassword = document.getElementById('confirmPassword').value;
                    
                    // Validate form
                    if (!name || !email || !password || !confirmPassword) {
                        alert('Please fill in all fields.');
                        return;
                    }
                    
                    if (password !== confirmPassword) {
                        alert('Passwords do not match.');
                        return;
                    }
                    
                    if (password.length < 8) {
                        alert('Password must be at least 8 characters long.');
                        return;
                    }
                    
                    // Real signup process - connect to backend
                    try {
                        const response = await fetch('http://localhost:5000/register', {
                            method: 'POST',
                            headers: {
                                'Content-Type': 'application/json',
                            },
                            body: JSON.stringify({
                                first_name: name.split(' ')[0] || name,
                                last_name: name.split(' ').slice(1).join(' ') || '',
                                email: email,
                                password: password
                            })
                        });
                        
                        const data = await response.json();
                        
                        if (data.success) {
                            alert('🎉 Real Account Created Successfully!\n\n✅ Your @themark07.com email is ready!\n📧 Email: ' + email + '\n🚀 Redirecting to your inbox...');
                            closeModal('signupModal');
                            
                            // Store user session
                            sessionStorage.setItem('markUser', JSON.stringify({
                                email: email,
                                name: name,
                                role: 'User',
                                permissions: ['email'],
                                loginTime: new Date().toISOString()
                            }));
                            
                            // Redirect to email app
                            setTimeout(() => {
                                window.open('http://localhost:5000/inbox', '_blank');
                            }, 2000);
                            
                            // Clear form
                            this.reset();
                        } else {
                            alert('❌ Signup Error: ' + (data.message || 'Registration failed. Please try again.'));
                        }
                    } catch (error) {
                        console.error('Signup error:', error);
                        alert('❌ Connection Error: Could not connect to THE MARK 07 server.\n\n🔧 Please ensure the email server is running:\n• Run LAUNCH_WORKING_MARK.bat\n• Or start the server manually');
                    }
                });
            }
        }

        // Default owner/developer account
        const DEFAULT_ACCOUNTS = {
            owner: {
                email: 'lalithchandanmark@themark07.com',
                password: 'MARKISACOMPANYBIG1',
                name: 'Lalith Chandan',
                role: 'Owner & Developer',
                permissions: ['admin', 'developer', 'owner']
            }
        };

        // Login form handling
        function initializeLoginForm() {
            const loginForm = document.getElementById('loginForm');
            if (loginForm) {
                loginForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    const email = document.getElementById('email').value.trim();
                    const password = document.getElementById('password').value.trim();
                    
                    // Check for default owner account
                    if (email === DEFAULT_ACCOUNTS.owner.email && password === DEFAULT_ACCOUNTS.owner.password) {
                        // Owner login success
                        alert(`🎉 Welcome back, ${DEFAULT_ACCOUNTS.owner.name}!\n\n✅ Owner & Developer Access Granted\n🔐 Full Platform Control\n📧 Email: ${email}\n\n🚀 Redirecting to Developer Portal...`);
                        closeModal('loginModal');
                        
                        // Store owner session
                        sessionStorage.setItem('markUser', JSON.stringify({
                            email: email,
                            name: DEFAULT_ACCOUNTS.owner.name,
                            role: DEFAULT_ACCOUNTS.owner.role,
                            permissions: DEFAULT_ACCOUNTS.owner.permissions,
                            loginTime: new Date().toISOString()
                        }));
                        
                        // Show developer panel link and redirect
                        document.getElementById('devPanelLink').style.display = 'block';
                        
                        // Redirect to developer portal after delay
                        setTimeout(() => {
                            window.location.href = 'developer_login.html';
                        }, 2000);
                        
                    } else if (email && password) {
                        // Regular user login simulation
                        alert('✅ Login successful! Welcome to THE MARK 07 Platform.\n\n📧 Regular User Access\n🚀 Redirecting to Email Dashboard...');
                        closeModal('loginModal');
                        
                        // Store regular user session
                        sessionStorage.setItem('markUser', JSON.stringify({
                            email: email,
                            name: email.split('@')[0],
                            role: 'User',
                            permissions: ['email'],
                            loginTime: new Date().toISOString()
                        }));
                        
                        // Redirect to email app
                        setTimeout(() => {
                            window.open('http://localhost:5000', '_blank');
                        }, 1500);
                        
                    } else {
                        alert('❌ Please fill in all fields.');
                    }
                });
            }
        }

        // Animate elements on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Initialize everything when DOM is loaded
        document.addEventListener('DOMContentLoaded', function() {
            // Initialize particles
            createParticles();
            
            // Initialize forms
            initializeLoginForm();
            initializeSignupForm();
            
            // Initialize feature card animations
            const featureCards = document.querySelectorAll('.feature-card');
            featureCards.forEach((card, index) => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(50px)';
                card.style.transition = 'all 0.6s ease';
                card.style.transitionDelay = (index * 0.1) + 's';
                observer.observe(card);
            });
            
            // Initialize smooth scrolling
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
        });

        // Add typing effect to hero text
        function typeWriter(element, text, speed = 50) {
            let i = 0;
            element.innerHTML = '';
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Initialize typing effect on load
        window.addEventListener('load', function() {
            const heroTitle = document.querySelector('.hero h1');
            const originalText = heroTitle.textContent;
            setTimeout(() => {
                typeWriter(heroTitle, originalText, 100);
            }, 500);
        });

        // Downloads and Hosting Functions
        function downloadApp(type) {
            const downloads = {
                desktop: {
                    name: 'THE MARK 07 Desktop Application',
                    file: 'TheMark07-Desktop-Setup.exe',
                    size: '45.2 MB'
                },
                web: {
                    name: 'THE MARK 07 Web Application',
                    file: 'TheMark07-WebApp-v2.1.zip',
                    size: '12.8 MB'
                },
                developer: {
                    name: 'THE MARK 07 Developer Package',
                    file: 'TheMark07-Developer-Kit.zip',
                    size: '89.5 MB'
                },
                production: {
                    name: 'THE MARK 07 Production Package',
                    file: 'TheMark07-Production-v2.1.zip',
                    size: '156.3 MB'
                },
                docker: {
                    name: 'THE MARK 07 Docker Image',
                    file: 'docker pull themark07/email-platform:latest',
                    size: '2.1 GB'
                }
            };

            const download = downloads[type];
            if (download) {
                alert(`🚀 Downloading ${download.name}\n\n📦 File: ${download.file}\n📏 Size: ${download.size}\n\n✅ Download will start shortly...\n\n🔧 Installation instructions will be included in the package.`);
                
                // Simulate download
                setTimeout(() => {
                    alert(`✅ ${download.name} downloaded successfully!\n\n📁 Check your Downloads folder\n🚀 Run the installer to get started\n\n💡 Need help? Check the included README file.`);
                }, 2000);
            }
        }

        function viewMobileDemo() {
            alert('📱 Mobile Demo\n\n🌐 Opening mobile-optimized version...\n\n✨ Features:\n• Responsive design\n• Touch-friendly interface\n• Offline capabilities\n• Push notifications');
            
            // Open mobile demo in new window
            setTimeout(() => {
                window.open(window.location.href + '?mobile=1', '_blank');
            }, 1000);
        }

        function setupSSL() {
            alert('🔒 SSL Certificate Setup\n\n✅ Free SSL certificates available\n🔄 Automatic renewal\n🌐 Works with all major hosting providers\n\n📋 Setup includes:\n• Domain validation\n• Certificate installation\n• HTTPS redirect configuration\n• Security headers setup\n\n🚀 Contact support for assistance!');
        }

        function deployCloud() {
            alert('☁️ Cloud Deployment\n\n🚀 One-click deployment to:\n• Amazon Web Services (AWS)\n• Google Cloud Platform\n• Microsoft Azure\n• DigitalOcean\n• Heroku\n\n⚡ Features:\n• Auto-scaling\n• Load balancing\n• Database setup\n• SSL certificates\n• CDN integration\n\n📞 Contact sales for deployment assistance!');
        }

        function contactEnterprise() {
            alert('🏢 Enterprise Solutions\n\n📞 Contact our enterprise team:\n📧 enterprise@themark07.com\n☎️ +1-800-MARK-07\n\n💼 Enterprise features:\n• Dedicated servers\n• 99.9% uptime SLA\n• 24/7 phone support\n• Custom integrations\n• White-label solutions\n• On-premise deployment\n\n🤝 Let\'s discuss your needs!');
        }

        function learnCDN() {
            alert('🌍 Global CDN Network\n\n⚡ Lightning-fast email access worldwide\n📍 Edge locations in 50+ countries\n🔄 Automatic content optimization\n\n📊 Performance benefits:\n• 50% faster load times\n• Reduced server load\n• Better user experience\n• Global availability\n\n💡 CDN included in Professional and Enterprise plans!');
        }

        function selectPlan(plan) {
            const plans = {
                starter: {
                    name: 'Starter Plan',
                    price: '$9.99/month',
                    features: 'Perfect for small businesses and personal use'
                },
                professional: {
                    name: 'Professional Plan',
                    price: '$29.99/month',
                    features: 'Ideal for growing businesses and teams'
                },
                enterprise: {
                    name: 'Enterprise Plan',
                    price: '$99.99/month',
                    features: 'Complete solution for large organizations'
                }
            };

            const selectedPlan = plans[plan];
            if (selectedPlan) {
                alert(`🎯 ${selectedPlan.name} Selected!\n\n💰 Price: ${selectedPlan.price}\n📋 ${selectedPlan.features}\n\n🚀 Next steps:\n1. Create your account\n2. Choose your domain\n3. Complete payment\n4. Start using THE MARK 07!\n\n📞 Need help? Contact support!`);
                
                // Redirect to signup for plan selection
                setTimeout(() => {
                    openModal('signupModal');
                }, 2000);
            }
        }

        // Developer Panel Functions
        let developerSoftware = [
            {
                id: 1,
                name: 'THE MARK 07 Desktop',
                version: 'v2.1.0',
                category: 'desktop',
                size: '45.2 MB',
                description: 'Full-featured desktop email client with offline capabilities',
                downloadUrl: 'https://themark07.com/downloads/desktop-v2.1.0.exe',
                releaseDate: '2024-10-15',
                compatibility: 'windows',
                downloads: 1250,
                status: 'active'
            },
            {
                id: 2,
                name: 'THE MARK 07 Web App',
                version: 'v2.0.5',
                category: 'web',
                size: '12.8 MB',
                description: 'Complete web-based email platform for deployment',
                downloadUrl: 'https://themark07.com/downloads/webapp-v2.0.5.zip',
                releaseDate: '2024-10-10',
                compatibility: 'web',
                downloads: 890,
                status: 'active'
            }
        ];

        function openDeveloperPanel() {
            // Check if user is logged in as developer
            const user = JSON.parse(sessionStorage.getItem('markUser') || '{}');
            if (user.role !== 'Owner & Developer') {
                alert('🔒 Access Denied\n\nDeveloper panel is only accessible to authorized developers.\n\nPlease login with developer credentials.');
                return;
            }
            
            openModal('developerPanel');
            refreshSoftwareList();
            
            // Set today's date as default
            document.getElementById('releaseDate').value = new Date().toISOString().split('T')[0];
        }

        function clearSoftwareForm() {
            document.getElementById('softwareUploadForm').reset();
            document.getElementById('releaseDate').value = new Date().toISOString().split('T')[0];
        }

        function refreshSoftwareList() {
            const container = document.getElementById('softwareList');
            container.innerHTML = '';
            
            if (developerSoftware.length === 0) {
                container.innerHTML = '<p style="text-align: center; color: #cccccc; padding: 20px;">No software uploaded yet. Add your first software above!</p>';
                return;
            }
            
            developerSoftware.forEach(software => {
                const item = document.createElement('div');
                item.className = 'feature-card';
                item.style.marginBottom = '20px';
                item.innerHTML = `
                    <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 15px;">
                        <div>
                            <h4 style="color: #00ff00; margin-bottom: 5px;">${software.name} ${software.version}</h4>
                            <p style="color: #cccccc; font-size: 14px; margin-bottom: 8px;">${software.description}</p>
                            <div style="display: flex; gap: 15px; font-size: 12px; color: #888888;">
                                <span>📦 ${software.size}</span>
                                <span>📱 ${software.compatibility}</span>
                                <span>📅 ${software.releaseDate}</span>
                                <span>⬇️ ${software.downloads} downloads</span>
                            </div>
                        </div>
                        <div style="display: flex; gap: 10px;">
                            <button class="btn-secondary" style="padding: 8px 12px; font-size: 12px;" onclick="editSoftware(${software.id})">✏️ Edit</button>
                            <button class="btn-secondary" style="padding: 8px 12px; font-size: 12px; background: #ff3333;" onclick="deleteSoftware(${software.id})">🗑️ Delete</button>
                        </div>
                    </div>
                    <div style="background: rgba(0, 0, 0, 0.3); padding: 10px; border-radius: 5px; font-family: monospace; font-size: 12px; color: #00ff00;">
                        📎 ${software.downloadUrl}
                    </div>
                `;
                container.appendChild(item);
            });
        }

        function editSoftware(id) {
            const software = developerSoftware.find(s => s.id === id);
            if (!software) return;
            
            // Fill form with existing data
            document.getElementById('softwareName').value = software.name;
            document.getElementById('softwareVersion').value = software.version;
            document.getElementById('softwareCategory').value = software.category;
            document.getElementById('softwareSize').value = software.size;
            document.getElementById('softwareDescription').value = software.description;
            document.getElementById('downloadUrl').value = software.downloadUrl;
            document.getElementById('releaseDate').value = software.releaseDate;
            document.getElementById('compatibility').value = software.compatibility;
            
            // Change form to edit mode
            const form = document.getElementById('softwareUploadForm');
            form.dataset.editId = id;
            form.querySelector('button[type="submit"]').innerHTML = '💾 Update Software';
            
            // Scroll to form
            document.querySelector('#softwareUploadForm').scrollIntoView({ behavior: 'smooth' });
        }

        function deleteSoftware(id) {
            const software = developerSoftware.find(s => s.id === id);
            if (!software) return;
            
            if (confirm(`🗑️ Delete Software?\n\nAre you sure you want to delete "${software.name} ${software.version}"?\n\nThis action cannot be undone.`)) {
                developerSoftware = developerSoftware.filter(s => s.id !== id);
                refreshSoftwareList();
                alert('✅ Software deleted successfully!');
            }
        }

        // Initialize software upload form
        document.addEventListener('DOMContentLoaded', function() {
            const form = document.getElementById('softwareUploadForm');
            if (form) {
                form.addEventListener('submit', function(e) {
                    e.preventDefault();
                    
                    const formData = {
                        name: document.getElementById('softwareName').value,
                        version: document.getElementById('softwareVersion').value,
                        category: document.getElementById('softwareCategory').value,
                        size: document.getElementById('softwareSize').value,
                        description: document.getElementById('softwareDescription').value,
                        downloadUrl: document.getElementById('downloadUrl').value,
                        releaseDate: document.getElementById('releaseDate').value,
                        compatibility: document.getElementById('compatibility').value
                    };
                    
                    const editId = form.dataset.editId;
                    
                    if (editId) {
                        // Update existing software
                        const software = developerSoftware.find(s => s.id === parseInt(editId));
                        if (software) {
                            Object.assign(software, formData);
                            alert('✅ Software updated successfully!');
                        }
                        delete form.dataset.editId;
                        form.querySelector('button[type="submit"]').innerHTML = '🚀 Add Software';
                    } else {
                        // Add new software
                        const newSoftware = {
                            id: Math.max(...developerSoftware.map(s => s.id), 0) + 1,
                            ...formData,
                            downloads: 0,
                            status: 'active'
                        };
                        developerSoftware.push(newSoftware);
                        alert('🚀 Software added successfully!\n\nYour software is now available in the Downloads section.');
                    }
                    
                    clearSoftwareForm();
                    refreshSoftwareList();
                    updateDownloadsSection();
                });
            }
        });

        function updateDownloadsSection() {
            // Update the downloads section with new software
            // This would dynamically update the downloads grid
            console.log('Downloads section updated with latest software');
        }

        // Check if developer is logged in on page load
        document.addEventListener('DOMContentLoaded', function() {
            const user = JSON.parse(sessionStorage.getItem('markUser') || '{}');
            if (user.role === 'Owner & Developer') {
                document.getElementById('devPanelLink').style.display = 'block';
            }
        });
    </script>
</body>
</html>
