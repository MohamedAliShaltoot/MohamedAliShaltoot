<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mohamed Ali Shaltoot — Flutter Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Sora:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e1a;
    --surface: #111827;
    --surface2: #1a2235;
    --accent: #38bdf8;
    --accent2: #818cf8;
    --accent3: #34d399;
    --text: #e2e8f0;
    --muted: #64748b;
    --border: rgba(56,189,248,0.15);
    --glow: 0 0 30px rgba(56,189,248,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Sora', sans-serif;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(56,189,248,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(56,189,248,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 80px 0 60px;
    position: relative;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 500px;
    height: 500px;
    background: radial-gradient(circle, rgba(56,189,248,0.07) 0%, transparent 70%);
    pointer-events: none;
  }

  .status-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(52,211,153,0.1);
    border: 1px solid rgba(52,211,153,0.3);
    color: var(--accent3);
    padding: 6px 16px;
    border-radius: 100px;
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    letter-spacing: 0.05em;
    margin-bottom: 28px;
    animation: fadeDown 0.6s ease both;
  }

  .status-dot {
    width: 7px;
    height: 7px;
    background: var(--accent3);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  h1 {
    font-size: clamp(2.2rem, 5vw, 3.5rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    line-height: 1.1;
    margin-bottom: 12px;
    animation: fadeDown 0.7s 0.1s ease both;
  }

  h1 span {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .subtitle {
    color: var(--muted);
    font-size: 1rem;
    font-family: 'Space Mono', monospace;
    margin-bottom: 32px;
    animation: fadeDown 0.7s 0.2s ease both;
  }

  .hero-links {
    display: flex;
    gap: 12px;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeDown 0.7s 0.3s ease both;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 22px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.2s ease;
    border: 1px solid transparent;
    cursor: pointer;
  }

  .btn-primary {
    background: var(--accent);
    color: var(--bg);
  }

  .btn-primary:hover { background: #7dd3fc; transform: translateY(-2px); box-shadow: 0 8px 24px rgba(56,189,248,0.3); }

  .btn-ghost {
    background: transparent;
    color: var(--text);
    border-color: var(--border);
  }

  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  /* ── SECTION ── */
  section {
    margin-bottom: 64px;
    animation: fadeUp 0.7s ease both;
  }

  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 28px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-label span {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
  }

  .section-num {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  h2 {
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--text);
  }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .info-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    transition: border-color 0.2s, box-shadow 0.2s;
  }

  .info-card:hover { border-color: rgba(56,189,248,0.4); box-shadow: var(--glow); }

  .info-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 6px;
  }

  .info-val {
    font-size: 15px;
    font-weight: 600;
    color: var(--text);
  }

  /* ── SKILLS ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 16px;
  }

  .skill-group {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 22px;
    transition: all 0.2s;
  }

  .skill-group:hover { border-color: rgba(129,140,248,0.4); transform: translateY(-3px); box-shadow: 0 12px 32px rgba(0,0,0,0.3); }

  .skill-group-title {
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--accent2);
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text);
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    padding: 4px 12px;
    border-radius: 6px;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 26px;
    position: relative;
    overflow: hidden;
    transition: all 0.25s;
    text-decoration: none;
    display: block;
    color: inherit;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s ease;
  }

  .project-card:hover { border-color: rgba(56,189,248,0.3); transform: translateY(-4px); box-shadow: 0 16px 40px rgba(0,0,0,0.4); }
  .project-card:hover::before { transform: scaleX(1); }

  .project-icon {
    font-size: 28px;
    margin-bottom: 14px;
  }

  .project-title {
    font-size: 16px;
    font-weight: 700;
    margin-bottom: 10px;
    color: var(--text);
  }

  .project-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 16px;
  }

  .project-tech {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tech-badge {
    font-size: 10px;
    font-family: 'Space Mono', monospace;
    background: rgba(56,189,248,0.08);
    border: 1px solid rgba(56,189,248,0.2);
    color: var(--accent);
    padding: 3px 10px;
    border-radius: 4px;
  }

  /* ── CERTS ── */
  .cert-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .cert-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 22px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
    transition: all 0.2s;
    text-decoration: none;
    color: inherit;
  }

  .cert-item:hover { border-color: rgba(56,189,248,0.4); box-shadow: var(--glow); }

  .cert-info { flex: 1; }

  .cert-name {
    font-size: 14px;
    font-weight: 600;
    margin-bottom: 3px;
  }

  .cert-issuer {
    font-size: 12px;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
  }

  .cert-status {
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    padding: 4px 12px;
    border-radius: 100px;
    white-space: nowrap;
    flex-shrink: 0;
  }

  .cert-status.done {
    background: rgba(52,211,153,0.1);
    border: 1px solid rgba(52,211,153,0.3);
    color: var(--accent3);
  }

  .cert-status.progress {
    background: rgba(251,191,36,0.1);
    border: 1px solid rgba(251,191,36,0.3);
    color: #fbbf24;
  }

  /* ── CONTACT ── */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
  }

  .contact-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 22px;
    text-align: center;
    text-decoration: none;
    color: inherit;
    transition: all 0.25s;
  }

  .contact-card:hover { border-color: var(--accent); transform: translateY(-4px); box-shadow: var(--glow); }

  .contact-icon { font-size: 26px; margin-bottom: 10px; }

  .contact-label {
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--muted);
    margin-bottom: 4px;
  }

  .contact-val {
    font-size: 13px;
    font-weight: 600;
    color: var(--accent);
  }

  /* ── FOOTER ── */
  footer {
    text-align: center;
    padding: 40px 0;
    border-top: 1px solid var(--border);
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    font-size: 12px;
  }

  footer em {
    color: var(--accent);
    font-style: normal;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  section:nth-child(1) { animation-delay: 0.1s; }
  section:nth-child(2) { animation-delay: 0.2s; }
  section:nth-child(3) { animation-delay: 0.3s; }
  section:nth-child(4) { animation-delay: 0.4s; }
  section:nth-child(5) { animation-delay: 0.5s; }
  section:nth-child(6) { animation-delay: 0.6s; }

  @media (max-width: 640px) {
    .about-grid, .projects-grid, .contact-grid { grid-template-columns: 1fr; }
    .skills-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="status-badge">
      <div class="status-dot"></div>
      Open to opportunities
    </div>
    <h1>Mohamed Ali<br><span>Shaltoot</span></h1>
    <p class="subtitle">Flutter Developer · Mobile Engineer · Egypt 🇪🇬</p>
    <div class="hero-links">
      <a href="https://www.linkedin.com/in/muhamed-ali-shaltoot/" class="btn btn-primary">💼 LinkedIn</a>
      <a href="https://github.com/MohamedAliShaltoot" class="btn btn-ghost">🐙 GitHub</a>
      <a href="mailto:mohamedali3092002@gmail.com" class="btn btn-ghost">✉️ Email</a>
    </div>
  </div>

  <!-- ABOUT -->
  <section>
    <div class="section-label">
      <span class="section-num">01</span>
      <span>About</span>
    </div>
    <div class="about-grid">
      <div class="info-card" style="grid-column: 1 / -1;">
        <p style="color: #94a3b8; font-size: 15px; line-height: 1.8;">
          Computer Systems Engineering graduate with a deep focus on <strong style="color: var(--accent);">cross-platform mobile development</strong>. I build scalable, user-centric applications using Flutter & Dart, with a commitment to clean architecture, solid design patterns, and seamless API integrations. Currently training in ITI's 9-month Mobile Native Track.
        </p>
      </div>
      <div class="info-card">
        <div class="info-label">Education</div>
        <div class="info-val">Computer & Systems Engineering</div>
        <div style="font-size: 12px; color: var(--muted); margin-top: 4px;">Zagazig University · Graduated Jun 2025</div>
      </div>
      <div class="info-card">
        <div class="info-label">Current Training</div>
        <div class="info-val">9-Month Mobile Native Track</div>
        <div style="font-size: 12px; color: var(--muted); margin-top: 4px;">ITI — Information Technology Institute</div>
      </div>
      <div class="info-card">
        <div class="info-label">Focus Areas</div>
        <div class="info-val">Flutter · Android · REST APIs</div>
        <div style="font-size: 12px; color: var(--muted); margin-top: 4px;">Clean Architecture · State Management</div>
      </div>
      <div class="info-card">
        <div class="info-label">Looking For</div>
        <div class="info-val">Internships & Mobile Projects</div>
        <div style="font-size: 12px; color: var(--muted); margin-top: 4px;">Open to Remote & On-site roles</div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section>
    <div class="section-label">
      <span class="section-num">02</span>
      <span>Technical Skills</span>
    </div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-title">📱 Mobile Development</div>
        <div class="tags">
          <span class="tag">Flutter</span>
          <span class="tag">Dart</span>
          <span class="tag">Kotlin</span>
          <span class="tag">Android SDK</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">⚙️ Architecture & Patterns</div>
        <div class="tags">
          <span class="tag">Clean Architecture</span>
          <span class="tag">SOLID</span>
          <span class="tag">BLoC</span>
          <span class="tag">REST APIs</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">🗄️ Data & Backend</div>
        <div class="tags">
          <span class="tag">Firebase</span>
          <span class="tag">SQLite</span>
          <span class="tag">Hive</span>
          <span class="tag">HTTP / Dio</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">🛠️ Tools & Languages</div>
        <div class="tags">
          <span class="tag">Git</span>
          <span class="tag">Android Studio</span>
          <span class="tag">Postman</span>
          <span class="tag">VS Code</span>
          <span class="tag">C</span>
          <span class="tag">JavaScript</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section>
    <div class="section-label">
      <span class="section-num">03</span>
      <span>Featured Projects</span>
    </div>
    <div class="projects-grid">
      <a class="project-card" href="https://github.com/MohamedAliShaltoot/NTI_E-commerce-Stylish-App-" target="_blank">
        <div class="project-icon">🛒</div>
        <div class="project-title">Cross-Border E-commerce Platform</div>
        <div class="project-desc">Full-featured shopping app with secure authentication, payment integration, real-time inventory management, and responsive UI across all screen sizes.</div>
        <div class="project-tech">
          <span class="tech-badge">Flutter</span>
          <span class="tech-badge">Firebase</span>
          <span class="tech-badge">REST APIs</span>
        </div>
      </a>
      <a class="project-card" href="https://github.com/MohamedAliShaltoot/TODO_App_with_APIs_Integration-" target="_blank">
        <div class="project-icon">✅</div>
        <div class="project-title">Advanced Task Management System</div>
        <div class="project-desc">Full CRUD task manager with API sync, secure authentication, profile management, and advanced account security protocols.</div>
        <div class="project-tech">
          <span class="tech-badge">Flutter</span>
          <span class="tech-badge">REST APIs</span>
          <span class="tech-badge">Auth</span>
        </div>
      </a>
      <a class="project-card" href="https://github.com/MohamedAliShaltoot/TODo_App" target="_blank">
        <div class="project-icon">📝</div>
        <div class="project-title">Local Storage Notes App</div>
        <div class="project-desc">Offline-first notes app with fast SQLite storage, clean architecture following SOLID principles, achieving 99.9% persistence reliability.</div>
        <div class="project-tech">
          <span class="tech-badge">Flutter</span>
          <span class="tech-badge">SQLite</span>
        </div>
      </a>
      <a class="project-card" href="https://github.com/MohamedAliShaltoot/Tasbih-application" target="_blank">
        <div class="project-icon">🔢</div>
        <div class="project-title">Digital Tasbih Counter</div>
        <div class="project-desc">Accessibility-focused spiritual counter app with intuitive gesture controls and a clean, distraction-free user interface.</div>
        <div class="project-tech">
          <span class="tech-badge">Flutter</span>
          <span class="tech-badge">State Mgmt</span>
        </div>
      </a>
    </div>
  </section>

  <!-- CERTIFICATIONS -->
  <section>
    <div class="section-label">
      <span class="section-num">04</span>
      <span>Certifications</span>
    </div>
    <div class="cert-list">
      <div class="cert-item">
        <div class="cert-info">
          <div class="cert-name">Mobile Native Track (9 Months)</div>
          <div class="cert-issuer">ITI — Information Technology Institute</div>
        </div>
        <span class="cert-status progress">⏳ In Progress</span>
      </div>
      <a class="cert-item" href="https://drive.google.com/file/d/1fkOUlEqTuihnKLNZ8qIgoY7Oxn_63YPU/view?usp=sharing" target="_blank">
        <div class="cert-info">
          <div class="cert-name">Mobile App Development using Flutter</div>
          <div class="cert-issuer">NTI — National Telecommunication Institute</div>
        </div>
        <span class="cert-status done">✓ Certified</span>
      </a>
      <a class="cert-item" href="https://drive.google.com/file/d/1p0wVJuX75ltH2v7ZdXeMs_3f4ctjE8-Y/view?usp=sharing" target="_blank">
        <div class="cert-info">
          <div class="cert-name">Mobile App Development (Android & Flutter)</div>
          <div class="cert-issuer">DEPI — Mansoura Branch</div>
        </div>
        <span class="cert-status done">✓ Certified</span>
      </a>
      <a class="cert-item" href="https://drive.google.com/file/d/1Oe9bqEoWR-c2F7zXfSHhv4bl68-z-AhD/view?usp=sharing" target="_blank">
        <div class="cert-info">
          <div class="cert-name">Cross Platform App Development using Flutter</div>
          <div class="cert-issuer">Frontend Masters (Online)</div>
        </div>
        <span class="cert-status done">✓ Certified</span>
      </a>
    </div>
  </section>

  <!-- CONTACT -->
  <section>
    <div class="section-label">
      <span class="section-num">05</span>
      <span>Connect</span>
    </div>
    <div class="contact-grid">
      <a class="contact-card" href="https://www.linkedin.com/in/muhamed-ali-shaltoot/" target="_blank">
        <div class="contact-icon">💼</div>
        <div class="contact-label">LinkedIn</div>
        <div class="contact-val">muhamed-ali-shaltoot</div>
      </a>
      <a class="contact-card" href="https://github.com/MohamedAliShaltoot" target="_blank">
        <div class="contact-icon">🐙</div>
        <div class="contact-label">GitHub</div>
        <div class="contact-val">MohamedAliShaltoot</div>
      </a>
      <a class="contact-card" href="mailto:mohamedali3092002@gmail.com">
        <div class="contact-icon">✉️</div>
        <div class="contact-label">Email</div>
        <div class="contact-val">mohamedali3092002</div>
      </a>
    </div>
  </section>

</div>

<footer>
  <div class="container">
    <em>"Building tomorrow's solutions with today's code"</em>
    <br><br>
    Mohamed Ali Shaltoot · Flutter Developer · Egypt
  </div>
</footer>

</body>
</html>
