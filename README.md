# heaven-alakraa.github.io;
cat > /mnt/user-data/outputs/heaven_alakraa_portfolio.html << 'HTMLEOF';
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Heaven Alakraa — Mechanical Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #111;
    --white: #fff;
    --gray: #666;
    --light: #f5f5f3;
    --border: #e0e0dc;
    --serif: 'DM Serif Display', Georgia, serif;
    --sans: 'DM Sans', system-ui, sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--sans);
    background: var(--white);
    color: var(--black);
    font-size: 16px;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: center;
    padding: 20px;
  }

  .nav-pill {
    display: flex;
    align-items: center;
    gap: 4px;
    background: rgba(255,255,255,0.92);
    backdrop-filter: blur(12px);
    border: 1px dashed var(--border);
    border-radius: 50px;
    padding: 6px 8px;
  }

  .nav-pill a {
    text-decoration: none;
    color: var(--black);
    font-size: 14px;
    font-weight: 400;
    padding: 6px 16px;
    border-radius: 50px;
    transition: background 0.2s;
  }

  .nav-pill a:hover { background: var(--light); }

  .nav-pill a.contact-btn {
    background: var(--black);
    color: var(--white);
    font-weight: 500;
  }

  .nav-pill a.contact-btn:hover { background: #333; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 120px 24px 80px;
  }

  .avatar {
    width: 90px;
    height: 90px;
    border-radius: 50%;
    background: var(--light);
    border: 2px solid var(--border);
    margin-bottom: 36px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--serif);
    font-size: 28px;
    color: var(--gray);
  }

  .hero h1 {
    font-family: var(--serif);
    font-size: clamp(36px, 6vw, 72px);
    font-weight: 400;
    line-height: 1.1;
    max-width: 820px;
    margin-bottom: 32px;
    letter-spacing: -0.5px;
  }

  .hero-sub {
    color: var(--gray);
    font-size: 16px;
    max-width: 520px;
    line-height: 1.7;
    margin-bottom: 12px;
  }

  .hero-btns {
    display: flex;
    gap: 12px;
    margin-top: 40px;
    flex-wrap: wrap;
    justify-content: center;
  }

  .btn {
    display: inline-block;
    text-decoration: none;
    padding: 12px 28px;
    border-radius: 50px;
    font-size: 14px;
    font-weight: 500;
    font-family: var(--sans);
    transition: all 0.2s;
    cursor: pointer;
    border: none;
  }

  .btn-dark { background: var(--black); color: var(--white); }
  .btn-dark:hover { background: #333; }
  .btn-outline { background: transparent; color: var(--black); border: 1.5px solid var(--black); }
  .btn-outline:hover { background: var(--black); color: var(--white); }

  /* SECTIONS */
  section { padding: 80px 24px; max-width: 1100px; margin: 0 auto; }

  .section-label {
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gray);
    margin-bottom: 48px;
    display: block;
  }

  .section-title {
    font-family: var(--serif);
    font-size: clamp(28px, 4vw, 48px);
    font-weight: 400;
    margin-bottom: 16px;
    line-height: 1.15;
  }

  /* PROJECTS GRID */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
  }

  .project-card {
    background: var(--white);
    padding: 40px 36px;
    cursor: pointer;
    transition: background 0.2s;
    position: relative;
    min-height: 280px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .project-card:hover { background: var(--light); }

  .project-card.wide { grid-column: span 2; }

  .project-year {
    font-size: 12px;
    color: var(--gray);
    font-weight: 400;
    letter-spacing: 0.06em;
    margin-bottom: 12px;
  }

  .project-title {
    font-family: var(--serif);
    font-size: clamp(20px, 2.5vw, 28px);
    font-weight: 400;
    line-height: 1.2;
    margin-bottom: 12px;
  }

  .project-desc {
    font-size: 13px;
    color: var(--gray);
    line-height: 1.6;
    flex: 1;
    margin-bottom: 20px;
  }

  .project-tag {
    display: inline-block;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    border: 1px solid var(--border);
    border-radius: 50px;
    padding: 4px 12px;
    color: var(--gray);
    margin-right: 6px;
    margin-bottom: 6px;
  }

  .project-arrow {
    position: absolute;
    top: 36px;
    right: 36px;
    font-size: 18px;
    color: var(--border);
    transition: color 0.2s, transform 0.2s;
  }

  .project-card:hover .project-arrow {
    color: var(--black);
    transform: translate(3px, -3px);
  }

  /* CAN OPENER INTERACTIVE SECTION */
  .can-opener-section {
    padding: 80px 24px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .exploded-container {
    margin-top: 48px;
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    background: var(--light);
    position: relative;
  }

  .exploded-controls {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px 28px;
    background: var(--white);
    border-bottom: 1px solid var(--border);
    flex-wrap: wrap;
  }

  .exploded-controls label {
    font-size: 13px;
    color: var(--gray);
    font-weight: 500;
  }

  .slider-wrapper {
    display: flex;
    align-items: center;
    gap: 12px;
    flex: 1;
    min-width: 200px;
  }

  .exploded-controls input[type=range] {
    flex: 1;
    accent-color: var(--black);
    cursor: pointer;
  }

  .slider-val {
    font-size: 13px;
    font-weight: 500;
    min-width: 50px;
  }

  #reset-btn {
    font-size: 12px;
    font-weight: 500;
    padding: 8px 16px;
    border-radius: 50px;
    border: 1.5px solid var(--black);
    background: transparent;
    cursor: pointer;
    font-family: var(--sans);
    color: var(--black);
    transition: all 0.2s;
    white-space: nowrap;
  }
  #reset-btn:hover { background: var(--black); color: var(--white); }

  #can-canvas {
    display: block;
    width: 100%;
    height: 520px;
    cursor: grab;
  }
  #can-canvas:active { cursor: grabbing; }

  .part-tooltip {
    position: absolute;
    background: var(--black);
    color: var(--white);
    font-size: 12px;
    font-weight: 500;
    padding: 6px 12px;
    border-radius: 8px;
    pointer-events: none;
    opacity: 0;
    transition: opacity 0.2s;
    white-space: nowrap;
    z-index: 10;
  }

  .part-labels {
    padding: 20px 28px;
    background: var(--white);
    border-top: 1px solid var(--border);
    display: flex;
    gap: 24px;
    flex-wrap: wrap;
  }

  .part-label-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    color: var(--gray);
    cursor: pointer;
    transition: color 0.2s;
  }
  .part-label-item:hover { color: var(--black); }
  .part-label-item.active { color: var(--black); font-weight: 500; }

  .part-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* SKILLS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 2px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    margin-top: 48px;
  }

  .skill-cell {
    background: var(--white);
    padding: 28px 28px;
  }

  .skill-category {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
    margin-bottom: 12px;
  }

  .skill-items {
    font-family: var(--serif);
    font-size: 16px;
    line-height: 1.8;
    color: var(--black);
  }

  /* ABOUT */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
    margin-top: 48px;
  }

  .about-text p {
    font-size: 16px;
    color: var(--gray);
    line-height: 1.8;
    margin-bottom: 20px;
  }

  .exp-item {
    border-bottom: 1px solid var(--border);
    padding: 20px 0;
  }

  .exp-item:first-child { border-top: 1px solid var(--border); }

  .exp-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 6px;
    gap: 12px;
  }

  .exp-org { font-weight: 500; font-size: 14px; }
  .exp-role { font-size: 13px; color: var(--gray); }
  .exp-date { font-size: 12px; color: var(--gray); white-space: nowrap; }

  /* CONTACT */
  .contact-section {
    padding: 80px 24px 120px;
    text-align: center;
  }

  .contact-inner {
    max-width: 600px;
    margin: 0 auto;
  }

  .contact-links {
    display: flex;
    gap: 12px;
    justify-content: center;
    margin-top: 40px;
    flex-wrap: wrap;
  }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 13px;
    color: var(--gray);
    max-width: 1100px;
    margin: 0 auto;
    flex-wrap: wrap;
    gap: 12px;
  }

  footer a { color: var(--gray); text-decoration: none; }
  footer a:hover { color: var(--black); }

  .divider { border: none; border-top: 1px solid var(--border); }

  /* Modal */
  .modal-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.5);
    z-index: 200;
    align-items: center;
    justify-content: center;
    padding: 24px;
  }
  .modal-overlay.open { display: flex; }

  .modal {
    background: var(--white);
    border-radius: 20px;
    max-width: 680px;
    width: 100%;
    max-height: 80vh;
    overflow-y: auto;
    padding: 48px;
    position: relative;
  }

  .modal-close {
    position: absolute;
    top: 20px; right: 20px;
    background: var(--light);
    border: none;
    border-radius: 50%;
    width: 36px; height: 36px;
    font-size: 18px;
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    font-family: var(--sans);
    color: var(--black);
  }
  .modal-close:hover { background: var(--border); }

  .modal-year { font-size: 13px; color: var(--gray); margin-bottom: 12px; }
  .modal-title { font-family: var(--serif); font-size: 28px; font-weight: 400; margin-bottom: 20px; }
  .modal-body { font-size: 15px; color: var(--gray); line-height: 1.8; }
  .modal-body ul { padding-left: 20px; margin-top: 12px; }
  .modal-body li { margin-bottom: 8px; }

  @media (max-width: 700px) {
    .projects-grid { grid-template-columns: 1fr; }
    .project-card.wide { grid-column: span 1; }
    .about-grid { grid-template-columns: 1fr; gap: 40px; }
    .modal { padding: 32px 24px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-pill">
    <a href="#projects">Projects</a>
    <a href="#about">About</a>
    <a href="#contact" class="contact-btn">Contact</a>
  </div>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="avatar">H</div>
  <h1>Mechanical engineer passionate about solving multidisciplinary problems through rigorous engineering problem solving and innovative design </h1>
  <p class="hero-sub">Sc.B. candidate in Mechanical Engineering at Brown University, Providence, RI </p>
  <p class="hero-sub"> American Society of Biomechanics, 2026 Recipient of the Carlo De Luca B-SURE Award</p>
  <div class="hero-btns">
    <a href="https://www.linkedin.com/in/heaven-alakraa-b09866325" class="btn btn-dark" target="_blank">LinkedIn ↗</a>
    <a href="https://docs.google.com/document/d/1A6ctqug-dhaARP5cIEn7oTQ4K7nVh9y6/edit?usp=sharing&ouid=105157443692331014401&rtpof=true&sd=true" class="btn btn-outline">Resume ↗</a>
  </div>
</div>

<hr class="divider" style="max-width:1100px; margin: 0 auto;">

<!-- ABOUT -->
<section id="about">
  <span class="section-label">About</span>
  <div class="about-grid">
    <div class="about-text">
      <h2 class="section-title" style="margin-bottom: 24px;">Hi, my name is Heaven.</h2>
      <p>I'm a mechanical engineering student at Brown University eager to solve problems across multiple fields, spanning from biomedical devices to infrastructure, from robotics to automotive and aeroscpace.</p>
      <p>Outside of classes, I've worked across research labs, biotech startups, and teaching roles, building projects that push me to apply theory to physical prototypes. Besides that, you'll find me at the Brown Design Workshop working with the Brown Formula Racing team on the cooling subsystem or enjoying the outdoors (either hiking on rocky mountains or skiing down icy summits) </p>

    <div class="about-exp">
      <div style="font-size: 12px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: var(--gray); margin-bottom: 20px;">Experience</div>

      <div class="exp-item">
        <div class="exp-top">
          <div>
            <div class="exp-org">RIH Bioengineering Lab</div>
            <div class="exp-role">Engineering Research Intern</div>
          </div>
          <div class="exp-date">May 2026–</div>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-top">
          <div>
            <div class="exp-org">Lilac Biosciences</div>
            <div class="exp-role">Product Design Intern</div>
          </div>
          <div class="exp-date">Jan 2025–</div>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-top">
          <div>
            <div class="exp-org">Tripathi Lab, Brown</div>
            <div class="exp-role">Research Assistant</div>
          </div>
          <div class="exp-date">Jan–Sep 2025</div>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-top">
          <div>
            <div class="exp-org">Brown Engineering</div>
            <div class="exp-role">Teaching Fellow</div>
          </div>
          <div class="exp-date">Aug–Jan 2026</div>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-top">
          <div>
            <div class="exp-org">Brown FSAE</div>
            <div class="exp-role">Cooling &amp; Radiator Testing Engineer</div>
          </div>
          <div class="exp-date">Sep 2025–</div>
        </div>
      </div>

      <div style="margin-top: 24px;">
        <div style="font-size: 12px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: var(--gray); margin-bottom: 12px;">Education</div>
        <div class="exp-org">Brown University</div>
        <div class="exp-role">Sc.B Mechanical Engineering · GPA 3.96</div>
        <div class="exp-date" style="margin-top: 4px;">2024–2028</div>
      </div>
    </div>
  </div>
</section>

<hr class="divider" style="max-width:1100px; margin: 0 auto;">

<!-- PROJECTS -->
<section id="projects">
  <span class="section-label">Work</span>
  <h2 class="section-title">Selected Projects</h2>
  <p style="color: var(--gray); margin-bottom: 48px; font-size: 15px;">Click any project to learn more.</p>

  <div class="projects-grid">

    <!-- Can Opener - wide -->
    <div class="project-card wide" onclick="openModal('canopener')">
      <span class="project-arrow">↗</span>
      <div>
        <div class="project-year">2024–2025</div>
        <div class="project-title">Can Opener Mechanical Design &amp; Analysis</div>
        <div class="project-desc">Fully constrained multi-component assembly in SolidWorks — complete with FEA, motion analysis, gear mechanics, and a full engineering drawing package. Scroll down to explore the interactive exploded view.</div>
      </div>
      <div>
        <span class="project-tag">SolidWorks</span>
        <span class="project-tag">FEA</span>
        <span class="project-tag">Motion Analysis</span>
        <span class="project-tag">Engineering Drawings</span>
      </div>
    </div>

    <!-- Cantilever Beam -->
    <div class="project-card" onclick="openModal('beam')">
      <span class="project-arrow">↗</span>
      <div>
        <div class="project-year">2024</div>
        <div class="project-title">Cantilever Beam Deflection Scale</div>
        <div class="project-desc">Designed and fabricated a mechanical scale using Euler-Bernoulli beam theory, optimized in MATLAB. Achieved &lt;10% error in mass prediction.</div>
      </div>
      <div>
        <span class="project-tag">MATLAB</span>
        <span class="project-tag">Fabrication</span>
        <span class="project-tag">BDW</span>
      </div>
    </div>

    <!-- Vertebral Body -->
    <div class="project-card" onclick="openModal('vertebral')">
      <span class="project-arrow">↗</span>
      <div>
        <div class="project-year">2025</div>
        <div class="project-title">Next-Gen Material Selection — Vertebral Body Replacement</div>
        <div class="project-desc">Screened 4,395 materials in Ansys Granta Edupack. Identified Polyetherimide (PEI) as a leading candidate for future clinical VBR applications.</div>
      </div>
      <div>
        <span class="project-tag">Ansys Granta</span>
        <span class="project-tag">FEA</span>
        <span class="project-tag">Biomedical</span>
      </div>
    </div>

    <!-- Heart Rate Sensor -->
    <div class="project-card" onclick="openModal('heartrate')">
      <span class="project-arrow">↗</span>
      <div>
        <div class="project-year">2025</div>
        <div class="project-title">Heart Rate Sensor &amp; F1 Safety Gear Testing</div>
        <div class="project-desc">Prototyped a real-time heart rate monitor with MAX30102 + Arduino OLED. Analyzed BPM data in MATLAB across simulated F1 safety gear conditions.</div>
      </div>
      <div>
        <span class="project-tag">Arduino</span>
        <span class="project-tag">MATLAB</span>
        <span class="project-tag">Prototyping</span>
      </div>
    </div>

    <!-- RNA Tube -->
    <div class="project-card" onclick="openModal('rna')">
      <span class="project-arrow">↗</span>
      <div>
        <div class="project-year">2025 – Present</div>
        <div class="project-title">RNA Purification Tube Redesign</div>
        <div class="project-desc">Redesigned tube geometry at Lilac Biosciences to replace centrifuge-dependent separation with integrated filtration. Iterating prototypes via 3D printing.</div>
      </div>
      <div>
        <span class="project-tag">SolidWorks</span>
        <span class="project-tag">3D Printing</span>
        <span class="project-tag">Biotech</span>
      </div>
    </div>

    <!-- Pendulum Testing -->
    <div class="project-card" onclick="openModal('pendulum')">
      <span class="project-arrow">↗</span>
      <div>
        <div class="project-year">2026 – Present</div>
        <div class="project-title">Pendulum Friction Testing Apparatus</div>
        <div class="project-desc">Designing active and passive pendulum apparatus in SolidWorks to measure coefficients of friction in biological joints at Rhode Island Hospital's Orthopaedic Foundation.</div>
      </div>
      <div>
        <span class="project-tag">SolidWorks</span>
        <span class="project-tag">Tribology</span>
        <span class="project-tag">Research</span>
      </div>
    </div>

  </div>
</section>

<hr class="divider" style="max-width:1100px; margin: 0 auto;">

<!-- CAN OPENER EXPLODED VIEW -->
<div class="can-opener-section" id="canopener-section">
  <span class="section-label">Interactive</span>
  <h2 class="section-title">Can Opener — Exploded View</h2>
  <p style="color: var(--gray); margin-bottom: 0; font-size: 15px; max-width: 560px;">
    Drag the slider to explode the assembly. Hover over parts to identify them. Drag to orbit. This is an interactive recreation of the SolidWorks assembly designed for Computer Aided Visualization and Design.
  </p>

  <div class="exploded-container">
    <div class="exploded-controls">
      <label>Explode</label>
      <div class="slider-wrapper">
        <input type="range" id="explode-slider" min="0" max="100" value="0" step="1">
        <span class="slider-val" id="explode-val">0%</span>
      </div>
      <button id="reset-btn">Reset view</button>
      <button id="animate-btn" class="btn btn-dark" style="font-size:12px; padding:8px 18px; border-radius:50px;">Auto-explode ▶</button>
    </div>

    <div style="position: relative;">
      <canvas id="can-canvas"></canvas>
      <div class="part-tooltip" id="part-tooltip"></div>
    </div>

    <div class="part-labels" id="part-labels"></div>
  </div>
</div>

<hr class="divider" style="max-width:1100px; margin: 0 auto;">

<!-- SKILLS -->
<section>
  <span class="section-label">Capabilities</span>
  <h2 class="section-title">Skills &amp; Tools</h2>
  <div class="skills-grid">
    <div class="skill-cell">
      <div class="skill-category">CAD &amp; Design</div>
      <div class="skill-items">SolidWorks<br>Fusion 360<br>Onshape</div>
    </div>
    <div class="skill-cell">
      <div class="skill-category">Analysis</div>
      <div class="skill-items">FEA (Ansys)<br>MATLAB<br>COMSOL</div>
    </div>
    <div class="skill-cell">
      <div class="skill-category">Fabrication</div>
      <div class="skill-items">3D Printing<br>Rapid Prototyping<br>Woodworking</div>
    </div>
    <div class="skill-cell">
      <div class="skill-category">Programming</div>
      <div class="skill-items">MATLAB<br>Python<br>Arduino</div>
    </div>
    <div class="skill-cell">
      <div class="skill-category">Biomedical</div>
      <div class="skill-items">qPCR, ELISA<br>DNA Methylation<br>NanoMosaic Tessie</div>
    </div>
    <div class="skill-cell">
      <div class="skill-category">Engineering</div>
      <div class="skill-items">Drawings<br>Simulations<br>Manufacturing</div>
    </div>
  </div>
</section>

<hr class="divider" style="max-width:1100px; margin: 0 auto;">

<!-- CONTACT -->
<div class="contact-section" id="contact">
  <div class="contact-inner">
    <span class="section-label" style="display: block; margin-bottom: 16px;">Get in touch</span>
    <h2 class="section-title">Let's talk.</h2>
    <p style="color: var(--gray); margin-top: 16px; font-size: 15px; line-height: 1.8;">Whether it's a research collaboration, internship opportunity, or just a conversation about engineering — I'd love to hear from you.</p>
    <div class="contact-links">
      <a href="mailto:heaven_alakraa@brown.edu" class="btn btn-dark">Email me ↗</a>
      <a href="https://www.linkedin.com/in/heaven-alakraa-b09866325" class="btn btn-outline" target="_blank">LinkedIn ↗</a>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <span>© Heaven Alakraa — 2026</span>
  <div style="display: flex; gap: 20px;">
    <a href="#projects">Projects</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </div>
</footer>

<!-- PROJECT MODALS -->
<div class="modal-overlay" id="modal-overlay" onclick="closeModal(event)">
  <div class="modal" id="modal-content">
    <button class="modal-close" onclick="closeModalDirect()">✕</button>
    <div id="modal-body-content"></div>
  </div>
</div>

<script>
// =========================================================
// INTERACTIVE EXPLODED VIEW — Canvas-based 3D-ish renderer
// =========================================================
const canvas = document.getElementById('can-canvas');
const ctx = canvas.getContext('2d');

function resize() {
  const rect = canvas.parentElement.getBoundingClientRect();
  canvas.width = rect.width * window.devicePixelRatio;
  canvas.height = 520 * window.devicePixelRatio;
  canvas.style.width = rect.width + 'px';
  canvas.style.height = '520px';
  ctx.scale(window.devicePixelRatio, window.devicePixelRatio);
}
resize();
window.addEventListener('resize', () => { resize(); draw(); });

// Parts definition — each part has a home position and explode offset
// We simulate a simple isometric-ish projection with orbit control
let rotX = -0.35, rotY = 0.55;
let isDragging = false, lastX, lastY;
let explode = 0;
let hoveredPart = null;
let animating = false;
let animDir = 1;
let animId = null;

const W = () => canvas.offsetWidth;
const H = () => canvas.offsetHeight;

const parts = [
  {
    id: 'handle-body',
    name: 'Handle Body',
    color: '#d4a96a',
    shadowColor: '#a07840',
    // base shape: main rectangular handle
    base: { x: 0, y: 0, z: 0 },
    explodeDir: { x: 0, y: 0, z: 0 },
    shapes: [
      { type: 'rect', x: -80, y: -10, w: 160, h: 20, depth: 14 },
      { type: 'rect', x: -80, y: -10, w: 20, h: 20, depth: 40 },
    ],
    label: 'Ergonomic handle body — ABS plastic',
  },
  {
    id: 'second-arm',
    name: 'Second Arm',
    color: '#c8a060',
    shadowColor: '#96783a',
    base: { x: 60, y: 0, z: 0 },
    explodeDir: { x: 1.2, y: 0, z: 0 },
    shapes: [
      { type: 'rect', x: -70, y: -10, w: 140, h: 20, depth: 12 },
    ],
    label: 'Second handle arm — steel',
  },
  {
    id: 'drive-gear',
    name: 'Drive Gear',
    color: '#bbb',
    shadowColor: '#888',
    base: { x: 0, y: 0, z: 20 },
    explodeDir: { x: 0, y: 0.8, z: 1.2 },
    shapes: [
      { type: 'gear', cx: 0, cy: 0, r: 30, teeth: 18, depth: 10 },
    ],
    label: 'Drive gear — stainless steel',
  },
  {
    id: 'feed-gear',
    name: 'Feed Gear',
    color: '#aaa',
    shadowColor: '#777',
    base: { x: 30, y: 0, z: 20 },
    explodeDir: { x: 0.6, y: 1, z: 1.2 },
    shapes: [
      { type: 'gear', cx: 0, cy: 0, r: 22, teeth: 14, depth: 8 },
    ],
    label: 'Feed gear — stainless steel',
  },
  {
    id: 'cutting-wheel',
    name: 'Cutting Wheel',
    color: '#e8e8e8',
    shadowColor: '#aaa',
    base: { x: -10, y: 20, z: 16 },
    explodeDir: { x: -0.5, y: 1.5, z: 0.8 },
    shapes: [
      { type: 'circle', cx: 0, cy: 0, r: 16, depth: 5 },
    ],
    label: 'Cutting wheel — hardened steel',
  },
  {
    id: 'drive-screw',
    name: 'Drive Screw',
    color: '#c0c0c0',
    shadowColor: '#909090',
    base: { x: 0, y: -10, z: 30 },
    explodeDir: { x: 0.2, y: -1.2, z: 1.8 },
    shapes: [
      { type: 'cylinder', cx: 0, cy: 0, r: 8, h: 30, depth: 8 },
    ],
    label: 'Drive screw — M5 stainless',
  },
  {
    id: 'feed-screw',
    name: 'Feed Screw',
    color: '#b8b8b8',
    shadowColor: '#888',
    base: { x: 30, y: -10, z: 30 },
    explodeDir: { x: 0.8, y: -1, z: 1.8 },
    shapes: [
      { type: 'cylinder', cx: 0, cy: 0, r: 6, h: 24, depth: 6 },
    ],
    label: 'Feed screw — M4 stainless',
  },
  {
    id: 'knob',
    name: 'Turning Knob',
    color: '#d4a96a',
    shadowColor: '#a07840',
    base: { x: 0, y: 0, z: 50 },
    explodeDir: { x: 0, y: -0.5, z: 2.5 },
    shapes: [
      { type: 'knob', cx: 0, cy: 0, r: 20, depth: 16 },
    ],
    label: 'Turning knob — brass',
  },
  {
    id: 'frame',
    name: 'Frame / Body Plate',
    color: '#e0e0e0',
    shadowColor: '#b0b0b0',
    base: { x: 0, y: 0, z: 0 },
    explodeDir: { x: 0, y: 0, z: -1.2 },
    shapes: [
      { type: 'rect', x: -55, y: -40, w: 110, h: 80, depth: 6 },
    ],
    label: 'Main frame / body plate — stainless steel',
  },
];

const PART_COLORS_LEGEND = ['#d4a96a','#c8a060','#bbb','#aaa','#e8e8e8','#c0c0c0','#b8b8b8','#d4a96a','#e0e0e0'];

// Iso projection
function project(x, y, z) {
  const cosX = Math.cos(rotX), sinX = Math.sin(rotX);
  const cosY = Math.cos(rotY), sinY = Math.sin(rotY);
  // rotate around Y
  const x1 = x * cosY + z * sinY;
  const z1 = -x * sinY + z * cosY;
  // rotate around X
  const y2 = y * cosX - z1 * sinX;
  const z2 = y * sinX + z1 * cosX;
  return {
    px: x1,
    py: y2,
    pz: z2
  };
}

function draw() {
  const cw = W(), ch = H();
  ctx.clearRect(0, 0, cw, ch);

  // background
  ctx.fillStyle = '#f5f5f3';
  ctx.fillRect(0, 0, cw, ch);

  // center offset
  const cx = cw / 2, cy = ch / 2;
  const scale = Math.min(cw, ch) / 380;

  // Sort parts back-to-front by projected z
  const sorted = parts.map((p, i) => {
    const ex = p.base.x + p.explodeDir.x * explode * 1.2;
    const ey = p.base.y + p.explodeDir.y * explode * 1.2;
    const ez = p.base.z + p.explodeDir.z * explode * 1.2;
    const proj = project(ex, ey, ez);
    return { part: p, px: proj.px, py: proj.py, pz: proj.pz, origIdx: i };
  }).sort((a, b) => a.pz - b.pz);

  sorted.forEach(({ part, px, py }) => {
    const isHovered = hoveredPart === part.id;
    drawPart(part, cx + px * scale, cy + py * scale, scale, isHovered);
  });

  // draw dotted assembly lines when exploding
  if (explode > 5) {
    ctx.save();
    ctx.setLineDash([3, 5]);
    ctx.strokeStyle = 'rgba(100,100,100,0.2)';
    ctx.lineWidth = 1;

    // Connect frame to gears
    const frameProj = project(parts[8].base.x + parts[8].explodeDir.x * explode * 1.2,
                              parts[8].base.y + parts[8].explodeDir.y * explode * 1.2,
                              parts[8].base.z + parts[8].explodeDir.z * explode * 1.2);
    const driveGearProj = project(parts[2].base.x + parts[2].explodeDir.x * explode * 1.2,
                                   parts[2].base.y + parts[2].explodeDir.y * explode * 1.2,
                                   parts[2].base.z + parts[2].explodeDir.z * explode * 1.2);
    ctx.beginPath();
    ctx.moveTo(cx + frameProj.px * scale, cy + frameProj.py * scale);
    ctx.lineTo(cx + driveGearProj.px * scale, cy + driveGearProj.py * scale);
    ctx.stroke();
    ctx.restore();
  }
}

function drawPart(part, cx, cy, scale, isHovered) {
  const alpha = isHovered ? 1 : 0.92;
  ctx.globalAlpha = alpha;

  part.shapes.forEach(shape => {
    if (shape.type === 'rect') {
      drawBox(ctx, cx + shape.x * scale, cy + shape.y * scale, shape.w * scale, shape.h * scale, shape.depth * scale * 0.5, part.color, part.shadowColor, isHovered);
    } else if (shape.type === 'gear') {
      drawGear(ctx, cx + shape.cx * scale, cy + shape.cy * scale, shape.r * scale, shape.teeth, shape.depth * scale * 0.4, part.color, part.shadowColor, isHovered);
    } else if (shape.type === 'circle') {
      drawDisc(ctx, cx + shape.cx * scale, cy + shape.cy * scale, shape.r * scale, shape.depth * scale * 0.4, part.color, part.shadowColor, isHovered);
    } else if (shape.type === 'cylinder') {
      drawCylinder(ctx, cx + shape.cx * scale, cy + shape.cy * scale, shape.r * scale, shape.h * scale, shape.depth * scale * 0.4, part.color, part.shadowColor, isHovered);
    } else if (shape.type === 'knob') {
      drawKnob(ctx, cx + shape.cx * scale, cy + shape.cy * scale, shape.r * scale, shape.depth * scale * 0.5, part.color, part.shadowColor, isHovered);
    }
  });

  ctx.globalAlpha = 1;
}

function drawBox(ctx, x, y, w, h, d, fill, shadow, hl) {
  const ox = d * 0.6, oy = -d * 0.4;
  ctx.fillStyle = hl ? lighten(fill, 0.15) : fill;
  ctx.strokeStyle = 'rgba(0,0,0,0.12)';
  ctx.lineWidth = 0.7;

  // top face
  ctx.beginPath();
  ctx.moveTo(x, y);
  ctx.lineTo(x + w, y);
  ctx.lineTo(x + w + ox, y + oy);
  ctx.lineTo(x + ox, y + oy);
  ctx.closePath();
  ctx.fillStyle = lighten(fill, 0.2);
  ctx.fill();
  ctx.stroke();

  // front face
  ctx.beginPath();
  ctx.rect(x, y, w, h);
  ctx.fillStyle = hl ? lighten(fill, 0.15) : fill;
  ctx.fill();
  ctx.stroke();

  // right face
  ctx.beginPath();
  ctx.moveTo(x + w, y);
  ctx.lineTo(x + w + ox, y + oy);
  ctx.lineTo(x + w + ox, y + h + oy);
  ctx.lineTo(x + w, y + h);
  ctx.closePath();
  ctx.fillStyle = shadow;
  ctx.fill();
  ctx.stroke();
}

function drawGear(ctx, cx, cy, r, teeth, d, fill, shadow, hl) {
  const toothH = r * 0.22;
  const toothW = (2 * Math.PI / teeth) * 0.45;
  const ox = d * 0.5, oy = -d * 0.3;

  // side shadow
  ctx.beginPath();
  for (let i = 0; i < teeth; i++) {
    const a = (i / teeth) * Math.PI * 2;
    const a1 = a - toothW / 2, a2 = a + toothW / 2;
    const or = r + toothH;
    ctx.moveTo(cx + Math.cos(a1) * r + ox, cy + Math.sin(a1) * r + oy);
    ctx.lineTo(cx + Math.cos(a1) * or + ox, cy + Math.sin(a1) * or + oy);
    ctx.lineTo(cx + Math.cos(a2) * or + ox, cy + Math.sin(a2) * or + oy);
    ctx.lineTo(cx + Math.cos(a2) * r + ox, cy + Math.sin(a2) * r + oy);
  }
  ctx.fillStyle = shadow;
  ctx.fill();

  // front gear
  ctx.beginPath();
  for (let i = 0; i < teeth; i++) {
    const a = (i / teeth) * Math.PI * 2;
    const a1 = a - toothW / 2, a2 = a + toothW / 2;
    const or = r + toothH;
    if (i === 0) ctx.moveTo(cx + Math.cos(a1) * r, cy + Math.sin(a1) * r);
    else ctx.lineTo(cx + Math.cos(a1) * r, cy + Math.sin(a1) * r);
    ctx.lineTo(cx + Math.cos(a1) * or, cy + Math.sin(a1) * or);
    ctx.lineTo(cx + Math.cos(a2) * or, cy + Math.sin(a2) * or);
    ctx.lineTo(cx + Math.cos(a2) * r, cy + Math.sin(a2) * r);
  }
  ctx.closePath();
  ctx.fillStyle = hl ? lighten(fill, 0.2) : fill;
  ctx.strokeStyle = 'rgba(0,0,0,0.15)';
  ctx.lineWidth = 0.7;
  ctx.fill();
  ctx.stroke();

  // center hole
  ctx.beginPath();
  ctx.arc(cx, cy, r * 0.22, 0, Math.PI * 2);
  ctx.fillStyle = '#f5f5f3';
  ctx.fill();
}

function drawDisc(ctx, cx, cy, r, d, fill, shadow, hl) {
  const ox = d * 0.5, oy = -d * 0.3;
  // rim
  ctx.beginPath();
  ctx.ellipse(cx + ox, cy + oy, r, r * 0.3, 0, 0, Math.PI * 2);
  ctx.fillStyle = shadow;
  ctx.fill();

  ctx.beginPath();
  ctx.arc(cx, cy, r, 0, Math.PI * 2);
  ctx.fillStyle = hl ? lighten(fill, 0.2) : fill;
  ctx.strokeStyle = 'rgba(0,0,0,0.15)';
  ctx.lineWidth = 0.7;
  ctx.fill();
  ctx.stroke();

  // serrated edge suggestion
  ctx.strokeStyle = 'rgba(0,0,0,0.1)';
  for (let i = 0; i < 24; i++) {
    const a = (i / 24) * Math.PI * 2;
    ctx.beginPath();
    ctx.moveTo(cx + Math.cos(a) * (r * 0.85), cy + Math.sin(a) * (r * 0.85));
    ctx.lineTo(cx + Math.cos(a) * r, cy + Math.sin(a) * r);
    ctx.stroke();
  }
}

function drawCylinder(ctx, cx, cy, r, h, d, fill, shadow, hl) {
  const ox = d * 0.5, oy = -d * 0.3;
  // side
  ctx.fillStyle = shadow;
  ctx.beginPath();
  ctx.moveTo(cx + r, cy);
  ctx.lineTo(cx + r + ox, cy + oy);
  ctx.lineTo(cx - r + ox, cy + oy);
  ctx.lineTo(cx - r, cy);
  ctx.closePath();
  ctx.fill();

  // body
  ctx.fillStyle = hl ? lighten(fill, 0.15) : fill;
  ctx.strokeStyle = 'rgba(0,0,0,0.12)';
  ctx.lineWidth = 0.7;
  ctx.beginPath();
  ctx.ellipse(cx, cy, r, r * 0.25, 0, 0, Math.PI);
  ctx.lineTo(cx - r, cy + h);
  ctx.ellipse(cx, cy + h, r, r * 0.25, 0, Math.PI, 0);
  ctx.closePath();
  ctx.fill();
  ctx.stroke();

  // top cap
  ctx.fillStyle = lighten(fill, 0.25);
  ctx.beginPath();
  ctx.ellipse(cx, cy, r, r * 0.25, 0, 0, Math.PI * 2);
  ctx.fill();
  ctx.stroke();

  // screw head cross
  ctx.strokeStyle = 'rgba(0,0,0,0.2)';
  ctx.lineWidth = 1;
  ctx.beginPath();
  ctx.moveTo(cx - r * 0.5, cy);
  ctx.lineTo(cx + r * 0.5, cy);
  ctx.moveTo(cx, cy - r * 0.12);
  ctx.lineTo(cx, cy + r * 0.12);
  ctx.stroke();
}

function drawKnob(ctx, cx, cy, r, d, fill, shadow, hl) {
  const ox = d * 0.5, oy = -d * 0.3;
  // side
  ctx.fillStyle = shadow;
  ctx.beginPath();
  ctx.arc(cx + ox, cy + oy, r, 0, Math.PI * 2);
  ctx.fill();

  // knurling lines suggestion
  for (let i = 0; i < 12; i++) {
    const a = (i / 12) * Math.PI * 2;
    ctx.strokeStyle = 'rgba(0,0,0,0.08)';
    ctx.lineWidth = 1;
    ctx.beginPath();
    ctx.moveTo(cx + Math.cos(a) * r * 0.6, cy + Math.sin(a) * r * 0.6);
    ctx.lineTo(cx + Math.cos(a) * r, cy + Math.sin(a) * r);
    ctx.stroke();
  }

  ctx.fillStyle = hl ? lighten(fill, 0.2) : fill;
  ctx.strokeStyle = 'rgba(0,0,0,0.12)';
  ctx.lineWidth = 0.8;
  ctx.beginPath();
  ctx.arc(cx, cy, r, 0, Math.PI * 2);
  ctx.fill();
  ctx.stroke();

  // inner ring
  ctx.strokeStyle = 'rgba(0,0,0,0.15)';
  ctx.lineWidth = 1;
  ctx.beginPath();
  ctx.arc(cx, cy, r * 0.55, 0, Math.PI * 2);
  ctx.stroke();
}

function lighten(hex, amt) {
  const r = parseInt(hex.slice(1,3),16), g = parseInt(hex.slice(3,5),16), b = parseInt(hex.slice(5,7),16);
  const lr = Math.min(255, Math.round(r + (255 - r) * amt));
  const lg = Math.min(255, Math.round(g + (255 - g) * amt));
  const lb = Math.min(255, Math.round(b + (255 - b) * amt));
  return `rgb(${lr},${lg},${lb})`;
}

// Orbit drag
canvas.addEventListener('mousedown', e => {
  isDragging = true;
  lastX = e.clientX;
  lastY = e.clientY;
  canvas.style.cursor = 'grabbing';
});

window.addEventListener('mouseup', () => {
  isDragging = false;
  canvas.style.cursor = 'grab';
});

window.addEventListener('mousemove', e => {
  if (isDragging) {
    const dx = e.clientX - lastX;
    const dy = e.clientY - lastY;
    rotY += dx * 0.007;
    rotX += dy * 0.007;
    lastX = e.clientX;
    lastY = e.clientY;
    draw();
    return;
  }

  // Hover detection
  const rect = canvas.getBoundingClientRect();
  const mx = e.clientX - rect.left;
  const my = e.clientY - rect.top;
  const scale = Math.min(W(), H()) / 380;
  const cxC = W() / 2, cyC = H() / 2;

  let found = null;
  parts.forEach(part => {
    const ex = part.base.x + part.explodeDir.x * explode * 1.2;
    const ey = part.base.y + part.explodeDir.y * explode * 1.2;
    const ez = part.base.z + part.explodeDir.z * explode * 1.2;
    const proj = project(ex, ey, ez);
    const px = cxC + proj.px * scale;
    const py = cyC + proj.py * scale;
    const dist = Math.sqrt((mx - px) ** 2 + (my - py) ** 2);
    if (dist < 55) found = part;
  });

  const tooltip = document.getElementById('part-tooltip');
  if (found) {
    hoveredPart = found.id;
    tooltip.style.opacity = '1';
    tooltip.style.left = (mx + 12) + 'px';
    tooltip.style.top = (my - 8) + 'px';
    tooltip.textContent = found.name;
    document.querySelectorAll('.part-label-item').forEach(el => {
      el.classList.toggle('active', el.dataset.id === found.id);
    });
  } else {
    hoveredPart = null;
    tooltip.style.opacity = '0';
    document.querySelectorAll('.part-label-item').forEach(el => el.classList.remove('active'));
  }
  draw();
});

// Touch support
canvas.addEventListener('touchstart', e => {
  const t = e.touches[0];
  isDragging = true;
  lastX = t.clientX;
  lastY = t.clientY;
});
canvas.addEventListener('touchend', () => { isDragging = false; });
canvas.addEventListener('touchmove', e => {
  if (!isDragging) return;
  const t = e.touches[0];
  const dx = t.clientX - lastX;
  const dy = t.clientY - lastY;
  rotY += dx * 0.007;
  rotX += dy * 0.007;
  lastX = t.clientX;
  lastY = t.clientY;
  draw();
  e.preventDefault();
}, { passive: false });

// Slider
const slider = document.getElementById('explode-slider');
const valLabel = document.getElementById('explode-val');
slider.addEventListener('input', () => {
  explode = +slider.value;
  valLabel.textContent = explode + '%';
  draw();
});

// Reset
document.getElementById('reset-btn').addEventListener('click', () => {
  rotX = -0.35; rotY = 0.55;
  explode = 0;
  slider.value = 0;
  valLabel.textContent = '0%';
  stopAnim();
  document.getElementById('animate-btn').textContent = 'Auto-explode ▶';
  draw();
});

// Auto-animate
const animBtn = document.getElementById('animate-btn');
function stopAnim() {
  animating = false;
  if (animId) cancelAnimationFrame(animId);
}
animBtn.addEventListener('click', () => {
  if (animating) {
    stopAnim();
    animBtn.textContent = 'Auto-explode ▶';
  } else {
    animating = true;
    animBtn.textContent = 'Pause ⏸';
    animDir = explode >= 99 ? -1 : 1;
    animate();
  }
});

function animate() {
  if (!animating) return;
  explode += animDir * 0.8;
  if (explode >= 100) { explode = 100; animDir = -1; }
  if (explode <= 0) { explode = 0; animDir = 1; }
  slider.value = explode;
  valLabel.textContent = Math.round(explode) + '%';
  rotY += 0.004;
  draw();
  animId = requestAnimationFrame(animate);
}

// Build part labels
const labelsContainer = document.getElementById('part-labels');
parts.forEach((p, i) => {
  const item = document.createElement('div');
  item.className = 'part-label-item';
  item.dataset.id = p.id;
  item.innerHTML = `<div class="part-dot" style="background:${PART_COLORS_LEGEND[i]}"></div><span>${p.name}</span>`;
  item.addEventListener('click', () => {
    hoveredPart = p.id;
    setTimeout(() => { hoveredPart = null; draw(); }, 1500);
    draw();
  });
  labelsContainer.appendChild(item);
});

draw();

// =========================================================
// MODAL LOGIC
// =========================================================
const modals = {
  canopener: {
    year: '2024–2025',
    title: 'Can Opener Mechanical Design & Analysis',
    body: `
      <p>Designed a fully constrained multi-component can opener assembly in SolidWorks from the ground up. This was my primary project for Computer Aided Visualization and Design.</p>
      <ul>
        <li>Produced detailed 2D engineering drawings, fully mated assembly, exploded views, and a complete drawing package for all components</li>
        <li>Conducted static Finite Element Analysis (FEA) on components under operational loading, validating the design against stainless steel's yield strength</li>
        <li>Performed motion analysis on the gear train, quantifying mechanical advantage and contact force distribution across a full rotation cycle</li>
        <li>Designed gear tooth profile, frame geometry, and ergonomic handle form</li>
      </ul>
      <p style="margin-top:16px;">Scroll down on this page to interact with the exploded view of the assembly.</p>
    `
  },
  beam: {
    year: '2024',
    title: 'Cantilever Beam Deflection Scale',
    body: `
      <p>Designed and fabricated a cantilever beam-based mechanical scale applying Euler–Bernoulli beam theory and Hooke's Law to translate analytical deflection expressions into a physical prototype.</p>
      <ul>
        <li>Fabricated using band saw, drill press, and other tools in the Brown Design Workshop</li>
        <li>Optimized beam dimensions and load placement using MATLAB, computing spring constant, bending stress, and safety factor</li>
        <li>Experimentally validated design through incremental calibration — predicted unknown masses with less than 10% error</li>
      </ul>
    `
  },
  vertebral: {
    year: '2025',
    title: 'Next-Gen Material Selection — Vertebral Body Replacement',
    body: `
      <p>A material selection case report focused on identifying next-generation candidates for vertebral body replacement (VBR) implants.</p>
      <ul>
        <li>Translated clinical needs and finite element analysis results into quantitative mechanical and biological design criteria</li>
        <li>Screened 4,395 materials in Ansys Granta Edupack and ASM Medical Materials databases</li>
        <li>Identified Polyetherimide (PEI) as a leading candidate for future clinical application based on mechanical and biocompatibility properties</li>
      </ul>
    `
  },
  heartrate: {
    year: '2025',
    title: 'Heart Rate Sensor & Formula 1 Safety Gear Testing',
    body: `
      <p>Prototyped a real-time heart rate monitor and used it to analyze biometric data under simulated F1 racing conditions.</p>
      <ul>
        <li>Built the sensor using MAX30102 pulse oximetry and an Arduino with OLED display</li>
        <li>Analyzed and visualized BPM data in MATLAB across simulated Formula 1 safety gear conditions</li>
        <li>Presented findings at an engineering showcase</li>
      </ul>
    `
  },
  rna: {
    year: '2025 – Present',
    title: 'RNA Purification Tube Redesign',
    body: `
      <p>A product design project at Lilac Biosciences Inc. aimed at improving RNA purification workflows in biotech.</p>
      <ul>
        <li>Redesigning RNA purification tube geometry in SolidWorks to replace centrifuge-dependent separation with integrated filtration</li>
        <li>Fabricating and iterating prototypes via 3D printing for experimental validation</li>
        <li>Evaluating filtration membrane candidates through structured literature review and vendor analysis to identify optimal pore size and material compatibility for RNA retention</li>
      </ul>
    `
  },
  pendulum: {
    year: '2026 – Present',
    title: 'Pendulum Friction Testing Apparatus',
    body: `
      <p>Research engineering work at the Bioengineering Laboratory, Orthopedics Department at Rhode Island Hospital.</p>
      <ul>
        <li>Designing active and passive pendulum testing apparatus in SolidWorks to measure coefficients of friction in biological joints</li>
        <li>Fabricating and assembling an experimental testing device in the RIH Orthopaedic Foundation testing facility</li>
        <li>Conducting mechanical validation to characterize tribological properties of soft tissue structures under physiological loading conditions</li>
      </ul>
    `
  }
};

function openModal(id) {
  const m = modals[id];
  if (!m) return;
  document.getElementById('modal-body-content').innerHTML = `
    <div class="modal-year">${m.year}</div>
    <div class="modal-title">${m.title}</div>
    <div class="modal-body">${m.body}</div>
  `;
  document.getElementById('modal-overlay').classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeModal(e) {
  if (e.target === document.getElementById('modal-overlay')) closeModalDirect();
}

function closeModalDirect() {
  document.getElementById('modal-overlay').classList.remove('open');
  document.body.style.overflow = '';
}

document.addEventListener('keydown', e => {
  if (e.key === 'Escape') closeModalDirect();
});
</script>
</body>
</html>
HTMLEOF
echo "Done"
