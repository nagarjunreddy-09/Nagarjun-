# Nagarjun-
My first website



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Green Valley Academy</title>
    
    <style>
        /* --- 1. Basic Setup & Classical Variables --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Smooth scrolling for navigation links */
        html {
            scroll-behavior: smooth;
        }

        /* Classical Color Theme Variables */
        :root {
            --navy-blue: #0f2847;
            --classic-gold: #d4af37;
            --crimson-red: #8b1a1a;
            --parchment-white: #fdfbf7;
            --text-dark: #2c3e50;
        }

        body {
            line-height: 1.6;
            color: var(--text-dark);
            background-color: var(--parchment-white);
            /* Clean sans-serif for reading, but we will use serif for headings */
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
        }

        /* Classical Serif Font for Headings */
        h1, h2, h3 {
            font-family: 'Georgia', 'Times New Roman', Times, serif;
            letter-spacing: 1px;
        }

        /* --- 2. CSS Animations --- */
        
        /* Fade In and Slide Up Animation */
        @keyframes fadeSlideUp {
            0% {
                opacity: 0;
                transform: translateY(40px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Pulse Animation for the button */
        @keyframes subtlePulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Applying animations to sections */
        section {
            padding: 5rem 2rem;
            text-align: center;
            animation: fadeSlideUp 1.2s ease-out forwards;
        }

        /* --- 3. Header & Navigation --- */
        header {
            background-color: var(--navy-blue);
            color: var(--classic-gold);
            padding: 1.2rem 3rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }

        header h1 {
            font-size: 2rem;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 2rem;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            position: relative;
            padding: 0.5rem 0;
            transition: color 0.3s ease;
        }

        /* Animated underline on hover */
        nav a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background-color: var(--classic-gold);
            transition: width 0.3s ease;
        }

        nav a:hover {
            color: var(--classic-gold);
        }

        nav a:hover::after {
            width: 100%;
        }

        /* --- 4. Section Headings --- */
        section h2 {
            color: var(--navy-blue);
            margin-bottom: 2rem;
            font-size: 2.5rem;
            position: relative;
            display: inline-block;
        }

        /* Elegant underline under section titles */
        section h2::after {
            content: '';
            display: block;
            width: 60%;
            height: 3px;
            background-color: var(--crimson-red);
            margin: 10px auto 0 auto;
            border-radius: 2px;
        }

        /* --- 5. Home Section & Banner --- */
        #home {
            background-color: var(--parchment-white);
        }

        .banner-placeholder {
            width: 100%;
            max-width: 900px;
            height: 400px;
            margin: 2rem auto;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 12px;
            /* Beautiful gradient combined with a classic library/school image */
            background: linear-gradient(rgba(15, 40, 71, 0.7), rgba(139, 26, 26, 0.7)), 
                        url('https://images.unsplash.com/photo-1523050854058-8df90110c9f1?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            transition: transform 0.5s ease;
        }

        .banner-placeholder:hover {
            transform: scale(1.02);
        }

        .banner-placeholder h2 {
            color: white;
            font-size: 3rem;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.8);
        }
        
        .banner-placeholder h2::after {
            display: none; /* remove red line from banner text */
        }

        /* --- 6. Buttons --- */
        .btn {
            background-color: var(--crimson-red);
            color: white;
            border: 2px solid var(--crimson-red);
            padding: 12px 28px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            border-radius: 30px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }

        .btn:hover {
            background-color: transparent;
            color: var(--crimson-red);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.2);
        }

        .btn-pulse {
            animation: subtlePulse 2s infinite;
        }

        /* --- 7. About Section --- */
        #about p {
            max-width: 800px;
            margin: 0 auto;
            font-size: 1.2rem;
            line-height: 1.8;
            color: #444;
        }

        /* --- 8. Courses Section --- */
        #courses {
            background-color: #f4f1ea; /* Slightly darker parchment */
            border-top: 1px solid #e0dacc;
            border-bottom: 1px solid #e0dacc;
        }

        .course-container {
            display: flex;
            justify-content: center;
            gap: 2.5rem;
            flex-wrap: wrap;
        }

        .course-card {
            background-color: white;
            padding: 2.5rem 1.5rem;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            width: 320px;
            border-top: 5px solid var(--navy-blue);
            transition: all 0.4s ease;
            cursor: pointer;
        }

        .course-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
            border-top: 5px solid var(--classic-gold);
        }

        .course-card h3 {
            color: var(--navy-blue);
            margin-bottom: 1rem;
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .course-card:hover h3 {
            color: var(--crimson-red);
        }

        /* --- 9. Contact Section --- */
        form {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 3rem;
            border-radius: 12px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            text-align: left;
            border: 1px solid #e0dacc;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: var(--navy-blue);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-size: 1rem;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--classic-gold);
            box-shadow: 0 0 8px rgba(212, 175, 55, 0.4);
        }

        .form-group textarea {
            resize: vertical;
            height: 150px;
        }

        /* --- 10. Footer --- */
        footer {
            background-color: var(--navy-blue);
            color: var(--parchment-white);
            text-align: center;
            padding: 2rem;
            font-size: 1rem;
            border-top: 4px solid var(--classic-gold);
        }

        /* --- 11. Responsive Design --- */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                text-align: center;
                padding: 1rem;
            }
            
            nav ul {
                margin-top: 1rem;
                flex-direction: column;
                gap: 1rem;
            }

            .banner-placeholder h2 {
                font-size: 2rem;
            }

            section {
                padding: 3rem 1rem;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>Green Valley Academy</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">Our History</a></li>
                <li><a href="#courses">Academics</a></li>
                <li><a href="#contact">Admissions</a></li>
            </ul>
        </nav>
    </header>

    <section id="home">
        <h2>Tradition Meets Excellence</h2>
        <p>Empowering minds and shaping the leaders of tomorrow since 1924.</p>
        
        <div class="banner-placeholder">
            <h2>Sapientia et Virtus</h2> </div>
        
        <button class="btn btn-pulse" onclick="showWelcomeMessage()">Discover Our Legacy</button>
        <p id="welcome-text" style="display:none; margin-top:1.5rem; font-size: 1.2rem; font-style: italic; color:var(--crimson-red);"></p>
    </section>

    <section id="about">
        <h2>Our History</h2>
        <p>Green Valley Academy has been a pillar of academic prestige for over a century. We combine time-honored teaching methods with modern innovation. Our historic campus features magnificent architecture, a world-class library, and dedicated educators committed to forging resilience, intellect, and character.</p>
    </section>

    <section id="courses">
        <h2>Academic Programs</h2>
        <div class="course-container">
            <div class="course-card">
                <h3>Classical Literature</h3>
                <p>Immerse yourself in the works of Shakespeare, Homer, and the great philosophers. Master the art of rhetoric and critical analysis.</p>
            </div>
            <div class="course-card">
                <h3>Advanced Sciences</h3>
                <p>From theoretical physics to organic chemistry, our state-of-the-art laboratories provide an unparalleled environment for discovery.</p>
            </div>
            <div class="course-card">
                <h3>Fine Arts & Music</h3>
                <p>Cultivate your artistic spirit. Our academy offers comprehensive training in classical music, oil painting, and sculptural arts.</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <h2>Inquire Today</h2>
        <form id="contactForm">
            <div class="form-group">
                <label for="name">Prospective Student Name:</label>
                <input type="text" id="name" placeholder="E.g., John Doe">
            </div>
            
            <div class="form-group">
                <label for="email">Email Address:</label>
                <input type="email" id="email" placeholder="contact@example.com">
            </div>
            
            <div class="form-group">
                <label for="message">Message or Inquiry:</label>
                <textarea id="message" placeholder="Please state your intended year of entry and any questions..."></textarea>
            </div>
            
            <button type="submit" class="btn">Submit Inquiry</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2026 Green Valley Academy. Honoring the Past, Inspiring the Future.</p>
    </footer>

    <script>
        // Welcome Message Animation
        function showWelcomeMessage() {
            const welcomeText = document.getElementById('welcome-text');
            welcomeText.innerText = "Welcome to our esteemed academy. Your journey to greatness begins here.";
            
            // Fade in effect using JS
            welcomeText.style.opacity = 0;
            welcomeText.style.display = "block";
            
            let opacity = 0;
            const fadeIn = setInterval(function() {
                if (opacity >= 1) {
                    clearInterval(fadeIn);
                }
                welcomeText.style.opacity = opacity;
                opacity += 0.1;
            }, 50);
        }

        // Form Validation Check
        document.getElementById('contactForm').addEventListener('submit', function(event) {
            event.preventDefault(); // Stop page refresh

            const name = document.getElementById('name').value.trim();
            const email = document.getElementById('email').value.trim();
            const message = document.getElementById('message').value.trim();

            if (name === "" || email === "" || message === "") {
                alert("Error: Please complete all fields for your inquiry.");
                return;
            }

            const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailPattern.test(email)) {
                alert("Error: Please provide a valid email format.");
                return;
            }

            alert("Thank you, " + name + ". Your inquiry has been received by our admissions office. We shall respond shortly.");
            document.getElementById('contactForm').reset();
        });
    </script>
</body>
</html>

