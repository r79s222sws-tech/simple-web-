# simple-web-
Website for company 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simple Electrical Solutions | West London Electricians</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700;900&family=Inter:wght@300;400;500;600&display=swap');

  :root {
    --volt: #4ECDC4;
    --volt-dark: #3ab5ac;
    --black: #0a0a0a;
    --dark: #111111;
    --card: #181818;
    --border: #2a2a2a;
    --white: #ffffff;
    --grey: #888888;
    --light-grey: #cccccc;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--black);
    color: var(--white);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 40px; height: 70px;
    background: rgba(10,10,10,0.95);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 22px; font-weight: 900; letter-spacing: 2px;
    color: var(--white); text-decoration: none;
  }
  .nav-logo span { color: var(--volt); }
  .nav-links { display: flex; gap: 32px; list-style: none; }
  .nav-links a {
    color: var(--light-grey); text-decoration: none;
    font-size: 13px; font-weight: 500; letter-spacing: 1px;
    text-transform: uppercase; transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--volt); }
  .nav-cta {
    background: var(--volt); color: var(--black);
    padding: 10px 22px; border-radius: 4px;
    font-size: 13px; font-weight: 700; letter-spacing: 1px;
    text-decoration: none; text-transform: uppercase;
    transition: background 0.2s;
  }
  .nav-cta:hover { background: var(--volt-dark); }
  .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; }
  .hamburger span { display: block; width: 24px; height: 2px; background: var(--white); }
  .mobile-menu {
    display: none; position: fixed; top: 70px; left: 0; right: 0;
    background: var(--dark); border-bottom: 1px solid var(--border);
    padding: 24px 40px; z-index: 99;
  }
  .mobile-menu.open { display: flex; flex-direction: column; gap: 20px; }
  .mobile-menu a {
    color: var(--light-grey); text-decoration: none;
    font-size: 16px; font-weight: 500; letter-spacing: 1px;
    text-transform: uppercase;
  }

  /* ── HERO ── */
  #home {
    min-height: 100vh;
    display: flex; align-items: center; justify-content: center;
    text-align: center;
    background: var(--black);
    padding: 120px 20px 80px;
    position: relative; overflow: hidden;
  }
  .hero-grid-bg {
    position: absolute; inset: 0; opacity: 0.04;
    background-image:
      linear-gradient(var(--volt) 1px, transparent 1px),
      linear-gradient(90deg, var(--volt) 1px, transparent 1px);
    background-size: 60px 60px;
  }
  .hero-content { position: relative; max-width: 900px; }
  .hero-badge {
    display: inline-block;
    border: 1px solid var(--volt); color: var(--volt);
    font-size: 11px; font-weight: 600; letter-spacing: 3px;
    text-transform: uppercase; padding: 6px 18px; border-radius: 2px;
    margin-bottom: 32px;
  }
  .hero-logo-img {
    width: 220px; margin: 0 auto 28px;
    display: block; filter: drop-shadow(0 0 30px rgba(78,205,196,0.3));
  }
  .hero h1 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: clamp(52px, 10vw, 100px);
    font-weight: 900; line-height: 0.9;
    letter-spacing: -1px; text-transform: uppercase;
    margin-bottom: 24px;
  }
  .hero h1 .volt { color: var(--volt); }
  .hero-sub {
    font-size: 16px; color: var(--grey); max-width: 520px;
    margin: 0 auto 40px; line-height: 1.7; font-weight: 300;
  }
  .hero-buttons { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }
  .btn-primary {
    background: var(--volt); color: var(--black);
    padding: 15px 36px; border-radius: 4px;
    font-size: 14px; font-weight: 700; letter-spacing: 1px;
    text-decoration: none; text-transform: uppercase; transition: all 0.2s;
  }
  .btn-primary:hover { background: var(--volt-dark); transform: translateY(-1px); }
  .btn-secondary {
    border: 1px solid var(--border); color: var(--white);
    padding: 15px 36px; border-radius: 4px;
    font-size: 14px; font-weight: 600; letter-spacing: 1px;
    text-decoration: none; text-transform: uppercase; transition: all 0.2s;
  }
  .btn-secondary:hover { border-color: var(--volt); color: var(--volt); }
  .hero-stats {
    display: flex; gap: 48px; justify-content: center;
    margin-top: 64px; flex-wrap: wrap;
  }
  .stat { text-align: center; }
  .stat-num {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 42px; font-weight: 900; color: var(--volt); line-height: 1;
  }
  .stat-label { font-size: 12px; color: var(--grey); letter-spacing: 1px; text-transform: uppercase; margin-top: 4px; }

  /* ── TRUST BAR ── */
  .trust-bar {
    background: var(--dark); border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border); padding: 20px 40px;
    display: flex; align-items: center; justify-content: center;
    gap: 48px; flex-wrap: wrap;
  }
  .trust-item {
    display: flex; align-items: center; gap: 10px;
    font-size: 13px; color: var(--grey); font-weight: 500;
  }
  .trust-item .dot { width: 6px; height: 6px; background: var(--volt); border-radius: 50%; }

  /* ── SECTION SHARED ── */
  section { padding: 100px 40px; }
  .section-label {
    font-size: 11px; font-weight: 600; letter-spacing: 3px;
    text-transform: uppercase; color: var(--volt); margin-bottom: 16px;
  }
  .section-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: clamp(36px, 6vw, 64px); font-weight: 900;
    text-transform: uppercase; line-height: 1; margin-bottom: 20px;
  }
  .section-sub { font-size: 16px; color: var(--grey); max-width: 500px; line-height: 1.7; }
  .container { max-width: 1200px; margin: 0 auto; }

  /* ── SERVICES ── */
  #services { background: var(--dark); }
  .services-header { margin-bottom: 60px; }
  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 2px;
  }
  .service-card {
    background: var(--card); padding: 36px 32px;
    border: 1px solid var(--border);
    transition: all 0.25s; cursor: default;
    position: relative; overflow: hidden;
  }
  .service-card::before {
    content: ''; position: absolute; top: 0; left: 0;
    width: 3px; height: 0; background: var(--volt);
    transition: height 0.3s;
  }
  .service-card:hover::before { height: 100%; }
  .service-card:hover { border-color: rgba(78,205,196,0.3); transform: translateY(-2px); }
  .service-icon { font-size: 32px; margin-bottom: 18px; }
  .service-card h3 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 22px; font-weight: 700; letter-spacing: 1px;
    text-transform: uppercase; margin-bottom: 12px;
  }
  .service-card p { font-size: 14px; color: var(--grey); line-height: 1.7; }
  .service-tag {
    display: inline-block; margin-top: 16px;
    font-size: 10px; letter-spacing: 2px; text-transform: uppercase;
    color: var(--volt); border: 1px solid rgba(78,205,196,0.3);
    padding: 4px 10px; border-radius: 2px;
  }

  /* ── CALCULATOR ── */
  #enquiries { background: var(--black); }
  .calc-wrapper {
    display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start;
  }
  .calc-intro .section-sub { margin-bottom: 32px; }
  .calc-note { font-size: 13px; color: var(--grey); line-height: 1.6; margin-top: 24px; }
  .calc-box {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 8px; padding: 40px;
  }
  .calc-box h3 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 24px; font-weight: 700; text-transform: uppercase;
    margin-bottom: 28px; color: var(--volt);
  }
  .calc-row { margin-bottom: 20px; }
  .calc-row label {
    display: block; font-size: 12px; font-weight: 600;
    letter-spacing: 1px; text-transform: uppercase;
    color: var(--grey); margin-bottom: 8px;
  }
  .calc-row-inner { display: flex; align-items: center; gap: 12px; }
  .calc-btn {
    width: 38px; height: 38px; background: var(--border);
    border: none; color: var(--white); font-size: 20px;
    border-radius: 4px; cursor: pointer; flex-shrink: 0;
    transition: background 0.2s; font-weight: 300;
  }
  .calc-btn:hover { background: var(--volt); color: var(--black); }
  .calc-count {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 28px; font-weight: 700; min-width: 40px; text-align: center;
  }
  .calc-divider { height: 1px; background: var(--border); margin: 24px 0; }
  .calc-total-row { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
  .calc-total-label { font-size: 13px; color: var(--grey); }
  .calc-total-val { font-size: 14px; font-weight: 600; }
  .calc-grand {
    display: flex; justify-content: space-between; align-items: center;
    margin-top: 16px;
  }
  .calc-grand-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 20px; font-weight: 700; text-transform: uppercase; letter-spacing: 1px;
  }
  .calc-grand-val {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 40px; font-weight: 900; color: var(--volt);
  }
  .calc-submit {
    display: block; width: 100%; margin-top: 24px;
    background: var(--volt); color: var(--black);
    border: none; padding: 15px; border-radius: 4px;
    font-size: 14px; font-weight: 700; letter-spacing: 1px;
    text-transform: uppercase; cursor: pointer; transition: background 0.2s;
  }
  .calc-submit:hover { background: var(--volt-dark); }

  /* ── PROJECTS ── */
  #projects { background: var(--dark); }
  .projects-header { margin-bottom: 60px; }
  .projects-grid {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 2px;
  }
  .project-card {
    background: var(--card); aspect-ratio: 4/3;
    border: 1px solid var(--border);
    display: flex; align-items: flex-end;
    overflow: hidden; position: relative;
    transition: transform 0.25s;
  }
  .project-card:hover { transform: scale(1.01); }
  .project-placeholder {
    position: absolute; inset: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 48px; opacity: 0.15;
  }
  .project-overlay {
    position: relative; width: 100%;
    background: linear-gradient(transparent, rgba(0,0,0,0.9));
    padding: 24px 20px 20px;
  }
  .project-tag {
    font-size: 10px; letter-spacing: 2px; text-transform: uppercase;
    color: var(--volt); margin-bottom: 6px;
  }
  .project-title { font-size: 15px; font-weight: 600; }
  .projects-upload-note {
    margin-top: 24px; padding: 20px;
    border: 1px dashed var(--border); border-radius: 4px;
    text-align: center; font-size: 13px; color: var(--grey);
  }

  /* ── ABOUT ── */
  #about { background: var(--black); }
  .about-wrapper { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; }
  .about-visual {
    background: var(--card); border: 1px solid var(--border);
    aspect-ratio: 1; display: flex; align-items: center; justify-content: center;
    border-radius: 8px; font-size: 80px; position: relative; overflow: hidden;
  }
  .about-visual::after {
    content: ''; position: absolute;
    top: 0; left: 0; right: 0; height: 3px;
    background: var(--volt);
  }
  .about-content .section-sub { margin-bottom: 32px; }
  .about-list { list-style: none; }
  .about-list li {
    display: flex; align-items: flex-start; gap: 14px;
    padding: 14px 0; border-bottom: 1px solid var(--border);
    font-size: 14px; color: var(--light-grey); line-height: 1.5;
  }
  .about-list li:last-child { border-bottom: none; }
  .about-list .tick { color: var(--volt); font-size: 16px; flex-shrink: 0; margin-top: 1px; }
  .cert-row {
    display: flex; gap: 16px; margin-top: 32px; flex-wrap: wrap; align-items: center;
  }
  .cert-badge {
    background: var(--card); border: 1px solid var(--border);
    padding: 10px 16px; border-radius: 4px;
    font-size: 11px; font-weight: 600; letter-spacing: 1px;
    text-transform: uppercase; color: var(--grey);
  }

  /* ── CONTACT ── */
  #contact { background: var(--dark); }
  .contact-wrapper { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; }
  .contact-info h2 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 48px; font-weight: 900; text-transform: uppercase;
    line-height: 1; margin-bottom: 20px;
  }
  .contact-info p { font-size: 15px; color: var(--grey); line-height: 1.7; margin-bottom: 40px; }
  .contact-item { display: flex; align-items: flex-start; gap: 16px; margin-bottom: 28px; }
  .contact-icon {
    width: 44px; height: 44px; background: rgba(78,205,196,0.1);
    border: 1px solid rgba(78,205,196,0.3); border-radius: 4px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px; flex-shrink: 0;
  }
  .contact-item-text .label { font-size: 11px; color: var(--grey); letter-spacing: 1px; text-transform: uppercase; margin-bottom: 4px; }
  .contact-item-text .value { font-size: 15px; font-weight: 500; }
  .contact-form { display: flex; flex-direction: column; gap: 16px; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .form-group { display: flex; flex-direction: column; gap: 8px; }
  .form-group label { font-size: 12px; font-weight: 600; letter-spacing: 1px; text-transform: uppercase; color: var(--grey); }
  .form-group input, .form-group textarea, .form-group select {
    background: var(--card); border: 1px solid var(--border);
    color: var(--white); padding: 13px 16px; border-radius: 4px;
    font-size: 14px; font-family: 'Inter', sans-serif;
    transition: border-color 0.2s; outline: none;
  }
  .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
    border-color: var(--volt);
  }
  .form-group select option { background: var(--card); }
  .form-group textarea { resize: vertical; min-height: 120px; }
  .form-submit {
    background: var(--volt); color: var(--black);
    border: none; padding: 16px; border-radius: 4px;
    font-size: 14px; font-weight: 700; letter-spacing: 1px;
    text-transform: uppercase; cursor: pointer; transition: background 0.2s;
    margin-top: 8px;
  }
  .form-submit:hover { background: var(--volt-dark); }

  /* ── EMERGENCY BANNER ── */
  .emergency-banner {
    background: var(--volt); color: var(--black);
    text-align: center; padding: 18px 40px;
  }
  .emergency-banner strong {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 20px; font-weight: 900; letter-spacing: 1px; text-transform: uppercase;
    margin-right: 16px;
  }
  .emergency-banner span { font-size: 14px; font-weight: 600; }
  .emergency-banner a { color: var(--black); font-weight: 700; text-decoration: underline; }

  /* ── FOOTER ── */
  footer {
    background: var(--black); border-top: 1px solid var(--border);
    padding: 60px 40px 40px;
  }
  .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 60px; max-width: 1200px; margin: 0 auto; }
  .footer-brand p { font-size: 14px; color: var(--grey); line-height: 1.7; margin: 16px 0 24px; max-width: 280px; }
  .footer-heading { font-size: 12px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 20px; color: var(--white); }
  .footer-links { list-style: none; display: flex; flex-direction: column; gap: 12px; }
  .footer-links a { font-size: 14px; color: var(--grey); text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: var(--volt); }
  .footer-bottom {
    display: flex; justify-content: space-between; align-items: center;
    max-width: 1200px; margin: 48px auto 0;
    padding-top: 24px; border-top: 1px solid var(--border);
    font-size: 12px; color: var(--grey); flex-wrap: wrap; gap: 12px;
  }

  /* ── TOAST ── */
  .toast {
    position: fixed; bottom: 24px; right: 24px; z-index: 999;
    background: var(--volt); color: var(--black);
    padding: 16px 24px; border-radius: 6px;
    font-size: 14px; font-weight: 700;
    transform: translateY(100px); opacity: 0;
    transition: all 0.4s; pointer-events: none;
  }
  .toast.show { transform: translateY(0); opacity: 1; }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 0 24px; }
    .nav-links, .nav-cta { display: none; }
    .hamburger { display: flex; }
    section { padding: 72px 24px; }
    .calc-wrapper, .about-wrapper, .contact-wrapper, .footer-grid { grid-template-columns: 1fr; gap: 40px; }
    .projects-grid { grid-template-columns: 1fr 1fr; }
    .form-row { grid-template-columns: 1fr; }
    .trust-bar { gap: 24px; padding: 20px 24px; }
    .hero-stats { gap: 32px; }
    footer { padding: 48px 24px 32px; }
    .footer-bottom { flex-direction: column; text-align: center; }
    .about-visual { display: none; }
  }
  @media (max-width: 600px) {
    .projects-grid { grid-template-columns: 1fr; }
    .hero h1 { letter-spacing: -2px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#home" class="nav-logo">S<span>⚡</span>MPLE <span style="font-size:12px;font-weight:400;color:var(--grey);letter-spacing:1px;">ELECTRICAL</span></a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#enquiries">Pricing</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="tel:+44XXXXXXXXXX" class="nav-cta">Call Now</a>
  <div class="hamburger" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </div>
</nav>

<div class="mobile-menu" id="mobileMenu">
  <a href="#services" onclick="toggleMenu()">Services</a>
  <a href="#projects" onclick="toggleMenu()">Projects</a>
  <a href="#about" onclick="toggleMenu()">About</a>
  <a href="#enquiries" onclick="toggleMenu()">Pricing</a>
  <a href="#contact" onclick="toggleMenu()">Contact</a>
  <a href="tel:+44XXXXXXXXXX" style="color:var(--volt);">📞 Call Now</a>
</div>

<!-- HERO -->
<section id="home" class="hero">
  <div class="hero-grid-bg"></div>
  <div class="hero-content">
    <div class="hero-badge">West London · Commercial Specialists</div>
    <img src="SES_NO_BACKGROUND.png" alt="Simple Electrical Solutions" class="hero-logo-img" onerror="this.style.display='none'">
    <h1 class="section-title">We Bring <span class="volt">Power</span><br>To Your Plans.</h1>
    <p class="hero-sub">Commercial electrical installation specialists covering West London. Rewires, access control, fire alarms, EV charging and more — done right, first time.</p>
    <div class="hero-buttons">
      <a href="#enquiries" class="btn-primary">Get a Quote</a>
      <a href="#services" class="btn-secondary">Our Services</a>
    </div>
    <div class="hero-stats">
      <div class="stat"><div class="stat-num">24/7</div><div class="stat-label">Call-Outs Available</div></div>
      <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Commercial Focus</div></div>
      <div class="stat"><div class="stat-num">Free</div><div class="stat-label">Quotes Always</div></div>
    </div>
  </div>
</section>

<!-- TRUST BAR -->
<div class="trust-bar">
  <div class="trust-item"><span class="dot"></span> NAPIT Registered</div>
  <div class="trust-item"><span class="dot"></span> Trusted Tradesman</div>
  <div class="trust-item"><span class="dot"></span> Mental Health Aware</div>
  <div class="trust-item"><span class="dot"></span> West London Based</div>
  <div class="trust-item"><span class="dot"></span> Free Quoting</div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="container">
    <div class="services-header">
      <div class="section-label">What We Do</div>
      <h2 class="section-title">Our Services</h2>
      <p class="section-sub">Full-spectrum electrical solutions for commercial properties across West London. Every job certified, every time.</p>
    </div>
    <div class="services-grid">
      <div class="service-card">
        <div class="service-icon">⚡</div>
        <h3>Electrical Installations</h3>
        <p>Full commercial electrical installations from first fix to completion. New builds, office fit-outs and industrial units.</p>
        <span class="service-tag">Commercial</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🔄</div>
        <h3>Rewires & Refurbs</h3>
        <p>Complete rewiring of commercial premises and full electrical refurbishment to bring properties up to current standards.</p>
        <span class="service-tag">Rewire</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🔍</div>
        <h3>Inspection & Testing</h3>
        <p>EICR condition reports, fixed wire testing and periodic inspections. Full certification provided on completion.</p>
        <span class="service-tag">EICR</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🔧</div>
        <h3>Maintenance</h3>
        <p>Planned and reactive maintenance contracts for commercial clients. Keeping your building's electrics safe and compliant.</p>
        <span class="service-tag">Ongoing</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🚪</div>
        <h3>Access Control</h3>
        <p>Supply and installation of access control door systems, intercoms, and electronic locking for commercial premises.</p>
        <span class="service-tag">Security</span>
      </div>
      <div class="service-card">
        <div class="service-icon">📹</div>
        <h3>CCTV & Intruder Alarm</h3>
        <p>Professional CCTV installation and intruder alarm systems to protect your business and give you peace of mind.</p>
        <span class="service-tag">Security</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🔥</div>
        <h3>Fire Alarms</h3>
        <p>Advanced fire alarm system installation and maintenance. We specialise in Advanced panel systems for complex commercial sites.</p>
        <span class="service-tag">Advanced Systems</span>
      </div>
      <div class="service-card">
        <div class="service-icon">🚗</div>
        <h3>EV Car Chargers</h3>
        <p>Electric vehicle charger installation for commercial car parks, office buildings and mixed-use developments. From £1,200.</p>
        <span class="service-tag">EV</span>
      </div>
      <div class="service-card">
        <div class="service-icon">📞</div>
        <h3>24/7 Call-Outs</h3>
        <p>Emergency electrical call-out service across West London. When something goes wrong, we're there when you need us.</p>
        <span class="service-tag">Emergency</span>
      </div>
    </div>
  </div>
</section>

<!-- PRICING CALCULATOR -->
<section id="enquiries">
  <div class="container">
    <div class="calc-wrapper">
      <div class="calc-intro">
        <div class="section-label">Instant Estimate</div>
        <h2 class="section-title">Pricing<br>Calculator</h2>
        <p class="section-sub">Get an instant guide price for your electrical project. Add the items you need and we'll give you an estimated cost on the spot.</p>
        <p class="calc-note">⚠️ Prices shown are guide prices only. Final costs depend on site conditions, cable runs, and specification. All quotes are free — contact us for a confirmed price.</p>
        <br>
        <a href="#contact" class="btn-secondary" style="display:inline-block;margin-top:8px;">Request Full Quote</a>
      </div>
      <div class="calc-box">
        <h3>⚡ Build Your Quote</h3>

        <div class="calc-row">
          <label>DB (Consumer Unit) Changes — £600 each</label>
          <div class="calc-row-inner">
            <button class="calc-btn" onclick="adjust('db',-1)">−</button>
            <div class="calc-count" id="db-count">0</div>
            <button class="calc-btn" onclick="adjust('db',1)">+</button>
          </div>
        </div>

        <div class="calc-row">
          <label>Power & Lighting Points — £80 per point</label>
          <div class="calc-row-inner">
            <button class="calc-btn" onclick="adjust('points',-1)">−</button>
            <div class="calc-count" id="points-count">0</div>
            <button class="calc-btn" onclick="adjust('points',1)">+</button>
          </div>
        </div>

        <div class="calc-row">
          <label>EV Car Chargers — £1,200 each</label>
          <div class="calc-row-inner">
            <button class="calc-btn" onclick="adjust('ev',-1)">−</button>
            <div class="calc-count" id="ev-count">0</div>
            <button class="calc-btn" onclick="adjust('ev',1)">+</button>
          </div>
        </div>

        <div class="calc-divider"></div>

        <div class="calc-total-row">
          <span class="calc-total-label">DB Changes</span>
          <span class="calc-total-val" id="db-total">£0</span>
        </div>
        <div class="calc-total-row">
          <span class="calc-total-label">Points</span>
          <span class="calc-total-val" id="points-total">£0</span>
        </div>
        <div class="calc-total-row">
          <span class="calc-total-label">EV Chargers</span>
          <span class="calc-total-val" id="ev-total">£0</span>
        </div>

        <div class="calc-divider"></div>

        <div class="calc-grand">
          <span class="calc-grand-label">Estimate</span>
          <span class="calc-grand-val" id="grand-total">£0</span>
        </div>

        <button class="calc-submit" onclick="submitQuote()">Send This Quote Request →</button>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="projects-header">
      <div class="section-label">Our Work</div>
      <h2 class="section-title">Recent Projects</h2>
      <p class="section-sub">A snapshot of our recent commercial work across West London. Photos coming soon — send yours over!</p>
    </div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-placeholder">⚡</div>
        <div class="project-overlay">
          <div class="project-tag">Commercial</div>
          <div class="project-title">Office Rewire — W6</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-placeholder">🚪</div>
        <div class="project-overlay">
          <div class="project-tag">Access Control</div>
          <div class="project-title">Multi-Door System — W4</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-placeholder">📹</div>
        <div class="project-overlay">
          <div class="project-tag">CCTV</div>
          <div class="project-title">Retail CCTV — W12</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-placeholder">🚗</div>
        <div class="project-overlay">
          <div class="project-tag">EV Charging</div>
          <div class="project-title">Car Park Install — TW8</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-placeholder">🔥</div>
        <div class="project-overlay">
          <div class="project-tag">Fire Alarm</div>
          <div class="project-title">Advanced System — W3</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-placeholder">🔍</div>
        <div class="project-overlay">
          <div class="project-tag">Testing</div>
          <div class="project-title">EICR — Commercial Block</div>
        </div>
      </div>
    </div>
    <div class="projects-upload-note">
      📷 Real project photos will go here — send them over and we'll update the site
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="about-wrapper">
      <div class="about-visual">⚡</div>
      <div class="about-content">
        <div class="section-label">Who We Are</div>
        <h2 class="section-title">Simple.<br>Reliable.<br>Qualified.</h2>
        <p class="section-sub">Simple Electrical Solutions is a West London-based commercial electrical contractor. We cut through the noise and just get the job done — on time, on budget, to the highest standard.</p>
        <ul class="about-list">
          <li><span class="tick">✓</span> Specialists in commercial electrical installations across West London</li>
          <li><span class="tick">✓</span> Advanced fire alarm system trained and experienced</li>
          <li><span class="tick">✓</span> Access control, CCTV and intruder alarm installation</li>
          <li><span class="tick">✓</span> 24/7 emergency call-outs available across West London</li>
          <li><span class="tick">✓</span> All work fully certified and compliant with BS 7671</li>
          <li><span class="tick">✓</span> Free no-obligation quotes on every job</li>
        </ul>
        <div class="cert-row">
          <span class="cert-badge">NAPIT</span>
          <span class="cert-badge">Trusted Tradesman</span>
          <span class="cert-badge">Mental Health Aware</span>
          <span class="cert-badge">BS 7671</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="contact-wrapper">
      <div class="contact-info">
        <div class="section-label">Get In Touch</div>
        <h2 class="section-title">Let's Talk<br><span style="color:var(--volt)">About Your<br>Project</span></h2>
        <p>Free quotes on every job. Based in West London, covering all surrounding areas. Whether it's a quick call-out or a full commercial fit-out — we're ready.</p>
        <div class="contact-item">
          <div class="contact-icon">📞</div>
          <div class="contact-item-text">
            <div class="label">Phone</div>
            <div class="value">Add your number here</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">✉️</div>
          <div class="contact-item-text">
            <div class="label">Email</div>
            <div class="value">Add your email here</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">📍</div>
          <div class="contact-item-text">
            <div class="label">Location</div>
            <div class="value">West London & Surrounding Areas</div>
          </div>
        </div>
      </div>
      <div>
        <form class="contact-form" onsubmit="submitContact(event)">
          <div class="form-row">
            <div class="form-group">
              <label>First Name</label>
              <input type="text" placeholder="John" required>
            </div>
            <div class="form-group">
              <label>Last Name</label>
              <input type="text" placeholder="Smith" required>
            </div>
          </div>
          <div class="form-group">
            <label>Email</label>
            <input type="email" placeholder="john@company.com" required>
          </div>
          <div class="form-group">
            <label>Phone</label>
            <input type="tel" placeholder="07xxx xxxxxx">
          </div>
          <div class="form-group">
            <label>Service Required</label>
            <select>
              <option value="">Select a service...</option>
              <option>Electrical Installation</option>
              <option>Rewire / Refurbishment</option>
              <option>Inspection & Testing (EICR)</option>
              <option>Maintenance</option>
              <option>Access Control</option>
              <option>CCTV / Intruder Alarm</option>
              <option>Fire Alarm</option>
              <option>EV Car Charger</option>
              <option>Emergency Call-Out</option>
              <option>Other / General Enquiry</option>
            </select>
          </div>
          <div class="form-group">
            <label>Tell Us About Your Project</label>
            <textarea placeholder="Describe the work needed, location, timescale..." required></textarea>
          </div>
          <button type="submit" class="form-submit">Send Enquiry →</button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- EMERGENCY BANNER -->
<div class="emergency-banner">
  <strong>⚡ 24/7 Emergency Call-Outs</strong>
  <span>West London electricians available when you need us most — <a href="tel:+44XXXXXXXXXX">Call Now</a></span>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <div style="font-family:'Barlow Condensed',sans-serif;font-size:24px;font-weight:900;letter-spacing:2px;">
        S<span style="color:var(--volt)">⚡</span>MPLE <span style="font-size:14px;font-weight:400;color:var(--grey);">ELECTRICAL SOLUTIONS</span>
      </div>
      <p>Commercial electrical specialists serving West London. Installations, rewires, access control, fire alarms and EV charging — all under one roof.</p>
      <div style="font-size:12px;color:var(--grey);">NAPIT Registered · Trusted Tradesman</div>
    </div>
    <div>
      <div class="footer-heading">Services</div>
      <ul class="footer-links">
        <li><a href="#services">Installations</a></li>
        <li><a href="#services">Rewires & Refurbs</a></li>
        <li><a href="#services">Inspection & Testing</a></li>
        <li><a href="#services">Access Control</a></li>
        <li><a href="#services">CCTV & Alarms</a></li>
        <li><a href="#services">EV Chargers</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-heading">Company</div>
      <ul class="footer-links">
        <li><a href="#about">About Us</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#enquiries">Pricing</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="#contact">Free Quote</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Simple Electrical Solutions. All rights reserved.</span>
    <span>West London · Commercial Electrical Specialists</span>
  </div>
</footer>

<!-- TOAST -->
<div class="toast" id="toast">✓ Enquiry sent! We'll be in touch shortly.</div>

<script>
  // Mobile menu
  function toggleMenu() {
    document.getElementById('mobileMenu').classList.toggle('open');
  }

  // Calculator
  const prices = { db: 600, points: 80, ev: 1200 };
  const counts = { db: 0, points: 0, ev: 0 };

  function adjust(key, delta) {
    counts[key] = Math.max(0, counts[key] + delta);
    document.getElementById(key + '-count').textContent = counts[key];
    updateTotals();
  }

  function updateTotals() {
    let grand = 0;
    for (const key in counts) {
      const t = counts[key] * prices[key];
      grand += t;
      document.getElementById(key + '-total').textContent = '£' + t.toLocaleString();
    }
    document.getElementById('grand-total').textContent = '£' + grand.toLocaleString();
  }

  function submitQuote() {
    const total = Object.keys(counts).reduce((s, k) => s + counts[k] * prices[k], 0);
    if (total === 0) { alert('Please add at least one item to your quote.'); return; }
    showToast('Quote request sent! Estimated: £' + total.toLocaleString());
    // Scroll to contact
    document.getElementById('contact').scrollIntoView({ behavior: 'smooth' });
  }

  function submitContact(e) {
    e.preventDefault();
    showToast('✓ Message sent! We\'ll be in touch soon.');
    e.target.reset();
  }

  function showToast(msg) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 4000);
  }

  // Smooth scroll for nav on mobile
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', () => {
      document.getElementById('mobileMenu').classList.remove('open');
    });
  });
</script>
</body>
</html>