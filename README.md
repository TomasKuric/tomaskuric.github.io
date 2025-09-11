<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Tomas Kuric — Financial Mathematics Student</title>
  <meta name="description" content="Portfolio of a Financial Mathematics student — projects, skills and contact." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0f1115;
      --card:#0f1720;
      --muted:#94a3b8;
      --accent1:#7c3aed;
      --accent2:#06b6d4;
      --glass: rgba(255,255,255,0.04);
      --radius:16px;
      --max-w:1100px;
      color-scheme: dark;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(124,58,237,0.08), transparent),
                  radial-gradient(800px 400px at 90% 90%, rgba(6,182,212,0.06), transparent),
                  var(--bg);
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
      padding:32px 20px;
      display:flex;
      justify-content:center;
    }

    .container{
      width:100%;
      max-width:var(--max-w);
    }

    header{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      margin-bottom:28px;
    }

    /* logo */
    .logo{
      display:flex;
      align-items:center;
      gap:12px;
    }
    .brand{
      background:linear-gradient(135deg,var(--accent1),var(--accent2));
      width:48px;height:48px;border-radius:12px;
      display:grid;place-items:center;font-weight:700;font-family:JetBrains Mono,monospace;
      box-shadow:0 6px 18px rgba(3,7,18,0.6);
    }
    nav{display:flex;align-items:center;gap:18px}
    nav a{
      color:var(--muted);text-decoration:none;font-weight:600;font-size:14px;padding:8px 10px;border-radius:10px;
    }
    nav a:hover{color:#fff;background:var(--glass)}

    /* hero */
    .hero{
      display:grid;grid-template-columns:1fr 360px;gap:32px;align-items:center;margin-bottom:48px;
    }

    .intro h1{
      font-size:44px;margin:0 0 8px 0;letter-spacing:-0.02em;
    }
    .intro p{margin:0 0 20px;color:var(--muted);max-width:52ch}
    .ctas{display:flex;gap:12px}
    .btn{display:inline-flex;align-items:center;gap:10px;padding:10px 14px;border-radius:12px;text-decoration:none;font-weight:700;font-size:14px}
    .btn-primary{background:linear-gradient(90deg,var(--accent1),var(--accent2));box-shadow:0 8px 30px rgba(7,12,22,0.5)}
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted)}

    .profile-card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
      padding:22px;border-radius:var(--radius);
      box-shadow: 0 10px 30px rgba(2,6,23,0.6);
      position:relative;overflow:hidden;
    }
    .blob{position:absolute;right:-80px;top:-80px;width:240px;height:240px;background:linear-gradient(135deg,var(--accent2),rgba(124,58,237,0.5));filter:blur(48px);opacity:0.6;border-radius:40%}
    .avatar{width:96px;height:96px;border-radius:20px;overflow:hidden;border:4px solid rgba(255,255,255,0.02);background:linear-gradient(180deg,#0b1220,#071018);display:block}
    .meta{display:flex;gap:12px;align-items:center}
    .meta h3{margin:0;font-size:18px}
    .meta p{margin:0;color:var(--muted);font-size:13px}
    .small{font-size:13px;color:var(--muted);margin-top:14px}

    /* projects */
    section.projects{margin-bottom:48px}
    .projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:18px}
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
      padding:16px;border-radius:14px;border:1px solid rgba(255,255,255,0.03);backdrop-filter: blur(6px);
      transition:transform .28s ease,box-shadow .28s ease;
    }
    .card:hover{transform:translateY(-8px);box-shadow:0 20px 40px rgba(2,6,23,0.6)}
    .card .thumb{height:130px;border-radius:10px;overflow:hidden;margin-bottom:12px;background:linear-gradient(90deg, rgba(124,58,237,0.12), rgba(6,182,212,0.06));display:grid;place-items:center;color:var(--muted);font-weight:700}
    .tech{display:flex;flex-wrap:wrap;gap:6px;margin-top:10px}
    .tag{font-size:12px;padding:6px 8px;border-radius:8px;background:rgba(255,255,255,0.02);color:var(--muted)}
    .card h4{margin:6px 0 0 0}
    .card p{color:var(--muted);font-size:13px}
    .card .links{display:flex;gap:10px;margin-top:12px}
    .link{
      text-decoration:none;font-weight:700;padding:8px 10px;border-radius:10px;font-size:13px;background:transparent;border:1px solid rgba(255,255,255,0.03)
    }

    /* about */
    .about{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-bottom:48px}
    .skills{display:flex;flex-wrap:wrap;gap:10px}

    /* footer */
    footer{padding:24px 0;color:var(--muted);display:flex;justify-content:space-between;align-items:center}

    /* responsive */
    @media (max-width:860px){
      .hero{grid-template-columns:1fr;}
      .about{grid-template-columns:1fr}
      nav{display:none}
    }

    /* simple modal */
    .modal-backdrop{position:fixed;inset:0;background:rgba(2,6,23,0.6);display:none;place-items:center;padding:20px}
    .modal{background:linear-gradient(180deg, #06101a, #07101b);padding:20px;border-radius:12px;max-width:720px;width:100%;border:1px solid rgba(255,255,255,0.04)}
    .modal h3{Margin-top:0}
    .close-btn{background:transparent;border:0;color:var(--muted);font-weight:700}

  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">
        <div class="brand">TK</div>
        <div>
          <div style="font-weight:700">Tomas Kuric</div>
          <div style="font-size:12px;color:var(--muted);margin-top:3px">Financial Mathematics • Student</div>
        </div>
      </div>
      <nav>
        <a href="#projects">Work</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
        <a class="btn btn-ghost" href="/resume.pdf" target="_blank">Resume</a>
      </nav>
    </header>

    <main>
      <section class="hero">
        <div class="intro">
          <h1>Hi — I'm Tomas. I turn numbers into clear models and visuals.</h1>
          <p>I study financial mathematics and enjoy translating quantitative ideas into reproducible code, clean reports and interactive visuals. Below are a few selected projects — mostly Python, some R and a little web work.</p>
          <div class="ctas">
            <a class="btn btn-primary" href="#projects">See my work</a>
            <a class="btn btn-ghost" href="#contact">Get in touch</a>
          </div>
        </div>

        <aside class="profile-card" aria-hidden="false">
          <div class="blob"></div>
          <div style="display:flex;align-items:center;gap:12px;position:relative;z-index:2">
            <img class="avatar" src="https://via.placeholder.com/200x200.png?text=Photo" alt="Portrait">
            <div>
              <div class="meta">
                <div>
                  <h3>Tomas Kuric</h3>
                  <p>Financial Mathematics • University</p>
                </div>
              </div>
              <div class="small">Available for internships & entry-level quantitative roles. Open to remote or on-site opportunities.</div>
            </div>
          </div>
        </aside>
      </section>

      <section id="projects" class="projects">
        <h2 style="margin:0 0 18px 0">Selected projects</h2>
        <div class="projects-grid">
          <article class="card" data-proj="1">
            <div class="thumb">─ Pricing Monte Carlo ─</div>
            <h4>Monte Carlo Option Pricer</h4>
            <p>Fast vectorised pricer for vanilla & barrier options. Includes variance reduction and sensitivity estimation.</p>
            <div class="tech">
              <span class="tag">Python</span>
              <span class="tag">NumPy</span>
              <span class="tag">Pandas</span>
            </div>
            <div class="links">
              <a class="link" href="#" data-open="1">Details</a>
              <a class="link" href="#" onclick="event.preventDefault();window.open('https://github.com/tomaskuric','_blank')">Code</a>
            </div>
          </article>

          <article class="card" data-proj="2">
            <div class="thumb">─ Time Series Dashboard ─</div>
            <h4>Risk Dashboard</h4>
            <p>Interactive dashboard showing VaR, rolling volatility and scenario analysis. Built with Plotly + Dash.</p>
            <div class="tech">
              <span class="tag">Python</span>
              <span class="tag">Plotly</span>
              <span class="tag">Dash</span>
            </div>
            <div class="links">
              <a class="link" href="#" data-open="2">Details</a>
              <a class="link" href="#" onclick="event.preventDefault();window.open('https://yourdashdemo.example','_blank')">Demo</a>
            </div>
          </article>

          <article class="card" data-proj="3">
            <div class="thumb">─ Term Structure Study ─</div>
            <h4>Term Structure Analysis</h4>
            <p>Yield curve modelling (Svensson & Nelson–Siegel) and forecast evaluation. Reproducible notebook included.</p>
            <div class="tech">
              <span class="tag">R</span>
              <span class="tag">tidyverse</span>
              <span class="tag">ggplot2</span>
            </div>
            <div class="links">
              <a class="link" href="#" data-open="3">Details</a>
              <a class="link" href="#" onclick="event.preventDefault();window.open('https://github.com/tomaskuric/term-structure','_blank')">Code</a>
            </div>
          </article>

        </div>
      </section>

      <section id="about" class="about">
        <div>
          <h2 style="margin-top:0">About me</h2>
          <p style="color:var(--muted)">I'm a student with interests in quantitative finance: stochastic calculus, time series, risk modelling and numerical methods. I prefer clean, reproducible code and clear visualisations.</p>
          <p style="color:var(--muted)">Current interests: option pricing, portfolio optimisation and model risk.</p>
        </div>
        <div>
          <h3 style="margin:0">Skills</h3>
          <div class="skills" style="margin-top:10px">
            <span class="tag">Python</span>
            <span class="tag">NumPy</span>
            <span class="tag">Pandas</span>
            <span class="tag">R</span>
            <span class="tag">SQL</span>
            <span class="tag">Machine Learning</span>
            <span class="tag">Time Series</span>
            <span class="tag">Mathematical Finance</span>
          </div>
          <div style="margin-top:16px;color:var(--muted);font-size:13px">Open to collaborating on open-source projects and demos.</div>
        </div>
      </section>

      <section id="contact" style="margin-bottom:48px">
        <h2 style="margin-top:0">Contact</h2>
        <p style="color:var(--muted)">If you'd like to discuss internships, projects or collaborations — email me or connect on LinkedIn.</p>
        <div style="display:flex;gap:12px;flex-wrap:wrap;margin-top:12px">
          <a class="btn btn-primary" href="mailto:you@example.com">Email me</a>
          <a class="btn btn-ghost" href="https://www.linkedin.com" target="_blank">LinkedIn</a>
          <a class="btn btn-ghost" href="https://github.com/tomaskuric" target="_blank">GitHub</a>
        </div>
      </section>

    </main>

    <footer>
      <div>© <span id="year"></span> Tomas Kuric</div>
      <div style="display:flex;gap:10px">
        <a href="https://github.com/tomaskuric" target="_blank" style="color:var(--muted);text-decoration:none">GitHub</a>
        <a href="https://www.linkedin.com" target="_blank" style="color:var(--muted);text-decoration:none">LinkedIn</a>
      </div>
    </footer>
  </div>

  <!-- modal -->
  <div id="modalBackdrop" class="modal-backdrop" role="dialog" aria-modal="true">
    <div class="modal" role="document">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
        <h3 id="modalTitle">Project</h3>
        <button class="close-btn" id="closeModal">✕</button>
      </div>
      <div id="modalBody" style="color:var(--muted)"></div>
    </div>
  </div>

  <script>
    // fill year
    document.getElementById('year').textContent = new Date().getFullYear();

    // project details (demo content)
    const projectData = {
      1: { title: 'Monte Carlo Option Pricer', body: `Vectorised payoff generation, antithetic sampling, control variates, and simple benchmarking (Jupyter notebook).` },
      2: { title: 'Risk Dashboard', body: `Plotly Dash app with rolling VaR, historical scenarios and simple stress-tests.` },
      3: { title: 'Term Structure Analysis', body: `Curve fitting, bootstrapping and visual analysis in a reproducible notebook.` }
    }

    // open modal
    document.querySelectorAll('[data-open]').forEach(btn => {
      btn.addEventListener('click', (e) => {
        const id = e.currentTarget.getAttribute('data-open');
        openModal(id);
      });
    });

    document.querySelectorAll('.card').forEach(card => {
      card.addEventListener('click', (e) => {
        const pid = card.getAttribute('data-proj');
        if(pid) openModal(pid);
      })
    })

    function openModal(id){
      const data = projectData[id];
      if(!data) return;
      document.getElementById('modalTitle').textContent = data.title;
      document.getElementById('modalBody').innerHTML = `<p>${data.body}</p><p style="margin-top:12px;">Links: <a href="https://github.com/tomaskuric" target="_blank">Code</a> • <a href="#">Notebook</a></p>`;
      const mb = document.getElementById('modalBackdrop');
      mb.style.display = 'grid';
      document.getElementById('closeModal').focus();
    }
    document.getElementById('closeModal').addEventListener('click', () => { document.getElementById('modalBackdrop').style.display = 'none'; })
    document.getElementById('modalBackdrop').addEventListener('click', (e) => { if(e.target === e.currentTarget) e.currentTarget.style.display = 'none'; })

    // smooth scroll
    document.querySelectorAll('a[href^="#"]').forEach(a=>{
      a.addEventListener('click', (e)=>{
        const href = a.getAttribute('href');
        if(href === '#') return;
        const el = document.querySelector(href);
        if(el){ e.preventDefault(); el.scrollIntoView({behavior:'smooth',block:'start'}) }
      })
    })

    // escape closes modal
    document.addEventListener('keydown', (e)=>{ if(e.key === 'Escape') document.getElementById('modalBackdrop').style.display = 'none'; })
  </script>
</body>
</html>
