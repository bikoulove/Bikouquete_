<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
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
            animation: heartbeat 2s infinite alternate 2s;
        }
        input {
            display: block;
            width: 110%;
            padding: 10px;
            margin: 10px auto;
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
            display: block;
            margin: 10px auto;
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
        <h1>La Bikouquête</h1>
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
