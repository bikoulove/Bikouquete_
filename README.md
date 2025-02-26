<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bikouquête - Code Secret</title>
    <style>
        /* Style général */
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            background: linear-gradient(45deg, #FF69B4, #FF1493); /* Gradient coloré qui pop */
            color: white;
            text-align: center;
            padding: 50px;
            background-size: cover;
            background-position: center;
            animation: fadeIn 1.5s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        h1 {
            font-size: 3.5em;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
            margin-bottom: 20px;
        }

        /* Zone du jeu de piste */
        .game-container {
            background-color: rgba(255, 255, 255, 0.5); /* Fond semi-transparent pour faire ressortir le texte */
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
            margin-top: 40px;
            display: inline-block;
            width: 60%;
            max-width: 600px;
        }

        /* Styles pour le champ de texte et bouton */
        input {
            padding: 15px;
            font-size: 18px;
            margin-bottom: 20px;
            border-radius: 10px;
            border: none;
            outline: none;
            width: 70%;
            text-align: center;
            background-color: #FFB6C1;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
            color: #333;
        }

        input:focus {
            background-color: #FF69B4;
            color: white;
        }

        button {
            padding: 12px 25px;
            font-size: 18px;
            background-color: #FF6347;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        }

        button:hover {
            background-color: #FF4500;
        }

        /* Personnages manga */
        .manga-character {
            width: 150px;
            margin: 30px 0;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.6);
        }

        /* Texte du message */
        #message {
            font-size: 1.5em;
            font-weight: bold;
            margin-top: 20px;
            color: yellow;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }

        /* Animation de texte */
        @keyframes glow {
            0% { text-shadow: 0 0 5px #ff99cc, 0 0 10px #ff99cc, 0 0 15px #ff99cc, 0 0 20px #ff1493; }
            50% { text-shadow: 0 0 10px #ff99cc, 0 0 20px #ff99cc, 0 0 30px #ff99cc, 0 0 40px #ff1493; }
            100% { text-shadow: 0 0 5px #ff99cc, 0 0 10px #ff99cc, 0 0 15px #ff99cc, 0 0 20px #ff1493; }
        }

        .glowing-text {
            animation: glow 1.5s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <h1 class="glowing-text">Bienvenue dans la Bikouquête !</h1>
    
    <!-- Musique de fond -->
    <audio autoplay loop>
        <source src="https://example.com/kpop-music.mp3" type="audio/mp3">
        Votre navigateur ne prend pas en charge l'élément audio.
    </audio>

    <!-- Zone de jeu -->
    <div class="game-container">
        <img src="https://example.com/manga-character.png" alt="Personnage Manga" class="manga-character">
        <p>Entrez le code secret pour avancer dans l'aventure !</p>
        <input type="text" id="code" placeholder="Entrez le code ici">
        <br>
        <button onclick="checkCode()">Valider</button>

        <p id="message"></p>
    </div>

    <script>
        function checkCode() {
            const code = document.getElementById('code').value;
            const correctCode = 'KPOP123'; // Change ce code par le vrai code
            if (code === correctCode) {
                document.getElementById('message').innerText = 'Code correct ! Vous avez débloqué le niveau suivant !';
                document.getElementById('message').style.color = '#00FF00'; // Vert pour le succès
                window.location.href = 'https://autresite.com'; // Redirige vers un autre site
            } else {
                document.getElementById('message').innerText = 'Code incorrect. Essayez encore !';
                document.getElementById('message').style.color = '#FF0000'; // Rouge pour l'échec
            }
        }
    </script>
</body>
</html>
