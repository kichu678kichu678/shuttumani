<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Valentine Universe 🌙💗</title>

<style>
  :root{
    --pink:#ff4da6;
    --pink2:#ff6fa5;
    --blue:#3aa0ff;
    --bg:#000;
    --card:#0f0f0f;
  }

  *{box-sizing:border-box}
  body{
    margin:0;
    background:var(--bg);
    color:#fff;
    font-family:Arial, sans-serif;
    overflow:hidden; /* we control scrolling per page */
    text-align:center;
  }

  /* ===== PAGES ===== */
  .page{
    position:fixed; inset:0;
    display:none;
    padding:18px;
  }
  .page.active{display:block;}
  .scrollPage{
    overflow-y:auto;
    -webkit-overflow-scrolling:touch;
  }

  /* ===== BACKGROUND LAYERS ===== */
  .bgLayer{
    position:fixed; inset:0;
    pointer-events:none;
    z-index:0;
  }
  .aurora{
    background:
      radial-gradient(circle at 15% 20%, rgba(255,77,166,.18), transparent 55%),
      radial-gradient(circle at 85% 25%, rgba(58,160,255,.14), transparent 58%),
      radial-gradient(circle at 50% 80%, rgba(255,255,255,.06), transparent 60%),
      radial-gradient(circle at 30% 70%, rgba(255,77,166,.10), transparent 55%),
      radial-gradient(circle at 70% 65%, rgba(58,160,255,.10), transparent 55%);
    filter: blur(14px) saturate(1.25);
    animation: auroraMove 8s ease-in-out infinite;
    opacity:.9;
  }
  @keyframes auroraMove{
    0%,100%{transform:translateY(0) scale(1)}
    50%{transform:translateY(18px) scale(1.03)}
  }
  .stars{
    background:
      radial-gradient(circle at 10% 30%, rgba(255,255,255,.22), transparent 35%),
      radial-gradient(circle at 20% 80%, rgba(255,255,255,.14), transparent 40%),
      radial-gradient(circle at 70% 20%, rgba(255,255,255,.18), transparent 45%),
      radial-gradient(circle at 85% 60%, rgba(255,255,255,.12), transparent 42%),
      radial-gradient(circle at 55% 55%, rgba(255,255,255,.08), transparent 50%);
    opacity:.85;
    animation: starDrift 10s ease-in-out infinite;
  }
  @keyframes starDrift{
    0%,100%{transform:translateY(0)}
    50%{transform:translateY(10px)}
  }

  /* Weather overlay (changes by phase) */
  .weatherOverlay{
    position:fixed; inset:0;
    pointer-events:none;
    z-index:1;
    opacity:0;
    transition: opacity 1.2s ease;
  }
  .weatherOverlay.on{opacity:1}

  /* Rain */
  .rainDrop{
    position:fixed;
    top:-20px;
    width:2px;
    height:14px;
    background:rgba(200,200,255,.35);
    border-radius:2px;
    pointer-events:none;
    z-index:2;
    animation: rainFall linear forwards;
  }
  @keyframes rainFall{
    to{ transform: translateY(110vh); opacity:0.2; }
  }

  /* Floating particles */
  .particle{
    position:fixed;
    width:8px; height:8px;
    border-radius:50%;
    background:rgba(255,77,166,.22);
    box-shadow: 0 0 18px rgba(255,77,166,.25);
    pointer-events:none;
    z-index:2;
    animation: floatParticle 6s ease-in-out infinite;
    opacity:.7;
  }
  @keyframes floatParticle{
    0%,100%{transform:translateY(0)}
    50%{transform:translateY(-14px)}
  }

  /* Finger gravity hearts */
  .followHeart{
    position:fixed;
    font-size:18px;
    pointer-events:none;
    z-index:9999;
    opacity:0.95;
    filter: drop-shadow(0 0 10px rgba(255,77,166,.18));
    transition: transform .12s linear, opacity .25s ease;
  }

  /* ===== UI CARDS ===== */
  .wrap{
    position:relative;
    z-index:5;
    max-width:920px;
    margin:0 auto;
    padding-bottom:38px;
  }
  .card{
    background:rgba(15,15,15,.92);
    border:1px solid rgba(255,77,166,.18);
    border-radius:18px;
    box-shadow: 0 18px 70px rgba(0,0,0,.55);
    padding:16px;
    text-align:left;
  }
  .centerCard{text-align:center;}
  .title{
    margin:10px 0 6px;
    font-size:28px;
    color:var(--pink);
    letter-spacing:.3px;
    text-shadow:0 0 18px rgba(255,77,166,.22);
  }
  .sub{
    margin:0 auto 14px;
    max-width:760px;
    opacity:.9;
    line-height:1.65;
    text-align:center;
  }

  button{
    padding:14px 22px;
    font-size:16px;
    border:none;
    border-radius:14px;
    background:var(--pink);
    color:#fff;
    cursor:pointer;
  }
  button:active{transform:scale(.99)}
  .btnDark{
    background:#1c1c1c;
    border:1px solid rgba(255,255,255,.08);
  }
  .btnRow{
    display:flex;
    gap:10px;
    flex-wrap:wrap;
    justify-content:center;
    margin-top:14px;
  }

  .divider{
    height:1px;
    margin:14px 0;
    background:linear-gradient(90deg, transparent, rgba(255,77,166,.55), transparent);
  }

  /* ===== BREATHING HEART ===== */
  .heartStage{
    display:grid;
    place-items:center;
    margin:16px auto 8px;
    height:220px;
    position:relative;
  }
  .breathingHeart{
    width:140px; height:140px;
    border-radius:50%;
    background: radial-gradient(circle at 30% 30%, rgba(255,255,255,.18), transparent 45%),
                radial-gradient(circle at 60% 60%, rgba(255,77,166,.50), rgba(255,77,166,.18), transparent 70%);
    box-shadow: 0 0 40px rgba(255,77,166,.22);
    position:relative;
    animation: breathe 2.2s ease-in-out infinite;
    cursor:pointer;
    user-select:none;
    -webkit-tap-highlight-color: transparent;
  }
  .breathingHeart::after{
    content:"❤️";
    position:absolute;
    left:50%; top:50%;
    transform:translate(-50%,-50%);
    font-size:54px;
    filter: drop-shadow(0 0 12px rgba(255,77,166,.25));
  }
  @keyframes breathe{
    0%,100%{transform:scale(1); filter:drop-shadow(0 0 10px rgba(255,77,166,.18));}
    50%{transform:scale(1.08); filter:drop-shadow(0 0 18px rgba(255,77,166,.30));}
  }
  .heartGlow{
    position:absolute;
    inset:-40px;
    background: radial-gradient(circle, rgba(255,77,166,.14), transparent 60%);
    filter: blur(10px);
    opacity:.9;
    animation: glowPulse 2.2s ease-in-out infinite;
    pointer-events:none;
  }
  @keyframes glowPulse{
    0%,100%{transform:scale(1); opacity:.75}
    50%{transform:scale(1.08); opacity:1}
  }

  .phaseText{
    margin:10px auto 0;
    padding:12px 14px;
    border-radius:16px;
    background:rgba(0,0,0,.35);
    border:1px solid rgba(255,255,255,.06);
    line-height:1.8;
    opacity:.95;
    text-align:center;
  }

  /* ===== PROMISE PARTICLES (tap to reveal) ===== */
  .promiseGrid{
    display:grid;
    grid-template-columns:1fr;
    gap:10px;
    margin-top:12px;
  }
  @media (min-width:720px){
    .promiseGrid{ grid-template-columns:1fr 1fr; }
  }
  .promiseCard{
    border-radius:16px;
    padding:12px 14px;
    background:rgba(0,0,0,.35);
    border:1px solid rgba(255,77,166,.18);
    line-height:1.8;
  }
  .promiseCard b{color:var(--pink)}
  .pillRow{
    margin-top:10px;
    display:flex;
    gap:8px;
    flex-wrap:wrap;
    justify-content:center;
  }
  .pill{
    padding:7px 11px;
    border-radius:999px;
    background:rgba(0,0,0,.35);
    border:1px solid rgba(255,255,255,.08);
    font-size:13px;
    opacity:.92;
  }

  /* ===== AIRPLANE (subtle) ===== */
  .plane{
    position:fixed;
    top:18%;
    left:-80px;
    font-size:26px;
    opacity:.75;
    z-index:3;
    pointer-events:none;
    animation: fly 14s linear infinite;
    filter: drop-shadow(0 0 10px rgba(58,160,255,.18));
  }
  @keyframes fly{
    0%{transform:translateX(-120px) translateY(0) rotate(8deg)}
    35%{transform:translateX(45vw) translateY(-18px) rotate(8deg)}
    70%{transform:translateX(88vw) translateY(6px) rotate(8deg)}
    100%{transform:translateX(120vw) translateY(0) rotate(8deg)}
  }

  /* ===== LOVE FLOOD ===== */
  .floodTitle{
    margin:4px 0 0;
    color:var(--pink);
    text-align:center;
  }
  .floodHint{
    margin:4px 0 12px;
    opacity:.8;
    text-align:center;
    font-size:14px;
  }
  .floodBox{
    border-radius:16px;
    padding:14px;
    background:rgba(0,0,0,.45);
    border:1px solid rgba(255,255,255,.06);
    min-height:260px;
  }
  .floodLine{
    padding:10px 10px;
    margin:8px 0;
    border-radius:12px;
    background:rgba(255,77,166,.08);
    border:1px solid rgba(255,77,166,.18);
    line-height:1.7;
    opacity:0;
    transform:translateY(10px);
    animation: lineIn .55s ease forwards;
  }
  @keyframes lineIn{ to{opacity:1; transform:translateY(0);} }

  /* Hold surprise */
  .holdHint{
    margin-top:12px;
    opacity:.75;
    text-align:center;
    text-decoration:underline;
  }
  .toast{
    position:fixed;
    left:50%;
    bottom:18px;
    transform:translateX(-50%);
    padding:12px 14px;
    border-radius:14px;
    background:rgba(15,15,15,.95);
    border:1px solid rgba(255,77,166,.22);
    box-shadow:0 20px 60px rgba(0,0,0,.6);
    z-index:99999;
    display:none;
    max-width:min(92vw,560px);
    line-height:1.6;
  }
  .toast.show{display:block;}

  /* Portal back */
  .portal{
    margin-top:14px;
    width:180px; height:180px;
    border-radius:50%;
    border:1px solid rgba(255,77,166,.22);
    background:
      radial-gradient(circle at 50% 50%, rgba(255,77,166,.18), transparent 60%),
      radial-gradient(circle at 35% 35%, rgba(58,160,255,.12), transparent 55%),
      rgba(0,0,0,.2);
    box-shadow: 0 0 40px rgba(255,77,166,.14);
    animation: portalSpin 3.6s linear infinite;
    display:grid;
    place-items:center;
    cursor:pointer;
    user-select:none;
    -webkit-tap-highlight-color: transparent;
  }
  @keyframes portalSpin{
    to{transform:rotate(360deg)}
  }
  .portal span{
    font-size:14px;
    letter-spacing:.3px;
    opacity:.92;
    padding:10px 12px;
    border-radius:999px;
    background:rgba(0,0,0,.35);
    border:1px solid rgba(255,255,255,.08);
  }

</style>
</head>

<body>

<!-- Background layers -->
<div class="bgLayer aurora"></div>
<div class="bgLayer stars"></div>

<div id="weatherOverlay" class="weatherOverlay"></div>
<div class="plane">✈️</div>

<!-- PAGE: MAIN -->
<div id="mainPage" class="page scrollPage active">
  <div class="wrap">

    <div class="card centerCard">
      <div class="title">Valentine Universe 🌙💗</div>
      <div class="sub">
        This is not a small page… this is a whole feeling.  
        Touch the heart. Scroll. Explore. And feel how precious one girl becomes in a life.
      </div>

      <div class="heartStage">
        <div class="heartGlow"></div>
        <div id="breathingHeart" class="breathingHeart" title="Tap me"></div>
      </div>

      <div id="heartMessage" class="phaseText">
        “This heart learned to beat differently… after you.”
      </div>

      <div class="divider"></div>

      <div class="sub" style="margin-bottom:0;">
        When you touch the screen, love follows you… like gravity.  
        (Move your finger 👉 hearts will follow.)
      </div>

      <div class="btnRow">
        <button onclick="show('storyPage')">Start Our Story ✨</button>
        <button class="btnDark" onclick="show('promisePage')">Promises 💗</button>
        <button class="btnDark" onclick="show('floodPage')">Love Flood ♾️</button>
      </div>

      <div class="holdHint">Hold anywhere for 3 seconds…</div>
    </div>

  </div>
</div>

<!-- PAGE: STORY -->
<div id="storyPage" class="page scrollPage">
  <div class="wrap">
    <div class="card">
      <div class="title" style="text-align:center;">Our Love Story 💞</div>
      <div class="sub">
        A small story… but a big feeling.  
        (The sky will change like emotions…)
      </div>

      <div class="phaseText" id="storyText">
        🌧️ Sometimes feelings start silently… and grow loudly inside.
      </div>

      <div class="divider"></div>

      <div class="promiseGrid">
        <div class="promiseCard">
          <b>8th standard</b> — You entered the scene like a quiet miracle.  
          The world was normal… but my eyes found you.
        </div>
        <div class="promiseCard">
          <b>February 2025</b> — I told you… and you said “no”.  
          But my heart didn’t stop… it only decided to prove love gently.
        </div>
        <div class="promiseCard">
          <b>Tuition days</b> — We met again and again…  
          and slowly, the “no” became a “maybe” inside your heart.
        </div>
        <div class="promiseCard">
          <b>01 • 03 • 2025</b> — You said you love me.  
          And from that day… life started feeling softer, brighter, safer.
        </div>
      </div>

      <div class="pillRow">
        <span class="pill">You = My Peace</span>
        <span class="pill">You = My Home</span>
        <span class="pill">You = My Forever</span>
      </div>

      <div class="btnRow">
        <button class="btnDark" onclick="show('mainPage')">Back 🌙</button>
        <button onclick="show('promisePage')">Go Promises 💗</button>
      </div>
    </div>
  </div>
</div>

<!-- PAGE: PROMISES -->
<div id="promisePage" class="page scrollPage">
  <div class="wrap">
    <div class="card">
      <div class="title" style="text-align:center;">Promises ✨</div>
      <div class="sub">Tap a promise line… each one is a real feeling.</div>

      <div class="promiseGrid" id="promiseGrid"></div>

      <div class="btnRow">
        <button class="btnDark" onclick="show('mainPage')">Back 🌙</button>
        <button onclick="show('floodPage')">Go Love Flood ♾️</button>
      </div>
    </div>
  </div>
</div>

<!-- PAGE: LOVE FLOOD -->
<div id="floodPage" class="page scrollPage">
  <div class="wrap">
    <div class="card">
      <div class="title" style="text-align:center;">Love Flood ♾️</div>
      <div class="sub">Endless lines… endless love…</div>

      <h3 class="floodTitle">I LOVE YOU SHUTTUMANI ❤️</h3>
      <p class="floodHint">New love lines will keep appearing…</p>

      <div id="floodBox" class="floodBox"></div>

      <div class="divider"></div>

      <div class="sub" style="margin-top:0;">
        When you’re done… touch the portal and return to your main website.
      </div>

      <div style="display:grid; place-items:center;">
        <div class="portal" onclick="goMainSite()">
          <span>Return Portal 🌀</span>
        </div>
      </div>

      <div class="btnRow">
        <button class="btnDark" onclick="show('mainPage')">Back 🌙</button>
        <button onclick="restartFlood()">Replay Flood ✨</button>
      </div>
    </div>
  </div>
</div>

<!-- Toast -->
<div id="toast" class="toast"></div>

<script>
/* =========================
   CONFIG: MAIN WEBSITE LINK
   ========================= */
const MAIN_WEBSITE_URL = "https://shuttumani.github.io/shuttumani/"; // back button goes here

/* =========================
   PAGE SWITCH
   ========================= */
function show(pageId){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  const page = document.getElementById(pageId);
  if(!page){ alert("Missing page id: " + pageId); return; }
  page.classList.add('active');
  // reset scroll for that page
  page.scrollTop = 0;

  // start/stop systems depending page
  if(pageId === "storyPage") startStoryWeather();
  else stopStoryWeather();

  if(pageId === "floodPage") startFlood();
  else stopFlood();
}

/* =========================
   RETURN PORTAL
   ========================= */
function goMainSite(){
  // smooth fade
  document.body.style.transition = "opacity .6s ease";
  document.body.style.opacity = "0";
  setTimeout(()=>{ window.location.href = MAIN_WEBSITE_URL; }, 620);
}

/* =========================
   BREATHING HEART TAPS
   ========================= */
let heartTaps = 0;
const heartMessage = document.getElementById("heartMessage");
const breathingHeart = document.getElementById("breathingHeart");

breathingHeart.addEventListener("click", ()=>{
  heartTaps++;
  // little burst
  burstHearts(window.innerWidth/2, window.innerHeight*0.42, 14);

  if(heartTaps === 1){
    heartMessage.textContent = "“You are the reason it stays alive.”";
  }else if(heartTaps === 3){
    heartMessage.textContent = "“If I had one wish… it would be you… again and again.”";
  }else if(heartTaps === 5){
    heartMessage.textContent = "“From now… your happiness is my peace.”";
  }else if(heartTaps >= 7){
    heartMessage.textContent = "“No matter what… my heart will always choose you.” ❤️";
  }
});

/* =========================
   BURST HEARTS (particles)
   ========================= */
function burstHearts(x,y,count){
  for(let i=0;i<count;i++){
    const el = document.createElement("div");
    el.className = "followHeart";
    el.textContent = "💖";
    el.style.left = x + "px";
    el.style.top = y + "px";
    el.style.opacity = "1";
    const dx = (Math.random()*2-1) * 140;
    const dy = (Math.random()*2-1) * 140;
    el.style.transform = `translate(${dx}px, ${dy}px) scale(${0.8 + Math.random()*0.6})`;
    document.body.appendChild(el);
    setTimeout(()=>{ el.style.opacity = "0"; }, 140);
    setTimeout(()=>{ el.remove(); }, 420);
  }
}

/* =========================
   LOVE GRAVITY HEARTS (follow finger)
   ========================= */
let pointerX = null, pointerY = null;
let followHearts = [];

function spawnFollowHearts(){
  // create 10 trailing hearts once
  if(followHearts.length) return;
  for(let i=0;i<10;i++){
    const h = document.createElement("div");
    h.className = "followHeart";
    h.textContent = (i%2===0) ? "❤️" : "💗";
    h.style.left = "-100px";
    h.style.top = "-100px";
    h.style.opacity = "0";
    document.body.appendChild(h);
    followHearts.push({el:h, x:0, y:0, vx:0, vy:0, delay:i*0.04});
  }
}
spawnFollowHearts();

function onMove(x,y){
  pointerX = x; pointerY = y;
}
window.addEventListener("mousemove", (e)=> onMove(e.clientX, e.clientY));
window.addEventListener("touchmove", (e)=>{
  const t = e.touches[0];
  if(t) onMove(t.clientX, t.clientY);
},{passive:true});

function animateFollow(){
  requestAnimationFrame(animateFollow);
  if(pointerX == null) return;

  followHearts.forEach((h,idx)=>{
    // trailing with spring
    const targetX = pointerX;
    const targetY = pointerY;

    if(idx===0){
      h.x += (targetX - h.x) * 0.22;
      h.y += (targetY - h.y) * 0.22;
    }else{
      const prev = followHearts[idx-1];
      h.x += (prev.x - h.x) * 0.18;
      h.y += (prev.y - h.y) * 0.18;
    }

    h.el.style.left = (h.x + 10) + "px";
    h.el.style.top  = (h.y + 10) + "px";
    h.el.style.opacity = "0.9";
  });
}
animateFollow();

/* =========================
   WEATHER / STORY PHASES
   ========================= */
let storyTimer = null;
let rainTimer = null;

const storyLines = [
  { phase:"rain",   text:"🌧️ Sometimes feelings start silently… and grow loudly inside." },
  { phase:"sunrise",text:"🌅 Then hope comes… slowly… like morning light after long nights." },
  { phase:"gold",   text:"✨ And love turns everything warmer… softer… safer." },
  { phase:"night",  text:"🌙 Finally… peace. Because when you are there… the world is calm." }
];

function startStoryWeather(){
  const overlay = document.getElementById("weatherOverlay");
  overlay.classList.add("on");

  let i = 0;
  applyPhase(storyLines[i]);
  storyTimer = setInterval(()=>{
    i = (i+1) % storyLines.length;
    applyPhase(storyLines[i]);
  }, 4200);
}

function stopStoryWeather(){
  const overlay = document.getElementById("weatherOverlay");
  overlay.classList.remove("on");
  if(storyTimer){ clearInterval(storyTimer); storyTimer=null; }
  stopRain();
  overlay.style.background = "transparent";
}

function applyPhase(item){
  const overlay = document.getElementById("weatherOverlay");
  const storyText = document.getElementById("storyText");
  if(storyText) storyText.textContent = item.text;

  // reset
  stopRain();

  if(item.phase === "rain"){
    overlay.style.background = "linear-gradient(180deg, rgba(58,160,255,.10), transparent 55%)";
    startRain();
  }
  if(item.phase === "sunrise"){
    overlay.style.background = "linear-gradient(180deg, rgba(255,180,90,.10), rgba(255,77,166,.06), transparent 70%)";
  }
  if(item.phase === "gold"){
    overlay.style.background = "radial-gradient(circle at 50% 30%, rgba(255,77,166,.12), transparent 60%)";
  }
  if(item.phase === "night"){
    overlay.style.background = "radial-gradient(circle at 20% 20%, rgba(255,255,255,.06), transparent 55%)";
  }
}

function startRain(){
  if(rainTimer) return;
  rainTimer = setInterval(()=>{
    const d = document.createElement("div");
    d.className = "rainDrop";
    d.style.left = Math.random()*100 + "vw";
    const dur = 700 + Math.random()*800;
    d.style.animationDuration = dur + "ms";
    document.body.appendChild(d);
    setTimeout(()=>d.remove(), dur+200);
  }, 70);
}
function stopRain(){
  if(rainTimer){ clearInterval(rainTimer); rainTimer=null; }
}

/* =========================
   PROMISE CARDS (tap reveals new line)
   ========================= */
const promises = [
  {t:"I choose you", d:"Not for a moment… for every tomorrow."},
  {t:"I miss you", d:"Even when you are not here, you live in my thoughts."},
  {t:"I protect you", d:"Your tears will always matter to me."},
  {t:"I respect you", d:"Your heart is precious… I’ll handle it gently."},
  {t:"I learn you", d:"Every day I want to understand you more."},
  {t:"I stay", d:"Whatever happens… I won’t disappear."},
  {t:"I grow", d:"With you, I want to become better… not just older."},
  {t:"I love you", d:"And I’ll prove it quietly… every day."}
];
function buildPromises(){
  const grid = document.getElementById("promiseGrid");
  grid.innerHTML = "";
  promises.forEach((p)=>{
    const div = document.createElement("div");
    div.className = "promiseCard";
    div.style.cursor = "pointer";
    div.innerHTML = `<b>${p.t}</b><br><span style="opacity:.92">${p.d}</span><div style="margin-top:8px;opacity:.75;font-size:13px;">tap to sparkle ✨</div>`;
    div.addEventListener("click",(e)=>{
      const rect = div.getBoundingClientRect();
      burstHearts(rect.left + rect.width/2, rect.top + rect.height/2, 10);
      toast(`💗 ${p.t} — ${p.d}`);
    });
    grid.appendChild(div);
  });
}
buildPromises();

/* =========================
   LOVE FLOOD (infinite generator)
   ========================= */
let floodTimer = null;
let floodCount = 0;

const floodLines = [
  "I love you… more than my words can hold.",
  "You made my life softer… just by entering it.",
  "Your smile is my calm. Your presence is my home.",
  "Even if the world changes… my choice won’t.",
  "I’ll love you in silence… and in storms… and in peace.",
  "If love had a name… it would sound like you.",
  "Every day with you feels like a blessing.",
  "You are my favorite thought… every single time.",
  "I’m proud of you… always.",
  "No matter what… I’m here."
];

function startFlood(){
  if(floodTimer) return;
  const box = document.getElementById("floodBox");
  if(!box) return;

  floodTimer = setInterval(()=>{
    const line = document.createElement("div");
    line.className = "floodLine";
    const txt = floodLines[floodCount % floodLines.length];
    floodCount++;
    line.innerHTML = `💗 ${txt}`;
    box.appendChild(line);

    // keep it light: limit DOM
    if(box.children.length > 60){
      box.removeChild(box.firstElementChild);
    }
  }, 650);
}
function stopFlood(){
  if(floodTimer){ clearInterval(floodTimer); floodTimer=null; }
}
function restartFlood(){
  const box = document.getElementById("floodBox");
  if(box) box.innerHTML = "";
  floodCount = 0;
  stopFlood();
  startFlood();
}

/* =========================
   TOAST
   ========================= */
let toastTimer = null;
function toast(msg){
  const t = document.getElementById("toast");
  t.innerHTML = msg;
  t.classList.add("show");
  if(toastTimer) clearTimeout(toastTimer);
  toastTimer = setTimeout(()=> t.classList.remove("show"), 2400);
}

/* =========================
   HOLD-TO-REVEAL (3 seconds)
   ========================= */
let holdStart = null;
let holdTimeout = null;

function startHold(){
  holdStart = Date.now();
  holdTimeout = setTimeout(()=>{
    toast("💗 “I am here. Always.”\nAnd I will keep choosing you… again and again.");
    burstHearts(window.innerWidth/2, window.innerHeight*0.75, 18);
  }, 3000);
}
function endHold(){
  holdStart = null;
  if(holdTimeout){ clearTimeout(holdTimeout); holdTimeout=null; }
}

window.addEventListener("mousedown", startHold);
window.addEventListener("mouseup", endHold);
window.addEventListener("touchstart", startHold, {passive:true});
window.addEventListener("touchend", endHold);
 /* =========================
   Ambient particles (soft)
   ========================= */
(function spawnAmbientParticles(){
  for(let i=0;i<18;i++){
    const p = document.createElement("div");
    p.className = "particle";
    p.style.left = Math.random()*100 + "vw";
    p.style.top  = (10 + Math.random()*85) + "vh";
    p.style.animationDuration = (4 + Math.random()*5) + "s";
    p.style.opacity = (0.35 + Math.random()*0.45);
    p.style.background = (i%3===0) ? "rgba(58,160,255,.18)" : "rgba(255,77,166,.22)";
    document.body.appendChild(p);
  }
})();

/* start story weather only when story page opened */
</script>
</body>
</html> 

