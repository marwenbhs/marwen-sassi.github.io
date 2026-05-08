<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Marwen Haj Sassi — Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #07090f;
      --surface: #0d1117;
      --surface2: #131920;
      --accent: #00c8ff;
      --accent2: #0057ff;
      --text: #e8edf5;
      --muted: #5a6a80;
      --border: #1a2535;
      --green: #00e5a0;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Mono', monospace;
      font-size: 14px;
      line-height: 1.7;
      overflow-x: hidden;
    }

    /* ── GRID NOISE OVERLAY ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        radial-gradient(ellipse 80% 60% at 10% 0%, rgba(0,88,255,0.07) 0%, transparent 60%),
        radial-gradient(ellipse 60% 50% at 90% 100%, rgba(0,200,255,0.05) 0%, transparent 60%);
      pointer-events: none;
      z-index: 0;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 18px 5vw;
      background: rgba(7,9,15,0.85);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: 16px;
      letter-spacing: 0.04em;
      color: var(--accent);
    }

    .nav-links {
      display: flex;
      gap: 28px;
      list-style: none;
    }

    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 12px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--accent); }

    /* ── HERO ── */
    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 120px 5vw 80px;
      overflow: hidden;
    }

    .hero-grid {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,200,255,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,200,255,0.04) 1px, transparent 1px);
      background-size: 60px 60px;
      mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 30%, transparent 100%);
    }

    .hero-content { position: relative; z-index: 1; max-width: 900px; }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 11px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 24px;
    }

    .hero-tag::before {
      content: '';
      width: 24px; height: 1px;
      background: var(--accent);
    }

    .hero h1 {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: clamp(42px, 8vw, 90px);
      line-height: 1.0;
      letter-spacing: -0.02em;
      margin-bottom: 24px;
    }

    .hero h1 span {
      display: block;
      background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero-desc {
      color: var(--muted);
      max-width: 560px;
      font-size: 15px;
      line-height: 1.8;
      margin-bottom: 40px;
    }

    .hero-cta {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 14px 28px;
      background: var(--accent);
      color: #000;
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: 13px;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      text-decoration: none;
      transition: all 0.2s;
      clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 10px, 100% 100%, 10px 100%, 0 calc(100% - 10px));
    }

    .btn-primary:hover {
      background: #fff;
      transform: translateY(-2px);
    }

    .btn-outline {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 14px 28px;
      border: 1px solid var(--border);
      color: var(--text);
      font-family: 'Syne', sans-serif;
      font-weight: 600;
      font-size: 13px;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      text-decoration: none;
      transition: all 0.2s;
    }

    .btn-outline:hover {
      border-color: var(--accent);
      color: var(--accent);
    }

    .hero-stats {
      display: flex;
      gap: 48px;
      margin-top: 64px;
      padding-top: 40px;
      border-top: 1px solid var(--border);
      flex-wrap: wrap;
    }

    .stat-item {}
    .stat-num {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: 36px;
      color: var(--accent);
      line-height: 1;
    }
    .stat-label {
      font-size: 11px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--muted);
      margin-top: 4px;
    }

    /* ── SECTIONS ── */
    section {
      position: relative;
      z-index: 1;
      padding: 100px 5vw;
    }

    .section-header {
      display: flex;
      align-items: center;
      gap: 16px;
      margin-bottom: 60px;
    }

    .section-num {
      font-size: 11px;
      letter-spacing: 0.15em;
      color: var(--accent);
    }

    .section-title {
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: clamp(24px, 4vw, 36px);
      letter-spacing: -0.01em;
    }

    .section-line {
      flex: 1;
      height: 1px;
      background: var(--border);
      max-width: 200px;
    }

    /* ── EXPERIENCE ── */
    .exp-list { display: flex; flex-direction: column; gap: 2px; }

    .exp-item {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 32px 36px;
      position: relative;
      overflow: hidden;
      transition: border-color 0.3s, transform 0.3s;
      cursor: default;
    }

    .exp-item::before {
      content: '';
      position: absolute;
      left: 0; top: 0; bottom: 0;
      width: 3px;
      background: var(--accent);
      transform: scaleY(0);
      transition: transform 0.3s;
    }

    .exp-item:hover {
      border-color: rgba(0,200,255,0.3);
      transform: translateX(4px);
    }

    .exp-item:hover::before { transform: scaleY(1); }

    .exp-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 16px;
    }

    .exp-company {
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: 18px;
      color: var(--text);
    }

    .exp-role {
      color: var(--accent);
      font-size: 12px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-top: 4px;
    }

    .exp-date {
      font-size: 11px;
      color: var(--muted);
      letter-spacing: 0.08em;
      white-space: nowrap;
      margin-top: 4px;
    }

    .exp-desc {
      color: var(--muted);
      font-size: 13px;
      line-height: 1.8;
    }

    .exp-desc li {
      list-style: none;
      padding-left: 16px;
      position: relative;
      margin-bottom: 4px;
    }

    .exp-desc li::before {
      content: '→';
      position: absolute;
      left: 0;
      color: var(--accent);
      font-size: 11px;
    }

    /* ── SKILLS ── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 2px;
    }

    .skill-card {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 28px;
      transition: border-color 0.3s;
    }

    .skill-card:hover { border-color: rgba(0,200,255,0.25); }

    .skill-icon {
      width: 36px; height: 36px;
      background: rgba(0,200,255,0.1);
      border: 1px solid rgba(0,200,255,0.2);
      display: flex; align-items: center; justify-content: center;
      margin-bottom: 16px;
      font-size: 16px;
    }

    .skill-category {
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: 14px;
      margin-bottom: 12px;
      color: var(--text);
    }

    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }

    .tag {
      font-size: 10px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 4px 10px;
      background: rgba(0,200,255,0.06);
      border: 1px solid rgba(0,200,255,0.15);
      color: var(--accent);
    }

    /* ── EDUCATION ── */
    .edu-card {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 40px;
      display: flex;
      gap: 32px;
      align-items: flex-start;
      flex-wrap: wrap;
    }

    .edu-year {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: 42px;
      color: rgba(0,200,255,0.15);
      line-height: 1;
      min-width: 100px;
    }

    .edu-info {}
    .edu-degree {
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: 20px;
      margin-bottom: 4px;
    }

    .edu-school { color: var(--accent); font-size: 13px; }
    .edu-field { color: var(--muted); margin-top: 8px; font-size: 13px; }

    /* ── LANGUAGES ── */
    .lang-grid {
      display: flex;
      gap: 2px;
      flex-wrap: wrap;
    }

    .lang-item {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 24px 36px;
      flex: 1;
      min-width: 180px;
    }

    .lang-name {
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: 18px;
      margin-bottom: 6px;
    }

    .lang-level { color: var(--muted); font-size: 12px; letter-spacing: 0.08em; text-transform: uppercase; }

    /* ── INTERESTS ── */
    .interests-grid {
      display: flex;
      gap: 2px;
      flex-wrap: wrap;
    }

    .interest-item {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 20px 28px;
      display: flex;
      align-items: center;
      gap: 12px;
      flex: 1;
      min-width: 160px;
    }

    .interest-icon { font-size: 20px; }
    .interest-label { font-size: 13px; color: var(--muted); }

    /* ── CONTACT ── */
    .contact-block {
      background: var(--surface);
      border: 1px solid var(--border);
      padding: 60px;
      text-align: center;
    }

    .contact-title {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: clamp(28px, 5vw, 48px);
      margin-bottom: 12px;
    }

    .contact-sub {
      color: var(--muted);
      margin-bottom: 40px;
      font-size: 14px;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      gap: 16px;
      flex-wrap: wrap;
    }

    .contact-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 12px 24px;
      border: 1px solid var(--border);
      color: var(--text);
      text-decoration: none;
      font-size: 12px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      transition: all 0.2s;
    }

    .contact-link:hover {
      border-color: var(--accent);
      color: var(--accent);
    }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      padding: 28px 5vw;
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: var(--muted);
      font-size: 11px;
      letter-spacing: 0.08em;
      flex-wrap: wrap;
      gap: 12px;
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .hero-content > * {
      animation: fadeUp 0.6s ease both;
    }

    .hero-tag { animation-delay: 0.1s; }
    .hero h1  { animation-delay: 0.2s; }
    .hero-desc{ animation-delay: 0.3s; }
    .hero-cta { animation-delay: 0.4s; }
    .hero-stats{ animation-delay: 0.5s; }

    /* ── SCROLLBAR ── */
    ::-webkit-scrollbar { width: 4px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--border); }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">MHS</div>
  <ul class="nav-links">
    <li><a href="#experience">Expérience</a></li>
    <li><a href="#skills">Compétences</a></li>
    <li><a href="#education">Formation</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-tag">Disponible pour de nouvelles opportunités</div>
    <h1>
      Marwen<br>
      <span>Haj Sassi</span>
    </h1>
    <p class="hero-desc">
      Administrateur Système &amp; Réseau avec +6 ans d'expérience. 
      Spécialisé en virtualisation, infrastructure serveur, et solutions backup 
      dans des environnements Windows/Linux complexes.
    </p>
    <div class="hero-cta">
      <a href="#contact" class="btn-primary">Me contacter</a>
      <a href="#experience" class="btn-outline">Voir mon parcours</a>
    </div>
    <div class="hero-stats">
      <div class="stat-item">
        <div class="stat-num">6+</div>
        <div class="stat-label">Années d'expérience</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">3</div>
        <div class="stat-label">Entreprises</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">3</div>
        <div class="stat-label">Langues</div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-header">
    <span class="section-num">01</span>
    <h2 class="section-title">Expériences</h2>
    <div class="section-line"></div>
  </div>
  <div class="exp-list">

    <div class="exp-item">
      <div class="exp-header">
        <div>
          <div class="exp-company">NextStep</div>
          <div class="exp-role">System Consultant</div>
        </div>
        <div class="exp-date">Mai 2023 — Présent</div>
      </div>
      <ul class="exp-desc">
        <li>Déploiement d'environnements de virtualisation haute performance (VMware vSphere, Microsoft Hyper-V)</li>
        <li>Gestion de systèmes de stockage SAN et NAS</li>
        <li>Configuration de solutions backup et réplication (Veeam, Nakivo)</li>
        <li>Installation et configuration de serveurs (Active Directory, DNS, DHCP)</li>
        <li>Maintenance de serveurs Rack, Blade, Tower, Switches et Unités de stockage</li>
        <li>Support technique de haut niveau et création de documentations LLD</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-header">
        <div>
          <div class="exp-company">Netcom</div>
          <div class="exp-role">System &amp; Network Administrator</div>
        </div>
        <div class="exp-date">Mars 2023 — Mai 2023</div>
      </div>
      <ul class="exp-desc">
        <li>Intégration et configuration de routeurs et équipements réseau</li>
        <li>Maintenance préventive, corrective et évolutive des infrastructures réseau</li>
        <li>Identification et résolution des problèmes de sécurité réseau</li>
        <li>Supervision et configuration des Access Switches</li>
      </ul>
    </div>

    <div class="exp-item">
      <div class="exp-header">
        <div>
          <div class="exp-company">Pyramidan</div>
          <div class="exp-role">System &amp; Network Administrator</div>
        </div>
        <div class="exp-date">Août 2017 — Fév 2023</div>
      </div>
      <ul class="exp-desc">
        <li>Administration CRM (Vtiger) et GLPI</li>
        <li>Backup &amp; restauration de données (NAS, Veeam Backup &amp; Replication)</li>
        <li>Sécurité réseau et données (Kaspersky Security Center)</li>
        <li>Gestion Active Directory sous Windows Server</li>
        <li>Maintenance de l'infrastructure réseau : DC, DNS, DHCP, Print Server</li>
      </ul>
    </div>

  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-header">
    <span class="section-num">02</span>
    <h2 class="section-title">Compétences</h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid">

    <div class="skill-card">
      <div class="skill-icon">🌐</div>
      <div class="skill-category">Administration Réseau</div>
      <div class="skill-tags">
        <span class="tag">Câblage</span>
        <span class="tag">Supervision</span>
        <span class="tag">Configuration</span>
        <span class="tag">Maintenance</span>
        <span class="tag">Fibre optique</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">🖥</div>
      <div class="skill-category">Virtualisation</div>
      <div class="skill-tags">
        <span class="tag">Hyper-V</span>
        <span class="tag">VMware</span>
        <span class="tag">vSphere</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">📞</div>
      <div class="skill-category">VOIP</div>
      <div class="skill-tags">
        <span class="tag">Asterisk</span>
        <span class="tag">IAX</span>
        <span class="tag">SIP</span>
        <span class="tag">MonitoringVOIP</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">⚙️</div>
      <div class="skill-category">Administration Système</div>
      <div class="skill-tags">
        <span class="tag">Windows Server</span>
        <span class="tag">Active Directory</span>
        <span class="tag">DNS</span>
        <span class="tag">DHCP</span>
        <span class="tag">PAM Server</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">💾</div>
      <div class="skill-category">Backup &amp; Stockage</div>
      <div class="skill-tags">
        <span class="tag">Veeam</span>
        <span class="tag">Nakivo</span>
        <span class="tag">NAS</span>
        <span class="tag">SAN</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">📊</div>
      <div class="skill-category">Monitoring &amp; Outils</div>
      <div class="skill-tags">
        <span class="tag">Zabbix</span>
        <span class="tag">Kaspersky SC</span>
        <span class="tag">GLPI</span>
        <span class="tag">Vtiger CRM</span>
        <span class="tag">Excel</span>
      </div>
    </div>

  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-header">
    <span class="section-num">03</span>
    <h2 class="section-title">Formation</h2>
    <div class="section-line"></div>
  </div>
  <div class="edu-card">
    <div class="edu-year">2013</div>
    <div class="edu-info">
      <div class="edu-degree">Licence en Informatique</div>
      <div class="edu-school">Institut Supérieur d'Informatique, Tunisie</div>
      <div class="edu-field">Spécialisation : Administration des réseaux et services</div>
    </div>
  </div>
</section>

<!-- LANGUAGES & INTERESTS -->
<section>
  <div class="section-header">
    <span class="section-num">04</span>
    <h2 class="section-title">Langues &amp; Intérêts</h2>
    <div class="section-line"></div>
  </div>

  <div class="lang-grid" style="margin-bottom: 2px;">
    <div class="lang-item">
      <div class="lang-name">Arabe</div>
      <div class="lang-level">Langue maternelle</div>
    </div>
    <div class="lang-item">
      <div class="lang-name">Français</div>
      <div class="lang-level">Courant</div>
    </div>
    <div class="lang-item">
      <div class="lang-name">Anglais</div>
      <div class="lang-level">Professionnel</div>
    </div>
  </div>

  <div class="interests-grid">
    <div class="interest-item">
      <span class="interest-icon">⛺</span>
      <span class="interest-label">Scout</span>
    </div>
    <div class="interest-item">
      <span class="interest-icon">🏊</span>
      <span class="interest-label">Natation</span>
    </div>
    <div class="interest-item">
      <span class="interest-icon">🥾</span>
      <span class="interest-label">Randonnée</span>
    </div>
    <div class="interest-item">
      <span class="interest-icon">🤝</span>
      <span class="interest-label">Bénévolat</span>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-block">
    <h2 class="contact-title">Travaillons ensemble</h2>
    <p class="contact-sub">Ouvert aux opportunités en administration système, réseau et infrastructure IT.</p>
    <div class="contact-links">
      <a class="contact-link" href="mailto:marwenbhs@hotmail.fr">
        ✉ marwenbhs@hotmail.fr
      </a>
      <a class="contact-link" href="tel:+21650954564">
        ☎ +216 50 954 564
      </a>
      <a class="contact-link" href="https://www.linkedin.com/in/marwenbhs" target="_blank">
        ⇗ LinkedIn
      </a>
    </div>
  </div>
</section>

<footer>
  <span>© 2024 Marwen Haj Sassi</span>
  <span>Ariana, Tunisie</span>
</footer>

</body>
</html>
