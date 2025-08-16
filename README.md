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
            height: 400vh;
            position: relative;
            background: var(--dark-bg);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .phone-container {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 100;
            transition: all 1.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
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
            transition: all 0.5s ease;
            animation: snowIn 0.8s ease-out;
        }

        @keyframes snowIn {
            0% { 
                opacity: 0; 
                transform: translateY(-30px) scale(0.9);
                filter: blur(2px);
            }
            100% { 
                opacity: 1; 
                transform: translateY(0) scale(1);
                filter: blur(0);
            }
        }

        .phone-text.fade-out {
            opacity: 0;
            transform: translateY(-20px);
        }

        .phone-text.fade-in {
            opacity: 1;
            transform: translateY(0);
            animation: snowIn 0.8s ease-out;
        }

        .plus-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            opacity: 0;
            transition: all 0.5s ease;
        }

        .focus-text {
            font-size: 1.1rem;
            font-weight: 500;
            opacity: 0;
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
            opacity: 0;
            transition: all 0.5s ease;
            white-space: nowrap;
            min-width: 180px;
        }

        .scroll-indicator {
            position: fixed;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            color: var(--text-light);
            font-size: 0.9rem;
            animation: pulse 2s infinite;
            opacity: 1;
            transition: opacity 0.5s ease;
        }

        .scroll-indicator.hidden {
            opacity: 0;
            pointer-events: none;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.6; }
            50% { opacity: 1; }
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            background: linear-gradient(135deg, rgba(0, 122, 255, 0.05), rgba(88, 86, 214, 0.05));
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
            display: flex;
            justify-content: center;
            align-items: flex-start;
            padding-top: 2rem;
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
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
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

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 0 20px;
            }

            .phone-frame {
                width: 280px;
                height: 560px;
            }

            .phone-text {
                font-size: 1.2rem;
            }

            .hero-content {
                grid-template-columns: 1fr;
                gap: 3rem;
                text-align: center;
            }

            .hero-text h1 {
                font-size: 2.5rem;
            }

            .hero-text p {
                font-size: 1.2rem;
            }

            .features h2,
            .onboarding h2,
            .cta h2 {
                font-size: 2.2rem;
            }

            .color-island {
                width: 250px;
                height: 180px;
            }

            .app-buttons {
                flex-direction: column;
                align-items: center;
            }

            .app-button img {
                height: 45px;
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
    </style>
</head>
<body>
    <!-- Phone Intro Section -->
    <section class="phone-intro">
        <div class="phone-container">
            <div class="phone-frame">
                <div class="phone-screen">
                    <div class="color-panel">
                        <div class="phone-text" id="phoneText">
                            Hallo, willkommen bei<br>Quality Time
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="scroll-indicator" id="scrollIndicator">
            Scrolle, um mehr zu erfahren ↓
        </div>
    </section>

    <!-- Hero Section -->
    <section class="hero">
        <div class="color-island"></div>
        <div class="container">
            <div class="hero-content
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Quality Time App</title>
  <style>
    /* General Styles */
    body, html {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      overflow-x: hidden;
    }

    .scroll-container {
      height: 500vh; /* Scroll area */
      position: relative;
    }

    .animation-section {
      height: 100vh;
      position: sticky;
      top: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .circle {
      position: absolute;
      border-radius: 50%;
      background-color: #D9D9D9;
      transition: all 0.5s ease;
    }

    /* Phone Styles */
    .phone-container {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 200px;
      height: 400px;
      border: 2px solid #000;
      border-radius: 30px;
      background-color: #fff;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      transition: all 1s ease;
      z-index: 10;
    }

    .phone-screen {
      width: 90%;
      height: 90%;
      border-radius: 20px;
      background-color: #f0f0f0;
      position: relative;
      overflow: hidden;
    }

    .color-panel {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 0%;
      background-color: #FF69B4;
      transition: height 1s ease;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .phone-text {
      position: absolute;
      width: 100%;
      text-align: center;
      font-size: 18px;
      opacity: 0;
      transition: opacity 1s ease;
    }

    .plus-icon {
      font-size: 48px;
      opacity: 0;
      transition: opacity 1s ease;
    }

    .focus-text {
      font-size: 18px;
      margin-top: 10px;
      opacity: 0;
      transition: opacity 1s ease;
    }

    .qr-button {
      position: absolute;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      padding: 10px 20px;
      background-color: #333;
      color: #fff;
      border-radius: 20px;
      font-size: 14px;
      opacity: 0;
      transition: opacity 1s ease;
    }

    /* Hero Section */
    .hero {
      display: grid;
      grid-template-columns: 1fr 1fr;
      height: 100vh;
      background-color: #f9f9f9;
      padding: 50px;
      box-sizing: border-box;
    }

    .hero-text {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 20px;
    }

    .hero-text h1 {
      font-size: 48px;
      margin: 0;
    }

    .hero-text p {
      font-size: 20px;
      margin: 20px 0;
    }

    .hero-text button {
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      border-radius: 25px;
      background-color: #333;
      color: white;
      cursor: pointer;
    }

    .phone-mockup {
      text-align: center;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding-top: 2rem;
    }
  </style>
</head>
<body>
  <div class="scroll-container">
    <div class="animation-section">
      <div class="circle" id="circle"></div>
      <div class="phone-container" id="phoneContainer">
        <div class="phone-screen">
          <div class="color-panel" id="colorPanel"></div>
          <div class="phone-text" id="phoneText">Quality Time</div>
        </div>
      </div>
    </div>
  </div>

  <section class="hero">
    <div class="hero-text">
      <h1>Quality Time</h1>
      <p>Fokuszeit mit deiner Familie – einfach per QR-Code teilen und Apps sperren.</p>
      <button>Jetzt starten</button>
    </div>
    <div class="phone-mockup"></div>
  </section>

  <script>
    const circle = document.getElementById('circle');
    const phoneContainer = document.getElementById('phoneContainer');
    const colorPanel = document.getElementById('colorPanel');
    const phoneText = document.getElementById('phoneText');
    let hasTransitioned = false;

    window.addEventListener('scroll', () => {
      const scrollTop = window.scrollY;
      const windowHeight = window.innerHeight;
      const docHeight = document.body.scrollHeight - windowHeight;
      const progress = scrollTop / docHeight;

      // Circle scaling
      const scale = Math.min(1000, 200 + progress * 2000);
      circle.style.width = `${scale}px`;
      circle.style.height = `${scale}px`;

      // Phone scaling
      const phoneScale = 1 + progress * 0.5;
      phoneContainer.style.transform = `translate(-50%, -50%) scale(${phoneScale})`;

      // Phone text fade in
      phoneText.style.opacity = progress;

      // Transition to Hero
      if (progress > 0.85 && !hasTransitioned) {
        hasTransitioned = true;

        const heroPhoneMockup = document.querySelector('.phone-mockup');

        // Handy nach rechts "fliegen lassen"
        phoneContainer.style.position = 'fixed';
        phoneContainer.style.left = '70%';
        phoneContainer.style.top = '50%';
        phoneContainer.style.transform = 'translate(-50%, -50%)';
        phoneContainer.style.zIndex = '10';

        setTimeout(() => {
          // Dann richtig ins Grid einsetzen
          phoneContainer.style.position = 'relative';
          phoneContainer.style.left = 'unset';
          phoneContainer.style.top = 'unset';
          phoneContainer.style.transform = 'none';
          phoneContainer.style.zIndex = 'auto';
          heroPhoneMockup.appendChild(phoneContainer);
        }, 1200);

        // Danach App-Interface anzeigen
        setTimeout(() => {
          colorPanel.style.height = '70%';
          phoneText.innerHTML = '<div class="plus-icon" style="opacity: 1;">+</div><div class="focus-text" style="opacity: 1;">Fokuszeit erstellen</div>';

          const qrButton = document.createElement('div');
          qrButton.className = 'qr-button';
          qrButton.textContent = 'QR-Code scannen';
          qrButton.style.opacity = '1';
          document.querySelector('.phone-screen').appendChild(qrButton);
        }, 400);
      }
    });
  </script>
</body>
</html>
