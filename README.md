<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Shafarik:wght@700&display=swap" rel="stylesheet">
    <style>
        body {
            background-image: url('https://raw.githubusercontent.com/bikoulove/La-Bikouquete/refs/heads/main/maxresdefault.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            margin: 0;
            padding: 0;
            height: 100vh;
            font-family: 'Shafarik', sans-serif;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            text-align: center;
            overflow: hidden;
            position: relative;
            animation: fadeInPink 5s ease-in-out, heartbeat 2s infinite alternate;
        }
        @keyframes heartbeat {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }
        .title-container {
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
        .title-container h1 {
            font-size: 3rem;
            text-align: center;
            color: white;
            margin-bottom: 20px;
        }
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
        <p>Entre le code secret pour continuer :</p>
        <input type="text" id="codeInput" placeholder="Code secret...">
        <br>
        <button onclick="applyFadeEffect()">Valider</button>
        <p id="result"></p>
    </div>
    <script>
        function applyFadeEffect() {
            document.body.classList.add('fade-pink');
        }
    </script>
</body>
</html>
