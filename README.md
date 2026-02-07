index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>❤️</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Georgia,serif}
body{background:black;color:white;height:100vh;overflow:hidden}

/* LOCK SCREEN */
#lock{
  position:fixed;
  inset:0;
  background:black;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  z-index:10;
}
#lock h2{margin-bottom:15px}
#lock input{
  padding:10px;
  font-size:18px;
  border-radius:6px;
  border:none;
  text-align:center;
}
#lock button{
  margin-top:15px;
  padding:10px 30px;
  background:#ff4d6d;
  color:white;
  border:none;
  border-radius:6px;
  font-size:16px;
}

/* MAIN */
#main{
  display:none;
  position:fixed;
  inset:0;
  background:linear-gradient(#000,#1a001a);
  flex-direction:column;
  justify-content:center;
  align-items:center;
}

/* POPUP */
#popup{
  font-size:22px;
  margin-bottom:25px;
  animation:fade 4s forwards;
}
@keyframes fade{
  0%{opacity:0}
  20%{opacity:1}
  80%{opacity:1}
  100%{opacity:0}
}

/* ENVELOPE */
#envelope{
  width:150px;
  height:100px;
  background:#8b0000;
  border-radius:8px;
  position:relative;
}
#envelope::before{
  content:'';
  position:absolute;
  top:0;
  left:0;
  width:100%;
  height:55%;
  background:#a00000;
  clip-path:polygon(0 0,50% 65%,100% 0);
}

/* HEARTS */
.heart{
  position:fixed;
  bottom:-20px;
  animation:float 6s linear infinite;
}
@keyframes float{
  from{transform:translateY(0);opacity:1}
  to{transform:translateY(-110vh);opacity:0}
}

/* LETTER */
#letter{
  display:none;
  position:fixed;
  inset:0;
  background:#0b0010;
  flex-direction:column;
}
#content{
  flex:1;
  padding:20px;
  overflow-y:auto;
  line-height:1.9;
  -webkit-overflow-scrolling:touch;
}
#back{
  padding:15px;
  text-align:center;
  background:#300020;
}
</style>
</head>

<body>

<!-- LOCK -->
<div id="lock">
  <h2>Enter Password</h2>
  <input id="pass" placeholder="DDMMYYYY">
  <button onclick="unlock()">Unlock</button>
</div>

<!-- MAIN -->
<div id="main">
  <div id="popup">ammede ponnu araaaa 💋</div>
  <div id="envelope" onclick="openLetter()"></div>
</div>

<!-- LETTER -->
<div id="letter">
  <div id="content">
<p>eth nee appozha vayika ennu arayillla Appozhayalum vayikulooo ninthe first Valentine's Day annu ennu okke ariyaaa nee annu tution nu varo ennu polum arayilla ethu Azhuthumbo pinne ollathu exam okke alle ath Kazhinja kanan polum pattillalo appo enth cheyyum nee vallathum aloichu vechit indooo vaveee enthe oru idea il korach okkee indu ath Njan parayaneee pinne kali akkanda ketta Njan romantic alla ennu paranju nee enthe eduth ethuuu matte parayana oru dhivasam varum daaaa nokkikooo pinne entha sugalle engane okke nadanna mathiyooo vellapozhum enne kurich okke ortholu tta marannu povaruthu nammal mindandu aya entha indava ponnah enthayalum nammal kanum enganelum okke enthelum mindum athokke orapa pinne ammede ponnu aradaaaa 😘🩷❤️💋🫂</p>

<p>exam kazhinju graduation nu enthavavo kalikan poovanel ninak ath scn avum ennu enik ariyaaaaa bhaki Allavarum adipoli ayit avide erikumbo enthe ponnu matharam blaa blaaa blaaaa enthaleeeee nja.</p>

<p>Atheeee enik ninne bhayankara ishtam a neee yes parayo ennu arayilla ennalum enik entho parayanam ennu thooni neee.</p>

<p style="text-align:center;font-size:22px;"><strong>I Love You ❤️</strong></p>

<p>Neeyum poovilla ennu Njan vishwosikunnu sharkareee.</p>

<p style="text-align:center;font-size:22px;"><strong>Appo veendum paraya I LOVE YOU ❤️</strong></p>
  </div>
  <div id="back" onclick="goBack()">← Back</div>
</div>

<script>
function unlock(){
  if(document.getElementById("pass").value==="01032025"){
    document.getElementById("lock").style.display="none";
    document.getElementById("main").style.display="flex";
    hearts();
  }
}

function hearts(){
  for(let i=0;i<15;i++){
    let h=document.createElement("div");
    h.className="heart";
    h.innerHTML="❤️";
    h.style.left=Math.random()*100+"vw";
    h.style.fontSize=(12+Math.random()*16)+"px";
    document.body.appendChild(h);
  }
}

function openLetter(){
  document.getElementById("main").style.display="none";
  document.getElementById("letter").style.display="flex";
}

function goBack(){
  document.getElementById("letter").style.display="none";
  document.getElementById("main").style.display="flex";
}
</script>

</body>
</html>

