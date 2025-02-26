<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête</title>
    <style>
        /* Corps de la page */
        body {
            font-family: 'Press Start 2P', cursive;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #a3a3ff, #9e3c9f);
            overflow: hidden;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            text-align: center;
            position: relative;
        }
        h1 {
            font-size: 50px;
            color: #ffffff;
            margin-bottom: 50px;
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.6);
            animation: glow 1.5s ease-in-out infinite alternate;
        }
        @keyframes glow {
            0% {
                text-shadow: 0 0 5px rgba(255, 255, 255, 0.8), 0 0 10px rgba(255, 255, 255, 0.5);
            }
            100% {
                text-shadow: 0 0 20px rgba(255, 255, 255, 1), 0 0 30px rgba(255, 255, 255, 0.8);
            }
        }
        /* Zone de code secret */
        .code-section {
            width: 80%;
            margin: 50px auto;
            padding: 30px;
            background-color: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 20px;
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
        /* Effet d'ondulation autour du curseur */
        .cursor-wave {
            position: absolute;
            top: 0;
            left: 0;
            pointer-events: none;
            width: 100vw;
            height: 100vh;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0) 80%);
            opacity: 0;
            animation: ripple-animation 1.5s infinite;
            transition: all 0.3s ease;
        }
        /* Personnages animés */
        .characters {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            justify-content: space-between;
            width: 60%;
        }
        .character {
            width: 80px;
            height: 120px;
            position: relative;
            animation: moveCharacter 1.5s linear infinite alternate;
        }
        /* Animation de mouvement des personnages */
        @keyframes moveCharacter {
            0% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
            100% {
                transform: translateY(0);
            }
        }
        /* Animation de l'effet d'ondulation du curseur */
        @keyframes ripple-animation {
            0% {
                opacity: 0;
                transform: scale(0);
            }
            50% {
                opacity: 0.5;
                transform: scale(1.5);
            }
            100% {
                opacity: 0;
                transform: scale(0);
            }
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
        <img src="personnage-blond.png" alt="Personnage blond animé" class="character">
        <img src="personnage-brun.png" alt="Personnage brun animé" class="character">
    </div>
    <!-- Effet d'ondulation autour du curseur -->
    <div class="cursor-wave"></div>
    <script>
        // Détection du mouvement de la souris et ajout de l'ondulation
        document.body.addEventListener('mousemove', function (e) {
            const wave = document.querySelector('.cursor-wave');
            const x = e.clientX;
            const y = e.clientY;
            wave.style.left = x - 50 + 'px';
            wave.style.top = y - 50 + 'px';
            wave.style.opacity = 1;
        });
        // Fonction pour changer la couleur de fond au survol de la souris
        document.body.addEventListener('mousemove', function () {
            const r = Math.floor(Math.random() * 256);
            const g = Math.floor(Math.random() * 256);
            const b = Math.floor(Math.random() * 256);
            document.body.style.background = `linear-gradient(135deg, rgb(${r}, ${g}, ${b}), #9e3c9f)`;
        });
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "Victoire"; // Remplace par ton vrai code secret
            if (code === correctCode) {
                window.location.href = "page2.html"; // Redirige vers la deuxième page
            } else {
                document.getElementById('result').innerHTML = "Code incorrect, réessaie !";
            }
        }
    </script>
</body>
</html>
