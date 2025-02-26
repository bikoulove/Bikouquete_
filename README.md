<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête - Cyberpunk</title>
    <link href="https://fonts.googleapis.com/css2?family=Honk&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Honk', sans-serif;
            overflow: hidden;
            background: linear-gradient(135deg, #1a1a1a, #ff00ff, #00ff00, #0000ff);
            background-size: 300% 300%;
            animation: gradientMove 6s ease infinite;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            position: relative;
        }
        @keyframes gradientMove {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }
        h1 {
            font-size: 5rem;
            text-align: center;
            color: #fff;
            text-transform: uppercase;
            background: linear-gradient(45deg, #ff00ff, #00ff00, #0000ff);
            -webkit-background-clip: text;
            color: transparent;
            padding: 10px;
            border: 3px solid #ff00ff;
            border-radius: 10px;
            animation: neonGlow 1.5s ease-in-out infinite alternate;
            position: relative;
            z-index: 2;
        }
        @keyframes neonGlow {
            0% {
                text-shadow: 0 0 5px #ff00ff, 0 0 10px #ff00ff, 0 0 15px #00ff00, 0 0 30px #ff00ff;
            }
            100% {
                text-shadow: 0 0 10px #ff00ff, 0 0 20px #ff00ff, 0 0 30px #00ff00, 0 0 50px #00ff00;
            }
        }
        .container {
            text-align: center;
            padding: 20px;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 15px;
            border: 3px solid #ff00ff;
            box-shadow: 0 0 20px #ff00ff;
            width: 350px;
        }
        .code-input {
            margin-top: 20px;
            padding: 15px;
            font-size: 18px;
            background: rgba(0, 0, 0, 0.9);
            border: 3px solid #00ff00;
            color: #00ff00;
            border-radius: 10px;
            width: 250px;
            text-align: center;
            font-family: 'Honk', sans-serif;
            transition: border-color 0.3s;
            box-shadow: 0 0 5px rgba(0, 255, 0, 0.6);
        }
        .code-input:focus {
            outline: none;
            box-shadow: 0 0 10px #00ff00;
            border-color: #ffff00;
        }
        button {
            margin-top: 20px;
            padding: 15px 30px;
            font-size: 18px;
            background: linear-gradient(45deg, #00ff00, #ffff00);
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-family: 'Honk', sans-serif;
            transition: all 0.3s ease-in-out;
        }
        button:hover {
            background: linear-gradient(45deg, #ff6600, #ff0000);
        }
        /* Ondulations du fond */
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
        /* Effet de suivi du curseur */
        .cursor-wave {
            position: absolute;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 1;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .cursor-wave div {
            position: absolute;
            border-radius: 50%;
            width: 80px;
            height: 80px;
            background-color: rgba(0, 255, 0, 0.4);
            animation: cursorRipple 1.2s linear infinite;
        }
        @keyframes cursorRipple {
            0% {
                transform: scale(0.5);
                opacity: 0.5;
            }
            100% {
                transform: scale(3);
                opacity: 0;
            }
        }
        /* Style de l'arrière-plan (effet cyberpunk) */
        .background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 255, 0, 0.1), rgba(0, 0, 0, 0.8));
            filter: blur(4px);
            z-index: -1;
            animation: cityBackground 6s infinite linear;
        }
        @keyframes cityBackground {
            0% {
                transform: scale(1) translate(0, 0);
            }
            50% {
                transform: scale(1.05) translate(10%, 10%);
            }
            100% {
                transform: scale(1) translate(0, 0);
            }
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
    <div class="cursor-wave"></div>
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
        // Effets ondulants au suivi du curseur
        document.body.addEventListener("mousemove", function(event) {
            const cursorWave = document.querySelector('.cursor-wave');
            const waveDiv = document.createElement('div');
            waveDiv.style.top = `${event.clientY - 40}px`;
            waveDiv.style.left = `${event.clientX - 40}px`;
            cursorWave.appendChild(waveDiv);
            setTimeout(() => waveDiv.remove(), 1200);
        });
    </script>
</body>
</html>
