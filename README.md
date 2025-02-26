<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête</title>
    <style>
        @font-face {
            font-family: 'CustomFont';
            src: url('https://github.com/bikoulove/La-Bikouquete/raw/refs/heads/main/SaucerBB.woff2') format('woff2'),
                 url('https://github.com/bikoulove/La-Bikouquete/raw/refs/heads/main/SaucerBB.woff') format('woff');
            font-weight: normal;
            font-style: normal;
        }
        body {
            background-image: url('https://raw.githubusercontent.com/bikoulove/La-Bikouquete/refs/heads/main/maxresdefault.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            margin: 0;
            padding: 0;
            height: 100vh;
            font-family: 'CustomFont', sans-serif;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }
        @keyframes heartbeat {
            0% { transform: scale(1); }
            30% { transform: scale(1.02); }
            50% { transform: scale(1); }
            70% { transform: scale(1.02); }
            100% { transform: scale(1); }
        }
        /* Effet heartbeat sur le fond */
        .background-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: inherit;
            background-size: cover;
            background-position: center;
            animation: heartbeat 2.5s infinite;
        }
        /* Conteneur principal */
        .main-container {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 30px;
            border-radius: 5px;
            text-align: center;
            width: 400px;
            box-shadow: 0 0 30px rgba(0, 255, 0, 0.7);
            animation: heartbeat 2.5s infinite;
        }
        .main-container p {
            font-size: 1.8rem;
        }
        input {
            padding: 15px;
            border: 2px solid #00FF00;
            border-radius: 5px;
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
            border-radius: 5px;
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
        /* Masquer complètement l'audio */
        .hidden-audio {
            display: none;
        }
    </style>
</head>
<body>
    <div class="background-container"></div>
    <div class="main-container">
        <p>La Bikouquête</p>
        <p>Entrez le code secret pour avancer</p>
        <input type="text" id="codeInput" placeholder="Code secret...">
        <br>
        <button onclick="checkCode()">Valider</button>
        <p id="result"></p>
    </div>
    <audio class="hidden-audio" autoplay loop>
        <source src="URL_DE_TON_SON.mp3" type="audio/mpeg">
    </audio>
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
    </script>
</body>
</html>
