<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quality Time - Verbinde dich wieder mit deiner Familie</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        :root {
            --primary-color: #007AFF;
            --secondary-color: #5856D6;
            --accent-color: #FF3B30;
            --soft-green: #34C759;
            --soft-orange: #FF9500;
            --text-dark: #F2F2F7;
            --text-light: #8E8E93;
            --white: #000000;
            --card-bg: #1C1C1E;
            --dark-bg: #000000;
            --section-padding: 120px 0;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            overflow-x: hidden;
            background: var(--dark-bg);
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 40px;
        }
        /* Animated Color Island */
        .color-island {
            position: absolute;
            width: 400px;
            height: 300px;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color), var(--accent-color));
            border-radius: 40px;
            opacity: 0.3;
            animation: float 6s ease-in-out infinite;
            z-index: -1;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
        /* Phone Intro Section */
        .phone-intro {
            height: 500vh;
            position: relative;
            background: var(--dark-bg);
            display: flex;
            align-items: flex-start;
            justify-content: center;
            padding-top: 10vh;
        }
        .phone-container {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 100;
            transition: opacity 0.8s ease, transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .phone-frame {
            width: 320px;
            height: 640px;
            background: linear-gradient(135deg, #1a1a1a, #2a2a2a);
            border-radius: 40px;
            padding: 8px;
            position: relative;
            box-shadow: 0 20px 60px rgba(0,0,0,0.5);
        }
        .phone-screen {
            width: 100%;
            height: 100%;
            background: var(--dark-bg);
            border-radius: 32px;
            overflow: hidden;
            position: relative;
        }
        .color-panel {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 65%;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            transition: all 0.8s ease;
            border-radius: 0 0 23px 23px;
        }
        .phone-text {
            color: white;
            font-size: 1.4rem;
            font-weight: 600;
            text-align: center;
            padding: 2rem;
            opacity: 1;
            transition: all 0.6s ease;
        }
        .phone-text.fade-out {
            opacity: 0;
            transform: translateY(-30px);
        }
        .phone-text.fade-in {
            opacity: 1;
            transform: translateY(0);
            animation: slideIn 0.8s ease-out;
        }
        @keyframes slideIn {
            0% { 
                opacity: 0; 
                transform: translateY(30px);
            }
            100% { 
                opacity: 1; 
                transform: translateY(0);
            }
        }
        /* Hero Phone (Phone 2) */
        .hero-phone-container {
            width: 320px;
            height: 640px;
            background: linear-gradient(135deg, #1a1a1a, #2a2a2a);
            border-radius: 40px;
            padding: 8px;
            position: relative;
            box-shadow: 0 20px 60px rgba(0,0,0,0.5);
            margin: 0 auto;
        }
        .hero-phone-screen {
            width: 100%;
            height: 100%;
            background: var(--dark-bg);
            border-radius: 32px;
            overflow: hidden;
            position: relative;
        }
        .hero-color-panel {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 70%;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            transition: all 0.8s ease;
            border-radius: 0 0 23px 23px;
        }
        .hero-phone-text {
            color: white;
            font-size: 1.4rem;
            font-weight: 600;
            text-align: center;
            padding: 2rem;
            opacity: 1;
            transition: all 0.5s ease;
        }
        .plus-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            opacity: 1;
            transition: all 0.5s ease;
        }
        .focus-text {
            font-size: 1.1rem;
            font-weight: 500;
            opacity: 1;
            transition: all 0.5s ease;
        }
        .qr-button {
            position: absolute;
            bottom: 12%;
            left: 50%;
            transform: translateX(-50%);
            padding: 16px 32px;
            background: rgba(0, 122, 255, 0.15);
            border: 2px solid rgba(0, 122, 255, 0.3);
            border-radius: 16px;
            color: rgba(0, 122, 255, 0.9);
            font-size: 1rem;
            font-weight: 600;
            opacity: 1;
            transition: all 0.5s ease;
            white-space: nowrap;
            min-width: 180px;
            cursor: pointer;
        }
        .focus-button {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 0;
            background: none;
            border: none;
            color: white;
            cursor: pointer;
            text-align: center;
            transition: all 0.3s ease;
        }
        .focus-button:hover {
            transform: translate(-50%, -50%) scale(1.05);
        }
        .feature-text {
            color: white;
            font-size: 1.1rem;
            font-weight: 500;
            text-align: center;
            padding: 2rem;
            opacity: 0;
            transition: all 0.5s ease;
            line-height: 1.4;
        }
        .done-button {
            position: absolute;
            top: 20px;
            right: 20px;
            padding: 8px 16px;
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 20px;
            color: white;
            font-size: 0.9rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            opacity: 0;
            z-index: 10;
        }
        .done-button:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            background: linear-gradient(135deg, rgba(0, 122, 255, 0.05), rgba(88, 86, 214, 0.05));
            padding: 80px 0;
        }
        .hero .color-island {
            right: 10%;
            top: 20%;
        }
        .hero-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
            width: 100%;
            position: relative;
        }
        .hero-text {
            z-index: 1;
            position: relative;
            padding: 2rem;
            background: rgba(0, 0, 0, 0.02);
            border-radius: 20px;
            backdrop-filter: blur(10px);
        }
        .hero-text h1 {
            font-size: 4rem;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 2rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: textGlow 3s ease-in-out infinite alternate;
        }
        @keyframes textGlow {
            0% { filter: brightness(1); }
            100% { filter: brightness(1.1); }
        }
        .hero-text p {
            font-size: 1.5rem;
            color: var(--text-light);
            font-weight: 300;
        }
        .phone-mockup {
            text-align: center;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            padding-top: 2rem;
            z-index: 2;
        }
        .phone-mockup img {
            max-width: 300px;
            height: auto;
            filter: drop-shadow(0 20px 40px rgba(0,0,0,0.1));
        }
        /* Features Section */
        .features {
            padding: var(--section-padding);
            position: relative;
        }
        .features .color-island {
            left: 5%;
            top: 30%;
            width: 300px;
            height: 200px;
        }
        .features h2 {
            text-align: center;
            font-size: 3rem;
            font-weight: 600;
            margin-bottom: 4rem;
            color: var(--text-dark);
        }
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 3rem;
        }
        .feature-card {
            background: var(--card-bg);
            padding: 3rem;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0,0,0,0.25);
            border: 0.5px solid rgba(142, 142, 147, 0.1);
            transition: transform 0.3s ease, opacity 0.6s ease;
            opacity: 0;
            transform: translateY(30px);
        }
        .feature-card.visible {
            opacity: 1;
            transform: translateY(0);
        }
        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.4);
        }
        .feature-icon {
            width: 80px;
            height: 80px;
            margin: 0 auto 2rem;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            margin-bottom: 2rem;
        }
        .feature-card:nth-child(1) .feature-icon {
            background: var(--accent-color);
            color: white;
        }
        .feature-card:nth-child(2) .feature-icon {
            background: var(--primary-color);
            color: white;
        }
        .feature-card:nth-child(3) .feature-icon {
            background: var(--secondary-color);
            color: white;
        }
        .feature-card:nth-child(4) .feature-icon {
            background: var(--soft-green);
            color: white;
        }
        .feature-card h3 {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }
        .feature-card p {
            color: var(--text-light);
            font-size: 1.1rem;
        }
        /* Onboarding Section */
        .onboarding {
            padding: var(--section-padding);
            background: linear-gradient(135deg, rgba(88, 86, 214, 0.05), rgba(52, 199, 89, 0.05));
            position: relative;
        }
        .onboarding .color-island {
            right: 15%;
            top: 10%;
            width: 350px;
            height: 250px;
        }
        .onboarding h2 {
            text-align: center;
            font-size: 3rem;
            font-weight: 600;
            margin-bottom: 3rem;
        }
        .onboarding-steps {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 3rem;
            margin-bottom: 3rem;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }
        .step-card {
            background: var(--card-bg);
            padding: 2.5rem;
            border-radius: 16px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.25);
            border: 0.5px solid rgba(142, 142, 147, 0.1);
            transition: transform 0.3s ease, opacity 0.6s ease;
            opacity: 0;
            transform: translateY(20px);
            max-width: 400px;
            width: 100%;
            position: relative;
        }
        
        .step-card:nth-child(1) {
            align-self: flex-start;
            margin-left: 10%;
        }
        
        .step-card:nth-child(2) {
            align-self: flex-end;
            margin-right: 10%;
        }
        
        .step-card:nth-child(3) {
            align-self: flex-start;
            margin-left: 5%;
        }
        .step-card.visible {
            opacity: 1;
            transform: translateY(0);
        }
        .step-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.35);
        }
        .step-number {
            display: inline-block;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--primary-color);
            color: white;
            text-align: center;
            line-height: 40px;
            font-weight: 600;
            margin-bottom: 1.5rem;
        }
        .step-card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
        }
        .step-card p {
            color: var(--text-light);
        }
        .name-input-demo {
            text-align: center;
            padding: 2rem;
            background: var(--card-bg);
            border-radius: 16px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.25);
            border: 0.5px solid rgba(142, 142, 147, 0.1);
            margin-top: 2rem;
        }
        .demo-input {
            padding: 1rem 1.5rem;
            border: 1px solid rgba(142, 142, 147, 0.3);
            border-radius: 12px;
            font-size: 1.1rem;
            margin: 1rem;
            min-width: 250px;
            background: var(--dark-bg);
            color: var(--text-dark);
            transition: border-color 0.3s ease;
        }
        .demo-input:focus {
            outline: none;
            border-color: var(--primary-color);
        }
        /* CTA Section */
        .cta {
            padding: var(--section-padding);
            text-align: center;
            background: var(--white);
        }
        .cta h2 {
            font-size: 3rem;
            font-weight: 600;
            margin-bottom: 2rem;
        }
        .cta p {
            font-size: 1.3rem;
            color: var(--text-light);
            margin-bottom: 3rem;
        }
        .app-buttons {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-bottom: 3rem;
        }
        .app-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            text-decoration: none;
            border-radius: 16px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .app-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }
        
        /* Support buttons */
        .support-buttons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }
        .support-button {
            display: inline-block;
            padding: 0.8rem 1.8rem;
            background: var(--card-bg);
            color: var(--text-dark);
            text-decoration: none;
            border-radius: 12px;
            border: 1px solid rgba(142, 142, 147, 0.3);
            font-weight: 500;
            font-size: 0.95rem;
            transition: all 0.3s ease;
        }
        .support-button:hover {
            background: rgba(142, 142, 147, 0.1);
            border-color: var(--primary-color);
            color: var(--primary-color);
        }
        /* Feedback Section */
        .feedback {
            padding: 80px 0;
            background: linear-gradient(135deg, rgba(0, 122, 255, 0.05), rgba(88, 86, 214, 0.05));
            text-align: center;
        }
        .feedback h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }
        .feedback p {
            font-size: 1.2rem;
            color: var(--text-light);
            margin-bottom: 2rem;
        }
        .feedback-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: var(--card-bg);
            color: var(--text-dark);
            text-decoration: none;
            border-radius: 12px;
            border: 1px solid var(--primary-color);
            font-weight: 500;
            transition: all 0.3s ease;
        }
        .feedback-button:hover {
            background: var(--primary-color);
            color: white;
        }
        
        /* Enhanced Mobile Optimizations */
        @media (max-width: 480px) {
            .container {
                padding: 0 15px;
            }
            
            /* Phone intro optimizations */
            .phone-intro {
                height: 300vh; /* Reduced height for mobile */
            }
            
            .phone-frame, .hero-phone-container {
                width: 250px;
                height: 500px;
            }
            
            .phone-text, .hero-phone-text {
                font-size: 1rem;
                padding: 1.5rem;
                line-height: 1.4;
            }
            
            .plus-icon {
                font-size: 1.5rem;
                margin-bottom: 0.3rem;
            }
            
            .focus-text {
                font-size: 0.9rem;
            }
            
            .qr-button {
                padding: 12px 24px;
                font-size: 0.9rem;
                min-width: 150px;
            }
            
            /* Hero section mobile */
            .hero {
                min-height: 80vh;
                padding: 40px 0;
            }
            
            .hero-content {
                grid-template-columns: 1fr;
                gap: 2rem;
                text-align: center;
            }
            
            .hero-text {
                padding: 1.5rem;
                margin: 0;
                order: 2;
            }
            
            .hero-text h1 {
                font-size: 2rem;
                margin-bottom: 1rem;
                line-height: 1.2;
            }
            
            .hero-text p {
                font-size: 1rem;
                line-height: 1.5;
            }
            
            .phone-mockup {
                order: 1;
                padding-top: 1rem;
            }
            
            /* Features mobile */
            .features {
                padding: 60px 0;
            }
            
            .features h2 {
                font-size: 1.8rem;
                margin-bottom: 2rem;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }
            
            .feature-card {
                padding: 2rem 1.5rem;
            }
            
            .feature-icon {
                width: 60px;
                height: 60px;
                font-size: 1.5rem;
                margin-bottom: 1rem;
            }
            
            .feature-card h3 {
                font-size: 1.2rem;
                margin-bottom: 0.8rem;
            }
            
            .feature-card p {
                font-size: 1rem;
                line-height: 1.5;
            }
            
            /* Onboarding mobile */
            .onboarding {
                padding: 60px 0;
            }
            
            .onboarding h2 {
                font-size: 1.8rem;
                margin-bottom: 2rem;
            }
            
            .onboarding-steps {
                gap: 2rem;
            }
            
            .step-card {
                max-width: none;
                margin-left: 0 !important;
                margin-right: 0 !important;
                align-self: center !important;
            }
            
            .support-buttons {
                flex-direction: column;
                align-items: center;
                gap: 1rem;
            }
            
            .step-card {
                padding: 2rem 1.5rem;
            }
            
            .step-number {
                width: 35px;
                height: 35px;
                line-height: 35px;
                font-size: 0.9rem;
                margin-bottom: 1rem;
            }
            
            .step-card h3 {
                font-size: 1.1rem;
                margin-bottom: 0.8rem;
            }
            
            .step-card p {
                font-size: 0.95rem;
                line-height: 1.5;
            }
            
            /* CTA mobile */
            .cta {
                padding: 60px 0;
            }
            
            .cta h2 {
                font-size: 1.8rem;
                margin-bottom: 1rem;
                line-height: 1.2;
            }
            
            .cta p {
                font-size: 1rem;
                margin-bottom: 2rem;
                line-height: 1.5;
            }
            
            .app-button {
                padding: 1rem 2rem;
                font-size: 1rem;
                width: 100%;
                max-width: 300px;
            }
            
            /* Feedback mobile */
            .feedback {
                padding: 60px 0;
            }
            
            .feedback h2 {
                font-size: 1.8rem;
                margin-bottom: 1rem;
            }
            
            .feedback p {
                font-size: 1rem;
                margin-bottom: 1.5rem;
                line-height: 1.5;
            }
            
            .feedback-button {
                padding: 1rem 1.5rem;
                font-size: 1rem;
                width: 100%;
                max-width: 300px;
            }
            
            .support-button {
                padding: 0.8rem 1.2rem;
                font-size: 0.9rem;
                width: 100%;
                max-width: 280px;
                text-align: center;
            }
            
            /* Color islands mobile */
            .color-island {
                width: 200px;
                height: 150px;
                opacity: 0.2;
            }
            
            /* Demo input mobile */
            .demo-input {
                min-width: auto;
                width: 100%;
                max-width: 280px;
                font-size: 1rem;
                padding: 0.8rem 1rem;
            }
            
            /* Touch optimization */
            .focus-button, .qr-button, .done-button, .app-button, .feedback-button {
                min-height: 44px; /* iOS recommended touch target */
            }
        }
        
        @media (max-width: 768px) and (min-width: 481px) {
            .container {
                padding: 0 25px;
            }
            
            .phone-frame, .hero-phone-container {
                width: 280px;
                height: 560px;
            }
            
            .phone-text, .hero-phone-text {
                font-size: 1.2rem;
                padding: 1.8rem;
            }
            
            .hero-content {
                grid-template-columns: 1fr;
                gap: 3rem;
                text-align: center;
            }
            
            .hero-text h1 {
                font-size: 2.8rem;
                line-height: 1.1;
            }
            
            .hero-text p {
                font-size: 1.2rem;
            }
            
            .features h2,
            .onboarding h2,
            .cta h2 {
                font-size: 2.2rem;
            }
            
            .features-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
                gap: 2rem;
            }
            
            .step-card {
                max-width: none;
                margin-left: 0 !important;
                margin-right: 0 !important;
                align-self: center !important;
            }
            
            .color-island {
                width: 250px;
                height: 180px;
            }
        }
        
        /* Large tablet optimization */
        @media (max-width: 1024px) and (min-width: 769px) {
            .hero-content {
                gap: 4rem;
            }
            
            .hero-text h1 {
                font-size: 3.2rem;
            }
            
            .hero-text p {
                font-size: 1.3rem;
            }
            
            .features-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 2.5rem;
            }
            
            .step-card {
                max-width: none;
                margin-left: 0 !important;
                margin-right: 0 !important;
                align-self: center !important;
            }
        }
        
        /* Landscape phone optimization */
        @media (max-height: 500px) and (orientation: landscape) {
            .phone-intro {
                height: 200vh;
            }
            
            .hero {
                min-height: 70vh;
                padding: 30px 0;
            }
            
            .hero-text h1 {
                font-size: 2rem;
                margin-bottom: 1rem;
            }
            
            .hero-text p {
                font-size: 1rem;
            }
            
            .features,
            .onboarding,
            .cta {
                padding: 40px 0;
            }
        }
        
        /* Smooth scrolling animations */
        .scroll-animation {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }
        .scroll-animation.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Performance optimizations for mobile */
        @media (max-width: 768px) {
            .color-island {
                animation-duration: 8s; /* Slower animation on mobile for better performance */
            }
            
            /* Reduce parallax effect on mobile for better performance */
            .hero .color-island,
            .features .color-island,
            .onboarding .color-island {
                transform: none !important;
            }
        }
    </style>
</head>
<body>
    <!-- Phone Intro Section (Phone 1) -->
    <section class="phone-intro">
        <div class="phone-container" id="phone1">
            <div class="phone-frame">
                <div class="phone-screen">
                    <div class="color-panel">
                        <div class="phone-text" id="phoneText1">
                            Hallo, willkommen bei<br>Quality Time
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="color-island"></div>
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Quality Time mit den Menschen, die dir wichtig sind</h1>
                    <p>Echte Verbindungen entstehen, wenn wir unsere Handys weglegen und uns voll aufeinander konzentrieren.</p>
                </div>
                <div class="phone-mockup">
                    <!-- Phone 2 - Hero Phone -->
                    <div class="hero-phone-container" id="phone2">
                        <div class="hero-phone-screen">
                            <div class="hero-color-panel">
                                <div class="hero-phone-text" id="phoneText2">
                                    <button class="focus-button" onclick="showFocusMode()">
                                        <div class="plus-icon">+</div>
                                        <div class="focus-text">Fokuszeit erstellen</div>
                                    </button>
                                </div>
                            </div>
                            <div class="qr-button" onclick="showQRMode()">
                                QR-Code scannen
                            </div>
                            <div class="done-button" onclick="resetHeroPhone()">
                                Fertig
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Features Section -->
    <section class="features">
        <div class="color-island"></div>
        <div class="container">
            <h2 class="scroll-animation">Für echte Momente gemacht</h2>
            <div class="features-grid">
                <div class="feature-card scroll-animation">
                    <div class="feature-icon">📵</div>
                    <h3>Bildschirmfreie Zeit</h3>
                    <p>Schafft bewusste Pausen von der digitalen Welt für tiefere Gespräche und echte Aufmerksamkeit.</p>
                </div>
                <div class="feature-card scroll-animation">
                    <div class="feature-icon">👥</div>
                    <h3>Gemeinsam fokussiert</h3>
                    <p>Ob Familie, Freunde oder Kollegen – alle sind gleichzeitig ablenkungsfrei und voll dabei.</p>
                </div>
                <div class="feature-card scroll-animation">
                    <div class="feature-icon">🧠</div>
                    <h3>Produktive Sessions</h3>
                    <p>Perfekt für Meetings, Brainstorming oder wichtige Gespräche ohne ständige Handy-Unterbrechungen.</p>
                </div>
                <div class="feature-card scroll-animation">
                    <div class="feature-icon">💎</div>
                    <h3>Wertvolle Momente</h3>
                    <p>Verwandelt gewöhnliche Situationen in bedeutungsvolle, ungeteilte Aufmerksamkeit für das was zählt.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Onboarding Section -->
    <section class="onboarding">
        <div class="color-island"></div>
        <div class="container">
            <h2 class="scroll-animation">So einfach startet eine Session</h2>
            <div class="onboarding-steps">
                <div class="step-card scroll-animation">
                    <div class="step-number">1</div>
                    <h3>Session erstellen</h3>
                    <p>Eine Person öffnet Quality Time, wählt die gewünschte Dauer und erstellt einen QR-Code für die Gruppe.</p>
                </div>
                <div class="step-card scroll-animation">
                    <div class="step-number">2</div>
                    <h3>Alle scannen mit</h3>
                    <p>Die anderen Teilnehmer scannen den Code – egal ob Freunde, Familie oder Kollegen.</p>
                </div>
                <div class="step-card scroll-animation">
                    <div class="step-number">3</div>
                    <h3>Ablenkungen verschwinden</h3>
                    <p>Alle störenden Apps werden automatisch blockiert. Jetzt ist Zeit für das, was wirklich wichtig ist.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Call to Action Section -->
    <section class="cta">
        <div class="container">
            <h2 class="scroll-animation">Bereit für echte Verbindungen?</h2>
            <p class="scroll-animation">Lade Quality Time kostenlos im Apple App Store herunter und erlebe, wie wertvoll ungeteilte Aufmerksamkeit sein kann.</p>
            <div class="app-buttons scroll-animation">
                <a href="#" class="app-button">
                    Kostenlos herunterladen
                </a>
            </div>
            <div class="support-buttons scroll-animation">
                <a href="https://forms.gle/iQgfn7wngMr4Trc96" class="support-button" target="_blank">Allgemeine Fragen/Support</a>
                <a href="https://forms.gle/1HAgYpgJcQ5BJDz77" class="support-button" target="_blank">Fragen zum Datenschutz</a>
            </div>
        </div>
    </section>
    
    <!-- Feedback Section -->
    <section class="feedback">
        <div class="container">
            <h2 class="scroll-animation">Eure Ideen sind gefragt</h2>
            <p class="scroll-animation">Habt ihr Wünsche oder Vorschläge für neue Features? Teilt eure Ideen mit uns!</p>
            <a href="https://forms.gle/TTVS5DNdcnTBrTqf7" class="feedback-button scroll-animation" target="_blank">Feature vorschlagen</a>
        </div>
    </section>
    
    <script>
        // Phone 1 (Intro) - text rotation with improved timing and fade-out
        const phoneTexts = [
            "Hallo, willkommen bei<br>Quality Time",
            "Zeit für echte<br>Verbindungen mit<br>deinen Liebsten",
            "Gemeinsame Momente<br>ohne Ablenkungen<br>schaffen",
            "Wertvolle Zeit für<br>echte Begegnungen<br>und tiefe Gespräche"
        ];
        let currentTextIndex = 0;
        let isTransitioning = false;
        
        function updatePhone1Text() {
            const phoneText = document.getElementById('phoneText1');
            const phoneContainer = document.getElementById('phone1');
            const phoneIntroSection = document.querySelector('.phone-intro');
            const scrolled = window.pageYOffset;
            const phoneIntroHeight = phoneIntroSection.offsetHeight;
            
            // Calculate progress through the phone intro section (0 to 1)
            const progress = Math.min(Math.max(scrolled / phoneIntroHeight, 0), 1);
            
            // Determine which text should be shown based on scroll progress
            // Divide the scroll area into 4 equal parts for 4 texts
            const textProgress = progress * phoneTexts.length;
            const newTextIndex = Math.min(Math.floor(textProgress), phoneTexts.length - 1);
            
            // Update text if we've moved to a new section and we're not already transitioning
            if (newTextIndex !== currentTextIndex && !isTransitioning && progress < 0.9) {
                isTransitioning = true;
                currentTextIndex = newTextIndex;
                
                // Fade out current text
                phoneText.classList.add('fade-out');
                
                setTimeout(() => {
                    phoneText.innerHTML = phoneTexts[currentTextIndex];
                    phoneText.classList.remove('fade-out');
                    phoneText.classList.add('fade-in');
                    
                    setTimeout(() => {
                        phoneText.classList.remove('fade-in');
                        isTransitioning = false;
                    }, 800);
                }, 300);
            }
            
            // Fade out phone completely when we reach the end (progress > 0.7) - faster fade out
            if (progress > 0.7) {
                const fadeProgress = (progress - 0.7) / 0.3; // 0 to 1 over the last 30%
                phoneContainer.style.opacity = (1 - fadeProgress).toString();
                phoneContainer.style.transform = `translate(-50%, -50%) scale(${1 - fadeProgress * 0.3})`;
                if (fadeProgress >= 1) {
                    phoneContainer.style.pointerEvents = 'none';
                }
            } else {
                // Keep phone visible during the intro section
                const opacity = Math.max(0, 1 - (progress * 0.1)); // Slight fade as we progress
                phoneContainer.style.opacity = opacity.toString();
                phoneContainer.style.transform = 'translate(-50%, -50%) scale(1)';
                phoneContainer.style.pointerEvents = 'auto';
            }
        }
        
        // Phone 2 (Hero) - interactive functions
        function showFocusMode() {
            const colorPanel = document.querySelector('.hero-color-panel');
            const phoneText = document.getElementById('phoneText2');
            const qrButton = document.querySelector('.qr-button');
            const doneButton = document.querySelector('.done-button');
            
            // Expand color panel to full screen
            colorPanel.style.height = '95%';
            colorPanel.style.borderRadius = '32px';
            
            // Hide QR button
            qrButton.style.opacity = '0';
            qrButton.style.pointerEvents = 'none';
            
            // Show done button
            doneButton.style.opacity = '1';
            
            // Show focus mode text
            phoneText.innerHTML = `
                <div class="feature-text" style="opacity: 1;">
                    Hier kannst du eine entspannte Fokuszeit erstellen und die wertvolle Zeit mit deinen Liebsten genießen ✨
                </div>
            `;
        }
        
        function showQRMode() {
            const colorPanel = document.querySelector('.hero-color-panel');
            const phoneText = document.getElementById('phoneText2');
            const qrButton = document.querySelector('.qr-button');
            const doneButton = document.querySelector('.done-button');
            
            // Shrink color panel to 30%
            colorPanel.style.height = '30%';
            
            // Hide QR button
            qrButton.style.opacity = '0';
            qrButton.style.pointerEvents = 'none';
            
            // Show done button
            doneButton.style.opacity = '1';
            
            // Show QR mode text
            phoneText.innerHTML = `
                <div class="feature-text" style="opacity: 1; font-size: 1rem;">
                    Hier kannst du einen QR-Code scannen, um an einer gemeinsamen Fokuszeit teilzunehmen 📱
                </div>
            `;
        }
        
        function resetHeroPhone() {
            const colorPanel = document.querySelector('.hero-color-panel');
            const phoneText = document.getElementById('phoneText2');
            const qrButton = document.querySelector('.qr-button');
            const doneButton = document.querySelector('.done-button');
            
            // Reset color panel
            colorPanel.style.height = '70%';
            colorPanel.style.borderRadius = '0 0 23px 23px';
            
            // Show QR button
            qrButton.style.opacity = '1';
            qrButton.style.pointerEvents = 'auto';
            
            // Hide done button
            doneButton.style.opacity = '0';
            
            // Reset to main view
            phoneText.innerHTML = `
                <button class="focus-button" onclick="showFocusMode()">
                    <div class="plus-icon">+</div>
                    <div class="focus-text">Fokuszeit erstellen</div>
                </button>
            `;
        }
        
        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);
        
        // Observe all scroll animation elements
        document.querySelectorAll('.scroll-animation, .feature-card, .step-card').forEach(el => {
            observer.observe(el);
        });
        
        // Add staggered animation delays for feature cards
        document.querySelectorAll('.feature-card').forEach((card, index) => {
            card.style.transitionDelay = `${index * 0.2}s`;
        });
        
        // Add staggered animation delays for step cards
        document.querySelectorAll('.step-card').forEach((card, index) => {
            card.style.transitionDelay = `${index * 0.3}s`;
        });
        
        // Update phone 1 text on scroll with throttling for better performance
        let ticking = false;
        function requestTick() {
            if (!ticking) {
                requestAnimationFrame(updatePhone1Text);
                ticking = true;
            }
        }
        
        // Optimized scroll handler for mobile
        let scrollTimeout;
        window.addEventListener('scroll', () => {
            if (scrollTimeout) {
                clearTimeout(scrollTimeout);
            }
            
            requestTick();
            ticking = false;
            
            // Reduced scroll frequency on mobile for better performance
            const isMobile = window.innerWidth <= 768;
            if (isMobile) {
                scrollTimeout = setTimeout(() => {
                    // Additional mobile optimizations can go here
                }, 100);
            }
        }, { passive: true }); // Passive listener for better performance
        
        // Smooth scrolling for anchor links
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
        
        // Optimized parallax effect for color islands (disabled on mobile for performance)
        window.addEventListener('scroll', () => {
            if (window.innerWidth > 768) { // Only run on desktop
                const scrolled = window.pageYOffset;
                const islands = document.querySelectorAll('.color-island');
                islands.forEach((island, index) => {
                    const rate = scrolled * -0.5;
                    island.style.transform = `translateY(${rate}px)`;
                });
            }
        }, { passive: true });
        
        // Touch optimization for mobile
        if ('ontouchstart' in window) {
            // Add touch-friendly classes
            document.body.classList.add('touch-device');
            
            // Improve touch responsiveness
            document.querySelectorAll('.focus-button, .qr-button, .done-button, .app-button, .feedback-button, .support-button').forEach(button => {
                button.addEventListener('touchstart', function() {
                    this.style.transform += ' scale(0.95)';
                }, { passive: true });
                
                button.addEventListener('touchend', function() {
                    setTimeout(() => {
                        this.style.transform = this.style.transform.replace(' scale(0.95)', '');
                    }, 100);
                }, { passive: true });
            });
        }
        
        // Viewport height fix for mobile browsers
        function setVHProperty() {
            const vh = window.innerHeight * 0.01;
            document.documentElement.style.setProperty('--vh', `${vh}px`);
        }
        
        setVHProperty();
        window.addEventListener('resize', setVHProperty);
        window.addEventListener('orientationchange', setVHProperty);
        
        // Initialize
        updatePhone1Text();
        
        // Prevent zoom on double tap for iOS
        let lastTouchEnd = 0;
        document.addEventListener('touchend', function (event) {
            const now = (new Date()).getTime();
            if (now - lastTouchEnd <= 300) {
                event.preventDefault();
            }
            lastTouchEnd = now;
        }, false);
    </script>
</body>
</html>
