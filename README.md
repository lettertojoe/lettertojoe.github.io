<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>NetEngineer — Your Name</title>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&family=Inter:wght@300;400;500&display=swap" rel="stylesheet"/>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"/>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css" rel="stylesheet"/>
  <style>
    :root {
      --teal:#00e5cc;--teal-dim:rgba(0,229,204,0.12);--teal-border:rgba(0,229,204,0.3);
      --bg:#0a0e0f;--bg2:#0d1214;--card:#111819;--border:rgba(255,255,255,0.07);
      --text:#b8cece;--muted:#506060;--mono:'Fira Code',monospace;
    }
    *{box-sizing:border-box;margin:0;padding:0}
    html{scroll-behavior:smooth}
    body{background:var(--bg);color:var(--text);font-family:'Inter',sans-serif;font-size:14px;font-weight:300;overflow-x:hidden}
    body::after{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.025) 2px,rgba(0,0,0,0.025) 4px);pointer-events:none;z-index:9999}
 
    /* NAVBAR */
    .navbar{background:rgba(10,14,15,0.93);backdrop-filter:blur(10px);border-bottom:1px solid var(--border);padding:14px 0}
    .navbar-brand{font-family:var(--mono);font-size:.95rem;color:var(--teal)!important}
    .navbar-brand span{color:var(--text)}
    .nav-link{font-family:var(--mono);font-size:.78rem;color:var(--muted)!important;padding:6px 14px!important;transition:color .2s}
    .nav-link:hover,.nav-link.active-link{color:var(--teal)!important}
    .btn-resume{font-family:var(--mono);font-size:.78rem;background:transparent;color:var(--teal);border:1px solid var(--teal);border-radius:4px;padding:6px 18px;text-decoration:none;transition:background .2s,color .2s}
    .btn-resume:hover{background:var(--teal);color:#000}
    .navbar-toggler{border-color:var(--teal-border)}
    .navbar-toggler-icon{filter:invert(.7) sepia(1) saturate(5) hue-rotate(130deg)}
 
    /* HERO */
    #hero{min-height:100vh;display:flex;align-items:center;padding:120px 0 80px;text-align:center;position:relative;
      background:radial-gradient(ellipse 70% 50% at 50% 0%,rgba(0,229,204,0.05) 0%,transparent 70%),
      repeating-linear-gradient(0deg,transparent,transparent 39px,rgba(0,229,204,0.025) 39px,rgba(0,229,204,0.025) 40px),
      repeating-linear-gradient(90deg,transparent,transparent 39px,rgba(0,229,204,0.025) 39px,rgba(0,229,204,0.025) 40px),var(--bg)}
    .float-dot{position:absolute;font-size:1.8rem;color:var(--teal);animation:fpulse 3s infinite}
    .float-dot.d1{top:38%;left:10%}
    .float-dot.d2{top:44%;right:10%;animation-delay:1.2s}
    .float-dot.d3{top:60%;left:20%;font-size:1rem;animation-delay:.6s}
    @keyframes fpulse{0%,100%{opacity:.25;transform:scale(1)}50%{opacity:1;transform:scale(1.4)}}
 
    .available-pill{display:inline-flex;align-items:center;gap:8px;border:1px solid var(--teal-border);border-radius:100px;padding:5px 16px;font-family:var(--mono);font-size:.72rem;color:var(--teal);margin-bottom:1.8rem}
    .blink-dot{width:7px;height:7px;border-radius:50%;background:var(--teal);animation:blink 1.4s infinite}
    @keyframes blink{0%,100%{opacity:1}50%{opacity:.15}}
 
    .hero-h1{font-family:var(--mono);font-size:clamp(2rem,5.5vw,3.8rem);font-weight:600;color:#fff;line-height:1.1;margin-bottom:.5rem}
    .hero-h1 .hl{color:var(--teal)}
    .hero-role{font-family:var(--mono);font-size:clamp(1.1rem,2.5vw,1.8rem);color:var(--teal);margin-bottom:1.5rem}
    .cursor-blink{display:inline-block;width:3px;height:1em;background:var(--teal);margin-left:3px;vertical-align:middle;animation:blink 1s infinite}
    .hero-desc{color:var(--muted);font-size:.88rem;max-width:480px;margin:0 auto 2.5rem;line-height:1.85}
 
    .btn-teal{font-family:var(--mono);font-size:.8rem;background:transparent;color:var(--teal);border:1px solid var(--teal);border-radius:4px;padding:11px 28px;text-decoration:none;display:inline-block;transition:background .2s,color .2s}
    .btn-teal:hover{background:var(--teal);color:#000}
    .btn-ghost{font-family:var(--mono);font-size:.8rem;background:transparent;color:var(--text);border:1px solid var(--border);border-radius:4px;padding:11px 28px;text-decoration:none;display:inline-block;transition:border-color .2s,color .2s}
    .btn-ghost:hover{border-color:var(--teal-border);color:var(--teal)}
 
    .hero-stats{margin-top:3rem;padding-top:2rem;border-top:1px solid var(--border);display:flex;justify-content:center;gap:3.5rem}
    .stat-val{font-family:var(--mono);font-size:1.7rem;color:var(--teal);font-weight:600}
    .stat-lbl{font-size:.72rem;color:var(--muted);margin-top:3px}
 
    /* SECTIONS */
    section{padding:90px 0}
    .sec-head{text-align:center;margin-bottom:3rem}
    .sec-head h2{font-family:var(--mono);font-size:1.5rem;color:#fff;font-weight:400}
    .sec-head h2 .ch{color:var(--teal);margin-right:6px}
    .sec-head .uline{width:48px;height:2px;background:var(--teal);margin:10px auto 0}
    .sec-head p{color:var(--muted);font-size:.83rem;margin-top:.7rem}
 
    /* ABOUT */
    #about{background:var(--bg2)}
    .about-text p{color:var(--text);font-size:.86rem;line-height:1.9;margin-bottom:1rem}
    .ping-cmd{font-family:var(--mono);font-size:.76rem;background:rgba(0,229,204,0.07);color:var(--teal);border:1px solid var(--teal-border);border-radius:4px;padding:8px 14px;display:inline-block;margin-top:.5rem;cursor:default}
 
    .feat-card{background:var(--card);border:1px solid var(--border);border-radius:8px;padding:20px;height:100%;transition:border-color .3s}
    .feat-card:hover{border-color:var(--teal-border)}
    .feat-card .ficon{color:var(--teal);font-size:1.2rem;margin-bottom:10px}
    .feat-card h6{font-family:var(--mono);font-size:.83rem;color:#fff;margin-bottom:6px}
    .feat-card p{font-size:.77rem;color:var(--muted);line-height:1.6;margin:0}
 
    /* PROJECTS */
    #projects{background:var(--bg);
      background-image:repeating-linear-gradient(0deg,transparent,transparent 39px,rgba(0,229,204,0.02) 39px,rgba(0,229,204,0.02) 40px),
      repeating-linear-gradient(90deg,transparent,transparent 39px,rgba(0,229,204,0.02) 39px,rgba(0,229,204,0.02) 40px)}
 
    .proj-card{background:var(--card);border:1px solid var(--border);border-radius:10px;overflow:hidden;height:100%;transition:border-color .3s,transform .3s}
    .proj-card:hover{border-color:var(--teal-border);transform:translateY(-4px)}
    .proj-thumb{width:100%;aspect-ratio:16/9;background:#0c1719;display:flex;align-items:center;justify-content:center;font-size:3rem;color:rgba(0,229,204,0.12);border-bottom:1px solid var(--border)}
    .proj-body{padding:20px}
    .proj-body h5{font-family:var(--mono);font-size:.9rem;color:#fff;margin-bottom:6px}
    .proj-body p{font-size:.79rem;color:var(--muted);line-height:1.65;margin-bottom:12px}
    .tag{display:inline-block;font-family:var(--mono);font-size:.66rem;color:var(--teal);border:1px solid var(--teal-border);border-radius:3px;padding:2px 7px;margin:2px}
    .proj-links{margin-top:12px;display:flex;gap:7px;flex-wrap:wrap}
    .proj-link{font-family:var(--mono);font-size:.71rem;background:rgba(255,255,255,0.03);color:var(--text);border:1px solid var(--border);border-radius:4px;padding:5px 12px;text-decoration:none;display:inline-flex;align-items:center;gap:5px;transition:border-color .2s,color .2s}
    .proj-link:hover{border-color:var(--teal-border);color:var(--teal)}
 
    /* SKILLS */
    #skills{background:var(--bg2)}
    .skill-box{background:var(--card);border:1px solid var(--border);border-radius:10px;padding:24px;height:100%}
    .skill-box h5{font-family:var(--mono);font-size:.85rem;color:var(--teal);margin-bottom:18px;padding-bottom:10px;border-bottom:1px solid var(--border)}
    .sk-row{margin-bottom:13px}
    .sk-row:last-child{margin-bottom:0}
    .sk-meta{display:flex;justify-content:space-between;font-family:var(--mono);font-size:.73rem;color:var(--text);margin-bottom:5px}
    .sk-meta span{color:var(--teal)}
    .sk-bar{height:4px;background:rgba(255,255,255,0.05);border-radius:2px;overflow:hidden}
    .sk-fill{height:100%;background:var(--teal);border-radius:2px;width:0;transition:width 1.3s ease}
 
    .cert-card{background:var(--card);border:1px solid var(--border);border-radius:8px;padding:16px 20px;text-align:center;transition:border-color .3s}
    .cert-card:hover{border-color:var(--teal-border)}
    .cert-card .cn{font-family:var(--mono);font-size:.8rem;color:#fff;margin-bottom:3px}
    .cert-card .ci{font-size:.71rem;color:var(--muted)}
 
    /* CONTACT */
    #contact{background:var(--bg);
      background-image:repeating-linear-gradient(0deg,transparent,transparent 39px,rgba(0,229,204,0.02) 39px,rgba(0,229,204,0.02) 40px),
      repeating-linear-gradient(90deg,transparent,transparent 39px,rgba(0,229,204,0.02) 39px,rgba(0,229,204,0.02) 40px)}
    .cinfo a{display:flex;align-items:center;gap:12px;color:var(--text);text-decoration:none;padding:10px 0;font-size:.84rem;transition:color .2s;border-bottom:1px solid var(--border)}
    .cinfo a:last-child{border-bottom:none}
    .cinfo a i{color:var(--teal);font-size:1rem;width:18px}
    .cinfo a:hover{color:var(--teal)}
    .socials{display:flex;gap:10px;margin-top:1.5rem}
    .socials a{width:36px;height:36px;border:1px solid var(--border);border-radius:6px;display:flex;align-items:center;justify-content:center;color:var(--muted);text-decoration:none;font-size:.95rem;transition:border-color .2s,color .2s}
    .socials a:hover{border-color:var(--teal-border);color:var(--teal)}
 
    .terminal-wrap{background:#0c1214;border:1px solid var(--border);border-radius:10px;overflow:hidden}
    .term-bar{background:#141d1f;padding:10px 16px;display:flex;align-items:center;gap:6px;border-bottom:1px solid var(--border)}
    .tdot{width:10px;height:10px;border-radius:50%}
    .term-bar .tl{margin-left:8px;font-family:var(--mono);font-size:.73rem;color:var(--muted)}
    .term-body{padding:22px}
    .ff{margin-bottom:15px}
    .ff label{display:block;font-family:var(--mono);font-size:.71rem;color:var(--teal);margin-bottom:6px}
    .ff label::before{content:'$ '}
    .ff input,.ff textarea{width:100%;background:rgba(255,255,255,0.03);border:1px solid var(--border);border-radius:5px;color:#fff;padding:10px 13px;font-family:var(--mono);font-size:.8rem;outline:none;transition:border-color .2s}
    .ff input:focus,.ff textarea:focus{border-color:var(--teal-border)}
    .ff input::placeholder,.ff textarea::placeholder{color:var(--muted)}
    .ff textarea{resize:none;min-height:95px}
    .btn-send{width:100%;background:var(--teal);color:#000;border:none;border-radius:5px;padding:12px;font-family:var(--mono);font-size:.83rem;font-weight:600;cursor:pointer;transition:opacity .2s}
    .btn-send:hover{opacity:.85}
 
    /* FOOTER */
    footer{background:#080c0d;border-top:1px solid var(--border);padding:22px 0}
    footer p,footer span{font-family:var(--mono);font-size:.73rem;color:var(--muted)}
    .footer-brand{font-family:var(--mono);font-size:.82rem;color:var(--teal)}
 
    /* ANIMATIONS */
    .fade-up{opacity:0;transform:translateY(22px);transition:opacity .6s ease,transform .6s ease}
    .fade-up.visible{opacity:1;transform:none}
  </style>
</head>
<body>
 
<!-- NAVBAR -->
<nav class="navbar navbar-expand-lg fixed-top">
  <div class="container">
    <a class="navbar-brand" href="#hero"><span>&lt;</span>NetEngineer<span>/&gt;</span></a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navMenu">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse justify-content-end" id="navMenu">
      <ul class="navbar-nav align-items-lg-center gap-lg-1">
        <li class="nav-item"><a class="nav-link" href="#about">About</a></li>
        <li class="nav-item"><a class="nav-link" href="#projects">Projects</a></li>
        <li class="nav-item"><a class="nav-link" href="#skills">Skills</a></li>
        <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
      </ul>
      <a href="#" class="btn-resume ms-lg-3 mt-3 mt-lg-0">Resume</a>
    </div>
  </div>
</nav>
 
<!-- HERO -->
<section id="hero">
  <span class="float-dot d1">·</span>
  <span class="float-dot d2">·</span>
  <span class="float-dot d3">·</span>
  <div class="container">
    <div class="available-pill"><span class="blink-dot"></span> Available for projects</div>
    <h1 class="hero-h1">
      <span class="hl">·</span>Hi, I'm <span class="hl">Your Name</span><span class="hl">·</span>
    </h1>
    <div class="hero-role">Network Engineer<span class="cursor-blink"></span></div>
    <p class="hero-desc">Building secure, scalable network infrastructures. Specializing in enterprise networking, cloud architecture, and cybersecurity solutions.</p>
    <div class="d-flex flex-wrap justify-content-center gap-3">
      <a href="#projects" class="btn-teal">View Projects</a>
      <a href="#contact" class="btn-ghost">Get In Touch</a>
    </div>
    <div class="hero-stats">
      <div><div class="stat-val">50+</div><div class="stat-lbl">Networks Designed</div></div>
      <div><div class="stat-val">100+</div><div class="stat-lbl">Servers Configured</div></div>
      <div><div class="stat-val">99.9%</div><div class="stat-lbl">Uptime Achieved</div></div>
    </div>
  </div>
</section>
 
<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="sec-head fade-up">
      <h2><span class="ch">&gt;</span> About Me</h2>
      <div class="uline"></div>
    </div>
    <div class="row g-5">
      <div class="col-lg-5 fade-up">
        <div class="about-text">
          <p>With over 5 years of experience in network engineering, I specialize in designing, implementing, and maintaining network infrastructures that power modern businesses.</p>
          <p>My expertise spans across routing protocols (BGP, OSPF, EIGRP), switching technologies, firewall configurations, and cloud networking. I hold certifications including CCNP, AWS Solutions Architect, and CompTIA Security+.</p>
          <p>I'm passionate about network automation and believe in building infrastructures that are not only reliable but also easy to manage and scale.</p>
          <span class="ping-cmd">$ ping passion --count infinite</span>
        </div>
      </div>
      <div class="col-lg-7 fade-up">
        <div class="row g-3">
          <div class="col-md-6">
            <div class="feat-card">
              <div class="ficon"><i class="bi bi-diagram-3-fill"></i></div>
              <h6>Enterprise Networks</h6>
              <p>Designing and implementing large-scale network infrastructures for Fortune 500 companies.</p>
            </div>
          </div>
          <div class="col-md-6">
            <div class="feat-card">
              <div class="ficon"><i class="bi bi-cloud-fill"></i></div>
              <h6>Cloud Architecture</h6>
              <p>Building hybrid cloud solutions with AWS, Azure, and on-premise data centers.</p>
            </div>
          </div>
          <div class="col-md-6">
            <div class="feat-card">
              <div class="ficon"><i class="bi bi-code-slash"></i></div>
              <h6>Network Automation</h6>
              <p>Developing Python and Ansible scripts for automated network provisioning.</p>
            </div>
          </div>
          <div class="col-md-6">
            <div class="feat-card">
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
 
<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="sec-head fade-up">
      <h2><span class="ch">&gt;</span> Projects</h2>
      <div class="uline"></div>
      <p>A selection of network infrastructure projects I've designed and implemented</p>
    </div>
    <div class="row g-4">
      <div class="col-md-6 fade-up">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-diagram-3-fill"></i></div>
          <div class="proj-body">
            <h5>Enterprise Campus Network</h5>
            <p>Designed and implemented a full campus network for a university with 10,000+ users. Included core, distribution, and access layers with redundant paths.</p>
            <div><span class="tag">Cisco</span><span class="tag">EIGRP</span><span class="tag">VLAN</span><span class="tag">QoS</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/campus-network" target="_blank" class="proj-link"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-link"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 fade-up">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-shield-lock-fill"></i></div>
          <div class="proj-body">
            <h5>Multi-Site VPN Infrastructure</h5>
            <p>Built a secure SD-WAN solution connecting 15 branch offices to headquarters with automatic failover and traffic optimisation.</p>
            <div><span class="tag">SD-WAN</span><span class="tag">IPSec</span><span class="tag">BGP</span><span class="tag">AWS</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/vpn-infra" target="_blank" class="proj-link"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-link"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 fade-up">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-hdd-stack-fill"></i></div>
          <div class="proj-body">
            <h5>Data Center Migration</h5>
            <p>Led the migration of legacy infrastructure to a modern data center with spine-leaf architecture, reducing latency by 40%.</p>
            <div><span class="tag">VXLAN</span><span class="tag">BGP-EVPN</span><span class="tag">Ansible</span><span class="tag">Python</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/dc-migration" target="_blank" class="proj-link"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-link"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 fade-up">
        <div class="proj-card">
          <div class="proj-thumb"><i class="bi bi-cloud-arrow-up-fill"></i></div>
          <div class="proj-body">
            <h5>Hybrid Cloud Network</h5>
            <p>Architected a hybrid multi-cloud network integrating on-premise network with AWS and Azure using Direct Connect and ExpressRoute.</p>
            <div><span class="tag">AWS</span><span class="tag">Azure</span><span class="tag">Terraform</span><span class="tag">Transit Gateway</span></div>
            <div class="proj-links">
              <a href="https://github.com/yourusername/hybrid-cloud" target="_blank" class="proj-link"><i class="bi bi-github"></i> Code</a>
              <a href="#" class="proj-link"><i class="bi bi-info-circle"></i> Details</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="sec-head fade-up">
      <h2><span class="ch">&gt;</span> Skills &amp; Certifications</h2>
      <div class="uline"></div>
    </div>
    <div class="row g-4 mb-5">
      <div class="col-lg-4 fade-up">
        <div class="skill-box">
          <h5>Routing &amp; Switching</h5>
          <div class="sk-row"><div class="sk-meta">BGP<span>95%</span></div><div class="sk-bar"><div class="sk-fill" data-w="95"></div></div></div>
          <div class="sk-row"><div class="sk-meta">OSPF<span>92%</span></div><div class="sk-bar"><div class="sk-fill" data-w="92"></div></div></div>
          <div class="sk-row"><div class="sk-meta">EIGRP<span>85%</span></div><div class="sk-bar"><div class="sk-fill" data-w="85"></div></div></div>
          <div class="sk-row"><div class="sk-meta">MPLS<span>80%</span></div><div class="sk-bar"><div class="sk-fill" data-w="80"></div></div></div>
        </div>
      </div>
      <div class="col-lg-4 fade-up">
        <div class="skill-box">
          <h5>Security</h5>
          <div class="sk-row"><div class="sk-meta">Firewall (Palo Alto/Cisco)<span>90%</span></div><div class="sk-bar"><div class="sk-fill" data-w="90"></div></div></div>
          <div class="sk-row"><div class="sk-meta">VPN/IPSec<span>88%</span></div><div class="sk-bar"><div class="sk-fill" data-w="88"></div></div></div>
          <div class="sk-row"><div class="sk-meta">IDS/IPS<span>55%</span></div><div class="sk-bar"><div class="sk-fill" data-w="55"></div></div></div>
          <div class="sk-row"><div class="sk-meta">Zero Trust<span>75%</span></div><div class="sk-bar"><div class="sk-fill" data-w="75"></div></div></div>
        </div>
      </div>
      <div class="col-lg-4 fade-up">
        <div class="skill-box">
          <h5>Cloud &amp; Automation</h5>
          <div class="sk-row"><div class="sk-meta">AWS Networking<span>85%</span></div><div class="sk-bar"><div class="sk-fill" data-w="85"></div></div></div>
          <div class="sk-row"><div class="sk-meta">Azure Networking<span>80%</span></div><div class="sk-bar"><div class="sk-fill" data-w="80"></div></div></div>
          <div class="sk-row"><div class="sk-meta">Ansible<span>82%</span></div><div class="sk-bar"><div class="sk-fill" data-w="82"></div></div></div>
          <div class="sk-row"><div class="sk-meta">Python<span>52%</span></div><div class="sk-bar"><div class="sk-fill" data-w="52"></div></div></div>
        </div>
      </div>
    </div>
    <h5 class="text-center mb-4 fade-up" style="font-family:var(--mono);font-size:.9rem;color:#fff;font-weight:400;">Certifications</h5>
    <div class="row g-3 justify-content-center fade-up">
      <div class="col-md-3 col-6"><div class="cert-card"><div class="cn">CCNP Enterprise</div><div class="ci">Cisco</div></div></div>
      <div class="col-md-3 col-6"><div class="cert-card"><div class="cn">AWS Solutions Architect</div><div class="ci">Amazon</div></div></div>
      <div class="col-md-3 col-6"><div class="cert-card"><div class="cn">CompTIA Security+</div><div class="ci">CompTIA</div></div></div>
      <div class="col-md-3 col-6"><div class="cert-card"><div class="cn">PCNSA</div><div class="ci">Palo Alto Networks</div></div></div>
    </div>
  </div>
</section>
 
<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="sec-head fade-up">
      <h2><span class="ch">&gt;</span> Contact</h2>
      <div class="uline"></div>
      <p>Let's connect and discuss how I can help with your network infrastructure needs</p>
    </div>
    <div class="row g-4 fade-up">
      <div class="col-lg-4">
        <h6 style="font-family:var(--mono);font-size:.8rem;color:#fff;margin-bottom:1rem;">Get in Touch</h6>
        <div class="cinfo">
          <a href="mailto:contact@example.com"><i class="bi bi-envelope"></i> contact@example.com</a>
          <a href="#"><i class="bi bi-geo-alt"></i> San Francisco, CA</a>
        </div>
        <h6 style="font-family:var(--mono);font-size:.8rem;color:#fff;margin-top:1.5rem;margin-bottom:.75rem;">Connect on</h6>
        <div class="socials">
          <a href="https://linkedin.com/in/yourprofile" target="_blank"><i class="bi bi-linkedin"></i></a>
          <a href="https://github.com/yourusername" target="_blank"><i class="bi bi-github"></i></a>
        </div>
      </div>
      <div class="col-lg-8">
        <div class="terminal-wrap">
          <div class="term-bar">
            <span class="tdot" style="background:#ff5f57"></span>
            <span class="tdot" style="background:#febc2e"></span>
            <span class="tdot" style="background:#28c840"></span>
            <span class="tl">&gt;_ Terminal</span>
          </div>
          <div class="term-body">
            <form id="cForm">
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
 
<!-- FOOTER -->
<footer>
  <div class="container">
    <div class="d-flex flex-column flex-md-row justify-content-between align-items-center gap-2">
      <span class="footer-brand">&lt;NetEngineer /&gt;</span>
      <p>&copy; 2025 All rights reserved.</p>
      <p>Built with <span style="color:var(--teal)">Bootstrap</span> &amp; GitHub Pages</p>
    </div>
  </div>
</footer>
 
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
<script>
  // Fade in on scroll
  const fadeEls = document.querySelectorAll('.fade-up');
  const obs = new IntersectionObserver(entries => {
    entries.forEach((e,i) => { if(e.isIntersecting) setTimeout(()=>e.target.classList.add('visible'), i*70); });
  }, {threshold:0.1});
  fadeEls.forEach(el => obs.observe(el));
 
  // Skill bars
  const skObs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if(e.isIntersecting) e.target.querySelectorAll('.sk-fill').forEach(b => b.style.width = b.dataset.w+'%');
    });
  }, {threshold:0.3});
  document.querySelectorAll('.skill-box').forEach(g => skObs.observe(g));
 
  // Active nav highlight
  const secs = document.querySelectorAll('section[id]');
  window.addEventListener('scroll', () => {
    let cur='';
    secs.forEach(s => { if(window.scrollY >= s.offsetTop-130) cur=s.id; });
    document.querySelectorAll('.nav-link').forEach(l => {
      l.classList.toggle('active-link', l.getAttribute('href')==='#'+cur);
    });
  });
 
  // Contact form → mailto
  document.getElementById('cForm').addEventListener('submit', e => {
    e.preventDefault();
    const n=document.getElementById('fn').value, em=document.getElementById('fe').value, m=document.getElementById('fm').value;
    window.location.href=`mailto:contact@example.com?subject=${encodeURIComponent('Message from '+n)}&body=${encodeURIComponent('From: '+n+' ('+em+')\n\n'+m)}`;
  });
</script>
</body>
</html>
