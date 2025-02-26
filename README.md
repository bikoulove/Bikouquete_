<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquête - Personnages Manga Animés</title>
    <style>
        /* Style général de la page */
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #ff8eb5, #7f7fff);
            font-family: 'Poppins', sans-serif;
            text-align: center;
            color: white;
            overflow-x: hidden;
        }

        /* Titre de la page */
        h1 {
            margin-top: 10%;
            font-size: 3em;
            color: #fff;
            animation: fadeIn 1.5s ease-in-out;
        }

        /* Animation d'apparition du titre */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Conteneur des personnages */
        .character-container {
            position: absolute;
            bottom: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            padding: 20px;
            animation: moveCharacters 5s linear infinite;
        }

        /* Animation de mouvement des personnages */
        @keyframes moveCharacters {
            0% {
                transform: translateX(-100%);
            }
            100% {
                transform: translateX(100%);
            }
        }

        /* Style des personnages */
        .character {
            width: 50px;
            height: 80px;
            background-color: #fff;
            border-radius: 10px;
            position: relative;
        }

        /* Tête */
        .head {
            width: 30px;
            height: 30px;
            background-color: #ffe6e6;
            border-radius: 50%;
            position: absolute;
            top: 10px;
            left: 10px;
        }

        /* Yeux */
        .eye {
            width: 8px;
            height: 8px;
            background-color: #000;
            border-radius: 50%;
            position: absolute;
        }

        .eye.left {
            left: 7px;
            top: 8px;
        }

        .eye.right {
            right: 7px;
            top: 8px;
        }

        /* Corps */
        .body {
            width: 40px;
            height: 40px;
            background-color: #ff99cc;
            border-radius: 8px;
            position: absolute;
            bottom: 0;
            left: 5px;
        }

        /* Bras */
        .arm {
            width: 10px;
            height: 20px;
            background-color: #ff80b3;
            border-radius: 5px;
            position: absolute;
            top: 25px;
        }

        .arm.left {
            left: -10px;
        }

        .arm.right {
            right: -10px;
        }

        /* Animation de course des personnages */
        .character-container .character {
            animation: running 1s steps(3) infinite; /* Animation de course avec 3 frames */
        }

        @keyframes running {
            from {
                transform: translateX(0);
            }
            to {
                transform: translateX(100px); /* Ajuste la largeur en fonction du mouvement */
            }
        }

        /* Musique de fond */
        audio {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            z-index: -1;
        }

    </style>
</head>
<body>

    <!-- Musique de fond -->
    <audio autoplay loop>
        <source src="your-music-file.mp3" type="audio/mpeg">
        Votre navigateur ne supporte pas l'élément audio.
    </audio>

    <!-- Titre de la page -->
    <h1>Bienvenue dans la Bikouquête !</h1>

    <!-- Conteneur des personnages animés -->
    <div class="character-container">
        <!-- Personnage 1 -->
        <div class="character">
            <div class="head">
                <div class="eye left"></div>
                <div class="eye right"></div>
            </div>
            <div class="body"></div>
            <div class="arm left"></div>
            <div class="arm right"></div>
        </div>

        <!-- Personnage 2 -->
        <div class="character">
            <div class="head">
                <div class="eye left"></div>
                <div class="eye right"></div>
            </div>
            <div class="body"></div>
            <div class="arm left"></div>
            <div class="arm right"></div>
        </div>

        <!-- Personnage 3 -->
        <div class="character">
            <div class="head">
                <div class="eye left"></div>
                <div class="eye right"></div>
            </div>
            <div class="body"></div>
            <div class="arm left"></div>
            <div class="arm right"></div>
        </div>
    </div>

</body>
</html>
