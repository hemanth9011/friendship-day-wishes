<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
<title>Happy Friendship Day 💙</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,500&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --navy-deep:#0a0f24;
    --navy-mid:#141b3d;
    --navy-soft:#232c5c;
    --blue-glow:#5eb8ff;
    --gold:#ffcf6b;
    --rose:#ff7fa8;
    --ink-light:#f3f2ff;
    --ink-muted:#aab0d8;
    --glass-border:rgba(255,255,255,0.16);
    font-size:16px;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html,body{
    height:100%;
    width:100%;
    overflow-x:hidden;
    background:var(--navy-deep);
    font-family:'Quicksand', sans-serif;
    color:var(--ink-light);
    -webkit-font-smoothing:antialiased;
  }
  ::selection{background:var(--blue-glow); color:var(--navy-deep);}

  .display{font-family:'Fraunces', serif;}

  /* ============ Layers ============ */
  #bg-gradient{
    position:fixed; inset:0; z-index:0;
    background:
      radial-gradient(circle at 15% 20%, rgba(94,184,255,0.22), transparent 45%),
      radial-gradient(circle at 85% 15%, rgba(255,127,168,0.18), transparent 50%),
      radial-gradient(circle at 50% 90%, rgba(255,207,107,0.12), transparent 55%),
      linear-gradient(120deg, var(--navy-deep), var(--navy-mid), var(--navy-soft), var(--navy-mid), var(--navy-deep));
    background-size:200% 200%, 200% 200%, 200% 200%, 400% 400%;
    animation: driftGrad 18s ease-in-out infinite;
  }
  @keyframes driftGrad{
    0%{background-position:0% 0%, 100% 0%, 50% 100%, 0% 50%;}
    50%{background-position:100% 100%, 0% 100%, 50% 0%, 100% 50%;}
    100%{background-position:0% 0%, 100% 0%, 50% 100%, 0% 50%;}
  }

  #stars{position:fixed; inset:0; z-index:1; pointer-events:none;}
  .star{
    position:absolute; border-radius:50%;
    background:var(--ink-light);
    opacity:.5;
    animation:twinkle 3.5s ease-in-out infinite;
  }
  @keyframes twinkle{0%,100%{opacity:.15; transform:scale(1);} 50%{opacity:.9; transform:scale(1.4);}}

  #hearts-layer, #confetti-layer, #fireworks-layer, #particles-layer{
    position:fixed; inset:0; z-index:2; pointer-events:none; overflow:hidden;
  }

  .heart{
    position:absolute;
    top:-10%;
    font-size:1.2rem;
    color:var(--rose);
    filter:drop-shadow(0 0 6px rgba(255,127,168,.8));
    animation-name:fall;
    animation-timing-function:linear;
    animation-iteration-count:infinite;
    will-change:transform;
    opacity:.85;
  }
  @keyframes fall{
    0%{transform:translateY(-10vh) translateX(0) rotate(0deg); opacity:0;}
    10%{opacity:.9;}
    100%{transform:translateY(115vh) translateX(var(--drift,20px)) rotate(360deg); opacity:.2;}
  }

  .particle{
    position:absolute; border-radius:50%;
    background:radial-gradient(circle, var(--blue-glow), transparent 70%);
    filter:blur(1px);
    animation:floatUp linear infinite;
    opacity:.6;
  }
  @keyframes floatUp{
    0%{transform:translateY(10vh) translateX(0); opacity:0;}
    15%{opacity:.7;}
    100%{transform:translateY(-110vh) translateX(var(--drift,0px)); opacity:0;}
  }

  .firework{position:absolute; width:4px; height:4px; border-radius:50%;}

  .confetti-piece{
    position:absolute; top:-5%;
    width:8px; height:14px;
    opacity:.95;
    animation-name:confettiFall;
    animation-timing-function:cubic-bezier(.35,.55,.6,1);
    animation-iteration-count:1;
    animation-fill-mode:forwards;
  }
  @keyframes confettiFall{
    0%{transform:translateY(-10vh) rotate(0deg); opacity:1;}
    90%{opacity:1;}
    100%{transform:translateY(110vh) rotate(720deg); opacity:0;}
  }

  /* ============ Utility controls (mute button, floating) ============ */
  #sound-toggle{
    position:fixed; top:18px; right:18px; z-index:50;
    width:50px; height:50px; border-radius:50%;
    background:rgba(255,255,255,0.08);
    border:1px solid var(--glass-border);
    backdrop-filter:blur(10px);
    color:var(--ink-light);
    display:flex; align-items:center; justify-content:center;
    font-size:1.3rem; cursor:pointer;
    transition:transform .25s ease, box-shadow .25s ease, background .25s ease;
    box-shadow:0 0 0 rgba(94,184,255,0);
  }
  #sound-toggle:hover{transform:scale(1.08); background:rgba(255,255,255,0.15); box-shadow:0 0 18px rgba(94,184,255,.5);}
  #sound-toggle:active{transform:scale(0.95);}

  /* ============ Page wrapper / transitions ============ */
  .page{
    position:relative; z-index:5;
    min-height:100vh; width:100%;
    display:flex; align-items:center; justify-content:center;
    padding:24px;
    transition:opacity .6s ease, filter .6s ease;
  }
  .page.hidden-page{
    display:none;
  }
  .fade-out{opacity:0; filter:blur(6px);}
  .fade-in-page{animation:pageFadeIn .8s ease forwards;}
  @keyframes pageFadeIn{
    from{opacity:0; filter:blur(10px); transform:scale(1.02);}
    to{opacity:1; filter:blur(0); transform:scale(1);}
  }

  /* ============ Glass card / login ============ */
  .glass-card{
    width:100%; max-width:460px;
    background:rgba(255,255,255,0.06);
    border:1px solid var(--glass-border);
    border-radius:28px;
    backdrop-filter:blur(22px) saturate(140%);
    -webkit-backdrop-filter:blur(22px) saturate(140%);
    box-shadow:0 8px 40px rgba(0,0,0,0.45), inset 0 1px 0 rgba(255,255,255,0.15);
    padding:48px 36px 40px;
    text-align:center;
    animation:cardIn 1s cubic-bezier(.2,.9,.25,1) forwards;
    opacity:0;
    transform:translateY(24px) scale(.97);
  }
  @keyframes cardIn{
    to{opacity:1; transform:translateY(0) scale(1);}
  }

  .emblem{
    font-size:2.6rem;
    margin-bottom:6px;
    animation:handshake 2.6s ease-in-out infinite;
    display:inline-block;
  }
  @keyframes handshake{
    0%,100%{transform:rotate(0deg);}
    10%{transform:rotate(-8deg);}
    20%{transform:rotate(8deg);}
    30%{transform:rotate(-6deg);}
    40%{transform:rotate(0deg);}
  }

  .title-main{
    font-family:'Fraunces', serif;
    font-weight:600;
    font-size:clamp(1.7rem, 5vw, 2.35rem);
    line-height:1.25;
    letter-spacing:.2px;
    background:linear-gradient(90deg, var(--blue-glow), var(--ink-light) 45%, var(--gold));
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
    margin:6px 0 6px;
  }

  .subtitle{
    color:var(--ink-muted);
    font-size:.95rem;
    margin-bottom:32px;
    letter-spacing:.4px;
  }

  .input-wrap{
    position:relative;
    margin-bottom:28px;
  }
  #nameInput{
    width:100%;
    padding:16px 18px;
    font-family:'Quicksand', sans-serif;
    font-size:1.05rem;
    font-weight:500;
    color:var(--ink-light);
    background:rgba(255,255,255,0.05);
    border:1.5px solid var(--glass-border);
    border-radius:14px;
    outline:none;
    transition:border-color .3s ease, box-shadow .3s ease, background .3s ease;
  }
  #nameInput::placeholder{color:var(--ink-muted);}
  #nameInput:focus{
    border-color:var(--blue-glow);
    background:rgba(94,184,255,0.06);
    box-shadow:0 0 0 4px rgba(94,184,255,0.15), 0 0 24px rgba(94,184,255,0.25);
  }
  #nameInput.shake{animation:shakeInput .45s ease;}
  @keyframes shakeInput{
    0%,100%{transform:translateX(0);}
    20%{transform:translateX(-8px);}
    40%{transform:translateX(8px);}
    60%{transform:translateX(-6px);}
    80%{transform:translateX(6px);}
  }

  .glow-btn{
    position:relative;
    width:100%;
    padding:16px 20px;
    font-family:'Quicksand', sans-serif;
    font-size:1.05rem;
    font-weight:700;
    letter-spacing:.5px;
    color:var(--navy-deep);
    background:linear-gradient(120deg, var(--blue-glow), var(--gold) 60%, var(--rose));
    background-size:200% 200%;
    border:none;
    border-radius:14px;
    cursor:pointer;
    overflow:hidden;
    animation:btnGradient 5s ease infinite, btnPulse 2.6s ease-in-out infinite;
    transition:transform .2s ease;
  }
  .glow-btn:hover{transform:translateY(-2px) scale(1.015);}
  .glow-btn:active{transform:translateY(0) scale(.98);}
  @keyframes btnGradient{
    0%{background-position:0% 50%;}
    50%{background-position:100% 50%;}
    100%{background-position:0% 50%;}
  }
  @keyframes btnPulse{
    0%,100%{box-shadow:0 0 14px rgba(94,184,255,.45), 0 0 0 rgba(255,207,107,0);}
    50%{box-shadow:0 0 30px rgba(94,184,255,.7), 0 0 44px rgba(255,207,107,.35);}
  }

  /* alert toast */
  #alert-toast{
    position:fixed;
    left:50%; top:26px;
    transform:translate(-50%, -140%);
    z-index:80;
    background:rgba(255,127,168,0.14);
    border:1px solid rgba(255,127,168,0.5);
    backdrop-filter:blur(16px);
    color:var(--ink-light);
    padding:14px 26px;
    border-radius:16px;
    font-weight:600;
    font-size:.95rem;
    display:flex; align-items:center; gap:10px;
    box-shadow:0 8px 30px rgba(255,127,168,.25);
    transition:transform .5s cubic-bezier(.2,.9,.25,1);
    white-space:nowrap;
  }
  #alert-toast.show{transform:translate(-50%, 0%);}

  /* ============ Celebration page ============ */
  #page-celebrate{
    flex-direction:column;
    padding-top:70px;
    padding-bottom:60px;
  }

  .celebrate-inner{
    width:100%; max-width:720px;
    display:flex; flex-direction:column; align-items:center;
    text-align:center;
  }

  .congrats-wrap{
    margin-bottom:18px;
  }
  .congrats-emoji{
    font-size:3rem;
    animation:zoomPop 1s cubic-bezier(.2,.9,.25,1);
  }
  @keyframes zoomPop{
    0%{transform:scale(0); opacity:0;}
    60%{transform:scale(1.15); opacity:1;}
    100%{transform:scale(1);}
  }
  .congrats-title{
    font-family:'Fraunces', serif;
    font-weight:700;
    font-size:clamp(1.9rem, 6vw, 2.8rem);
    margin:8px 0 4px;
    background:linear-gradient(90deg, var(--gold), var(--rose), var(--blue-glow));
    -webkit-background-clip:text; background-clip:text; color:transparent;
    animation:zoomPop 1.1s cubic-bezier(.2,.9,.25,1);
  }
  .congrats-sub{
    font-family:'Fraunces', serif;
    font-style:italic;
    font-weight:500;
    font-size:clamp(1.1rem, 3.4vw, 1.5rem);
    color:var(--ink-light);
    animation:zoomPop 1.3s cubic-bezier(.2,.9,.25,1);
  }
  .bfl{color:var(--rose); font-weight:700; font-style:normal;}

  .wish-card{
    margin-top:34px;
    width:100%;
    background:rgba(255,255,255,0.05);
    border:1px solid var(--glass-border);
    border-radius:24px;
    backdrop-filter:blur(18px) saturate(140%);
    -webkit-backdrop-filter:blur(18px) saturate(140%);
    box-shadow:0 8px 40px rgba(0,0,0,0.4), inset 0 1px 0 rgba(255,255,255,.12);
    padding:34px 30px;
    text-align:left;
    opacity:0;
    animation:fadeUp 1s ease forwards;
    animation-delay:.4s;
  }
  @keyframes fadeUp{
    from{opacity:0; transform:translateY(30px);}
    to{opacity:1; transform:translateY(0);}
  }
  .wish-greeting{
    font-family:'Fraunces', serif;
    font-size:1.25rem;
    font-weight:600;
    color:var(--blue-glow);
    margin-bottom:14px;
  }
  #typedWish{
    font-size:1.02rem;
    line-height:1.75;
    color:var(--ink-light);
    min-height:180px;
  }
  #typedWish .cursor{
    display:inline-block;
    width:2px; height:1.1em;
    background:var(--gold);
    margin-left:2px;
    vertical-align:middle;
    animation:blink 1s steps(1) infinite;
  }
  @keyframes blink{50%{opacity:0;}}

  .quote-box{
    margin-top:26px;
    width:100%;
    text-align:center;
    padding:18px 22px;
    border-left:3px solid var(--gold);
    border-radius:8px;
    background:rgba(255,207,107,0.06);
    opacity:0;
    animation:fadeUp 1s ease forwards;
    animation-delay:.8s;
  }
  #quoteText{
    font-family:'Fraunces', serif;
    font-style:italic;
    font-size:1.02rem;
    color:var(--ink-light);
    transition:opacity .4s ease;
  }

  .action-row{
    margin-top:32px;
    display:flex; flex-wrap:wrap; gap:14px; justify-content:center;
    opacity:0;
    animation:fadeUp 1s ease forwards;
    animation-delay:1s;
  }
  .action-btn{
    padding:13px 22px;
    border-radius:12px;
    font-family:'Quicksand', sans-serif;
    font-weight:600;
    font-size:.92rem;
    cursor:pointer;
    border:1px solid var(--glass-border);
    background:rgba(255,255,255,0.06);
    color:var(--ink-light);
    display:flex; align-items:center; gap:8px;
    backdrop-filter:blur(10px);
    transition:transform .25s ease, box-shadow .25s ease, background .25s ease;
  }
  .action-btn:hover{
    transform:translateY(-2px);
    background:rgba(255,255,255,0.12);
    box-shadow:0 6px 20px rgba(94,184,255,.25);
  }
  .action-btn:active{transform:translateY(0);}
  .action-btn.primary{
    background:linear-gradient(120deg, var(--blue-glow), var(--rose));
    color:var(--navy-deep);
    border:none;
    font-weight:700;
  }

  .signoff{
    margin-top:50px;
    width:100%;
    text-align:center;
    opacity:0;
    animation:fadeUp 1.2s ease forwards;
    animation-delay:1.2s;
  }
  .divider{
    color:var(--ink-muted);
    letter-spacing:4px;
    font-size:.8rem;
    margin-bottom:14px;
  }
  .signoff-label{
    color:var(--ink-muted);
    font-size:.85rem;
    letter-spacing:1px;
    margin-bottom:6px;
  }
  .signoff-name{
    font-family:'Fraunces', serif;
    font-weight:700;
    font-size:1.5rem;
    color:var(--rose);
    margin-bottom:6px;
    text-shadow:0 0 18px rgba(255,127,168,.4);
  }
  .signoff-tag{
    color:var(--blue-glow);
    font-size:.9rem;
    font-weight:600;
    letter-spacing:.5px;
  }

  footer{
    margin-top:40px;
    text-align:center;
    color:var(--ink-muted);
    font-size:.85rem;
    letter-spacing:.3px;
    opacity:0;
    animation:fadeUp 1.2s ease forwards;
    animation-delay:1.4s;
  }
  footer .heart-ico{color:var(--rose);}
  footer .yr{color:var(--gold); font-weight:700;}

  /* responsive tweaks */
  @media (max-width:480px){
    .glass-card{padding:38px 22px 30px; border-radius:22px;}
    .wish-card{padding:26px 20px;}
    .action-row{gap:10px;}
    .action-btn{flex:1 1 40%; justify-content:center; font-size:.85rem; padding:12px 14px;}
  }

  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important;}
  }
</style>
</head>
<body>

<div id="bg-gradient"></div>
<div id="stars"></div>
<div id="hearts-layer"></div>
<div id="particles-layer"></div>
<div id="fireworks-layer"></div>
<div id="confetti-layer"></div>

<button id="sound-toggle" aria-label="Toggle music" title="Toggle music">🔇</button>
<div id="alert-toast" role="alert">⚠️ <span>Please enter your name to continue 💙</span></div>

<!-- LOGIN PAGE -->
<section class="page" id="page-login">
  <div class="glass-card">
    <span class="emblem">🤝</span>
    <h1 class="title-main">Happy Friendship Day 💙</h1>
    <p class="subtitle">Someone special has a message just for you</p>
    <div class="input-wrap">
      <input type="text" id="nameInput" placeholder="Enter Your Name" maxlength="40" autocomplete="off">
    </div>
    <button class="glow-btn" id="loginBtn">Login ✨</button>
  </div>
</section>

<!-- CELEBRATION PAGE -->
<section class="page hidden-page" id="page-celebrate">
  <div class="celebrate-inner">
    <div class="congrats-wrap">
      <div class="congrats-emoji">🎉</div>
      <h2 class="congrats-title">Congratulations!</h2>
      <p class="congrats-sub">You're added to my<br><span class="bfl">❤️ Best Friend List ❤️</span></p>
    </div>

    <div class="wish-card">
      <div class="wish-greeting" id="wishGreeting">Dear Friend 💙,</div>
      <div id="typedWish"><span class="cursor"></span></div>
    </div>

    <div class="quote-box">
      <p id="quoteText"></p>
    </div>

    <div class="action-row">
      <button class="action-btn primary" id="shareBtn">🔗 Share with Friends</button>
      <button class="action-btn" id="replayBtn">🔁 Replay Celebration</button>
    </div>

    <div class="signoff">
      <div class="divider">──────────────────────────</div>
      <div class="signoff-label">💙 Wishes From 💙</div>
      <div class="signoff-name">❤️ Hemanth Adapa ❤️</div>
      <div class="signoff-tag">Forever Friends 🤝</div>
    </div>

    <footer>
      Made with <span class="heart-ico">❤️</span> by Hemanth Adapa &nbsp;·&nbsp; <span class="yr" id="yearNow"></span>
    </footer>
  </div>
</section>

<script>
(function(){
  "use strict";

  /* ---------- Utility ---------- */
  const $ = (sel) => document.querySelector(sel);
  const rand = (min, max) => Math.random() * (max - min) + min;

  document.getElementById('yearNow').textContent = new Date().getFullYear();

  /* ---------- Background stars ---------- */
  const starsLayer = $('#stars');
  const starCount = window.innerWidth < 600 ? 40 : 80;
  for(let i=0;i<starCount;i++){
    const s = document.createElement('div');
    s.className = 'star';
    const size = rand(1,2.6);
    s.style.width = size+'px';
    s.style.height = size+'px';
    s.style.left = rand(0,100)+'vw';
    s.style.top = rand(0,100)+'vh';
    s.style.animationDelay = rand(0,3.5)+'s';
    s.style.animationDuration = rand(2.5,5)+'s';
    starsLayer.appendChild(s);
  }

  /* ---------- Falling hearts (continuous, both pages) ---------- */
  const heartsLayer = $('#hearts-layer');
  const heartGlyphs = ['💙','💖','💗','💕','🤍','💛'];
  function spawnHeart(){
    const h = document.createElement('div');
    h.className = 'heart';
    h.textContent = heartGlyphs[Math.floor(rand(0,heartGlyphs.length))];
    h.style.left = rand(0,100)+'vw';
    h.style.fontSize = rand(0.9,1.8)+'rem';
    h.style.setProperty('--drift', rand(-60,60)+'px');
    const dur = rand(7,14);
    h.style.animationDuration = dur+'s';
    heartsLayer.appendChild(h);
    setTimeout(()=>h.remove(), dur*1000 + 200);
  }
  for(let i=0;i<10;i++) setTimeout(spawnHeart, i*400);
  setInterval(spawnHeart, 900);

  /* ---------- Floating glowing particles ---------- */
  const particlesLayer = $('#particles-layer');
  function spawnParticle(){
    const p = document.createElement('div');
    p.className = 'particle';
    const size = rand(4,10);
    p.style.width = size+'px';
    p.style.height = size+'px';
    p.style.left = rand(0,100)+'vw';
    p.style.setProperty('--drift', rand(-40,40)+'px');
    const dur = rand(9,18);
    p.style.animationDuration = dur+'s';
    particlesLayer.appendChild(p);
    setTimeout(()=>p.remove(), dur*1000+200);
  }
  for(let i=0;i<14;i++) setTimeout(spawnParticle, i*300);
  setInterval(spawnParticle, 1200);

  /* ---------- Fireworks (canvas-free, DOM particle burst) ---------- */
  const fwLayer = $('#fireworks-layer');
  const fwColors = ['#5eb8ff','#ffcf6b','#ff7fa8','#ffffff','#8fd3ff'];
  function burstFirework(x, y){
    const particleCount = 22;
    for(let i=0;i<particleCount;i++){
      const f = document.createElement('div');
      f.className = 'firework';
      const angle = (Math.PI*2*i)/particleCount;
      const dist = rand(60,140);
      const color = fwColors[Math.floor(rand(0,fwColors.length))];
      f.style.left = x+'px';
      f.style.top = y+'px';
      f.style.background = color;
      f.style.boxShadow = '0 0 8px '+color+', 0 0 16px '+color;
      f.style.transition = 'transform 1.1s cubic-bezier(.15,.7,.3,1), opacity 1.1s ease';
      fwLayer.appendChild(f);
      requestAnimationFrame(()=>{
        f.style.transform = `translate(${Math.cos(angle)*dist}px, ${Math.sin(angle)*dist + 40}px)`;
        f.style.opacity = '0';
      });
      setTimeout(()=>f.remove(), 1200);
    }
  }
  let fireworksTimer = null;
  function startFireworks(){
    stopFireworks();
    fireworksTimer = setInterval(()=>{
      const x = rand(window.innerWidth*0.1, window.innerWidth*0.9);
      const y = rand(window.innerHeight*0.1, window.innerHeight*0.55);
      burstFirework(x,y);
    }, 1000);
  }
  function stopFireworks(){
    if(fireworksTimer){ clearInterval(fireworksTimer); fireworksTimer = null; }
  }

  /* ---------- Confetti burst ---------- */
  const confettiLayer = $('#confetti-layer');
  const confettiColors = ['#5eb8ff','#ffcf6b','#ff7fa8','#f3f2ff','#8fd3ff','#ffe08a'];
  function launchConfetti(count){
    count = count || 130;
    for(let i=0;i<count;i++){
      const c = document.createElement('div');
      c.className = 'confetti-piece';
      c.style.left = rand(0,100)+'vw';
      c.style.background = confettiColors[Math.floor(rand(0,confettiColors.length))];
      const isCircle = Math.random() > 0.5;
      if(isCircle){ c.style.borderRadius = '50%'; c.style.width = '9px'; c.style.height='9px'; }
      const dur = rand(2.6,4.6);
      c.style.animationDuration = dur+'s';
      c.style.animationDelay = rand(0,0.6)+'s';
      confettiLayer.appendChild(c);
      setTimeout(()=>c.remove(), (dur+0.7)*1000);
    }
  }

  /* ---------- Ambient instrumental music (generated, no external file) ---------- */
  let audioCtx = null;
  let musicNodes = [];
  let musicPlaying = false;
  const soundBtn = $('#sound-toggle');

  function initAudio(){
    if(audioCtx) return;
    try{
      audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    }catch(e){ audioCtx = null; }
  }

  function startMusic(){
    if(!audioCtx || musicPlaying) return;
    musicPlaying = true;
    const masterGain = audioCtx.createGain();
    masterGain.gain.value = 0.05;
    masterGain.connect(audioCtx.destination);

    // gentle arpeggio pad — friendly major scale tones
    const notes = [261.63, 329.63, 392.00, 523.25, 392.00, 329.63]; // C E G C G E
    let step = 0;

    function pluck(){
      if(!musicPlaying) return;
      const osc = audioCtx.createOscillator();
      const g = audioCtx.createGain();
      osc.type = 'sine';
      osc.frequency.value = notes[step % notes.length];
      g.gain.value = 0;
      osc.connect(g);
      g.connect(masterGain);
      const now = audioCtx.currentTime;
      g.gain.linearRampToValueAtTime(0.6, now + 0.05);
      g.gain.exponentialRampToValueAtTime(0.001, now + 1.6);
      osc.start(now);
      osc.stop(now + 1.7);
      step++;
      musicNodes.push(osc);
      musicTimer = setTimeout(pluck, 900);
    }
    let musicTimer = setTimeout(pluck, 0);
    musicNodes.push({ stop: ()=>clearTimeout(musicTimer) });

    // soft pad drone underneath
    const pad = audioCtx.createOscillator();
    const padGain = audioCtx.createGain();
    pad.type = 'sine';
    pad.frequency.value = 130.81; // C3
    padGain.gain.value = 0.02;
    pad.connect(padGain);
    padGain.connect(masterGain);
    pad.start();
    musicNodes.push(pad);

    window.__musicStop = function(){
      musicPlaying = false;
      musicNodes.forEach(n=>{ try{ n.stop && n.stop(); }catch(e){} });
      musicNodes = [];
    };
  }

  function stopMusic(){
    if(window.__musicStop) window.__musicStop();
    musicPlaying = false;
  }

  let soundOn = false;
  soundBtn.addEventListener('click', function(){
    initAudio();
    if(audioCtx && audioCtx.state === 'suspended') audioCtx.resume();
    soundOn = !soundOn;
    if(soundOn){
      startMusic();
      soundBtn.textContent = '🔊';
    } else {
      stopMusic();
      soundBtn.textContent = '🔇';
    }
  });

  /* ---------- Alert toast ---------- */
  const alertToast = $('#alert-toast');
  let toastTimer = null;
  function showAlert(msg){
    alertToast.querySelector('span').textContent = msg;
    alertToast.classList.add('show');
    clearTimeout(toastTimer);
    toastTimer = setTimeout(()=>alertToast.classList.remove('show'), 2800);
  }

  /* ---------- Typing animation ---------- */
  const wishParagraphs = [
`Happy Friendship Day! 🤝💙`,
`A true friend is someone who stands by you through every high and low, makes life brighter with laughter, and turns ordinary moments into unforgettable memories.`,
`Thank you for being a part of my journey. Wishing you endless happiness, success, good health, and countless beautiful memories. May our friendship continue to grow stronger with every passing year.`,
`Have an amazing Friendship Day! 🌸✨`
  ];

  let typingActive = false;
  function typeWish(){
    const container = $('#typedWish');
    container.innerHTML = '<span class="cursor"></span>';
    const cursor = container.querySelector('.cursor');
    typingActive = true;

    let pIndex = 0;
    function typeParagraph(){
      if(!typingActive) return;
      if(pIndex >= wishParagraphs.length){
        return;
      }
      const p = document.createElement('p');
      p.style.marginBottom = '14px';
      container.insertBefore(p, cursor);
      const text = wishParagraphs[pIndex];
      let cIndex = 0;
      const speed = 18;
      (function typeChar(){
        if(!typingActive) return;
        if(cIndex < text.length){
          p.textContent += text.charAt(cIndex);
          cIndex++;
          setTimeout(typeChar, speed);
        } else {
          pIndex++;
          setTimeout(typeParagraph, 350);
        }
      })();
    }
    typeParagraph();
  }

  /* ---------- Friendship quotes rotator ---------- */
  const quotes = [
    "A good friend knows all your stories. A best friend helped you write them.",
    "Friendship isn't about who you've known the longest, it's about who walked in and never left.",
    "Good friends are like stars — you don't always see them, but you know they're always there.",
    "A true friend is the greatest of all blessings.",
    "Friends are the family we choose for ourselves.",
    "In the cookie of life, friends are the chocolate chips."
  ];
  let quoteIndex = 0;
  let quoteTimer = null;
  function rotateQuotes(){
    const el = $('#quoteText');
    el.style.opacity = 0;
    setTimeout(()=>{
      el.textContent = '“' + quotes[quoteIndex % quotes.length] + '”';
      el.style.opacity = 1;
      quoteIndex++;
    }, 400);
  }

  /* ---------- Page transition logic ---------- */
  const pageLogin = $('#page-login');
  const pageCelebrate = $('#page-celebrate');
  const nameInput = $('#nameInput');
  const loginBtn = $('#loginBtn');
  let currentName = 'Friend';

  function goToCelebration(name){
    currentName = name;
    pageLogin.classList.add('fade-out');
    setTimeout(()=>{
      pageLogin.classList.add('hidden-page');
      pageLogin.classList.remove('fade-out');
      pageCelebrate.classList.remove('hidden-page');
      pageCelebrate.classList.add('fade-in-page');
      $('#wishGreeting').textContent = 'Dear ' + name + ' 💙,';
      launchCelebrationSequence();
    }, 550);
  }

  function launchCelebrationSequence(){
    launchConfetti(150);
    startFireworks();
    typeWish();
    clearInterval(quoteTimer);
    rotateQuotes();
    quoteTimer = setInterval(rotateQuotes, 5000);
    // extra confetti bursts for a richer celebration
    setTimeout(()=>launchConfetti(60), 1200);
    setTimeout(()=>launchConfetti(60), 2400);
  }

  loginBtn.addEventListener('click', function(){
    const name = nameInput.value.trim();
    if(!name){
      showAlert('Please enter your name to continue 💙');
      nameInput.classList.remove('shake');
      void nameInput.offsetWidth;
      nameInput.classList.add('shake');
      nameInput.focus();
      return;
    }
    goToCelebration(name);
  });

  nameInput.addEventListener('keydown', function(e){
    if(e.key === 'Enter') loginBtn.click();
  });

  /* ---------- Share with Friends ---------- */
  $('#shareBtn').addEventListener('click', async function(){
    const shareData = {
      title: 'Happy Friendship Day 💙',
      text: `${currentName}, you're on my Best Friend List! 🤝💙 Happy Friendship Day!`,
      url: window.location.href
    };
    try{
      if(navigator.share){
        await navigator.share(shareData);
      } else {
        await navigator.clipboard.writeText(shareData.url);
        showAlert('Link copied to clipboard! Share it with your friends 💙');
      }
    }catch(err){
      try{
        await navigator.clipboard.writeText(window.location.href);
        showAlert('Link copied to clipboard! 💙');
      }catch(e2){
        showAlert('Could not share — copy the link manually 💙');
      }
    }
  });

  /* ---------- Replay Celebration ---------- */
  $('#replayBtn').addEventListener('click', function(){
    typingActive = false;
    setTimeout(()=>{
      launchCelebrationSequence();
    }, 60);
  });

})();
</script>
</body>
</html>
