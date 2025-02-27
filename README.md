<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Orbitron', sans-serif; }
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-image: url('https://raw.githubusercontent.com/bikoulove/La-Bikouquete/refs/heads/main/maxresdefault.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }
        .overlay {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            color: white;
            animation: heartbeat 1s infinite alternate 2s;
            width: 100%;
        }
        input {
            display: block;
            width: 120%;
            padding: 12px;
            margin: 15px auto;
            text-align: center;
            border: 2px solid white;
            background: rgba(0, 0, 0, 0.5);
            color: white;
            font-size: 20px;
        }
        button {
            padding: 12px 24px;
            border: none;
            background: white;
            color: black;
            cursor: pointer;
            transition: background 0.3s;
            display: block;
            margin: 15px auto;
            font-size: 18px;
        }
        button:hover {
            background: gray;
        }
        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); background: rgba(0, 0, 0, 0.5); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>
    <div class="overlay">
        <input type="text" id="code" placeholder="Entre le code secret pour continuer :p">
        <button onclick="verifierCode()">Valider</button>
        <p id="message" style="color: red; font-weight: bold;"></p>
    </div>
    <script>
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
