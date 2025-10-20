<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M.A.R.K - Professional Email Platform</title>
    <style>
        /* M.A.R.K Website - Complete Apple Design System (Dark Theme) */

        :root {
            /* Apple Complete CSS Variables System - Dark Theme Adaptation */
            
            /* Navigation Heights & Responsive System */
            --ribbon-height: 0px;
            --r-globalnav-height: 44px;
            --r-globalmessage-segment-height: 0px;
            --r-globalnav-segmentbar-height: 0px;
            --nav-collective-height: calc(var(--r-globalnav-height, 0px) + var(--r-localnav-height, 0px) + var(--ribbon-height, 0px) + var(--r-localeswitcher-height, 0px) + var(--r-globalmessage-segment-height, 0px));
            
            /* Local Navigation Variables */
            --r-localnav-height: calc(52px * var(--r-localnav-text-zoom-factor));
            --r-localnav-stacked-height: calc(66px * var(--r-localnav-text-zoom-factor));
            --r-localnav-gn-height: calc(var(--r-globalnav-height, 44px) * var(--r-localnav-text-zoom-factor));
            --r-localnav-text-zoom-factor: 1;
            
            /* Focus System */
            --sk-focus-color: #00ff00;
            --sk-focus-color-alt: #ffffff;
            --sk-focus-offset: 1px;
            --sk-focus-offset-container: 3px;
            
            /* Complete Dark Theme Color System */
            --sk-glyph: #ffffff;
            --sk-glyph-gray: #f5f5f7;
            --sk-glyph-gray-alpha: rgba(255, 255, 255, 0.88);
            --sk-glyph-gray-secondary: #86868b;
            --sk-glyph-gray-secondary-alpha: rgba(255, 255, 255, 0.56);
            --sk-glyph-gray-secondary-alt: #d2d2d7;
            --sk-glyph-gray-secondary-alt-alpha: rgba(255, 255, 255, 0.72);
            --sk-glyph-gray-tertiary: #6e6e73;
            --sk-glyph-gray-tertiary-alpha: rgba(255, 255, 255, 0.48);
            --sk-glyph-blue: #0099ff;
            --sk-glyph-orange: #ff8c00;
            --sk-glyph-green: #00ff00;
            --sk-glyph-red: #ff3333;
            
            /* Dark Fill Colors */
            --sk-fill: #000000;
            --sk-fill-secondary: #1a1a1a;
            --sk-fill-tertiary: #2d2d2d;
            --sk-fill-gray: #f5f5f7;
            --sk-fill-gray-alpha: rgba(255, 255, 255, 0.88);
            --sk-fill-gray-secondary: #86868b;
            --sk-fill-gray-secondary-alpha: rgba(255, 255, 255, 0.48);
            --sk-fill-gray-tertiary: #424245;
            --sk-fill-gray-tertiary-alpha: rgba(255, 255, 255, 0.16);
            --sk-fill-gray-quaternary: #2d2d2d;
            --sk-fill-gray-quaternary-alpha: rgba(255, 255, 255, 0.08);
            --sk-fill-blue: #0071e3;
            --sk-fill-orange: #f56300;
            --sk-fill-orange-secondary: #1a0f00;
            --sk-fill-green: #00ff00;
            --sk-fill-green-secondary: #001a00;
            --sk-fill-red: #ff3333;
            --sk-fill-red-secondary: #1a0000;
            --sk-fill-yellow: #ffe045;
            --sk-fill-yellow-secondary: #1a1a00;
            --sk-productred: #af1e2d;
            --sk-enviro-green: #00d959;
            --sk-enviro-neutral: #2d2d2d;
            
            /* Typography System */
            --sk-body-text-color: #ffffff;
            --sk-headline-text-color: #ffffff;
            --sk-body-background-color: #000000;
            --sk-body-font-stack: SF Pro Text, SF Pro Icons, Helvetica Neue, Helvetica, Arial, sans-serif;
            --sk-default-stacked-margin: 0.4em;
            --sk-paragraph-plus-element-margin: 0.8em;
            --sk-headline-plus-first-element-margin: 0.8em;
            --sk-headline-plus-headline-margin: 0.4em;
            --sk-paragraph-plus-headline-margin: 1.6em;
            
            /* Footnote System */
            --sk-footnote-font-size: 0.6em;
            --sk-footnote-offset-top: -0.5em;
            
            /* Navigation Backgrounds */
            --r-globalnav-background: rgba(0, 0, 0, 0.9);
            --r-globalnav-background-opened: #1a1a1a;
            --r-globalnav-background-opened-dark: #161617;
            
            /* Links */
            --sk-body-link-color: #00ff00;
            --sk-link-disabled-opacity: 0.42;
            
            /* Spacing System */
            --sk-spacing-xs: 4px;
            --sk-spacing-sm: 8px;
            --sk-spacing-md: 16px;
            --sk-spacing-lg: 24px;
            --sk-spacing-xl: 32px;
            --sk-spacing-xxl: 48px;
            --sk-spacing-xxxl: 64px;
        }

        /* Responsive Navigation Heights */
        @media only screen and (max-width: 833px) {
            :root {
                --r-globalnav-height: 48px;
                --r-localnav-height: calc(48px * var(--r-localnav-text-zoom-factor));
                --r-localnav-stacked-height: calc(63px * var(--r-localnav-text-zoom-factor));
                --r-localnav-gn-height: calc(var(--r-globalnav-height, 48px) * var(--r-localnav-text-zoom-factor));
            }
        }

        /* Ribbon Support */
        :root:has(.ribbon) {
            --ribbon-height: 52px;
        }

        html:not([dir=rtl]) {
            --r-sk-start: left;
            --r-sk-end: right;
            --r-sk-safe-area-inset-start: env(safe-area-inset-left);
            --r-sk-safe-area-inset-end: env(safe-area-inset-right);
            --r-sk-logical-factor: 1;
        }

        /* Apple Reset System */
        abbr, blockquote, body, button, dd, dl, dt, fieldset, figure, form, h1, h2, h3, h4, h5, h6, hgroup, input, legend, li, ol, p, pre, ul {
            margin: 0;
            padding: 0;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            margin: 0;
            padding: 0;
        }

        html {
            font-family: var(--sk-body-font-stack);
            font-size: 106.25%;
            quotes: """ """;
            -ms-text-size-adjust: 100%;
            -webkit-text-size-adjust: 100%;
        }

        body {
            min-width: 320px;
            font-size: 17px;
            line-height: 1.4705882353;
            font-weight: 400;
            letter-spacing: -0.022em;
            font-family: var(--sk-body-font-stack);
            background-color: var(--sk-body-background-color);
            color: var(--sk-body-text-color);
            font-style: normal;
            overflow-x: hidden;
        }

        /* Apple Font Rendering */
        body, button, input, select, textarea {
            font-synthesis: none;
            font-feature-settings: "kern";
            -moz-font-feature-settings: "kern";
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
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

        /* Navigation Styles */
        .nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: var(--r-globalnav-background);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--sk-glyph-green);
            z-index: 1000;
            padding: 0 max(var(--sk-spacing-md), env(safe-area-inset-left));
            transition: all 0.3s cubic-bezier(0.4, 0, 0.6, 1);
            height: var(--r-globalnav-height);
        }

        .nav-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: 100%;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.41176rem;
            font-weight: 600;
            color: var(--sk-glyph);
            text-decoration: none;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.6, 1);
            letter-spacing: -0.022em;
        }

        .logo:hover {
            transform: scale(1.02);
            color: var(--sk-glyph-green);
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            margin-right: var(--sk-spacing-md);
            background: linear-gradient(135deg, var(--sk-fill-green), var(--sk-glyph-green));
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--sk-fill);
            font-weight: 600;
            font-size: 1.17647rem;
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
            gap: var(--sk-spacing-xl);
        }

        .nav-links a {
            color: var(--sk-glyph-gray-secondary);
            text-decoration: none;
            font-size: 0.94118rem;
            font-weight: 400;
            letter-spacing: -0.022em;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.6, 1);
            position: relative;
            padding: var(--sk-spacing-sm) 0;
        }

        .nav-links a:hover {
            color: var(--sk-glyph);
            transform: translateY(-1px);
        }

        .nav-links a:focus {
            outline: var(--sk-focus-offset) solid var(--sk-focus-color);
            outline-offset: var(--sk-focus-offset-container);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 1px;
            background: var(--sk-glyph-green);
            transition: width 0.3s cubic-bezier(0.4, 0, 0.6, 1);
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
            padding: calc(var(--r-globalnav-height) + 80px) 0 100px;
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
            padding: 0 var(--sk-spacing-lg);
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
            font-size: 4.23529rem;
            font-weight: 600;
            line-height: 1.05;
            letter-spacing: -0.015em;
            margin-bottom: var(--sk-headline-plus-first-element-margin);
            background: linear-gradient(135deg, var(--sk-glyph), var(--sk-glyph-green));
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            color: var(--sk-headline-text-color);
            animation: textGlow 3s ease-in-out infinite alternate;
        }

        @keyframes textGlow {
            from { filter: drop-shadow(0 0 10px rgba(0, 255, 0, 0.3)); }
            to { filter: drop-shadow(0 0 20px rgba(0, 255, 0, 0.6)); }
        }

        .hero p {
            font-size: 1.41176rem;
            font-weight: 400;
            line-height: 1.381;
            letter-spacing: -0.022em;
            color: var(--sk-glyph-gray-secondary);
            margin-bottom: var(--sk-paragraph-plus-element-margin);
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .cta-buttons {
            display: flex;
            gap: var(--sk-spacing-lg);
            justify-content: center;
            flex-wrap: wrap;
            margin-top: var(--sk-paragraph-plus-element-margin);
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        /* Buttons - Apple Style */
        .btn-primary {
            background: var(--sk-fill-green);
            color: var(--sk-fill);
            padding: 12px 24px;
            border-radius: 980px;
            text-decoration: none;
            font-size: 1.05882rem;
            font-weight: 400;
            letter-spacing: -0.022em;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.6, 1);
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 16px rgba(0, 255, 0, 0.2);
            position: relative;
            overflow: hidden;
            min-width: 120px;
            text-align: center;
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
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(0, 255, 0, 0.3);
            background: var(--sk-glyph-green);
        }

        .btn-primary:focus {
            outline: var(--sk-focus-offset) solid var(--sk-focus-color);
            outline-offset: var(--sk-focus-offset-container);
        }

        .btn-secondary {
            background: transparent;
            color: var(--sk-glyph-green);
            padding: 12px 24px;
            border: 1px solid var(--sk-glyph-green);
            border-radius: 980px;
            text-decoration: none;
            font-size: 1.05882rem;
            font-weight: 400;
            letter-spacing: -0.022em;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.6, 1);
            position: relative;
            overflow: hidden;
            min-width: 120px;
            text-align: center;
        }

        .btn-secondary::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--sk-glyph-green);
            transition: width 0.3s cubic-bezier(0.4, 0, 0.6, 1);
            z-index: -1;
        }

        .btn-secondary:hover::before {
            width: 100%;
        }

        .btn-secondary:hover {
            color: var(--sk-fill);
            transform: translateY(-2px);
        }

        /* Features Section */
        .features {
            padding: 100px 0;
            position: relative;
        }

        .features-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--sk-spacing-lg);
        }

        .section-header {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-header h2 {
            font-size: 3.29412rem;
            font-weight: 600;
            line-height: 1.08;
            letter-spacing: -0.015em;
            margin-bottom: var(--sk-headline-plus-first-element-margin);
            color: var(--sk-headline-text-color);
            animation: slideInFromLeft 1s ease-out;
        }

        .section-header p {
            font-size: 1.17647rem;
            font-weight: 400;
            line-height: 1.4;
            letter-spacing: -0.022em;
            color: var(--sk-glyph-gray-secondary);
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
            background: var(--sk-fill-secondary);
            border: 1px solid var(--sk-fill-gray-tertiary);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.6, 1);
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
            border-color: var(--sk-glyph-green);
            box-shadow: 0 20px 40px rgba(0, 255, 0, 0.2);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--sk-fill-green), var(--sk-glyph-green));
            border-radius: 20px;
            margin: 0 auto 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 36px;
            color: var(--sk-fill);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        .feature-card h3 {
            font-size: 1.41176rem;
            font-weight: 600;
            line-height: 1.21;
            letter-spacing: -0.022em;
            margin-bottom: var(--sk-spacing-md);
            color: var(--sk-headline-text-color);
        }

        .feature-card p {
            font-size: 1rem;
            font-weight: 400;
            line-height: 1.47059;
            letter-spacing: -0.022em;
            color: var(--sk-glyph-gray-secondary);
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
            background: var(--sk-fill-secondary);
            margin: 5% auto;
            padding: 40px;
            border: 1px solid var(--sk-glyph-green);
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
            color: var(--sk-glyph-gray-secondary);
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close:hover {
            color: var(--sk-glyph-green);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--sk-body-text-color);
            font-weight: 500;
        }

        .form-group input {
            width: 100%;
            padding: 12px 16px;
            background: var(--sk-fill);
            border: 1px solid var(--sk-fill-gray-tertiary);
            border-radius: 10px;
            color: var(--sk-body-text-color);
            font-size: 16px;
            transition: all 0.3s ease;
        }

        .form-group input:focus {
            outline: none;
            border-color: var(--sk-glyph-green);
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.3);
        }

        /* Footer */
        .footer {
            background: var(--sk-fill-secondary);
            color: var(--sk-body-text-color);
            padding: 80px 0 40px;
            border-top: 1px solid var(--sk-fill-gray-tertiary);
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--sk-spacing-lg);
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h4 {
            font-size: 1.17647rem;
            font-weight: 600;
            margin-bottom: var(--sk-spacing-lg);
            color: var(--sk-glyph-green);
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section li {
            margin-bottom: 12px;
        }

        .footer-section a {
            color: var(--sk-glyph-gray-secondary);
            text-decoration: none;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .footer-section a:hover {
            color: var(--sk-glyph-green);
            transform: translateX(5px);
        }

        .footer-bottom {
            border-top: 1px solid var(--sk-fill-gray-tertiary);
            padding-top: var(--sk-spacing-xl);
            text-align: center;
            color: var(--sk-glyph-gray-secondary);
            font-size: 0.94118rem;
            letter-spacing: -0.022em;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.35294rem;
            }
            
            .hero p {
                font-size: 1.17647rem;
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
            
            .section-header h2 {
                font-size: 2.35294rem;
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
                    <p>Create professional
                        <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M.A.R.K - Professional Email Platform</title>
    <style>
        :root {
            --r-globalnav-height: 44px;
            --sk-focus-color: #00ff00;
            --sk-glyph: #ffffff;
            --sk-glyph-gray-secondary: #86868b;
            --sk-glyph-green: #00ff00;
            --sk-fill: #000000;
            --sk-fill-secondary: #1a1a1a;
            --sk-fill-tertiary: #2d2d2d;
            --sk-fill-gray-tertiary: #424245;
            --sk-fill-green: #00ff00;
            --sk-body-text-color: #ffffff;
            --sk-headline-text-color: #ffffff;
            --sk-body-background-color: #000000;
            --sk-body-font-stack: SF Pro Text, SF Pro Icons, Helvetica Neue, Helvetica, Arial, sans-serif;
            --sk-spacing-sm: 8px;
            --sk-spacing-md: 16px;
            --sk-spacing-lg: 24px;
            --sk-spacing-xl: 32px;
        }

        @media (max-width: 833px) {
            :root { --r-globalnav-height: 48px; }
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            min-width: 320px;
            font-size: 17px;
            line-height: 1.4705882353;
            font-weight: 400;
            letter-spacing: -0.022em;
            font-family: var(--sk-body-font-stack);
            background-color: var(--sk-body-background-color);
            color: var(--sk-body-text-color);
            overflow-x: hidden;
            font-synthesis: none;
            -webkit-font-smoothing: antialiased;
        }

        .animated-bg {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;
            background: linear-gradient(45deg, #000000, #1a1a1a, #000000);
            background-size: 400% 400%; animation: gradientShift 15s ease infinite;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .particles { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; }
        .particle {
            position: absolute; background: #00ff00; border-radius: 50%; opacity: 0.1;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); }
            100% { transform: translateY(-100vh) rotate(360deg); }
        }

        .nav {
            position: fixed; top: 0; width: 100%; background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(20px); border-bottom: 1px solid var(--sk-glyph-green);
            z-index: 1000; height: var(--r-globalnav-height);
        }

        .nav-content {
            max-width: 1200px; margin: 0 auto; display: flex;
            align-items: center; justify-content: space-between; height: 100%;
            padding: 0 var(--sk-spacing-lg);
        }

        .logo {
            display: flex; align-items: center; font-size: 1.41176rem;
            font-weight: 600; color: var(--sk-glyph); text-decoration: none;
        }

        .logo-icon {
            width: 40px; height: 40px; margin-right: var(--sk-spacing-md);
            background: linear-gradient(135deg, var(--sk-fill-green), #00cc00);
            border-radius: 10px; display: flex; align-items: center; justify-content: center;
            color: var(--sk-fill); font-weight: 600; font-size: 1.17647rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 20px rgba(0, 255, 0, 0.3); }
            50% { box-shadow: 0 0 30px rgba(0, 255, 0, 0.6); }
        }

        .nav-links {
            display: flex; list-style: none; gap: var(--sk-spacing-xl);
        }

        .nav-links a {
            color: var(--sk-glyph-gray-secondary); text-decoration: none;
            font-size: 0.94118rem; transition: all 0.3s ease;
        }

        .nav-links a:hover { color: var(--sk-glyph); }

        .mobile-menu { display: none; flex-direction: column; cursor: pointer; }
        .mobile-menu span { width: 25px; height: 3px; background: #ffffff; margin: 3px 0; }

        .hero {
            padding: calc(var(--r-globalnav-height) + 80px) 0 100px;
            text-align: center; min-height: 100vh; display: flex;
            align-items: center; justify-content: center;
        }

        .hero-content { max-width: 1200px; margin: 0 auto; padding: 0 var(--sk-spacing-lg); }

        .hero h1 {
            font-size: 4.23529rem; font-weight: 600; line-height: 1.05;
            letter-spacing: -0.015em; margin-bottom: 0.8em;
            background: linear-gradient(135deg, var(--sk-glyph), var(--sk-glyph-green));
            background-clip: text; -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.41176rem; line-height: 1.381; letter-spacing: -0.022em;
            color: var(--sk-glyph-gray-secondary); margin-bottom: 0.8em;
            max-width: 700px; margin-left: auto; margin-right: auto;
        }

        .cta-buttons { display: flex; gap: var(--sk-spacing-lg); justify-content: center; flex-wrap: wrap; }

        .btn-primary {
            background: var(--sk-fill-green); color: var(--sk-fill);
            padding: 12px 24px; border-radius: 980px; text-decoration: none;
            font-size: 1.05882rem; transition: all 0.3s ease; border: none;
            cursor: pointer; min-width: 120px;
        }

        .btn-primary:hover { transform: translateY(-2px); }

        .btn-secondary {
            background: transparent; color: var(--sk-glyph-green);
            padding: 12px 24px; border: 1px solid var(--sk-glyph-green);
            border-radius: 980px; text-decoration: none; font-size: 1.05882rem;
            transition: all 0.3s ease; min-width: 120px;
        }

        .btn-secondary:hover { background: var(--sk-glyph-green); color: var(--sk-fill); }

        .features { padding: 100px 0; }
        .features-content { max-width: 1200px; margin: 0 auto; padding: 0 var(--sk-spacing-lg); }
        .section-header { text-align: center; margin-bottom: 80px; }

        .section-header h2 {
            font-size: 3.29412rem; font-weight: 600; line-height: 1.08;
            margin-bottom: 0.8em; color: var(--sk-headline-text-color);
        }

        .section-header p {
            font-size: 1.17647rem; color: var(--sk-glyph-gray-secondary);
            max-width: 700px; margin: 0 auto;
        }

        .features-grid {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px; margin-top: 60px;
        }

        .feature-card {
            background: var(--sk-fill-secondary); border: 1px solid var(--sk-fill-gray-tertiary);
            border-radius: 20px; padding: 40px; text-align: center;
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-10px); border-color: var(--sk-glyph-green);
            box-shadow: 0 20px 40px rgba(0, 255, 0, 0.2);
        }

        .feature-icon {
            width: 80px; height: 80px; background: linear-gradient(135deg, var(--sk-fill-green), #00cc00);
            border-radius: 20px; margin: 0 auto 30px; display: flex;
            align-items: center; justify-content: center; font-size: 36px; color: var(--sk-fill);
        }

        .feature-card h3 {
            font-size: 1.41176rem; font-weight: 600; margin-bottom: var(--sk-spacing-md);
            color: var(--sk-headline-text-color);
        }

        .feature-card p { color: var(--sk-glyph-gray-secondary); }

        .modal {
            display: none; position: fixed; z-index: 2000; left: 0; top: 0;
            width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.8);
        }

        .modal-content {
            background: var(--sk-fill-secondary); margin: 5% auto; padding: 40px;
            border: 1px solid var(--sk-glyph-green); border-radius: 20px;
            width: 90%; max-width: 500px;
        }

        .close { color: #cccccc; float: right; font-size: 28px; cursor: pointer; }
        .close:hover { color: var(--sk-glyph-green); }

        .form-group { margin-bottom: 20px; }
        .form-group label { display: block; margin-bottom: 8px; color: var(--sk-body-text-color); }
        .form-group input {
            width: 100%; padding: 12px 16px; background: var(--sk-fill);
            border: 1px solid var(--sk-fill-gray-tertiary); border-radius: 10px;
            color: var(--sk-body-text-color);
        }

        .footer {
            background: var(--sk-fill-secondary); padding: 80px 0 40px;
            border-top: 1px solid var(--sk-fill-gray-tertiary);
        }

        .footer-content { max-width: 1200px; margin: 0 auto; padding: 0 var(--sk-spacing-lg); }
        .footer-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 40px; }
        .footer-section h4 { color: var(--sk-glyph-green); margin-bottom: var(--sk-spacing-lg); }
        .footer-section ul { list-style: none; }
        .footer-section a { color: var(--sk-glyph-gray-secondary); text-decoration: none; }
        .footer-section a:hover { color: var(--sk-glyph-green); }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.35294rem; }
            .nav-links { display: none; }
            .mobile-menu { display: flex; }
            .features-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div class="animated-bg"></div>
    <div class="particles" id="particles"></div>

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
            <div class="mobile-menu">
                <span></span><span></span><span></span>
            </div>
        </div>
    </nav>

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
            </div>
        </div>
    </section>

    <div id="loginModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('loginModal')">&times;</span>
            <h2 style="color: #00ff00; margin-bottom: 30px; text-align: center;">Login to M.A.R.K</h2>
            <form>
                <div class="form-group">
                    <label>Email Address</label>
                    <input type="email" placeholder="your.name@mark.com" required>
                </div>
                <div class="form-group">
                    <label>Password</label>
                    <input type="password" placeholder="Enter your password" required>
                </div>
                <button type="submit" class="btn-primary" style="width: 100%;">Login</button>
            </form>
        </div>
    </div>

    <footer class="footer">
        <div class="footer-content">
            <div class="footer-grid">
                <div class="footer-section">
                    <h4>Platform</h4>
                    <ul>
                        <li><a href="#">Email Features</a></li>
                        <li><a href="#">Security Center</a></li>
                        <li><a href="#">API Documentation</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Support</h4>
                    <ul>
                        <li><a href="#">Help Center</a></li>
                        <li><a href="#">Contact Support</a></li>
                        <li><a href="#">System Status</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>

    <script>
        function createParticles() {
            const container = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.width = Math.random() * 4 + 2 + 'px';
                particle.style.height = particle.style.width;
                particle.style.animationDelay = Math.random() * 20 + 's';
                container.appendChild(particle);
            }
        }

        function openModal(id) {
            document.getElementById(id).style.display = 'block';
        }

        function closeModal(id) {
            document.getElementById(id).style.display = 'none';
        }

        window.onclick = function(event) {
            if (event.target.classList.contains('modal')) {
                event.target.style.display = 'none';
            }
        }

        document.addEventListener('DOMContentLoaded', createParticles);
    </script>
</body>
</html>
