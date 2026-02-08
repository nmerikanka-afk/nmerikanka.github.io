<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name - Portfolio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Work+Sans:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --cream: #FFF8F0;
            --charcoal: #1a1a1a;
            --rust: #B85C38;
            --sage: #7A9B76;
            --gold: #D4A574;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Work Sans', sans-serif;
            background: var(--cream);
            color: var(--charcoal);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animated Background Elements */
        .bg-decoration {
            position: fixed;
            border-radius: 50%;
            opacity: 0.1;
            z-index: 0;
            pointer-events: none;
        }

        .circle-1 {
            width: 600px;
            height: 600px;
            background: var(--rust);
            top: -200px;
            right: -200px;
            animation: float 20s ease-in-out infinite;
        }

        .circle-2 {
            width: 400px;
            height: 400px;
            background: var(--sage);
            bottom: -100px;
            left: -100px;
            animation: float 25s ease-in-out infinite reverse;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            50% { transform: translate(30px, -30px) scale(1.1); }
        }

        /* Header */
        header {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 2rem;
            overflow: hidden;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            text-align: center;
            animation: fadeInUp 1s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(3rem, 8vw, 7rem);
            font-weight: 900;
            margin-bottom: 1rem;
            line-height: 1.1;
            letter-spacing: -0.02em;
        }

        .name-highlight {
            color: var(--rust);
            position: relative;
            display: inline-block;
        }

        .tagline {
            font-size: clamp(1.2rem, 2.5vw, 1.8rem);
            font-weight: 300;
            color: var(--charcoal);
            opacity: 0.8;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 0.2s backwards;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: var(--charcoal);
            color: var(--cream);
            text-decoration: none;
            font-weight: 600;
            letter-spacing: 0.05em;
            text-transform: uppercase;
            font-size: 0.9rem;
            border: 2px solid var(--charcoal);
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease-out 0.4s backwards;
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--rust);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .cta-button:hover::before {
            left: 0;
        }

        .cta-button:hover {
            border-color: var(--rust);
            color: var(--cream);
        }

        /* Sections */
        section {
            position: relative;
            z-index: 1;
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        h2 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 3rem;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60%;
            height: 4px;
            background: var(--rust);
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            animation: fadeIn 1s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
        }

        .skill-item {
            padding: 1.5rem;
            background: white;
            border-left: 4px solid var(--sage);
            transition: transform 0.3s ease, border-color 0.3s ease;
        }

        .skill-item:hover {
            transform: translateX(10px);
            border-color: var(--rust);
        }

        .skill-item h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--charcoal);
        }

        .skill-item p {
            font-size: 0.95rem;
            opacity: 0.8;
        }

        /* Projects Section */
        #projects {
            background: linear-gradient(135deg, rgba(122, 155, 118, 0.05) 0%, rgba(184, 92, 56, 0.05) 100%);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background: white;
            padding: 2rem;
            border-radius: 4px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--rust), var(--gold));
            transform: scaleX(0);
            transition: transform 0.3s ease;
            transform-origin: left;
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .project-card h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.6rem;
            margin-bottom: 1rem;
            color: var(--charcoal);
        }

        .project-card p {
            margin-bottom: 1rem;
            opacity: 0.8;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .tag {
            padding: 0.3rem 0.8rem;
            background: var(--cream);
            border: 1px solid var(--sage);
            font-size: 0.85rem;
            color: var(--charcoal);
            border-radius: 20px;
        }

        /* Contact Section */
        .contact-content {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .contact-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 2rem;
            background: white;
            color: var(--charcoal);
            text-decoration: none;
            font-weight: 600;
            border: 2px solid var(--charcoal);
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            background: var(--charcoal);
            color: var(--cream);
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
        }

        /* Footer */
        footer {
            background: var(--charcoal);
            color: var(--cream);
            text-align: center;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        footer p {
            opacity: 0.8;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .about-content {
                grid-template-columns: 1fr;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            h2::after {
                width: 80%;
            }

            .contact-links {
                flex-direction: column;
                align-items: center;
            }
        }

        /* Scroll Animation Utility */
        .fade-in-section {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }

        .fade-in-section.is-visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Background Decorations -->
    <div class="bg-decoration circle-1"></div>
    <div class="bg-decoration circle-2"></div>

    <!-- Header/Hero Section -->
    <header>
        <div class="hero-content">
            <h1>Hi, I'm <span class="name-highlight">Your Name</span></h1>
            <p class="tagline">Creative Developer & Designer</p>
            <a href="#contact" class="cta-button">Get in Touch</a>
        </div>
    </header>

    <!-- About Section -->
    <section id="about">
        <h2>About Me</h2>
        <div class="about-content fade-in-section">
            <div class="about-text">
                <p>I'm a passionate creative professional who loves bringing ideas to life through design and development. With a keen eye for detail and a commitment to excellence, I craft experiences that are both beautiful and functional.</p>
                <p>Whether it's building responsive websites, designing intuitive interfaces, or solving complex problems, I approach every project with curiosity and dedication.</p>
            </div>
            <div class="skills-grid">
                <div class="skill-item">
                    <h3>Design</h3>
                    <p>UI/UX, Branding, Visual Design</p>
                </div>
                <div class="skill-item">
                    <h3>Development</h3>
                    <p>HTML, CSS, JavaScript, React</p>
                </div>
                <div class="skill-item">
                    <h3>Tools</h3>
                    <p>Figma, Adobe Suite, VS Code</p>
                </div>
                <div class="skill-item">
                    <h3>Other</h3>
                    <p>Photography, Writing, Strategy</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2>Featured Work</h2>
        <div class="projects-grid fade-in-section">
            <div class="project-card">
                <h3>Project One</h3>
                <p>A modern web application that helps users manage their daily tasks with an intuitive interface and powerful features.</p>
                <div class="project-tags">
                    <span class="tag">React</span>
                    <span class="tag">Design</span>
                    <span class="tag">UX</span>
                </div>
            </div>
            <div class="project-card">
                <h3>Project Two</h3>
                <p>Brand identity and website redesign for a local business, resulting in increased engagement and modern appeal.</p>
                <div class="project-tags">
                    <span class="tag">Branding</span>
                    <span class="tag">Web Design</span>
                </div>
            </div>
            <div class="project-card">
                <h3>Project Three</h3>
                <p>An interactive portfolio showcasing creative work with smooth animations and an engaging user experience.</p>
                <div class="project-tags">
                    <span class="tag">JavaScript</span>
                    <span class="tag">Animation</span>
                    <span class="tag">CSS</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2>Let's Connect</h2>
        <div class="contact-content fade-in-section">
            <p>I'm always excited to collaborate on new projects or just have a conversation about design and development. Feel free to reach out!</p>
            <div class="contact-links">
                <a href="mailto:your.email@example.com" class="contact-link">
                    📧 Email Me
                </a>
                <a href="https://linkedin.com/in/yourprofile" class="contact-link" target="_blank">
                    💼 LinkedIn
                </a>
                <a href="https://github.com/yourusername" class="contact-link" target="_blank">
                    💻 GitHub
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Your Name. Designed with passion.</p>
    </footer>

    <script>
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

        // Fade in sections on scroll
        const fadeInSections = document.querySelectorAll('.fade-in-section');
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible');
                }
            });
        }, {
            threshold: 0.1
        });

        fadeInSections.forEach(section => {
            observer.observe(section);
        });
    </script>
</body>
</html>
