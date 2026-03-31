# nikhildubey.github.io
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nikhil Dubey — Menace to Monk</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1a1410;
    --parchment: #f5f0e8;
    --gold: #c9a84c;
    --gold-light: #e8d5a3;
    --rust: #8b3a2a;
    --sage: #4a6741;
    --cream: #faf7f2;
    --muted: #6b5c4e;
    --border: rgba(201,168,76,0.3);
  }
 
  * { margin: 0; padding: 0; box-sizing: border-box; }
 
  html { scroll-behavior: smooth; }
 
  body {
    background: var(--cream);
    color: var(--ink);
    font-family: 'Cormorant Garamond', serif;
    overflow-x: hidden;
  }
 
  /* Grain overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.4;
  }
 
  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.2rem 4rem;
    background: rgba(250,247,242,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
  }
 
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    color: var(--ink);
    text-decoration: none;
  }
 
  .nav-logo span { color: var(--gold); }
 
  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }
 
  .nav-links a {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.3s;
  }
 
  .nav-links a:hover { color: var(--gold); }
 
  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }
 
  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 8rem 4rem 4rem 6rem;
    position: relative;
  }
 
  .hero-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.2s forwards;
  }
 
  .hero-name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 5vw, 5.5rem);
    font-weight: 900;
    line-height: 1.0;
    color: var(--ink);
    opacity: 0;
    animation: fadeUp 0.8s 0.4s forwards;
  }
 
  .hero-name em {
    font-style: italic;
    color: var(--gold);
    display: block;
  }
 
  .hero-divider {
    width: 60px;
    height: 2px;
    background: linear-gradient(90deg, var(--gold), transparent);
    margin: 2rem 0;
    opacity: 0;
    animation: fadeUp 0.8s 0.6s forwards;
  }
 
  .hero-tagline {
    font-size: 1.35rem;
    font-weight: 300;
    font-style: italic;
    color: var(--muted);
    line-height: 1.6;
    max-width: 400px;
    opacity: 0;
    animation: fadeUp 0.8s 0.8s forwards;
  }
 
  .hero-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
    margin-top: 2.5rem;
    opacity: 0;
    animation: fadeUp 0.8s 1s forwards;
  }
 
  .pill {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    padding: 0.4rem 1rem;
    border: 1px solid var(--border);
    border-radius: 100px;
    color: var(--muted);
    background: rgba(201,168,76,0.06);
    text-transform: uppercase;
    transition: all 0.3s;
  }
 
  .pill:hover {
    background: var(--gold);
    color: var(--cream);
    border-color: var(--gold);
  }
 
  .hero-cta {
    display: flex;
    gap: 1rem;
    margin-top: 3rem;
    opacity: 0;
    animation: fadeUp 0.8s 1.2s forwards;
  }
 
  .btn-primary {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    padding: 0.85rem 2rem;
    background: var(--ink);
    color: var(--cream);
    border: none;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.3s;
  }
 
  .btn-primary:hover { background: var(--gold); }
 
  .btn-outline {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    padding: 0.85rem 2rem;
    background: transparent;
    color: var(--ink);
    border: 1px solid var(--ink);
    cursor: pointer;
    text-decoration: none;
    transition: all 0.3s;
  }
 
  .btn-outline:hover { border-color: var(--gold); color: var(--gold); }
 
  .hero-right {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }
 
  .hero-right::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--gold-light) 0%, var(--parchment) 50%, #d4c5a0 100%);
    opacity: 0.4;
  }
 
  .hero-monogram {
    position: relative;
    z-index: 2;
    font-family: 'Playfair Display', serif;
    font-size: 22vw;
    font-weight: 900;
    font-style: italic;
    color: rgba(201,168,76,0.12);
    line-height: 1;
    user-select: none;
    opacity: 0;
    animation: fadeIn 1.2s 0.5s forwards;
  }
 
  .hero-quote {
    position: absolute;
    bottom: 3rem;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
    z-index: 3;
    opacity: 0;
    animation: fadeUp 0.8s 1.4s forwards;
  }
 
  .hero-quote p {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.05rem;
    font-style: italic;
    color: var(--muted);
    white-space: nowrap;
  }
 
  .hero-quote span {
    display: block;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    color: var(--gold);
    text-transform: uppercase;
    margin-top: 0.4rem;
  }
 
  /* ── SCROLL INDICATOR ── */
  .scroll-indicator {
    position: absolute;
    bottom: 2rem;
    left: 6rem;
    display: flex;
    align-items: center;
    gap: 1rem;
    opacity: 0;
    animation: fadeIn 1s 2s forwards;
  }
 
  .scroll-line {
    width: 40px;
    height: 1px;
    background: var(--gold);
    position: relative;
    overflow: hidden;
  }
 
  .scroll-line::after {
    content: '';
    position: absolute;
    top: 0; left: -100%;
    width: 100%; height: 100%;
    background: var(--ink);
    animation: scanLine 2s infinite;
  }
 
  .scroll-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
  }
 
  /* ── SECTION BASE ── */
  section {
    padding: 7rem 6rem;
    position: relative;
  }
 
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }
 
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 3.2rem);
    font-weight: 700;
    line-height: 1.1;
    color: var(--ink);
    margin-bottom: 1.5rem;
  }
 
  .section-title em { font-style: italic; color: var(--gold); }
 
  /* ── ABOUT ── */
  .about {
    background: var(--ink);
    color: var(--cream);
    display: grid;
    grid-template-columns: 1fr 1.5fr;
    gap: 6rem;
    align-items: center;
  }
 
  .about .section-label { color: var(--gold); }
  .about .section-title { color: var(--cream); }
  .about .section-title em { color: var(--gold); }
 
  .about-text {
    font-size: 1.15rem;
    line-height: 1.9;
    color: rgba(250,247,242,0.75);
    font-weight: 300;
  }
 
  .about-text p + p { margin-top: 1.2rem; }
 
  .about-text strong {
    color: var(--gold-light);
    font-weight: 600;
  }
 
  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
 
  .stat-card {
    border: 1px solid rgba(201,168,76,0.2);
    padding: 2rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }
 
  .stat-card:hover { border-color: var(--gold); }
 
  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 0;
    background: var(--gold);
    transition: height 0.4s;
  }
 
  .stat-card:hover::before { height: 100%; }
 
  .stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 2.8rem;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
  }
 
  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(250,247,242,0.5);
    margin-top: 0.5rem;
  }
 
  /* ── DUAL IDENTITY ── */
  .dual {
    background: var(--parchment);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    padding: 0;
  }
 
  .dual-card {
    padding: 6rem;
    position: relative;
    overflow: hidden;
    transition: all 0.4s;
  }
 
  .dual-card:first-child {
    background: #1a2a1a;
    color: var(--cream);
  }
 
  .dual-card:last-child {
    background: #2a1a0e;
    color: var(--cream);
  }
 
  .dual-card:hover { transform: scale(1.02); z-index: 2; }
 
  .dual-icon {
    font-size: 3.5rem;
    margin-bottom: 2rem;
    display: block;
  }
 
  .dual-title {
    font-family: 'Playfair Display', serif;
    font-size: 2rem;
    font-weight: 700;
    font-style: italic;
    color: var(--gold);
    margin-bottom: 1rem;
  }
 
  .dual-sub {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: rgba(250,247,242,0.5);
    margin-bottom: 1.5rem;
  }
 
  .dual-desc {
    font-size: 1.05rem;
    line-height: 1.8;
    color: rgba(250,247,242,0.7);
    font-weight: 300;
  }
 
  .dual-skills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 2rem;
  }
 
  .dual-skill {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem;
    letter-spacing: 0.1em;
    padding: 0.35rem 0.8rem;
    border: 1px solid rgba(201,168,76,0.3);
    color: var(--gold-light);
    text-transform: uppercase;
  }
 
  /* ── EDUCATION ── */
  .education { background: var(--cream); }
 
  .edu-timeline {
    position: relative;
    margin-top: 4rem;
    padding-left: 3rem;
  }
 
  .edu-timeline::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(180deg, var(--gold), transparent);
  }
 
  .edu-item {
    position: relative;
    padding: 0 0 4rem 3rem;
    opacity: 0;
    transform: translateX(-20px);
    transition: all 0.6s;
  }
 
  .edu-item.visible {
    opacity: 1;
    transform: translateX(0);
  }
 
  .edu-item::before {
    content: '';
    position: absolute;
    left: -4px; top: 8px;
    width: 9px; height: 9px;
    background: var(--gold);
    border-radius: 50%;
    box-shadow: 0 0 0 3px var(--cream), 0 0 0 4px var(--gold);
  }
 
  .edu-year {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }
 
  .edu-degree {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--ink);
    margin-bottom: 0.3rem;
  }
 
  .edu-school {
    font-size: 1.05rem;
    font-style: italic;
    color: var(--muted);
  }
 
  /* ── PHILOSOPHY ── */
  .philosophy {
    background: var(--gold);
    text-align: center;
    padding: 8rem 6rem;
  }
 
  .philosophy-quote {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 3vw, 3rem);
    font-weight: 400;
    font-style: italic;
    color: var(--ink);
    line-height: 1.4;
    max-width: 900px;
    margin: 0 auto 2rem;
  }
 
  .philosophy-attr {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: rgba(26,20,16,0.6);
  }
 
  /* ── CONTACT ── */
  .contact {
    background: var(--ink);
    color: var(--cream);
    text-align: center;
    padding: 8rem 6rem;
  }
 
  .contact .section-label { color: var(--gold); }
  .contact .section-title { color: var(--cream); }
  .contact .section-title em { color: var(--gold); }
 
  .contact-sub {
    font-size: 1.15rem;
    color: rgba(250,247,242,0.6);
    font-style: italic;
    margin-bottom: 3rem;
    font-weight: 300;
  }
 
  .contact-links {
    display: flex;
    justify-content: center;
    gap: 2rem;
    flex-wrap: wrap;
  }
 
  .contact-link {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    color: rgba(250,247,242,0.7);
    text-decoration: none;
    border: 1px solid rgba(201,168,76,0.2);
    padding: 1rem 1.8rem;
    transition: all 0.3s;
  }
 
  .contact-link:hover {
    color: var(--gold);
    border-color: var(--gold);
    background: rgba(201,168,76,0.05);
  }
 
  /* ── FOOTER ── */
  footer {
    background: #0e0c0a;
    padding: 2rem 6rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(201,168,76,0.1);
  }
 
  .footer-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem;
    letter-spacing: 0.15em;
    color: rgba(250,247,242,0.3);
    text-transform: uppercase;
  }
 
  .footer-brand {
    font-family: 'Playfair Display', serif;
    font-size: 1rem;
    font-style: italic;
    color: var(--gold);
  }
 
  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
 
  @keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }
 
  @keyframes scanLine {
    0%   { left: -100%; }
    100% { left: 200%; }
  }
 
  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-left { padding: 7rem 2rem 3rem; }
    .hero-right { height: 220px; }
    .about { grid-template-columns: 1fr; gap: 3rem; padding: 4rem 2rem; }
    .dual { grid-template-columns: 1fr; }
    .dual-card { padding: 3rem 2rem; }
    section { padding: 4rem 2rem; }
    .contact-links { flex-direction: column; align-items: center; }
    footer { flex-direction: column; gap: 1rem; text-align: center; }
    .scroll-indicator { display: none; }
  }
</style>
</head>
<body>
 
<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">N<span>.</span>Dubey</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#identity">Identity</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
 
<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <p class="hero-tag">✦ Ranchi, Jharkhand · India</p>
    <h1 class="hero-name">
      Nikhil<br>
      <em>Dubey</em>
    </h1>
    <div class="hero-divider"></div>
    <p class="hero-tagline">
      The most interesting ideas live at the intersection of disciplines.
    </p>
    <div class="hero-pills">
      <span class="pill">MCA Candidate</span>
      <span class="pill">UPSC Aspirant</span>
      <span class="pill">Python · ML</span>
      <span class="pill">Sociology</span>
      <span class="pill">Avid Reader</span>
    </div>
    <div class="hero-cta">
      <a href="#about" class="btn-primary">Explore</a>
      <a href="mailto:nikhildubey056@gmail.com" class="btn-outline">Get in Touch</a>
    </div>
    <div class="scroll-indicator">
      <div class="scroll-line"></div>
      <span class="scroll-text">Scroll</span>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-monogram">N</div>
    <div class="hero-quote">
      <p>"Menace to Monk"</p>
      <span>A transformation story</span>
    </div>
  </div>
</section>
 
<!-- ABOUT -->
<section class="about" id="about">
  <div>
    <p class="section-label">✦ Who I Am</p>
    <h2 class="section-title">A mind that<br>refuses to<br><em>stay in one lane</em></h2>
  </div>
  <div>
    <div class="about-text">
      <p>I am a <strong>computer science enthusiast</strong> with a solid foundation in programming, data structures, networking, and operating systems — currently pursuing my MCA at Marwari College, Ranchi.</p>
      <p>Beyond the terminal, I have cultivated a working knowledge of <strong>UPSC-oriented subjects</strong> — particularly Sociology and General Studies — which has sharpened my ability to think critically about society, governance, and human systems.</p>
      <p>Reading <strong>literary fiction</strong> strengthens my analytical reasoning and articulation. I believe technology always operates within a human context, and the best solutions are built by people who can think both systemically and empathetically.</p>
      <p>That's the kind of thinker I am working to become.</p>
    </div>
    <div class="about-stats" style="margin-top:3rem;">
      <div class="stat-card">
        <div class="stat-number">MCA</div>
        <div class="stat-label">Computer Science<br>Marwari College</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">IAS</div>
        <div class="stat-label">Aspiring Civil<br>Servant · UPSC</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">ML</div>
        <div class="stat-label">Machine Learning<br>& Python Dev</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">📚</div>
        <div class="stat-label">Avid Reader<br>Literary Fiction</div>
      </div>
    </div>
  </div>
</section>
 
<!-- DUAL IDENTITY -->
<div class="dual" id="identity">
  <div class="dual-card">
    <span class="dual-icon">💻</span>
    <div class="dual-sub">Technical Identity</div>
    <div class="dual-title">The Engineer</div>
    <p class="dual-desc">
      Grounded in the core pillars of computer science — from programming paradigms to algorithms, networking protocols to operating systems. Currently building expertise in Machine Learning and AI.
    </p>
    <div class="dual-skills">
      <span class="dual-skill">Python</span>
      <span class="dual-skill">C</span>
      <span class="dual-skill">Machine Learning</span>
      <span class="dual-skill">Algorithms</span>
      <span class="dual-skill">DSA</span>
      <span class="dual-skill">Networking</span>
      <span class="dual-skill">OS</span>
    </div>
  </div>
  <div class="dual-card">
    <span class="dual-icon">🏛️</span>
    <div class="dual-sub">Civil Service Identity</div>
    <div class="dual-title">The Aspirant</div>
    <p class="dual-desc">
      Deeply invested in UPSC preparation — studying Sociology and General Studies to analyze social structures, governance frameworks, and human systems with rigor and nuance. Ranchi → LBSNAA.
    </p>
    <div class="dual-skills">
      <span class="dual-skill">Sociology</span>
      <span class="dual-skill">General Studies</span>
      <span class="dual-skill">Polity</span>
      <span class="dual-skill">History</span>
      <span class="dual-skill">Governance</span>
      <span class="dual-skill">Public Policy</span>
    </div>
  </div>
</div>
 
<!-- EDUCATION -->
<section class="education" id="education">
  <p class="section-label">✦ Academic Journey</p>
  <h2 class="section-title">Education &<br><em>Formation</em></h2>
  <div class="edu-timeline">
    <div class="edu-item">
      <div class="edu-year">May 2024 — June 2026</div>
      <div class="edu-degree">Master of Computer Applications</div>
      <div class="edu-school">Marwari College, Ranchi · Computer Science</div>
    </div>
    <div class="edu-item">
      <div class="edu-year">May 2021 — May 2024</div>
      <div class="edu-degree">Bachelor of Applied Science</div>
      <div class="edu-school">Gossner College, Ranchi · Information Technology</div>
    </div>
    <div class="edu-item">
      <div class="edu-year">July 2019 — July 2021</div>
      <div class="edu-degree">Intermediate · Class XII</div>
      <div class="edu-school">St. Xavier's College, Ranchi · Science</div>
    </div>
  </div>
</section>
 
<!-- PHILOSOPHY -->
<section class="philosophy">
  <p class="philosophy-quote">
    "The best solutions are built by people who can think systemically and empathetically — who can write clean code and communicate it clearly, who can solve a problem and ask whether it's the right problem to solve."
  </p>
  <p class="philosophy-attr">— Nikhil Dubey · Personal Philosophy</p>
</section>
 
<!-- CONTACT -->
<section class="contact" id="contact">
  <p class="section-label">✦ Let's Connect</p>
  <h2 class="section-title">Reach Out &<br><em>Say Hello</em></h2>
  <p class="contact-sub">Always open to conversations about technology, civil services, books, or ideas.</p>
  <div class="contact-links">
    <a href="mailto:nikhildubey056@gmail.com" class="contact-link">
      <span>✉</span> nikhildubey056@gmail.com
    </a>
    <a href="https://www.linkedin.com/in/nikhildubey01" target="_blank" class="contact-link">
      <span>in</span> linkedin.com/in/nikhildubey01
    </a>
    <a href="#" class="contact-link">
      <span>📍</span> Ranchi, Jharkhand, India
    </a>
  </div>
</section>
 
<!-- FOOTER -->
<footer>
  <span class="footer-text">© 2026 Nikhil Dubey · All rights reserved</span>
  <span class="footer-brand">Menace to Monk</span>
  <span class="footer-text">Built with purpose</span>
</footer>
 
<script>
  // Scroll reveal for education items
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 150);
      }
    });
  }, { threshold: 0.2 });
 
  document.querySelectorAll('.edu-item').forEach(el => observer.observe(el));
 
  // Smooth active nav
  const sections = document.querySelectorAll('section[id], div[id]');
  const navLinks = document.querySelectorAll('.nav-links a');
 
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(sec => {
      if (window.scrollY >= sec.offsetTop - 200) current = sec.id;
    });
    navLinks.forEach(link => {
      link.style.color = link.getAttribute('href') === `#${current}` ? 'var(--gold)' : '';
    });
  });
</script>
</body>
</html>
 
