<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            margin: 0;
            padding: 0;
            background: #1a1a1a;
            font-family: 'Orbitron', sans-serif;
            overflow: hidden;
            color: #fff;
            animation: fadeIn 1s forwards; /* Ajout de l'animation fadeIn */
        }
        @keyframes fadeIn {
            0% {
                background: transparent;
            }
            100% {
                background: #ffffff; /* Fondu au blanc */
            }
        }
        h1 {
            font-family: 'Press Start 2P', cursive;
            font-size: 4rem;
            text-align: center;
            text-transform: uppercase;
            background: linear-gradient(45deg, #ff00cc, #00ffff);
            -webkit-background-clip: text;
            color: transparent;
            animation: neonGlow 1.5s ease-in-out infinite alternate;
        }
        @keyframes neonGlow {
            0% {
                text-shadow: 0 0 5px #ff00cc, 0 0 10px #ff00cc, 0 0 15px #ff00cc, 0 0 20px #00ffff, 0 0 30px #00ffff;
            }
            100% {
                text-shadow: 0 0 10px #ff00cc, 0 0 20px #ff00cc, 0 0 30px #ff00cc, 0 0 40px #00ffff, 0 0 50px #00ffff;
            }
        }
        .container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            z-index: 10;
            animation: waveEffect 2s ease-in-out infinite;
        }
        @keyframes waveEffect {
            0% {
                transform: translate(-50%, -50%) rotate(0deg);
            }
            50% {
                transform: translate(-50%, -50%) rotate(10deg);
            }
            100% {
                transform: translate(-50%, -50%) rotate(0deg);
            }
        }
        .code-input {
            margin-top: 20px;
            padding: 15px;
            font-size: 18px;
            background: rgba(0, 0, 0, 0.6);
            border: 2px solid #00ffff;
            color: #00ffff;
            border-radius: 5px;
            width: 250px;
            text-align: center;
            font-family: 'Courier New', Courier, monospace;
        }
        .code-input:focus {
            outline: none;
            box-shadow: 0 0 10px #ff00cc, 0 0 15px #ff00cc;
        }
        button {
            margin-top: 20px;
            padding: 15px 30px;
            font-size: 18px;
            background: linear-gradient(45deg, #ff00cc, #00ffff);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-family: 'Orbitron', sans-serif;
            transition: all 0.3s ease-in-out;
        }
        button:hover {
            background: linear-gradient(45deg, #ff00cc, #ff6600);
        }
        .background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://cdn.pixabay.com/photo/2016/11/29/03/26/robot-1867270_960_720.jpg') no-repeat center center fixed;
            background-size: cover;
            filter: blur(5px);
            z-index: -1;
            animation: backgroundEffect 3s ease-in-out infinite alternate;
        }
        @keyframes backgroundEffect {
            0% {
                filter: blur(5px);
            }
            100% {
                filter: blur(8px);
            }
        }
        .wave {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 500px;
            height: 500px;
            border-radius: 50%;
            background: rgba(0, 255, 255, 0.2);
            box-shadow: 0 0 60px rgba(0, 255, 255, 0.4);
            animation: waveMovement 2.5s linear infinite;
        }
        @keyframes waveMovement {
            0% {
                transform: translate(-50%, -50%) scale(0.8);
            }
            50% {
                transform: translate(-50%, -50%) scale(1.2);
            }
            100% {
                transform: translate(-50%, -50%) scale(0.8);
            }
        }
    </style>
</head>
<body>
    <div class="background"></div>
    <div class="wave"></div>
    <h1>La Bikouquête</h1>
    <div class="container">
        <input class="code-input" type="text" id="codeInput" placeholder="Entrez le code secret">
        <br>
        <button onclick="checkCode()">Valider</button>
    </div>
    <script>
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "xxx"; 
            if (code === correctCode) {
                alert("Code correct ! Vous êtes prêt pour la prochaine étape.");
                window.location.href = "page2.html";
            } else {
                alert("Code incorrect, réessayez !");
            }
        }
    </script>
</body>
</html>
