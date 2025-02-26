<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête</title>
    <link href="https://fonts.googleapis.com/css2?family=Honk&display=swap" rel="stylesheet">
    <style>
        body {
            /* Fond de la page avec image depuis GitHub */
            background-image: url('https://raw.githubusercontent.com/bikoulove/La-Bikouquete/refs/heads/main/maxresdefault.jpg'); /* URL de l'image */
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
        /* Titre principal stylisé */
        h1 {
            text-align: center;
            font-size: 4rem;
            margin-bottom: 20px;
            text-shadow: 0 0 15px rgba(0, 255, 0, 1), 0 0 30px rgba(0, 255, 0, 0.7);
            color: white;
            font-weight: bold;
        }
        /* Conteneur pour le code secret */
        .code-container {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 30px;
            border: 3px solid #00FF00;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 0 25px rgba(0, 255, 0, 0.5);
        }
        /* Champs de texte */
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
        /* Bouton de validation */
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
            background-color: #00cc00;
            box-shadow: 0 0 20px rgba(0, 255, 0, 1);
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
