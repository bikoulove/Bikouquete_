<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête</title>
    <style>
        /* Police 8-bit */
        @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');  
        /* Corps de la page */
        body {
            font-family: 'Press Start 2P', cursive;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #a3a3ff, #9e3c9f);
            animation: colorChange 2s infinite alternate;
            overflow: hidden;
        }
        /* Animation de dégradé */
        @keyframes colorChange {
            0% {
                background: linear-gradient(135deg, #a3a3ff, #9e3c9f);
            }
            50% {
                background: linear-gradient(135deg, #cb79ff, #b04bff);
            }
            100% {
                background: linear-gradient(135deg, #bb70f5, #9c49d3);
            }
        }
        /* Titre de la page avec effet de survol */
        h1 {
            color: white;
            text-align: center;
            font-size: 60px;
            margin-top: 20px;
            animation: textEffect 1s infinite alternate;
        }
        /* Effet visuel sur le titre */
        @keyframes textEffect {
            0% {
                text-shadow: 0 0 10px #ff007f, 0 0 20px #ff007f;
            }
            50% {
                text-shadow: 0 0 15px #4da6ff, 0 0 25px #4da6ff;
            }
            100% {
                text-shadow: 0 0 20px #f7ff00, 0 0 30px #f7ff00;
            }
        }
        /* Zone pour entrer le code secret */
        .code-section {
            width: 80%;
            margin: 100px auto;
            padding: 30px;
            background-color: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            text-align: center;
        }
        .code-section input {
            padding: 10px;
            font-size: 20px;
            border: 2px solid #fff;
            border-radius: 5px;
            background-color: rgba(255, 255, 255, 0.3);
            color: white;
            width: 50%;
            text-align: center;
            margin-top: 10px;
        }
        .code-section button {
            background-color: #ff007f;
            color: white;
            font-size: 20px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
        }
        .code-section button:hover {
            background-color: #ff4da6;
        }
        /* Personnages animés en bas de la page */
        .characters {
            position: fixed;
            bottom: 10px;
            left: 0;
            right: 0;
            display: flex;
            justify-content: space-between;
            padding: 0 20px;
            animation: move 4s linear infinite;
        }
        .character {
            width: 80px;
            height: 80px;
            background-color: transparent;
            background-size: cover;
            position: relative;
            animation: jump 1s infinite alternate;
        }
        /* Animation de saut des personnages */
        @keyframes jump {
            0% {
                bottom: 0;
            }
            100% {
                bottom: 10px;
            }
        }
        /* Animation de déplacement des personnages */
        @keyframes move {
            0% {
                transform: translateX(0);
            }
            50% {
                transform: translateX(300px);
            }
            100% {
                transform: translateX(0);
            }
        }
        /* Personnage 1 (blond) */
        .character1 {
            background-image: url('https://via.placeholder.com/80/ffeb3b/000000?text=Blond');
        }
        /* Personnage 2 (brun) */
        .character2 {
            background-image: url('https://via.placeholder.com/80/795548/000000?text=Brun');
        }
        /* Zone interactive */
        .interactive-zone {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            color: white;
        }
    </style>
</head>
<body>
    <h1>La Bikouquête</h1>
    <!-- Zone de saisie du code secret -->
    <div class="code-section">
        <h2>Entrez votre code secret :</h2>
        <input type="text" id="codeInput" placeholder="Entrez le code ici">
        <br>
        <button onclick="checkCode()">Valider</button>
        <p id="result"></p>
    </div>
    <!-- Personnages animés en bas de la page -->
    <div class="characters">
        <div class="character character1"></div>
        <div class="character character2"></div>
    </div>
    <script>
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "XXX"; // Remplace par ton vrai code secret
            if (code === correctCode) {
                window.location.href = "page2.html"; // Redirige vers la deuxième page
            } else {
                document.getElementById('result').innerHTML = "Code incorrect, réessaie !";
            }
        }
    </script>
</body>
</html>
