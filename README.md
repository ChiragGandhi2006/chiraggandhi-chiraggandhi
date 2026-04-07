<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Chirag Gandhi — ML & Data Analytics</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #0d0d0f;
      --surface: #16161a;
      --surface2: #1e1e24;
      --border: rgba(255,255,255,0.08);
      --border2: rgba(255,255,255,0.14);
      --text: #f0f0f4;
      --muted: #8a8a9a;
      --accent: #7c6af7;
      --accent2: #34d49e;
      --accent3: #f0704a;
      --mono: 'Space Mono', monospace;
      --sans: 'DM Sans', sans-serif;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--sans);
      font-size: 15px;
      line-height: 1.7;
      min-height: 100vh;
    }

    /* Background grid */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(124,106,247,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(124,106,247,0.03) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
      z-index: 0;
    }

    .wrap {
      max-width: 860px;
      margin: 0 auto;
      padding: 3rem 1.5rem 4rem;
      position: relative;
      z-index: 1;
    }

    /* ── HERO ── */
    .hero {
      display: grid;
      grid-template-columns: auto 1fr;
      gap: 2rem;
      align-items: center;
      padding: 2.5rem;
      background: var(--surface);
      border: 1px solid var(--border2);
      border-radius: 20px;
      margin-bottom: 1.5rem;
      position: relative;
      overflow: hidden;
    }

    .hero::after {
      content: '';
      position: absolute;
      top: -60px; right: -60px;
      width: 220px; height: 220px;
      background: radial-gradient(circle, rgba(124,106,247,0.12) 0%, transparent 70%);
      pointer-events: none;
    }

    .avatar-ring {
      width: 88px; height: 88px;
      border-radius: 50%;
      padding: 3px;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      flex-shrink: 0;
    }

    .avatar-inner {
      width: 100%; height: 100%;
      border-radius: 50%;
      background: var(--bg);
      display: flex; align-items: center; justify-content: center;
      font-family: var(--mono);
      font-size: 22px;
      font-weight: 700;
      color: var(--accent);
    }

    .hero-text h1 {
      font-family: var(--mono);
      font-size: 26px;
      font-weight: 700;
      color: var(--text);
      letter-spacing: -0.5px;
      margin-bottom: 4px;
    }

    .hero-text .role {
      font-size: 14px;
      color: var(--accent2);
      font-family: var(--mono);
      margin-bottom: 10px;
    }

    .hero-text p {
      font-size: 14px;
      color: var(--muted);
      max-width: 480px;
      margin-bottom: 14px;
    }

    .tag-row { display: flex; flex-wrap: wrap; gap: 6px; }
    .tag {
      font-size: 11px;
      font-family: var(--mono);
      padding: 3px 10px;
      border-radius: 20px;
      border: 1px solid;
    }
    .tag-purple { border-color: rgba(124,106,247,0.4); color: #a598f9; background: rgba(124,106,247,0.08); }
    .tag-green  { border-color: rgba(52,212,158,0.4);  color: #34d49e; background: rgba(52,212,158,0.08); }
    .tag-coral  { border-color: rgba(240,112,74,0.4);  color: #f0704a; background: rgba(240,112,74,0.08); }

    /* ── SECTION TITLE ── */
    .sec-title {
      font-family: var(--mono);
      font-size: 11px;
      color: var(--muted);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 0.75rem;
      padding-bottom: 6px;
      border-bottom: 1px solid var(--border);
    }

    /* ── SOCIAL LINKS ── */
    .links-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
      gap: 10px;
      margin-bottom: 1.5rem;
    }

    .link-card {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 14px 16px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 14px;
      text-decoration: none;
      color: var(--text);
      transition: border-color 0.2s, background 0.2s, transform 0.15s;
    }

    .link-card:hover {
      border-color: var(--accent);
      background: var(--surface2);
      transform: translateY(-2px);
    }

    .link-icon {
      width: 38px; height: 38px;
      border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
      flex-shrink: 0;
    }

    .link-icon svg, .link-icon img { width: 20px; height: 20px; }
    .li-gh   { background: rgba(255,255,255,0.06); }
    .li-mail { background: rgba(124,106,247,0.12); }
    .li-cv   { background: rgba(52,212,158,0.12); }
    .li-lc   { background: rgba(240,112,74,0.12); }

    .link-info { min-width: 0; }
    .link-label { font-size: 13px; font-weight: 600; color: var(--text); display: block; }
    .link-sub   { font-size: 11px; color: var(--muted); font-family: var(--mono); display: block; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }

    .link-arrow {
      margin-left: auto;
      color: var(--muted);
      font-size: 16px;
      flex-shrink: 0;
    }

    /* ── PROJECT CARD ── */
    .project-card {
      display: block;
      text-decoration: none;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 1.4rem 1.5rem;
      margin-bottom: 1.5rem;
      transition: border-color 0.2s, transform 0.15s;
      position: relative;
      overflow: hidden;
    }

    .project-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 3px; height: 100%;
      background: linear-gradient(to bottom, var(--accent), var(--accent2));
    }

    .project-card:hover {
      border-color: rgba(124,106,247,0.4);
      transform: translateY(-2px);
    }

    .project-header {
      display: flex; align-items: center; gap: 12px; margin-bottom: 8px;
    }

    .project-dot {
      width: 10px; height: 10px; border-radius: 50%;
      background: var(--accent2);
      box-shadow: 0 0 8px var(--accent2);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    .project-title {
      font-family: var(--mono);
      font-size: 15px;
      font-weight: 700;
      color: var(--text);
    }

    .project-badge {
      margin-left: auto;
      font-size: 10px;
      font-family: var(--mono);
      padding: 3px 9px;
      border-radius: 20px;
      background: rgba(52,212,158,0.1);
      color: var(--accent2);
      border: 1px solid rgba(52,212,158,0.3);
    }

    .project-desc {
      font-size: 14px;
      color: var(--muted);
      padding-left: 22px;
    }

    /* ── TWO COLUMN ── */
    .two-col {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
      margin-bottom: 1.5rem;
    }

    @media (max-width: 560px) { .two-col { grid-template-columns: 1fr; } }

    .card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 1.25rem 1.4rem;
    }

    /* ── TOOLS ── */
    .tools-wrap { display: flex; flex-wrap: wrap; gap: 8px; }

    .tool-chip {
      display: flex; align-items: center; gap: 7px;
      padding: 6px 12px;
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: 20px;
      font-size: 12px;
      color: var(--text);
      font-weight: 500;
      transition: border-color 0.15s;
    }

    .tool-chip:hover { border-color: var(--border2); }
    .tool-chip img { width: 16px; height: 16px; }

    /* ── STATS ── */
    .stat-row {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      margin-bottom: 1.5rem;
    }

    .stat-box {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 1.1rem 1rem;
      text-align: center;
    }

    .stat-val {
      font-family: var(--mono);
      font-size: 22px;
      font-weight: 700;
      margin-bottom: 4px;
    }

    .stat-lbl { font-size: 11px; color: var(--muted); }

    /* ── PROFILE VIEWS BADGE ── */
    .profile-views {
      display: flex; justify-content: center;
      margin-bottom: 1.5rem;
    }

    .views-badge {
      display: flex; align-items: center; gap: 10px;
      padding: 10px 20px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 40px;
      font-size: 13px;
      color: var(--muted);
    }

    .views-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--accent); }

    /* ── GITHUB STATS IMAGES ── */
    .gh-stats {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-bottom: 1.5rem;
    }

    @media (max-width: 560px) { .gh-stats { grid-template-columns: 1fr; } }

    .gh-stats-full { margin-bottom: 1.5rem; }

    .gh-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 1rem;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .gh-card img { width: 100%; max-width: 100%; border-radius: 8px; }

    /* ── FOOTER ── */
    .footer {
      text-align: center;
      font-family: var(--mono);
      font-size: 11px;
      color: rgba(138,138,154,0.5);
      padding-top: 1rem;
      border-top: 1px solid var(--border);
    }

    @media (max-width: 600px) {
      .hero { grid-template-columns: 1fr; text-align: center; }
      .tag-row { justify-content: center; }
      .stat-row { grid-template-columns: 1fr 1fr; }
    }
  </style>
</head>
<body>
<div class="wrap">

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="avatar-ring">
      <div class="avatar-inner">CG</div>
    </div>
    <div class="hero-text">
      <h1>Chirag Gandhi</h1>
      <div class="role">// ML Engineer &amp; Data Analytics</div>
      <p>Passionate about building intelligent systems. Currently exploring autonomous AI agents and end-to-end data pipelines. Based in India.</p>
      <div class="tag-row">
        <span class="tag tag-purple">Machine Learning</span>
        <span class="tag tag-green">Data Analytics</span>
        <span class="tag tag-coral">Autonomous AI</span>
        <span class="tag tag-purple">Python</span>
        <span class="tag tag-green">Scikit-learn</span>
      </div>
    </div>
  </div>

  <!-- ── PROFILE VIEWS ── -->
  <div class="profile-views">
    <div class="views-badge">
      <div class="views-dot"></div>
      <img src="https://komarev.com/ghpvc/?username=chiraggandhi2006&label=Profile+views&color=7c6af7&style=flat" alt="Profile Views" style="height:20px;" />
    </div>
  </div>

  <!-- ── CONNECT LINKS ── -->
  <p class="sec-title">Connect with me</p>
  <div class="links-grid">

    <a class="link-card" href="https://github.com/ChiragGandhi2006" target="_blank">
      <div class="link-icon li-gh">
        <svg viewBox="0 0 24 24" fill="#f0f0f4"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.745 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
      </div>
      <div class="link-info">
        <span class="link-label">GitHub</span>
        <span class="link-sub">ChiragGandhi2006</span>
      </div>
      <span class="link-arrow">↗</span>
    </a>

    <a class="link-card" href="mailto:gandhichirag2006@gmail.com">
      <div class="link-icon li-mail">
        <svg viewBox="0 0 24 24" fill="none" stroke="#a598f9" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="M22 7l-10 7L2 7"/></svg>
      </div>
      <div class="link-info">
        <span class="link-label">Email</span>
        <span class="link-sub">gandhichirag2006@gmail.com</span>
      </div>
      <span class="link-arrow">↗</span>
    </a>

    <a class="link-card" href="https://drive.google.com/file/d/1tbnrEaX0_JBXDrE6vKeMO9vXBwBKPfjc/view?usp=sharing" target="_blank">
      <div class="link-icon li-cv">
        <svg viewBox="0 0 24 24" fill="none" stroke="#34d49e" stroke-width="2"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>
      </div>
      <div class="link-info">
        <span class="link-label">Resume / CV</span>
        <span class="link-sub">View on Google Drive</span>
      </div>
      <span class="link-arrow">↗</span>
    </a>

    <a class="link-card" href="https://leetcode.com/u/ckhjbwyksg/" target="_blank">
      <div class="link-icon li-lc">
        <svg viewBox="0 0 24 24" fill="#f0704a"><path d="M13.483 0a1.374 1.374 0 00-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 00-1.209 2.104 5.35 5.35 0 00-.125.513 5.527 5.527 0 00.062 2.362 5.83 5.83 0 00.349 1.017 5.938 5.938 0 001.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 00-1.951-.003l-2.396 2.392a3.021 3.021 0 01-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 01.066-.523 2.545 2.545 0 01.619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 00-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0013.483 0zm-2.866 12.815a1.38 1.38 0 00-1.38 1.382 1.38 1.38 0 001.38 1.382H20.79a1.38 1.38 0 001.38-1.382 1.38 1.38 0 00-1.38-1.382z"/></svg>
      </div>
      <div class="link-info">
        <span class="link-label">LeetCode</span>
        <span class="link-sub">ckhjbwyksg</span>
      </div>
      <span class="link-arrow">↗</span>
    </a>

  </div>

  <!-- ── ACTIVE PROJECT ── -->
  <p class="sec-title">Currently building</p>
  <a class="project-card" href="https://github.com/ChiragGandhi2006/Autonomous-AI-Project-Partner" target="_blank">
    <div class="project-header">
      <div class="project-dot"></div>
      <span class="project-title">Autonomous-AI-Project-Partner</span>
      <span class="project-badge">Active</span>
    </div>
    <p class="project-desc">An autonomous AI agent capable of assisting with end-to-end project management — from ideation to execution. Built with Python and modern LLM tooling.</p>
  </a>

  <!-- ── TOOLS + STATS ── -->
  <div class="two-col">
    <div class="card">
      <p class="sec-title">Languages &amp; Tools</p>
      <div class="tools-wrap">
        <div class="tool-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="">Python</div>
        <div class="tool-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="">C</div>
        <div class="tool-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt="">C++</div>
        <div class="tool-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="">Pandas</div>
        <div class="tool-chip"><img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" alt="">Scikit-learn</div>
        <div class="tool-chip"><img src="https://seaborn.pydata.org/_images/logo-mark-lightbg.svg" alt="">Seaborn</div>
        <div class="tool-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="">MySQL</div>
        <div class="tool-chip"><img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="">Git</div>
        <div class="tool-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="">HTML5</div>
        <div class="tool-chip"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="">CSS3</div>
        <div class="tool-chip"><img src="https://cdn.worldvectorlogo.com/logos/arduino-1.svg" alt="">Arduino</div>
      </div>
    </div>

    <div class="card">
      <p class="sec-title">Focus areas</p>
      <div class="stat-row" style="grid-template-columns:1fr 1fr 1fr; margin-bottom:0;">
        <div class="stat-box">
          <div class="stat-val" style="color:var(--accent)">ML</div>
          <div class="stat-lbl">Machine Learning</div>
        </div>
        <div class="stat-box">
          <div class="stat-val" style="color:var(--accent2)">DA</div>
          <div class="stat-lbl">Data Analytics</div>
        </div>
        <div class="stat-box">
          <div class="stat-val" style="color:var(--accent3)">AI</div>
          <div class="stat-lbl">AI Agents</div>
        </div>
      </div>

      <div style="margin-top:14px;">
        <p class="sec-title" style="margin-top:4px;">GitHub trophies</p>
        <img src="https://github-profile-trophy.vercel.app/?username=chiraggandhi2006&theme=darkhub&no-frame=true&margin-w=4&column=4" alt="Trophies" style="width:100%; border-radius:8px;" />
      </div>
    </div>
  </div>

  <!-- ── GITHUB STATS ── -->
  <p class="sec-title">GitHub stats</p>
  <div class="gh-stats">
    <div class="gh-card">
      <img src="https://github-readme-stats.vercel.app/api/top-langs?username=chiraggandhi2006&show_icons=true&locale=en&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages" />
    </div>
    <div class="gh-card">
      <img src="https://github-readme-stats.vercel.app/api?username=chiraggandhi2006&show_icons=true&locale=en&theme=tokyonight&hide_border=true" alt="GitHub Stats" />
    </div>
  </div>
  <div class="gh-stats-full">
    <div class="gh-card">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=chiraggandhi2006&theme=tokyonight&hide_border=true" alt="GitHub Streak" />
    </div>
  </div>

  <!-- ── FOOTER ── -->
  <div class="footer">
    Made with passion · Chirag Gandhi · Pune, India · gandhichirag2006@gmail.com
  </div>

</div>
</body>
</html>
