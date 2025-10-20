<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M.A.R.K - Professional Email Platform</title>
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
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: #ffffff;
            margin: 3px 0;
            transition: 0.3s;
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
            
            .nav-links {
                display: none;
            }
            
            .mobile-menu {
                display: flex;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
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
                <div class="logo-icon">M</div>
                M.A.R.K
            </a>
            <ul class="nav-links">
                <li><a href="#features">Features</a></li>
                <li><a href="#platform">Platform</a></li>
                <li><a href="#security">Security</a></li>
                <li><a href="#" onclick="openModal('loginModal')">Login</a></li>
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
            <h1>M.A.R.K Email Platform</h1>
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
                    <p>Create professional @mark.com email addresses with full domain control and enterprise-grade branding capabilities.</p>
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

    <!-- Login Modal -->
    <div id="loginModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('loginModal')">&times;</span>
            <h2 style="color: #00ff00; margin-bottom: 30px; text-align: center;">Login to M.A.R.K</h2>
            <form id="loginForm">
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" id="email" name="email" placeholder="your.name@mark.com" required>
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
                Don't have an account? <a href="#" style="color: #00ff00;" onclick="alert('Registration feature coming soon!')">Sign up</a>
            </p>
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
                        <li><a href="#">About M.A.R.K</a></li>
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
                <p>&copy; 2024 M.A.R.K Platform. All rights reserved. | Professional Email Communication</p>
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

        // Smooth scrolling for navigation links
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
            document.getElementById(modalId).style.display = 'block';
            document.body.style.overflow = 'hidden';
        }

        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
            document.body.style.overflow = 'auto';
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

        // Login form handling
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            
            // Simulate login process
            if (email && password) {
                alert('Login successful! Welcome to M.A.R.K Platform.');
                closeModal('loginModal');
                // Here you would typically redirect to the dashboard
                // window.location.href = 'dashboard.html';
            } else {
                alert('Please fill in all fields.');
            }
        });

        // Mobile menu toggle
        function toggleMobileMenu() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
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

        // Observe feature cards for animation
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            
            const featureCards = document.querySelectorAll('.feature-card');
            featureCards.forEach((card, index) => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(50px)';
                card.style.transition = 'all 0.6s ease';
                card.style.transitionDelay = (index * 0.1) + 's';
                observer.observe(card);
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
    </script>
</body>
</html>
