<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>John Chua — Portfolio</title>
  <meta name="description" content="Electrical Engineering student portfolio: embedded systems, power electronics, projects, and contact." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b1020; --panel:#0f172a; --card:#111b33; --text:#e5ecff; --muted:#a6b3d6; --border:#1f2a44; --accent:#7dd3fc; --accent-2:#a78bfa; --ring:rgba(125,211,252,.25)
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial;background:radial-gradient(1200px 600px at 10% -10%, rgba(167,139,250,.12), transparent),radial-gradient(900px 500px at 110% 0%, rgba(125,211,252,.10), transparent),var(--bg);color:var(--text)}

    .container{max-width:1040px;margin:0 auto;padding:0 20px}
    header{position:sticky;top:0;z-index:40;background:rgba(11,16,32,.65);backdrop-filter:saturate(150%) blur(8px);border-bottom:1px solid rgba(255,255,255,.06)}
    .nav{display:flex;align-items:center;justify-content:space-between;padding:14px 0}
    .brand{font-weight:800;letter-spacing:.3px}
    .nav a{color:var(--muted);text-decoration:none;margin-left:18px;font-weight:600}
    .nav a:hover{color:var(--text)}

    section{padding:48px 0}
    h1{font-size:42px;line-height:1.15;margin:0 0 12px}
    h2{font-size:26px;margin:0 0 16px}
    p{line-height:1.6}

    .hero{display:grid;grid-template-columns:1.2fr .8fr;gap:28px;align-items:center;padding-top:72px}
    .lead{color:var(--muted);font-size:18px}
    .chips{display:flex;gap:10px;flex-wrap:wrap;margin:18px 0 26px}
    .chip{padding:6px 10px;border-radius:999px;background:rgba(255,255,255,.06);border:1px solid var(--border);color:var(--muted);font-size:13px}

    .panel{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:16px;padding:16px}
    .kpi{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
    .kpi .panel{text-align:center}
    .kpi .val{font-size:26px;font-weight:800}
    .kpi .sub{color:var(--muted);font-size:12px}

    .grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
    .card{background:var(--card);border:1px solid rgba(255,255,255,.07);border-radius:16px;padding:18px;display:flex;flex-direction:column;gap:10px;transform:translateZ(0);transition:transform .18s ease, box-shadow .2s}
    .card:hover{transform:translateY(-4px);box-shadow:0 10px 30px rgba(0,0,0,.35)}
    .tag{font-size:12px;color:var(--muted)}
    .card h3{margin:0;font-size:18px}
    .card p{margin:0;color:var(--muted);font-size:14px}

    .twocol{display:grid;grid-template-columns:1fr 1fr;gap:16px}

    footer{padding:44px 0 60px;color:var(--muted);border-top:1px solid rgba(255,255,255,.06);margin-top:40px}

    @keyframes fadeUp{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
    section{animation:fadeUp .6s ease both}

    @media (max-width: 900px){
      .hero{grid-template-columns:1fr}
      .grid{grid-template-columns:1fr}
      .twocol{grid-template-columns:1fr}
    }

    @media (prefers-reduced-motion: reduce){
      *{animation:none !important;transition:none !important}
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">John Chua</div>
      <nav>
        <a href="#projects">Projects</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="hero">
      <div>
        <h1>Electrical Engineering student focused on embedded systems & power electronics.</h1>
        <p class="lead">Hands-on with STM32 microcontrollers, MATLAB/Simulink, and signal processing. I build real-time control systems and practical hardware–software projects.</p>
        <div class="chips">
          <span class="chip">Python</span>
          <span class="chip">C/C++</span>
          <span class="chip">STM32</span>
          <span class="chip">MATLAB/Simulink</span>
          <span class="chip">PSpice</span>
        </div>
      </div>
      <div class="panel">
        <div class="kpi">
          <div class="panel"><div class="val">4+</div><div class="sub">Projects</div></div>
          <div class="panel"><div class="val">3 yrs</div><div class="sub">SFSU EE</div></div>
          <div class="panel"><div class="val">2025</div><div class="sub">Graduation</div></div>
        </div>
      </div>
    </section>

    <section id="projects">
      <h2>Projects</h2>
      <div class="grid">
        <article class="card">
          <span class="tag">Python • DSP</span>
          <h3>Automatic Music Transcriber</h3>
          <p>Real-time note detection using FFT and frequency analysis. Converts guitar audio into musical notes.</p>
        </article>
        <article class="card">
          <span class="tag">MATLAB/Simulink • Haptics</span>
          <h3>Teleoperation (Quanser Omni)</h3>
          <p>Leader–follower teleoperation with joint-space position control, trajectory record/replay, and PID tuning.</p>
        </article>
        <article class="card">
          <span class="tag">STM32 • Power</span>
          <h3>DC–DC Buck Converter Control</h3>
          <p>PWM-based voltage regulation with ripple measurement and efficiency characterization across loads.</p>
        </article>
      </div>
    </section>

    <section id="about" class="twocol">
      <div>
        <h2>About</h2>
        <p>I'm an EE student at SFSU interested in embedded systems, power conversion, and control. I enjoy building practical systems that blend analog sensing with real-time firmware.</p>
        <p>When I'm not in the lab, you'll find me documenting builds, tuning controllers, or exploring signal processing.</p>
      </div>
      <div class="panel">
        <h3>Skills</h3>
        <ul>
          <li>Programming: Python, C, C++</li>
          <li>Tools: MATLAB/Simulink, Keil, Xilinx, PSpice</li>
          <li>Hardware: STM32, sensor interfacing, PWM, ADC</li>
        </ul>
      </div>
    </section>

    <section id="contact" class="twocol">
      <div>
        <h2>Contact</h2>
        <p>Email: <a href="mailto:jchua100103@gmail.com">jchua100103@gmail.com</a><br/>
           GitHub: <a href="https://github.com/JohnChua03" target="_blank">github.com/JohnChua03</a><br/>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">© <span id="y"></span> John Chua • Built with HTML/CSS • Hosted on GitHub Pages</div>
  </footer>
  <script>
    document.getElementById('y').textContent = new Date().getFullYear();
  </script>
</body>
</html>
