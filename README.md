<style>
  @import url('https://fonts.googleapis.com/css2?family=Silkscreen:wght@400;700&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap');

  :root {
    --pond-deep: #0a1f18;
    --pond-mid: #0d3028;
    --pond-teal: #1a5c4a;
    --pond-jade: #2d8c6e;
    --water-teal: #1e6b6b;
    --water-shimmer: #2ea89a;
    --lily-green: #3d9e5a;
    --lily-bright: #5ec47a;
    --lily-dark: #1e5c35;
    --lotus-pink: #d4748a;
    --lotus-light: #f0a8b8;
    --lotus-rose: #c45c74;
    --lotus-cream: #f5e8d0;
    --koi-orange: #e8834a;
    --koi-gold: #d4a030;
    --koi-white: #f0ede0;
    --moss: #6aac5a;
    --cream: #f0ead8;
    --rosy-brown: #b07858;
    --midnight: #105668;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--pond-deep);
    font-family: 'Space Mono', monospace;
    color: var(--cream);
    overflow-x: hidden;
    min-height: 100vh;
  }

  .readme-wrap {
    max-width: 680px;
    margin: 0 auto;
    padding: 0 0 48px;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    text-align: center;
    padding: 0px 20px 0;
    overflow: hidden;
    min-height: 380px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
  }

  /* layered pond background */
  .pond-bg {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 40% at 30% 60%, rgba(30,107,107,0.5) 0%, transparent 60%),
      radial-gradient(ellipse 50% 35% at 75% 55%, rgba(45,140,110,0.4) 0%, transparent 55%),
      radial-gradient(ellipse 80% 70% at 50% 80%, #0d3028 0%, #0a1f18 80%);
    z-index: 0;
  }

  /* dappled light patches on water */
  .light-patch {
    position: absolute;
    border-radius: 50%;
    background: radial-gradient(ellipse, rgba(255,255,220,0.06) 0%, transparent 70%);
    pointer-events: none;
    animation: lightDrift 8s ease-in-out infinite;
  }
  .light-patch:nth-child(1) { width: 120px; height: 60px; top: 35%; left: 15%; animation-delay: 0s; }
  .light-patch:nth-child(2) { width: 80px; height: 40px; top: 55%; left: 55%; animation-delay: 2s; }
  .light-patch:nth-child(3) { width: 100px; height: 50px; top: 25%; left: 70%; animation-delay: 4s; }
  @keyframes lightDrift {
    0%,100% { opacity: 0.6; transform: scale(1) rotate(-5deg); }
    50% { opacity: 1; transform: scale(1.15) rotate(5deg); }
  }

  /* Koi fish */
  .koi {
    position: absolute;
    pointer-events: none;
    opacity: 0.7;
  }
  .koi-1 { animation: koiSwim1 18s ease-in-out infinite; }
  .koi-2 { animation: koiSwim2 22s ease-in-out infinite; animation-delay: -6s; }
  .koi-3 { animation: koiSwim3 15s ease-in-out infinite; animation-delay: -10s; }

  @keyframes koiSwim1 {
    0%   { transform: translate(60px, 120px) rotate(20deg) scaleX(1); opacity: 0.5; }
    30%  { transform: translate(340px, 80px) rotate(-10deg) scaleX(1); opacity: 0.8; }
    60%  { transform: translate(500px, 200px) rotate(15deg) scaleX(-1); opacity: 0.6; }
    100% { transform: translate(60px, 120px) rotate(20deg) scaleX(1); opacity: 0.5; }
  }
  @keyframes koiSwim2 {
    0%   { transform: translate(400px, 180px) rotate(-25deg) scaleX(-1); opacity: 0.4; }
    40%  { transform: translate(150px, 240px) rotate(10deg) scaleX(-1); opacity: 0.75; }
    70%  { transform: translate(80px, 100px) rotate(-15deg) scaleX(1); opacity: 0.5; }
    100% { transform: translate(400px, 180px) rotate(-25deg) scaleX(-1); opacity: 0.4; }
  }
  @keyframes koiSwim3 {
    0%   { transform: translate(250px, 50px) rotate(5deg) scaleX(1); opacity: 0.3; }
    50%  { transform: translate(450px, 160px) rotate(-20deg) scaleX(-1); opacity: 0.65; }
    100% { transform: translate(250px, 50px) rotate(5deg) scaleX(1); opacity: 0.3; }
  }

  /* ripple rings on water surface */
  .ripple-ring {
    position: absolute;
    border: 1px solid rgba(94,196,122,0.12);
    border-radius: 50%;
    animation: ripple 5s ease-out infinite;
    pointer-events: none;
  }
  .ripple-ring:nth-child(8)  { width: 60px; height: 24px; bottom: 95px; left: 22%; animation-delay: 0s; }
  .ripple-ring:nth-child(9)  { width: 110px; height: 40px; bottom: 88px; left: 17%; animation-delay: 0.5s; }
  .ripple-ring:nth-child(10) { width: 160px; height: 58px; bottom: 80px; left: 12%; animation-delay: 1s; }
  .ripple-ring:nth-child(11) { width: 55px; height: 22px; bottom: 100px; right: 18%; animation-delay: 2s; }
  .ripple-ring:nth-child(12) { width: 100px; height: 36px; bottom: 92px; right: 13%; animation-delay: 2.5s; }

  @keyframes ripple {
    0% { opacity: 0.7; transform: scale(0.5); }
    100% { opacity: 0; transform: scale(1.5); }
  }

  .hero-content { position: relative; z-index: 2; padding-bottom: 20px; width: 100%; }

  .name-badge {
    display: inline-block;
    background: rgba(10,31,24,0.85);
    border: 1px solid rgba(94,196,122,0.5);
    border-radius: 4px;
    padding: 5px 16px;
    font-family: 'Silkscreen', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--lily-bright);
    margin-bottom: 10px;
    animation: fadeSlideDown 0.8s ease both;
  }

  .hero-title {
    font-family: 'Silkscreen', monospace;
    font-size: clamp(22px, 4.5vw, 34px);
    line-height: 1.15;
    color: var(--cream);
    margin-bottom: 6px;
    animation: fadeSlideDown 0.9s ease both;
    text-shadow: 0 0 40px rgba(46,168,154,0.5), 0 2px 8px rgba(0,0,0,0.8);
  }

  .hero-sub {
    font-size: 11px;
    color: var(--water-shimmer);
    margin-bottom: 20px;
    animation: fadeSlideDown 1s ease both;
    letter-spacing: 1px;
  }

  .typing-line {
    font-size: 12px;
    color: var(--lotus-light);
    margin-bottom: 24px;
    min-height: 18px;
    animation: fadeSlideDown 1.1s ease both;
  }

  .cursor {
    display: inline-block;
    width: 7px; height: 13px;
    background: var(--lotus-light);
    margin-left: 2px;
    vertical-align: middle;
    animation: blink 0.9s step-end infinite;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── LILY PADS SCENE (bottom of hero) ── */
  .pond-scene {
    position: relative;
    z-index: 2;
    width: 100%;
    overflow: visible;
    margin-bottom: -2px;
  }

  @keyframes fadeSlideDown {
    from { opacity: 0; transform: translateY(-14px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* Floating frog */
  .frog-hero {
    margin: 0 auto 0;
    width: 110px;
    animation: float 3.5s ease-in-out infinite, fadeSlideDown 1.2s ease both;
    position: relative; z-index: 3;
    filter: drop-shadow(0 8px 16px rgba(0,0,0,0.6));
  }
  @keyframes float {
    0%,100% { transform: translateY(0px) rotate(-1deg); }
    50%      { transform: translateY(-7px) rotate(1deg); }
  }

  /* ── WATER TRANSITION ── */
  .water-surface {
    height: 56px;
    background: linear-gradient(to bottom, rgba(13,48,40,0.6), var(--midnight));
    position: relative;
    overflow: hidden;
  }
  .water-shimmer-bar {
    position: absolute;
    left: 0; right: 0;
    height: 1px;
    background: linear-gradient(to right, transparent, rgba(46,168,154,0.4), rgba(94,196,122,0.3), rgba(46,168,154,0.4), transparent);
    top: 18px;
    animation: shimmerSlide 4s ease-in-out infinite;
  }
  .water-shimmer-bar:nth-child(2) { top: 30px; animation-delay: 1.3s; opacity: 0.6; }
  .water-shimmer-bar:nth-child(3) { top: 42px; animation-delay: 2.6s; opacity: 0.4; }
  @keyframes shimmerSlide {
    0%,100% { transform: scaleX(0.7) translateX(-5%); opacity: 0.5; }
    50%      { transform: scaleX(1.1) translateX(5%); opacity: 1; }
  }

  /* ── SECTIONS ── */
  .section {
    margin: 22px 16px 0;
    animation: riseUp 0.7s ease both;
  }
  @keyframes riseUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .section-header {
    display: flex; align-items: center; gap: 10px;
    margin-bottom: 13px;
  }
  .section-dot {
    width: 7px; height: 7px;
    background: var(--lotus-pink);
    border-radius: 50%;
    flex-shrink: 0;
    animation: pulse-dot 2.5s ease-in-out infinite;
    box-shadow: 0 0 8px rgba(212,116,138,0.5);
  }
  @keyframes pulse-dot {
    0%,100% { box-shadow: 0 0 4px rgba(212,116,138,0.4); }
    50%      { box-shadow: 0 0 12px rgba(212,116,138,0.7); }
  }
  .section-title {
    font-family: 'Silkscreen', monospace;
    font-size: 11px;
    color: var(--water-shimmer);
    letter-spacing: 2px;
  }
  .section-line {
    flex: 1; height: 1px;
    background: linear-gradient(to right, rgba(46,168,154,0.5), transparent);
  }

  /* ── ABOUT CARD ── */
  .about-card {
    background: linear-gradient(135deg, rgba(13,48,40,0.8) 0%, rgba(26,92,74,0.4) 100%);
    border: 1px solid rgba(46,168,154,0.3);
    border-radius: 10px;
    padding: 20px 22px;
    position: relative;
    overflow: hidden;
  }
  .about-card::before {
    content: '';
    position: absolute;
    top: -30px; right: -30px;
    width: 120px; height: 120px;
    background: radial-gradient(circle, rgba(212,116,138,0.12) 0%, transparent 70%);
    border-radius: 50%;
  }
  .about-card::after {
    content: '🐸';
    position: absolute;
    right: 18px; top: 16px;
    font-size: 26px;
    opacity: 0.25;
  }
  .about-text {
    font-size: 11.5px;
    line-height: 1.85;
    color: var(--cream);
    opacity: 0.92;
  }
  .about-text em {
    color: var(--lotus-light);
    font-style: normal;
    text-shadow: 0 0 10px rgba(240,168,184,0.3);
  }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
  }
  .stat-card {
    background: linear-gradient(160deg, rgba(13,48,40,0.9) 0%, rgba(16,86,104,0.5) 100%);
    border: 1px solid rgba(46,168,154,0.2);
    border-radius: 10px;
    padding: 16px 12px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.2s;
    cursor: default;
  }
  .stat-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(to right, var(--pond-jade), var(--water-shimmer));
    transform: scaleX(0);
    transition: transform 0.3s;
  }
  .stat-card:hover { border-color: rgba(46,168,154,0.6); transform: translateY(-3px); }
  .stat-card:hover::before { transform: scaleX(1); }
  .stat-num {
    font-family: 'Silkscreen', monospace;
    font-size: 20px;
    color: var(--water-shimmer);
    display: block;
    margin-bottom: 4px;
    text-shadow: 0 0 12px rgba(46,168,154,0.5);
  }
  .stat-label {
    font-size: 9px;
    color: var(--moss);
    letter-spacing: 1.5px;
    text-transform: uppercase;
  }

  /* ── SKILL PILLS ── */
  .pills-grid { display: flex; flex-wrap: wrap; gap: 7px; }
  .pill {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(10,31,24,0.85);
    border: 1px solid rgba(46,168,154,0.22);
    border-radius: 20px;
    padding: 5px 13px;
    font-size: 10.5px;
    color: var(--cream);
    letter-spacing: 0.4px;
    transition: all 0.2s;
    cursor: default;
  }
  .pill:hover {
    border-color: var(--water-shimmer);
    background: rgba(46,168,154,0.18);
    transform: scale(1.06);
  }
  .pill-dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }

  /* ── PROJECT CARDS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  .proj-card {
    background: linear-gradient(145deg, rgba(13,48,40,0.85) 0%, rgba(16,86,104,0.3) 100%);
    border: 1px solid rgba(46,168,154,0.18);
    border-radius: 10px;
    padding: 16px;
    position: relative;
    overflow: hidden;
    transition: all 0.25s;
    cursor: default;
  }
  .proj-card::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(to right, transparent, rgba(212,116,138,0.4), transparent);
    opacity: 0;
    transition: opacity 0.25s;
  }
  .proj-card:hover { border-color: rgba(46,168,154,0.5); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,0.4); }
  .proj-card:hover::after { opacity: 1; }
  .proj-card-emoji { font-size: 20px; margin-bottom: 8px; display: block; }
  .proj-card-name {
    font-family: 'Silkscreen', monospace;
    font-size: 10.5px; color: var(--water-shimmer);
    margin-bottom: 6px;
  }
  .proj-card-desc { font-size: 9.5px; color: #8ab8a0; line-height: 1.65; }
  .proj-card-lang {
    margin-top: 10px; display: flex; align-items: center;
    gap: 5px; font-size: 9.5px; color: var(--cream); opacity: 0.55;
  }
  .lang-dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }

  /* ── CONTRIBUTION GRAPH ── */
  .contrib-grid {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 2px;
    padding: 14px;
    background: rgba(10,31,24,0.7);
    border: 1px solid rgba(46,168,154,0.18);
    border-radius: 10px;
    overflow: hidden;
  }
  .contrib-cell {
    aspect-ratio: 1;
    border-radius: 2px;
    background: rgba(46,168,154,0.06);
    transition: transform 0.15s;
    cursor: default;
  }
  .contrib-cell:hover { transform: scale(1.6); z-index: 2; position: relative; }
  .c1 { background: rgba(46,168,154,0.15); }
  .c2 { background: rgba(46,168,154,0.32); }
  .c3 { background: rgba(46,168,154,0.55); }
  .c4 { background: rgba(212,116,138,0.65); }
  .c5 { background: rgba(212,116,138,0.95); }

  /* ── CONNECT ── */
  .connect-row { display: flex; gap: 8px; flex-wrap: wrap; }
  .connect-badge {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(10,31,24,0.85);
    border: 1px solid rgba(46,168,154,0.28);
    border-radius: 7px;
    padding: 7px 14px;
    font-size: 10.5px; color: var(--water-shimmer);
    text-decoration: none;
    transition: all 0.2s;
    cursor: pointer;
  }
  .connect-badge:hover {
    background: rgba(46,168,154,0.18);
    border-color: var(--water-shimmer);
    transform: translateY(-2px);
    color: var(--cream);
  }

  /* ── FOOTER SCENE ── */
  .footer-scene {
    margin: 30px 16px 0;
    text-align: center;
  }
  .footer-text {
    font-family: 'Silkscreen', monospace;
    font-size: 10px; color: var(--pond-jade);
    letter-spacing: 2px;
    animation: float 4s ease-in-out infinite;
    margin-top: 6px;
  }

  /* stagger */
  .section:nth-child(1) { animation-delay: 0.2s; }
  .section:nth-child(2) { animation-delay: 0.35s; }
  .section:nth-child(3) { animation-delay: 0.5s; }
  .section:nth-child(4) { animation-delay: 0.65s; }
  .section:nth-child(5) { animation-delay: 0.8s; }
  .section:nth-child(6) { animation-delay: 0.95s; }
</style>

<h2 class="sr-only">GitHub profile README – frog pond aesthetic with lotus flowers, koi fish, and jade water</h2>

<div class="readme-wrap">

  <!-- HERO -->
  <div class="hero">
    <div class="pond-bg"></div>

    <!-- Dappled light -->
    <div class="light-patch"></div>
    <div class="light-patch"></div>
    <div class="light-patch"></div>

    <!-- Koi fish SVGs -->
    <svg class="koi koi-1" width="52" height="22" viewBox="0 0 52 22" xmlns="http://www.w3.org/2000/svg">
      <ellipse cx="26" cy="11" rx="22" ry="8" fill="#e8834a" opacity="0.85"/>
      <ellipse cx="26" cy="11" rx="14" ry="5" fill="#f0a060" opacity="0.6"/>
      <ellipse cx="8" cy="11" rx="8" ry="8" fill="#d46030" opacity="0.7"/>
      <path d="M48 4 Q56 11 48 18" fill="#c05020" opacity="0.8"/>
      <circle cx="10" cy="9" r="1.5" fill="#1a1a1a"/>
    </svg>
    <svg class="koi koi-2" width="44" height="18" viewBox="0 0 44 18" xmlns="http://www.w3.org/2000/svg">
      <ellipse cx="22" cy="9" rx="18" ry="6.5" fill="#f0ede0" opacity="0.8"/>
      <ellipse cx="22" cy="9" rx="10" ry="4" fill="#d4a030" opacity="0.5"/>
      <ellipse cx="7" cy="9" rx="7" ry="7" fill="#e0d8c0" opacity="0.7"/>
      <path d="M40 3 Q48 9 40 15" fill="#c8c0a0" opacity="0.75"/>
      <circle cx="9" cy="7.5" r="1.5" fill="#1a1a1a"/>
    </svg>
    <svg class="koi koi-3" width="38" height="16" viewBox="0 0 38 16" xmlns="http://www.w3.org/2000/svg">
      <ellipse cx="19" cy="8" rx="15" ry="5.5" fill="#e8834a" opacity="0.7"/>
      <ellipse cx="19" cy="8" rx="8" ry="3.5" fill="#f0ede0" opacity="0.6"/>
      <ellipse cx="6" cy="8" rx="6" ry="6" fill="#d46030" opacity="0.65"/>
      <path d="M34 3 Q41 8 34 13" fill="#c05020" opacity="0.7"/>
      <circle cx="7.5" cy="6.5" r="1.2" fill="#1a1a1a"/>
    </svg>

    <!-- ripples -->
    <div class="ripple-ring"></div>
    <div class="ripple-ring"></div>
    <div class="ripple-ring"></div>
    <div class="ripple-ring"></div>
    <div class="ripple-ring"></div>

    <!-- Text content -->
    <div class="hero-content">
      <div class="name-badge">VISITOR FROM THE LILY PAD</div>
      <h1 class="hero-title">// yourname.dev</h1>
      <p class="hero-sub">somewhere in the pond · building things that hop</p>
      <div class="typing-line">
        <span id="typed-text"></span><span class="cursor"></span>
      </div>
    </div>

    <!-- Pond Scene: lily pads, lotus, frog -->
    <div class="pond-scene">
      <svg viewBox="0 0 680 220" width="100%" xmlns="http://www.w3.org/2000/svg" style="position:relative;z-index:2;">

        <!-- Water surface shimmer -->
        <ellipse cx="340" cy="200" rx="340" ry="30" fill="#0d3028" opacity="0.9"/>
        <ellipse cx="340" cy="190" rx="330" ry="20" fill="#1a5c4a" opacity="0.5"/>

        <!-- Shimmer lines on water -->
        <line x1="60" y1="195" x2="180" y2="195" stroke="rgba(46,168,154,0.25)" stroke-width="1"/>
        <line x1="260" y1="198" x2="420" y2="198" stroke="rgba(46,168,154,0.2)" stroke-width="1"/>
        <line x1="480" y1="194" x2="600" y2="194" stroke="rgba(46,168,154,0.18)" stroke-width="1"/>

        <!-- Big lily pad left -->
        <ellipse cx="120" cy="188" rx="68" ry="20" fill="#1e5c35" opacity="0.9"/>
        <ellipse cx="120" cy="185" rx="62" ry="17" fill="#2d8c6e" opacity="0.7"/>
        <path d="M120 168 L120 188" stroke="#1a4a2e" stroke-width="2" fill="none" opacity="0.6"/>
        <path d="M120 170 Q100 178 85 184" stroke="#1a4a2e" stroke-width="1" fill="none" opacity="0.4"/>
        <path d="M120 170 Q140 178 155 184" stroke="#1a4a2e" stroke-width="1" fill="none" opacity="0.4"/>
        <!-- notch -->
        <path d="M120 168 L108 182 L120 182" fill="#0d3028" opacity="0.4"/>

        <!-- Lotus on left lily pad -->
        <g transform="translate(100 162)">
          <ellipse cx="0" cy="6" rx="10" ry="4" fill="#1e5c35" opacity="0.8"/>
          <!-- petals outer -->
          <ellipse cx="0" cy="-8" rx="5" ry="9" fill="#c45c74" opacity="0.7" transform="rotate(-15 0 0)"/>
          <ellipse cx="0" cy="-8" rx="5" ry="9" fill="#c45c74" opacity="0.7" transform="rotate(15 0 0)"/>
          <ellipse cx="0" cy="-8" rx="5" ry="9" fill="#d4748a" opacity="0.8" transform="rotate(45 0 0)"/>
          <ellipse cx="0" cy="-8" rx="5" ry="9" fill="#d4748a" opacity="0.8" transform="rotate(-45 0 0)"/>
          <!-- petals inner -->
          <ellipse cx="0" cy="-6" rx="4" ry="7" fill="#e8909a" opacity="0.9" transform="rotate(0 0 0)"/>
          <ellipse cx="0" cy="-6" rx="4" ry="7" fill="#e8909a" opacity="0.9" transform="rotate(30 0 0)"/>
          <ellipse cx="0" cy="-6" rx="4" ry="7" fill="#e8909a" opacity="0.9" transform="rotate(-30 0 0)"/>
          <!-- center -->
          <circle cx="0" cy="-2" r="4.5" fill="#f5e8d0"/>
          <circle cx="0" cy="-2" r="2.5" fill="#d4a030"/>
        </g>

        <!-- Small lily pad center-left -->
        <ellipse cx="240" cy="192" rx="42" ry="12" fill="#1e5c35" opacity="0.8"/>
        <ellipse cx="240" cy="190" rx="36" ry="10" fill="#2d8c6e" opacity="0.6"/>
        <path d="M240 180 L228 190" stroke="#1a4a2e" stroke-width="1.5" fill="none" opacity="0.5"/>

        <!-- Small lily pad center-right -->
        <ellipse cx="460" cy="193" rx="38" ry="11" fill="#1e5c35" opacity="0.8"/>
        <ellipse cx="460" cy="191" rx="32" ry="9" fill="#2d8c6e" opacity="0.6"/>
        <!-- Lotus bud on this pad -->
        <g transform="translate(460 178)">
          <ellipse cx="0" cy="0" rx="4" ry="8" fill="#c45c74" opacity="0.85" transform="rotate(-10 0 0)"/>
          <ellipse cx="0" cy="0" rx="4" ry="8" fill="#d4748a" opacity="0.85" transform="rotate(10 0 0)"/>
          <ellipse cx="0" cy="-2" rx="3" ry="6" fill="#f0a8b8" opacity="0.7"/>
          <ellipse cx="0" cy="8" rx="6" ry="3" fill="#1e5c35" opacity="0.9"/>
        </g>

        <!-- Big lily pad right -->
        <ellipse cx="570" cy="187" rx="72" ry="21" fill="#1e5c35" opacity="0.9"/>
        <ellipse cx="570" cy="184" rx="64" ry="17" fill="#2d8c6e" opacity="0.65"/>
        <path d="M570 166 L570 187" stroke="#1a4a2e" stroke-width="2" fill="none" opacity="0.5"/>
        <path d="M570 168 Q550 178 535 184" stroke="#1a4a2e" stroke-width="1" fill="none" opacity="0.35"/>
        <path d="M570 168 Q590 178 605 184" stroke="#1a4a2e" stroke-width="1" fill="none" opacity="0.35"/>
        <!-- notch right -->
        <path d="M570 166 L582 180 L570 180" fill="#0d3028" opacity="0.35"/>

        <!-- Lotus on right lily pad (open/bloomed) -->
        <g transform="translate(578 158)">
          <ellipse cx="0" cy="6" rx="10" ry="4" fill="#1e5c35" opacity="0.8"/>
          <ellipse cx="0" cy="-10" rx="6" ry="10" fill="#b04060" opacity="0.6" transform="rotate(-30 0 0)"/>
          <ellipse cx="0" cy="-10" rx="6" ry="10" fill="#b04060" opacity="0.6" transform="rotate(30 0 0)"/>
          <ellipse cx="0" cy="-10" rx="6" ry="10" fill="#c45c74" opacity="0.75" transform="rotate(-60 0 0)"/>
          <ellipse cx="0" cy="-10" rx="6" ry="10" fill="#c45c74" opacity="0.75" transform="rotate(60 0 0)"/>
          <ellipse cx="0" cy="-10" rx="6" ry="10" fill="#c45c74" opacity="0.75" transform="rotate(0 0 0)"/>
          <ellipse cx="0" cy="-7" rx="5" ry="8" fill="#e8909a" opacity="0.9" transform="rotate(-20 0 0)"/>
          <ellipse cx="0" cy="-7" rx="5" ry="8" fill="#e8909a" opacity="0.9" transform="rotate(20 0 0)"/>
          <ellipse cx="0" cy="-7" rx="5" ry="8" fill="#f0a8b8" opacity="0.85" transform="rotate(0 0 0)"/>
          <circle cx="0" cy="-2" r="5" fill="#f5e8d0"/>
          <circle cx="0" cy="-2" r="3" fill="#d4a030"/>
        </g>

        <!-- MAIN FROG on the big central lily pad area -->
        <!-- Frog sitting on the left big pad -->
        <g transform="translate(320 140)">
          <!-- shadow -->
          <ellipse cx="0" cy="50" rx="30" ry="7" fill="#0a1f18" opacity="0.5"/>
          <!-- hind legs -->
          <ellipse cx="-22" cy="44" rx="14" ry="7" fill="#3d9e5a" opacity="0.8" transform="rotate(-30 -22 44)"/>
          <ellipse cx="22" cy="44" rx="14" ry="7" fill="#3d9e5a" opacity="0.8" transform="rotate(30 22 44)"/>
          <!-- body -->
          <ellipse cx="0" cy="38" rx="30" ry="22" fill="#4aac6e"/>
          <!-- belly -->
          <ellipse cx="0" cy="42" rx="19" ry="14" fill="#a8e6a8"/>
          <!-- eye bumps -->
          <ellipse cx="-20" cy="20" rx="13" ry="12" fill="#3d9e5a"/>
          <ellipse cx="20" cy="20" rx="13" ry="12" fill="#3d9e5a"/>
          <!-- eyes -->
          <circle cx="-20" cy="19" r="8" fill="#1a1a1a"/>
          <circle cx="20" cy="19" r="8" fill="#1a1a1a"/>
          <circle cx="-18" cy="17" r="3" fill="white"/>
          <circle cx="22" cy="17" r="3" fill="white"/>
          <!-- head -->
          <rect x="-20" y="26" width="40" height="14" rx="5" fill="#4aac6e"/>
          <!-- nostrils -->
          <circle cx="-7" cy="29" r="2" fill="#2d8c6e"/>
          <circle cx="7" cy="29" r="2" fill="#2d8c6e"/>
          <!-- smile -->
          <path d="M-12 38 Q0 46 12 38" stroke="#2d8c6e" stroke-width="1.8" fill="none" stroke-linecap="round"/>
          <!-- front legs -->
          <ellipse cx="-22" cy="50" rx="9" ry="5" fill="#3d9e5a" transform="rotate(-15 -22 50)"/>
          <ellipse cx="22" cy="50" rx="9" ry="5" fill="#3d9e5a" transform="rotate(15 22 50)"/>
          <!-- toes -->
          <circle cx="-30" cy="52" r="2.5" fill="#3d9e5a"/>
          <circle cx="-26" cy="55" r="2.5" fill="#3d9e5a"/>
          <circle cx="-21" cy="56" r="2.5" fill="#3d9e5a"/>
          <circle cx="30" cy="52" r="2.5" fill="#3d9e5a"/>
          <circle cx="26" cy="55" r="2.5" fill="#3d9e5a"/>
          <circle cx="21" cy="56" r="2.5" fill="#3d9e5a"/>

          <!-- lily pad under frog -->
          <ellipse cx="0" cy="56" rx="38" ry="11" fill="#1e5c35" opacity="0.95"/>
          <ellipse cx="0" cy="54" rx="34" ry="9" fill="#2d8c6e" opacity="0.7"/>
          <path d="M0 44 L0 56" stroke="#1a4a2e" stroke-width="1.5" fill="none" opacity="0.5"/>
        </g>

        <!-- Floating white flowers on water -->
        <g transform="translate(200 196)">
          <circle cx="0" cy="0" r="5" fill="white" opacity="0.6"/>
          <circle cx="8" cy="-3" r="4" fill="white" opacity="0.5"/>
          <circle cx="-6" cy="-4" r="3.5" fill="white" opacity="0.45"/>
          <circle cx="0" cy="0" r="2" fill="#d4a030" opacity="0.7"/>
        </g>
        <g transform="translate(420 200)">
          <circle cx="0" cy="0" r="4" fill="white" opacity="0.5"/>
          <circle cx="6" cy="-2" r="3" fill="white" opacity="0.4"/>
          <circle cx="-5" cy="-3" r="3" fill="white" opacity="0.4"/>
          <circle cx="0" cy="0" r="1.8" fill="#d4a030" opacity="0.65"/>
        </g>

        <!-- Dragonfly hint -->
        <g transform="translate(480 90)" opacity="0.6">
          <ellipse cx="0" cy="0" rx="1.5" ry="8" fill="#2ea89a"/>
          <ellipse cx="-14" cy="-4" rx="12" ry="3.5" fill="rgba(46,168,154,0.35)" transform="rotate(-10 -14 -4)"/>
          <ellipse cx="14" cy="-4" rx="12" ry="3.5" fill="rgba(46,168,154,0.35)" transform="rotate(10 14 -4)"/>
          <ellipse cx="-12" cy="2" rx="9" ry="2.5" fill="rgba(46,168,154,0.25)" transform="rotate(10 -12 2)"/>
          <ellipse cx="12" cy="2" rx="9" ry="2.5" fill="rgba(46,168,154,0.25)" transform="rotate(-10 12 2)"/>
          <circle cx="0" cy="-9" r="3" fill="#1e6b6b"/>
          <circle cx="-1.2" cy="-10" r="1.2" fill="rgba(255,255,255,0.5)"/>
        </g>

      </svg>
    </div>
  </div>

  <!-- water shimmer transition -->
  <div class="water-surface">
    <div class="water-shimmer-bar"></div>
    <div class="water-shimmer-bar"></div>
    <div class="water-shimmer-bar"></div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">// about.frog</span>
      <div class="section-line"></div>
    </div>
    <div class="about-card">
      <p class="about-text">
        Hey there 👋 I'm a developer who thrives in <em>still waters</em> —
        building <em>calm, reliable systems</em> that handle the chaos underneath.
        I believe good code, like a good pond, has depth you can't always see.<br><br>
        Currently leaping between <em>full-stack web dev</em>, open source,
        and building tools that make other devs' lives easier.
        When I'm not shipping, I'm somewhere watching the reflections.
      </p>
    </div>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">// pond.stats</span>
      <div class="section-line"></div>
    </div>
    <div class="stats-row">
      <div class="stat-card">
        <span class="stat-num" id="commits-num">0</span>
        <span class="stat-label">commits</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" id="repos-num">0</span>
        <span class="stat-label">repos</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" id="stars-num">0</span>
        <span class="stat-label">stars</span>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">// skills.lily</span>
      <div class="section-line"></div>
    </div>
    <div class="pills-grid">
      <span class="pill"><span class="pill-dot" style="background:#f7df1e"></span>JavaScript</span>
      <span class="pill"><span class="pill-dot" style="background:#3178c6"></span>TypeScript</span>
      <span class="pill"><span class="pill-dot" style="background:#61dafb"></span>React</span>
      <span class="pill"><span class="pill-dot" style="background:#5ec47a"></span>Node.js</span>
      <span class="pill"><span class="pill-dot" style="background:#3ecf8e"></span>Supabase</span>
      <span class="pill"><span class="pill-dot" style="background:#4285f4"></span>Go</span>
      <span class="pill"><span class="pill-dot" style="background:#d4748a"></span>Rust</span>
      <span class="pill"><span class="pill-dot" style="background:#d4a030"></span>Python</span>
      <span class="pill"><span class="pill-dot" style="background:#e34c26"></span>HTML/CSS</span>
      <span class="pill"><span class="pill-dot" style="background:#2ea89a"></span>Docker</span>
      <span class="pill"><span class="pill-dot" style="background:#a78bfa"></span>GraphQL</span>
      <span class="pill"><span class="pill-dot" style="background:#4aac6e"></span>Linux</span>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">// projects.log</span>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">
      <div class="proj-card">
        <span class="proj-card-emoji">🌿</span>
        <div class="proj-card-name">pond-ui</div>
        <div class="proj-card-desc">A calm, nature-inspired component library. No noise, just clarity.</div>
        <div class="proj-card-lang"><span class="lang-dot" style="background:#f7df1e"></span>JavaScript · 142 ⭐</div>
      </div>
      <div class="proj-card">
        <span class="proj-card-emoji">🐸</span>
        <div class="proj-card-name">hopper</div>
        <div class="proj-card-desc">Lightweight task runner that hops across services with zero config.</div>
        <div class="proj-card-lang"><span class="lang-dot" style="background:#4285f4"></span>Go · 89 ⭐</div>
      </div>
      <div class="proj-card">
        <span class="proj-card-emoji">🌊</span>
        <div class="proj-card-name">ripple-db</div>
        <div class="proj-card-desc">Event propagation system. One change, many echoes.</div>
        <div class="proj-card-lang"><span class="lang-dot" style="background:#d4748a"></span>Rust · 57 ⭐</div>
      </div>
      <div class="proj-card">
        <span class="proj-card-emoji">🍃</span>
        <div class="proj-card-name">duckweed</div>
        <div class="proj-card-desc">Tiny floating utilities. Fast, light, covers everything.</div>
        <div class="proj-card-lang"><span class="lang-dot" style="background:#3178c6"></span>TypeScript · 203 ⭐</div>
      </div>
    </div>
  </div>

  <!-- CONTRIBUTIONS -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">// pond.activity</span>
      <div class="section-line"></div>
    </div>
    <div class="contrib-grid" id="contrib-grid"></div>
  </div>

  <!-- CONNECT -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <span class="section-title">// find.me</span>
      <div class="section-line"></div>
    </div>
    <div class="connect-row">
      <span class="connect-badge">🐦 @yourhandle</span>
      <span class="connect-badge">💼 linkedin</span>
      <span class="connect-badge">🌐 yoursite.dev</span>
      <span class="connect-badge">📬 hello@yoursite.dev</span>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer-scene">
    <svg viewBox="0 0 400 60" width="100%" xmlns="http://www.w3.org/2000/svg">
      <ellipse cx="200" cy="48" rx="190" ry="10" fill="#1a5c4a" opacity="0.4"/>
      <!-- small frog left -->
      <g transform="translate(60 18)">
        <ellipse cx="-5" cy="4" rx="5" ry="5" fill="#3d9e5a"/>
        <ellipse cx="5" cy="4" rx="5" ry="5" fill="#3d9e5a"/>
        <ellipse cx="0" cy="6" rx="10" ry="7" fill="#4aac6e"/>
        <circle cx="-4" cy="4" r="2" fill="#1a1a1a"/>
        <circle cx="4" cy="4" r="2" fill="#1a1a1a"/>
        <circle cx="-3" cy="3" r="0.8" fill="white"/>
        <circle cx="5" cy="3" r="0.8" fill="white"/>
        <ellipse cx="0" cy="13" rx="14" ry="4" fill="#1e5c35" opacity="0.9"/>
      </g>
      <!-- small frog right -->
      <g transform="translate(330 20)">
        <ellipse cx="-5" cy="4" rx="5" ry="5" fill="#3d9e5a"/>
        <ellipse cx="5" cy="4" rx="5" ry="5" fill="#3d9e5a"/>
        <ellipse cx="0" cy="6" rx="10" ry="7" fill="#4aac6e"/>
        <circle cx="-4" cy="4" r="2" fill="#1a1a1a"/>
        <circle cx="4" cy="4" r="2" fill="#1a1a1a"/>
        <circle cx="-3" cy="3" r="0.8" fill="white"/>
        <circle cx="5" cy="3" r="0.8" fill="white"/>
        <ellipse cx="0" cy="13" rx="14" ry="4" fill="#1e5c35" opacity="0.9"/>
      </g>
      <!-- lily pads -->
      <ellipse cx="140" cy="47" rx="30" ry="7" fill="#1e5c35" opacity="0.75"/>
      <ellipse cx="270" cy="46" rx="24" ry="6" fill="#1e5c35" opacity="0.7"/>
      <!-- lotus buds -->
      <g transform="translate(200 38)">
        <ellipse cx="0" cy="0" rx="3" ry="6" fill="#d4748a" opacity="0.8"/>
        <ellipse cx="4" cy="2" rx="3" ry="5" fill="#c45c74" opacity="0.7"/>
        <ellipse cx="0" cy="6" rx="6" ry="2.5" fill="#1e5c35" opacity="0.9"/>
      </g>
    </svg>
    <p class="footer-text">*ribbit* · crafted with 🐸 in the pond · *plop*</p>
  </div>

</div>

<script>
  const phrases = [
    'building things that hop',
    'debugging at dawn',
    'shipping from the lily pad',
    'making ripples in the pond',
    'watching koi between commits',
  ];
  let pi = 0, ci = 0, deleting = false;
  const el = document.getElementById('typed-text');
  function type() {
    const phrase = phrases[pi];
    if (!deleting) {
      el.textContent = phrase.slice(0, ++ci);
      if (ci === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = phrase.slice(0, --ci);
      if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
    }
    setTimeout(type, deleting ? 38 : 75);
  }
  type();

  function countUp(id, target) {
    const el = document.getElementById(id);
    let v = 0;
    const step = Math.max(1, Math.ceil(target / 60));
    const t = setInterval(() => {
      v = Math.min(v + step, target);
      el.textContent = v;
      if (v >= target) clearInterval(t);
    }, 22);
  }
  setTimeout(() => {
    countUp('commits-num', 1247);
    countUp('repos-num', 34);
    countUp('stars-num', 491);
  }, 600);

  const grid = document.getElementById('contrib-grid');
  for (let i = 0; i < 52 * 7; i++) {
    const cell = document.createElement('div');
    cell.className = 'contrib-cell';
    const r = Math.random();
    if (r > 0.55) {
      const idx = r > 0.93 ? 5 : r > 0.85 ? 4 : r > 0.75 ? 3 : r > 0.65 ? 2 : 1;
      cell.classList.add(['','c1','c2','c3','c4','c5'][idx]);
    }
    grid.appendChild(cell);
  }
</script>
