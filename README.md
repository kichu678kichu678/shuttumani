index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Suttumani ❤️</title>
    <style>
        body, html {
            margin: 0; padding: 0;
            font-family: 'Poppins', sans-serif;
            background-color: #fff0f3;
            height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        #lock-screen {
            position: fixed; width: 100%; height: 100%;
            background: white; z-index: 1000;
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
        }
        #lock-screen h2 { color: #ff4d6d; }
        #lock-screen input {
            padding: 15px; font-size: 1.2rem;
            border: 2px solid #ff4d6d; border-radius: 50px;
            text-align: center; outline: none; width: 250px;
            margin-bottom: 20px;
        }
        
        /* Added Button Style */
        #enterBtn {
            padding: 10px 30px;
            font-size: 1.2rem;
            background-color: #ff4d6d;
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
        }

        #popup-msg {
            display: none; position: fixed; top: 0; left: 0;
            width: 100%; height: 100%; background: white;
            z-index: 2000; justify-content: center; align-items: center;
            font-size: 2.2rem; color: #ff4d6d; font-weight: bold;
            text-align: center; padding: 20px;
        }

        #main-content { display: none; }
    </style>
</head>
<body>

    <div id="lock-screen">
        <h2>Enter Code ❤️</h2>
        <input type="password" id="passInput" placeholder="DDMMYYYY">
        <button id="enterBtn" onclick="checkPassword()">Enter</button>
    </div>

    <div id="popup-msg">ammede ponnu araaa💋💋</div>

    <div id="main-content">
        <h1>Site Loaded</h1>
    </div>

    <audio id="bgMusic" loop>
        <source src="music.mp3" type="audio/mpeg">
    </audio>

    <script>
        function checkPassword() {
            const input = document.getElementById('passInput').value;
            
            if (input === "01032025") {
                document.getElementById('lock-screen').style.display = 'none';
                const popup = document.getElementById('popup-msg');
                popup.style.display = 'flex';
                
                // Play music after interaction
                const music = document.getElementById('bgMusic');
                music.play().catch(e => console.log(e));
                
                setTimeout(() => {
                    popup.style.display = 'none';
                    document.getElementById('main-content').style.display = 'block';
                }, 3000);
            } else {
                alert("Incorrect Password");
            }
        }
    </script>
</body>
</html>
