<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête</title>
    <link href="https://fonts.googleapis.com/css2?family=Honk&display=swap" rel="stylesheet">
    <style>
        body {
            background-image: url('https://raw.githubusercontent.com/bikoulove/La-Bikouquete/refs/heads/main/maxresdefault.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            margin: 0;
            padding: 0;
            height: 100vh;
            font-family: 'Honk', sans-serif;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            overflow: hidden;
            position: relative;
        }
        /* Effet de fondu au blanc lors du chargement (1.5s) */
        body::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: pink;
            animation: fadeIn 1.5s ease-in-out forwards;
        }
        @keyframes fadeIn {
            0% { opacity: 1; }
            100% { opacity: 0; }
        }
        /* Effet d'ondulation lent blanc et gris */
        .wave {
            position: absolute;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, rgba(128,128,128,0.2) 100%);
            border-radius: 50%;
            opacity: 0.7;
            pointer-events: none;
            animation: slowWaves 6s infinite ease-in-out;
            transition: transform 0.2s ease-out;
        }
@keyframes slowWaves {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.5); }
        }
        /* Titre centré avec contour noir */
        h1 {
            font-size: 3rem;
            text-align: center;
            color: white;
            text-shadow: 3px 3px 0px black, -3px -3px 0px black, -3px 3px 0px black, 3px -3px 0px black;
            margin-bottom: 20px;
        }
        /* Conteneur pour le code */
        .code-container {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 30px;
            border: 3px solid #00FF00;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 0 25px rgba(0, 255, 0, 0.5);
            width: 350px;
        }
        /* Champs de texte */
        input {
            padding: 15px;
            border: 2px solid #00FF00;
            border-radius: 10px;
            background-color: transparent;
            color: white;
            font-size: 1.5rem;
            margin-bottom: 20px;
            width: 250px;
            text-align: center;
        }
        /* Bouton */
        button {
            background-color: #00FF00;
            padding: 15px 30px;
            font-size: 1.5rem;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.3s;
            color: white;
            font-weight: bold;
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.8);
        }
        button:hover {
            background-color: #00cc00;
            box-shadow: 0 0 20px rgba(0, 255, 0, 1);
        }
        /* Zone sonore */
        .audio-container {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            padding: 10px;
            background-color: rgba(0, 0, 0, 0.7);
            border: 3px solid #00FF00;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.5);
            width: 300px;
            text-align: center;
        }
        audio {
            width: 100%;
        }
    </style>
</head>
<body>
    <h1>La Bikouquête</h1>
    <div class="code-container">
        <p>Entrez le code secret pour avancer</p>
        <input type="text" id="codeInput" placeholder="Code secret...">
        <br>
        <button onclick="checkCode()">Valider</button>
        <p id="result"></p>
    </div>
    <!-- Zone sonore -->
    <div class="audio-container">
        <audio id="backgroundMusic" autoplay>
            <source src="your-audio-file.mp3" type="audio/mp3">
            Votre navigateur ne supporte pas la balise audio.
        </audio>
    </div>
    <script>
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "Bikou123"; // Code secret pour la page suivante
            if (code === correctCode) {
                window.location.href = "page2.html"; // Redirige vers une nouvelle page
            } else {
                document.getElementById('result').innerText = "Code incorrect, réessayez.";
            }
        }
        // Effet d'ondulation qui suit la souris
        document.addEventListener('mousemove', function(e) {
            let wave = document.querySelector('.wave');
            if (!wave) {
                wave = document.createElement('div');
                wave.classList.add('wave');
                document.body.appendChild(wave);
            }
            wave.style.left = `${e.clientX - 100}px`;
            wave.style.top = `${e.clientY - 100}px`;
        });
        // Activer automatiquement la musique après 1 seconde
        setTimeout(() => {
            const audio = document.getElementById('backgroundMusic');
            if (audio) {
                audio.play().catch(error => console.log("Lecture auto bloquée par le navigateur :", error));
            }
        }, 1000);
    </script>
</body>
</html>
