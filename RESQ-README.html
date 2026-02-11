<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RESQ — Disaster Response Platform</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --red:     #e8291c;
      --red-dim: #7a130d;
      --orange:  #ff6b2b;
      --amber:   #f5a623;
      --dark:    #0a0a0b;
      --surface: #111114;
      --panel:   #18181d;
      --border:  #2a2a33;
      --text:    #e8e8ed;
      --muted:   #7a7a8a;
      --accent:  #00d4ff;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--dark);
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      font-size: 15px;
      line-height: 1.7;
      overflow-x: hidden;
    }

    /* ── NOISE OVERLAY ── */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      opacity: 0.4;
    }

    /* ── SCANLINE EFFECT ── */
    body::after {
      content: '';
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background: repeating-linear-gradient(
        0deg, transparent, transparent 2px,
        rgba(0,0,0,0.04) 2px, rgba(0,0,0,0.04) 4px
      );
    }

    .page { position: relative; z-index: 1; max-width: 960px; margin: 0 auto; padding: 0 24px 80px; }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex; flex-direction: column; justify-content: center; align-items: flex-start;
      padding: 80px 0 60px;
      position: relative;
    }

    .hero-bg {
      position: absolute; inset: 0; overflow: hidden; pointer-events: none;
    }
    .hero-bg-ring {
      position: absolute;
      border-radius: 50%;
      border: 1px solid rgba(232,41,28,0.12);
      animation: expandRing 6s ease-out infinite;
    }
    .hero-bg-ring:nth-child(1) { width: 400px; height: 400px; right: -100px; top: 50%; transform: translateY(-50%); animation-delay: 0s; }
    .hero-bg-ring:nth-child(2) { width: 650px; height: 650px; right: -225px; top: 50%; transform: translateY(-50%); animation-delay: 2s; }
    .hero-bg-ring:nth-child(3) { width: 900px; height: 900px; right: -350px; top: 50%; transform: translateY(-50%); animation-delay: 4s; }

    @keyframes expandRing {
      0%   { opacity: 0.8; }
      100% { opacity: 0; }
    }

    .hero-tag {
      font-family: 'DM Mono', monospace;
      font-size: 11px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--red);
      background: rgba(232,41,28,0.1);
      border: 1px solid rgba(232,41,28,0.25);
      padding: 5px 14px;
      border-radius: 2px;
      margin-bottom: 28px;
      display: inline-block;
      animation: fadeUp 0.6s ease both;
    }

    .hero-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(72px, 12vw, 128px);
      line-height: 0.9;
      letter-spacing: 0.02em;
      animation: fadeUp 0.6s 0.1s ease both;
    }

    .hero-title .r { color: var(--red); }
    .hero-title .e { color: var(--orange); }
    .hero-title .s { color: var(--amber); }
    .hero-title .q { color: var(--text); }

    .hero-expand {
      font-family: 'DM Mono', monospace;
      font-size: 11px;
      letter-spacing: 0.15em;
      color: var(--muted);
      margin-top: 10px;
      animation: fadeUp 0.6s 0.2s ease both;
    }

    .hero-desc {
      max-width: 560px;
      font-size: 17px;
      font-weight: 300;
      color: rgba(232,232,237,0.75);
      margin-top: 28px;
      line-height: 1.65;
      animation: fadeUp 0.6s 0.3s ease both;
    }

    .hero-stats {
      display: flex; gap: 0; margin-top: 48px;
      border: 1px solid var(--border); border-radius: 4px;
      overflow: hidden;
      animation: fadeUp 0.6s 0.4s ease both;
    }

    .stat {
      padding: 18px 32px;
      border-right: 1px solid var(--border);
      background: var(--panel);
    }
    .stat:last-child { border-right: none; }
    .stat-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 36px;
      line-height: 1;
      color: var(--red);
    }
    .stat-label {
      font-size: 11px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--muted);
      margin-top: 4px;
    }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── SECTION HEADERS ── */
    .section { margin-top: 80px; }

    .section-label {
      font-family: 'DM Mono', monospace;
      font-size: 10px;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: var(--red);
      margin-bottom: 12px;
    }

    .section-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(36px, 5vw, 52px);
      letter-spacing: 0.04em;
      line-height: 1;
      margin-bottom: 28px;
    }

    /* ── DIVIDER ── */
    .divider {
      height: 1px;
      background: linear-gradient(90deg, var(--red), transparent);
      margin-bottom: 32px;
    }

    /* ── FEATURE GRID ── */
    .feature-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(270px, 1fr));
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
    }

    .feature-card {
      background: var(--panel);
      padding: 28px;
      transition: background 0.2s;
    }
    .feature-card:hover { background: #1e1e24; }

    .feature-icon {
      width: 38px; height: 38px;
      border-radius: 4px;
      display: flex; align-items: center; justify-content: center;
      font-size: 18px;
      margin-bottom: 16px;
    }
    .icon-red    { background: rgba(232,41,28,0.12); }
    .icon-orange { background: rgba(255,107,43,0.12); }
    .icon-amber  { background: rgba(245,166,35,0.12); }
    .icon-cyan   { background: rgba(0,212,255,0.1); }
    .icon-green  { background: rgba(0,210,120,0.1); }
    .icon-purple { background: rgba(160,100,255,0.1); }

    .feature-title {
      font-weight: 600;
      font-size: 14px;
      margin-bottom: 8px;
      letter-spacing: 0.02em;
    }

    .feature-desc {
      font-size: 13px;
      color: var(--muted);
      line-height: 1.6;
    }

    /* ── WORKFLOW ── */
    .flow-steps { display: flex; flex-direction: column; gap: 0; }

    .flow-step {
      display: grid;
      grid-template-columns: 56px 1fr;
      gap: 24px;
      padding: 28px 0;
      border-bottom: 1px solid var(--border);
      position: relative;
    }
    .flow-step:last-child { border-bottom: none; }

    .step-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 42px;
      color: var(--red-dim);
      line-height: 1;
      padding-top: 4px;
    }

    .step-content {}
    .step-title {
      font-weight: 600;
      font-size: 15px;
      margin-bottom: 6px;
      color: var(--text);
    }
    .step-desc {
      font-size: 13px;
      color: var(--muted);
      line-height: 1.6;
    }

    /* ── TECH STACK ── */
    .tech-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 12px;
    }

    .tech-group {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 20px;
    }

    .tech-group-title {
      font-family: 'DM Mono', monospace;
      font-size: 10px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 14px;
    }

    .tech-list { list-style: none; }
    .tech-list li {
      font-size: 13px;
      color: var(--muted);
      padding: 4px 0;
      border-bottom: 1px solid rgba(255,255,255,0.04);
      display: flex; align-items: center; gap: 8px;
    }
    .tech-list li:last-child { border-bottom: none; }
    .tech-dot {
      width: 5px; height: 5px; border-radius: 50%;
      background: var(--red); flex-shrink: 0;
    }

    /* ── FILE TREE ── */
    .tree {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 24px;
      font-family: 'DM Mono', monospace;
      font-size: 13px;
      line-height: 2;
      overflow-x: auto;
    }

    .tree-line { display: flex; align-items: center; gap: 0; }
    .tree-indent { color: var(--border); padding-right: 2px; }
    .tree-dir  { color: var(--amber); }
    .tree-file { color: var(--muted); }
    .tree-file.hl { color: var(--text); }
    .tree-comment { color: #3d3d4d; font-size: 11px; margin-left: 12px; }

    /* ── CODE BLOCKS ── */
    .code-block {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
      margin: 16px 0;
    }

    .code-header {
      display: flex; align-items: center; gap: 8px;
      padding: 10px 16px;
      border-bottom: 1px solid var(--border);
      background: rgba(255,255,255,0.02);
    }

    .code-dot { width: 10px; height: 10px; border-radius: 50%; }
    .cd-r { background: #e8291c; }
    .cd-y { background: #f5a623; }
    .cd-g { background: #1dba5a; }

    .code-lang {
      margin-left: auto;
      font-family: 'DM Mono', monospace;
      font-size: 10px;
      color: var(--muted);
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    .code-body {
      padding: 20px 24px;
      font-family: 'DM Mono', monospace;
      font-size: 13px;
      line-height: 1.9;
      color: var(--muted);
      overflow-x: auto;
    }

    .code-body .cmd { color: var(--accent); }
    .code-body .cmt { color: #3d3d4d; }
    .code-body .str { color: var(--amber); }
    .code-body .kw  { color: var(--orange); }

    /* ── BADGES ── */
    .badges { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 32px; }
    .badge {
      font-family: 'DM Mono', monospace;
      font-size: 10px;
      padding: 4px 12px;
      border-radius: 2px;
      border: 1px solid;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }
    .badge-red    { color: var(--red);    border-color: rgba(232,41,28,0.35);    background: rgba(232,41,28,0.07);    }
    .badge-orange { color: var(--orange); border-color: rgba(255,107,43,0.35);   background: rgba(255,107,43,0.07);   }
    .badge-amber  { color: var(--amber);  border-color: rgba(245,166,35,0.35);   background: rgba(245,166,35,0.07);   }
    .badge-cyan   { color: var(--accent); border-color: rgba(0,212,255,0.3);     background: rgba(0,212,255,0.06);    }
    .badge-green  { color: #00d278;       border-color: rgba(0,210,120,0.3);     background: rgba(0,210,120,0.06);    }

    /* ── ENHANCEMENT CARDS ── */
    .enhance-list { display: flex; flex-direction: column; gap: 10px; }
    .enhance-item {
      display: flex; align-items: flex-start; gap: 16px;
      background: var(--panel);
      border: 1px solid var(--border);
      border-left: 3px solid var(--red-dim);
      border-radius: 0 4px 4px 0;
      padding: 16px 20px;
      transition: border-left-color 0.2s, background 0.2s;
    }
    .enhance-item:hover { border-left-color: var(--red); background: #1a1a20; }
    .enhance-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 22px;
      color: var(--red-dim);
      line-height: 1;
      flex-shrink: 0;
      padding-top: 2px;
      min-width: 28px;
    }
    .enhance-text {}
    .enhance-title {
      font-weight: 600;
      font-size: 14px;
      margin-bottom: 4px;
    }
    .enhance-desc { font-size: 13px; color: var(--muted); }

    /* ── LICENSE ── */
    .license-box {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 32px;
    }
    .license-box p { font-size: 13px; color: var(--muted); margin-top: 12px; line-height: 1.8; }

    /* ── FOOTER ── */
    .footer {
      margin-top: 80px;
      padding: 32px 0;
      border-top: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 12px;
    }

    .footer-brand {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 22px;
      letter-spacing: 0.1em;
    }
    .footer-brand .r { color: var(--red); }
    .footer-brand .e { color: var(--orange); }
    .footer-brand .s { color: var(--amber); }

    .footer-copy {
      font-family: 'DM Mono', monospace;
      font-size: 11px;
      color: var(--muted);
    }

    /* ── ALERT BANNER ── */
    .alert-banner {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      background: var(--red);
      padding: 8px;
      text-align: center;
      font-family: 'DM Mono', monospace;
      font-size: 11px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: #fff;
      animation: alertPulse 3s ease-in-out infinite;
    }
    @keyframes alertPulse {
      0%, 100% { background: var(--red); }
      50%       { background: #c01810; }
    }

    .alert-dot {
      display: inline-block;
      width: 7px; height: 7px;
      background: #fff;
      border-radius: 50%;
      margin-right: 8px;
      animation: blink 1s step-end infinite;
    }
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50%       { opacity: 0; }
    }

    .page { padding-top: 40px; }

    /* ── SCROLLBAR ── */
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: var(--dark); }
    ::-webkit-scrollbar-thumb { background: var(--red-dim); border-radius: 3px; }

    /* ── RESPONSIVE ── */
    @media (max-width: 600px) {
      .hero-stats { flex-direction: column; }
      .stat { border-right: none; border-bottom: 1px solid var(--border); }
      .stat:last-child { border-bottom: none; }
      .flow-step { grid-template-columns: 40px 1fr; gap: 16px; }
    }
  </style>
</head>
<body>

  <div class="alert-banner">
    <span class="alert-dot"></span>
    RESQ · Real-Time Disaster Response Platform · India · v1.0
  </div>

  <div class="page">

    <!-- ═══ HERO ═══ -->
    <section class="hero">
      <div class="hero-bg">
        <div class="hero-bg-ring"></div>
        <div class="hero-bg-ring"></div>
        <div class="hero-bg-ring"></div>
      </div>

      <div class="hero-tag">&#x25CF;&nbsp; Disaster Management System</div>

      <div class="hero-title">
        <span class="r">R</span><span class="e">E</span><span class="s">S</span><span class="q">Q</span>
      </div>

      <div class="hero-expand">Respond · Evacuate · Support · Quickly</div>

      <p class="hero-desc">
        A browser-based emergency response platform for civilians and volunteers during natural disasters. One-click SOS dispatch, interactive Quell Zone mapping across all Indian state capitals, AI-powered chat assistance, and a full volunteer management system.
      </p>

      <div class="hero-stats">
        <div class="stat">
          <div class="stat-num">36+</div>
          <div class="stat-label">State Capitals Mapped</div>
        </div>
        <div class="stat">
          <div class="stat-num">5</div>
          <div class="stat-label">Core Modules</div>
        </div>
        <div class="stat">
          <div class="stat-num">0</div>
          <div class="stat-label">Dependencies to Install</div>
        </div>
      </div>
    </section>


    <!-- ═══ BADGES ═══ -->
    <div class="badges">
      <span class="badge badge-red">Static Frontend</span>
      <span class="badge badge-orange">Leaflet.js Maps</span>
      <span class="badge badge-amber">Geolocation API</span>
      <span class="badge badge-cyan">REST Chatbot API</span>
      <span class="badge badge-green">Responsive</span>
      <span class="badge badge-red">MIT License</span>
    </div>


    <!-- ═══ OVERVIEW ═══ -->
    <section class="section">
      <div class="section-label">// 01 — Overview</div>
      <h2 class="section-title">What is RESQ?</h2>
      <div class="divider"></div>
      <p style="color:rgba(232,232,237,0.75); max-width:680px; font-size:15px;">
        During disasters, civilians face a critical gap: no reliable way to signal for help, locate safe zones, or connect with rescue volunteers. RESQ bridges that gap. It is a zero-install, open-in-browser platform that works on any device, combining GPS-based SOS alerting, an interactive evacuation map pre-loaded with hospitals and shelters, a disaster chatbot, and a volunteer coordination dashboard — all in a single cohesive interface.
      </p>
    </section>


    <!-- ═══ FEATURES ═══ -->
    <section class="section">
      <div class="section-label">// 02 — Features</div>
      <h2 class="section-title">Key Capabilities</h2>
      <div class="divider"></div>
      <div class="feature-grid">

        <div class="feature-card">
          <div class="feature-icon icon-red">🆘</div>
          <div class="feature-title">One-Click SOS Dispatch</div>
          <div class="feature-desc">Captures GPS coordinates via the browser Geolocation API and pins the user on the map instantly. Reveals WhatsApp, email, and emergency call actions post-trigger.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-orange">🗺️</div>
          <div class="feature-title">Interactive Quell Zone Map</div>
          <div class="feature-desc">Leaflet.js map pre-loaded with 2–5 safe zone markers per state capital across all 36 Indian capitals — hospitals, shelters, and relief centers.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-amber">🔀</div>
          <div class="feature-title">Turn-by-Turn Routing</div>
          <div class="feature-desc">Leaflet Routing Machine draws highlighted routes from the user's current GPS position to any searched location or clicked Quell Zone.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-cyan">💬</div>
          <div class="feature-title">QChat Disaster Chatbot</div>
          <div class="feature-desc">Sends user queries to a deployed REST backend on Render and renders responses live. Supports platform navigation actions through response anchor tags.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-green">📡</div>
          <div class="feature-title">Live Location Tracking</div>
          <div class="feature-desc">Polls the Geolocation API every 5 seconds to continuously update the user's marker and map view during an active emergency session.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-purple">🙋</div>
          <div class="feature-title">Volunteer Dashboard</div>
          <div class="feature-desc">Post-login dashboard with task tracker, event calendar, leaderboard, achievement badges, and a Chart.js doughnut breakdown of service hours by category.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-red">🏥</div>
          <div class="feature-title">Health Profile on Registration</div>
          <div class="feature-desc">Two-step signup flow: standard credentials followed by an optional health form capturing allergies, chronic conditions, and medications for triage support.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-amber">💸</div>
          <div class="feature-title">Donation Portal</div>
          <div class="feature-desc">Direct UPI and PayPal donation links on the Services page to fund emergency supplies and relief operations.</div>
        </div>

        <div class="feature-card">
          <div class="feature-icon icon-orange">📞</div>
          <div class="feature-title">Emergency Contact Modal</div>
          <div class="feature-desc">Homepage modal displaying all India emergency numbers: 112 (National), Police 100, Fire 101, Ambulance 108, NDRF hotline.</div>
        </div>

      </div>
    </section>


    <!-- ═══ ARCHITECTURE ═══ -->
    <section class="section">
      <div class="section-label">// 03 — Architecture</div>
      <h2 class="section-title">How It Works</h2>
      <div class="divider"></div>
      <div class="flow-steps">

        <div class="flow-step">
          <div class="step-num">01</div>
          <div class="step-content">
            <div class="step-title">User Opens Platform → Homepage</div>
            <div class="step-desc">The index page loads disaster alert cards, an emergency contact modal (112, NDRF, Police, Fire, Ambulance), and navigation links to all modules. No login required to access SOS or the map.</div>
          </div>
        </div>

        <div class="flow-step">
          <div class="step-num">02</div>
          <div class="step-content">
            <div class="step-title">SOS Trigger → GPS Capture → Map Pin</div>
            <div class="step-desc">On the SOS Hub, pressing the SOS button plays an audio siren, calls <code style="font-family:'DM Mono',monospace;color:var(--amber);font-size:12px;">navigator.geolocation.getCurrentPosition()</code>, drops a custom marker, and reveals sharing options. Location is shared as a Google Maps deep link via WhatsApp URL scheme or a mailto: URI.</div>
          </div>
        </div>

        <div class="flow-step">
          <div class="step-num">03</div>
          <div class="step-content">
            <div class="step-title">Quell Zone Markers → Route to Safety</div>
            <div class="step-desc">On page load, all 36 state capital Quell Zones are rendered as map markers. Clicking a zone popup and pressing "Get Directions" fires Leaflet Routing Machine from the user's current coordinates to the zone, rendering a yellow route overlay.</div>
          </div>
        </div>

        <div class="flow-step">
          <div class="step-num">04</div>
          <div class="step-content">
            <div class="step-title">QChat Message → REST API → Response</div>
            <div class="step-desc">The chatbot frontend sends a GET request to <code style="font-family:'DM Mono',monospace;color:var(--amber);font-size:12px;">https://resq-ziw9.onrender.com/get?msg=&lt;query&gt;</code>. The backend returns <code style="font-family:'DM Mono',monospace;color:var(--amber);font-size:12px;">&#123;"response":"..."&#125;</code>. If the response contains <code style="font-family:'DM Mono',monospace;color:var(--amber);font-size:12px;">data-action</code> anchors, clicking them redirects the user to the relevant page.</div>
          </div>
        </div>

        <div class="flow-step">
          <div class="step-num">05</div>
          <div class="step-content">
            <div class="step-title">Registration → Health Profile → Volunteer Dashboard</div>
            <div class="step-desc">New users register credentials, then optionally complete a health form. Volunteers register on the Services page and access a dashboard with Chart.js activity visualization, task management, event RSVP, and downloadable service reports.</div>
          </div>
        </div>

      </div>
    </section>


    <!-- ═══ TECH STACK ═══ -->
    <section class="section">
      <div class="section-label">// 04 — Stack</div>
      <h2 class="section-title">Technology Stack</h2>
      <div class="divider"></div>
      <div class="tech-grid">

        <div class="tech-group">
          <div class="tech-group-title">Frontend</div>
          <ul class="tech-list">
            <li><span class="tech-dot"></span> HTML5</li>
            <li><span class="tech-dot"></span> CSS3</li>
            <li><span class="tech-dot"></span> Vanilla JavaScript (ES6+)</li>
            <li><span class="tech-dot"></span> Google Fonts — Poppins</li>
          </ul>
        </div>

        <div class="tech-group">
          <div class="tech-group-title">Maps & Routing</div>
          <ul class="tech-list">
            <li><span class="tech-dot"></span> Leaflet.js</li>
            <li><span class="tech-dot"></span> Leaflet Routing Machine</li>
            <li><span class="tech-dot"></span> OpenStreetMap Tiles</li>
            <li><span class="tech-dot"></span> Nominatim Geocoding API</li>
          </ul>
        </div>

        <div class="tech-group">
          <div class="tech-group-title">UI Libraries</div>
          <ul class="tech-list">
            <li><span class="tech-dot"></span> Font Awesome 6</li>
            <li><span class="tech-dot"></span> Boxicons 2.1.4</li>
            <li><span class="tech-dot"></span> Chart.js</li>
          </ul>
        </div>

        <div class="tech-group">
          <div class="tech-group-title">APIs & Integrations</div>
          <ul class="tech-list">
            <li><span class="tech-dot"></span> Browser Geolocation API</li>
            <li><span class="tech-dot"></span> WhatsApp URL Scheme</li>
            <li><span class="tech-dot"></span> mailto: URI</li>
            <li><span class="tech-dot"></span> UPI Deep Link</li>
            <li><span class="tech-dot"></span> PayPal Donate URL</li>
          </ul>
        </div>

        <div class="tech-group">
          <div class="tech-group-title">Backend</div>
          <ul class="tech-list">
            <li><span class="tech-dot"></span> REST API on Render</li>
            <li><span class="tech-dot"></span> GET /get?msg= endpoint</li>
            <li><span class="tech-dot"></span> JSON response format</li>
          </ul>
        </div>

        <div class="tech-group">
          <div class="tech-group-title">Deploy / Serve</div>
          <ul class="tech-list">
            <li><span class="tech-dot"></span> Any static file server</li>
            <li><span class="tech-dot"></span> Python http.server</li>
            <li><span class="tech-dot"></span> Node.js http-server</li>
            <li><span class="tech-dot"></span> VS Code Live Server</li>
          </ul>
        </div>

      </div>
    </section>


    <!-- ═══ PROJECT STRUCTURE ═══ -->
    <section class="section">
      <div class="section-label">// 05 — Structure</div>
      <h2 class="section-title">Project Structure</h2>
      <div class="divider"></div>
      <div class="tree">
        <div class="tree-line"><span class="tree-dir">RESQ-main/</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-file hl">index.html</span><span class="tree-comment">← Homepage, alert cards, emergency modal</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-file hl">sos.html</span><span class="tree-comment">← SOS Hub, map, Quell Zones, routing (695 lines)</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-file hl">Qchat.html</span><span class="tree-comment">← Chatbot UI, REST API integration</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-file hl">service.html</span><span class="tree-comment">← Mission, donations, volunteer registration</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-file hl">volunteer.html</span><span class="tree-comment">← Dashboard, Chart.js, tasks, badges</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-file hl">ppj.html</span><span class="tree-comment">← Login / register + health profile</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-file">exp.html</span><span class="tree-comment">← About / Explore page</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-dir">css/</span></div>
        <div class="tree-line"><span class="tree-indent">│   ├── </span><span class="tree-file">index.css</span></div>
        <div class="tree-line"><span class="tree-indent">│   ├── </span><span class="tree-file">ppj.css</span></div>
        <div class="tree-line"><span class="tree-indent">│   └── </span><span class="tree-file">volunteer.css</span></div>
        <div class="tree-line"><span class="tree-indent">├── </span><span class="tree-dir">js/</span></div>
        <div class="tree-line"><span class="tree-indent">│   ├── </span><span class="tree-file">index.js</span></div>
        <div class="tree-line"><span class="tree-indent">│   └── </span><span class="tree-file">ppj.js</span></div>
        <div class="tree-line"><span class="tree-indent">└── </span><span class="tree-dir">images/</span></div>
        <div class="tree-line"><span class="tree-indent">&nbsp;&nbsp;&nbsp; ├── </span><span class="tree-file">RESQ.jpg</span><span class="tree-comment">← Platform logo</span></div>
        <div class="tree-line"><span class="tree-indent">&nbsp;&nbsp;&nbsp; ├── </span><span class="tree-file">chatbotbg.jpg</span></div>
        <div class="tree-line"><span class="tree-indent">&nbsp;&nbsp;&nbsp; ├── </span><span class="tree-file">explore.jpg</span></div>
        <div class="tree-line"><span class="tree-indent">&nbsp;&nbsp;&nbsp; └── </span><span class="tree-file">icon.jpg</span></div>
      </div>
    </section>


    <!-- ═══ SETUP ═══ -->
    <section class="section">
      <div class="section-label">// 06 — Setup</div>
      <h2 class="section-title">Installation & Setup</h2>
      <div class="divider"></div>

      <p style="color:var(--muted); margin-bottom:20px; font-size:14px;">No build step. No package manager. Clone and serve.</p>

      <div class="code-block">
        <div class="code-header">
          <div class="code-dot cd-r"></div><div class="code-dot cd-y"></div><div class="code-dot cd-g"></div>
          <span class="code-lang">bash</span>
        </div>
        <div class="code-body">
<span class="cmt"># Clone the repository</span>
<span class="cmd">git clone</span> https://github.com/&lt;your-username&gt;/RESQ.git
<span class="cmd">cd</span> RESQ

<span class="cmt"># Option A — Python 3</span>
<span class="cmd">python -m http.server</span> <span class="str">8080</span>

<span class="cmt"># Option B — Node.js</span>
<span class="cmd">npm install -g</span> http-server
<span class="cmd">http-server -p</span> <span class="str">8080</span>

<span class="cmt"># Open in browser</span>
<span class="kw">open</span> http://localhost:8080
        </div>
      </div>

      <p style="color:var(--muted); margin-top:20px; font-size:13px;">
        <strong style="color:var(--amber);">Chatbot backend:</strong> The QChat module calls <code style="font-family:'DM Mono',monospace;color:var(--text);font-size:12px;">https://resq-ziw9.onrender.com/get?msg=</code>. To use your own backend, replace this URL in <code style="font-family:'DM Mono',monospace;color:var(--text);font-size:12px;">Qchat.html</code>. The endpoint must return <code style="font-family:'DM Mono',monospace;color:var(--text);font-size:12px;">{ "response": "string" }</code>.<br><br>
        <strong style="color:var(--amber);">Geolocation:</strong> Requires HTTPS in production. Works over HTTP locally with a browser permission prompt.<br><br>
        <strong style="color:var(--amber);">Donations:</strong> Replace placeholder UPI (<code style="font-family:'DM Mono',monospace;color:var(--text);font-size:12px;">donate@upi</code>) and PayPal email in <code style="font-family:'DM Mono',monospace;color:var(--text);font-size:12px;">service.html</code> before deploying.
      </p>
    </section>


    <!-- ═══ FUTURE ═══ -->
    <section class="section">
      <div class="section-label">// 07 — Roadmap</div>
      <h2 class="section-title">Future Enhancements</h2>
      <div class="divider"></div>
      <div class="enhance-list">

        <div class="enhance-item">
          <div class="enhance-num">01</div>
          <div class="enhance-text">
            <div class="enhance-title">Persistent Backend & User Database</div>
            <div class="enhance-desc">Replace client-only registration with a server-side database (Firebase or PostgreSQL) to persist user accounts, health profiles, and volunteer records across sessions.</div>
          </div>
        </div>

        <div class="enhance-item">
          <div class="enhance-num">02</div>
          <div class="enhance-text">
            <div class="enhance-title">Live Weather Integration</div>
            <div class="enhance-desc">Connect the SOS Hub weather panel to OpenWeatherMap API using captured GPS coordinates, replacing the current simulated weather string.</div>
          </div>
        </div>

        <div class="enhance-item">
          <div class="enhance-num">03</div>
          <div class="enhance-text">
            <div class="enhance-title">Admin Operations Dashboard</div>
            <div class="enhance-desc">Build a coordinator panel for NDRF / SDMA operators to monitor active SOS pins on a central map, assign volunteers in real time, and update Quell Zone availability.</div>
          </div>
        </div>

        <div class="enhance-item">
          <div class="enhance-num">04</div>
          <div class="enhance-text">
            <div class="enhance-title">Web Push Notifications</div>
            <div class="enhance-desc">Deliver real-time disaster alerts via the Web Push API to registered users based on their stored geographic region.</div>
          </div>
        </div>

        <div class="enhance-item">
          <div class="enhance-num">05</div>
          <div class="enhance-text">
            <div class="enhance-title">Offline Support via Service Workers</div>
            <div class="enhance-desc">Cache the SOS page and emergency contacts offline using a service worker — critical when network connectivity fails during disasters.</div>
          </div>
        </div>

        <div class="enhance-item">
          <div class="enhance-num">06</div>
          <div class="enhance-text">
            <div class="enhance-title">Multilingual Interface</div>
            <div class="enhance-desc">Add localization for Hindi, Tamil, Telugu, and Bengali to improve accessibility for non-English speakers during emergencies.</div>
          </div>
        </div>

      </div>
    </section>


    <!-- ═══ LICENSE ═══ -->
    <section class="section">
      <div class="section-label">// 08 — License</div>
      <h2 class="section-title">License</h2>
      <div class="divider"></div>
      <div class="license-box">
        <div class="badges" style="margin-bottom:16px;">
          <span class="badge badge-green">MIT License</span>
          <span class="badge badge-cyan">Open Source</span>
        </div>
        <p>Copyright &copy; 2025 RESQ. Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction — including the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies — subject to the above copyright notice being included in all copies or substantial portions of the software.</p>
        <p>THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND. THE AUTHORS ARE NOT LIABLE FOR ANY CLAIM, DAMAGES, OR OTHER LIABILITY ARISING FROM THE USE OF THE SOFTWARE.</p>
      </div>
    </section>


    <!-- ═══ FOOTER ═══ -->
    <div class="footer">
      <div class="footer-brand">
        <span class="r">R</span><span class="e">E</span><span class="s">S</span>Q
      </div>
      <div class="footer-copy">Respond · Evacuate · Support · Quickly &nbsp;|&nbsp; © 2025 RESQ</div>
    </div>

  </div><!-- end .page -->

</body>
</html>
