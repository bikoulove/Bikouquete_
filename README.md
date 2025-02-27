<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Orbitron', sans-serif; }
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-image: url('URL_DE_VOTRE_IMAGE');
            background-size: cover;
            background-position: center;
            transition: opacity 2s ease-in-out;
        }
        {
    background-image: url('https://raw.githubusercontent.com/bikoulove/La-Bikouquete/refs/heads/main/maxresdefault.jpg');
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
}
        .fade-in { opacity: 1; }
        .overlay {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            color: white;
            animation: heartbeat 2s infinite alternate 2s;
        }
        input {
            display: block;
            width: 110%;
            padding: 10px;
            margin: 10px 0;
            text-align: center;
            border: 2px solid white;
            background: rgba(0, 0, 0, 0.5);
            color: white;
            font-size: 16px;
        }
        button {
            padding: 10px 20px;
            border: none;
            background: white;
            color: black;
            cursor: pointer;
            transition: background 0.3s;
        }
        button:hover {
            background: gray;
        }
        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        .pink-screen {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: pink;
            z-index: 999;
            animation: fadeOut 2s forwards;
        }
        @keyframes fadeOut {
            0% { opacity: 1; }
            100% { opacity: 0; display: none; }
        }
    </style>
</head>
<body>
    <div class="pink-screen"></div>
    <div class="overlay">
        <h1>La Bikouquête</h1>
        <input type="text" id="code" placeholder="Entre le code secret pour continuer :p">
        <button onclick="verifierCode()">Valider</button>
        <p id="message" style="color: red; font-weight: bold;"></p>
    </div>
    <script>
        document.body.style.opacity = "0";
        window.onload = () => { document.body.classList.add("fade-in"); };
        function verifierCode() {
            const codeSaisi = document.getElementById("code").value;
            if (codeSaisi === "Bikou42") {
                window.location.href = "page2.html";
            } else {
                document.getElementById("message").textContent = "Rééssaye !";
            }
        }
    </script>
</body>
</html>
