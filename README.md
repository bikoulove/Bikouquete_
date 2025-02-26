<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            background-image: url('https://raw.githubusercontent.com/bikoulove/La-Bikouquete/refs/heads/main/maxresdefault.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            margin: 0;
            padding: 0;
            height: 100vh;
            font-family: 'Orbitron', sans-serif;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            overflow: hidden;
            position: relative;
            animation: heartbeat 1.5s infinite;
        }
        @keyframes heartbeat {
            0% { transform: scale(1); }
            30% { transform: scale(1.02); }
            50% { transform: scale(1); }
            70% { transform: scale(1.02); }
            100% { transform: scale(1); }
        }
        .title-container {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            width: 400px;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.7);
        }
        h1 {
            font-size: 2.5rem;
            color: white;
            margin-bottom: 15px;
        }
        .code-container {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            width: 350px;
            box-shadow: 0 0 25px rgba(0, 255, 0, 0.5);
        }
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
            transform: scale(0.75);
            background-color: #00cc00;
            box-shadow: 0 0 30px rgba(0, 255, 0, 1);
        }
        .audio-container {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            padding: 10px;
            background-color: rgba(0, 0, 0, 0.7);
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
    <div class="title-container">
        <h1>La Bikouquête</h1>
    </div>
    <div class="code-container">
        <p>Entrez le code secret pour avancer</p>
        <input type="text" id="codeInput" placeholder="Code secret...">
        <br>
        <button onclick="checkCode()">Valider</button>
        <p id="result"></p>
    </div>
    <div class="audio-container">
        <audio id="heartbeatSound" autoplay loop>
            <source src="heartbeat.mp3" type="audio/mp3">
            Votre navigateur ne supporte pas la balise audio.
        </audio>
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
        // Activer automatiquement le son après 1 seconde (évite blocage des navigateurs)
        setTimeout(() => {
            const audio = document.getElementById('heartbeatSound');
            if (audio) {
                audio.play().catch(error => console.log("Lecture auto bloquée :", error));
            }
        }, 1000);
    </script>
</body>
</html>
