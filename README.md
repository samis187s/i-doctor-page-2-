<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Doctor AI | Your Personal Health Assistant</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #8a2be2;
            --primary-dark: #6a1b9a;
            --primary-light: #b388ff;
            --accent: #ff5e94;
            --dark: #1a0033;
            --light: #f8f5ff;
            --white: #ffffff;
            --gray: #f0f0f0;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, var(--light) 0%, var(--white) 100%);
            color: var(--dark);
            min-height: 100vh;
            line-height: 1.6;
        }
        
        .hero {
            background: linear-gradient(135deg, rgba(26, 0, 51, 0.95) 0%, rgba(138, 43, 226, 0.8) 100%);
            color: var(--white);
            padding: 80px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiPjxkZWZzPjxwYXR0ZXJuIGlkPSJwYXR0ZXJuIiB3aWR0aD0iNDAiIGhlaWdodD0iNDAiIHBhdHRlcm5Vbml0cz0idXNlclNwYWNlT25Vc2UiIHBhdHRlcm5UcmFuc2Zvcm09InJvdGF0ZSgxMzUpIj48cmVjdCBpZD0icGF0dGVybi1oZXgiIHdpZHRoPSIyMCIgaGVpZ2h0PSIyMCIgZmlsbD0icmdiYSgyNTUsMjU1LDI1NSwwLjAzKSIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3QgZmlsbD0idXJsKCNwYXR0ZXJuKSIgaGVpZ2h0PSIxMDAlIiB3aWR0aD0iMTAwJSIvPjwvc3ZnPg==');
            opacity: 0.5;
            z-index: 0;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }
        
        .logo-container {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
        }
        
        .logo {
            width: 180px;
            height: 180px;
            object-fit: contain;
            filter: drop-shadow(0 10px 20px rgba(0, 0, 0, 0.2));
            animation: pulse 3s infinite ease-in-out;
            transition: transform 0.3s ease;
        }
        
        .logo:hover {
            transform: scale(1.05);
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(to right, var(--white), var(--primary-light));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: -0.5px;
        }
        
        .tagline {
            font-size: 1.5rem;
            font-weight: 300;
            margin-bottom: 40px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .cta-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 40px;
            flex-wrap: wrap;
        }
        
        .cta-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background-color: var(--accent);
            color: var(--white);
            padding: 16px 32px;
            text-decoration: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 10px 20px rgba(255, 94, 148, 0.3);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, var(--accent), var(--primary));
            z-index: -1;
            transition: opacity 0.3s ease;
            opacity: 0;
        }
        
        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 25px rgba(255, 94, 148, 0.4);
        }
        
        .cta-button:hover::before {
            opacity: 1;
        }
        
        .secondary-button {
            background-color: transparent;
            border: 2px solid var(--white);
            box-shadow: none;
        }
        
        .secondary-button:hover {
            background-color: var(--white);
            color: var(--primary);
        }
        
        .features {
            padding: 80px 0;
            text-align: center;
        }
        
        .section-title {
            font-size: 2.5rem;
            margin-bottom: 60px;
            color: var(--primary-dark);
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(to right, var(--primary), var(--accent));
            border-radius: 2px;
        }
        
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 40px;
        }
        
        .feature-card {
            background: var(--white);
            border-radius: 20px;
            padding: 40px 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(138, 43, 226, 0.1);
        }
        
        .feature-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .feature-description {
            color: #666;
            font-size: 1rem;
        }
        
        .footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 40px 0;
            text-align: center;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        
        .footer-link {
            color: var(--primary-light);
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-link:hover {
            color: var(--white);
        }
        
        .copyright {
            margin-top: 20px;
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.6);
        }
        
        /* Media Queries */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .tagline {
                font-size: 1.2rem;
            }
            
            .logo {
                width: 150px;
                height: 150px;
            }
            
            .hero {
                padding: 60px 20px;
            }
            
            .feature-grid {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 480px) {
            h1 {
                font-size: 2rem;
            }
            
            .logo {
                width: 120px;
                height: 120px;
            }
            
            .cta-button {
                width: 100%;
                padding: 14px 20px;
                font-size: 1rem;
            }
            
            .cta-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <section class="hero">
        <div class="container">
            <div class="logo-container">
                <img src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/an%20attractive%20AI%20doctor%20logo%20with%20a%20purple%20theme%20and%20no%20background%2C%20stoic%2C%20inspired%20by%20Leonardo%20da%20Vinci-eqneWU6PZEAwufgsAwG5l5phtwO34G.png" alt="Doctor AI Logo" class="logo">
            </div>
            <h1>Doctor AI</h1>
            <p class="tagline">Your personal AI-powered health assistant, providing medical insights and guidance at your fingertips.</p>
            <div class="cta-container">
                <a href="https://play.google.com/store/apps/details?id=ai.doctor" target="_blank" class="cta-button">Install the App</a>
                <a href="#features" class="cta-button secondary-button">Learn More</a>
            </div>
        </div>
    </section>
    
    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Why Choose Doctor AI</h2>
            <div class="feature-grid">
                <div class="feature-card">
                    <div class="feature-icon">🔍</div>
                    <h3 class="feature-title">Symptom Analysis</h3>
                    <p class="feature-description">Advanced AI algorithms analyze your symptoms and provide potential causes and recommendations.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">⏰</div>
                    <h3 class="feature-title">24/7 Availability</h3>
                    <p class="feature-description">Get medical insights anytime, anywhere without waiting for appointments.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔒</div>
                    <h3 class="feature-title">Privacy First</h3>
                    <p class="feature-description">Your health data is encrypted and secure, with strict privacy protocols.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h3 class="feature-title">Health Tracking</h3>
                    <p class="feature-description">Monitor your health metrics over time and receive personalized insights.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🩺</div>
                    <h3 class="feature-title">Medical References</h3>
                    <p class="feature-description">Access a vast database of medical information verified by healthcare professionals.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">💬</div>
                    <h3 class="feature-title">Natural Conversations</h3>
                    <p class="feature-description">Interact with Doctor AI through natural language for a seamless experience.</p>
                </div>
            </div>
        </div>
    </section>
    
    <footer class="footer">
        <div class="container">
            <div class="footer-links">
                <a href="#" class="footer-link">About Us</a>
                <a href="#" class="footer-link">Privacy Policy</a>
                <a href="#" class="footer-link">Terms of Service</a>
                <a href="#" class="footer-link">Contact</a>
                <a href="#" class="footer-link">FAQ</a>
            </div>
            <p class="copyright">© 2025 Doctor AI. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
