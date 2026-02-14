<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine 💝</title>

<style>

body{
margin:0;
background:black;
color:white;
font-family:Arial;
overflow:hidden;
text-align:center;
}

.page{
position:fixed;
inset:0;
display:none;
justify-content:center;
align-items:center;
flex-direction:column;
padding:20px;
}

.active{
display:flex;
}

/* heart rain */

.heart{
position:fixed;
top:-20px;
font-size:18px;
animation:fall linear forwards;
opacity:.8;
}

@keyframes fall{
to{
transform:translateY(110vh);
}
}

/* cinematic text */

.big{
font-size:32px;
color:#ff4da6;
margin-bottom:10px;
}

.story{
max-width:600px;
line-height:1.8;
opacity:.9;
}

/* glow */

.glow{
animation:glow 2s infinite alternate;
}

@keyframes glow{
from{
text-shadow:0 0 10px #ff4da6;
}
to{
text-shadow:0 0 30px #ff4da6;
}
}

button{
padding:14px 24px;
font-size:18px;
border:none;
border-radius:12px;
background:#ff4da6;
color:white;
margin-top:20px;
}

</style>
</head>

<body>

<!-- PAGE 1 -->
<div id="page1" class="page active">

<h1 class="big glow">Happy Valentine’s Day 💝</h1>

<p class="story">
Some stories are written by fate...  
Some stories are written by time...  
But our story was written by heart. ❤️
</p>

<button onclick="nextPage(2)">Next ➜</button>

</div>


<!-- PAGE 2 -->
<div id="page2" class="page">

<h1 class="big glow">The First Time I Saw You</h1>

<p class="story">
I was in 8th standard...  
Going to tuition like every normal day.  
But that day was not normal.  
Because that day... I saw you.  
And without knowing... my heart remembered you.
</p>

<button onclick="nextPage(3)">Next ➜</button>

</div>


<!-- PAGE 3 -->
<div id="page3" class="page">

<h1 class="big glow">The Day Everything Changed</h1>

<p class="story">
February... I told you my feelings.  
You said no.  
But my love did not stop.  
I stayed. I cared. I loved you silently.
</p>

<button onclick="nextPage(4)">Next ➜</button>

</div>


<!-- PAGE 4 -->
<div id="page4" class="page">

<h1 class="big glow">March 1, 2025 ❤️</h1>

<p class="story">
The most beautiful day of my life.  
The day you said you love me.  
The day my world became complete.
</p>

<button onclick="nextPage(5)">Next ➜</button>

</div>


<!-- PAGE 5 -->
<div id="page5" class="page">

<h1 class="big glow">My Valentine</h1>

<p class="story">
You are not just my love...  
You are my peace.  
My happiness.  
My forever.  

I Love You Shuttumani ❤️
</p>

<button onclick="goBack()">Back to Our World 🌙</button>

</div>



<script>

function nextPage(n){

document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"))

document.getElementById("page"+n).classList.add("active")

}

/* heart rain */

setInterval(()=>{

let heart=document.createElement("div")

heart.className="heart"

heart.innerHTML="❤️"

heart.style.left=Math.random()*100+"%"

heart.style.animationDuration=(3+Math.random()*3)+"s"

document.body.appendChild(heart)

setTimeout(()=>heart.remove(),6000)

},200)


/* back to main website */

function goBack(){

window.location.href="https://shuttumani.github.io/shuttumani/"

}

</script>

</body>
</html>


