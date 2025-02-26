<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête - Personnages Manga Animés</title>
    <style>
        /* Style global de la page */
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
        h1::after {
            content: "⚡";
            font-size: 1.5em;
            color: #fff;
            animation: blink 1s step-end infinite;
        }
        .character-container {
            position: absolute;
            bottom: 10px;
            width: 100%;
            display: flex;
            justify-content: space-around;
            padding: 20px;
            animation: moveCharacters 5s linear infinite;
        }
        @keyframes moveCharacters {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        .character {
            width: 50px;
            height: 80px;
            background-color: #fff;
            border-radius: 10px;
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            animation: running 0.8s steps(3) infinite;
        }
        @keyframes running {
            from { transform: translateX(0); }
            to { transform: translateX(100px); }
        }
        .head {
            width: 30px;
            height: 30px;
            background-color: #ffe6e6;
            border-radius: 50%;
            position: absolute;
            top: 5px;
            left: 10px;
        }
        .eye {
            width: 8px;
            height: 8px;
            background-color: #000;
            border-radius: 50%;
            position: absolute;
        }
        .eye.left { left: 7px; top: 8px; }
        .eye.right { right: 7px; top: 8px; }
        .body {
            width: 40px;
            height: 40px;
            background-color: #ff99cc;
            border-radius: 8px;
            position: absolute;
            bottom: 0;
            left: 5px;
        }
        .arm {
            width: 10px;
            height: 20px;
            background-color: #ff80b3;
            border-radius: 5px;
            position: absolute;
            top: 25px;
        }
        .arm.left { left: -10px; }
        .arm.right { right: -10px; }
        audio {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            z-index: -1;
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
    </style>
</head>
<body>
    <audio autoplay loop>
        <source src="your-music-file.mp3" type="audio/mpeg">
        Votre navigateur ne supporte pas l'élément audio.
    </audio>
    <h1>Bienvenue dans la Bikouquête !</h1>
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
        // Fonction pour vérifier le code secret
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "BIKOU123"; // Change le code ici pour l'adapter
            if (code === correctCode) {
                window.location.href = "https://exemple.com/nouvelle-page"; // Remplace par la page suivante
            } else {
                document.getElementById('result').innerHTML = "Code incorrect, réessaie !";
            }
        }
    </script>

</body>
</html>
