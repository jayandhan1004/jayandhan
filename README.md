# Muruga Estate
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muruga Estates - Premium Real Estate Solutions</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-gold: #d4af37;
            --dark-bg: #0f1419;
            --dark-card: #1a1f2e;
            --accent-blue: #1e90ff;
            --text-light: #e0e0e0;
            --text-muted: #a0a0a0;
            --success: #00d084;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f1419 0%, #1a1f2e 100%);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(15, 20, 25, 0.95);
            backdrop-filter: blur(10px);
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            border-bottom: 1px solid rgba(212, 175, 55, 0.1);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            background: linear-gradient(135deg, #d4af37 0%, #ffd700 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-light);
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: 500;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary-gold);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #d4af37 0%, #ffd700 100%);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .admin-btn, .register-btn {
            padding: 0.8rem 1.5rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .admin-btn {
            background: transparent;
            color: var(--primary-gold);
            border: 2px solid var(--primary-gold);
        }

        .admin-btn:hover {
            background: var(--primary-gold);
            color: var(--dark-bg);
            transform: translateY(-2px);
        }

        .register-btn {
            background: linear-gradient(135deg, #1e90ff 0%, #00d084 100%);
            color: white;
        }

        .register-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(30, 144, 255, 0.3);
        }

        /* Hero Section */
        .hero {
            margin-top: 80px;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            perspective: 1000px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                radial-gradient(circle at 20% 50%, rgba(212, 175, 55, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(30, 144, 255, 0.1) 0%, transparent 50%);
            animation: gradientShift 8s ease infinite;
        }

        @keyframes gradientShift {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        .hero-content {
            text-align: center;
            z-index: 10;
            animation: fadeInUp 1s ease 0.2s both;
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

        .hero h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #d4af37 0%, #ffd700 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 3px;
            text-transform: uppercase;
        }

        .hero p {
            font-size: 1.4rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary, .btn-secondary {
            padding: 1rem 2.5rem;
            font-size: 1.1rem;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn-primary {
            background: linear-gradient(135deg, #d4af37 0%, #ffd700 100%);
            color: var(--dark-bg);
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(212, 175, 55, 0.5);
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid var(--primary-gold);
            color: var(--primary-gold);
        }

        .btn-secondary:hover {
            background: var(--primary-gold);
            color: var(--dark-bg);
            transform: translateY(-5px);
        }

        /* 3D Cards */
        .projects-section {
            padding: 6rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 3rem;
            font-weight: 800;
            text-align: center;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #d4af37 0%, #ffd700 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 2px;
        }

        .section-subtitle {
            text-align: center;
            color: var(--text-muted);
            font-size: 1.2rem;
            margin-bottom: 3rem;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            perspective: 1000px;
        }

        .project-card {
            background: linear-gradient(135deg, #1a1f2e 0%, #252d3d 100%);
            border-radius: 15px;
            padding: 2rem;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.23, 1, 0.320, 1);
            border: 1px solid rgba(212, 175, 55, 0.2);
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(212, 175, 55, 0.1) 0%, transparent 100%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-15px) rotateX(5deg);
            border-color: var(--primary-gold);
            box-shadow: 0 20px 60px rgba(212, 175, 55, 0.3), inset 0 1px 0 rgba(255, 255, 255, 0.2);
        }

        .project-card:hover::before {
            opacity: 1;
        }

        .project-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .project-card h3 {
            font-size: 1.5rem;
            margin-bottom: 0.8rem;
            color: var(--primary-gold);
        }

        .project-card p {
            color: var(--text-muted);
            margin-bottom: 1rem;
        }

        /* Info Section */
        .info-section {
            background: linear-gradient(135deg, rgba(212, 175, 55, 0.05) 0%, rgba(30, 144, 255, 0.05) 100%);
            padding: 4rem 5%;
            margin: 3rem 0;
            border-top: 1px solid rgba(212, 175, 55, 0.2);
            border-bottom: 1px solid rgba(212, 175, 55, 0.2);
        }

        .info-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .info-card {
            background: rgba(26, 31, 46, 0.5);
            padding: 2rem;
            border-radius: 10px;
            border-left: 4px solid var(--primary-gold);
            backdrop-filter: blur(10px);
        }

        .info-card h4 {
            color: var(--primary-gold);
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .info-card p {
            color: var(--text-light);
            font-size: 1.1rem;
        }

        /* Registration Form */
        .registration-section {
            padding: 6rem 5%;
            max-width: 1000px;
            margin: 0 auto;
        }

        .form-container {
            background: linear-gradient(135deg, #1a1f2e 0%, #252d3d 100%);
            padding: 3rem;
            border-radius: 20px;
            border: 1px solid rgba(212, 175, 55, 0.2);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--primary-gold);
            font-weight: 600;
            font-size: 0.95rem;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 0.9rem;
            border: 2px solid rgba(212, 175, 55, 0.3);
            background: rgba(26, 31, 46, 0.8);
            color: var(--text-light);
            border-radius: 8px;
            font-family: inherit;
            transition: all 0.3s ease;
            font-size: 1rem;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-gold);
            background: rgba(26, 31, 46, 0.95);
            box-shadow: 0 0 15px rgba(212, 175, 55, 0.2);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
        }

        .form-row-full {
            grid-column: 1 / -1;
        }

        .submit-btn {
            width: 100%;
            padding: 1.2rem;
            background: linear-gradient(135deg, #d4af37 0%, #ffd700 100%);
            color: var(--dark-bg);
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 1rem;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 40px rgba(212, 175, 55, 0.4);
        }

        .submit-btn:active {
            transform: translateY(0);
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal-content {
            background: linear-gradient(135deg, #1a1f2e 0%, #252d3d 100%);
            margin: 5% auto;
            padding: 2rem;
            border: 2px solid var(--primary-gold);
            width: 90%;
            max-width: 600px;
            border-radius: 20px;
            max-height: 80vh;
            overflow-y: auto;
            animation: slideDown 0.3s ease;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .close {
            color: var(--primary-gold);
            float: right;
            font-size: 2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .close:hover {
            color: #ffd700;
            transform: rotate(90deg);
        }

        /* Admin Panel */
        .admin-panel {
            padding: 2rem;
            background: rgba(26, 31, 46, 0.8);
            border-radius: 15px;
            margin-bottom: 2rem;
        }

        .admin-section {
            margin-bottom: 2rem;
        }

        .admin-section h3 {
            color: var(--primary-gold);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        /* Footer */
        footer {
            background: rgba(15, 20, 25, 0.95);
            padding: 3rem 5%;
            border-top: 1px solid rgba(212, 175, 55, 0.2);
            margin-top: 4rem;
        }

        .footer-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-column h4 {
            color: var(--primary-gold);
            margin-bottom: 1rem;
        }

        .footer-column a, .footer-column p {
            color: var(--text-muted);
            text-decoration: none;
            margin-bottom: 0.5rem;
            transition: all 0.3s ease;
        }

        .footer-column a:hover {
            color: var(--primary-gold);
            padding-left: 5px;
        }

        .footer-bottom {
            text-align: center;
            border-top: 1px solid rgba(212, 175, 55, 0.2);
            padding-top: 2rem;
            color: var(--text-muted);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .nav-links {
                gap: 1rem;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .section-title {
                font-size: 2rem;
            }

            .hero-buttons {
                flex-direction: column;
            }

            .btn-primary, .btn-secondary {
                width: 100%;
            }
        }

        /* Success Message */
        .success-message {
            display: none;
            position: fixed;
            top: 100px;
            right: 20px;
            background: linear-gradient(135deg, #00d084 0%, #00a860 100%);
            color: white;
            padding: 1.5rem 2rem;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 208, 132, 0.3);
            z-index: 2001;
            animation: slideInRight 0.5s ease;
        }

        @keyframes slideInRight {
            from {
                transform: translateX(400px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <div class="logo">🏢 MURUGA ESTATES</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <div style="display: flex; gap: 1rem;">
            <button class="admin-btn" onclick="openAdminPanel()">Admin Panel</button>
            <button class="register-btn" onclick="scrollToForm()">Register Now</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Muruga Estates</h1>
            <p>Premium Villas & Real Estate Excellence Across Hosur Region</p>
            <p style="font-size: 1.1rem; color: var(--text-muted); margin-bottom: 2rem;">50+ Successful Projects | Luxury Living Spaces | Expert Real Estate Solutions</p>
            <div class="hero-buttons">
                <button class="btn-primary" onclick="scrollToForm()">Book Your Dream Villa</button>
                <button class="btn-secondary" onclick="document.getElementById('projectsSection').scrollIntoView({behavior: 'smooth'})">Explore Projects</button>
            </div>
        </div>
    </section>

    <!-- Business Info Section -->
    <section class="info-section">
        <div class="info-grid">
            <div class="info-card">
                <h4>👤 Owner</h4>
                <p>P. Teekaraman</p>
            </div>
            <div class="info-card">
                <h4>📞 Mobile</h4>
                <p>+91 9962699649</p>
            </div>
            <div class="info-card">
                <h4>📧 Email</h4>
                <p>teekaraman.ptsjn@gmail.com</p>
            </div>
            <div class="info-card">
                <h4>🏢 Business</h4>
                <p>Muruga Estates</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects-section" id="projects" style="display: none;" id="projectsSection">
        <h2 class="section-title">Our Flagship Projects</h2>
        <p class="section-subtitle">50+ Successful Projects Across Prime Locations</p>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-icon">👑</div>
                <h3>Chola's Empire</h3>
                <p>Premium luxury villas with world-class amenities</p>
                <p style="font-size: 0.9rem; color: var(--primary-gold);">Hosur Rayakottai Road</p>
            </div>
            <div class="project-card">
                <div class="project-icon">🌃</div>
                <h3>Vartika</h3>
                <p>Royal villa community with exclusive features</p>
                <p style="font-size: 0.9rem; color: var(--primary-gold);">Hosur Thally Road</p>
            </div>
            <div class="project-card">
                <div class="project-icon">🏛️</div>
                <h3>Temple Town</h3>
                <p>Duplex villas in serene surroundings</p>
                <p style="font-size: 0.9rem; color: var(--primary-gold);">Hosur Alasanatham</p>
            </div>
            <div class="project-card">
                <div class="project-icon">✨</div>
                <h3>Silverwood</h3>
                <p>Luxury residential complex with club facilities</p>
                <p style="font-size: 0.9rem; color: var(--primary-gold);">Multiple Locations</p>
            </div>
            <div class="project-card">
                <div class="project-icon">🏠</div>
                <h3>Premium Villas</h3>
                <p>2-4 BHK luxury apartments and villas</p>
                <p style="font-size: 0.9rem; color: var(--primary-gold);">Across Hosur Region</p>
            </div>
            <div class="project-card">
                <div class="project-icon">🌍</div>
                <h3>Land Sales</h3>
                <p>Prime residential and commercial plots</p>
                <p style="font-size: 0.9rem; color: var(--primary-gold);">Premium Locations</p>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="info-section" id="about">
        <div style="max-width: 1400px; margin: 0 auto;">
            <h2 class="section-title">About Muruga Estates</h2>
            <p style="text-align: center; color: var(--text-muted); margin-top: 2rem; max-width: 800px; margin-left: auto; margin-right: auto; line-height: 1.8;">
                With over 50-60 successfully completed projects, Muruga Estates stands as a beacon of trust and excellence in real estate. 
                Our portfolio includes Premium Villas, Luxury Apartments, Duplex Units, Royal Residences, Club Houses, and Prime Lands across 
                Hosur Rayakottai Road, Hosur Thally Road, Hosur Alasanatham, and other premium locations. We are committed to delivering 
                world-class living spaces that exceed expectations.
            </p>
        </div>
    </section>

    <!-- Registration Form Section -->
    <section class="registration-section" id="contact">
        <h2 class="section-title">Register for Property Booking</h2>
        <p class="section-subtitle" style="margin-top: -1rem;">Get Your Dream Property Today</p>

        <div class="form-container">
            <form id="registrationForm" onsubmit="handleFormSubmit(event)">
                <div class="form-row">
                    <div class="form-group">
                        <label for="fullName">Full Name *</label>
                        <input type="text" id="fullName" name="fullName" required placeholder="Enter your full name">
                    </div>
                    <div class="form-group">
                        <label for="contactNumber">Contact Number *</label>
                        <input type="tel" id="contactNumber" name="contactNumber" required placeholder="Enter your mobile number">
                    </div>
                </div>

                <div class="form-group form-row-full">
                    <label for="emailId">Email Address *</label>
                    <input type="email" id="emailId" name="emailId" required placeholder="Enter your email address">
                </div>

                <div class="form-row">
                    <div class="form-group">
                        <label for="priceRange">Budget (Price Range) *</label>
                        <select id="priceRange" name="priceRange" required>
                            <option value="">Select Price Range</option>
                            <option value="95 Lakhs">95 Lakhs</option>
                            <option value="96 Lakhs">96 Lakhs</option>
                            <option value="98 Lakhs">98 Lakhs</option>
                            <option value="1 Crore">1 Crore</option>
                            <option value="1.1 Crore">1.1 Crore</option>
                            <option value="1.2 Crore">1.2 Crore</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="location">Preferred Location *</label>
                        <select id="location" name="location" required>
                            <option value="">Select Location</option>
                            <option value="Hosur Rayakottai Road">Hosur Rayakottai Road</option>
                            <option value="Hosur Thally Road">Hosur Thally Road</option>
                            <option value="Hosur Alasanatham">Hosur Alasanatham</option>
                        </select>
                    </div>
                </div>

                <div class="form-row">
                    <div class="form-group">
                        <label for="villaType">Villa Type *</label>
                        <select id="villaType" name="villaType" required>
                            <option value="">Select Villa Type</option>
                            <option value="Premium Villa">Premium Villa</option>
                            <option value="Royal Villa">Royal Villa</option>
                            <option value="Luxury Villa">Luxury Villa</option>
                            <option value="Duplex Villa">Duplex Villa</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="bhk">Number of BHK *</label>
                        <select id="bhk" name="bhk" required>
                            <option value="">Select BHK</option>
                            <option value="2 BHK">2 BHK</option>
                            <option value="3 BHK">3 BHK</option>
                            <option value="4 BHK">4 BHK</option>
                        </select>
                    </div>
                </div>

                <div class="form-group form-row-full">
                    <label for="additionalInfo">Additional Information</label>
                    <textarea id="additionalInfo" name="additionalInfo" rows="4" placeholder="Any specific requirements or queries..."></textarea>
                </div>

                <button type="submit" class="submit-btn">Submit Registration</button>
            </form>
        </div>
    </section>

    <!-- Admin Panel Modal -->
    <div id="adminModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeAdminPanel()">&times;</span>
            <h2 style="color: var(--primary-gold); margin-bottom: 1.5rem;">Admin Panel - Update Profile</h2>

            <div class="admin-panel">
                <div class="admin-section">
                    <h3>Owner Information</h3>
                    <div class="form-group">
                        <label>Owner Name</label>
                        <input type="text" id="adminName" value="P. Teekaraman">
                    </div>
                    <div class="form-group">
                        <label>Mobile Number</label>
                        <input type="tel" id="adminMobile" value="9962699649">
                    </div>
                    <div class="form-group">
                        <label>Email Address</label>
                        <input type="email" id="adminEmail" value="teekaraman.ptsjn@gmail.com">
                    </div>
                </div>

                <div class="admin-section">
                    <h3>Business Information</h3>
                    <div class="form-group">
                        <label>Business Name</label>
                        <input type="text" id="adminBusiness" value="Muruga Estates">
                    </div>
                    <div class="form-group">
                        <label>Business Description</label>
                        <textarea id="adminDescription" rows="4">Premium Real Estate Solutions - 50+ Successful Projects including Villas, Apartments, and Lands</textarea>
                    </div>
                </div>

                <div class="admin-section">
                    <h3>Locations</h3>
                    <div class="form-group">
                        <label>Operating Locations (comma-separated)</label>
                        <textarea id="adminLocations" rows="3">Hosur Rayakottai Road, Hosur Thally Road, Hosur Alasanatham</textarea>
                    </div>
                </div>

                <button class="submit-btn" onclick="saveAdminProfile()" style="background: linear-gradient(135deg, #00d084 0%, #00a860 100%);">Save Changes</button>
            </div>
        </div>
    </div>

    <!-- Success Message -->
    <div class="success-message" id="successMessage">
        ✓ Registration submitted successfully! Our team will contact you soon.
    </div>

    <script>
        // Scroll to form
        function scrollToForm() {
            document.getElementById('contact').scrollIntoView({ behavior: 'smooth' });
        }

        // Admin Panel Functions
        function openAdminPanel() {
            document.getElementById('adminModal').style.display = 'block';
        }

        function closeAdminPanel() {
            document.getElementById('adminModal').style.display = 'none';
        }

        window.onclick = function(event) {
            const modal = document.getElementById('adminModal');
            if (event.target == modal) {
                modal.style.display = 'none';
            }
        }

        function saveAdminProfile() {
            const profileData = {
                ownerName: document.getElementById('adminName').value,
                mobile: document.getElementById('adminMobile').value,
                email: document.getElementById('adminEmail').value,
                businessName: document.getElementById('adminBusiness').value,
                description: document.getElementById('adminDescription').value,
                locations: document.getElementById('adminLocations').value
            };

            // Save to localStorage
            localStorage.setItem('muragaProfile', JSON.stringify(profileData));

            // Send to backend
            fetch('http://localhost:5000/update_profile', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(profileData)
            })
            .then(response => response.json())
            .then(data => {
                showSuccessMessage('Profile updated successfully!');
                setTimeout(() => closeAdminPanel(), 1500);
            })
            .catch(error => console.error('Error:', error));
        }

        // Form Submission
        function handleFormSubmit(event) {
            event.preventDefault();

            const formData = {
                fullName: document.getElementById('fullName').value,
                contactNumber: document.getElementById('contactNumber').value,
                emailId: document.getElementById('emailId').value,
                priceRange: document.getElementById('priceRange').value,
                location: document.getElementById('location').value,
                villaType: document.getElementById('villaType').value,
                bhk: document.getElementById('bhk').value,
                additionalInfo: document.getElementById('additionalInfo').value,
                timestamp: new Date().toLocaleString()
            };

            // Send to backend to save in Excel
            fetch('http://localhost:5000/save_registration', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(formData)
            })
            .then(response => response.json())
            .then(data => {
                showSuccessMessage();
                document.getElementById('registrationForm').reset();
            })
            .catch(error => {
                console.error('Error:', error);
                showSuccessMessage('Registration submitted! (Local save)');
                document.getElementById('registrationForm').reset();
            });
        }

        function showSuccessMessage(customMsg = null) {
            const message = document.getElementById('successMessage');
            if (customMsg) {
                message.textContent = '✓ ' + customMsg;
            }
            message.style.display = 'block';
            setTimeout(() => {
                message.style.display = 'none';
            }, 4000);
        }

        // Load admin profile from localStorage on page load
        window.addEventListener('load', function() {
            const savedProfile = localStorage.getItem('muragaProfile');
            if (savedProfile) {
                const profile = JSON.parse(savedProfile);
                document.getElementById('adminName').value = profile.ownerName;
                document.getElementById('adminMobile').value = profile.mobile;
                document.getElementById('adminEmail').value = profile.email;
                document.getElementById('adminBusiness').value = profile.businessName;
                document.getElementById('adminDescription').value = profile.description;
                document.getElementById('adminLocations').value = profile.locations;
            }
        });
    </script>

</body>
</html>
