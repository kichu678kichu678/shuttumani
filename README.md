index.html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shuttumani</title>

<style>
body{
  margin:0;
  background:black;
  color:white;
  font-family:Arial;
  text-align:center;
}

.page{
  display:none;
  height:100vh;
  justify-content:center;
  align-items:center;
  flex-direction:column;
}

.active{
  display:flex;
}

input{
  padding:15px;
  font-size:18px;
  border-radius:10px;
  border:none;
  margin-top:20px;
}

button{
  padding:15px 25px;
  font-size:18px;
  border:none;
  border-radius:10px;
  background:#ff4da6;
  color:white;
  margin-top:10px;
}
</style>
</head>

<body>

<!-- LOCK SCREEN -->
<div id="lockPage" class="page active">
  <h1>shuttumani 💋</h1>
  <input type="password" id="passwordInput" placeholder="Enter date">
  <button onclick="checkPassword()">Unlock</button>
</div>

<!-- ENVELOPE PAGE -->
<div id="envelopePage" class="page">
  <h2>Love Letter 💌</h2>
  <button onclick="openLetter()">Open</button>
</div>

<!-- LETTER PAGE -->
<div id="letterPage" class="page">
  <div style="height:70vh; overflow-y:auto; padding:20px;">
    YOUR LETTER HERE
  </div>
</div>

<audio id="bgMusic" loop>
  <source src="music.mp3" type="audio/mpeg">
</audio>

<script>
function show(page){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.getElementById(page).classList.add('active');
}

function checkPassword(){
  var input=document.getElementById("passwordInput").value;
  if(input==="01032025"){
    document.getElementById("bgMusic").play();
    show("envelopePage");
  }else{
    alert("Wrong password 💔");
  }
}

function openLetter(){
  show("letterPage");
}
</script>

</body>
</html>

