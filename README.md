idex.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You ❤️</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Georgia',serif;}
body{background:#000;color:#fff;overflow:hidden;}

.screen{
  position:absolute;
  width:100%;
  height:100%;
  top:0;left:0;
  display:flex;
  align-items:center;
  justify-content:center;
  flex-direction:column;
  transition:transform .6s ease, opacity .6s ease;
}

.hidden{opacity:0;pointer-events:none;}

.lock{
  background:radial-gradient(circle at top,#200010,#000);
}

.lock input{
  padding:12px;
  font-size:18px;
  border:none;
  outline:none;
  border-radius:8px;
  text-align:center;
  margin-top:20px;
}

.fadeText{
  font-size:22px;
  animation:fade 3s infinite;
}

@keyframes fade{
  0%,100%{opacity:0}
  50%{opacity:1}
}

.main{
  background:#000;
  transform:translateY(100%);
}

.envelope{
  width:200px;
  height:130px;
  border:2px solid #fff;
  position:relative;
  cursor:pointer;
}

.envelope:before{
  content:'';
  position:absolute;
  width:100%;
  height:100%;
  border-top:2px solid #fff;
  transform:skewY(-20deg);
  top:-60px;
}

.letter{
  max-width:90%;
  text-align:left;
  font-size:17px;
  line-height:1.6;
  display:none;
}

.hearts span{
  position:absolute;
  color:red;
  animation:float 6s linear infinite;
}

@keyframes float{
  from{bottom:-20px;opacity:1}
  to{bottom:100%;opacity:0}
}

.countdown{
  transform:translateY(100%);
  background:#050505;
}

button{
  padding:10px 20px;
  border:none;
  background:#ff3366;
  color:#fff;
  border-radius:20px;
  margin-top:20px;
}
</style>
</head>

<body>

<!-- LOCK SCREEN -->
<div class="screen lock" id="lock">
  <div class="fadeText">ammede ponnu araaa 💋💋</div>
  <input type="password" placeholder="Enter password" id="pass">
</div>

<!-- MAIN -->
<div class="screen main" id="main">
  <div class="envelope" id="openLetter"></div>

  <div class="letter" id="letter">
    <p>
Happy Valentine’s Day ponnahhh ❤️<br><br>

eth nee appozha vayika ennu arayillla Appozhayalum vayikulooo ninthe first Valentine's Day annu ennu okke ariyaaa nee annu tution nu varo ennu polum arayilla ethu Azhuthumbo pinne ollathu exam okke alle ath Kazhinja kanan polum pattillalo appo enth cheyyum nee vallathum aloichu vechit indooo vaveee enthe oru idea il korach okkee indu ath Njan parayaneee pinne kali akkanda ketta Njan romantic alla ennu paranju nee enthe eduth ethuuu matte parayana oru dhivasam varum daaaa nokkikooo pinne entha sugalle engane okke nadanna mathiyooo vellapozhum enne kurich okke ortholu tta marannu povaruthu nammal mindandu aya entha indava ponnah enthayalum nammal kanum enganelum okke enthelum mindum athokke orapa pinne ammede ponnu aradaaaa 😘🩷❤️💋🫂 exam kazhinju graduation nu enthavavo kalikan poovanel ninak ath scn avum ennu enik ariyaaaaa bhaki Allavarum adipoli ayit avide erikumbo enthe ponnu matharam blaa blaaa blaaaa enthaleeeee nja. Avide annelum ninthe thanne alledaaaaaa enthokke aleeeeee eni korach serious ayit paraya 
Atheeee enik ninne bhayankara ishtam a neee yes parayo ennu arayilla ennalum enik entho parayanam ennu thooni neee Chilappo enne angane kandit undavilla ennalum Njan eth eni paranjillel eni annelum eth parayumbo annu paranjel Njan yes paranjene ennu nee Paranja enik veshamam avummm atha eppo parayane enik ninne bhayankara ishtam a "I Love You❤️"
Nee ethinu rply thannolu Chilappo eth kelkumbo nee ennod eni mindi ennu varilla angane onnum venda tta ishtam allel ath Paranja mathi scn ella eppo ishtam annu paranju ennu vech kozhapam ellata nammal pazhayath pole thanne veliya vethasam onnum ella nammal thammil ethra kollam ayit ariyaaa pinne angotum engotum ariyathathu onnum ellanu vekkanu Ninak enne ishtam anno ennu arayilla eni eth parayumbozhano athine kurich aloikane ennu polum arayilla enth okke annelum neee enthe koode indel adipoli avum ennu thooni athokke thanne prethekish onnum ella ethokke thanne appo aloichu okke paranjolu tta eppo ninne ishtapedan Karanam ennu okke choicha nee nalla kochanu mariyathak okke nokkum enthelum okke ninnod Paranja nee avide veenolum veliya scn onnnum ella oru kidilan kocha neee athranne pinne elle enthokke okke vannalum 10 kazhinju pooyalum scn onnum indavalle tta enik ninnod olla ishtam poovilla enik  aennum nee enthe koch thanneya Neeyum poovilla ennu Njan vishwosikunnu sharkareee. Aloichu okke eni paranjolu tta 
Appo veendum paraya I LOVE YOU ❤️ —<br><br>

<strong>I LOVE YOU ❤️</strong>
    </p>
  </div>

  <button id="downBtn">Swipe Down ⬇️</button>
</div>

<!-- COUNTDOWN -->
<div class="screen countdown" id="count">
  <h2>We 💞</h2>
  <p id="timer"></p>

  <ul>
    <li>01/03/2025 – She said she loves me</li>
    <li>05/06/2023 – First time saw her</li>
    <li>20/07/2010 – She was born</li>
  </ul>

  <button id="upBtn">Swipe Up ⬆️</button>
  <br><br>
  <a href="https://docs.google.com/forms/d/e/1FAIpQLSc1JncNbHTVKlZooN4NaDi_Ov08J6Q1g-v5PMHlNnZ_mcGp6A/viewform?usp=dialog" target="_blank">
    <button>Reply to Me 💌</button>
  </a>
</div>

<audio id="music" src="https://dl.sndup.net/cz8k/love.mp3"></audio>

<script>
const pass=document.getElementById("pass");
const lock=document.getElementById("lock");
const main=document.getElementById("main");
const count=document.getElementById("count");
const letter=document.getElementById("letter");
const music=document.getElementById("music");

pass.addEventListener("input",()=>{
  if(pass.value==="01032025"){
    lock.classList.add("hidden");
    main.style.transform="translateY(0)";
  }
});

document.getElementById("openLetter").onclick=()=>{
  music.play();
  letter.style.display="block";
};

document.getElementById("downBtn").onclick=()=>{
  main.style.transform="translateY(-100%)";
  count.style.transform="translateY(0)";
};

document.getElementById("upBtn").onclick=()=>{
  count.style.transform="translateY(100%)";
  main.style.transform="translateY(0)";
};

function updateTimer(){
  const start=new Date("2025-03-01");
  const now=new Date();
  const diff=now-start;
  document.getElementById("timer").innerText=
    Math.floor(diff/86400000)+" days together ❤️";
}
setInterval(updateTimer,1000);
</script>

</body>
</html>
