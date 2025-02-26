<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquette</title>
    <style>
        body {
            background-color: #ff4da6;
            font-family: 'Press Start 2P', cursive;
            color: #fff;
            text-align: center;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }
        h1, p {
            font-family: 'Press Start 2P', cursive;
            font-size: 40px;
            text-transform: uppercase;
            color: #fff;
        }
        .container {
            position: relative;
            height: 100vh;
            background-color: #ff007f;
            overflow: hidden;
        }
        .character {
            position: absolute;
            bottom: 10%;
            animation: dance 1.5s infinite;
        }
      .blonde {
            left: 10%;
            width: 40px;
            height: 80px;
            background-color: #FFD700;
            border-radius: 5px;
            position: relative;
        }
        .blonde .head {
            width: 20px;
            height: 20px;
            background-color: #FFD700;
            border-radius: 50%;
            position: absolute;
            top: -20px;
            left: 10px;
        }
        .blonde .eyes {
            position: absolute;
            top: 5px;
            left: 5px;
            color: blue;
            font-size: 4px;
        }
        .blonde .body {
            width: 100%;
            height: 60px;
            background-color: #f5b300;
            position: absolute;
            bottom: 0;
            left: 0;
        }
        .blonde .legs {
            position: absolute;
            width: 100%;
            height: 20px;
            bottom: -20px;
            background-color: #964B00;
        }
        .blonde .arms {
            position: absolute;
            top: 15px;
            width: 100%;
            height: 20px;
            background-color: #f5b300;
        }
        .brunette {
            left: 50%;
            width: 40px;
            height: 80px;
            background-color: #6A4E23;
            border-radius: 5px;
            position: relative;
        }
        .brunette .head {
            width: 20px;
            height: 20px;
            background-color: #6A4E23;
            border-radius: 50%;
            position: absolute;
            top: -20px;
            left: 10px;
        }
        .brunette .eyes {
            position: absolute;
            top: 5px;
            left: 5px;
            color: blue;
            font-size: 4px;
        }
        .brunette .body {
            width: 100%;
            height: 60px;
            background-color: #f5b300;
            position: absolute;
            bottom: 0;
            left: 0;
        }
        .brunette .legs {
            position: absolute;
            width: 100%;
            height: 20px;
            bottom: -20px;
            background-color: #964B00;
        }
        .brunette .arms {
            position: absolute;
            top: 15px;
            width: 100%;
            height: 20px;
            background-color: #f5b300;
        }
        @keyframes dance {
            0%, 100% {
                transform: rotate(0deg);
            }
            25% {
                transform: rotate(5deg);
            }
            50% {
                transform: rotate(-5deg);
            }
            75% {
                transform: rotate(3deg);
            }
        }
        .code-container {
            background: rgba(0, 0, 0, 0.7);
            padding: 30px;
            border-radius: 15px;
            width: 60%;
            margin: 0 auto;
            color: #fff;
            font-size: 25px;
            text-align: center;
            margin-top: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
            background-color: #ff007f;
        }
        input {
            padding: 15px;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            text-align: center;
            width: 80%;
            margin-bottom: 20px;
        }
        button {
            margin-top: 15px;
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            background: #ff4da6;
            color: white;
            cursor: pointer;
            transition: 0.3s;
        }
        button:hover {
            background: #ff007f;
        }
        @keyframes fadeInBackground {
            0% {
                background-color: #ffffff;
            }
            100% {
                background-color: #ff4da6;
            }
        }
        .fade-in-background {
            animation: fadeInBackground 2s forwards;
        }
    </style>
</head>
<body class="fade-in-background">
    <div class="container">
        <h1>La Bikouquette</h1>
        <p>Rentre ton code secret pour avancer !</p>
        <div class="character blonde">
            <div class="head"></div>
            <div class="eyes">● ●</div>
            <div class="body"></div>
            <div class="arms"></div>
            <div class="legs"></div>
        </div>
        <div class="character brunette">
            <div class="head"></div>
            <div class="eyes">● ●</div>
            <div class="body"></div>
            <div class="arms"></div>
            <div class="legs"></div>
        </div>
        <div class="code-container">
            <p>Entre ton code secret !</p>
            <input type="text" id="codeInput" placeholder="Code ici">
            <br>
            <button onclick="checkCode()">Valider</button>
            <p id="result"></p>
        </div>
    </div>
    <script>
        function checkCode() {
            const code = document.getElementById('codeInput').value;
            const correctCode = "xxx";
            if (code === correctCode) {
                window.location.href = "page2.html"; // Redirection vers la page 2
            } else {
                document.getElementById('result').innerHTML = "Code incorrect, réessaie !";
            }
        }
    </script>
</body>
</html>
