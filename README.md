<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Corps de la page - Style Cyberpunk */
        body {
            font-family: 'Press Start 2P', cursive;
            margin: 0;
            padding: 0;
            background: #111;
            overflow: hidden;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            text-align: center;
            position: relative;
            color: #00ff99; /* Vert néon */
        }
        h1 {
            font-size: 60px;
            color: #ff00ff; /* Rose néon */
            margin-bottom: 50px;
            text-shadow: 0 0 10px rgba(255, 0, 255, 0.8), 0 0 20px rgba(255, 0, 255, 0.6);
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
        /* Zone de saisie du code secret */
        .code-section {
            width: 80%;
            margin: 50px auto;
            padding: 30px;
            background-color: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            border: 2px solid #00ff99;
        }
        .code-section input {
            padding: 10px;
            font-size: 20px;
            border: 2px solid #ff00ff;
            border-radius: 5px;
            background-color: rgba(255, 255, 255, 0.3);
            color: white;
            width: 50%;
            text-align: center;
            margin-top: 10px;
        }
        .code-section button {
            background-color: #00ff99;
            color: black;
            font-size: 20px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 0.3s ease;
        }
        .code-section button:hover {
            background-color: #ff00ff;
        }
        /* Effet d'ondulation géométrique */
        .wave-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .wave {
            position: absolute;
            width: 200%;
            height: 200%;
            border-radius: 50%;
            animation: wave-animation 4s infinite linear;
            opacity: 0.5;
        }
        .wave:nth-child(1) {
            background-color: rgba(0, 255, 255, 0.2);
            animation-duration: 3.5s;
        }
        .wave:nth-child(2) {
            background-color: rgba(255, 0, 255, 0.4);
            animation-duration: 4s;
        }
        .wave:nth-child(3) {
            background-color: rgba(0, 255, 255, 0.3);
            animation-duration: 4.5s;
        }
        @keyframes wave-animation {
            0% {
                transform: scale(0);
                opacity: 0.5;
            }
            100% {
                transform: scale(1);
                opacity: 0;
            }
        }
        /* Effet de changement de couleur */
        body {
            transition: background 1s ease-in-out;
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
    <!-- Vagues animées en fond -->
    <div class="wave-container">
        <div class="wave"></div>
        <div class="wave"></div>
        <div class="wave"></div>
    </div>
    <script>
        // Effet de changement de couleur du fond au survol de la souris
        document.body.addEventListener('mousemove', function() {
            const r = Math.floor(Math.random() * 256);
            const g = Math.floor(Math.random() * 256);
            const b = Math.floor(Math.random() * 256);
            document.body.style.background = `linear-gradient(135deg, rgb(${r}, ${g}, ${b}), #111)`;
        });
        // Fonction pour vérifier le code secret
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "XXX"; // Remplace avec ton vrai code secret
            if (code === correctCode) {
                window.location.href = "page2.html"; // Redirige vers la deuxième page
            } else {
                document.getElementById('result').innerHTML = "Code incorrect, réessaie !";
            }
        }
    </script>
</body>
</html>
