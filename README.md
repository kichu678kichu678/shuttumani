<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>🔒 Shuttumani Private Chat</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>

body{
margin:0;
font-family:Arial;
background:linear-gradient(135deg,#0a0a0a,#1a0033,#000);
color:white;
}

.center{
display:flex;
justify-content:center;
align-items:center;
height:100vh;
flex-direction:column;
}

.box{
background:rgba(255,255,255,0.05);
padding:25px;
border-radius:15px;
width:90%;
max-width:400px;
backdrop-filter:blur(10px);
}

input{
width:100%;
padding:12px;
margin:8px 0;
border-radius:10px;
border:none;
background:rgba(255,255,255,0.1);
color:white;
}

button{
padding:12px;
border:none;
border-radius:10px;
background:linear-gradient(45deg,#ff0080,#ff66cc);
color:white;
width:100%;
margin-top:10px;
font-weight:bold;
}

#chatPage{
display:none;
padding:15px;
}

#messages{
height:60vh;
overflow:auto;
border-radius:10px;
padding:10px;
background:rgba(255,255,255,0.05);
}

.msg{
background:#ff008055;
padding:10px;
margin:5px;
border-radius:10px;
}

.top{
display:flex;
justify-content:space-between;
align-items:center;
margin-bottom:10px;
}

.online{
color:#00ff88;
font-weight:bold;
}

</style>
</head>

<body>

<!-- UNLOCK PAGE -->

<div id="unlockPage" class="center">

<div class="box">

<h2>🔒 Secret Unlock</h2>

<input id="secretInput" placeholder="Enter secret word">

<button onclick="unlock()">Unlock</button>

</div>

</div>

<!-- LOGIN PAGE -->

<div id="loginPage" class="center" style="display:none">

<div class="box">

<h2>Login ❤️</h2>

<input id="email" placeholder="Email">
<input id="password" type="password" placeholder="Password">

<button onclick="login()">Login</button>

<button onclick="enableNotifications()">Enable Notifications</button>

</div>

</div>

<!-- CHAT PAGE -->

<div id="chatPage">

<div class="top">

<h3>Our Room 💬</h3>

<div id="status" class="online">Offline</div>

<button onclick="logout()">Logout</button>

</div>

<div id="messages"></div>

<input id="msgInput" placeholder="Type message">

<button onclick="sendMessage()">Send</button>

</div>

<!-- FIREBASE + CHAT SCRIPT -->

<script type="module">

import { initializeApp } from "https://www.gstatic.com/firebasejs/12.9.0/firebase-app.js";

import {
getAuth,
signInWithEmailAndPassword,
onAuthStateChanged,
signOut
}
from "https://www.gstatic.com/firebasejs/12.9.0/firebase-auth.js";

import {
getFirestore,
collection,
addDoc,
query,
orderBy,
onSnapshot,
serverTimestamp
}
from "https://www.gstatic.com/firebasejs/12.9.0/firebase-firestore.js";

import {
getMessaging,
getToken,
onMessage
}
from "https://www.gstatic.com/firebasejs/12.9.0/firebase-messaging.js";


const firebaseConfig = {

apiKey: "AIzaSyDJ5nrd-sCZNvCsg3THxXhewT0cBzkDoCI",

authDomain: "shuttumani-chat.firebaseapp.com",

projectId: "shuttumani-chat",

storageBucket: "shuttumani-chat.firebasestorage.app",

messagingSenderId: "1033302224383",

appId: "1:1033302224383:web:952bdfed407ab257cf0bca"

};

const app = initializeApp(firebaseConfig);

const auth = getAuth();

const db = getFirestore();

const messaging = getMessaging(app);


window.unlock = function(){

const secret="ammede ponnu njana";

const input=document.getElementById("secretInput").value;

if(input===secret){

document.getElementById("unlockPage").style.display="none";

document.getElementById("loginPage").style.display="flex";

}else{

alert("Wrong secret");

}

}


window.login = function(){

const email=document.getElementById("email").value;

const pass=document.getElementById("password").value;

signInWithEmailAndPassword(auth,email,pass)

.then(()=>{})

.catch(()=>alert("Login failed"));

}


onAuthStateChanged(auth,user=>{

if(user){

document.getElementById("loginPage").style.display="none";

document.getElementById("chatPage").style.display="block";

document.getElementById("status").innerText="Online";

loadMessages();

}

});


window.logout=function(){

signOut(auth);

location.reload();

}


window.sendMessage=async function(){

const text=document.getElementById("msgInput").value;

if(text==="")return;

await addDoc(collection(db,"messages"),{

text:text,

user:auth.currentUser.email,

time:serverTimestamp()

});

document.getElementById("msgInput").value="";

}


function loadMessages(){

const q=query(collection(db,"messages"),orderBy("time"));

onSnapshot(q,snap=>{

const div=document.getElementById("messages");

div.innerHTML="";

snap.forEach(doc=>{

const d=doc.data();

div.innerHTML+=`

<div class="msg">

${d.text}

<br>

<small>${d.user}</small>

</div>

`;

});

});

}


window.enableNotifications=async function(){

const permission=await Notification.requestPermission();

if(permission==="granted"){

alert("Notifications enabled");

}

}


onMessage(messaging,(payload)=>{

new Notification("New message ❤️");

});

</script>

</body>
</html>
