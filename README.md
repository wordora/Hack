<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>SYSTEM CRITICAL ERROR</title>
    <style>
        body, html { margin: 0; padding: 0; width: 100%; height: 100%; background: black; overflow: hidden; font-family: 'Courier New', monospace; }
        #matrix-bg { position: fixed; top: 0; left: 0; width: 100%; height: 100%; color: #00FF00; font-size: 14px; white-space: pre-wrap; word-break: break-all; opacity: 0.4; z-index: 1; }
        .overlay { position: relative; z-index: 10; display: flex; align-items: center; justify-content: center; height: 100vh; }
        .warning-box { background: rgba(20, 0, 0, 0.9); border: 3px solid #ff0000; padding: 40px; text-align: center; box-shadow: 0 0 50px #ff0000; max-width: 500px; color: white; animation: shake 0.5s infinite; }
        @keyframes shake { 0% { transform: translate(1px, 1px); } 20% { transform: translate(-3px, 0px); } 40% { transform: translate(3px, 2px); } 60% { transform: translate(-1px, -1px); } 80% { transform: translate(-1px, -2px); } 100% { transform: translate(1px, -2px); } }
        h1 { color: #ff0000; font-size: 2rem; text-transform: uppercase; }
        .timer-text { font-size: 3rem; color: #ffff00; margin: 20px 0; font-weight: bold; }
        .btn { background: #ff0000; color: white; padding: 15px 30px; font-size: 1.2rem; border: none; cursor: pointer; font-weight: bold; }
        #prank-screen { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: linear-gradient(45deg, #12c2e9, #c471ed, #f64f59); z-index: 100; flex-direction: column; align-items: center; justify-content: center; color: white; text-align: center; }
    </style>
</head>
<body>
    <div id="matrix-bg"></div>
    <div class="overlay" id="main-content">
        <div class="warning-box">
            <h1>⚠️ SYSTEM COMPROMISED ⚠️</h1>
            <p>1000 TK না পাঠালে আপনার সমস্ত তথ্য ডিলিট হয়ে যাবে!</p>
            <div class="timer-text" id="timer">05:00</div>
            <button class="btn" onclick="triggerPrank()">নিচের এইখানে ক্লিক করলে টাকা পাঠান</button>
        </div>
    </div>
    <div id="prank-screen">
        <h2>😂 PRANKED! 😂</h2>
        <p>Your device is safe. This was just a simulation by <b>AI King</b>.</p>
    </div>
    <script>
        const bg = document.getElementById('matrix-bg');
        const chars = "W*(&)A#A#*(A#*%)(&%)*()&%#$@!^&*(0987654321";
        function updateMatrix() {
            let content = "";
            for(let i=0; i<1500; i++) { content += chars.charAt(Math.floor(Math.random() * chars.length)); }
            bg.innerText = content;
        }
        setInterval(updateMatrix, 50);
        let timeLeft = 300;
        setInterval(() => {
            if (timeLeft <= 0) return;
            timeLeft--;
            let mins = Math.floor(timeLeft / 60);
            let secs = timeLeft % 60;
            document.getElementById('timer').innerText = `0${mins}:${secs < 10 ? '0' + secs : secs}`;
        }, 1000);
        function triggerPrank() {
            document.getElementById('main-content').style.display = 'none';
            document.getElementById('prank-screen').style.display = 'flex';
        }
    </script>
</body>
</html>
