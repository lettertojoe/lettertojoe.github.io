<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>NetEngineer | Your Name</title>
 
  <!-- ================================================
       BOOTSTRAP 5.3 — CDN LINKS
       Copy these two lines into any project to use Bootstrap
       CSS: paste in <head>, JS: paste before </body>
  ================================================ -->
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
    rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
    crossorigin="anonymous"
  />
  <!-- Bootstrap Icons -->
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css"
    rel="stylesheet"
  />
  <!-- Google Fonts: Fira Code (monospace used throughout) -->
  <link
    href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&display=swap"
    rel="stylesheet"
  />
 
  <style>
    /* ── CSS CUSTOM PROPERTIES ── */
    :root {
      --teal:         #00e5c8;
      --teal-glow:    rgba(0, 229, 200, 0.15);
      --teal-border:  rgba(0, 229, 200, 0.30);
      --bg:           #0b0f10;
      --bg-alt:       #0e1315;
      --card:         #121a1c;
      --card-hover:   #162022;
      --border:       rgba(255,255,255,0.07);
      --text:         #9bbcbc;
      --text-bright:  #d0e8e8;
      --muted:        #4a6464;
      --mono:         'Fira Code', 'Courier New', monospace;
    }
 
    *, *::before, *::after { box-sizing: border-box; }
    html  { scroll-behavior: smooth; }
    body  {
      background: var(--bg);
      color: var(--text);
      font-family: var(--mono);
      font-size: 13px;
      font-weight: 300;
      overflow-x: hidden;
    }
 
    /* subtle scanline texture */
    body::after {
      content: '';
      position: fixed; inset: 0;
      background: repeating-linear-gradient(
        0deg, transparent, transparent 2px,
        rgba(0,0,0,.03) 2px, rgba(0,0,0,.03) 4px
      );
      pointer-events: none;
      z-index: 9999;
    }
 
    /* ────────────────────────────────────
       NAVBAR
    ──────────────────────────────────── */
    .navbar {
      background: rgba(11,15,16,.95);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
      padding: 12px 0;
    }
    .navbar-brand {
      font-family: var(--mono);
      font-size: .9rem;
      color: var(--teal) !important;
      letter-spacing: -.3px;
    }
    .navbar-brand .bracket { color: var(--text-bright); }
 
    .nav-link {
      font-family: var(--mono);
      font-size: .78rem;
      color: var(--muted) !important;
      padding: 5px 13px !important;
      transition: color .2s;
    }
    .nav-link:hover, .nav-link.active { color: var(--teal) !important; }
 
    .btn-nav-resume {
      font-family: var(--mono);
      font-size: .75rem;
      color: var(--teal);
      border: 1px solid var(--teal);
      border-radius: 4px;
      padding: 5px 16px;
      text-decoration: none;
      transition: background .2s, color .2s;
    }
    .btn-nav-resume:hover { background: var(--teal); color: #000; }
 
    .navbar-toggler {
      border-color: var(--teal-border);
    }
    .navbar-toggler-icon {
      filter: invert(.6) sepia(1) saturate(6) hue-rotate(130deg);
    }
 
    /* ────────────────────────────────────
       HERO
    ──────────────────────────────────── */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 130px 0 80px;
      text-align: center;
      position: relative;
      overflow: hidden;
      background:
        radial-gradient(ellipse 80% 55% at 50% 0%,
          rgba(0,229,200,.06) 0%, transparent 68%),
        repeating-linear-gradient(0deg,   transparent, transparent 39px,
          rgba(0,229,200,.025) 39px, rgba(0,229,200,.025) 40px),
        repeating-linear-gradient(90deg,  transparent, transparent 39px,
          rgba(0,229,200,.025) 39px, rgba(0,229,200,.025) 40px),
        var(--bg);
    }
 
    /* floating teal dots */
    .fdot {
      position: absolute;
      color: var(--teal);
      font-size: 1.6rem;
      line-height: 1;
      animation: fdot 3s ease-in-out infinite;
      pointer-events: none;
    }
    .fdot.a { top: 38%; left: 9%;  animation-delay: 0s;   font-size: 2rem; }
    .fdot.b { top: 45%; right: 8%; animation-delay: 1.2s; font-size: 1.4rem; }
    .fdot.c { top: 62%; left: 18%; animation-delay: .6s;  font-size: 1rem; }
    @keyframes fdot {
      0%,100% { opacity: .2; transform: scale(1); }
      50%      { opacity: 1;  transform: scale(1.5); }
    }
 
    /* available badge */
    .avail-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      border: 1px solid var(--teal-border);
      border-radius: 100px;
      padding: 5px 16px;
      font-size: .72rem;
      color: var(--teal);
      margin-bottom: 1.8rem;
    }
    .pulse-dot {
      width: 7px; height: 7px;
      border-radius: 50%;
      background: var(--teal);
      animation: pulse 1.4s ease-in-out infinite;
    }
    @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.15} }
 
    /* hero heading */
    .hero-h1 {
      font-size: clamp(2rem, 6vw, 3.8rem);
      font-weight: 600;
      color: #fff;
      line-height: 1.05;
      margin-bottom: .5rem;
      letter-spacing: -.5px;
    }
    .hero-h1 .hl { color: var(--teal); }
 
    .hero-role {
      font-size: clamp(1rem, 2.8vw, 1.75rem);
      color: var(--teal);
      margin-bottom: 1.4rem;
    }
    /* blinking cursor */
    .cursor {
      display: inline-block;
      width: 3px; height: .9em;
      background: var(--teal);
      margin-left: 3px;
      vertical-align: middle;
      animation: pulse 1s infinite;
    }
 
    .hero-sub {
      color: var(--muted);
      font-size: .82rem;
      max-width: 460px;
      margin: 0 auto 2.2rem;
      line-height: 1.9;
      font-weight: 300;
    }
 
    /* hero buttons */
    .btn-teal {
      display: inline-block;
      font-family: var(--mono);
      font-size: .8rem;
      color: var(--teal);
      border: 1px solid var(--teal);
      border-radius: 4px;
      padding: 11px 26px;
      text-decoration: none;
      transition: background .2s, color .2s;
    }
    .btn-teal:hover { background: var(--teal); color: #000; }
 
    .btn-outline {
      display: inline-block;
      font-family: var(--mono);
      font-size: .8rem;
      color: var(--text-bright);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 11px 26px;
      text-decoration: none;
      transition: border-color .2s, color .2s;
    }
    .btn-outline:hover { border-color: var(--teal-border); color: var(--teal); }
 
    /* hero stats */
    .hero-stats {
      margin-top: 3rem;
      padding-top: 2rem;
      border-top: 1px solid var(--border);
      display: flex;
      justify-content: center;
      gap: 3.5rem;
      flex-wrap: wrap;
    }
    .stat-val {
      font-size: 1.7rem;
      font-weight: 600;
      color: var(--teal);
      line-height: 1;
    }
    .stat-lbl {
      font-size: .68rem;
      color: var(--muted);
      margin-top: 4px;
    }
 
    /* ────────────────────────────────────
       SHARED SECTION STYLES
    ──────────────────────────────────── */
    section { padding: 90px 0; }
 
    .sec-head { text-align: center; margin-bottom: 3rem; }
    .sec-head h2 {
      font-size: 1.45rem;
      font-weight: 400;
      color: #fff;
    }
    .sec-head h2 .chevron { color: var(--teal); margin-right: 6px; }
    .sec-underline {
      width: 46px; height: 2px;
      background: var(--teal);
      margin: 10px auto 0;
      border-radius: 2px;
    }
    .sec-sub {
      font-size: .78rem;
      color: var(--muted);
      margin-top: .6rem;
    }
 
    /* fade-in on scroll */
    .reveal {
      opacity: 0;
      transform: translateY(22px);
      transition: opacity .6s ease, transform .6s ease;
    }
    .reveal.show { opacity: 1; transform: none; }
 
    /* ────────────────────────────────────
       ABOUT
    ──────────────────────────────────── */
    #about { background: var(--bg-alt); }
 
    .about-text p {
      font-size: .82rem;
      color: var(--text);
      line-height: 1.95;
      margin-bottom: .9rem;
      font-weight: 300;
    }
    .ping-badge {
      display: inline-block;
      font-size: .74rem;
      color: var(--teal);
      background: rgba(0,229,200,.07);
      border: 1px solid var(--teal-border);
      border-radius: 4px;
      padding: 7px 14px;
      margin-top: .4rem;
      cursor: default;
    }
 
    /* feature cards in about */
    .feat {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 18px;
      height: 100%;
      transition: border-color .3s, background .3s;
    }
    .feat:hover { border-color: var(--teal-border); background: var(--card-hover); }
    .feat .ficon { font-size: 1.2rem; color: var(--teal); margin-bottom: 9px; }
    .feat h6 { font-size: .8rem; color: #fff; margin-bottom: 5px; }
    .feat p  { font-size: .74rem; color: var(--muted); line-height: 1.6; margin: 0; }
 
    /* ────────────────────────────────────
       PROJECTS
    ──────────────────────────────────── */
    #projects {
      background: var(--bg);
      background-image:
        repeating-linear-gradient(0deg,  transparent, transparent 39px,
          rgba(0,229,200,.02) 39px, rgba(0,229,200,.02) 40px),
        repeating-linear-gradient(90deg, transparent, transparent 39px,
          rgba(0,229,200,.02) 39px, rgba(0,229,200,.02) 40px);
    }
 
    .proj-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      overflow: hidden;
      height: 100%;
      transition: border-color .3s, transform .3s;
    }
    .proj-card:hover { border-color: var(--teal-border); transform: translateY(-5px); }
 
    .proj-thumb {
      width: 100%; aspect-ratio: 16/9;
      background: #0c1618;
      display: flex; align-items: center; justify-content: center;
      font-size: 3rem;
      color: rgba(0,229,200,.13);
      border-bottom: 1px solid var(--border);
    }
 
    .proj-body { padding: 18px 20px 20px; }
    .proj-body h5 { font-size: .88rem; color: #fff; margin-bottom: 6px; }
    .proj-body p  { font-size: .76rem; color: var(--muted); line-height: 1.7; margin-bottom: 12px; }
 
    .tag {
      display: inline-block;
      font-size: .64rem;
      color: var(--teal);
      border: 1px solid var(--teal-border);
      border-radius: 3px;
      padding: 2px 7px;
      margin: 2px 2px 0 0;
    }
 
    .proj-links { display: flex; gap: 8px; margin-top: 13px; flex-wrap: wrap; }
    .proj-btn {
      font-size: .7rem;
      color: var(--text);
      background: rgba(255,255,255,.03);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 5px 12px;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 5px;
      transition: border-color .2s, color .2s;
    }
    .proj-btn:hover { border-color: var(--teal-border); color: var(--teal); }
 
    /* ────────────────────────────────────
       SKILLS
    ──────────────────────────────────── */
    #skills { background: var(--bg-alt); }
 
    .skill-box {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 22px 24px;
      height: 100%;
    }
    .skill-box h5 {
      font-size: .82rem;
      color: var(--teal);
      margin-bottom: 16px;
      padding-bottom: 10px;
      border-bottom: 1px solid var(--border);
    }
    .sk { margin-bottom: 13px; }
    .sk:last-child { margin-bottom: 0; }
    .sk-top {
      display: flex;
      justify-content: space-between;
      font-size: .72rem;
      color: var(--text-bright);
      margin-bottom: 5px;
    }
    .sk-top span { color: var(--teal); }
    .sk-bar {
      height: 4px;
      background: rgba(255,255,255,.05);
      border-radius: 2px;
      overflow: hidden;
    }
    .sk-fill {
      height: 100%;
      background: var(--teal);
      border-radius: 2px;
      width: 0;
      transition: width 1.4s ease;
    }
 
    /* certifications */
    .cert {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 16px;
      text-align: center;
      transition: border-color .3s;
    }
    .cert:hover { border-color: var(--teal-border); }
    .cert .cname { font-size: .78rem; color: #fff; margin-bottom: 3px; }
    .cert .cissue { font-size: .68rem; color: var(--muted); }
 
    /* ────────────────────────────────────
       CONTACT
    ──────────────────────────────────── */
    #contact {
      background: var(--bg);
      background-image:
        repeating-linear-gradient(0deg,  transparent, transparent 39px,
          rgba(0,229,200,.02) 39px, rgba(0,229,200,.02) 40px),
        repeating-linear-gradient(90deg, transparent, transparent 39px,
          rgba(0,229,200,.02) 39px, rgba(0,229,200,.02) 40px);
    }
 
    .cinfo-label {
      font-size: .75rem;
      color: #fff;
      margin-bottom: .9rem;
    }
    .cinfo a {
      display: flex; align-items: center; gap: 10px;
      color: var(--text); text-decoration: none;
      font-size: .78rem;
      padding: 9px 0;
      border-bottom: 1px solid var(--border);
      transition: color .2s;
    }
    .cinfo a:last-child { border-bottom: none; }
    .cinfo a i { color: var(--teal); width: 16px; font-size: .95rem; }
    .cinfo a:hover { color: var(--teal); }
 
    .social-row { display: flex; gap: 9px; margin-top: 1.3rem; }
    .soc-btn {
      width: 34px; height: 34px;
      border: 1px solid var(--border);
      border-radius: 6px;
      display: flex; align-items: center; justify-content: center;
      color: var(--muted); text-decoration: none;
      font-size: .9rem;
      transition: border-color .2s, color .2s;
    }
    .soc-btn:hover { border-color: var(--teal-border); color: var(--teal); }
 
    /* terminal form */
    .terminal {
      background: #0c1214;
      border: 1px solid var(--border);
      border-radius: 10px;
      overflow: hidden;
    }
    .term-bar {
      background: #141d1f;
      padding: 9px 15px;
      display: flex; align-items: center; gap: 6px;
      border-bottom: 1px solid var(--border);
    }
    .tdot { width: 10px; height: 10px; border-radius: 50%; }
    .term-title {
      margin-left: 7px;
      font-size: .71rem;
      color: var(--muted);
    }
    .term-body { padding: 22px; }
 
    .ff { margin-bottom: 14px; }
    .ff label {
      display: block;
      font-size: .69rem;
      color: var(--teal);
      margin-bottom: 5px;
    }
    .ff label::before { content: '$ '; }
    .ff input,
    .ff textarea {
      width: 100%;
      background: rgba(255,255,255,.03);
      border: 1px solid var(--border);
      border-radius: 5px;
      color: #fff;
      padding: 9px 12px;
      font-family: var(--mono);
      font-size: .78rem;
      outline: none;
      transition: border-color .2s;
    }
    .ff input:focus, .ff textarea:focus { border-color: var(--teal-border); }
    .ff input::placeholder, .ff textarea::placeholder { color: var(--muted); }
    .ff textarea { resize: none; min-height: 90px; }
 
    .btn-send {
      width: 100%;
      background: var(--teal);
      color: #000;
      border: none;
      border-radius: 5px;
      padding: 11px;
      font-family: var(--mono);
      font-size: .82rem;
      font-weight: 600;
      cursor: pointer;
      transition: opacity .2s;
    }
    .btn-send:hover { opacity: .85; }
 
    /* ────────────────────────────────────
       FOOTER
    ──────────────────────────────────── */
    footer {
      background: #080c0d;
      border-top: 1px solid var(--border);
      padding: 20px 0;
    }
    footer p, footer span {
      font-size: .71rem;
      color: var(--muted);
      margin: 0;
    }
    .footer-brand { font-size: .8rem; color: var(--teal); }
  </style>
</head>
<body>
 
<!-- ══════════════════════════════════════
     NAVBAR
══════════════════════════════════════ -->
<nav class="navbar navbar-expand-lg fixed-top">
  <div class="container">
    <a class="navbar-brand" href="#hero">
      <span class="bracket">&lt;</span>NetEngineer<span class="bracket">/&gt;</span>
    </a>
    <button class="navbar-toggler" type="button"
            data-bs-toggle="collapse" data-bs-target="#navMenu"
            aria-controls="navMenu" aria-expanded="false">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse justify-content-end" id="navMenu">
      <ul class="navbar-nav align-items-lg-center gap-lg-1 mb-2 mb-lg-0">
        <li class="nav-item"><a class="nav-link" href="#about">About</a></li>
        <li class="nav-item"><a class="nav-link" href="#projects">Projects</a></li>
        <li class="nav-item"><a class="nav-link" href="#skills">Skills</a></li>
        <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
      </ul>
      <a href="#" class="btn-nav-resume ms-lg-3 mt-2 mt-lg-0">Resume</a>
    </div>
  </div>
</nav>
 
 
<!-- ══════════════════════════════════════
     HERO
══════════════════════════════════════ -->
<section id="hero">
  <span class="fdot a">·</span>
  <span class="fdot b">·</span>
  <span class="fdot c">·</span>
 
  <div class="container">
    <div class="avail-badge">
      <span class="pulse-dot"></span> Available for projects
    </div>
 
    <h1 class="hero-h1">
      <span class="hl">·</span>Hi, I'm <span class="hl">Your Name</span><span class="hl">·</span>
    </h1>
 
    <div class="hero-role">
      Network Engineer<span class="cursor"></span>
    </div>
 
    <p class="hero-sub">
      Building secure, scalable network infrastructures. Specializing in<br>
      enterprise networking, cloud architecture, and cybersecurity solutions.
    </p>
 
    <div class="d-flex flex-wrap justify-content-center gap-3">
      <a href="#projects" class="btn-teal">View Projects</a>
      <a href="#contact" class="btn-outline">Get In Touch</a>
    </div>
 
    <div class="hero-stats">
      <div>
        <div class="stat-val">50+</div>
        <div class="stat-lbl">Networks Designed</div>
      </div>
      <div>
        <div class="stat-val">100+</div>
        <div class="stat-lbl">Servers Configured</div>
      </div>
      <div>
        <div class="stat-val">99.9%</div>
        <div class="stat-lbl">Uptime Achieved</div>
      </div>
    </div>
  </div>
</section>
 
 
<!-- ══════════════════════════════════════
     ABOUT
══════════════════════════════════════ -->
<section id="about">
  <div class="container">
 
    <div class="sec-head reveal">
      <h2><span class="chevron">&gt;</span> About Me</h2>
      <div class="sec-underline"></div>
    </div>
 
    <div class="row g-5">
      <!-- left: text -->
      <div class="col-lg-5 reveal">
        <div class="about-text">
          <p>With over 5 years of experience in network engineering, I specialize in designing, implementing, and maintaining network infrastructures that power modern businesses.</p>
          <p>My expertise spans across routing protocols (BGP, OSPF, EIGRP), switching technologies, firewall configurations, and cloud networking. I hold certifications including CCNP, AWS Solutions Architect, and CompTIA Security+.</p>
          <p>I'm passionate about network automation and believe in building infrastructures that are not only reliable but also easy to manage and scale.</p>
          <span class="ping-badge">$ ping passion --count infinite</span>
        </div>
      </div>
 
      <!-- right: feature cards -->
      <div class="col-lg-7 reveal">
        <div class="row g-3">
          <div class="col-md-6">
            <div class="feat">
              <div class="ficon"><i class="bi bi-diagram-3-fill"></i></div>
              <h6>Enterprise Networks</h6>
              <p>Designing and implementing large-scale network infrastructures for Fortune 500 companies.</p>
            </div>
          </div>
          <div class="col-md-6">
            <div class="feat">
              <div class="ficon"><i class="bi bi-grid-3x3-gap-fill"></i></div>
              <h6>Cloud Architecture</h6>
              <p>Building hybrid cloud solutions with AWS, Azure, and on-premise data centers.</p>
            </div>
          </div>
          <div class="col-md-6">
            <div class="feat">
              <div class="ficon"><i class="bi bi-code-slash"></i></div>
              <h6>Network Automation</h6>
              <p>Developing Python and Ansible scripts for automated network provisioning.</p>
            </div>
          </div>
          <div class="col-md-6">
            <div class="feat">
              <div class="ficon"><i class="bi bi-lightning-charge-fill"></i></div>
              <h6>Performance Optimization</h6>
              <p>Analysing and optimising network performance for maximum throughput.</p>
            </div>
          </div>
        </div>
      </div>
    </div><!-- /row -->
  </div>
</section>
 
 
<!-- ══════════════════════════════════════
     PROJECTS
══════════════════════════════════════ -->
<section id="projects">
  <div class="container">
 
    <div class="sec-head reveal">
      <h2><span class="chevron">&gt;</span> Projects</h2>
      <div class="sec-underline"></div>
      <p class="sec-sub">A selection of network infrastructure projects I've designed and implemented</p>
    </div>
 
    <div class="row g-4">
 
      <!-- card 1 -->
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-diagram-3-fill"></i></div>
          <div class="proj-body">
            <h5>Enterprise Campus Network</h5>
            <p>Designed and implemented a full campus network for a university with 10,000+ users. Included core, distribution, and access layers with redundant paths.</p>
            <div>
              <span class="tag">Cisco</span>
              <span class="tag">EIGRP</span>
              <span class="tag">VLAN</span>
              <span class="tag">QoS</span>
            </div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/campus-network" target="_blank" class="proj-btn">
                <i class="bi bi-github"></i> Code
              </a>
              <a href="#" class="proj-btn">
                <i class="bi bi-info-circle"></i> Details
              </a>
            </div>
          </div>
        </div>
      </div>
 
      <!-- card 2 -->
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-shield-lock-fill"></i></div>
          <div class="proj-body">
            <h5>Multi-Site VPN Infrastructure</h5>
            <p>Built a secure SD-WAN solution connecting 15 branch offices to headquarters with automatic failover and traffic optimisation.</p>
            <div>
              <span class="tag">SD-WAN</span>
              <span class="tag">IPSec</span>
              <span class="tag">BGP</span>
              <span class="tag">AWS</span>
            </div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/vpn-infra" target="_blank" class="proj-btn">
                <i class="bi bi-github"></i> Code
              </a>
              <a href="#" class="proj-btn">
                <i class="bi bi-info-circle"></i> Details
              </a>
            </div>
          </div>
        </div>
      </div>
 
      <!-- card 3 -->
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-hdd-stack-fill"></i></div>
          <div class="proj-body">
            <h5>Data Center Migration</h5>
            <p>Led the migration of legacy infrastructure to a modern data center with spine-leaf architecture, reducing latency by 40%.</p>
            <div>
              <span class="tag">VXLAN</span>
              <span class="tag">BGP-EVPN</span>
              <span class="tag">Ansible</span>
              <span class="tag">Python</span>
            </div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/dc-migration" target="_blank" class="proj-btn">
                <i class="bi bi-github"></i> Code
              </a>
              <a href="#" class="proj-btn">
                <i class="bi bi-info-circle"></i> Details
              </a>
            </div>
          </div>
        </div>
      </div>
 
      <!-- card 4 -->
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-cloud-arrow-up-fill"></i></div>
          <div class="proj-body">
            <h5>Hybrid Cloud Network</h5>
            <p>Architected a hybrid multi-cloud network integrating on-premise network with AWS and Azure using Direct Connect and ExpressRoute.</p>
            <div>
              <span class="tag">AWS</span>
              <span class="tag">Azure</span>
              <span class="tag">Terraform</span>
              <span class="tag">Transit Gateway</span>
            </div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/hybrid-cloud" target="_blank" class="proj-btn">
                <i class="bi bi-github"></i> Code
              </a>
              <a href="#" class="proj-btn">
                <i class="bi bi-info-circle"></i> Details
              </a>
            </div>
          </div>
        </div>
      </div>
 
    </div><!-- /row -->
  </div>
</section>
 
 
<!-- ══════════════════════════════════════
     SKILLS & CERTIFICATIONS
══════════════════════════════════════ -->
<section id="skills">
  <div class="container">
 
    <div class="sec-head reveal">
      <h2><span class="chevron">&gt;</span> Skills &amp; Certifications</h2>
      <div class="sec-underline"></div>
    </div>
 
    <!-- skill bars -->
    <div class="row g-4 mb-5">
      <div class="col-lg-4 reveal">
        <div class="skill-box">
          <h5>Routing &amp; Switching</h5>
          <div class="sk">
            <div class="sk-top">BGP <span>95%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="95"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">OSPF <span>92%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="92"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">EIGRP <span>85%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="85"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">MPLS <span>80%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="80"></div></div>
          </div>
        </div>
      </div>
 
      <div class="col-lg-4 reveal">
        <div class="skill-box">
          <h5>Security</h5>
          <div class="sk">
            <div class="sk-top">Firewall (Palo Alto/Cisco) <span>90%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="90"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">VPN/IPSec <span>88%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="88"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">IDS/IPS <span>55%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="55"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">Zero Trust <span>75%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="75"></div></div>
          </div>
        </div>
      </div>
 
      <div class="col-lg-4 reveal">
        <div class="skill-box">
          <h5>Cloud &amp; Automation</h5>
          <div class="sk">
            <div class="sk-top">AWS Networking <span>85%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="85"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">Azure Networking <span>80%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="80"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">Ansible <span>82%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="82"></div></div>
          </div>
          <div class="sk">
            <div class="sk-top">Python <span>52%</span></div>
            <div class="sk-bar"><div class="sk-fill" data-w="52"></div></div>
          </div>
        </div>
      </div>
    </div>
 
    <!-- certifications -->
    <p class="text-center mb-3 reveal" style="font-size:.85rem;color:#fff;">Certifications</p>
    <div class="row g-3 justify-content-center reveal">
      <div class="col-md-3 col-6">
        <div class="cert">
          <div class="cname">CCNP Enterprise</div>
          <div class="cissue">Cisco</div>
        </div>
      </div>
      <div class="col-md-3 col-6">
        <div class="cert">
          <div class="cname">AWS Solutions Architect</div>
          <div class="cissue">Amazon</div>
        </div>
      </div>
      <div class="col-md-3 col-6">
        <div class="cert">
          <div class="cname">CompTIA Security+</div>
          <div class="cissue">CompTIA</div>
        </div>
      </div>
      <div class="col-md-3 col-6">
        <div class="cert">
          <div class="cname">PCNSA</div>
          <div class="cissue">Palo Alto Networks</div>
        </div>
      </div>
    </div>
 
  </div>
</section>
 
 
<!-- ══════════════════════════════════════
     CONTACT
══════════════════════════════════════ -->
<section id="contact">
  <div class="container">
 
    <div class="sec-head reveal">
      <h2><span class="chevron">&gt;</span> Contact</h2>
      <div class="sec-underline"></div>
      <p class="sec-sub">Let's connect and discuss how I can help with your network infrastructure needs</p>
    </div>
 
    <div class="row g-4 reveal">
 
      <!-- left: contact info -->
      <div class="col-lg-4">
        <p class="cinfo-label">Get in Touch</p>
        <div class="cinfo">
          <a href="mailto:contact@example.com">
            <i class="bi bi-envelope"></i> contact@example.com
          </a>
          <a href="#">
            <i class="bi bi-geo-alt"></i> San Francisco, CA
          </a>
        </div>
        <p class="cinfo-label mt-4">Connect on</p>
        <div class="social-row">
          <a href="https://linkedin.com/in/yourprofile" target="_blank" class="soc-btn">
            <i class="bi bi-linkedin"></i>
          </a>
          <a href="https://github.com/yourusername" target="_blank" class="soc-btn">
            <i class="bi bi-github"></i>
          </a>
        </div>
      </div>
 
      <!-- right: terminal form -->
      <div class="col-lg-8">
        <div class="terminal">
          <div class="term-bar">
            <span class="tdot" style="background:#ff5f57"></span>
            <span class="tdot" style="background:#febc2e"></span>
            <span class="tdot" style="background:#28c840"></span>
            <span class="term-title">&gt;_ Terminal</span>
          </div>
          <div class="term-body">
            <form id="contactForm">
              <div class="ff">
                <label for="fn">name</label>
                <input type="text" id="fn" placeholder="Jane Doe" required />
              </div>
              <div class="ff">
                <label for="fe">email</label>
                <input type="email" id="fe" placeholder="john@example.com" required />
              </div>
              <div class="ff">
                <label for="fm">message</label>
                <textarea id="fm" placeholder="Your message here ..." required></textarea>
              </div>
              <button type="submit" class="btn-send">Send Message</button>
            </form>
          </div>
        </div>
      </div>
 
    </div><!-- /row -->
  </div>
</section>
 
 
<!-- ══════════════════════════════════════
     FOOTER
══════════════════════════════════════ -->
<footer>
  <div class="container">
    <div class="d-flex flex-column flex-md-row justify-content-between align-items-center gap-2">
      <span class="footer-brand">&lt;NetEngineer /&gt;</span>
      <p>&copy; 2025 All rights reserved.</p>
      <p>Built with <span style="color:var(--teal)">Bootstrap</span> &amp; GitHub Pages</p>
    </div>
  </div>
</footer>
 
 
<!-- ══════════════════════════════════════
     BOOTSTRAP 5 JS — required for navbar toggle
══════════════════════════════════════ -->
<script
  src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
  integrity="sha384-YvpcrYf0tY3lHB60NNkmXc4s9bIOgUxi8T/jzmJ/2N5a8U9eiRHMO7j2iFQP0v9a"
  crossorigin="anonymous">
</script>
 
<script>
  /* ── scroll reveal ── */
  const revealEls = document.querySelectorAll('.reveal');
  const revealObs = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('show'), i * 80);
      }
    });
  }, { threshold: 0.1 });
  revealEls.forEach(el => revealObs.observe(el));
 
  /* ── skill bar animation ── */
  const barObs = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.querySelectorAll('.sk-fill').forEach(bar => {
          bar.style.width = bar.dataset.w + '%';
        });
      }
    });
  }, { threshold: 0.4 });
  document.querySelectorAll('.skill-box').forEach(b => barObs.observe(b));
 
  /* ── active nav on scroll ── */
  const sections = document.querySelectorAll('section[id]');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => {
      if (window.scrollY >= s.offsetTop - 140) current = s.getAttribute('id');
    });
    document.querySelectorAll('.nav-link').forEach(link => {
      link.classList.toggle('active', link.getAttribute('href') === '#' + current);
    });
  });
 
  /* ── contact form → mailto ── */
  document.getElementById('contactForm').addEventListener('submit', function(e) {
    e.preventDefault();
    const name    = document.getElementById('fn').value;
    const email   = document.getElementById('fe').value;
    const message = document.getElementById('fm').value;
    window.location.href =
      `mailto:contact@example.com` +
      `?subject=${encodeURIComponent('Message from ' + name)}` +
      `&body=${encodeURIComponent('From: ' + name + ' (' + email + ')\n\n' + message)}`;
  });
</script>
 
</body>
</html>
