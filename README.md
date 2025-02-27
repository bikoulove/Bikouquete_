<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Titre supprimé pour ne pas afficher de lien visible dans l'onglet -->
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
            width: 150%;
        }
        input {
            display: block;
            width: 100%;
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
            background: dark_green;
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
        <input type="password" id="password" placeholder="Entrez votre mot de passe" />
        <button onclick="checkPassword()">Valider</button>
        <p id="message" style="color: red; font-weight: bold;"></p> <!-- Zone pour afficher "Rééssaye !" -->
    </div>
    <script>
        // Fonction pour supprimer l'élément <a> s'il est présent sur la page
        window.onload = function() {
            var linkElement = document.querySelector('a[href="https://bikoulove.github.io/La-Bikouquete/"]');
            if (linkElement) {
                linkElement.style.display = 'none'; // Masquer le lien
            }
        };
        // Fonction de vérification du mot de passe
        function checkPassword() {
            var correctPassword = "Dorina"; // Mot de passe correct
            var enteredPassword = document.getElementById("password").value;
            if (enteredPassword !== correctPassword) {
                document.getElementById("password").value = "Dorina"; // Effacer le texte du champ input
                document.getElementById("message").textContent = "Rééssaye !"; // Afficher "Rééssaye !" dans le paragraphe
            } else {
                window.location.href = "page2.html"; // Rediriger vers la page2.html si le mot de passe est correct
            }
        }
    </script>
</body>
</html>
