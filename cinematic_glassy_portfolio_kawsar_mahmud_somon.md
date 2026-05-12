# Cinematic Glassy Portfolio Website

Save the following as `index.html` and keep your image file in the same folder with the exact name:

`My picture for Linkdin.jpg`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Kawsar Mahmud Somon | Portfolio</title>

  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css"/>
  <link href="https://unpkg.com/aos@2.3.4/dist/aos.css" rel="stylesheet">

  <style>

    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      scroll-behavior:smooth;
      font-family:'Segoe UI',sans-serif;
    }

    body{
      overflow-x:hidden;
      color:#1f2937;
      background:
      radial-gradient(circle at top left, rgba(96,165,250,0.18), transparent 30%),
      radial-gradient(circle at bottom right, rgba(129,140,248,0.18), transparent 30%),
      linear-gradient(135deg,#f8fbff,#eef4ff,#f7faff);
      animation:bgMove 15s ease infinite alternate;
      position:relative;
    }

    @keyframes bgMove{
      0%{
        background-position:left top,right bottom;
      }
      100%{
        background-position:right top,left bottom;
      }
    }

    body::before{
      content:"";
      position:fixed;
      inset:0;
      background-image:
      linear-gradient(rgba(0,0,0,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,0,0,0.03) 1px, transparent 1px);
      background-size:40px 40px;
      z-index:-3;
    }

    .blur-orb{
      position:fixed;
      border-radius:50%;
      filter:blur(80px);
      opacity:0.35;
      z-index:-1;
      animation:floatOrb 18s infinite alternate ease-in-out;
    }

    .orb1{
      width:300px;
      height:300px;
      background:#60a5fa;
      top:-50px;
      left:-80px;
    }

    .orb2{
      width:250px;
      height:250px;
      background:#818cf8;
      bottom:0;
      right:-50px;
      animation-delay:4s;
    }

    .orb3{
      width:200px;
      height:200px;
      background:#93c5fd;
      top:40%;
      left:50%;
      animation-delay:8s;
    }

    @keyframes floatOrb{
      0%{
        transform:translateY(0) translateX(0) scale(1);
      }
      100%{
        transform:translateY(-50px) translateX(40px) scale(1.2);
      }
    }

    nav{
      position:sticky;
      top:0;
      width:100%;
      padding:18px 8%;
      display:flex;
      justify-content:space-between;
      align-items:center;
      background:rgba(255,255,255,0.35);
      backdrop-filter:blur(20px);
      border-bottom:1px solid rgba(255,255,255,0.3);
      box-shadow:0 8px 30px rgba(31,38,135,0.08);
      z-index:1000;
    }

    .logo a{
      text-decoration:none;
      font-size:28px;
      font-weight:800;
      letter-spacing:1px;
      background:linear-gradient(90deg,#2563eb,#4f46e5);
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
    }

    nav ul{
      display:flex;
      align-items:center;
      gap:24px;
      list-style:none;
    }

    nav ul li a{
      text-decoration:none;
      color:#1f2937;
      font-weight:600;
      transition:0.4s;
    }

    nav ul li a:hover{
      color:#2563eb;
      transform:translateY(-2px);
    }

    section{
      padding:100px 8%;
    }

    .hero{
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:50px;
      flex-wrap:wrap;
    }

    .hero-text{
      flex:1;
    }

    .hero-text h1{
      font-size:72px;
      line-height:1.1;
      margin-bottom:20px;
      font-weight:800;
      background:linear-gradient(90deg,#2563eb,#4f46e5,#3b82f6);
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
      animation:textGlow 4s infinite alternate;
    }

    @keyframes textGlow{
      0%{
        filter:drop-shadow(0 0 5px rgba(37,99,235,0.2));
      }
      100%{
        filter:drop-shadow(0 0 18px rgba(37,99,235,0.5));
      }
    }

    .hero-text p{
      font-size:20px;
      line-height:2;
      color:#4b5563;
      max-width:700px;
      margin-bottom:35px;
    }

    .hero-btn{
      display:inline-block;
      padding:15px 34px;
      border-radius:50px;
      text-decoration:none;
      color:white;
      font-weight:700;
      background:linear-gradient(135deg,#2563eb,#4f46e5);
      position:relative;
      overflow:hidden;
      box-shadow:0 15px 35px rgba(37,99,235,0.25);
      transition:0.4s;
    }

    .hero-btn::before{
      content:"";
      position:absolute;
      width:100%;
      height:100%;
      background:rgba(255,255,255,0.25);
      top:0;
      left:-120%;
      transform:skewX(-30deg);
    }

    .hero-btn:hover::before{
      left:120%;
      transition:1s;
    }

    .hero-btn:hover{
      transform:translateY(-6px);
    }

    .profile-container{
      width:360px;
      height:360px;
      position:relative;
      animation:floatImage 6s ease-in-out infinite;
    }

    @keyframes floatImage{
      0%,100%{
        transform:translateY(0);
      }
      50%{
        transform:translateY(-15px);
      }
    }

    .profile-ring{
      position:absolute;
      width:100%;
      height:100%;
      border-radius:50%;
      padding:6px;
      background:linear-gradient(135deg,#60a5fa,#4f46e5,#2563eb);
      animation:spin 10s linear infinite;
      box-shadow:
      0 0 40px rgba(96,165,250,0.45),
      0 0 80px rgba(79,70,229,0.25);
    }

    @keyframes spin{
      100%{
        transform:rotate(360deg);
      }
    }

    .profile-img{
      width:100%;
      height:100%;
      border-radius:50%;
      object-fit:cover;
      border:8px solid rgba(255,255,255,0.85);
      position:relative;
      z-index:2;
      box-shadow:0 20px 40px rgba(0,0,0,0.15);
    }

    .glass-card,
    .skill-box,
    .timeline-item,
    .contact-card{
      background:rgba(255,255,255,0.28);
      backdrop-filter:blur(18px);
      border:1px solid rgba(255,255,255,0.25);
      border-radius:28px;
      box-shadow:0 8px 32px rgba(31,38,135,0.12);
      transition:0.5s;
    }

    .glass-card{
      padding:45px;
    }

    .glass-card:hover,
    .skill-box:hover,
    .timeline-item:hover,
    .contact-card:hover{
      transform:translateY(-10px);
      box-shadow:0 15px 40px rgba(37,99,235,0.18);
    }

    .section-title{
      font-size:42px;
      color:#2563eb;
      margin-bottom:35px;
      position:relative;
      display:inline-block;
    }

    .section-title::after{
      content:"";
      position:absolute;
      width:60%;
      height:4px;
      background:linear-gradient(90deg,#2563eb,#818cf8);
      left:0;
      bottom:-10px;
      border-radius:10px;
    }

    .about p,
    .experience p{
      line-height:2;
      font-size:17px;
      color:#374151;
    }

    .skills{
      margin-top:40px;
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
      gap:22px;
    }

    .skill-box{
      padding:30px;
      text-align:center;
      overflow:hidden;
      position:relative;
    }

    .skill-box::before{
      content:"";
      position:absolute;
      width:150%;
      height:150%;
      background:linear-gradient(120deg,transparent,rgba(255,255,255,0.25),transparent);
      top:-120%;
      left:-120%;
      transform:rotate(25deg);
    }

    .skill-box:hover::before{
      top:120%;
      left:120%;
      transition:1s;
    }

    .skill-box i{
      font-size:42px;
      color:#2563eb;
      margin-bottom:18px;
    }

    .timeline{
      display:flex;
      flex-direction:column;
      gap:25px;
      margin-top:30px;
    }

    .timeline-item{
      padding:30px;
      border-left:5px solid #2563eb;
    }

    .timeline-item h3{
      margin-bottom:12px;
    }

    .award{
      color:#2563eb;
      font-weight:700;
    }

    .contact-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
      gap:25px;
      margin-top:40px;
    }

    .contact-card{
      padding:35px;
      text-align:center;
      overflow:hidden;
      position:relative;
    }

    .contact-card::after{
      content:"";
      position:absolute;
      inset:0;
      background:linear-gradient(120deg,transparent,rgba(255,255,255,0.22),transparent);
      transform:translateX(-120%);
    }

    .contact-card:hover::after{
      transform:translateX(120%);
      transition:1s;
    }

    .contact-card i{
      font-size:42px;
      color:#2563eb;
      margin-bottom:18px;
    }

    .contact-card a{
      text-decoration:none;
      color:#1f2937;
      font-weight:600;
      word-break:break-word;
    }

    footer{
      text-align:center;
      padding:40px;
      background:rgba(255,255,255,0.2);
      backdrop-filter:blur(10px);
      border-top:1px solid rgba(255,255,255,0.25);
      color:#6b7280;
    }

    @media(max-width:900px){

      .hero{
        flex-direction:column-reverse;
        text-align:center;
      }

      .hero-text h1{
        font-size:52px;
      }

      .profile-container{
        width:280px;
        height:280px;
      }

      nav ul{
        gap:14px;
      }
    }

    @media(max-width:650px){

      nav{
        padding:16px 5%;
      }

      nav ul{
        display:none;
      }

      .hero-text h1{
        font-size:42px;
      }

      .section-title{
        font-size:34px;
      }

      .hero-text p{
        font-size:17px;
      }
    }

  </style>
</head>
<body>

  <div class="blur-orb orb1"></div>
  <div class="blur-orb orb2"></div>
  <div class="blur-orb orb3"></div>

  <nav>

    <div class="logo">
      <a href="#home">
        Kawsar Mahmud Somon
      </a>
    </div>

    <ul>

      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#contact">Contact</a></li>

      <li>
        <a href="mailto:kawsarmahmudsomon@gmail.com" target="_blank">
          <i class="fa-solid fa-envelope"></i>
        </a>
      </li>

      <li>
        <a href="tel:+8801330857084">
          <i class="fa-solid fa-phone"></i>
        </a>
      </li>

      <li>
        <a href="https://linkedin.com/in/kawsarmahmudsomon" target="_blank">
          <i class="fa-brands fa-linkedin"></i>
        </a>
      </li>

    </ul>

  </nav>

  <section class="hero" id="home">

    <div class="hero-text" data-aos="fade-right">

      <h1>
        Kawsar Mahmud Somon
      </h1>

      <p>
        Customer Service Specialist & Data Analyst focused on data-driven solutions,
        operational efficiency, performance analytics, dashboard reporting,
        and customer experience optimization.
      </p>

      <a href="#contact" class="hero-btn">
        Let's Connect
      </a>

    </div>

    <div class="profile-container" data-aos="fade-left">

      <div class="profile-ring"></div>

      <img
        src="My picture for Linkdin.jpg"
        alt="Kawsar Mahmud Somon"
        class="profile-img"
      >

    </div>

  </section>

  <section id="about">

    <div class="glass-card about" data-aos="fade-up">

      <h2 class="section-title">
        About Me
      </h2>

      <p>
        I am currently pursuing my BSS in Economics under National University.
        My educational background developed my analytical thinking,
        business understanding, and financial knowledge.
      </p>

      <br>

      <p>
        My professional journey evolved from customer service operations into
        Data Analytics, where I discovered how meaningful insights and operational
        reporting can improve performance and customer satisfaction.
      </p>

      <br>

      <p>
        I specialize in CRM systems, Advanced Excel, Power BI,
        data visualization, performance tracking, email support,
        and phone-based customer communication.
      </p>

      <div class="skills">

        <div class="skill-box" data-aos="zoom-in">
          <i class="fa-solid fa-chart-line"></i>
          <h3>Power BI</h3>
        </div>

        <div class="skill-box" data-aos="zoom-in">
          <i class="fa-solid fa-file-excel"></i>
          <h3>Advanced Excel</h3>
        </div>

        <div class="skill-box" data-aos="zoom-in">
          <i class="fa-solid fa-headset"></i>
          <h3>CRM Systems</h3>
        </div>

        <div class="skill-box" data-aos="zoom-in">
          <i class="fa-solid fa-chart-pie"></i>
          <h3>Data Visualization</h3>
        </div>

      </div>

    </div>

  </section>

  <section id="experience">

    <div class="glass-card experience" data-aos="fade-up">

      <h2 class="section-title">
        Experience & Achievements
      </h2>

      <div class="timeline">

        <div class="timeline-item" data-aos="fade-right">

          <h3>
            Customer Service Specialist
          </h3>

          <p>
            Experienced in customer communication, issue resolution,
            operational support, email handling, phone support,
            and maintaining strong client satisfaction.
          </p>

        </div>

        <div class="timeline-item" data-aos="fade-left">

          <h3>
            Data Analytics & Reporting
          </h3>

          <p>
            Skilled in KPI tracking, dashboard analysis,
            operational reporting, workflow optimization,
            and transforming raw data into actionable insights.
          </p>

        </div>

        <div class="timeline-item" data-aos="fade-right">

          <h3 class="award">
            Best Employee Award ×2
          </h3>

          <p>
            Earned recognition and professional certificates twice
            for operational excellence, customer service quality,
            and dedication to performance improvement.
          </p>

        </div>

      </div>

    </div>

  </section>

  <section id="contact">

    <div class="glass-card" data-aos="fade-up">

      <h2 class="section-title">
        Contact
      </h2>

      <div class="contact-grid">

        <div class="contact-card" data-aos="zoom-in">

          <i class="fa-solid fa-phone"></i>

          <h3>Phone</h3>

          <br>

          <a href="tel:+8801330857084">
            +8801330857084
          </a>

        </div>

        <div class="contact-card" data-aos="zoom-in">

          <i class="fa-solid fa-envelope"></i>

          <h3>Email</h3>

          <br>

          <a href="mailto:kawsarmahmudsomon@gmail.com">
            kawsarmahmudsomon@gmail.com
          </a>

        </div>

        <div class="contact-card" data-aos="zoom-in">

          <i class="fa-brands fa-linkedin"></i>

          <h3>LinkedIn</h3>

          <br>

          <a href="https://linkedin.com/in/kawsarmahmudsomon" target="_blank">
            linkedin.com/in/kawsarmahmudsomon
          </a>

        </div>

        <div class="contact-card" data-aos="zoom-in">

          <i class="fa-solid fa-location-dot"></i>

          <h3>Location</h3>

          <br>

          <p>
            Nikunja-2, Dhaka
          </p>

        </div>

      </div>

    </div>

  </section>

  <footer>
    © 2026 Kawsar Mahmud Somon | Cinematic Glass Portfolio
  </footer>

  <script src="https://unpkg.com/aos@2.3.4/dist/aos.js"></script>

  <script>

    AOS.init({
      duration:1200,
      once:true
    });

  </script>

</body>
</html>
```

