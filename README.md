<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête</title>
    <link href="https://fonts.googleapis.com/css2?family=Honk&display=swap" rel="stylesheet">
    <style>
        body {
            /* Ajout de l'image en fond */
            background-image: url('https://www.rockpapershotgun.com/cyberpunk-2077-netflix-anime-series-announced-cyberpunk-edgerunners'); /* Remplacer par l'URL de l'image */
            background-size: cover;  /* L'image couvre toute la page */
            background-position: center;
            background-attachment: fixed;
            margin: 0;
            padding: 0;
            height: 100vh;  /* Assure que l'image couvre toute la hauteur */
            font-family: 'Honk', sans-serif;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            overflow: hidden;
        }
        /* Effet d'ondulation qui suit le curseur */
        body::after {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            background: radial-gradient(circle, rgba(0, 255, 0, 0.5), rgba(0, 255, 255, 0.5));
            mix-blend-mode: multiply;
            animation: ripple 2s infinite linear;
        }
        @keyframes ripple {
            0% {
                transform: scale(0);
                opacity: 1;
            }
            100% {
                transform: scale(1);
                opacity: 0;
            }
        }
        /* Titre et texte */
        h1 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 10px rgba(0, 255, 0, 0.7);
        }
        .code-container {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 20px;
            border: 3px solid #00FF00;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
        }
        input {
            padding: 10px;
            border: 1px solid #00FF00;
            border-radius: 5px;
            background-color: transparent;
            color: white;
            font-size: 1.5rem;
            margin-bottom: 15px;
            width: 100%;
        }
        button {
            background-color: #00FF00;
            padding: 10px 20px;
            font-size: 1.5rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
            color: white;
        }
        button:hover {
            background-color: #00cc00;
        }
        /* Animation de transition de fond lors du chargement */
        .fade-in {
            animation: fadeIn 1s ease-in-out;
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
    </style>
</head>
<body class="fade-in">
    <h1>Bienvenue dans la Bikouquête</h1>
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
            const correctCode = "Bikou123"; // Code secret pour la page suivante
            if (code === correctCode) {
                window.location.href = "page2.html"; // Redirige vers une nouvelle page
            } else {
                document.getElementById('result').innerText = "Code incorrect, réessayez.";
            }
        }
    </script>
</body>
</html>
