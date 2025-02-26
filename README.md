<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
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
        /* Effet de fondu au blanc au chargement */
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
        /* Titre centré avec contour noir */
        h1 {
            font-size: 4rem;
            text-align: center;
            color: white;
            text-shadow: 4px 4px 0px black, -4px -4px 0px black, -4px 4px 0px black, 4px -4px 0px black;
            margin-bottom: 20px;
            position: relative;
            z-index: 10;
        }
        /* Conteneur du code */
        .code-container {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 30px;
            border: 3px solid #00FF00;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 0 25px rgba(0, 255, 0, 0.5);
            width: 350px;
            position: relative;
            z-index: 10;
        }
        /* Champ de texte */
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
            position: relative;
            z-index: 10;
        }
        /* Effet sur le bouton au passage de la souris */
        button:hover {
            transform: scale(0.75);
            background-color: #00cc00;
            box-shadow: 0 0 30px rgba(0, 255, 0, 1);
        }
        /* Effet d'ondulation */
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
    <script>
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "Bikou123";
            if (code === correctCode) {
                window.location.href = "page2.html";
            } else {
                document.getElementById('result').innerText = "Code incorrect, réessayez.";
            }
        }
        // Création et gestion des ondes
        const waves = [];
        for (let i = 0; i < 5; i++) {
            let wave = document.createElement('div');
            wave.classList.add('wave');
            wave.style.top = `${Math.random() * window.innerHeight}px`;
            wave.style.left = `${Math.random() * window.innerWidth}px`;
            document.body.appendChild(wave);
            waves.push(wave);
        }
        document.addEventListener('mousemove', function(e) {
            waves.forEach((wave, index) => {
                setTimeout(() => {
                    wave.style.left = `${e.clientX - 100}px`;
                    wave.style.top = `${e.clientY - 100}px`;
                }, index * 100);
            });
        });
    </script>
</body>
</html>
