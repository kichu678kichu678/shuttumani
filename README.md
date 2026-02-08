index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Ponnu ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');

        :root {
            --primary: #ff4d6d;
            --dark: #1a0a0c;
            --soft-pink: #ffb3c1;
        }

        * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

        body, html {
            margin: 0; padding: 0;
            font-family: 'Poppins', sans-serif;
            background-color: var(--dark);
            color: white;
            overflow: hidden;
            height: 100vh; width: 100vw;
        }

        /* --- 1. LOCK SCREEN --- */
        #lock-screen {
            position: fixed; inset: 0;
            background: radial-gradient(circle, #2a0d13 0%, #000 100%);
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
            z-index: 5000; transition: transform 0.8s cubic-bezier(0.7, 0, 0.3, 1);
        }

        #lock-screen h2 { font-family: 'Dancing Script', cursive; font-size: 2.5rem; margin-bottom: 20px; color: var(--primary); }

        #lock-screen input {
            background: rgba(255,255,255,0.1); border: 2px solid var(--primary);
            border-radius: 30px; padding: 15px 25px; color: white;
            text-align: center; font-size: 1.2rem; outline: none; width: 80%; max-width: 300px;
        }

        .shake { animation: shake 0.5s; }
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-10px); }
            75% { transform: translateX(10px); }
        }

        /* --- TRANSITION POPUP --- */
        #transition-popup {
            position: fixed; inset: 0; background: white; z-index: 6000;
            display: none; justify-content: center; align-items: center;
            color: var(--primary); font-size: 2rem; font-weight: bold; text-align: center;
        }

        /* --- HEART ANIMATION ENGINE --- */
        .heart-container { position: fixed; inset: 0; pointer-events: none; z-index: 1000; overflow: hidden; }
        .heart { position: absolute; color: var(--primary); opacity: 0.6; filter: drop-shadow(0 0 5px var(--primary)); animation: float 5s linear infinite; }
        @keyframes float {
            0% { transform: translateY(105vh) rotate(0deg) scale(1); opacity: 0.8; }
            100% { transform: translateY(-10vh) rotate(360deg) scale(1.5); opacity: 0; }
        }

        /* --- CONTENT WRAPPER --- */
        #app-shell { display: none; height: 100vh; width: 100vw; position: relative; }
        
        section {
            height: 100vh; width: 100vw;
            display: none; flex-direction: column;
            align-items: center; justify-content: center;
            padding: 30px; overflow-y: auto; text-align: center;
            background: linear-gradient(to bottom, #1a0a0c, #2d0b12);
        }
        .active { display: flex; }

        /* --- 4. LOVE LETTER --- */
        .envelope { font-size: 100px; cursor: pointer; transition: 0.3s; }
        .envelope:active { transform: scale(0.9); }
        
        .letter-paper {
            background: #fff9fb; color: #333; padding: 30px; border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5); line-height: 1.8;
            max-width: 500px; text-align: left; display: none;
            max-height: 70vh; overflow-y: auto; position: relative;
        }

        /* --- COUNTDOWN --- */
        .timer-box { font-size: 1.5rem; font-weight: bold; color: var(--primary); margin: 20px 0; }
        .memory-list { text-align: left; background: rgba(255,255,255,0.05); padding: 20px; border-radius: 15px; }
        .memory-list p { margin: 10px 0; font-size: 0.9rem; }

        /* --- OPTIONS HUB --- */
        .hub-grid { display: grid; gap: 15px; width: 100%; max-width: 300px; }
        .hub-btn {
            background: var(--primary); color: white; border: none; padding: 20px;
            border-radius: 15px; font-size: 1.1rem; font-weight: bold; cursor: pointer;
        }

        /* --- UI HELPERS --- */
        .back-btn { position: absolute; top: 20px; left: 20px; background: none; border: 1px solid white; color: white; border-radius: 50%; width: 40px; height: 40px; cursor: pointer; }
        .swipe-hint { position: absolute; bottom: 20px; font-size: 0.8rem; opacity: 0.6; animation: bounce 2s infinite; }
        @keyframes bounce { 0%, 20%, 50%, 80%, 100% {transform: translateY(0);} 40% {transform: translateY(-10px);} 60% {transform: translateY(-5px);} }

        iframe { border-radius: 15px; border: none; background: white; }

        .image-container { display: flex; gap: 10px; flex-wrap: wrap; justify-content: center; }
        .img-box { width: 140px; height: 180px; background: #333; border-radius: 10px; border: 2px solid var(--primary); overflow: hidden; }
        .img-box img { width: 100%; height: 100%; object-fit: cover; }
    </style>
</head>
<body>

    <audio id="bg-music" loop><source src="music.mp3" type="audio/mpeg"></audio>

    <div id="lock-screen">
        <h2>Privacy Lock</h2>
        <input type="text" id="pass-input" placeholder="Type password...">
        <p style="margin-top: 20px; font-size: 0.8rem; color: #666;">Hint: ammede ponnu...</p>
    </div>

    <div id="transition-popup">ammede ponnu araaa💋💋</div>

    <div id="app-shell">
        <div class="heart-container" id="hearts"></div>

        <section id="page-letter" class="active">
            <div id="env-icon" class="envelope" onclick="openLetter()">✉️</div>
            <div id="letter-container" class="letter-paper">
                <h3 style="color: var(--primary); text-align: center;">Happy Valentine's Day ponnahhh❤💋💋🫂</h3>
                <p id="letter-text">
                    eth nee appozha vayika ennu arayillla Appozhayalum vayikulooo ninthe first Valentine's Day annu ennu okke ariyaaa nee annu tution nu varo ennu polum arayilla ethu Azhuthumbo pinne ollathu exam okke alle ath Kazhinja kanan polum pattillalo appo enth cheyyum nee vallathum aloichu vechit indooo vaveee enthe oru idea il korach okkee indu ath Njan parayaneee pinne kali akkanda ketta Njan romantic alla ennu paranju nee enthe eduth ethuuu matte parayana oru dhivasam varum daaaa nokkikooo pinne entha sugalle engane okke nadanna mathiyooo vellapozhum enne kurich okke ortholu tta marannu povaruthu nammal mindandu aya entha indava ponnah enthayalum nammal kanum enganelum okke enthelum mindum athokke orapa pinne ammede ponnu aradaaaa 😘🩷❤️💋🫂 exam kazhinju graduation nu enthavavo kalikan poovanel ninak ath scn avum ennu enik ariyaaaaa bhaki Allavarum adipoli ayit avide erikumbo enthe ponnu matharam blaa blaaa blaaaa enthaleeeee nja. Avide annelum ninthe thanne alledaaaaaa enthokke aleeeeee eni korach serious ayit paraya 
                    <br><br>
                    Atheeee enik ninne bhayankara ishtam a neee yes parayo ennu arayilla ennalum enik entho parayanam ennu thooni neee Chilappo enne angane kandit undavilla ennalum Njan eth eni paranjillel eni annelum eth parayumbo annu paranjel Njan yes paranjene ennu nee Paranja enik veshamam avummm atha eppo parayane enik ninne bhayankara ishtam a <b style="color:var(--primary)">"I Love You❤️"</b>
                    <br><br>
                    Nee ethinu rply thannolu Chilappo eth kelkumbo nee ennod eni mindi ennu varilla angane onnum venda tta ishtam allel ath Paranja mathi scn ella eppo ishtam annu paranju ennu vech kozhapam ellata nammal pazhayath pole thanne veliya vethasam onnum ella nammal thammil ethra kollam ayit ariyaaa pinne angotum engotum ariyathathu onnum ellanu vekkanu Ninak enne ishtam anno ennu arayilla eni eth parayumbozhano athine kurich aloikane ennu polum arayilla enth okke annelum neee enthe koode indel adipoli avum ennu thooni athokke thanne prethekish onnum ella ethokke thanne appo aloichu okke paranjolu tta eppo ninne ishtapedan Karanam ennu okke choicha nee nalla kochanu mariyathak okke nokkum enthelum okke ninnod Paranja nee avide veenolum veliya scn onnnum ella oru kidilan kocha neee athranne pinne elle enthokke okke vannalum 10 kazhinju pooyalum scn onnum indavalle tta enik ninnod olla ishtam poovilla enik aennum nee enthe koch thanneya Neeyum poovilla ennu Njan vishwosikunnu sharkareee. Aloichu okke eni paranjolu tta 
                    <br><br>
                    Appo veendum paraya <b style="color:var(--primary)">I LOVE YOU ❤️</b>
                </p>
                <button onclick="changePage('page-countdown')" style="width: 100%; padding: 10px; margin-top: 10px; border: none; background: var(--primary); color: white; border-radius: 5px;">Swipe Down ↓</button>
            </div>
            <div class="swipe-hint">Swipe Down to Continue</div>
        </section>

        <section id="page-countdown">
            <h2>We Committed on 01/03/2025</h2>
            <div class="timer-box" id="timer">00d 00h 00m 00s</div>
            <div class="memory-list">
                <p>📍 <b>01/03/2025</b> - She said back that she loves me</p>
                <p>📍 <b>05/06/2023</b> - First time I saw her in the tution class</p>
                <p>📍 <b>20/07/2010</b> - When she came into the world</p>
            </div>
            <div class="swipe-hint">Swipe Right →</div>
        </section>

        <section id="page-diary">
            <h2>Daily Diary</h2>
            <p style="font-size: 0.8rem; margin-bottom: 10px;">Reply everyday after seeing my messages!</p>
            <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSc1JncNbHTVKlZooN4NaDi_Ov08J6Q1g-v5PMHlNnZ_mcGp6A/viewform?embedded=true" width="100%" height="450">Loading…</iframe>
            <div class="swipe-hint">Swipe Up ↑</div>
        </section>

        <section id="page-hub">
            <h2 style="font-family: 'Dancing Script';">Our Worlds</h2>
            <div class="hub-grid">
                <button class="hub-btn" onclick="changePage('page-time')">Our Time</button>
                <button class="hub-btn" onclick="changePage('page-memories')">Memories</button>
                <button class="hub-btn" onclick="changePage('page-oneday')">One Day</button>
            </div>
            <div class="swipe-hint" onclick="changePage('page-upload')">Swipe Up for Photos ↑</div>
        </section>

        <section id="page-time">
            <button class="back-btn" onclick="changePage('page-hub')">←</button>
            <h2>Our Time</h2>
            <div class="image-container">
                <div class="img-box"><img src="your-photo1.jpg" alt="Memory"></div>
                <div class="img-box"><img src="your-photo2.jpg" alt="Memory"></div>
            </div>
            <p style="margin-top: 20px; font-style: italic;">Every second with you is a romantic transition...</p>
        </section>

        <section id="page-memories">
            <button class="back-btn" onclick="changePage('page-hub')">←</button>
            <h2>Memories</h2>
            <p style="background: rgba(0,0,0,0.3); padding: 20px; border-radius: 10px; font-size: 0.9rem;">
                Tution class... that long wooden bench and table where we sat together. 
                I still feel your hand in mine as we shared our day. 
                Remember the staircase whispers on the way to the second floor? 
                Every step we took was a secret story only we knew.
            </p>
        </section>

        <section id="page-oneday">
            <button class="back-btn" onclick="changePage('page-hub')">←</button>
            <h2>One Day</h2>
            <p>Our Wedding. Our Future Life.</p>
            <div class="img-box" style="width: 250px; height: 150px; margin-bottom: 10px;">
                <img src="https://via.placeholder.com/250x150" alt="Wedding Vision">
            </div>
            <p style="font-size: 0.9rem;">A life of peaceful togetherness and endless love. I see us, hand in hand, forever.</p>
        </section>

        <section id="page-upload">
            <h2>Private Photo Upload</h2>
            <p style="font-size: 0.8rem;">Fully private. Just for us.</p>
            <div class="image-container">
                <div class="img-box" style="border-style: dashed;"><p style="font-size: 0.6rem; margin-top: 40%;">Your Slot</p></div>
                <div class="img-box"><img src="https://via.placeholder.com/140x180" alt="Her Photo"></div>
            </div>
            <br>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSc1JncNbHTVKlZooN4NaDi_Ov08J6Q1g-v5PMHlNnZ_mcGp6A/viewform" target="_blank" style="color: var(--primary);">Upload New Photo Here</a>
            <div class="swipe-hint">Swipe Left ←</div>
        </section>

        <section id="page-surprise">
            <h1 style="font-family: 'Dancing Script'; font-size: 3rem;">I Loved It So Much</h1>
            <p style="max-width: 80%; line-height: 1.6;">
                A place where both of us can just live in. 
                This is my creation for you. 
                I hope this artistic space makes you feel how much you mean to me.
            </p>
            <div class="swipe-hint">Swipe Up for Conclusion ↑</div>
        </section>

        <section id="page-conclusion">
            <div class="letter-paper" style="display: block; font-size: 0.85rem;">
                ethokke enthe idea annu athra adipoli anno ennu arayilla Ninak ishtam avoo ennu arayilla enthanelum enik ninne bhayankara ishtam a nayeeee ethokke korach variety annu ennu vechuuu athaaaa nee pinne ammede ponnu alleda suttumaniiii ❤️💋💋💋💋💋 ummahhhh💋💋💋💋 love you 😘😘😘😘😘 appo Randalum angot engotum poovand randaleyum nokki nadaka ketta ummahhhh 💋💋💋
            </div>
            <button onclick="finalReturn()" style="background: var(--primary); border: none; color: white; padding: 15px 30px; border-radius: 25px; margin-top: 20px; font-weight: bold;">Love you forever</button>
            <div class="swipe-hint">Swipe Left to go Home ←</div>
        </section>
    </div>

    <script>
        const passInput = document.getElementById('pass-input');
        const lockScreen = document.getElementById('lock-screen');
        const transitionPopup = document.getElementById('transition-popup');
        const appShell = document.getElementById('app-shell');
        const bgMusic = document.getElementById('bg-music');

        // PASSWORD CHECK
        passInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                if (passInput.value === 'ammede ponnu araaa💋💋') {
                    handleUnlock();
                } else {
                    passInput.classList.add('shake');
                    setTimeout(() => passInput.classList.remove('shake'), 500);
                }
            }
        });

        function handleUnlock() {
            transitionPopup.style.display = 'flex';
            setTimeout(() => {
                transitionPopup.style.display = 'none';
                lockScreen.style.transform = 'translateY(-100%)';
                appShell.style.display = 'block';
                bgMusic.play();
                createHearts();
                startTimer();
            }, 2500);
        }

        // NAVIGATION ENGINE
        function changePage(pageId) {
            document.querySelectorAll('section').forEach(s => s.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
        }

        function openLetter() {
            document.getElementById('env-icon').style.display = 'none';
            document.getElementById('letter-container').style.display = 'block';
        }

        function finalReturn() {
            const over = document.getElementById('transition-popup');
            over.innerHTML = "I Love You suttumaniiii ❤️ 💋 ummahhhh";
            over.style.display = 'flex';
            setTimeout(() => {
                over.style.display = 'none';
                changePage('page-letter');
            }, 3000);
        }

        // SWIPE GESTURES
        let touchstartX = 0; let touchstartY = 0;
        document.addEventListener('touchstart', e => { touchstartX = e.changedTouches[0].screenX; touchstartY = e.changedTouches[0].screenY; });
        document.addEventListener('touchend', e => {
            let x = e.changedTouches[0].screenX; let y = e.changedTouches[0].screenY;
            handleSwipe(touchstartX, x, touchstartY, y);
        });

        function handleSwipe(x1, x2, y1, y2) {
            const activePage = document.querySelector('section.active').id;
            if (y1 - y2 > 100) { // Swipe Up
                if (activePage === 'page-diary') changePage('page-hub');
                if (activePage === 'page-hub') changePage('page-upload');
                if (activePage === 'page-surprise') changePage('page-conclusion');
            }
            if (y2 - y1 > 100) { // Swipe Down
                if (activePage === 'page-letter') changePage('page-countdown');
            }
            if (x1 - x2 > 100) { // Swipe Left
                if (activePage === 'page-countdown') changePage('page-diary');
                if (activePage === 'page-upload') changePage('page-surprise');
                if (activePage === 'page-conclusion') finalReturn();
            }
        }

        // HEART FACTORY
        function createHearts() {
            const container = document.getElementById('hearts');
            setInterval(() => {
                const heart = document.createElement('div');
                heart.innerHTML = '❤️';
                heart.className = 'heart';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
                heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
                container.appendChild(heart);
                setTimeout(() => heart.remove(), 5000);
            }, 400);
        }

        // TIMER FACTORY
        function startTimer() {
            const commitDate = new Date("March 1, 2025 00:00:00").getTime();
            setInterval(() => {
                const now = new Date().getTime();
                const diff = now - commitDate;
                const d = Math.floor(diff / (1000 * 60 * 60 * 24));
                const h = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const m = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
                const s = Math.floor((diff % (1000 * 60)) / 1000);
                document.getElementById('timer').innerHTML = `${d}d ${h}h ${m}m ${s}s`;
            }, 1000);
        }
    </script>
</body>
</html>



