<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquette</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #ff8eb5, #7f7fff);
            font-family: 'Poppins', sans-serif;
            text-align: center;
            color: white;
            overflow-x: hidden;
            height: 100vh;
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            animation: fadeIn 1s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        #intro {
            position: absolute;
            background-color: white;
            width: 100%;
            height: 100%;
            z-index: 1;
            animation: fadeOut 2s forwards;
        }
        @keyframes fadeOut {
            0% { opacity: 1; }
            100% { opacity: 0; display: none; }
        }
        h1 {
            font-size: 4em;
            font-weight: bold;
            color: #fff;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
            animation: titleAnimation 3s ease-in-out infinite alternate;
        }
        @keyframes titleAnimation {
            0% { color: #ff4da6; }
            50% { color: #7f7fff; }
            100% { color: #ff8eb5; }
        }
        .code-container {
            position: absolute;
            top: 20%;
            width: 100%;
            text-align: center;
            z-index: 1;
        }
        .code-container input {
            padding: 10px;
            font-size: 1.5em;
            width: 60%;
            border-radius: 10px;
            border: none;
            margin-top: 20px;
            text-align: center;
        }
        .code-container button {
            padding: 15px 30px;
            margin-top: 20px;
            font-size: 1.5em;
            background-color: #ff4da6;
            border: none;
            border-radius: 10px;
            color: white;
            cursor: pointer;
            transition: 0.3s;
        }
        .code-container button:hover {
            background-color: #ff007f;
        }
        .code-container p {
            color: #fff;
            font-size: 1.2em;
            margin-top: 20px;
        }
        .character-container {
            position: absolute;
            bottom: 10px;
            width: 100%;
            display: flex;
            justify-content: space-around;
            padding: 20px;
            animation: moveCharacters 10s linear infinite;
        }
        @keyframes moveCharacters {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        .character {
            width: 60px;
            height: 100px;
            background-color: #ffcccc;
            border-radius: 10px;
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            animation: jump 1.5s ease-in-out infinite;
        }
        @keyframes jump {
            0% { transform: translateY(0); }
            50% { transform: translateY(-30px); }
            100% { transform: translateY(0); }
        }
        .head {
            width: 40px;
            height: 40px;
            background-color: #ffe6e6;
            border-radius: 50%;
            position: absolute;
            top: 10px;
            left: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            border: 2px solid #ff4da6;
        }
        .eye {
            width: 8px;
            height: 8px;
            background-color: #000;
            border-radius: 50%;
            position: absolute;
        }
        .eye.left { left: 7px; top: 10px; }
        .eye.right { right: 7px; top: 10px; }
        .body {
            width: 50px;
            height: 50px;
            background-color: #ff80b3;
            border-radius: 8px;
            position: absolute;
            bottom: 0;
            left: 5px;
        }
        .arm {
            width: 15px;
            height: 25px;
            background-color: #ff66cc;
            border-radius: 5px;
            position: absolute;
            top: 20px;
        }
        .arm.left { left: -12px; }
        .arm.right { right: -12px; }
        audio {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            z-index: -1;
        }
    </style>
</head>
<body>
    <div id="intro"></div>
    <audio autoplay loop>
        <source src="your-music-file.mp3" type="audio/mpeg">
        Votre navigateur ne supporte pas l'élément audio.
    </audio>
    <h1>La Bikouquette</h1>
    <div class="code-container">
        <p>Entrez votre code secret pour commencer :</p>
        <input type="text" id="codeInput" placeholder="Entre ton code ici">
        <br>
        <button onclick="checkCode()">Valider</button>
        <p id="result"></p>
    </div>
    <div class="character-container">
        <div class="character">
            <div class="head">
                <div class="eye left"></div>
                <div class="eye right"></div>
            </div>
            <div class="body"></div>
            <div class="arm left"></div>
            <div class="arm right"></div>
        </div>
        <div class="character">
            <div class="head">
                <div class="eye left"></div>
                <div class="eye right"></div>
            </div>
            <div class="body"></div>
            <div class="arm left"></div>
            <div class="arm right"></div>
        </div>
        <div class="character">
            <div class="head">
                <div class="eye left"></div>
                <div class="eye right"></div>
            </div>
            <div class="body"></div>
            <div class="arm left"></div>
            <div class="arm right"></div>
        </div>
    </div>
    <script>
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "BIKOU123"; 
            if (code === correctCode) {
                window.location.href = "page2.html"; 
            } else {
                document.getElementById('result').innerHTML = "Code incorrect, réessaie !";
            }
        }
    </script>
</body>
</html>
