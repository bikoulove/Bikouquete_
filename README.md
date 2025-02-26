<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Bikouquette - Suite</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #ff8eb5, #7f7fff);
            font-family: 'Poppins', sans-serif;
            text-align: center;
            color: white;
            overflow-x: hidden;
            height: 100vh;
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            animation: fadeIn 1s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        h1 {
            font-size: 4em;
            font-weight: bold;
            color: #fff;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
            animation: titleAnimation 3s ease-in-out infinite alternate;
            font-family: 'Bangers', cursive;
        }
        @keyframes titleAnimation {
            0% { color: #ff4da6; }
            50% { color: #7f7fff; }
            100% { color: #ff8eb5; }
        }
        .code-container {
            position: absolute;
            top: 30%;
            width: 100%;
            text-align: center;
            z-index: 1;
        }
        .code-container p {
            color: #fff;
            font-size: 1.2em;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>La Bikouquette - Suite</h1>
    <div class="code-container">
        <p>Votre nouveau code est : xxx</p>
    </div>
</body>
</html>
