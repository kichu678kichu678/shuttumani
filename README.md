index.html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Shuttumani</title>

<style>
  body{
    margin:0;
    background:black;
    color:white;
    font-family:Arial;
    text-align:center;
    overflow:hidden;
  }

  /* pages */
  .page{
    display:none;
    height:100vh;
    width:100%;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    padding:20px;
    box-sizing:border-box;
  }
  .page.active{ display:flex; }

  input{
    padding:15px;
    font-size:18px;
    border-radius:10px;
    border:none;
    margin-top:20px;
    text-align:center;
  }

  button{
    padding:15px 25px;
    font-size:18px;
    border:none;
    border-radius:10px;
    background:#ff4da6;
    color:white;
    margin-top:12px;
  }

  /* hearts */
  .heart{
    position:fixed;
    bottom:-10px;
    font-size:20px;
    animation: floatUp 5s linear infinite;
    opacity:0.7;
    pointer-events:none;
  }
  @keyframes floatUp{
    0%{transform:translateY(0);}
    100%{transform:translateY(-110vh);}
  }

  /* envelope */
  .envelope{
    position: relative;
    width: 220px;
    height: 150px;
    margin-top: 20px;
    cursor: pointer;
  }
  .envelope .body{
    width:100%;
    height:100%;
    background:#e75480;
    border-radius:10px;
    position:absolute;
    top:0; left:0;
  }
  .envelope .flap{
    width:0; height:0;
    border-left:110px solid transparent;
    border-right:110px solid transparent;
    border-bottom:75px solid #ff6fa5;
    position:absolute;
    top:-75px; left:0;
    transform-origin: bottom;
    transition: transform .8s ease;
  }
  .envelope.open .flap{
    transform: rotateX(180deg);
  }
  .tapText{
    position:absolute;
    bottom:-35px;
    width:100%;
    text-align:center;
    opacity:.85;
  }

  /* letter scroll box */
  .letterBox{
    height:70vh;
    overflow-y:auto;
    padding:20px;
    font-size:18px;
    line-height:1.6;
    text-align:left;
    border-radius:12px;
    background:#0f0f0f;
  }

  /* countdown text box */
  .countBox{
    max-width:520px;
    margin:25px auto;
    text-align:left;
    line-height:1.9;
    font-size:15px;
  }
</style>
</head>

<body>

<!-- MUSIC -->
<audio id="bgMusic" loop>
  <source src="music.mp3" type="audio/mpeg" />
</audio>

<!-- LOCK SCREEN -->
<div id="lockPage" class="page active">
  <h1>shuttumani 💋</h1>
  <input type="password" id="passwordInput" placeholder="Enter date (01032025)" />
  <button onclick="checkPassword()">Unlock</button>
</div>

<!-- ENVELOPE PAGE -->
<div id="envelopePage" class="page">
  <h2>Love Letter 💌</h2>

  <div class="envelope" id="env" onclick="openLetter()">
    <div class="flap"></div>
    <div class="body"></div>
    <p class="tapText">Tap to open 💌</p>
  </div>

  <button onclick="show('lockPage')" style="background:#222;">Back 🔒</button>
</div>

<!-- LETTER PAGE -->
<div id="letterPage" class="page">
  <h2>For You ❤️</h2>

  <div class="letterBox">
eth nee appozha vayika ennu arayillla Appozhayalum vayikulooo ninthe first Valentine's Day annu ennu okke ariyaaa nee annu tution nu varo ennu polum arayilla ethu Azhuthumbo pinne ollathu exam okke alle ath Kazhinja kanan polum pattillalo appo enth cheyyum nee vallathum aloichu vechit indooo vaveee enthe oru idea il korach okkee indu ath Njan parayaneee pinne kali akkanda ketta Njan romantic alla ennu paranju nee enthe eduth ethuuu matte parayana oru dhivasam varum daaaa nokkikooo pinne entha sugalle engane okke nadanna mathiyooo vellapozhum enne kurich okke ortholu tta marannu povaruthu nammal mindandu aya entha indava ponnah enthayalum nammal kanum enganelum okke enthelum mindum athokke orapa pinne ammede ponnu aradaaaa 😘🩷❤️💋🫂 exam kazhinju graduation nu enthavavo kalikan poovanel ninak ath scn avum ennu enik ariyaaaaa bhaki Allavarum adipoli ayit avide erikumbo enthe ponnu matharam blaa blaaa blaaaa enthaleeeee nja. Avide annelum ninthe thanne alledaaaaaa enthokke aleeeeee eni korach serious ayit paraya  

<br><br>

Atheeee enik ninne bhayankara ishtam a neee yes parayo ennu arayilla ennalum enik entho parayanam ennu thooni neee Chilappo enne angane kandit undavilla ennalum Njan eth eni paranjillel eni annelum eth parayumbo annu paranjel Njan yes paranjene ennu nee Paranja enik veshamam avummm atha eppo parayane enik ninne bhayankara ishtam a "I Love You❤️"

<br><br>

Nee ethinu rply thannolu Chilappo eth kelkumbo nee ennod eni mindi ennu varilla angane onnum venda tta ishtam allel ath Paranja mathi scn ella eppo ishtam annu paranju ennu vech kozhapam ellata nammal pazhayath pole thanne veliya vethasam onnum ella nammal thammil ethra kollam ayit ariyaaa pinne angotum engotum ariyathathu onnum ellanu vekkanu Ninak enne ishtam anno ennu arayilla eni eth parayumbozhano athine kurich aloikane ennu polum arayilla enth okke annelum neee enthe koode indel adipoli avum ennu thooni athokke thanne prethekish onnum ella ethokke thanne appo aloichu okke paranjolu tta eppo ninne ishtapedan Karanam ennu okke choicha nee nalla kochanu mariyathak okke nokkum enthelum okke ninnod Paranja nee avide veenolum veliya scn onnnum ella oru kidilan kocha neee athranne pinne elle enthokke okke vannalum 10 kazhinju pooyalum scn onnum indavalle tta enik ninnod olla ishtam poovilla enik aennum nee enthe koch thanneya Neeyum poovilla ennu Njan vishwosikunnu sharkareee. Aloichu okke eni paranjolu tta  

<br><br>

Appo veendum paraya I LOVE YOU ❤️
  </div>

  <button onclick="show('countdownPage')">Our Date 💞</button>
  <button onclick="show('envelopePage')" style="background:#222;">Back 💌</button>
</div>

<!-- COUNTDOWN PAGE -->
<div id="countdownPage" class="page">
  <h2 style="color:#ff4d88;">We committed on</h2>
  <h1>01 • 03 • 2025 💖</h1>

  <p id="countdownTimer" style="font-size:18px; margin-top:15px;"></p>

  <div class="countBox">
    <p>💗 01-03-2025 — The Day We Became “Us”  
    This was not just a date on the calendar. This was the day feelings turned into something real. The day we stopped standing on two different sides and slowly started walking in the same direction. From this day, your happiness became my peace, your sadness became my concern, and your presence became my comfort. 01-03-2025 is not just when we committed… it is the day my heart officially chose you.</p>

    <p>💗 05-06-2023 — The First Time I Saw You  
    I still don’t know if you noticed me that day in tuition class… but I remember noticing you. Maybe it was just another normal day for the world, but for me, it quietly became special. I didn’t know that the girl sitting there would later become someone who would change my thoughts, my feelings, and my future. That first sight was simple… but it was the beginning of everything.</p>

    <p>💗 20-07-2010 — The Day the World Became Beautiful  
    Long before I knew you… before tuition, before conversations, before feelings… this was the day you came into this world. And I sometimes think how lucky this world is to have you in it. Because without this day, there would be no smiles from you, no talks with you, no “us.” 20-07-2010 is special not just because you were born… but because that’s the day the person I would one day love started her journey.</p>
  </div>

  <button onclick="show('letterPage')" style="background:#222;">Back ❤️</button>
</div>

<script>
  // page switch
  function show(pageId){
    document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
    document.getElementById(pageId).classList.add('active');
  }

  // lock
  function checkPassword(){
    const entered = document.getElementById("passwordInput").value.trim();
    if(entered === "01032025"){
      const music = document.getElementById("bgMusic");
      if(music) music.play().catch(()=>{});
      show("envelopePage");
    } else {
      alert("Wrong date 💔");
    }
  }

  // envelope -> letter
  function openLetter(){
    const env = document.getElementById("env");
    env.classList.add("open");
    setTimeout(()=>show("letterPage"), 650);
  }

  // floating hearts
  setInterval(function(){
    var heart=document.createElement("div");
    heart.className="heart";
    heart.innerHTML="❤️";
    heart.style.left=Math.random()*100+"%";
    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),5000);
  },800);

  // countdown timer (since 01-03-2025)
  (function startCountdown(){
    const target = new Date("2025-03-01T00:00:00").getTime();
    setInterval(() => {
      const now = Date.now();
      const diff = now - target;

      const days = Math.floor(diff / (1000*60*60*24));
      const hours = Math.floor((diff % (1000*60*60*24)) / (1000*60*60));
      const mins = Math.floor((diff % (1000*60*60)) / (1000*60));
      const secs = Math.floor((diff % (1000*60)) / 1000);

      const el = document.getElementById("countdownTimer");
      if (el) el.innerHTML = `${days} days 💕 ${hours} hrs 💕 ${mins} mins 💕 ${secs} sec together`;
    }, 1000);
  })();
</script>

</body>
</html>


