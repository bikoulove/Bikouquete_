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
            background: rgba(0, 0, 0, 0.7);
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
        .building-style {
            border: 2px solid #00ff00;
            border-radius: 10px;
            padding: 10px;
            background-color: rgba(0, 0, 0, 0.7);
            margin-top: 20px;
            width: 270px;
            text-align: center;
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.6);
        }
    </style>
</head>
<body>
    <div class="background"></div>
    <h1>La Bikouquête</h1>
    <div class="container">
        <div class="building-style">
            <input class="code-input" type="text" id="codeInput" placeholder="Entrez le code secret">
            <br>
            <button onclick="checkCode()">Valider</button>
        </div>
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
        // Ondulations suivant le curseur
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
