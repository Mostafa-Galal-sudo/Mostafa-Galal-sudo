<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- ██████  ███████ ██   ██ ████████  █████   ██████  ██   ██      -->
<!-- ██   ██ ██      ██   ██    ██    ██   ██ ██       ██   ██      -->
<!-- ███████ ███████ ███████    ██    ███████ ██   ███ ███████      -->
<!-- ██   ██      ██ ██   ██    ██    ██   ██ ██    ██ ██   ██      -->
<!-- ██   ██ ███████ ██   ██    ██    ██   ██  ██████  ██   ██      -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- RAYES.0xKRNL — Mostafa Galal — Maximum Offensive Security      -->

<style>
  /* ═══════════════════════════════════════════════════════════════ */
  /* GLOBAL DARK THEME + VIDEO BACKGROUND                          */
  /* ═══════════════════════════════════════════════════════════════ */
  body {
    background-color: #000000 !important;
    color: #e0e0e0 !important;
    font-family: 'Courier New', 'Fira Code', monospace !important;
  }

  /* Video Background Container */
  .video-bg-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    overflow: hidden;
    pointer-events: none;
  }

  .video-bg-container video {
    position: absolute;
    top: 50%;
    left: 50%;
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
    transform: translate(-50%, -50%);
    opacity: 0.15;
    filter: grayscale(100%) contrast(120%) brightness(0.4);
  }

  /* Scanline Overlay */
  .scanlines {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(
      to bottom,
      rgba(255,255,255,0),
      rgba(255,255,255,0) 50%,
      rgba(0,0,0,0.1) 50%,
      rgba(0,0,0,0.1)
    );
    background-size: 100% 4px;
    z-index: 9999;
    pointer-events: none;
    animation: scanlineMove 0.1s linear infinite;
  }

  @keyframes scanlineMove {
    0% { background-position: 0 0; }
    100% { background-position: 0 4px; }
  }

  /* CRT Flicker */
  .crt-flicker {
    animation: flicker 0.15s infinite;
  }

  @keyframes flicker {
    0% { opacity: 0.97; }
    50% { opacity: 1; }
    100% { opacity: 0.98; }
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* GLITCH TEXT EFFECT                                             */
  /* ═══════════════════════════════════════════════════════════════ */
  .glitch {
    position: relative;
    color: #ff0000;
    font-weight: 900;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-shadow: 
      0.05em 0 0 rgba(255,0,0,0.75),
      -0.025em -0.05em 0 rgba(0,255,0,0.75),
      0.025em 0.05em 0 rgba(0,0,255,0.75);
    animation: glitch 2s infinite;
  }

  .glitch::before,
  .glitch::after {
    content: attr(data-text);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  .glitch::before {
    left: 2px;
    text-shadow: -2px 0 #00ff00;
    clip: rect(44px, 450px, 56px, 0);
    animation: glitch-anim 5s infinite linear alternate-reverse;
  }

  .glitch::after {
    left: -2px;
    text-shadow: -2px 0 #0000ff;
    clip: rect(44px, 450px, 56px, 0);
    animation: glitch-anim2 5s infinite linear alternate-reverse;
  }

  @keyframes glitch-anim {
    0% { clip: rect(12px, 9999px, 52px, 0); }
    20% { clip: rect(65px, 9999px, 11px, 0); }
    40% { clip: rect(26px, 9999px, 89px, 0); }
    60% { clip: rect(78px, 9999px, 14px, 0); }
    80% { clip: rect(33px, 9999px, 67px, 0); }
    100% { clip: rect(91px, 9999px, 23px, 0); }
  }

  @keyframes glitch-anim2 {
    0% { clip: rect(65px, 9999px, 99px, 0); }
    20% { clip: rect(12px, 9999px, 33px, 0); }
    40% { clip: rect(88px, 9999px, 11px, 0); }
    60% { clip: rect(44px, 9999px, 77px, 0); }
    80% { clip: rect(22px, 9999px, 55px, 0); }
    100% { clip: rect(66px, 9999px, 22px, 0); }
  }

  @keyframes glitch {
    0% { text-shadow: 0.05em 0 0 rgba(255,0,0,0.75), -0.05em -0.025em 0 rgba(0,255,0,0.75), -0.025em 0.05em 0 rgba(0,0,255,0.75); }
    14% { text-shadow: 0.05em 0 0 rgba(255,0,0,0.75), -0.05em -0.025em 0 rgba(0,255,0,0.75), -0.025em 0.05em 0 rgba(0,0,255,0.75); }
    15% { text-shadow: -0.05em -0.025em 0 rgba(255,0,0,0.75), 0.025em 0.025em 0 rgba(0,255,0,0.75), -0.05em -0.05em 0 rgba(0,0,255,0.75); }
    49% { text-shadow: -0.05em -0.025em 0 rgba(255,0,0,0.75), 0.025em 0.025em 0 rgba(0,255,0,0.75), -0.05em -0.05em 0 rgba(0,0,255,0.75); }
    50% { text-shadow: 0.025em 0.05em 0 rgba(255,0,0,0.75), 0.05em 0 0 rgba(0,255,0,0.75), 0 -0.05em 0 rgba(0,0,255,0.75); }
    99% { text-shadow: 0.025em 0.05em 0 rgba(255,0,0,0.75), 0.05em 0 0 rgba(0,255,0,0.75), 0 -0.05em 0 rgba(0,0,255,0.75); }
    100% { text-shadow: -0.025em 0 0 rgba(255,0,0,0.75), -0.025em -0.025em 0 rgba(0,255,0,0.75), -0.025em -0.05em 0 rgba(0,0,255,0.75); }
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* PULSE GLOW EFFECTS                                             */
  /* ═══════════════════════════════════════════════════════════════ */
  .pulse-glow {
    animation: pulseGlow 2s ease-in-out infinite;
  }

  @keyframes pulseGlow {
    0%, 100% { 
      box-shadow: 0 0 5px rgba(255, 0, 0, 0.5), 0 0 20px rgba(255, 0, 0, 0.3), 0 0 40px rgba(255, 0, 0, 0.1);
      text-shadow: 0 0 5px rgba(255, 0, 0, 0.5), 0 0 20px rgba(255, 0, 0, 0.3);
    }
    50% { 
      box-shadow: 0 0 10px rgba(255, 0, 0, 0.8), 0 0 40px rgba(255, 0, 0, 0.5), 0 0 80px rgba(255, 0, 0, 0.2);
      text-shadow: 0 0 10px rgba(255, 0, 0, 0.8), 0 0 40px rgba(255, 0, 0, 0.5);
    }
  }

  .pulse-glow-green {
    animation: pulseGlowGreen 2s ease-in-out infinite;
  }

  @keyframes pulseGlowGreen {
    0%, 100% { 
      box-shadow: 0 0 5px rgba(0, 255, 0, 0.3), 0 0 20px rgba(0, 255, 0, 0.1);
    }
    50% { 
      box-shadow: 0 0 10px rgba(0, 255, 0, 0.6), 0 0 40px rgba(0, 255, 0, 0.3);
    }
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* TERMINAL STYLING                                               */
  /* ═══════════════════════════════════════════════════════════════ */
  .terminal {
    background: rgba(0, 0, 0, 0.9);
    border: 1px solid #ff0000;
    border-radius: 8px;
    padding: 20px;
    margin: 20px 0;
    position: relative;
    overflow: hidden;
  }

  .terminal::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 30px;
    background: linear-gradient(180deg, rgba(255,0,0,0.1) 0%, transparent 100%);
    border-bottom: 1px solid rgba(255,0,0,0.3);
  }

  .terminal-header {
    display: flex;
    gap: 8px;
    margin-bottom: 15px;
    position: relative;
    z-index: 1;
  }

  .terminal-dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    animation: blink 1.5s infinite;
  }

  .terminal-dot.red { background: #ff0000; }
  .terminal-dot.yellow { background: #ffaa00; animation-delay: 0.5s; }
  .terminal-dot.green { background: #00ff00; animation-delay: 1s; }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .terminal-content {
    color: #00ff00;
    font-family: 'Courier New', monospace;
    line-height: 1.6;
  }

  .terminal-content .prompt {
    color: #ff0000;
  }

  .terminal-content .command {
    color: #ffffff;
  }

  .terminal-content .output {
    color: #aaaaaa;
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* BADGE HOVER EFFECTS                                            */
  /* ═══════════════════════════════════════════════════════════════ */
  .badge-container a {
    transition: all 0.3s ease;
    display: inline-block;
  }

  .badge-container a:hover {
    transform: scale(1.1) translateY(-3px);
    filter: brightness(1.3) drop-shadow(0 0 10px rgba(255, 0, 0, 0.7));
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* TABLE STYLING                                                  */
  /* ═══════════════════════════════════════════════════════════════ */
  table {
    border-collapse: collapse;
    width: 100%;
    margin: 15px 0;
  }

  th {
    background: rgba(139, 0, 0, 0.3);
    color: #ff0000;
    padding: 12px;
    text-align: left;
    border-bottom: 2px solid #ff0000;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  td {
    padding: 10px 12px;
    border-bottom: 1px solid rgba(255, 0, 0, 0.2);
    color: #cccccc;
  }

  tr:hover td {
    background: rgba(255, 0, 0, 0.05);
    color: #ffffff;
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* DETAILS/SUMMARY STYLING                                        */
  /* ═══════════════════════════════════════════════════════════════ */
  details {
    background: rgba(0, 0, 0, 0.7);
    border: 1px solid rgba(255, 0, 0, 0.3);
    border-radius: 8px;
    margin: 10px 0;
    overflow: hidden;
  }

  details summary {
    padding: 15px 20px;
    cursor: pointer;
    color: #ff0000;
    font-weight: bold;
    transition: all 0.3s ease;
    background: rgba(139, 0, 0, 0.1);
  }

  details summary:hover {
    background: rgba(139, 0, 0, 0.2);
    padding-left: 25px;
  }

  details[open] summary {
    border-bottom: 1px solid rgba(255, 0, 0, 0.3);
  }

  details > *:not(summary) {
    padding: 15px 20px;
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* SECTION HEADERS                                                */
  /* ═══════════════════════════════════════════════════════════════ */
  .section-header {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
    margin: 40px 0 25px;
    padding: 15px;
    background: linear-gradient(90deg, transparent, rgba(139, 0, 0, 0.2), transparent);
    border-top: 1px solid rgba(255, 0, 0, 0.3);
    border-bottom: 1px solid rgba(255, 0, 0, 0.3);
  }

  .section-header h3 {
    color: #ff0000;
    margin: 0;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    text-shadow: 0 0 10px rgba(255, 0, 0, 0.5);
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* MATRIX RAIN CANVAS (Background)                                */
  /* ═══════════════════════════════════════════════════════════════ */
  #matrix-canvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -2;
    opacity: 0.08;
    pointer-events: none;
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* FOOTER STYLING                                                 */
  /* ═══════════════════════════════════════════════════════════════ */
  .footer-quote {
    text-align: center;
    padding: 30px;
    margin-top: 40px;
    border-top: 2px solid rgba(255, 0, 0, 0.3);
    background: linear-gradient(180deg, transparent, rgba(139, 0, 0, 0.1));
  }

  .footer-quote pre {
    color: #ff0000;
    font-family: 'Courier New', monospace;
    line-height: 1.8;
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* ANIMATED DIVIDERS                                              */
  /* ═══════════════════════════════════════════════════════════════ */
  .blood-divider {
    height: 2px;
    background: linear-gradient(90deg, transparent, #ff0000, #8b0000, #ff0000, transparent);
    background-size: 200% 100%;
    animation: bloodFlow 3s linear infinite;
    margin: 30px 0;
    border: none;
  }

  @keyframes bloodFlow {
    0% { background-position: 0% 50%; }
    100% { background-position: 200% 50%; }
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* SOCIAL LINKS STYLING                                           */
  /* ═══════════════════════════════════════════════════════════════ */
  .social-links {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
    margin: 20px 0;
  }

  .social-links a {
    transition: all 0.3s ease;
  }

  .social-links a:hover {
    transform: scale(1.15) rotate(2deg);
    filter: drop-shadow(0 0 15px rgba(255, 0, 0, 0.8));
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* STATUS INDICATORS                                              */
  /* ═══════════════════════════════════════════════════════════════ */
  .status-active { color: #00ff00; text-shadow: 0 0 5px rgba(0, 255, 0, 0.5); }
  .status-private { color: #ffaa00; text-shadow: 0 0 5px rgba(255, 170, 0, 0.5); }
  .status-archived { color: #888888; }

  /* ═══════════════════════════════════════════════════════════════ */
  /* SCROLLBAR STYLING                                              */
  /* ═══════════════════════════════════════════════════════════════ */
  ::-webkit-scrollbar {
    width: 10px;
  }

  ::-webkit-scrollbar-track {
    background: #000000;
  }

  ::-webkit-scrollbar-thumb {
    background: #8b0000;
    border-radius: 5px;
  }

  ::-webkit-scrollbar-thumb:hover {
    background: #ff0000;
  }

  /* ═══════════════════════════════════════════════════════════════ */
  /* RESPONSIVE                                                     */
  /* ═══════════════════════════════════════════════════════════════ */
  @media (max-width: 768px) {
    .glitch {
      font-size: 0.7em;
    }

    .section-header {
      flex-direction: column;
      gap: 10px;
    }

    .social-links {
      flex-direction: column;
      align-items: center;
    }
  }
</style>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- VIDEO BACKGROUND                                               -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="video-bg-container">
  <!-- ضع لينك الفيديو بتاعك هنا -->
  <video autoplay muted loop playsinline>
    <source src="https://assets.mixkit.co/videos/preview/mixkit-digital-animation-of-futuristic-devices-99786-large.mp4" type="video/mp4">
    <!-- fallback: لو الفيديو مش شغال، هيبقى background سود -->
  </video>
</div>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- MATRIX RAIN CANVAS                                             -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<canvas id="matrix-canvas"></canvas>

<script>
  const canvas = document.getElementById('matrix-canvas');
  const ctx = canvas.getContext('2d');

  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  const chars = "01アイウエオカキクケコサシスセソタチツテトナニヌネノハヒフヘホマミムメモヤユヨラリルレロワヲン";
  const charArray = chars.split('');
  const fontSize = 14;
  const columns = canvas.width / fontSize;
  const drops = [];

  for (let i = 0; i < columns; i++) {
    drops[i] = Math.random() * -100;
  }

  function drawMatrix() {
    ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = '#ff0000';
    ctx.font = fontSize + 'px monospace';

    for (let i = 0; i < drops.length; i++) {
      const text = charArray[Math.floor(Math.random() * charArray.length)];
      ctx.fillText(text, i * fontSize, drops[i] * fontSize);

      if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
        drops[i] = 0;
      }
      drops[i]++;
    }
  }

  setInterval(drawMatrix, 50);

  window.addEventListener('resize', () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  });
</script>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- SCANLINES OVERLAY                                              -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="scanlines"></div>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- HEADER BANNER: BLOOD RED WAVE                                -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,20:1a0000,40:4a0000,60:8B0000,80:FF0000,100:000000&height=280&section=header&text=RAYES.0xKRNL&fontSize=70&fontColor=FF0000&fontAlignY=30&desc=Mostafa%20Galal%20%E2%80%94%20ECE%20%C3%97%20Offensive%20Security&descAlignY=52&descSize=20&animation=fadeIn&stroke=FF0000&strokeWidth=3&font=Fira%20Code" width="100%" />
</div>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- GLITCH TYPING ANIMATION                                        -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center" style="margin: 30px 0;">
  <div class="glitch" data-text="INITIALIZING OFFENSIVE PROTOCOLS..." style="font-size: 28px; margin-bottom: 15px;">
    INITIALIZING OFFENSIVE PROTOCOLS...
  </div>
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=800&size=24&duration=2500&pause=800&color=FF0000&center=true&vCenter=true&multiline=true&width=850&height=120&lines=Electronics+%26+Communications+Engineer;Red+Team+Operator+%7C+CTF+Assassin+%7C+Bug+Hunter;Low-Level+%7C+Pwn+%7C+Embedded+Death+Machines;The+best+defense+is+understanding+the+offense." alt="Typing SVG" />
  </a>
</div>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- BLOOD DIVIDER                                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center">
  <hr class="blood-divider" style="width: 80%;" />
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- STATUS BADGES: BLOOD ON BLACK                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center" class="badge-container">
  <img src="https://hits.sh/github.com/Mostafa-Galal-sudo/Mostafa-Galal-sudo.svg?label=VOID%20VIEWS&extraCount=0&color=000000&labelColor=8B0000" alt="Profile Views" />
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/Status-0xBLOOD%20Online-FF0000?style=for-the-badge&logo=statuspage&logoColor=white&labelColor=000000" alt="Status" />
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/Threat%20Level-MAXIMUM%20OVERDRIVE-8B0000?style=for-the-badge&logo=hackthebox&logoColor=white&labelColor=000000" alt="Threat Level" />
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/Access-ROOT%20PRIVILEGES-FF0000?style=for-the-badge&logo=rootme&logoColor=white&labelColor=000000" alt="Root Access" />
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- TERMINAL WHOAMI: VOID EDITION                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center">
  <div class="terminal pulse-glow" style="max-width: 700px; text-align: left;">
    <div class="terminal-header">
      <div class="terminal-dot red"></div>
      <div class="terminal-dot yellow"></div>
      <div class="terminal-dot green"></div>
      <span style="color: #ff0000; margin-left: 10px; font-size: 12px;">root@0xKRNL:~#</span>
    </div>
    <div class="terminal-content">
      <span class="prompt">$</span> <span class="command">sudo whoami --blood --full-recon</span><br><br>
      <span class="output">
      ┌──────────────────────────────────────────────────────────────┐<br>
      │  <span style="color:#ff0000;">TARGET IDENTIFIED</span>                                          │<br>
      │                                                              │<br>
      │  > Name: <span style="color:#ffffff;">Mostafa Galal</span>  ·  Alias: <span style="color:#ff0000;">RAYES.0xKRNL</span>             │<br>
      │  > Role: <span style="color:#00ff00;">Electronics & Communications Engineer</span>              │<br>
      │  > Focus: <span style="color:#ffaa00;">low-level internals, binary exploitation,</span>          │<br>
      │           <span style="color:#ffaa00;">kernel security, embedded smart systems</span>            │<br>
      │  > Certs: <span style="color:#00ffff;">eJPT · CCNA · CCNP</span>                               │<br>
      │  > Arena: <span style="color:#ff0000;">HackTheBox · Red Team Ops · Bug Bounty</span>           │<br>
      └──────────────────────────────────────────────────────────────┘
      </span>
    </div>
  </div>
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- LETHAL ARSENAL                                                 -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="section-header">
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Crossed%20Swords.png" width="30" />
  <h3>LETHAL ARSENAL</h3>
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Dagger.png" width="30" />
</div>

<div align="center" class="badge-container">

### 🔴 Offensive Security
[![Kali Linux](https://img.shields.io/badge/Kali_Linux-8B0000?style=for-the-badge&logo=kali-linux&logoColor=white&labelColor=000000)](https://www.kali.org)
[![Burp Suite](https://img.shields.io/badge/Burp_Suite-8B0000?style=for-the-badge&logo=burp-suite&logoColor=white&labelColor=000000)](https://portswigger.net/burp)
[![Ghidra](https://img.shields.io/badge/Ghidra-8B0000?style=for-the-badge&logo=ghidra&logoColor=white&labelColor=000000)](https://ghidra-sre.org)
[![Wireshark](https://img.shields.io/badge/Wireshark-8B0000?style=for-the-badge&logo=wireshark&logoColor=white&labelColor=000000)](https://www.wireshark.org)
[![Nmap](https://img.shields.io/badge/Nmap-8B0000?style=for-the-badge&logo=nmap&logoColor=white&labelColor=000000)](https://nmap.org)
[![Metasploit](https://img.shields.io/badge/Metasploit-8B0000?style=for-the-badge&logo=metasploit&logoColor=white&labelColor=000000)](https://www.metasploit.com)
[![pwntools](https://img.shields.io/badge/pwntools-8B0000?style=for-the-badge&logo=python&logoColor=white&labelColor=000000)](https://docs.pwntools.com)
[![GDB](https://img.shields.io/badge/GDB%2Fpwndbg-8B0000?style=for-the-badge&logoColor=FF0000&labelColor=000000)](https://github.com/pwndbg/pwndbg)

### ⚙️ Embedded & Electronics
[![Arduino](https://img.shields.io/badge/Arduino-8B0000?style=for-the-badge&logo=arduino&logoColor=white&labelColor=000000)](https://www.arduino.cc)
[![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-8B0000?style=for-the-badge&logo=raspberry-pi&logoColor=white&labelColor=000000)](https://www.raspberrypi.org)
[![OpenCV](https://img.shields.io/badge/OpenCV-8B0000?style=for-the-badge&logo=opencv&logoColor=white&labelColor=000000)](https://opencv.org)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-8B0000?style=for-the-badge&logo=google&logoColor=white&labelColor=000000)](https://mediapipe.dev)
[![Blender](https://img.shields.io/badge/Blender-8B0000?style=for-the-badge&logo=blender&logoColor=white&labelColor=000000)](https://www.blender.org)
[![SageMath](https://img.shields.io/badge/SageMath-8B0000?style=for-the-badge&logoColor=FF0000&labelColor=000000)](https://www.sagemath.org)

### 🌐 Platforms & DevOps
[![Docker](https://img.shields.io/badge/Docker-8B0000?style=for-the-badge&logo=docker&logoColor=white&labelColor=000000)](https://www.docker.com)
[![Linux](https://img.shields.io/badge/Linux-8B0000?style=for-the-badge&logo=linux&logoColor=white&labelColor=000000)](https://www.linux.org)
[![HackTheBox](https://img.shields.io/badge/HackTheBox-8B0000?style=for-the-badge&logo=hackthebox&logoColor=white&labelColor=000000)](https://app.hackthebox.com)
[![React](https://img.shields.io/badge/React-8B0000?style=for-the-badge&logo=react&logoColor=white&labelColor=000000)](https://react.dev)
[![Cloudflare](https://img.shields.io/badge/Cloudflare-8B0000?style=for-the-badge&logo=cloudflare&logoColor=white&labelColor=000000)](https://www.cloudflare.com)

</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- VOID TELEMETRY                                                 -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="section-header">
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Bar%20Chart.png" width="25" />
  <h3>VOID TELEMETRY</h3>
</div>

<div align="center">
  <img src="/github-metrics.svg" alt="GitHub Metrics" width="100%" style="border: 1px solid rgba(255,0,0,0.3); border-radius: 8px;" />
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- STATS CARDS: PURE BLACK + BLOOD RED                            -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=Mostafa-Galal-sudo&show_icons=true&hide_border=true&bg_color=000000&title_color=FF0000&icon_color=8B0000&text_color=FFFFFF&count_private=true&include_all_commits=true&line_height=24&custom_title=0xKRNL%20%7C%20VOID%20STATS" />
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Mostafa-Galal-sudo&layout=compact&hide_border=true&bg_color=000000&title_color=FF0000&text_color=FFFFFF&langs_count=10&hide=html,css&custom_title=LANGUAGE%20DISTRIBUTION" />
</div>

<div align="center" style="margin-top: 15px;">
  <img height="180em" src="https://github-readme-streak-stats.herokuapp.com/?user=Mostafa-Galal-sudo&hide_border=true&background=000000&ring=FF0000&fire=8B0000&currStreakLabel=FF0000&sideLabels=FFFFFF&currStreakNum=FFFFFF&sideNums=FF0000&dates=8B0000" />
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- TROPHIES: DARK ELITE                                           -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=Mostafa-Galal-sudo&theme=onestar&no-frame=true&no-bg=true&margin-w=15&margin-h=15&column=7" alt="GitHub Trophies" width="100%" style="filter: drop-shadow(0 0 10px rgba(255,0,0,0.3));" />
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- BLACK OPS: PROJECTS                                            -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="section-header">
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/File%20Folder.png" width="25" />
  <h3>BLACK OPERATIONS</h3>
</div>

<details>
<summary><b>🔴 Security Tooling & Offensive Capabilities</b></summary>
<br>

| Project | Description | Status | Tech |
|---------|-------------|--------|------|
| [**NM Analyzer**](https://github.com/Mostafa-Galal-sudo) | Static analysis engine for Linux Kernel Modules — symbol-table heuristics detect rootkits, privesc symbols, syscall hooks. Weighted risk scoring + JSON report. | <span class="status-active">🟢 Active</span> | Python, ELF |
| [**PrivEsc-Suite**](https://github.com/Mostafa-Galal-sudo) | Comprehensive Linux privilege escalation framework — 3300+ lines, 183+ SUID binaries, 55+ sudo cases, 13 kernel CVEs, LD_PRELOAD/PYTHONPATH chains. | <span class="status-active">🟢 Active</span> | Bash, Python |
| [**Shadow Core**](https://github.com/Mostafa-Galal-sudo) | Modular framework for staged payload delivery and controlled listener orchestration. Configuration-driven module graph, multi-stage loader chain, pluggable transports. | <span class="status-private">🔒 Private</span> | Python, C |
| [**Payload Generator**](https://github.com/Mostafa-Galal-sudo) | Multi-platform payload research toolkit — Windows/Linux/macOS/Python/JS/PowerShell formats, obfuscation pipeline, listener integration. Lab use only. | <span class="status-private">🔒 Private</span> | Python, C++ |
| [**Keylogger Framework**](https://github.com/Mostafa-Galal-sudo) | Client-server telemetry framework for keystroke pattern analysis. Async transport, JSON session logging, controlled lab environments. | <span class="status-archived">📦 Archived</span> | Python, Socket |
| [**TCP Full Scan Tool**](https://github.com/Mostafa-Galal-sudo) | Async TCP full-port scanner (1–65535) — asyncio semaphore concurrency, banner grabbing, well-known service fallback, CSV export. | <span class="status-active">🟢 Active</span> | Python |

</details>

<details>
<summary><b>⚙️ Embedded Systems & Hardware</b></summary>
<br>

| Project | Description | Status | Tech |
|---------|-------------|--------|------|
| [**SmartCar OS**](https://github.com/Mostafa-Galal-sudo/SmartCarApp) | Full-stack smart RC car — Android app with 9 control modes (voice AI, gyroscope, camera line-follower, clap detection, music rhythm, draw path), Arduino AVR firmware with servo sweep & obstacle avoidance, real-time cyberpunk web dashboard via WebSocket. Biometric auth, telemetry radar, Web Audio beat detection. | <span class="status-active">🟢 Active</span> | React, Arduino, WebSocket |
| [**S.W.A.R.M**](https://github.com/Mostafa-Galal-sudo) | Smart Wireless Autonomous Reactive Mobile — HC-SR04 + L298N + HC-05 BT, 5-state decision system, Flask+SocketIO dashboard (Simple/Complex/Military/Engineering modes), PySerial bridge, Argon2 auth, SQLite logging. | <span class="status-archived">📦 Archived</span> | Python, Flask, Arduino |
| [**Smart Recon Vehicle**](https://github.com/youssefsalama-11/Smart-Car-Project) | Bluetooth-controlled rover — differential PWM drive, ATmega328P, UART serial telemetry. | <span class="status-archived">📦 Archived</span> | C++, AVR |
| [**Hand Sanitizer Dispenser**](https://github.com/Mostafa-Galal-sudo) | Arduino with HC-SR04 ultrasonic, LCD display, 4-state machine, relay noise isolation. | <span class="status-archived">📦 Archived</span> | C++, Arduino |
| [**Smart Curtain System**](https://github.com/Mostafa-Galal-sudo) | Pure gate logic — no MCU. AND/OR/NOT gates, Karnaugh-minimized, hazard-free truth table for light/time/manual override inputs. | <span class="status-archived">📦 Archived</span> | Digital Logic |
| [**Series RLC Band-Pass**](https://github.com/Mostafa-Galal-sudo) | Passive RLC BPF — f₀ = 1.59 MHz, Q = 12.4, BW = 128 kHz. ngspice AC sim, pass-band ripple < 0.4 dB. | <span class="status-archived">📦 Archived</span> | ngspice |
| [**3rd-Order Butterworth BPF**](https://github.com/Mostafa-Galal-sudo) | Maximally flat 3rd-order band-pass — f₀ = 1 MHz, BW = 10 kHz, −60 dB/decade roll-off. | <span class="status-archived">📦 Archived</span> | ngspice |

</details>

<details>
<summary><b>🤖 AI, Computer Vision & Automation</b></summary>
<br>

| Project | Description | Status | Tech |
|---------|-------------|--------|------|
| [**FaceBlur Live**](https://github.com/Mostafa-Galal-sudo) | Real-time face detection + mosaic blur — MediaPipe + OpenCV, simultaneous audio recording via sounddevice, FFmpeg merge for final output. | <span class="status-active">🟢 Active</span> | Python, MediaPipe, FFmpeg |
| [**TikTok Media Downloader**](https://github.com/Mostafa-Galal-sudo) | Professional customtkinter GUI — watermark-free download, thumbnail preview, video metadata, audio extraction, progress bar. tikwm API. | <span class="status-archived">📦 Archived</span> | Python, customtkinter |

</details>

<details>
<summary><b>🌐 Web Portfolio & CTF Arsenal</b></summary>
<br>

| Project | Description | Status | Tech |
|---------|-------------|--------|------|
| [**cybernetic-canvas**](https://github.com/Mostafa-Galal-sudo/cybernetic-canvas) | Personal portfolio — React + TanStack Router + TypeScript + Cloudflare Workers. Neural network visualization, IDE-style projects workspace, cyberpunk design system. | <span class="status-active">🟢 Active</span> | React, TypeScript, Workers |
| [**CTF Writeups**](https://github.com/Mostafa-Galal-sudo/ctf) | HackTheBox writeups & exploit chains — pwn, RE, crypto, web. BOF, ASLR bypass via format-string leak, AD attack paths, binary analysis. | <span class="status-active">🟢 Active</span> | Markdown, Python |

</details>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- BLOOD OATHS: CERTIFICATIONS                                    -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="section-header">
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Scroll.png" width="25" />
  <h3>BLOOD OATHS & CLEARANCE</h3>
</div>

<div align="center" style="max-width: 700px; margin: 0 auto;">

| Badge | Details | Verification |
|-------|---------|-------------|
| 🎖️ **eJPT** | eLearnSecurity Junior Penetration Tester | INE/eJPT |
| 🌐 **CCNA** | Cisco Certified Network Associate | Cisco |
| 🔗 **CCNP** | Cisco Certified Network Professional | Cisco |
| 🧩 **HackTheBox** | Active Player — pwn · RE · crypto · web · AD | [Profile](https://app.hackthebox.com) |

</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- SNAKE CONTRIBUTION GRAPH: DARK BLOOD                           -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="section-header">
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Animals/Snake.png" width="25" />
  <h3>NEURAL BLOODPATH</h3>
</div>

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Mostafa-Galal-sudo/Mostafa-Galal-sudo/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Mostafa-Galal-sudo/Mostafa-Galal-sudo/output/github-contribution-grid-snake-dark.svg" />
    <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/Mostafa-Galal-sudo/Mostafa-Galal-sudo/output/github-contribution-grid-snake-dark.svg" style="filter: drop-shadow(0 0 15px rgba(255,0,0,0.4));" />
  </picture>
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- ACTIVITY GRAPH: BLOOD HEATMAP                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Mostafa-Galal-sudo&bg_color=000000&color=FF0000&line=8B0000&point=FF0000&area=true&hide_border=true&custom_title=0xKRNL%20%7C%20BLOOD%20HEATMAP" width="100%" style="border-radius: 8px; filter: drop-shadow(0 0 10px rgba(255,0,0,0.3));" />
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- DEAD DROPS: SOCIAL                                             -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div class="section-header">
  <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Satellite%20Antenna.png" width="25" />
  <h3>DEAD DROPS</h3>
</div>

<div class="social-links">
  <a href="https://app.hackthebox.com">
    <img src="https://img.shields.io/badge/HackTheBox-Profile-8B0000?style=for-the-badge&logo=hackthebox&logoColor=white&labelColor=000000" />
  </a>
  <a href="https://github.com/Mostafa-Galal-sudo/cybernetic-canvas">
    <img src="https://img.shields.io/badge/Portfolio-cybernetic--canvas-8B0000?style=for-the-badge&logo=react&logoColor=white&labelColor=000000" />
  </a>
  <a href="https://linkedin.com/in/mostafa-galal">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-8B0000?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=000000" />
  </a>
  <a href="https://github.com/Mostafa-Galal-sudo">
    <img src="https://img.shields.io/badge/GitHub-0xKRNL-8B0000?style=for-the-badge&logo=github&logoColor=white&labelColor=000000" />
  </a>
</div>

<br>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!-- FOOTER BANNER: BLOOD RED → BLACK                               -->
<!-- ═══════════════════════════════════════════════════════════════ -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:8B0000,50:FF0000,100:000000&height=150&section=footer&text=The%20best%20defense%20is%20understanding%20the%20offense.&fontSize=20&fontColor=FF0000&fontAlignY=70&animation=fadeIn" width="100%" />
</div>

<div class="footer-quote">
  <pre class="pulse-glow">
╔══════════════════════════════════════════════════════════╗
║  The best defense is understanding the offense.          ║
║                                        — RAYES.0xKRNL    ║
╚══════════════════════════════════════════════════════════╝
  </pre>
</div>
