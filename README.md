# <!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Portfólio BI | Analista de Dados</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
:root {
  --dark: #0a0e1a;
  --darker: #060910;
  --card: #111827;
  --card2: #141d2e;
  --accent: #3b82f6;
  --accent2: #06b6d4;
  --accent3: #8b5cf6;
  --gold: #f59e0b;
  --green: #10b981;
  --text: #f1f5f9;
  --muted: #94a3b8;
  --border: rgba(255,255,255,0.07);
  --glow: rgba(59,130,246,0.15);
}

*{margin:0;padding:0;box-sizing:border-box;}

html{scroll-behavior:smooth;}

body{
  background:var(--dark);
  color:var(--text);
  font-family:'DM Sans',sans-serif;
  font-size:16px;
  line-height:1.7;
  overflow-x:hidden;
}

/* ── GRID BACKGROUND ── */
body::before{
  content:'';
  position:fixed;
  inset:0;
  background-image:
    linear-gradient(rgba(59,130,246,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(59,130,246,0.04) 1px, transparent 1px);
  background-size:60px 60px;
  pointer-events:none;
  z-index:0;
}

/* ── NAVBAR ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:100;
  display:flex;align-items:center;justify-content:space-between;
  padding:1.2rem 5%;
  background:rgba(10,14,26,0.85);
  backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border);
}

.nav-logo{
  font-family:'Syne',sans-serif;
  font-weight:800;font-size:1.2rem;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  letter-spacing:-0.02em;
}

.nav-links{display:flex;gap:2rem;list-style:none;}
.nav-links a{
  color:var(--muted);font-size:0.88rem;text-decoration:none;
  font-weight:500;letter-spacing:0.05em;text-transform:uppercase;
  transition:color 0.2s;
}
.nav-links a:hover{color:var(--text);}

/* ── HERO ── */
#hero{
  min-height:100vh;
  display:flex;align-items:center;
  padding:0 5%;
  position:relative;
  overflow:hidden;
}

.hero-blob{
  position:absolute;
  border-radius:50%;
  filter:blur(80px);
  pointer-events:none;
}
.blob1{width:500px;height:500px;background:rgba(59,130,246,0.12);top:-100px;right:-100px;}
.blob2{width:400px;height:400px;background:rgba(139,92,246,0.10);bottom:-80px;left:5%;}
.blob3{width:300px;height:300px;background:rgba(6,182,212,0.08);top:40%;right:30%;}

.hero-content{
  position:relative;z-index:1;
  max-width:800px;
}

.hero-tag{
  display:inline-flex;align-items:center;gap:0.5rem;
  background:rgba(59,130,246,0.1);
  border:1px solid rgba(59,130,246,0.25);
  border-radius:999px;
  padding:0.35rem 1rem;
  font-size:0.8rem;font-weight:500;color:var(--accent2);
  letter-spacing:0.08em;text-transform:uppercase;
  margin-bottom:1.5rem;
  animation:fadeUp 0.6s ease both;
}

.dot-pulse{
  width:7px;height:7px;border-radius:50%;background:var(--green);
  animation:pulse 2s infinite;
}

@keyframes pulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:0.5;transform:scale(0.8);}}

.hero-title{
  font-family:'Syne',sans-serif;
  font-size:clamp(2.8rem,7vw,5.5rem);
  font-weight:800;
  line-height:1.05;
  letter-spacing:-0.03em;
  margin-bottom:1.5rem;
  animation:fadeUp 0.6s 0.1s ease both;
}

.hero-title .line2{
  background:linear-gradient(135deg,var(--accent) 0%,var(--accent2) 50%,var(--accent3) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
}

.hero-sub{
  font-size:1.15rem;color:var(--muted);
  max-width:520px;margin-bottom:2.5rem;
  font-weight:300;
  animation:fadeUp 0.6s 0.2s ease both;
}

.hero-actions{
  display:flex;gap:1rem;flex-wrap:wrap;
  animation:fadeUp 0.6s 0.3s ease both;
}

.btn-primary{
  display:inline-flex;align-items:center;gap:0.5rem;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  color:#fff;font-weight:600;font-size:0.95rem;
  padding:0.85rem 2rem;border-radius:8px;
  text-decoration:none;border:none;cursor:pointer;
  transition:transform 0.2s,box-shadow 0.2s;
  box-shadow:0 0 30px rgba(59,130,246,0.3);
}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 0 45px rgba(59,130,246,0.45);}

.btn-outline{
  display:inline-flex;align-items:center;gap:0.5rem;
  background:transparent;
  color:var(--text);font-weight:500;font-size:0.95rem;
  padding:0.85rem 2rem;border-radius:8px;
  text-decoration:none;
  border:1px solid var(--border);
  transition:border-color 0.2s,background 0.2s;
}
.btn-outline:hover{border-color:rgba(255,255,255,0.2);background:rgba(255,255,255,0.05);}

/* ── STATS BAR ── */
.stats-bar{
  display:flex;gap:3rem;flex-wrap:wrap;
  margin-top:4rem;padding-top:3rem;
  border-top:1px solid var(--border);
  animation:fadeUp 0.6s 0.4s ease both;
}
.stat-item{}
.stat-num{
  font-family:'Syne',sans-serif;
  font-size:2rem;font-weight:800;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
}
.stat-label{font-size:0.82rem;color:var(--muted);text-transform:uppercase;letter-spacing:0.06em;}

/* ── SECTIONS ── */
section{
  position:relative;z-index:1;
  padding:6rem 5%;
}

.section-label{
  display:inline-block;
  font-size:0.75rem;font-weight:600;
  color:var(--accent2);letter-spacing:0.15em;text-transform:uppercase;
  margin-bottom:0.8rem;
}

.section-title{
  font-family:'Syne',sans-serif;
  font-size:clamp(1.8rem,4vw,2.8rem);
  font-weight:800;letter-spacing:-0.02em;
  margin-bottom:1rem;
}

.section-sub{
  color:var(--muted);font-size:1rem;
  max-width:500px;margin-bottom:3rem;
  font-weight:300;
}

/* ── SKILLS ── */
#skills{background:var(--darker);}

.skills-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:1.5rem;
}

.skill-card{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:16px;
  padding:1.8rem;
  transition:transform 0.2s,border-color 0.2s,box-shadow 0.2s;
  position:relative;overflow:hidden;
}
.skill-card::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,var(--glow),transparent);
  opacity:0;transition:opacity 0.3s;
}
.skill-card:hover{transform:translateY(-4px);border-color:rgba(59,130,246,0.3);box-shadow:0 20px 40px rgba(0,0,0,0.3);}
.skill-card:hover::before{opacity:1;}

.skill-icon{
  width:48px;height:48px;border-radius:12px;
  display:flex;align-items:center;justify-content:center;
  font-size:1.5rem;margin-bottom:1rem;
}

.skill-name{
  font-family:'Syne',sans-serif;
  font-size:1.05rem;font-weight:700;margin-bottom:0.4rem;
}
.skill-desc{font-size:0.88rem;color:var(--muted);}

.skill-tags{display:flex;flex-wrap:wrap;gap:0.4rem;margin-top:1rem;}
.tag{
  font-size:0.72rem;font-weight:500;
  padding:0.25rem 0.65rem;border-radius:999px;
  background:rgba(59,130,246,0.1);
  border:1px solid rgba(59,130,246,0.2);
  color:var(--accent2);
}

/* ── PROJECTS ── */
#projetos{}

.projects-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
  gap:1.5rem;
}

.project-card{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:20px;
  overflow:hidden;
  transition:transform 0.2s,box-shadow 0.2s;
  display:flex;flex-direction:column;
}
.project-card:hover{transform:translateY(-6px);box-shadow:0 30px 60px rgba(0,0,0,0.4);}

.project-thumb{
  height:180px;
  display:flex;align-items:center;justify-content:center;
  position:relative;overflow:hidden;
}

.thumb-rh{background:linear-gradient(135deg,#0f1e3d,#1e3a6e);}
.thumb-fin{background:linear-gradient(135deg,#0a2017,#144d30);}
.thumb-log{background:linear-gradient(135deg,#1a0b2e,#3b1f5e);}
.thumb-op{background:linear-gradient(135deg,#1a1200,#4a3000);}
.thumb-exec{background:linear-gradient(135deg,#0d1a2e,#1a3a5c);}
.thumb-com{background:linear-gradient(135deg,#1a0d14,#3d1a2e);}

.thumb-grid{
  display:grid;grid-template-columns:repeat(3,1fr);gap:6px;
  padding:1.5rem;width:100%;
}
.thumb-bar{border-radius:4px;animation:barGrow 1s ease both;}
@keyframes barGrow{from{transform:scaleY(0);transform-origin:bottom;}to{transform:scaleY(1);}}

.thumb-label{
  position:absolute;bottom:1rem;left:1rem;
  font-family:'Syne',sans-serif;
  font-size:0.7rem;font-weight:700;
  letter-spacing:0.12em;text-transform:uppercase;
  color:rgba(255,255,255,0.4);
}

.project-body{padding:1.5rem;flex:1;display:flex;flex-direction:column;}

.project-badge{
  font-size:0.7rem;font-weight:600;
  padding:0.2rem 0.6rem;border-radius:999px;
  text-transform:uppercase;letter-spacing:0.08em;
  display:inline-block;margin-bottom:0.8rem;
  width:fit-content;
}
.badge-rh{background:rgba(59,130,246,0.15);color:#60a5fa;}
.badge-fin{background:rgba(16,185,129,0.15);color:#34d399;}
.badge-log{background:rgba(139,92,246,0.15);color:#a78bfa;}
.badge-op{background:rgba(245,158,11,0.15);color:#fbbf24;}
.badge-exec{background:rgba(6,182,212,0.15);color:#22d3ee;}
.badge-com{background:rgba(236,72,153,0.15);color:#f472b6;}

.project-title{
  font-family:'Syne',sans-serif;
  font-size:1.2rem;font-weight:700;
  margin-bottom:0.5rem;letter-spacing:-0.01em;
}
.project-desc{font-size:0.88rem;color:var(--muted);flex:1;margin-bottom:1.2rem;}

.project-metrics{
  display:flex;gap:1rem;flex-wrap:wrap;
  margin-bottom:1.2rem;
}
.metric-pill{
  font-size:0.78rem;font-weight:500;color:var(--muted);
  display:flex;align-items:center;gap:0.3rem;
}
.metric-pill span{color:var(--text);font-weight:600;}

.project-footer{
  display:flex;align-items:center;justify-content:space-between;
  padding-top:1rem;border-top:1px solid var(--border);
}
.project-tools{display:flex;gap:0.4rem;flex-wrap:wrap;}
.tool-tag{
  font-size:0.7rem;padding:0.2rem 0.5rem;border-radius:4px;
  background:rgba(255,255,255,0.05);color:var(--muted);
  border:1px solid var(--border);
}

.btn-view{
  font-size:0.78rem;font-weight:600;color:var(--accent2);
  text-decoration:none;
  display:flex;align-items:center;gap:0.3rem;
  transition:gap 0.2s;
  background:none;border:none;cursor:pointer;
}
.btn-view:hover{gap:0.6rem;}

/* ── PROCESS ── */
#processo{background:var(--darker);}

.process-steps{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
  gap:0;
  position:relative;
}
.process-steps::before{
  content:'';
  position:absolute;top:36px;left:10%;right:10%;height:1px;
  background:linear-gradient(90deg,transparent,var(--accent),var(--accent2),transparent);
}

.process-step{
  text-align:center;padding:0 1rem;
  position:relative;z-index:1;
}
.step-num{
  width:72px;height:72px;border-radius:50%;
  border:1px solid rgba(59,130,246,0.3);
  background:var(--card);
  display:flex;align-items:center;justify-content:center;
  margin:0 auto 1.2rem;
  font-family:'Syne',sans-serif;
  font-size:1.3rem;font-weight:800;
  color:var(--accent);
  box-shadow:0 0 30px rgba(59,130,246,0.15);
}
.step-title{
  font-family:'Syne',sans-serif;
  font-size:0.95rem;font-weight:700;margin-bottom:0.4rem;
}
.step-desc{font-size:0.82rem;color:var(--muted);}

/* ── ABOUT ── */
#sobre{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:5rem;
  align-items:center;
}

.about-visual{
  position:relative;
}

.about-card-main{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:20px;
  padding:2rem;
  position:relative;
}

.avatar{
  width:80px;height:80px;border-radius:50%;
  background:linear-gradient(135deg,var(--accent),var(--accent3));
  display:flex;align-items:center;justify-content:center;
  font-family:'Syne',sans-serif;font-size:2rem;font-weight:800;
  color:#fff;margin-bottom:1.2rem;
}

.about-name{font-family:'Syne',sans-serif;font-size:1.3rem;font-weight:700;margin-bottom:0.2rem;}
.about-role{font-size:0.88rem;color:var(--accent2);}

.about-card-stats{
  display:grid;grid-template-columns:1fr 1fr;gap:1rem;
  margin-top:1.5rem;padding-top:1.5rem;border-top:1px solid var(--border);
}
.about-stat{text-align:center;}
.about-stat-num{
  font-family:'Syne',sans-serif;font-size:1.6rem;font-weight:800;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
}
.about-stat-label{font-size:0.75rem;color:var(--muted);}

.floating-badge{
  position:absolute;
  background:var(--card2);
  border:1px solid var(--border);
  border-radius:12px;
  padding:0.8rem 1rem;
  font-size:0.8rem;font-weight:500;
  display:flex;align-items:center;gap:0.5rem;
  box-shadow:0 10px 30px rgba(0,0,0,0.3);
}
.fb1{top:-20px;right:-20px;}
.fb2{bottom:-20px;left:-20px;}
.fb-dot{width:8px;height:8px;border-radius:50%;}

.about-text p{color:var(--muted);margin-bottom:1.2rem;font-size:0.97rem;}
.about-text strong{color:var(--text);}

.cert-list{
  display:flex;flex-direction:column;gap:0.8rem;margin-top:2rem;
}
.cert-item{
  display:flex;align-items:center;gap:0.8rem;
  background:var(--card);border:1px solid var(--border);
  border-radius:10px;padding:0.8rem 1rem;
  font-size:0.85rem;
}
.cert-icon{
  width:32px;height:32px;border-radius:8px;
  display:flex;align-items:center;justify-content:center;
  font-size:1rem;flex-shrink:0;
}

/* ── CONTACT ── */
#contato{background:var(--darker);text-align:center;}

.contact-card{
  max-width:600px;margin:0 auto;
  background:var(--card);
  border:1px solid var(--border);
  border-radius:24px;
  padding:3rem;
  position:relative;overflow:hidden;
}
.contact-card::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse at top,rgba(59,130,246,0.08),transparent 60%);
}

.contact-title{
  font-family:'Syne',sans-serif;
  font-size:1.8rem;font-weight:800;margin-bottom:0.5rem;
  position:relative;
}
.contact-sub{color:var(--muted);margin-bottom:2rem;position:relative;}

.contact-form{position:relative;}
.form-group{margin-bottom:1rem;text-align:left;}
.form-label{font-size:0.8rem;font-weight:500;color:var(--muted);display:block;margin-bottom:0.4rem;text-transform:uppercase;letter-spacing:0.06em;}
.form-input,.form-textarea{
  width:100%;
  background:rgba(255,255,255,0.04);
  border:1px solid var(--border);
  border-radius:10px;
  padding:0.8rem 1rem;
  color:var(--text);
  font-family:'DM Sans',sans-serif;
  font-size:0.95rem;
  transition:border-color 0.2s,box-shadow 0.2s;
  outline:none;
}
.form-input:focus,.form-textarea:focus{
  border-color:rgba(59,130,246,0.5);
  box-shadow:0 0 0 3px rgba(59,130,246,0.1);
}
.form-textarea{resize:vertical;min-height:120px;}

.form-row{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}

.btn-send{
  width:100%;margin-top:0.5rem;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  color:#fff;font-weight:600;font-size:1rem;
  padding:1rem;border-radius:10px;
  border:none;cursor:pointer;
  font-family:'DM Sans',sans-serif;
  transition:transform 0.2s,box-shadow 0.2s;
  box-shadow:0 0 30px rgba(59,130,246,0.3);
}
.btn-send:hover{transform:translateY(-2px);box-shadow:0 0 45px rgba(59,130,246,0.45);}

.contact-links{
  display:flex;justify-content:center;gap:1rem;margin-top:1.5rem;position:relative;
}
.contact-link{
  display:flex;align-items:center;gap:0.4rem;
  color:var(--muted);font-size:0.85rem;text-decoration:none;
  transition:color 0.2s;padding:0.5rem 0.8rem;
  border-radius:8px;border:1px solid var(--border);
}
.contact-link:hover{color:var(--text);border-color:rgba(255,255,255,0.2);}

/* ── FOOTER ── */
footer{
  text-align:center;padding:2rem 5%;
  border-top:1px solid var(--border);
  color:var(--muted);font-size:0.82rem;
}

/* ── ANIMATIONS ── */
@keyframes fadeUp{
  from{opacity:0;transform:translateY(24px);}
  to{opacity:1;transform:translateY(0);}
}

.reveal{opacity:0;transform:translateY(30px);transition:opacity 0.6s ease,transform 0.6s ease;}
.reveal.visible{opacity:1;transform:translateY(0);}

/* ── SCROLLBAR ── */
::-webkit-scrollbar{width:6px;}
::-webkit-scrollbar-track{background:var(--darker);}
::-webkit-scrollbar-thumb{background:rgba(59,130,246,0.4);border-radius:99px;}

/* ── MOBILE ── */
@media(max-width:768px){
  nav{padding:1rem 4%;}
  .nav-links{display:none;}
  #sobre{grid-template-columns:1fr;gap:2rem;}
  .process-steps::before{display:none;}
  .form-row{grid-template-columns:1fr;}
  .floating-badge{display:none;}
  .stats-bar{gap:2rem;}
}
</style>
</head>
<body>

<!-- ══ NAV ══ -->
<nav>
  <div class="nav-logo">BI Portfolio</div>
  <ul class="nav-links">
    <li><a href="#habilidades">Habilidades</a></li>
    <li><a href="#projetos">Projetos</a></li>
    <li><a href="#processo">Processo</a></li>
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#contato">Contato</a></li>
  </ul>
  <a href="#contato" class="btn-primary" style="padding:0.6rem 1.2rem;font-size:0.85rem;">Fale comigo</a>
</nav>

<!-- ══ HERO ══ -->
<section id="hero">
  <div class="hero-blob blob1"></div>
  <div class="hero-blob blob2"></div>
  <div class="hero-blob blob3"></div>

  <div class="hero-content">
    <div class="hero-tag">
      <span class="dot-pulse"></span>
      Disponível para projetos
    </div>

    <h1 class="hero-title">
      Dados que<br>
      <span class="line2">geram decisões.</span>
    </h1>

    <p class="hero-sub">
      Analista de BI especializado em transformar dados brutos em dashboards estratégicos que aceleram decisões de negócio.
    </p>

    <div class="hero-actions">
      <a href="#projetos" class="btn-primary">
        Ver projetos
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </a>
      <a href="#contato" class="btn-outline">Entrar em contato</a>
    </div>

    <div class="stats-bar">
      <div class="stat-item">
        <div class="stat-num">6+</div>
        <div class="stat-label">Dashboards no portfólio</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">3</div>
        <div class="stat-label">Áreas de atuação</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">100%</div>
        <div class="stat-label">Foco em resultado</div>
      </div>
    </div>
  </div>
</section>

<!-- ══ SKILLS ══ -->
<section id="habilidades">
  <div class="section-label">Habilidades</div>
  <h2 class="section-title">Stack técnica</h2>
  <p class="section-sub">Ferramentas e tecnologias que uso para construir soluções de dados completas.</p>

  <div class="skills-grid reveal">

    <div class="skill-card">
      <div class="skill-icon" style="background:rgba(59,130,246,0.15);">📊</div>
      <div class="skill-name">Power BI</div>
      <div class="skill-desc">Construção de dashboards interativos, modelagem de dados e relatórios executivos.</div>
      <div class="skill-tags">
        <span class="tag">DAX</span><span class="tag">Power Query</span><span class="tag">Relatórios</span><span class="tag">KPIs</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon" style="background:rgba(16,185,129,0.15);">🗄️</div>
      <div class="skill-name">SQL</div>
      <div class="skill-desc">Extração, transformação e análise de dados em bancos relacionais.</div>
      <div class="skill-tags">
        <span class="tag">SELECT / JOIN</span><span class="tag">Subqueries</span><span class="tag">CTEs</span><span class="tag">Window Functions</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon" style="background:rgba(245,158,11,0.15);">📋</div>
      <div class="skill-name">Excel Avançado</div>
      <div class="skill-desc">Análises complexas, tabelas dinâmicas, Power Query e automação com fórmulas.</div>
      <div class="skill-tags">
        <span class="tag">Power Query</span><span class="tag">Pivot</span><span class="tag">PROCV/ÍNDICE</span><span class="tag">Dashboards</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon" style="background:rgba(139,92,246,0.15);">🔢</div>
      <div class="skill-name">DAX</div>
      <div class="skill-desc">Criação de medidas e KPIs avançados com inteligência de tempo e análises condicionais.</div>
      <div class="skill-tags">
        <span class="tag">CALCULATE</span><span class="tag">Time Intelligence</span><span class="tag">SWITCH</span><span class="tag">SUMX</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon" style="background:rgba(6,182,212,0.15);">🔄</div>
      <div class="skill-name">ETL & Power Query</div>
      <div class="skill-desc">Transformação, limpeza e integração de múltiplas fontes de dados.</div>
      <div class="skill-tags">
        <span class="tag">Unpivot</span><span class="tag">Merge</span><span class="tag">M Language</span><span class="tag">Limpeza</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon" style="background:rgba(236,72,153,0.15);">📈</div>
      <div class="skill-name">Análise de Negócios</div>
      <div class="skill-desc">Tradução de necessidades do negócio em soluções analíticas que geram valor.</div>
      <div class="skill-tags">
        <span class="tag">KPIs</span><span class="tag">Storytelling</span><span class="tag">Insights</span><span class="tag">Apresentações</span>
      </div>
    </div>

  </div>
</section>

<!-- ══ PROJECTS ══ -->
<section id="projetos" style="background:var(--darker);">
  <div class="section-label">Portfólio</div>
  <h2 class="section-title">Dashboards desenvolvidos</h2>
  <p class="section-sub">Projetos reais cobrindo as principais áreas de negócio.</p>

  <div class="projects-grid reveal">

    <!-- MONITORAMENTO OPERACIONAL -->
    <div class="project-card">
      <div class="project-thumb thumb-op">
        <div class="thumb-grid">
          <div class="thumb-bar" style="height:70px;background:rgba(245,158,11,0.6);animation-delay:0.1s;align-self:end;"></div>
          <div class="thumb-bar" style="height:90px;background:rgba(245,158,11,0.8);animation-delay:0.2s;align-self:end;"></div>
          <div class="thumb-bar" style="height:55px;background:rgba(245,158,11,0.5);animation-delay:0.3s;align-self:end;"></div>
        </div>
        <div class="thumb-label">Operacional</div>
      </div>
      <div class="project-body">
        <span class="project-badge badge-op">Monitoramento</span>
        <div class="project-title">Monitoramento Operacional</div>
        <div class="project-desc">Acompanhamento em tempo real de faturamento, metas por vendedor e detalhamento operacional de vendas com ranking de performance.</div>
        <div class="project-metrics">
          <div class="metric-pill">📦 <span>5</span> KPIs</div>
          <div class="metric-pill">📊 <span>3</span> visuais</div>
          <div class="metric-pill">👥 <span>5</span> vendedores</div>
        </div>
        <div class="project-footer">
          <div class="project-tools">
            <span class="tool-tag">Power BI</span><span class="tool-tag">DAX</span><span class="tool-tag">Excel</span>
          </div>
        </div>
      </div>
    </div>

    <!-- RESUMO EXECUTIVO -->
    <div class="project-card">
      <div class="project-thumb thumb-exec">
        <div class="thumb-grid">
          <div class="thumb-bar" style="height:80px;background:rgba(6,182,212,0.5);animation-delay:0.1s;align-self:end;"></div>
          <div class="thumb-bar" style="height:60px;background:rgba(6,182,212,0.7);animation-delay:0.2s;align-self:end;"></div>
          <div class="thumb-bar" style="height:95px;background:rgba(6,182,212,0.6);animation-delay:0.3s;align-self:end;"></div>
        </div>
        <div class="thumb-label">Executivo</div>
      </div>
      <div class="project-body">
        <span class="project-badge badge-exec">Estratégico</span>
        <div class="project-title">Resumo Executivo</div>
        <div class="project-desc">Visão estratégica de faturamento total, ticket médio, metas comerciais e top 10 produtos por receita com análise regional.</div>
        <div class="project-metrics">
          <div class="metric-pill">💰 <span>R$ 4,1M</span> faturamento</div>
          <div class="metric-pill">🎯 <span>19%</span> meta</div>
        </div>
        <div class="project-footer">
          <div class="project-tools">
            <span class="tool-tag">Power BI</span><span class="tool-tag">DAX</span><span class="tool-tag">Power Query</span>
          </div>
        </div>
      </div>
    </div>

    <!-- ANÁLISE COMERCIAL -->
    <div class="project-card">
      <div class="project-thumb thumb-com">
        <div class="thumb-grid">
          <div class="thumb-bar" style="height:85px;background:rgba(236,72,153,0.5);animation-delay:0.1s;align-self:end;"></div>
          <div class="thumb-bar" style="height:65px;background:rgba(236,72,153,0.7);animation-delay:0.2s;align-self:end;"></div>
          <div class="thumb-bar" style="height:75px;background:rgba(236,72,153,0.6);animation-delay:0.3s;align-self:end;"></div>
        </div>
        <div class="thumb-label">Comercial</div>
      </div>
      <div class="project-body">
        <span class="project-badge badge-com">Comercial</span>
        <div class="project-title">Análise Comercial</div>
        <div class="project-desc">Análise completa de vendas por vendedor, participação por categoria (Periféricos, Hardware, Infraestrutura) e faturamento mensal por região.</div>
        <div class="project-metrics">
          <div class="metric-pill">🏆 <span>1523</span> vendas</div>
          <div class="metric-pill">🗺️ <span>4</span> regiões</div>
        </div>
        <div class="project-footer">
          <div class="project-tools">
            <span class="tool-tag">Power BI</span><span class="tool-tag">DAX</span><span class="tool-tag">Excel</span>
          </div>
        </div>
      </div>
    </div>

    <!-- RH -->
    <div class="project-card">
      <div class="project-thumb thumb-rh">
        <div class="thumb-grid">
          <div class="thumb-bar" style="height:75px;background:rgba(59,130,246,0.5);animation-delay:0.1s;align-self:end;"></div>
          <div class="thumb-bar" style="height:90px;background:rgba(59,130,246,0.8);animation-delay:0.2s;align-self:end;"></div>
          <div class="thumb-bar" style="height:60px;background:rgba(59,130,246,0.4);animation-delay:0.3s;align-self:end;"></div>
        </div>
        <div class="thumb-label">People Analytics</div>
      </div>
      <div class="project-body">
        <span class="project-badge badge-rh">RH</span>
        <div class="project-title">People Analytics</div>
        <div class="project-desc">Dashboard de RH com headcount, turnover, absenteísmo, custo por colaborador, avaliações de desempenho e diversidade por departamento.</div>
        <div class="project-metrics">
          <div class="metric-pill">👥 <span>200</span> colaboradores</div>
          <div class="metric-pill">📋 <span>12</span> DAX</div>
        </div>
        <div class="project-footer">
          <div class="project-tools">
            <span class="tool-tag">Power BI</span><span class="tool-tag">DAX</span><span class="tool-tag">Excel</span>
          </div>
        </div>
      </div>
    </div>

    <!-- FINANCEIRO -->
    <div class="project-card">
      <div class="project-thumb thumb-fin">
        <div class="thumb-grid">
          <div class="thumb-bar" style="height:80px;background:rgba(16,185,129,0.6);animation-delay:0.1s;align-self:end;"></div>
          <div class="thumb-bar" style="height:95px;background:rgba(16,185,129,0.8);animation-delay:0.2s;align-self:end;"></div>
          <div class="thumb-bar" style="height:65px;background:rgba(16,185,129,0.5);animation-delay:0.3s;align-self:end;"></div>
        </div>
        <div class="thumb-label">Financeiro / DRE</div>
      </div>
      <div class="project-body">
        <span class="project-badge badge-fin">Financeiro</span>
        <div class="project-title">Financeiro / DRE</div>
        <div class="project-desc">DRE interativo com análise de receitas vs despesas, margem líquida mensal, real vs orçado por categoria e resultado por projeto.</div>
        <div class="project-metrics">
          <div class="metric-pill">📊 <span>600</span> lançamentos</div>
          <div class="metric-pill">💡 <span>12</span> DAX</div>
        </div>
        <div class="project-footer">
          <div class="project-tools">
            <span class="tool-tag">Power BI</span><span class="tool-tag">Power Query</span><span class="tool-tag">DAX</span>
          </div>
        </div>
      </div>
    </div>

    <!-- LOGÍSTICA -->
    <div class="project-card">
      <div class="project-thumb thumb-log">
        <div class="thumb-grid">
          <div class="thumb-bar" style="height:70px;background:rgba(139,92,246,0.5);animation-delay:0.1s;align-self:end;"></div>
          <div class="thumb-bar" style="height:85px;background:rgba(139,92,246,0.7);animation-delay:0.2s;align-self:end;"></div>
          <div class="thumb-bar" style="height:55px;background:rgba(139,92,246,0.6);animation-delay:0.3s;align-self:end;"></div>
        </div>
        <div class="thumb-label">Supply Chain</div>
      </div>
      <div class="project-body">
        <span class="project-badge badge-log">Logística</span>
        <div class="project-title">Logística / Supply Chain</div>
        <div class="project-desc">Monitoramento de OTD, lead time por modal, avarias, status de estoque por CD e mapa de pedidos por UF com análise por transportadora.</div>
        <div class="project-metrics">
          <div class="metric-pill">🚚 <span>500</span> pedidos</div>
          <div class="metric-pill">📦 <span>13</span> DAX</div>
        </div>
        <div class="project-footer">
          <div class="project-tools">
            <span class="tool-tag">Power BI</span><span class="tool-tag">DAX</span><span class="tool-tag">Mapa</span>
          </div>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ══ PROCESS ══ -->
<section id="processo">
  <div class="section-label">Metodologia</div>
  <h2 class="section-title">Como trabalho</h2>
  <p class="section-sub">Um processo estruturado do entendimento do negócio até a entrega final.</p>

  <div class="process-steps reveal">
    <div class="process-step">
      <div class="step-num">01</div>
      <div class="step-title">Entendimento</div>
      <div class="step-desc">Mapeio as necessidades do negócio e os KPIs que realmente importam para cada área.</div>
    </div>
    <div class="process-step">
      <div class="step-num">02</div>
      <div class="step-title">Dados</div>
      <div class="step-desc">Coleto, trato e modelo os dados via Power Query e SQL para garantir qualidade.</div>
    </div>
    <div class="process-step">
      <div class="step-num">03</div>
      <div class="step-title">Modelagem</div>
      <div class="step-desc">Crio o modelo estrela e as medidas DAX com inteligência de tempo e análises avançadas.</div>
    </div>
    <div class="process-step">
      <div class="step-num">04</div>
      <div class="step-title">Dashboard</div>
      <div class="step-desc">Desenvolvo os visuais com foco em clareza, hierarquia de informação e boa UX.</div>
    </div>
    <div class="process-step">
      <div class="step-num">05</div>
      <div class="step-title">Entrega</div>
      <div class="step-desc">Apresento os insights e capacito o time para explorar o dashboard de forma autônoma.</div>
    </div>
  </div>
</section>

<!-- ══ ABOUT ══ -->
<section id="sobre" style="padding:6rem 5%;">
  <div class="about-visual reveal">
    <div class="about-card-main">
      <div class="avatar">BI</div>
      <div class="about-name">Seu Nome Aqui</div>
      <div class="about-role">Analista de BI & Dados</div>
      <div class="about-card-stats">
        <div class="about-stat">
          <div class="about-stat-num">6+</div>
          <div class="about-stat-label">Dashboards</div>
        </div>
        <div class="about-stat">
          <div class="about-stat-num">3</div>
          <div class="about-stat-label">Áreas cobertas</div>
        </div>
        <div class="about-stat">
          <div class="about-stat-num">100%</div>
          <div class="about-stat-label">Dedicação</div>
        </div>
        <div class="about-stat">
          <div class="about-stat-num">SC</div>
          <div class="about-stat-label">Localização</div>
        </div>
      </div>
    </div>
    <div class="floating-badge fb1">
      <span class="fb-dot" style="background:#10b981;"></span>
      Power BI Expert
    </div>
    <div class="floating-badge fb2">
      <span class="fb-dot" style="background:#3b82f6;"></span>
      DAX & Power Query
    </div>
  </div>

  <div class="about-text reveal">
    <div class="section-label">Sobre mim</div>
    <h2 class="section-title">Transformando dados em decisões estratégicas</h2>

    <p>Sou analista de <strong>Business Intelligence</strong> especializado em construir dashboards que realmente geram valor para o negócio. Meu foco é traduzir dados complexos em histórias visuais claras e acionáveis.</p>

    <p>Trabalho com <strong>Power BI, DAX, Power Query e SQL</strong> para criar soluções completas — desde a modelagem dos dados até o dashboard final que chega na mão do gestor.</p>

    <p>Meu portfólio cobre as principais áreas de negócio: <strong>Comercial, RH, Financeiro e Logística</strong>, com bases de dados realistas e medidas DAX documentadas.</p>

    <div class="cert-list">
      <div class="cert-item">
        <div class="cert-icon" style="background:rgba(59,130,246,0.15);">🏆</div>
        <div>
          <div style="font-weight:600;font-size:0.9rem;">Power BI Desktop</div>
          <div style="font-size:0.78rem;color:var(--muted);">Modelagem, DAX e Relatórios</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon" style="background:rgba(16,185,129,0.15);">📊</div>
        <div>
          <div style="font-weight:600;font-size:0.9rem;">Excel Avançado</div>
          <div style="font-size:0.78rem;color:var(--muted);">Power Query, Tabelas Dinâmicas e Dashboards</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon" style="background:rgba(245,158,11,0.15);">🗄️</div>
        <div>
          <div style="font-weight:600;font-size:0.9rem;">SQL para Análise de Dados</div>
          <div style="font-size:0.78rem;color:var(--muted);">Consultas, Joins e Window Functions</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══ CONTACT ══ -->
<section id="contato">
  <div class="section-label" style="display:block;text-align:center;margin-bottom:0.5rem;">Contato</div>
  <h2 class="section-title" style="text-align:center;">Vamos conversar?</h2>
  <p class="section-sub" style="margin:0 auto 2.5rem;text-align:center;">Aberto a oportunidades de emprego, projetos freelance e colaborações.</p>

  <div class="contact-card reveal">
    <h3 class="contact-title">Envie uma mensagem</h3>
    <p class="contact-sub">Responderei em até 24 horas.</p>

    <form class="contact-form" onsubmit="handleSubmit(event)">
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">Nome</label>
          <input class="form-input" type="text" placeholder="Seu nome" required/>
        </div>
        <div class="form-group">
          <label class="form-label">E-mail</label>
          <input class="form-input" type="email" placeholder="seu@email.com" required/>
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Assunto</label>
        <input class="form-input" type="text" placeholder="Ex: Vaga de Analista BI, Projeto freelance..."/>
      </div>
      <div class="form-group">
        <label class="form-label">Mensagem</label>
        <textarea class="form-textarea" placeholder="Conte mais sobre a oportunidade ou projeto..." required></textarea>
      </div>
      <button type="submit" class="btn-send" id="send-btn">Enviar mensagem →</button>
    </form>

    <div class="contact-links">
      <a href="https://linkedin.com/in/seuperfil" class="contact-link" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="https://github.com/seuperfil" class="contact-link" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
        GitHub
      </a>
      <a href="mailto:seuemail@email.com" class="contact-link">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        E-mail
      </a>
    </div>
  </div>
</section>

<!-- ══ FOOTER ══ -->
<footer>
  <p>Feito com dedicação · Portfólio de Business Intelligence · <span id="year"></span></p>
</footer>

<script>
// ── YEAR
document.getElementById('year').textContent = new Date().getFullYear();

// ── SCROLL REVEAL
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry, i) => {
    if (entry.isIntersecting) {
      entry.target.style.transitionDelay = (i * 0.08) + 's';
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// ── FORM SUBMIT
function handleSubmit(e) {
  e.preventDefault();
  const btn = document.getElementById('send-btn');
  btn.textContent = 'Mensagem enviada! ✓';
  btn.style.background = 'linear-gradient(135deg,#10b981,#059669)';
  btn.disabled = true;
  setTimeout(() => {
    btn.textContent = 'Enviar mensagem →';
    btn.style.background = '';
    btn.disabled = false;
    e.target.reset();
  }, 3000);
}

// ── SMOOTH NAV
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    const target = document.querySelector(a.getAttribute('href'));
    if (target) {
      e.preventDefault();
      target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    }
  });
});
</script>
</body>
</html>
