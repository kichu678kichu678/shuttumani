index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You ❤️</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Segoe UI',sans-serif;
}

body{
  height:100vh;
  background:linear-gradient(180deg,#ffb6c1,#ffe4e1);
  overflow:hidden;
}

.hidden{display:none;}
.center{
  display:flex;
  justify-content:center;
  align-items:center;
  flex-direction:column;
  height:100vh;
  text-align:center;
}

/* LOCK */
#lockScreen input{
  padding:12px;
  border-radius:20px;
  border:none;
  text-align:center;
}
#lockScreen button{
  margin-top:15px;
  padding:10px 25px;
  border:none;
  border-radius:20px;
  background:#ff4d6d;
  color:#fff;
}

/* WELCOME */
#welcome{
  font-size:28px;
  animation:fade 3s ease-in-out;
}

/* ENVELOPE */
#envelope{
  font-size:90px;
  cursor:pointer;
  animation:float 2s infinite;
}

/* LETTER */
#letter{
  padding:20px;
  max-height:85vh;
  overflow-y:auto;
  line-height:1.7;
  font-size:16px;
}
.love{
  text-align:center;
  font-size:24px;
  color:#ff2d55;
  font-weight:bold;
  margin:20px 0;
}

/* HEARTS */
.heart{
  position:fixed;
  bottom:-10px;
  font-size:20px;
  animation:rise 6s linear infinite;
  color:#ff2d55;
  opacity:0.7;
}

/* ANIMATIONS */
@keyframes fade{
  0%{opacity:0}
  20%{opacity:1}
  80%{opacity:1}
  100%{opacity:0}
}
@keyframes float{
  0%{transform:translateY(0)}
  50%{transform:translateY(-12px)}
  100%{transform:translateY(0)}
}
@keyframes rise{
  from{transform:translateY(0);opacity:1}
  to{transform:translateY(-110vh);opacity:0}
}
</style>
</head>

<body>

<!-- LOCK SCREEN -->
<div id="lockScreen" class="center">
  <h2>Enter the password 💗</h2>
  <input type="password" id="pass">
  <button onclick="unlock()">Unlock</button>
</div>

<!-- WELCOME -->
<div id="welcome" class="center hidden">
  ammede ponnu araaa 💋💋
</div>

<!-- MAIN -->
<div id="main" class="center hidden">
  <div id="envelope">💌</div>
  <p>Tap the letter</p>
</div>

<!-- LETTER -->
<div id="letter" class="hidden">

<p>Happy Valentine's Day ponnahhh ❤💋💋🫂</p>

<p>
eth nee appozha vayika ennu arayillla… Appozhayalum vayikulooo.  
ninthe first Valentine's Day annu ennu okke ariyaaa…  
nee annu tution nu varo ennu polum arayilla…
</p>

<p>
ethu azhuthumbo pinne ollathu exam okke alle…  
ath kazhinja kanan polum pattillalo…  
appo enth cheyyum nee…  
vallathum aloichu vechit indooo vaveee…
</p>

<p>
enthe oru idea il korach okkee indu…  
ath njan parayaneee…  
pinne kali akkanda kettaaa…  
njan romantic alla ennu paranju nee enthe eduth ethuuu…
</p>

<p>
vellapozhum enne kurich ortholu tta…  
marannu povaruthu…  
enthayalum nammal kanum…  
enganelum okke enthelum mindum… ath orappa…
</p>

<p>
pinne ammede ponnu aradaaaa 😘🩷❤️💋🫂  
exam kazhinju graduation nu enthavavo…  
kalikan poovanel ninak ath scn avum ennu enik ariyaaaaa…
</p>

<p>
atheeee…  
enik ninne bhayankara ishtam a neee…  
yes parayo ennu arayilla…  
ennalum enik entho parayanam ennu thooni…
</p>

<div class="love">I LOVE YOU ❤️</div>

<p>
nee ethinu reply thannolu…  
ishtam allel ath paranja mathi…  
scn ella…  
nammal pazhayath pole thanne…
</p>

<p>
enthokke vannalum…  
enik ninnod olla ishtam poovilla…  
aennum nee enthe koch thanneya…  
njane ath vishwasikkunnu…
</p>

<div class="love">Appo veendum paraya… I LOVE YOU ❤️</div>

</div>

<audio id="music" loop>
  <source src="YOUR_MUSIC_LINK_HERE" type="audio/mpeg">
</audio>

<script>
const lockScreen=document.getElementById("lockScreen");
const welcome=document.getElementById("welcome");
const main=document.getElementById("main");
const letter=document.getElementById("letter");
const music=document.getElementById("music");

function unlock(){
  if(document.getElementById("pass").value==="01032025"){
    lockScreen.classList.add("hidden");
    welcome.classList.remove("hidden");
    music.play();
    setTimeout(()=>{
      welcome.classList.add("hidden");
      main.classList.remove("hidden");
    },3000);
  }else{
    alert("Wrong password 💔");
  }
}

document.getElementById("envelope").onclick=()=>{
  main.classList.add("hidden");
  letter.classList.remove("hidden");
};

// HEARTS
setInterval(()=>{
  const h=document.createElement("div");
  h.className="heart";
  h.innerHTML="❤️";
  h.style.left = Math.random()*100 + "vw";
  h.style.fontSize=(15+Math.random()*20)+"px";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),6000);
},400);
</script>

</body>
</html>





