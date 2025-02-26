<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête - Cyberpunk</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Courier New', Courier, monospace;
            overflow: hidden;
            color: #fff;
            background-color: black;
            animation: fadeIn 1s forwards;
        }
        @keyframes fadeIn {
            0% {
                background: transparent;
            }
            100% {
                background: black;
            }
        }
        h1 {
            font-family: 'Courier New', Courier, monospace;
            font-size: 4rem;
            text-align: center;
            color: white;
            text-transform: uppercase;
            background: linear-gradient(45deg, #00ff00, #ffff00, #00ff00);
            -webkit-background-clip: text;
            color: transparent;
            padding: 10px;
            border: 3px solid #00ff00;
            border-radius: 10px;
            animation: neonGlow 1.5s ease-in-out infinite alternate;
            position: relative;
            z-index: 2;
        }
        @keyframes neonGlow {
            0% {
                text-shadow: 0 0 5px #00ff00, 0 0 10px #00ff00, 0 0 15px #ffff00, 0 0 30px #00ff00;
            }
            100% {
                text-shadow: 0 0 10px #00ff00, 0 0 20px #00ff00, 0 0 30px #ffff00, 0 0 50px #ffff00;
            }
        }
        .container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            z-index: 10;
        }
        .code-input {
            margin-top: 20px;
            padding: 15px;
            font-size: 18px;
            background: rgba(0, 0, 0, 0.6);
            border: 2px solid #00ff00;
            color: #00ff00;
            border-radius: 5px;
            width: 250px;
            text-align: center;
        }
        .code-input:focus {
            outline: none;
            box-shadow: 0 0 10px #00ff00;
        }
        button {
            margin-top: 20px;
            padding: 15px 30px;
            font-size: 18px;
            background: linear-gradient(45deg, #00ff00, #ffff00);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-family: 'Courier New', Courier, monospace;
            transition: all 0.3s ease-in-out;
        }
        button:hover {
            background: linear-gradient(45deg, #ff6600, #ff0000);
        }
        .background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 255, 0, 0.2), rgba(0, 0, 0, 0.8));
            filter: blur(3px);
            z-index: -1;
            animation: waveEffect 5s infinite linear;
        }
        @keyframes waveEffect {
            0% {
                transform: scale(1);
            }
            100% {
                transform: scale(1.1);
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
            background: rgba(0, 255, 0, 0.2);
            box-shadow: 0 0 60px rgba(0, 255, 0, 0.4);
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
        .wave:hover {
            transform: scale(1.4) translate(-50%, -50%);
        }
    </style>
</head>
<body>
    <div class="background"></div>
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
                window.location.href = "page2.html"; // Redirection vers la page 2
            } else {
                alert("Code incorrect, réessayez !");
            }
        }
    </script>
</body>
</html>
