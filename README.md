<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AladiaCityRoleplay - Community</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-image: url('https://images.unsplash.com/photo-1514565131-fce0801e5785?w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            background-repeat: no-repeat;
            min-height: 100vh;
            position: relative;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(180deg, rgba(20, 20, 20, 0.92) 0%, rgba(30, 30, 30, 0.88) 50%, rgba(20, 20, 20, 0.92) 100%);
            z-index: 0;
            pointer-events: none;
        }

        .navbar {
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            padding: 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.5);
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            align-items: center;
        }

        .nav-links {
            display: flex;
            list-style: none;
            margin: 0;
            padding: 0;
        }

        .nav-links li {
            position: relative;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 1.2rem 2rem;
            display: block;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            left: 0;
            right: 100%;
            bottom: 0;
            height: 3px;
            background: #764ba2;
            transition: right 0.3s;
        }

        .nav-links a:hover::before,
        .nav-links a.active::before {
            right: 0;
        }

        .nav-links a:hover,
        .nav-links a.active {
            background: rgba(118, 75, 162, 0.1);
        }

        /* Page Sections */
        .page-section {
            display: none;
            position: relative;
            z-index: 1;
            min-height: calc(100vh - 60px);
        }

        .page-section.active {
            display: block;
        }

        /* Home Section */
        .home-section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
            color: white;
        }

        .home-title {
            text-align: center;
            font-size: 3rem;
            color: #ff9800;
            margin-bottom: 2rem;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
        }

        .home-content {
            background: rgba(0, 0, 0, 0.7);
            padding: 3rem;
            border-radius: 10px;
            line-height: 1.8;
            font-size: 1.1rem;
            margin-bottom: 3rem;
        }

        .home-content p {
            margin-bottom: 1.5rem;
            text-align: justify;
        }

        .home-subtitle {
            text-align: center;
            font-size: 2.5rem;
            color: #ff9800;
            margin: 3rem 0 2rem 0;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
        }

        .hero {
            text-align: center;
            padding: 4rem 2rem;
            color: white;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.95;
            text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.8);
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2rem;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(102, 126, 234, 0.6);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 2px solid white;
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
        }

        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.95);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            transition: all 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.4);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #764ba2;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1.1rem;
            color: #555;
            font-weight: 600;
        }

        .features-section {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 3rem;
            margin: 3rem 0;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        .features-section h2 {
            text-align: center;
            font-size: 2.5rem;
            color: #764ba2;
            margin-bottom: 3rem;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            padding: 2rem;
            border-radius: 10px;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            border: 2px solid rgba(118, 75, 162, 0.2);
            transition: all 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            border-color: #764ba2;
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-card h3 {
            color: #764ba2;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        .feature-card p {
            color: #555;
            line-height: 1.6;
        }

        .community-section {
            text-align: center;
            padding: 3rem 0;
        }

        .community-section h2 {
            color: white;
            font-size: 2.5rem;
            margin-bottom: 2rem;
            text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.5);
        }

        .discord-widget {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            padding: 2rem;
            max-width: 600px;
            margin: 0 auto;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        footer {
            background: rgba(0, 0, 0, 0.9);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
            position: relative;
            z-index: 1;
        }

        .server-info {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            padding: 2rem;
            margin: 3rem 0;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        .server-info h3 {
            color: #764ba2;
            font-size: 2rem;
            margin-bottom: 1.5rem;
            text-align: center;
        }

        .server-details {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .detail-item {
            padding: 1rem;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            border-radius: 8px;
            border-left: 4px solid #764ba2;
        }

        .detail-item strong {
            color: #764ba2;
            display: block;
            margin-bottom: 0.5rem;
        }

        @media (max-width: 768px) {
            .nav-links {
                flex-wrap: wrap;
            }

            .nav-links a {
                padding: 1rem 1.5rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .home-title {
                font-size: 2rem;
            }

            .home-subtitle {
                font-size: 1.8rem;
            }

            .stats-section {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="nav-container">
            <ul class="nav-links">
                <li><a href="#" class="nav-link active" data-page="home">Home</a></li>
                <li><a href="#" class="nav-link" data-page="about">About</a></li>
                <li><a href="#" class="nav-link" data-page="features">Features</a></li>
                <li><a href="#" class="nav-link" data-page="community">Community</a></li>
            </ul>
        </div>
    </nav>

    <!-- Home Page -->
    <div id="home-page" class="page-section active">
        <div class="home-section">
            <h1 class="home-title">Welcome to AladiaCityRoleplay!</h1>
            
            <div class="home-content">
                <p>
                    AladiaCityRoleplay is a Roblox roleplay community founded with a mission to provide a unique roleplaying experience in a family-friendly environment. Our goal is to provide you with a supportive and loyal community where your voice will be heard and your efforts appreciated. With numerous departments and divisions to choose from, utilizing top-notch assets and scripts, we aim to offer a truly one-of-a-kind roleplaying experience.
                </p>
                <p>
                    We believe that these aspects are what sets us apart and contributes to our thriving community, where long-lasting bonds are formed and every member is respected and cared for by the administration, staff, and peers. We're always here to help you make the most of your experience at AladiaCityRoleplay, and we can't wait to welcome you into our family.
                </p>
            </div>

            <h2 class="home-subtitle">Want to join AladiaCityRoleplay?</h2>
            
            <div class="home-content">
                <p>
                    Great! We'd love to have you here. We have plenty of departments for you to join. At the top of the website you will see "Open Applications" make sure you click on that then select "Recruit Application" that will redirect to our server application. Please read all AladiaCityRoleplay's rules and regulations and community requirements before applying.
                </p>
                <p>
                    If you don't have a PC but still want to be apart of the AladiaCityRoleplay Community and contribute to our growing community, you can join through Roblox! Our community is accessible on multiple platforms, allowing you to experience the roleplay action wherever you are. Whether you're on PC or mobile, nobody is excluded. We want you to join our community because the only way we can thrive is through your passion and dedication to the server!
                </p>
            </div>

            <div style="text-align: center; margin-top: 3rem;">
                <button class="btn btn-primary" onclick="window.open('https://discord.com', '_blank')" style="margin-right: 1rem;">Join Discord</button>
                <button class="btn btn-secondary" onclick="window.open('https://roblox.com', '_blank')">Play on Roblox</button>
            </div>
        </div>
    </div>

    <!-- About Page -->
    <div id="about-page" class="page-section">
        <section class="hero">
            <h1>About AladiaCityRoleplay</h1>
            <p>Experience the ultimate roleplay adventure in our vibrant Roblox city</p>
        </section>

        <div class="container">
            <div class="stats-section">
                <div class="stat-card">
                    <div class="stat-number">49+</div>
                    <div class="stat-label">Active Players</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">24/7</div>
                    <div class="stat-label">Server Uptime</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">3</div>
                    <div class="stat-label">Custom Jobs</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">10+</div>
                    <div class="stat-label">Unique Vehicles</div>
                </div>
            </div>

            <div class="server-info">
                <h3>Server Information</h3>
                <div class="server-details">
                    <div class="detail-item">
                        <strong>Server Name:</strong>
                        AladiaCityRoleplay
                    </div>
                    <div class="detail-item">
                        <strong>Platform:</strong>
                        Roblox
                    </div>
                    <div class="detail-item">
                        <strong>Location:</strong>
                        Philippines
                    </div>
                    <div class="detail-item">
                        <strong>Max Players:</strong>
                        49 Slots
                    </div>
                    <div class="detail-item">
                        <strong>Server Type:</strong>
                        Serious Roleplay
                    </div>
                    <div class="detail-item">
                        <strong>Whitelist:</strong>
                        Yes (Application Required)
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Features Page -->
    <div id="features-page" class="page-section">
        <div class="container">
            <div class="features-section">
                <h2>Server Features</h2>
                <div class="features-grid">
                    <div class="feature-card">
                        <div class="feature-icon">🎭</div>
                        <h3>Realistic Roleplay</h3>
                        <p>Immerse yourself in a realistic roleplay environment with dedicated players and staff members.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">💼</div>
                        <h3>Custom Jobs</h3>
                        <p>Choose from 3 exciting job opportunities including police, civilian work, and business operations.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🚗</div>
                        <h3>Custom Vehicles</h3>
                        <p>Drive over 10 unique custom vehicles available in-game.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🏠</div>
                        <h3>Housing System</h3>
                        <p>Own and customize your own properties throughout the city.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">👮</div>
                        <h3>Active Staff</h3>
                        <p>24/7 staff support to ensure fair play and handle any issues promptly.</p>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🎨</div>
                        <h3>Custom Scripts</h3>
                        <p>Unique custom Roblox scripts and features not found on other servers.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Community Page -->
    <div id="community-page" class="page-section">
        <div class="container">
            <section class="community-section">
                <h2>Join Our Community</h2>
                <div class="discord-widget">
                    <h3 style="color: #764ba2; margin-bottom: 1rem;">Connect with us on Discord</h3>
                    <p style="color: #555; margin-bottom: 1.5rem;">Join our Discord server to stay updated, apply for whitelist, and connect with other players!</p>
                    <button class="btn btn-primary">Join Discord Server</button>
                </div>
            </section>
        </div>
    </div>

    <footer>
        <p>&copy; 2025 AladiaCityRoleplay. All rights reserved.</p>
        <p style="margin-top: 0.5rem; opacity: 0.8;">Building the best Roblox roleplay experience in the Philippines</p>
    </footer>

    <script>
        // Page Navigation
        const navLinks = document.querySelectorAll('.nav-link');
        const pages = document.querySelectorAll('.page-section');

        navLinks.forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                
                // Remove active class from all links and pages
                navLinks.forEach(l => l.classList.remove('active'));
                pages.forEach(p => p.classList.remove('active'));
                
                // Add active class to clicked link
                this.classList.add('active');
                
                // Show corresponding page
                const pageId = this.getAttribute('data-page') + '-page';
                document.getElementById(pageId).classList.add('active');
                
                // Scroll to top
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });
        });

        // Animations
        const statNumbers = document.querySelectorAll('.stat-number');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.6s ease-out';
                }
            });
        });

        statNumbers.forEach(stat => observer.observe(stat));
    </script>
</body>
</html>
