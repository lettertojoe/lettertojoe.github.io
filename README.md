<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
 
  <!-- Bootstrap 5.3 CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous"/>
  <!-- Bootstrap Icons -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css" rel="stylesheet"/>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet"/>
 
  <style>
    :root {
      /* ── COLOUR PALETTE ──
         Background : soft slate-blue (#1e2a3a → #243447)
         Cards      : lighter navy (#2a3f55)
         Accent     : bright cyan-teal (#00c9a7)
         Text       : near-white (#e8f0f7) / medium (#a8bfd4)
         Muted      : (#6a8aaa)
      */
      --accent:        #00c9a7;
      --accent-light:  rgba(0, 201, 167, 0.15);
      --accent-border: rgba(0, 201, 167, 0.35);
      --bg:            #1e2a3a;
      --bg-alt:        #243447;
      --card:          #2a3f55;
      --card-hover:    #304a65;
      --border:        rgba(168, 191, 212, 0.15);
      --text:          #e8f0f7;
      --text-mid:      #a8bfd4;
      --muted:         #6a8aaa;
      --mono:          'Fira Code', 'Courier New', monospace;
      --sans:          'Inter', sans-serif;
    }
 
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      background: var(--bg);
      color: var(--text-mid);
      font-family: var(--sans);
      font-size: 14px;
      font-weight: 400;
      overflow-x: hidden;
    }
 
    /* ── NAVBAR ── */
    .navbar {
      background: rgba(30, 42, 58, 0.96);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border);
      padding: 13px 0;
    }
    .navbar-brand {
      font-family: var(--mono);
      font-size: .95rem;
      color: var(--accent) !important;
    }
    .navbar-brand .bracket { color: var(--text); }
    .nav-link {
      font-family: var(--mono);
      font-size: .78rem;
      color: var(--muted) !important;
      padding: 6px 14px !important;
      transition: color .2s;
    }
    .nav-link:hover, .nav-link.active { color: var(--accent) !important; }
    .btn-nav-resume {
      font-family: var(--mono);
      font-size: .75rem;
      color: var(--accent);
      border: 1px solid var(--accent);
      border-radius: 5px;
      padding: 6px 18px;
      text-decoration: none;
      transition: background .2s, color .2s;
    }
    .btn-nav-resume:hover { background: var(--accent); color: #fff; }
    .navbar-toggler { border-color: var(--accent-border); }
    .navbar-toggler-icon { filter: invert(.7) sepia(1) saturate(4) hue-rotate(130deg); }
 
    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 130px 0 80px;
      text-align: center;
      position: relative;
      overflow: hidden;
      background:
        radial-gradient(ellipse 80% 60% at 50% 0%,
          rgba(0,201,167,.1) 0%, transparent 65%),
        linear-gradient(180deg, #1a2840 0%, #1e2a3a 100%);
    }
 
    /* grid lines */
    #hero::before {
      content: '';
      position: absolute; inset: 0;
      background:
        repeating-linear-gradient(0deg,  transparent, transparent 49px, rgba(0,201,167,.04) 49px, rgba(0,201,167,.04) 50px),
        repeating-linear-gradient(90deg, transparent, transparent 49px, rgba(0,201,167,.04) 49px, rgba(0,201,167,.04) 50px);
      pointer-events: none;
    }
 
    .fdot { position: absolute; color: var(--accent); animation: fdot 3s ease-in-out infinite; pointer-events: none; }
    .fdot.a { font-size: 2rem; top: 38%; left: 9%;  animation-delay: 0s; }
    .fdot.b { font-size: 1.4rem; top: 45%; right: 8%; animation-delay: 1.2s; }
    .fdot.c { font-size: 1rem; top: 62%; left: 18%; animation-delay: .6s; }
    @keyframes fdot { 0%,100%{opacity:.2;transform:scale(1)} 50%{opacity:.9;transform:scale(1.5)} }
 
    .avail-badge {
      display: inline-flex; align-items: center; gap: 8px;
      border: 1px solid var(--accent-border);
      border-radius: 100px;
      padding: 5px 16px;
      font-family: var(--mono);
      font-size: .72rem;
      color: var(--accent);
      background: var(--accent-light);
      margin-bottom: 1.8rem;
    }
    .pulse-dot { width: 7px; height: 7px; border-radius: 50%; background: var(--accent); animation: pulse 1.4s infinite; }
    @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.2} }
 
    .hero-h1 {
      font-family: var(--mono);
      font-size: clamp(2rem, 5.5vw, 3.6rem);
      font-weight: 600;
      color: var(--text);
      line-height: 1.08;
      margin-bottom: .5rem;
    }
    .hero-h1 .hl { color: var(--accent); }
 
    .hero-role {
      font-family: var(--mono);
      font-size: clamp(1rem, 2.5vw, 1.6rem);
      color: var(--accent);
      margin-bottom: 1.5rem;
    }
    .cursor { display: inline-block; width: 3px; height: .85em; background: var(--accent); margin-left: 3px; vertical-align: middle; animation: pulse 1s infinite; }
 
    .hero-sub {
      color: var(--text-mid);
      font-size: .88rem;
      max-width: 480px;
      margin: 0 auto 2.4rem;
      line-height: 1.9;
    }
 
    .btn-teal {
      display: inline-block;
      font-family: var(--mono); font-size: .8rem;
      color: #fff; background: var(--accent);
      border: 1px solid var(--accent);
      border-radius: 5px; padding: 11px 28px;
      text-decoration: none; transition: opacity .2s, transform .2s;
    }
    .btn-teal:hover { opacity: .88; transform: translateY(-2px); color: #fff; }
 
    .btn-outline-hero {
      display: inline-block;
      font-family: var(--mono); font-size: .8rem;
      color: var(--text);
      border: 1px solid var(--border);
      border-radius: 5px; padding: 11px 28px;
      text-decoration: none; transition: border-color .2s, color .2s;
    }
    .btn-outline-hero:hover { border-color: var(--accent-border); color: var(--accent); }
 
    .hero-stats {
      margin-top: 3rem; padding-top: 2rem;
      border-top: 1px solid var(--border);
      display: flex; justify-content: center; gap: 3.5rem; flex-wrap: wrap;
    }
    .stat-val { font-family: var(--mono); font-size: 1.8rem; font-weight: 600; color: var(--accent); line-height: 1; }
    .stat-lbl { font-size: .7rem; color: var(--muted); margin-top: 4px; }
 
    /* ── SECTION SHARED ── */
    section { padding: 90px 0; }
    .sec-head { text-align: center; margin-bottom: 3rem; }
    .sec-head h2 { font-family: var(--mono); font-size: 1.5rem; font-weight: 400; color: var(--text); }
    .sec-head h2 .ch { color: var(--accent); margin-right: 6px; }
    .sec-underline { width: 48px; height: 2px; background: var(--accent); margin: 10px auto 0; border-radius: 2px; }
    .sec-sub { font-size: .8rem; color: var(--muted); margin-top: .65rem; }
 
    .reveal { opacity: 0; transform: translateY(22px); transition: opacity .65s ease, transform .65s ease; }
    .reveal.show { opacity: 1; transform: none; }
 
    /* ── ABOUT ── */
    #about { background: var(--bg-alt); }
 
    .about-text p { font-size: .86rem; color: var(--text-mid); line-height: 1.95; margin-bottom: .95rem; }
    .ping-badge {
      display: inline-block;
      font-family: var(--mono); font-size: .74rem;
      color: var(--accent);
      background: var(--accent-light);
      border: 1px solid var(--accent-border);
      border-radius: 5px; padding: 7px 14px;
      margin-top: .5rem; cursor: default;
    }
 
    .feat {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px; padding: 20px; height: 100%;
      transition: border-color .3s, background .3s, transform .3s;
    }
    .feat:hover { border-color: var(--accent-border); background: var(--card-hover); transform: translateY(-3px); }
    .feat .ficon { font-size: 1.3rem; color: var(--accent); margin-bottom: 10px; }
    .feat h6 { font-family: var(--mono); font-size: .82rem; color: var(--text); margin-bottom: 6px; }
    .feat p  { font-size: .76rem; color: var(--muted); line-height: 1.65; margin: 0; }
 
    /* ── PROJECTS ── */
    #projects { background: var(--bg); }
 
    .proj-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px; overflow: hidden; height: 100%;
      transition: border-color .3s, transform .3s;
    }
    .proj-card:hover { border-color: var(--accent-border); transform: translateY(-5px); }
 
    .proj-thumb {
      width: 100%; aspect-ratio: 16/9;
      background: linear-gradient(135deg, #243447 0%, #2a3f55 100%);
      display: flex; align-items: center; justify-content: center;
      font-size: 3.2rem; color: rgba(0,201,167,.25);
      border-bottom: 1px solid var(--border);
    }
 
    .proj-body { padding: 20px; }
    .proj-body h5 { font-family: var(--mono); font-size: .9rem; color: var(--text); margin-bottom: 7px; }
    .proj-body p  { font-size: .78rem; color: var(--text-mid); line-height: 1.7; margin-bottom: 13px; }
 
    .tag {
      display: inline-block;
      font-family: var(--mono); font-size: .65rem;
      color: var(--accent);
      background: var(--accent-light);
      border: 1px solid var(--accent-border);
      border-radius: 4px; padding: 2px 8px; margin: 2px 2px 0 0;
    }
 
    .proj-links { display: flex; gap: 8px; margin-top: 14px; flex-wrap: wrap; }
    .proj-btn {
      font-family: var(--mono); font-size: .71rem;
      color: var(--text-mid);
      background: rgba(255,255,255,.05);
      border: 1px solid var(--border);
      border-radius: 5px; padding: 5px 13px;
      text-decoration: none; display: inline-flex; align-items: center; gap: 5px;
      transition: border-color .2s, color .2s, background .2s;
    }
    .proj-btn:hover { border-color: var(--accent-border); color: var(--accent); background: var(--accent-light); }
 
    /* ── SKILLS ── */
    #skills { background: var(--bg-alt); }
 
    .skill-box {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px; padding: 24px; height: 100%;
    }
    .skill-box h5 {
      font-family: var(--mono); font-size: .82rem; color: var(--accent);
      margin-bottom: 18px; padding-bottom: 10px;
      border-bottom: 1px solid var(--border);
    }
    .sk { margin-bottom: 14px; }
    .sk:last-child { margin-bottom: 0; }
    .sk-top { display: flex; justify-content: space-between; font-family: var(--mono); font-size: .73rem; color: var(--text); margin-bottom: 5px; }
    .sk-top span { color: var(--accent); }
    .sk-bar { height: 5px; background: rgba(255,255,255,.08); border-radius: 3px; overflow: hidden; }
    .sk-fill { height: 100%; background: linear-gradient(90deg, var(--accent), #00e8c0); border-radius: 3px; width: 0; transition: width 1.4s ease; }
 
    .cert {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px; padding: 18px; text-align: center;
      transition: border-color .3s, transform .3s;
    }
    .cert:hover { border-color: var(--accent-border); transform: translateY(-3px); }
    .cert .cname { font-family: var(--mono); font-size: .8rem; color: var(--text); margin-bottom: 4px; }
    .cert .cissue { font-size: .7rem; color: var(--muted); }
 
    /* ── CONTACT ── */
    #contact { background: var(--bg); }
 
    .cinfo-label { font-family: var(--mono); font-size: .78rem; color: var(--text); margin-bottom: .9rem; }
    .cinfo a {
      display: flex; align-items: center; gap: 12px;
      color: var(--text-mid); text-decoration: none;
      font-size: .8rem; padding: 10px 0;
      border-bottom: 1px solid var(--border);
      transition: color .2s;
    }
    .cinfo a:last-child { border-bottom: none; }
    .cinfo a i { color: var(--accent); font-size: 1rem; width: 18px; }
    .cinfo a:hover { color: var(--accent); }
 
    .social-row { display: flex; gap: 10px; margin-top: 1.4rem; }
    .soc-btn {
      width: 38px; height: 38px;
      border: 1px solid var(--border);
      border-radius: 7px;
      display: flex; align-items: center; justify-content: center;
      color: var(--muted); text-decoration: none; font-size: 1rem;
      transition: border-color .2s, color .2s, background .2s;
    }
    .soc-btn:hover { border-color: var(--accent-border); color: var(--accent); background: var(--accent-light); }
 
    /* terminal form */
    .terminal {
      background: var(--bg-alt);
      border: 1px solid var(--border);
      border-radius: 12px; overflow: hidden;
    }
    .term-bar {
      background: var(--card);
      padding: 10px 16px;
      display: flex; align-items: center; gap: 6px;
      border-bottom: 1px solid var(--border);
    }
    .tdot { width: 10px; height: 10px; border-radius: 50%; }
    .term-title { margin-left: 8px; font-family: var(--mono); font-size: .72rem; color: var(--muted); }
    .term-body { padding: 24px; }
 
    .ff { margin-bottom: 15px; }
    .ff label { display: block; font-family: var(--mono); font-size: .71rem; color: var(--accent); margin-bottom: 6px; }
    .ff label::before { content: '$ '; }
    .ff input, .ff textarea {
      width: 100%;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 6px;
      color: var(--text); padding: 10px 13px;
      font-family: var(--mono); font-size: .8rem;
      outline: none; transition: border-color .2s;
    }
    .ff input:focus, .ff textarea:focus { border-color: var(--accent-border); }
    .ff input::placeholder, .ff textarea::placeholder { color: var(--muted); }
    .ff textarea { resize: none; min-height: 95px; }
    .btn-send {
      width: 100%; background: var(--accent); color: #fff;
      border: none; border-radius: 6px; padding: 12px;
      font-family: var(--mono); font-size: .84rem; font-weight: 600;
      cursor: pointer; transition: opacity .2s, transform .2s;
    }
    .btn-send:hover { opacity: .88; transform: translateY(-1px); }
 
    /* ── FOOTER ── */
    footer {
      background: #182232;
      border-top: 1px solid var(--border);
      padding: 22px 0;
    }
    footer p, footer span { font-family: var(--mono); font-size: .72rem; color: var(--muted); margin: 0; }
    .footer-brand { font-family: var(--mono); font-size: .82rem; color: var(--accent); }
  </style>
</head>
<body>
 
<!-- ══ NAVBAR ══ -->
<nav class="navbar navbar-expand-lg fixed-top">
  <div class="container">
    <a class="navbar-brand" href="#hero">
     ! <span class="bracket">&lt;</span>NetEngineer<span class="bracket">/&gt;</span>!
    </a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navMenu">
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
 
<!-- ══ HERO ══ -->
<section id="hero">
  <span class="fdot a">·</span>
  <span class="fdot b">·</span>
  <span class="fdot c">·</span>
  <div class="container position-relative">
    <div class="avail-badge">
      <span class="pulse-dot"></span> Available for projects
    </div>
    <h1 class="hero-h1">
      <span class="hl">·</span>Hi, I'm <span class="hl">Joseph Ozurumba</span><span class="hl">·</span>
    </h1>
    <div class="hero-role">Network Engineer<span class="cursor"></span></div>
    <p class="hero-sub">
      Building secure, scalable network infrastructures. Specializing in<br>
      enterprise networking, cloud architecture, and cybersecurity solutions.
    </p>
    <div class="d-flex flex-wrap justify-content-center gap-3">
      <a href="#projects" class="btn-teal">View Projects</a>
      <a href="#contact" class="btn-outline-hero">Get In Touch</a>
    </div>
    <div class="hero-stats">
      <div><div class="stat-val">50+</div><div class="stat-lbl">Networks Designed</div></div>
      <div><div class="stat-val">100+</div><div class="stat-lbl">Servers Configured</div></div>
      <div><div class="stat-val">99.9%</div><div class="stat-lbl">Uptime Achieved</div></div>
    </div>
  </div>
</section>
 
<!-- ══ ABOUT ══ -->
<section id="about">
  <div class="container">
    <div class="sec-head reveal">
      <h2><span class="ch">&gt;</span> About Me</h2>
      <div class="sec-underline"></div>
    </div>
    <div class="row g-5">
      <div class="col-lg-5 reveal">
        <div class="about-text">
          <p>With over 5 years of experience in network engineering, I specialize in designing, implementing, and maintaining network infrastructures that power modern businesses.</p>
          <p>My expertise spans across routing protocols (BGP, OSPF, EIGRP), switching technologies, firewall configurations, and cloud networking. I hold certifications including CCNP, AWS Solutions Architect, and CompTIA Security+.</p>
          <p>I'm passionate about network automation and believe in building infrastructures that are not only reliable but also easy to manage and scale.</p>
          <span class="ping-badge">$ ping passion --count infinite</span>
        </div>
      </div>
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
    </div>
  </div>
</section>
 
<!-- ══ PROJECTS ══ -->
<section id="projects">
  <div class="container">
    <div class="sec-head reveal">
      <h2><span class="ch">&gt;</span> Projects</h2>
      <div class="sec-underline"></div>
      <p class="sec-sub">A selection of network infrastructure projects I've designed and implemented</p>
    </div>
    <div class="row g-4">
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-diagram-3-fill"></i></div>
          <div class="proj-body">
            <h5>Enterprise Campus Network</h5>
            <p>Designed and implemented a full campus network for a university with 10,000+ users. Included core, distribution, and access layers with redundant paths.</p>
            <div><span class="tag">Cisco</span><span class="tag">EIGRP</span><span class="tag">VLAN</span><span class="tag">QoS</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/campus-network" target="_blank" class="proj-btn"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-btn"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-shield-lock-fill"></i></div>
          <div class="proj-body">
            <h5>Multi-Site VPN Infrastructure</h5>
            <p>Built a secure SD-WAN solution connecting 15 branch offices to headquarters with automatic failover and traffic optimisation.</p>
            <div><span class="tag">SD-WAN</span><span class="tag">IPSec</span><span class="tag">BGP</span><span class="tag">AWS</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/vpn-infra" target="_blank" class="proj-btn"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-btn"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-hdd-stack-fill"></i></div>
          <div class="proj-body">
            <h5>Data Center Migration</h5>
            <p>Led the migration of legacy infrastructure to a modern data center with spine-leaf architecture, reducing latency by 40%.</p>
            <div><span class="tag">VXLAN</span><span class="tag">BGP-EVPN</span><span class="tag">Ansible</span><span class="tag">Python</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/dc-migration" target="_blank" class="proj-btn"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-btn"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 reveal">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-cloud-arrow-up-fill"></i></div>
          <div class="proj-body">
            <h5>Hybrid Cloud Network</h5>
            <p>Architected a hybrid multi-cloud network integrating on-premise network with AWS and Azure using Direct Connect and ExpressRoute.</p>
            <div><span class="tag">AWS</span><span class="tag">Azure</span><span class="tag">Terraform</span><span class="tag">Transit Gateway</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/hybrid-cloud" target="_blank" class="proj-btn"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-btn"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- ══ SKILLS ══ -->
<section id="skills">
  <div class="container">
    <div class="sec-head reveal">
      <h2><span class="ch">&gt;</span> Skills &amp; Certifications</h2>
      <div class="sec-underline"></div>
    </div>
    <div class="row g-4 mb-5">
      <div class="col-lg-4 reveal">
        <div class="skill-box">
          <h5>Routing &amp; Switching</h5>
          <div class="sk"><div class="sk-top">BGP<span>95%</span></div><div class="sk-bar"><div class="sk-fill" data-w="95"></div></div></div>
          <div class="sk"><div class="sk-top">OSPF<span>92%</span></div><div class="sk-bar"><div class="sk-fill" data-w="92"></div></div></div>
          <div class="sk"><div class="sk-top">EIGRP<span>85%</span></div><div class="sk-bar"><div class="sk-fill" data-w="85"></div></div></div>
          <div class="sk"><div class="sk-top">MPLS<span>80%</span></div><div class="sk-bar"><div class="sk-fill" data-w="80"></div></div></div>
        </div>
      </div>
      <div class="col-lg-4 reveal">
        <div class="skill-box">
          <h5>Security</h5>
          <div class="sk"><div class="sk-top">Firewall (Palo Alto/Cisco)<span>90%</span></div><div class="sk-bar"><div class="sk-fill" data-w="90"></div></div></div>
          <div class="sk"><div class="sk-top">VPN/IPSec<span>88%</span></div><div class="sk-bar"><div class="sk-fill" data-w="88"></div></div></div>
          <div class="sk"><div class="sk-top">IDS/IPS<span>55%</span></div><div class="sk-bar"><div class="sk-fill" data-w="55"></div></div></div>
          <div class="sk"><div class="sk-top">Zero Trust<span>75%</span></div><div class="sk-bar"><div class="sk-fill" data-w="75"></div></div></div>
        </div>
      </div>
      <div class="col-lg-4 reveal">
        <div class="skill-box">
          <h5>Cloud &amp; Automation</h5>
          <div class="sk"><div class="sk-top">AWS Networking<span>85%</span></div><div class="sk-bar"><div class="sk-fill" data-w="85"></div></div></div>
          <div class="sk"><div class="sk-top">Azure Networking<span>80%</span></div><div class="sk-bar"><div class="sk-fill" data-w="80"></div></div></div>
          <div class="sk"><div class="sk-top">Ansible<span>82%</span></div><div class="sk-bar"><div class="sk-fill" data-w="82"></div></div></div>
          <div class="sk"><div class="sk-top">Python<span>52%</span></div><div class="sk-bar"><div class="sk-fill" data-w="52"></div></div></div>
        </div>
      </div>
    </div>
    <p class="text-center mb-3 reveal" style="font-family:var(--mono);font-size:.85rem;color:var(--text);">Certifications</p>
    <div class="row g-3 justify-content-center reveal">
      <div class="col-md-3 col-6"><div class="cert"><div class="cname">CCNP Enterprise</div><div class="cissue">Cisco</div></div></div>
      <div class="col-md-3 col-6"><div class="cert"><div class="cname">AWS Solutions Architect</div><div class="cissue">Amazon</div></div></div>
      <div class="col-md-3 col-6"><div class="cert"><div class="cname">CompTIA Security+</div><div class="cissue">CompTIA</div></div></div>
      <div class="col-md-3 col-6"><div class="cert"><div class="cname">PCNSA</div><div class="cissue">Palo Alto Networks</div></div></div>
    </div>
  </div>
</section>
 
<!-- ══ CONTACT ══ -->
<section id="contact">
  <div class="container">
    <div class="sec-head reveal">
      <h2><span class="ch">&gt;</span> Contact</h2>
      <div class="sec-underline"></div>
      <p class="sec-sub">Let's connect and discuss how I can help with your network infrastructure needs</p>
    </div>
    <div class="row g-4 reveal">
      <div class="col-lg-4">
        <p class="cinfo-label">Get in Touch</p>
        <div class="cinfo">
          <a href="mailto:contact@example.com"><i class="bi bi-envelope"></i> contact@example.com</a>
          <a href="#"><i class="bi bi-geo-alt"></i> San Francisco, CA</a>
        </div>
        <p class="cinfo-label mt-4">Connect on</p>
        <div class="social-row">
          <a href="https://linkedin.com/in/yourprofile" target="_blank" class="soc-btn"><i class="bi bi-linkedin"></i></a>
          <a href="https://github.com/yourusername" target="_blank" class="soc-btn"><i class="bi bi-github"></i></a>
        </div>
      </div>
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
              <div class="ff"><label for="fn">name</label><input type="text" id="fn" placeholder="Jane Doe" required/></div>
              <div class="ff"><label for="fe">email</label><input type="email" id="fe" placeholder="john@example.com" required/></div>
              <div class="ff"><label for="fm">message</label><textarea id="fm" placeholder="Your message here ..." required></textarea></div>
              <button type="submit" class="btn-send">Send Message</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- ══ FOOTER ══ -->
<footer>
  <div class="container">
    <div class="d-flex flex-column flex-md-row justify-content-between align-items-center gap-2">
      <span class="footer-brand">&lt;NetEngineer /&gt;</span>
      <p>&copy; 2025 All rights reserved.</p>
      <p>Built with <span style="color:var(--accent)">Bootstrap</span> &amp; GitHub Pages</p>
    </div>
  </div>
</footer>
 
<!-- Bootstrap 5 JS -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc4s9bIOgUxi8T/jzmJ/2N5a8U9eiRHMO7j2iFQP0v9a" crossorigin="anonymous"></script>
 
<script>
  // Scroll reveal
  const obs = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) setTimeout(() => e.target.classList.add('show'), i * 80);
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
 
  // Skill bars animate when visible
  const barObs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting)
        e.target.querySelectorAll('.sk-fill').forEach(b => b.style.width = b.dataset.w + '%');
    });
  }, { threshold: 0.4 });
  document.querySelectorAll('.skill-box').forEach(b => barObs.observe(b));
 
  // Active nav highlight on scroll
  const sections = document.querySelectorAll('section[id]');
  window.addEventListener('scroll', () => {
    let cur = '';
    sections.forEach(s => { if (window.scrollY >= s.offsetTop - 140) cur = s.id; });
    document.querySelectorAll('.nav-link').forEach(l => {
      l.classList.toggle('active', l.getAttribute('href') === '#' + cur);
    });
  });
 
  // Contact form → mailto
  document.getElementById('contactForm').addEventListener('submit', function(e) {
    e.preventDefault();
    const n = document.getElementById('fn').value;
    const em = document.getElementById('fe').value;
    const m = document.getElementById('fm').value;
    window.location.href = `mailto:contact@example.com?subject=${encodeURIComponent('Message from ' + n)}&body=${encodeURIComponent('From: ' + n + ' (' + em + ')\n\n' + m)}`;
  });
</script>
</body>
</html>
