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
            animation: heartbeat 2s infinite;
        }
        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            20%, 60% { transform: scale(1.05); }
            40%, 80% { transform: scale(1); }
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
        /* Titre dans le cadre noir */
        .title-container {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 15px 30px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
            margin-bottom: 20px;
        } 
        h1 {
            font-size: 4rem;
            color: white;
            text-shadow: 4px 4px 0px black, -4px -4px 0px black;
            margin: 0;
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
