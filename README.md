<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Spark Media</title>
    <!-- AOS CSS for Scroll Animations -->
    <link href="https://cdn.jsdelivr.net/npm/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <style>
        /* General Styles */
        body, html {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            height: 100%;
            /* Gradient Background for Entire Website */
            background: linear-gradient(135deg, #007bff, #6a1b9a, #ff4081);
            background-size: 400% 400%;
            animation: gradientAnimation 15s ease infinite;
            color: white;
        }

        /* Keyframes for background gradient animation */
        @keyframes gradientAnimation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Header and Search Bar Styles */
        header {
            background-color: rgba(26, 26, 26, 0.9); /* Semi-transparent black */
            padding: 10px;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            text-align: center;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* Logo in Header */
        .logo {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .logo h1 {
            margin: 0;
            font-size: 24px;
            text-align: center;
        }

        .logo h1 span {
            display: block;
        }

        /* Navigation Menu */
        nav {
            margin-right: 20px;
        }

        .header nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
        }

        .header nav ul li {
            display: inline;
            margin: 0 15px;
        }

        .header nav ul li a {
            color: white;
            text-decoration: none;
        }

        .header nav ul li a:hover {
            color: #ff4081;
        }

        /* Search Bar Styles */
        .search-bar {
            display: flex;
            justify-content: flex-end;
            position: absolute;
            right: 20px;
        }

        .search-bar input {
            width: 0;
            padding: 10px;
            border: none;
            border-radius: 4px;
            transition: width 0.5s;
            opacity: 0;
            font-size: 16px;
        }

        .search-bar.active input {
            width: 200px;
            opacity: 1;
        }

        .search-bar button {
            background: none;
            border: none;
            cursor: pointer;
        }

        .menu-icon {
            width: 24px;
            height: 24px;
            display: inline-block;
            position: relative;
            cursor: pointer;
        }

        .menu-icon .bar {
            background-color: #999;
            height: 3px;
            width: 100%;
            position: absolute;
            left: 0;
            transition: 0.3s ease;
        }

        .menu-icon .bar:nth-child(1) {
            top: 0;
        }

        .menu-icon .bar:nth-child(2) {
            top: 10px;
        }

        .menu-icon .bar:nth-child(3) {
            top: 20px;
        }

        /* Title Section with Gradient */
        .title-section {
            padding: 100px 0;
            text-align: center;
            margin-top: 70px;
        }

        .title-section h2 {
            font-size: 48px;
        }

        .primary-button {
            background-color: #000;
            color: white;
            padding: 10px 20px;
            border: none;
            text-decoration: none;
            font-size: 18px;
            margin-top: 20px;
            display: inline-block;
        }

        .primary-button:hover {
            background-color: #333;
        }

        /* Sections */
        .section {
            padding: 80px 0;
            text-align: center;
            background-color: rgba(255, 255, 255, 0.1); /* Semi-transparent white */
            margin: 20px 0;
        }

        .about-section,
        .contact-section {
            background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent black */
            color: white;
        }

        .container {
            width: 80%;
            margin: 0 auto;
        }

        h2 {
            font-size: 36px;
            margin-bottom: 20px;
        }

        p {
            font-size: 18px;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .service-box {
            margin-bottom: 30px;
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.5s ease-in-out;
        }

        .fade-in.in-view {
            opacity: 1;
            transform: translateY(0);
        }

        /* Image Animation */
        .image-container img {
            width: 100%;
            height: auto;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }

        .image-container img.in-view {
            opacity: 1;
        }

        /* Footer */
        footer {
            background-color: rgba(26, 26, 26, 0.9);
            color: white;
            text-align: center;
            padding: 20px 0;
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header class="header">
        <!-- Logo -->
        <div class="logo">
            <h1><span>Grid</span><span>Spark Media</span></h1>
        </div>

        <!-- Navigation Menu -->
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>

        <!-- Search Bar in Header -->
        <div class="search-bar" id="searchBar">
            <input type="text" placeholder="Search...">
        </div>

        <!-- Menu Icon for toggling search bar -->
        <div class="menu-icon" onclick="toggleSearchBar()">
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
        </div>
    </header>

    <!-- Title Section -->
    <section id="home" class="title-section" data-aos="fade-up">
        <div class="container">
            <h2>Your Partner for Digital Success</h2>
            <p>Creating cutting-edge websites and innovative advertising solutions.</p>
            <a href="#about" class="primary-button">About Us</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about-section section">
        <div class="container" data-aos="fade-up">
            <h2>About Us</h2>

            <!-- Image of Laptop -->
            <div class="image-container">
                <div class="laptop-image">
                    <img src="https://via.placeholder.com/1200x800" alt="Laptop Image">
                </div>
            </div>

            <p>At Grid Spark Media, we specialize in creating cutting-edge websites and innovative advertising solutions tailored to elevate your brand in the digital world.</p>
            <p>Our team of creative designers, experienced developers, and marketing experts work collaboratively to ensure that every project we take on not only meets your needs but exceeds expectations. From custom website builds to full-scale digital advertising campaigns, we harness the power of technology and creativity to spark growth and visibility for your business.</p>
            <p>Whether you're looking to build a professional website, optimize your existing one, or launch a targeted advertising campaign, Grid Spark Media is your partner in turning your digital vision into reality.</p>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services-section section">
        <div class="container" data-aos="fade-up">
            <h2>Our Services</h2>
            <div class="service-box">
                <h3>Website Development</h3>
                <p>Custom websites built to meet your needs and exceed your expectations.</p>
            </div>
            <div class="service-box">
                <h3>Digital Advertising</h3>
                <p>Targeted campaigns to increase visibility and drive results.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact-section section">
        <div class="container" data-aos="fade-up">
            <h2>Contact</h2>
            <p>Email: gridsparkmedia@gmail.com</p>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>Grid Spark Media © 2024 - All Rights Reserved</p>
    </footer>

    <!-- AOS JS for Scroll Animations -->
    <script src="https://cdn.jsdelivr.net/npm/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({
            duration: 1000, // Animation duration in milliseconds
            once: false, // Set to false to replay animations
        });

        // Toggle the search bar on click
        function toggleSearchBar() {
            document.getElementById('searchBar').classList.toggle('active');
        }
    </script>
</body>
</html>