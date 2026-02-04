index. html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Meghana ❤️</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Georgia', serif;
}

body {
  background: linear-gradient(135deg, #ffafbd, #ffc3a0);
  height: 100vh;
  overflow: hidden;
}

/* LOCK */
#lock {
  position: fixed;
  inset: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

input {
  padding: 12px;
  border-radius: 8px;
  border: none;
  font-size: 16px;
  margin-top: 10px;
}

button {
  margin-top: 10px;
  padding: 10px 20px;
  border: none;
  border-radius: 20px;
  background: #ff6b81;
  color: white;
  font-size: 16px;
}

/* MWAAH */
#mwah {
  position: fixed;
  inset: 0;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 60px;
  color: white;
  display: none;
  animation: pop 2s ease;
}

@keyframes pop {
  0% { transform: scale(0.3); opacity: 0; }
  50% { transform: scale(1.3); opacity: 1; }
  100% { transform: scale(1); opacity: 1; }
}

/* LETTER */
#letter-box {
  position: fixed;
  inset: 0;
  display: none;
  justify-content: center;
  align-items: center;
}

.envelope {
  font-size: 70px;
  cursor: pointer;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%,100% { transform: translateY(0); }
  50% { transform: translateY(-15px); }
}

.letter {
  background: white;
  padding: 25px;
  border-radius: 20px;
  max-width: 90%;
  text-align: center;
  display: none;
}

/* HEARTS */
.heart {
  position: fixed;
  bottom: -20px;
  color: red;
  font-size: 20px;
  animation: float 6s linear infinite;
}

@keyframes float {
  to {
    transform: translateY(-120vh);
    opacity: 0;
  }
}
</style>
</head>

<body>

<!-- LOCK -->
<div id="lock">
  <h2>Enter Our Date ❤️</h2>
  <input type="password" id="pass" placeholder="DDMMYYYY">
  <button onclick="unlock()">Unlock</button>
</div>

<!-- MWAAH -->
<div id="mwah">UMMAAA 💋💋</div>

<!-- LETTER -->
<div id="letter-box">
  <div class="envelope" onclick="openLetter()">💌</div>

  <div class="letter" id="letter">
    <h2>My Love ❤️</h2>
    <p>
      Meghana,<br><br>
      From the day you came into my life,  
      everything felt softer, warmer, and meaningful.  
      Even when distance comes between us,  
      my heart will always choose you.<br><br>

      01-03-2025 is not just a date,  
      it is the day my forever began.<br><br>

      Even if we cannot see each other for days,  
      my love never leaves you for a second.
    </p>
    <br>
    <strong>Faithfully yours,<br>shuttumaniii ❤️</strong>
  </div>
</div>

<script>
function unlock() {
  const p = document.getElementById("pass").value;
  if (p === "01032025") {
    document.getElementById("lock").style.display = "none";
    document.getElementById("mwah").style.display = "flex";

    setTimeout(() => {
      document.getElementById("mwah").style.display = "none";
      document.getElementById("letter-box").style.display = "flex";
      hearts();
    }, 2000);
  } else {
    alert("Wrong password ❤️");
  }
}

function openLetter() {
  document.querySelector(".envelope").style.display = "none";
  document.getElementById("letter").style.display = "block";
}

function hearts() {
  setInterval(() => {
    const h = document.createElement("div");
    h.className = "heart";
    h.innerHTML = "❤️";
    h.style.left = Math.random() * 100 + "vw";
    document.body.appendChild(h);
    setTimeout(() => h.remove(), 6000);
  }, 500);
}
</script>

</body>
</html>
