<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>My Portfolio - Rohit Naidu</title>
  <link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
  <script src="https://cdn.tailwindcss.com"></script> <style>
    /* Base styles from user, with modifications */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Georgia', 'Times New Roman', Times, serif;
    }

    html {
      scroll-behavior: smooth; /* Enables smooth scrolling for anchor links */
    }

    body {
      color: #ededed;
      background: linear-gradient(to right, #2c003e, #002f7a); /* Global fixed background */
      background-attachment: fixed;
      overflow-x: hidden; /* Prevent horizontal scroll */
    }

    .header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 20px 5%; /* Use percentage for responsiveness */
      background: rgba(13, 13, 13, 0.3); /* Slightly transparent background for depth */
      backdrop-filter: blur(5px); /* Frosted glass effect */
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 1000; /* Increased z-index */
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    }

    .logo {
      font-size: 25px;
      color: #fff;
      text-decoration: none;
      font-weight: 600;
      cursor: pointer; /* Added cursor */
    }

    .navbar a {
      font-size: 18px; /* Adjusted for responsiveness */
      color: #fff;
      text-decoration: none;
      font-weight: 500;
      margin-left: 25px; /* Adjusted for responsiveness */
      transition: color 0.3s ease, transform 0.3s ease;
    }

    .navbar a:hover,
    .navbar a.active { /* Active link styling */
      color: #0ef;
      transform: translateY(-2px);
    }
    
    /* Hamburger Menu for mobile */
    .menu-toggle {
        display: none; /* Hidden by default */
        font-size: 30px;
        color: #fff;
        cursor: pointer;
    }

    /* Base section styling */
    section {
      min-height: 100vh;
      padding: 120px 5% 60px; /* Top padding to account for header, use percentage for side padding */
      display: flex;
      flex-direction: column; /* Align content vertically */
      justify-content: center;
      align-items: center;
      text-align: center; /* Center text by default */
      position: relative; /* For potential pseudo-elements or absolute positioned children */
    }
    
    /* Section specific content wrappers */
    .section-content-wrapper {
        max-width: 800px; /* Max width for content in sections */
        width: 100%;
    }


    .home {
      /* Home section already has specific flex settings, keep them if needed or adjust */
      /* background gradient is now on body */
      flex-direction: row; /* For side-by-side layout on larger screens */
      justify-content: space-around; /* Example for home layout */
      text-align: left;
    }
    
    .home-content {
      max-width: 600px;
      animation: slideInFromLeft 1s ease-out; /* Animation for home content */
    }
    
    @keyframes slideInFromLeft {
        0% { transform: translateX(-100%); opacity: 0; }
        100% { transform: translateX(0); opacity: 1; }
    }

    .home-image img {
        max-width: 350px;
        border-radius: 50%;
        border: 5px solid #0ef;
        box-shadow: 0 0 30px #0ef;
        animation: zoomIn 1s ease-out 0.5s; /* Animation for image */
        opacity: 0; /* Start hidden for animation */
        animation-fill-mode: forwards; /* Keep final state */
    }

    @keyframes zoomIn {
        0% { transform: scale(0.5); opacity: 0; }
        100% { transform: scale(1); opacity: 1; }
    }


    .home-content h1 {
      font-size: clamp(32px, 5vw, 50px); /* Responsive font size */
      margin: 10px 0;
      font-weight: 700;
    }

    .home-content h3 {
      font-size: clamp(24px, 4vw, 30px); /* Responsive font size */
      color: #0ef;
      font-weight: 600;
    }
    .home-content h3 .profession {
        display: inline-block; /* For proper animation */
    }

    .home-content p {
      margin-top: 15px;
      font-size: clamp(16px, 2.5vw, 18px); /* Responsive font size */
      line-height: 1.6;
    }

    .home-sci {
      margin-top: 25px;
      margin-bottom: 30px; /* Added margin bottom */
    }

    .home-sci a {
      display: inline-flex;
      justify-content: center;
      align-items: center;
      width: 40px;
      height: 40px;
      background: transparent;
      border: 2px solid #0ef;
      border-radius: 50%;
      font-size: 20px;
      color: #0ef;
      text-decoration: none;
      margin: 0 10px 10px 0; /* Adjusted margin */
      transition: 0.3s ease;
    }

    .home-sci a:hover {
      background: #0ef;
      color: #0d0d0d;
      box-shadow: 0 0 20px #0ef;
      transform: scale(1.1);
    }

    .btn-box {
      display: inline-block;
      padding: 12px 28px;
      background: #0ef;
      color: #0d0d0d;
      border-radius: 8px;
      font-size: 16px; /* Added font size */
      font-weight: 600; /* Adjusted font weight */
      text-decoration: none;
      transition: 0.3s ease;
      letter-spacing: 1px;
      border: 2px solid #0ef; /* Added border for consistency */
    }

    .btn-box:hover {
      background: transparent;
      color: #0ef;
      box-shadow: 0 0 25px #0ef, 0 0 50px #0ef;
    }

    /* General Section Heading */
    .section-heading {
      font-size: clamp(30px, 5vw, 45px);
      color: #fff;
      margin-bottom: 40px;
      position: relative;
      padding-bottom: 10px;
    }
    .section-heading span {
      color: #0ef;
    }
    .section-heading::after {
      content: '';
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      bottom: 0;
      width: 80px;
      height: 4px;
      background-color: #0ef;
      border-radius: 2px;
    }

    /* About Section */
    #about {
        /* background-color: rgba(0,0,0,0.1); /* Subtle overlay if needed */
    }
    .about-content {
      display: flex;
      flex-direction: column; /* Stack image and text on small screens */
      align-items: center;
      gap: 30px;
      text-align: left; /* Align text to left for readability */
    }
    .about-image img {
      max-width: 300px;
      width: 100%;
      border-radius: 15px;
      border: 3px solid #0ef;
      box-shadow: 0 0 20px rgba(0, 238, 255, 0.5);
    }
    .about-text p {
      font-size: clamp(15px, 2.2vw, 17px);
      line-height: 1.7;
      margin-bottom: 15px;
    }
    .about-text .highlight {
        color: #0ef;
        font-weight: 600;
    }

    /* Skills Section */
    .skills-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); /* Responsive grid */
      gap: 30px;
      width: 100%;
      margin-top: 20px;
    }
    .skill-item {
      background: rgba(255, 255, 255, 0.05); /* Subtle background for skill items */
      padding: 20px;
      border-radius: 10px;
      border: 1px solid rgba(0, 238, 255, 0.2);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .skill-item:hover {
      transform: translateY(-10px);
      box-shadow: 0 10px 30px rgba(0, 238, 255, 0.3);
    }
    .skill-name {
      font-size: 20px;
      font-weight: 600;
      color: #0ef;
      margin-bottom: 10px;
    }
    .skill-bar-container {
      width: 100%;
      height: 20px; /* Increased height for better visibility */
      background-color: rgba(0,0,0,0.2);
      border-radius: 10px;
      overflow: hidden;
      border: 1px solid #0ef; /* Added border */
    }
    .skill-bar {
      height: 100%;
      background-color: #0ef;
      border-radius: 8px; /* Slightly less than container for inset look */
      width: 0; /* Initial width, will be set by JS or hover */
      transition: width 0.8s ease-in-out, background-color 0.3s ease;
    }
    .skill-item:hover .skill-bar {
      /* Example: width: 90%;  This will be handled by JS for specific percentages */
      /* For "rise" effect, we can play with box-shadow on skill-item or transform */
    }
    /* Individual skill levels (can be set via JS) */
    .skill-bar.html-skill { width: 90%; }
    .skill-bar.css-skill { width: 85%; }
    .skill-bar.js-skill { width: 75%; }
    .skill-bar.sql-skill { width: 80%; }
    .skill-bar.powerbi-skill { width: 70%; }
    .skill-bar.tableau-skill { width: 65%; }

    /* Portfolio Section */
    .portfolio-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        gap: 25px;
        margin-top: 20px;
    }
    .portfolio-item {
        background: rgba(255, 255, 255, 0.05);
        border: 1px solid rgba(0, 238, 255, 0.2);
        border-radius: 10px;
        overflow: hidden;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .portfolio-item:hover {
        transform: translateY(-10px) scale(1.03);
        box-shadow: 0 10px 30px rgba(0, 238, 255, 0.3);
    }
    .portfolio-item img {
        width: 100%;
        height: 200px;
        object-fit: cover;
        display: block;
    }
    .portfolio-item-content {
        padding: 15px;
    }
    .portfolio-item-content h4 {
        color: #0ef;
        font-size: 18px;
        margin-bottom: 8px;
    }
    .portfolio-item-content p {
        font-size: 14px;
        color: #ccc; /* Lighter text for description */
        line-height: 1.5;
    }


    /* Contact Section */
    .contact-container {
      display: flex;
      flex-direction: column; /* Stack items on small screens */
      gap: 25px;
      align-items: center; /* Center items */
      margin-top: 20px;
      width: 100%;
      max-width: 500px; /* Limit width of contact items container */
    }
    .contact-item {
      display: flex;
      align-items: center;
      gap: 15px;
      background: rgba(255, 255, 255, 0.05);
      padding: 15px 20px;
      border-radius: 8px;
      border: 1px solid rgba(0, 238, 255, 0.2);
      width: 100%; /* Make items take full width of container */
      transition: background-color 0.3s ease;
    }
    .contact-item:hover {
        background: rgba(0, 238, 255, 0.1);
    }
    .contact-item i {
      font-size: 28px;
      color: #0ef;
    }
    .contact-item p, .contact-item a {
      font-size: 17px;
      color: #ededed;
      text-decoration: none;
    }
    .contact-item a:hover {
      color: #0ef;
    }
    
    /* Footer */
    .footer {
        padding: 20px 5%;
        text-align: center;
        background: rgba(13, 13, 13, 0.5); /* Consistent with header */
        border-top: 1px solid rgba(255, 255, 255, 0.1);
        margin-top: auto; /* Push to bottom if content is short */
    }
    .footer p {
        color: #aaa;
        font-size: 14px;
    }
    .footer p a {
        color: #0ef;
        text-decoration: none;
    }
    .footer p a:hover {
        text-decoration: underline;
    }

    /* Responsive adjustments */
    @media (max-width: 768px) {
      .navbar {
        display: none; /* Hide navbar */
        position: absolute;
        top: 100%; /* Position below header */
        left: 0;
        width: 100%;
        background: rgba(13, 13, 13, 0.9); /* Darker background for mobile menu */
        flex-direction: column;
        padding: 10px 0;
        border-top: 1px solid rgba(0, 238, 255, 0.2);
      }
      .navbar.active {
        display: flex; /* Show navbar when active */
      }
      .navbar a {
        margin: 10px 0;
        text-align: center;
        width: 100%;
        padding: 10px 0;
      }
      .navbar a:hover {
          background-color: rgba(0, 238, 255, 0.1);
      }
      .menu-toggle {
        display: block; /* Show hamburger icon */
      }
      .home {
        flex-direction: column; /* Stack content on smaller screens */
        text-align: center; /* Center text for stacked layout */
      }
      .home-content {
          text-align: center; /* Ensure text is centered on mobile */
          margin-bottom: 30px;
      }
      .home-image {
          margin-top: 30px;
      }
      .home-image img {
          max-width: 250px; /* Smaller image on mobile */
      }
      .about-content {
        flex-direction: column;
        text-align: center;
      }
      .about-text {
        text-align: justify; /* Justify for better readability on mobile */
        padding: 0 10px;
      }
    }

    @media (max-width: 480px) {
        .header { padding: 15px 3%; }
        section { padding: 100px 3% 40px; }
        .home-content h1 { font-size: 28px; }
        .home-content h3 { font-size: 20px; }
        .home-content p { font-size: 14px; }
        .section-heading { font-size: 26px; }
        .skill-item { padding: 15px; }
        .skill-name { font-size: 18px; }
        .skill-bar-container { height: 18px; }
        .contact-item p, .contact-item a { font-size: 15px; }
    }

  </style>
</head>
<body>

  <header class="header">
    <a href="#home" class="logo">Rohit Naidu</a>
    <i class='bx bx-menu menu-toggle'></i>
    <nav class="navbar">
      <a href="#home" class="active">Home</a>
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#portfolio">Portfolio</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section class="home" id="home">
    <div class="home-content">
      <h3>Hello, It's Me</h3>
      <h1>Rohit Naidu</h1>
      <h3>And I'm a <span class="profession"></span></h3>
      <p>I'm a passionate web designer with a strong foundation in HTML, CSS, and responsive design.<br>
         Eager to create clean, user-friendly websites and grow in a creative development environment.</p>
      <div class="home-sci">
        <a href="#" target="_blank" aria-label="Facebook"><i class='bx bxl-facebook'></i></a>
        <a href="#" target="_blank" aria-label="Instagram"><i class='bx bxl-instagram'></i></a>
        <a href="#" target="_blank" aria-label="WhatsApp"><i class='bx bxl-whatsapp'></i></a>
        <a href=" https://www.linkedin.com/in/rohitdasari1" target="_blank" aria-label="LinkedIn"><i class='bx bxl-linkedin'></i></a>
      </div>
      <a href="#about" class="btn-box">More About Me</a>
    </div>
    <div class="home-image">
        <img src="https://placehold.co/400x400/0ef/0d0d0d?text=Rohit" alt="Rohit Naidu - Placeholder Image">
    </div>
  </section>

  <section class="about" id="about">
    <div class="section-content-wrapper">
        <h2 class="section-heading">About <span>Me</span></h2>
        <div class="about-content">
            <div class="about-image">
                <img src="/Images/Passpoert Size Photo.jpg" alt="About Rohit Naidu">
            </div>
            <div class="about-text">
                <p>Hello! I'm Rohit Naidu, a dedicated and enthusiastic web designer based in Visakhapatna. My journey into web design started with a fascination for how websites could blend creativity with functionality to deliver engaging user experiences.</p>
                <p>I specialize in front-end development, focusing on <span class="highlight">HTML, CSS, and JavaScript</span> to build responsive and visually appealing websites. I believe in the power of clean code and intuitive design to make the web a more accessible and enjoyable place for everyone.</p>
                <p>Beyond web design, I'm also keen on data visualization and have been exploring tools like <span class="highlight">Power BI and Tableau</span> to turn complex data into understandable insights. My analytical skills extend to <span class="highlight">SQL</span> for data querying and management. I'm a lifelong learner, always excited to pick up new technologies and improve my craft. When I'm not coding, I enjoy playing cricket and drawings .</p>
                <p>I'm currently looking for opportunities to contribute my skills to innovative projects and collaborate with talented teams. Let's create something amazing together!</p>
            </div>
        </div>
    </div>
  </section>

  <section class="skills" id="skills">
    <div class="section-content-wrapper">
        <h2 class="section-heading">My <span>Skills</span></h2>
        <div class="skills-container">
          <div class="skill-item">
            <div class="skill-name">HTML 90%</div>
            <div class="skill-bar-container"><div class="skill-bar html-skill" data-skill="90%"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name">CSS 85%</div>
            <div class="skill-bar-container"><div class="skill-bar css-skill" data-skill="85%"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name">JavaScript 75%</div>
            <div class="skill-bar-container"><div class="skill-bar js-skill" data-skill="75%"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name">SQL 90%</div>
            <div class="skill-bar-container"><div class="skill-bar sql-skill" data-skill="80%"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name">Power BI 70%</div>
            <div class="skill-bar-container"><div class="skill-bar powerbi-skill" data-skill="70%"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name">Tableau 65%</div>
            <div class="skill-bar-container"><div class="skill-bar tableau-skill" data-skill="65%"></div></div>
          </div>
        </div>
    </div>
  </section>

  <section class="portfolio" id="portfolio">
    <div class="section-content-wrapper">
        <h2 class="section-heading">My <span>Portfolio</span></h2>
        <div class="portfolio-grid">
            <div class="portfolio-item">
                <img src="https://images.pexels.com/photos/6214155/pexels-photo-6214155.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Project Alpha">
                <div class="portfolio-item-content">
                    <h4>Ecommerce </h4>
                    <p>A brief description of Ecommerce, highlighting key technologies and features. (e.g., Responsive e-commerce site)</p>
                    <div><a href="https://github.com/Dasarirohi/Olist-E-Commarces-Store-Analysis" target="_blank"> press Her to get my project file </a></div>
                </div>
            </div>
            <div class="portfolio-item">
                <img src="https://media.istockphoto.com/id/1357021263/photo/indian-five-hundred-rupee-notes-in-a-sack-cloth.jpg?b=1&s=612x612&w=0&k=20&c=Z9MTXd9_37kQDoJ5DGMBnF8D54Qb_IRZ1PzJH4mYx9k=" alt="Project Beta">
                <div class="portfolio-item-content">
                    <h4>Bank Loan </h4>
                    <p>Description for Project bank loan (e.g., Interactive data visualization dashboard using Tableau/Power BI)</p>
                    <div><a href="https://github.com/Dasarirohi/Bank-Analyst" target="_blank"> press Her to get my project file </a></div>
                </div>
            </div>
            <div class="portfolio-item">
                <img src="https://images.pexels.com/photos/326514/pexels-photo-326514.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Project Gamma">
                <div class="portfolio-item-content">
                    <h4>creating website </h4>
                    <p>Description for Project Gamma. (e.g., Personal blog platform with custom CSS animations)</p>
                </div>
            </div>
            <div class="portfolio-item">
                <img src="https://images.pexels.com/photos/3184639/pexels-photo-3184639.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Project Beta">
                <div class="portfolio-item-content">
                    <h4> HR Analytics </h4>
                    <p>Description for  HR Analytics  (e.g., Interactive data visualization dashboard using Tableau/Power BI)</p>
                </div>
            </div>
        </div>
        <p style="margin-top: 30px; font-style: italic;">More projects coming soon...</p>
    </div>
  </section>

  <section class="contact" id="contact">
    <div class="section-content-wrapper">
        <h2 class="section-heading">Contact <span>Me</span></h2>
        <div class="contact-container">
          <div class="contact-item">
            <i class='bx bxs-phone'></i>
            <a href="tel:6305710257">+91 6305710257</a>
          </div>
          <div class="contact-item">
            <i class='bx bxs-envelope'></i>
            <a href="https://mailto:rohitdasari41@gmail.com">rohitdasari41@gmail.com</a>
          </div>
          <div class="contact-item">
            <i class='bx bxl-linkedin-square'></i>
            <a href=" https://www.linkedin.com/in/rohitdasari1" target="_blank">linkedin.com/in/rohitdasari1</a> </div>
        </div>
        <p style="margin-top:30px;">Feel free to reach out. I'm always open to discussing new projects or opportunities!</p>
    </div>
  </section>
  
  <footer class="footer">
      <p>&copy; <span id="currentYear"></span> Rohit Naidu. All Rights Reserved.</p>
      <p>Designed with <i class='bx bxs-heart' style="color: #0ef;"></i> by Rohit Naidu</p>
  </footer>

  <script>
    // Typed.js functionality (simple version)
    const professionSpan = document.querySelector('.home-content .profession');
    const professions = ["Web Designer", "Developer", "Data Enthusiast", "Problem Solver"];
    let currentProfessionIndex = 0;
    let currentCharIndex = 0;
    let isDeleting = false;
    const typingSpeed = 100;
    const deletingSpeed = 50;
    const delayBetweenProfessions = 1500;

    function type() {
      const currentProfession = professions[currentProfessionIndex];
      if (isDeleting) {
        professionSpan.textContent = currentProfession.substring(0, currentCharIndex - 1);
        currentCharIndex--;
      } else {
        professionSpan.textContent = currentProfession.substring(0, currentCharIndex + 1);
        currentCharIndex++;
      }

      if (!isDeleting && currentCharIndex === currentProfession.length) {
        isDeleting = true;
        setTimeout(type, delayBetweenProfessions);
      } else if (isDeleting && currentCharIndex === 0) {
        isDeleting = false;
        currentProfessionIndex = (currentProfessionIndex + 1) % professions.length;
        setTimeout(type, typingSpeed);
      } else {
        setTimeout(type, isDeleting ? deletingSpeed : typingSpeed);
      }
    }
    // Start typing animation when the document is loaded
    document.addEventListener('DOMContentLoaded', () => {
        if (professionSpan) { // Check if the element exists
             setTimeout(type, typingSpeed);
        }
        // Set current year in footer
        document.getElementById('currentYear').textContent = new Date().getFullYear();

        // Hamburger menu toggle
        const menuToggle = document.querySelector('.menu-toggle');
        const navbar = document.querySelector('.navbar');

        if(menuToggle && navbar) {
            menuToggle.addEventListener('click', () => {
                navbar.classList.toggle('active');
                // Toggle icon
                if (navbar.classList.contains('active')) {
                    menuToggle.classList.remove('bx-menu');
                    menuToggle.classList.add('bx-x');
                } else {
                    menuToggle.classList.remove('bx-x');
                    menuToggle.classList.add('bx-menu');
                }
            });
        }
        
        // Close mobile menu when a link is clicked
        const navLinks = document.querySelectorAll('.navbar a');
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                if (navbar.classList.contains('active')) {
                    navbar.classList.remove('active');
                    menuToggle.classList.remove('bx-x');
                    menuToggle.classList.add('bx-menu');
                }
            });
        });


        // Active navbar link highlighting on scroll
        const sections = document.querySelectorAll('section');
        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                // Adjust offset if header is fixed, e.g., sectionTop - headerHeight
                if (pageYOffset >= (sectionTop - sectionHeight / 3) ) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });
             // Fallback for top of page
            if (pageYOffset < sections[0].offsetTop - sections[0].clientHeight / 3) {
                navLinks.forEach(link => link.classList.remove('active'));
                const homeLink = document.querySelector('.navbar a[href="#home"]');
                if (homeLink) homeLink.classList.add('active');
            }
        });


        // Skill bars animation on hover (or could be on scroll into view)
        const skillItems = document.querySelectorAll('.skill-item');
        skillItems.forEach(item => {
            const bar = item.querySelector('.skill-bar');
            const skillLevel = bar.getAttribute('data-skill');
            
            // Set initial width for CSS animation to take effect from 0
            // The CSS already sets this, but this is for direct manipulation if needed
            // bar.style.width = '0%'; 

            // Animate on hover (already handled by CSS for simplicity)
            // If you want JS-controlled animation on hover:
            item.addEventListener('mouseenter', () => {
                 bar.style.width = skillLevel; // This will trigger the CSS transition
            });
            // item.addEventListener('mouseleave', () => {
            //    bar.style.width = '0%'; // Optional: reset on mouse leave
            // });

            // Alternative: Animate when skill section is in view
            // This is a more robust way to ensure animation happens once visible
            const observer = new IntersectionObserver(entries => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        bar.style.width = skillLevel;
                        observer.unobserve(item); // Stop observing once animated
                    }
                });
            }, { threshold: 0.5 }); // Trigger when 50% of item is visible

            observer.observe(item);
        });
    });

  </script>
</body>
</html>
