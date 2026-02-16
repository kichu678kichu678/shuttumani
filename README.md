<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Shuttumani 💗</title>

<style>

body{
margin:0;
font-family:Arial;
background:linear-gradient(180deg,#000,#0a0a0a);
color:white;
overflow:hidden;
}

/* page system */
.page{
position:fixed;
inset:0;
display:none;
}

.active{
display:flex;
}

/* lock screen */
#lockPage{
justify-content:center;
align-items:center;
background:radial-gradient(circle,#111,#000);
}

.lockBox{
background:#111;
padding:35px;
border-radius:20px;
box-shadow:0 0 40px rgba(255,77,166,0.4);
text-align:center;
}

.lockTitle{
font-size:28px;
margin-bottom:15px;
color:#ff4da6;
}

input{
padding:14px;
border-radius:12px;
border:none;
font-size:18px;
text-align:center;
width:220px;
background:#222;
color:white;
}

/* chat page */
#chatPage{
flex-direction:column;
}

/* header */
.header{
display:flex;
align-items:center;
gap:10px;
padding:15px;
background:#0f0f0f;
border-bottom:1px solid #222;
}

.avatar{
width:40px;
height:40px;
border-radius:50%;
background:#ff4da6;
display:flex;
align-items:center;
justify-content:center;
font-weight:bold;
}

.userInfo{
flex:1;
}

.name{
font-size:18px;
}

.status{
font-size:13px;
color:#aaa;
}

/* online dot */
.dot{
width:10px;
height:10px;
border-radius:50%;
background:#0f0;
display:inline-block;
margin-right:5px;
box-shadow:0 0 8px #0f0;
}

/* messages */
.messages{
flex:1;
overflow-y:auto;
padding:15px;
display:flex;
flex-direction:column;
gap:10px;
}

.msg{
padding:12px 16px;
border-radius:14px;
max-width:70%;
animation:fadeIn 0.3s;
}

.me{
background:#ff4da6;
align-self:flex-end;
}

.her{
background:#222;
align-self:flex-start;
}

@keyframes fadeIn{
from{opacity:0;transform:translateY(10px);}
to{opacity:1;transform:translateY(0);}
}

/* typing */
.typing{
font-size:13px;
color:#aaa;
padding-left:15px;
height:20px;
}

/* input */
.inputArea{
display:flex;
gap:10px;
padding:10px;
background:#0f0f0f;
}

.inputArea input{
flex:1;
}

button{
padding:14px 25px;
border:none;
border-radius:12px;
background:#ff4da6;
color:white;
font-size:16px;
cursor:pointer;
}

/* floating hearts */
.heart{
position:fixed;
bottom:-10px;
animation:float 6s linear infinite;
color:#ff4da6;
}

@keyframes float{
from{transform:translateY(0);}
to{transform:translateY(-110vh);}
}

</style>

</head>
<body>

<!-- LOCK PAGE -->
<div id="lockPage" class="page active">

<div class="lockBox">

<div class="lockTitle">
Shuttumani 💗
</div>

<input id="password" placeholder="Enter date">

<br><br>

<button onclick="unlock()">Unlock</button>

</div>

</div>


<!-- CHAT PAGE -->
<div id="chatPage" class="page">

<!-- header -->
<div class="header">

<div class="avatar">
S
</div>

<div class="userInfo">

<div class="name">
Shuttumani
</div>

<div class="status">
<span class="dot"></span>Online
</div>

</div>

</div>


<!-- messages -->
<div id="messages" class="messages">
</div>

<div id="typing" class="typing"></div>


<!-- input -->
<div class="inputArea">

<input id="msgInput"
placeholder="Type message..."
oninput="typing()"
onkeydown="if(event.key==='Enter') send()">

<button onclick="send()">Send</button>

</div>

</div>


<audio id="sound">
<source src="https://www.soundjay.com/buttons/sounds/button-3.mp3">
</audio>


<script>

/* PASSWORD */
const PASSWORD="01032025";


function unlock(){

const input=document.getElementById("password").value;

if(input===PASSWORD){

show("chatPage");

}
else{

alert("Wrong date 💔");

}

}


/* show page */
function show(id){

document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));

document.getElementById(id).classList.add("active");

}


/* send message */
function send(){

const input=document.getElementById("msgInput");

const text=input.value.trim();

if(!text) return;

addMsg(text,"me");

input.value="";

document.getElementById("typing").innerText="";

document.getElementById("sound").play();

}


/* add message */
function addMsg(text,type){

const div=document.createElement("div");

div.className="msg "+type;

div.innerText=text;

document.getElementById("messages").appendChild(div);

scroll();

}


function scroll(){

document.getElementById("messages").scrollTop=999999;

}


/* typing indicator */
function typing(){

document.getElementById("typing").innerText="Typing...";

clearTimeout(window.typingTimer);

window.typingTimer=setTimeout(()=>{
document.getElementById("typing").innerText="";
},1000);

}


/* floating hearts */
setInterval(()=>{

const heart=document.createElement("div");

heart.className="heart";

heart.innerText="💗";

heart.style.left=Math.random()*100+"%";

document.body.appendChild(heart);

setTimeout(()=>heart.remove(),6000);

},700);

</script>

</body>
</html>
