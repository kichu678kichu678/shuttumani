index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You ❤️</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Georgia,serif;}
body{background:#000;color:#fff;overflow:hidden;height:100vh;}

.screen{
  position:absolute;
  width:100%;
  height:100%;
  display:flex;
  align-items:center;
  justify-content:center;
  flex-direction:column;
  transition:all .6s ease;
}

/* LOCK */
#lock{
  background:#000;
}
#lock p{
  margin-bottom:20px;
  font-size:20px;
  opacity:.8;
}
#lock input{
  padding:12px;
  font-size:18px;
  border:none;
  border-radius:8px;
  text-align:center;
}

/* MAIN */
#main{
  display:none;
  background:radial-gradient(circle at top,#1a0010,#000);
}

/* Envelope */
.envelope{
  width:220px;
  height:140px;
  border:2px solid #fff;
  position:relative;
  cursor:pointer;
}
.envelope::before{
  content:"";
  position:absolute;
  top:-70px;
  left:0;
  width:100%;
  height:100%;
  border-top:2px solid #fff;
  transform:skewY(-20deg);
}

/* Letter */
#letter{
  display:none;
  padding:20px;
  max-height:75vh;
  overflow-y:auto;
  font-size:16px;
  line-height:1.7;
}

/* Countdown */
#count{
  display:none;
  background:#050505;
  text-align:center;
  padding:20px;
}
button{
  padding:10px 20px;
  border:none;
  border-radius:20px;
  background:#ff3366;
  color:#fff;
  margin-top:20px;
}
ul{
  text-align:left;
  margin-top:20px;
}
</style>
</head>

<body>

<!-- LOCK SCREEN -->
<div class="screen" id="lock">
  <p>ammede ponnu araaa 💋💋</p>
  <input type="password" id="pass" placeholder="01 03 2025">
</div>

<!-- MAIN SCREEN -->
<div class="screen" id="main">
  <div class="envelope" id="openLetter"></div>

  <div id="letter">
eth nee appozha vayika ennu arayillla Appozhayalum vayikulooo ninthe first Valentine's Day annu ennu okke ariyaaa nee annu tution nu varo ennu polum arayilla ethu Azhuthumbo pinne ollathu exam okke alle ath Kazhinja kanan polum pattillalo appo enth cheyyum nee vallathum aloichu vechit indooo vaveee enthe oru idea il korach okkee indu ath Njan parayaneee pinne kali akkanda ketta Njan romantic alla ennu paranju nee enthe eduth ethuuu matte parayana oru dhivasam varum daaaa nokkikooo pinne entha sugalle engane okke nadanna mathiyooo vellapozhum enne kurich okke ortholu tta marannu povaruthu nammal mindandu aya entha indava ponnah enthayalum nammal kanum enganelum okke enthelum mindum athokke orapa pinne ammede ponnu aradaaaa 😘🩷❤️💋🫂 exam kazhinju graduation nu enthavavo kalikan poovanel ninak ath scn avum ennu enik ariyaaaaa bhaki Allavarum adipoli ayit avide erikumbo enthe ponnu matharam blaa blaaa blaaaa enthaleeeee nja. Avide annelum ninthe thanne alledaaaaaa enthokke aleeeeee eni korach serious ayit paraya  

Atheeee enik ninne bhayankara ishtam a neee yes parayo ennu arayilla ennalum enik entho parayanam ennu thooni neee Chilappo enne angane kandit undavilla ennalum Njan eth eni paranjillel eni annelum eth parayumbo annu paranjel Njan yes paranjene ennu nee Paranja enik veshamam avummm atha eppo parayane enik ninne bhayankara ishtam a "I Love You❤️"  

Nee ethinu rply thannolu Chilappo eth kelkumbo nee ennod eni mindi ennu varilla angane onnum venda tta ishtam allel ath Paranja mathi scn ella eppo ishtam annu paranju ennu vech kozhapam ellata nammal pazhayath pole thanne veliya vethasam onnum ella nammal thammil ethra kollam ayit ariyaaa pinne angotum engotum ariyathathu onnum ellanu vekkanu Ninak enne ishtam anno ennu arayilla eni eth parayumbozhano athine kurich aloikane ennu polum arayilla enth okke annelum neee enthe koode indel adipoli avum ennu thooni athokke thanne prethekish onnum ella ethokke thanne appo aloichu okke paranjolu tta  

Appo veendum paraya  
I LOVE YOU ❤️
  </div>

  <button id="downBtn" style="display:none;">Swipe Down ⬇️</button>
</div>

<!-- COUNTDOWN -->
<div class="screen" id="count">
  <h2>We 💞</h2>
  <p id="timer"></p>

  <ul>
    <li>01/03/2025 – She said she loves me</li>
    <li>05/06/2023 – First time I saw her</li>
    <li>20/07/2010 – She came into the world</li>
  </ul>

  <button id="upBtn">Go Back ⬆️</button>
</div>

<audio id="music" src="https://dl.sndup.net/cz8k/love.mp3"></audio>

<script>
const pass = document.getElementById("pass");
const lock = document.getElementById("lock");
const main = document.getElementById("main");
const openLetter = document.getElementById("openLetter");
const letter = document.getElementById("letter");
const downBtn = document.getElementById("downBtn");
const count = document.getElementById("count");
const music = document.getElementById("music");

pass.addEventListener("input",()=>{
  if(pass.value==="01032025"){
    lock.style.display="none";
    main.style.display="flex";
  }
});

openLetter.onclick=()=>{
  openLetter.style.display="none";
  letter.style.display="block";
  downBtn.style.display="inline-block";
  music.play();
};

downBtn.onclick=()=>{
  main.style.display="none";
  count.style.display="flex";
};

document.getElementById("upBtn").onclick=()=>{
  count.style.display="none";
  main.style.display="flex";
};

function updateTimer(){
  const start=new Date("2025-03-01");
  const now=new Date();
  const days=Math.floor((now-start)/86400000);
  document.getElementById("timer").innerText=days+" days together ❤️";
}
setInterval(updateTimer,1000);
</script>

</body>
</html>

