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
            background: linear-gradient(135deg, #ff8eb5, #7f7fff);
            animation: colorChange 2s infinite alternate;
            overflow: hidden;
        }
        /* Animation de dégradé */
        @keyframes colorChange {
            0% {
                background: linear-gradient(135deg, #ff8eb5, #7f7fff);
            }
            50% {
                background: linear-gradient(135deg, #ff007f, #00aaff);
            }
            100% {
                background: linear-gradient(135deg, #f9c7d9, #34b8db);
            }
        }
        /* Titre de la page */
        h1 {
            color: white;
            text-align: center;
            font-size: 40px;
            margin-top: 20px;
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
            background-color: #000;
            background-image: url('https://upload.wikimedia.org/wikipedia/commons/6/60/Pixel_Art_Pikachu_8bit.svg');
            background-size: contain;
            background-repeat: no-repeat;
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
            background-image: url('https://upload.wikimedia.org/wikipedia/commons/a/a2/Pixel_Art_8bit_Character.png');
        }
        /* Personnage 2 (brun) */
        .character2 {
            background-image: url('https://upload.wikimedia.org/wikipedia/commons/0/06/Pixel_Art_Pikachu_8bit.svg');
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
    <div class="interactive-zone">
        <h2>Discutons !</h2>
        <p>Personnage 1: "T'as vu la nouvelle quête ?"</p>
        <p>Personnage 2: "Ouais, je suis super excité de la commencer !" </p>
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
