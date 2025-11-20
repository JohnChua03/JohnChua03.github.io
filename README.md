<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>John Chua — Portfolio</title>
  <meta name="description" content="Electrical Engineering student portfolio — embedded systems, power electronics, projects, resume, and contact." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #0b0f12;
      --card: #12171c;
      --text: #e6edf3;
      --muted: #9fb0c0;
      --accent: #60a5fa;
      --accent-2: #34d399;
      --ring: rgba(96,165,250,0.35);
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0; font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji", "Segoe UI Emoji";
      background: radial-gradient(1000px 600px at 10% -10%, rgba(96,165,250,0.12), transparent),
                  radial-gradient(900px 500px at 100% 0%, rgba(52,211,153,0.10), transparent), var(--bg);
      color: var(--text);
    }
    header { position: sticky; top: 0; backdrop-filter: saturate(180%) blur(10px); background: rgba(11,15,18,0.7); border-bottom: 1px solid rgba(255,255,255,0.06); z-index: 50; }
    .container { max-width: 1100px; margin: 0 auto; padding: 0 20px; }
    .nav { display: flex; align-items: center; justify-content: space-between; padding: 14px 0; }
    .nav a { color: var(--muted); text-decoration: none; margin-left: 18px; font-weight: 600; }
    .nav a:hover { color: var(--text); }
    .brand { font-weight: 700; letter-spacing: 0.3px; color: var(--text); }

    .hero { padding: 80px 0 40px; display: grid; grid-template-columns: 1.2fr 0.8fr; gap: 32px; align-items: center; }
    .hero h1 { font-size: 42px; line-height: 1.15; margin: 0 0 12px; }
    .hero p { color: var(--muted); font-size: 18px; }
    .chips { display: flex; gap: 10px; flex-wrap: wrap; margin: 18px 0 26px; }
    .chip { padding: 6px 10px; border-radius: 999px; background: #0e1419; border: 1px solid rgba(255,255,255,0.08); color: var(--muted); font-size: 13px; }
    .cta { display: flex; gap: 12px; flex-wrap: wrap; }
    .btn { border: 1px solid rgba(255,255,255,0.12); color: var(--text); background: linear-gradient(180deg, #182029, #12171c); padding: 12px 16px; border-radius: 12px; text-decoration: none; font-weight: 600; box-shadow: 0 0 0 0 var(--ring); transition: box-shadow .2s, transform .15s; }
    .btn:hover { box-shadow: 0 0 0 6px var(--ring); transform: translateY(-1px); }
    .btn.primary { background: linear-gradient(180deg, #2a6df1, #215fd3); border-color: rgba(255,255,255,0.18); }

    .panel { background: var(--card); border: 1px solid rgba(255,255,255,0.06); border-radius: 16px; padding: 16px; }
    .kpi { display: grid; grid-template-columns: repeat(3,1fr); gap: 14px; }
    .kpi .panel { text-align: center; }
    .kpi .val { font-size: 26px; font-weight: 700; }
    .kpi .sub { color: var(--muted); font-size: 13px; }

    section { padding: 44px 0; }
    h2 { font-size: 26px; margin: 0 0 16px; }

    .grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
    .card { background: var(--card); border: 1px solid rgba(255,255,255,0.06); border-radius: 16px; padding: 18px; display: flex; flex-direction: column; gap: 12px; }
    .tag { font-size: 12px; color: var(--muted); }
    .card h3 { margin: 0; font-size: 18px; }
    .card p { margin: 0; color: var(--muted); font-size: 14px; }
    .card a { margin-top: auto; align-self: flex-start; }

    .twocol { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }

    footer { padding: 40px 0 60px; color: var(--muted); border-top: 1px solid rgba(255,255,255,0.06); margin-top: 40px; }

    @media (max-width: 900px) {
      .hero { grid-template-columns: 1fr; }
      .grid { grid-template-columns: 1fr; }
      .twocol { grid-template-columns: 1fr; }
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
        <a href="resume.pdf" target="_blank">Resume</a>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="hero">
      <div>
        <h1>Electrical Engineering student focused on embedded systems & power electronics.</h1>
        <p>Hands-on with STM32 microcontrollers, MATLAB/Simulink, and signal processing. I build real-time control systems and practical hardware–software projects.</p>
        <div class="chips">
          <span class="chip">Python</span>
          <span class="chip">C/C++</span>
          <span class="chip">STM32</span>
          <span class="chip">MATLAB/Simulink</span>
          <span class="chip">PSpice</span>
        </div>
        <div class="cta">
          <a class="btn primary" href="#projects">See Projects</a>
          <a class="btn" href="mailto:jchua100103@gmail.com">Email Me</a>
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
          <a class="btn" href="#" target="_blank">View Code</a>
        </article>
        <article class="card">
          <span class="tag">MATLAB/Simulink • Haptics</span>
          <h3>Teleoperation (Quanser Omni)</h3>
          <p>Leader–follower teleoperation with joint-space position control, trajectory record/replay, and PID tuning.</p>
          <a class="btn" href="#" target="_blank">Project Docs</a>
        </article>
        <article class="card">
          <span class="tag">STM32 • Power</span>
          <h3>DC–DC Buck Converter Control</h3>
          <p>PWM-based voltage regulation with ripple measurement and efficiency characterization across loads.</p>
          <a class="btn" href="#" target="_blank">Overview</a>
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
           GitHub: <a href="https://github.com/yourusername" target="_blank">github.com/yourusername</a><br/>
           LinkedIn: <a href="https://linkedin.com/in/yourprofile" target="_blank">linkedin.com/in/yourprofile</a></p>
      </div>
      <form class="panel" action="https://formspree.io/f/your-id" method="POST">
        <h3>Quick Message</h3>
        <input required name="name" placeholder="Your name" style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.12);background:#0e1419;color:var(--text);margin-bottom:10px;" />
        <input required type="email" name="email" placeholder="Your email" style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.12);background:#0e1419;color:var(--text);margin-bottom:10px;" />
        <textarea required name="message" placeholder="Say hello…" rows="5" style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.12);background:#0e1419;color:var(--text);margin-bottom:12px;"></textarea>
        <button class="btn primary" type="submit">Send</button>
      </form>
    </section>
  </main>

  <footer>
    <div class="container">© <span id="y"></span> John Chua • Built with HTML/CSS • Hosted on GitHub Pages</div>
  </footer>
  <script>document.getElementById('y').textContent = new Date().getFullYear()</script>
</body>
</html>
