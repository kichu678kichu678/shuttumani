index. html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Meghana ❤️ Deva</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Georgia,serif}
body{background:linear-gradient(#fff0f5,#f3e5f5);overflow-x:hidden}
section{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;padding:30px}

/* ❤️ HEARTS */
.heart{position:fixed;color:rgba(255,105,180,.6);font-size:18px;animation:float 8s linear infinite}
@keyframes float{from{transform:translateY(100vh)}to{transform:translateY(-10vh);opacity:0}}

/* 🔐 LOCK */
.lock{font-size:70px;cursor:pointer}
.kiss{font-size:90px;margin-top:20px;display:none;animation:pop 1.5s forwards}
@keyframes pop{0%{transform:scale(0)}60%{transform:scale(1.4)}100%{transform:scale(1)}}

/* 🪑 BENCH */
.scene{position:relative;width:90%;max-width:700px;height:300px;margin-top:30px}
.desk{position:absolute;bottom:120px;width:100%;height:20px;background:#8d6e63}
.bench{position:absolute;bottom:90px;width:100%;height:18px;background:#6d4c41}
.person{position:absolute;bottom:108px;width:40px;height:80px;background:#444;border-radius:20px}
.boy{left:45%}.girl{left:52%}
.person::before{content:"";position:absolute;top:-28px;left:5px;width:30px;height:30px;background:#555;border-radius:50%}
.hand{position:absolute;width:20px;height:6px;background:#555;top:35px;animation:touch 4s infinite}
.boy .hand{right:-10px}.girl .hand{left:-10px}
@keyframes touch{50%{transform:translateX(6px)}}

/* 💌 ENVELOPE */
.envelope{width:160px;height:100px;background:#ffcdd2;position:relative;cursor:pointer;border-radius:6px;margin-top:30px}
.flap{position:absolute;top:0;width:100%;height:50%;background:#f48fb1;clip-path:polygon(0 0,50% 100%,100% 0)}
.letter{display:none;margin-top:20px;max-width:600px;font-size:18px;color:#6a1b9a}

/* 🕊️ BIRDS */
.bird{position:absolute;font-size:22px;animation:fly 3s linear forwards}
@keyframes fly{to{transform:translate(200px,-200px);opacity:0}}

/* 📖 DIARY */
textarea{width:90%;max-width:600px;height:120px;border-radius:10px;padding:10px;border:1px solid #ccc;font-size:16px}
.reply{margin-top:10px;background:#fce4ec;padding:10px;border-radius:10px}

/* 🖼️ PHOTOS */
.photos{display:grid;grid-template-columns:repeat(2,1fr);gap:15px;margin-top:20px}
.photo{height:140px;background:#f8bbd0;border-radius:12px;display:flex;align-items:center;justify-content:center}

/* 🎶 MUSIC */
audio{margin-top:20px}
</style>
</head>

<body>

<!-- ❤️ Hearts -->
<script>
for(let i=0;i<25;i++){
 let h=document.createElement("div");
 h.className="heart";h.innerHTML="❤️";
 h.style.left=Math.random()*100+"vw";
 h.style.animationDelay=Math.random()*8+"s";
 document.body.appendChild(h);
}
</script>

<!-- 🔐 LOCK -->
<section>
  <div class="lock" onclick="unlock()">🔒</div>
  <div>Tap to unlock our story</div>
  <div class="kiss" id="kiss">💋</div>
</section>

<!-- 🪑 BENCH -->
<section>
  <h2>That Tuition Class</h2>
  <div class="scene">
    <div class="desk"></div><div class="bench"></div>
    <div class="person boy"><div class="hand"></div></div>
    <div class="person girl"><div class="hand"></div></div>
  </div>
  <p>Sometimes the class was empty. We sat together — silently loud.</p>
</section>

<!-- 💌 ENVELOPE -->
<section>
  <h2>A Letter For You</h2>
  <div class="envelope" onclick="openLetter()">
    <div class="flap"></div>
  </div>
  <div class="letter" id="letter">
    My love, every day I choose you again.<br>
    You are my calm and my chaos 🤍
  </div>
</section>

<!-- 📖 DIARY -->
<section>
  <h2>Today I Felt…</h2>
  <textarea placeholder="Write your feelings today…"></textarea>
  <div class="reply">Her reply will live here 🤍</div>
</section>

<!-- 🖼️ PHOTOS -->
<section>
  <h2>Memories</h2>
  <div class="photos">
    <div class="photo">Photo 1</div>
    <div class="photo">Photo 2</div>
    <div class="photo">Photo 3</div>
    <div class="photo">Photo 4</div>
  </div>
</section>

<!-- 🎶 MUSIC -->
<section>
  <h2>Our Song</h2>
  <audio controls>
    <source src="assets/music.mp3" type="audio/mpeg">
  </audio>
</section>

<script>
function unlock(){
 document.getElementById("kiss").style.display="block";
}
function openLetter(){
 document.getElementById("letter").style.display="block";
 for(let i=0;i<5;i++){
   let b=document.createElement("div");
   b.className="bird";b.innerHTML="🕊️";
   b.style.left="50%";b.style.top="50%";
   document.body.appendChild(b);
 }
}
</script>

</body>
</html>
