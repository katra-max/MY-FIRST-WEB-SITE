<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Adam Quatra - Hacker Style</title>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet" />
  <style>
    :root {
      --color-bg-dark: #0e0e0e;
      --color-bg-light: #f9f9f9;
      --color-text-dark: #f1c40f;
      --color-text-light: #22222;
      --color-section-bg-dark: rgba(34, 34, 34, 0.85);
      --color-section-bg-light: rgba(255, 255, 255, 0.85);
      --color-section-border-dark: #f1c40f;
      --color-section-border-light: #f1c40f;
    }
    body {
      margin: 0;
      font-family: 'Courier New', monospace;
      background-color: var(--color-bg-dark);
      color: var(--color-text-dark);
      overflow-x: hidden;
      padding-top: 60px;
      transition: background-color 0.5s, color 0.5s;
    }
    body.light-theme {
      background-color: var(--color-bg-light);
      color: var(--color-text-light);
    }
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      background-color: #111;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
      box-shadow: 0 2px 10px #000;
      padding: 10px 0;
      transition: background-color 0.5s;
    }
    body.light-theme nav {
      background-color: #e3e3e3;
      box-shadow: 0 2px 10px #bbb;
    }
    .navbar {
      list-style: none;
      display: flex;
      gap: 30px;
      padding: 0;
      margin: 0;
      flex-grow: 1;
      justify-content: center;
    }
    .navbar a {
      color: var(--color-text-dark);
      text-decoration: none;
      font-weight: bold;
      font-size: 1.1em;
      transition: 0.3s;
    }
    body.light-theme .navbar a {
      color: var(--color-text-light);
    }
    .navbar a:hover {
      color: #ffffff;
    }
    body.light-theme .navbar a:hover {
      color: #3498db;
    }
    section {
      max-width: 800px;
      margin: 60px auto;
      background: var(--color-section-bg-dark);
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0 0 20px var(--color-section-border-dark);
      text-align: center;
      position: relative;
      z-index: 10;
      border: 4px solid var(--color-section-border-dark);
      color: var(--color-text-dark);
      transition: background 0.5s, color 0.5s, border-color 0.5s;
    }
    body.light-theme section {
      background: var(--color-section-bg-light);
      border-color: var(--color-section-border-light);
      color: var(--color-text-light);
      box-shadow: 0 0 20px var(--color-section-border-light);
    }
    section h1 {
      font-size: 2em;
      color: inherit;
      text-shadow: 0 0 10px currentColor;
    }
    section h2 {
      color: #f39c12;
      font-style: italic;
      margin-bottom: 20px;
      transition: color 0.5s;
    }
    body.light-theme section h2 {
      color: #2980b9;
    }
    section p {
      font-size: 1.1em;
      line-height: 1.6em;
      color: inherit;
    }
    section img {
      margin-top: 20px;
      max-width: 100%;
      border: 4px solid currentColor;
      border-radius: 15px;
      box-shadow: 0 0 25px #f39c12;
      transition: border-color 0.5s;
    }
    body.light-theme section img {
      box-shadow: 0 0 25px #2980b9;
    }
    .social-links {
      margin-top: 15px;
    }
    .social-links a {
      margin: 0 15px;
      font-size: 2em;
      color: var(--color-text-dark);
      text-decoration: none;
      transition: 0.3s;
    }
    body.light-theme .social-links a {
      color: var(--color-text-light);
    }
    .social-links a:hover {
      color: #fff;
    }
    body.light-theme .social-links a:hover {
      color: #2980b9;
    }
    footer {
      text-align: center;
      margin-top: 50px;
      color: #999;
      font-size: 0.9em;
      z-index: 10;
      position: relative;
      transition: color 0.5s;
    }
    body.light-theme footer {
      color: #555;
    }
    .animated-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(#1a1a1a, #000);
      z-index: 0;
      overflow: hidden;
      transition: background 0.5s;
    }
    body.light-theme .animated-bg {
      background: radial-gradient(#ddd, #fff);
    }
    .animated-bg::before {
      content: "";
      position: absolute;
      width: 200%;
      height: 200%;
      background-image: repeating-linear-gradient(0deg, #f1c40f 0px, #f1c40f 2px, transparent 2px, transparent 8px);
      animation: scroll 8s linear infinite;
      opacity: 0.04;
      transition: background-color 0.5s;
    }
    body.light-theme .animated-bg::before {
      background-image: repeating-linear-gradient(0deg, #2980b9 0px, #2980b9 2px, transparent 2px, transparent 8px);
    }
    @keyframes scroll {
      0% { transform: translateY(0); }
      100% { transform: translateY(-100px); }
    }
    @media (max-width: 600px) {
      .navbar {
        gap: 15px;
      }
      section {
        margin: 40px 15px;
      }
    }

    /* Top Button */
    #topBtn {
      display: none;
      position: fixed;
      bottom: 30px;
      right: 30px;
      z-index: 1001;
      font-size: 24px;
      border: none;
      outline: none;
      background-color:black;
      color: var(--color-text-dark);
      cursor:pointerr;
      padding: 12px 18px;
      border-radius: 50%;
      box-shadow: 0 0 10px var(--color-section-border-dark);
      transition: background-color 0.3s, color 0.3s;
    }
    #topBtn:hover {
      background-color:black;
      color: var(--color-section-border-dark);
    }
    body.light-theme #topBtn {
      background-color:skyblue;
      color:black;
      box-shadow: 0 0 10px var(--color-section-border-light);
    }
    body.light-theme #topBtn:hover {
      background-color:Yellow;
      color:skyblue;
    }

    /* Theme Toggle Button */
    #themeToggle {
      position: fixed;
      top: 12px;
      right: 12px;
      z-index: 1100;
      background-color:black;
      border: ;
      color: var(--color-text-dark);
      font-size: 20px;
      cursor:pointer;
      padding: 8px 12px;
      border-radius: 6px;
      box-shadow: 0 0 10px var(--color-section-border-dark);
      transition: background-color 0.3s, color 0.3s;
    }
    #themeToggle:hover {
      background-color:black;
      color: var(--color-section-border-dark);
    }
    body.light-theme #themeToggle {
      background-color: var(--color-section-border-light);
      color: var(--color-text-light);
      box-shadow: 0 0 10px var(--color-section-border-light);
    }
    body.light-theme #themeToggle:hover {
      background-color: black;
      color:skyblue;
    }
  </style>
</head>
<body>
  <div class="animated-bg"></div>

  <nav>
    <ul class="navbar">
      <li><a href="#about">About Me</a></li>
      <li><a href="#hobbies">Hobbies</a></li>
      <li><a href="#goals">Goals</a></li>
      <li><a href="#youtube">YouTube</a></li>
      <li><a href="#funfacts">Fun Facts</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <button id="themeToggle" title="Toggle Light/Dark Theme"><i class="fas fa-adjust"></i></button>
  <button id="topBtn" title="Go to Top"><i class="fas fa-arrow-up"></i></button>

  <section id="about">
    <h1>About Me</h1>
    <h2>Get to know Adam Quatra</h2>
    <p>My name is <strong>Adam Quatra</strong>, I'm <strong>14 years old</strong> and I live in <strong>Morocco</strong>. I'm passionate about <strong>coding, tech</strong>, innovation and <strong>Science fiction</strong>.</p>
     <img src="https://cdn-icons-png.flaticon.com/512/3135/3135715.png" alt="Person Icon" />
  </section>

  <section id="hobbies">
    <h1>Hobbies</h1>
    <h2>What I love to do</h2>
    <p>I enjoy <strong>programming, gaming</strong>, creating <strong>websites</strong>, watching <strong>tech</strong> content, and exploring <strong>new thinks</strong> .</p>
    <img src="https://cdn-icons-png.flaticon.com/512/1006/1006553.png" alt="Programming and Gaming Icon" />
  </section>

  <section id="goals">
    <h1>Goals</h1>
    <h2>My ambitions</h2>
    <p>My goals include mastering <strong>web development</strong>, learning <strong>AI</strong>, building <strong>cool projects, apps, or Websites</strong> that make life easier.</p>
    <img src="https://cdn-icons-png.flaticon.com/512/3135/3135793.png" alt="Goals Icon" />
  </section>

  <section id="youtube">
    <h1>YouTube Channel</h1>
    <h2>Follow me on YouTube</h2>
    <p>I share <strong>content and storys</strong> generated by <strong>AI</strong> tools on my <strong>YouTube channel</strong>.</p>
     <img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="YouTube Icon" />
  </section>

  <section id="funfacts">
    <h1>Fun Facts</h1>
    <h2>Did you know?</h2>
    <p>I'm fascinated by <strong>Science fiction</strong> and <strong>Useful games</strong></p>
      <img src="https://cdn-icons-png.flaticon.com/512/4727/4727495.png" alt="Fun Facts Icon" />
  </section>

  <section id="skills">
    <h1>Skills</h1>
    <h2>What I know</h2>
    <p>HTML, CSS, JavaScript, Python basics.</p>
      <img src="https://cdn-icons-png.flaticon.com/512/919/919828.png" alt="Code Icon" />
  </section>

  <section id="contact">
    <h1>Contact</h1>
    <h2>Get in touch</h2>
    <p>Email:<strong>adam.quatra@example.com</strong></p>
    <p>User Discord:<strong>adamquatra2010</strong></p>
    <img src="https://cdn-icons-png.flaticon.com/512/542/542638.png" alt="Contact Icon" />
  </section>

  <footer>
    &copy; 2025 Adam Quatra. All rights reserved.
  </footer>

  <script>
    // Top button show/hide and scroll to top
    const topBtn = document.getElementById('topBtn');
    window.onscroll = function () {
      if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
        topBtn.style.display = 'block';
      } else {
        topBtn.style.display = 'none';
      }
    };
    topBtn.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Theme toggle
    const themeToggle = document.getElementById('themeToggle');
    themeToggle.addEventListener('click', () => {
      document.body.classList.toggle('light-theme');
      if(document.body.classList.contains('light-theme')) {
        localStorage.setItem('theme', 'light');
      } else {
        localStorage.setItem('theme', 'dark');
      }
    });

    // Load saved theme on page load
    window.addEventListener('load', () => {
      if(localStorage.getItem('theme') === 'light') {
        document.body.classList.add('light-theme');
      }
    });
  </script>
</body>
</html>
