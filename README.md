# Game1234.com<!DOCTYPE html>
<html lang="sk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Games1234.com</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #003366;
            color: white;
            padding: 10px;
            text-align: center;
            font-size: 30px;
        }
        .container {
            padding: 20px;
        }
        h2 {
            color: #003366;
        }
        .game-list {
            list-style-type: none;
            padding: 0;
        }
        .game-list li {
            padding: 10px;
            background-color: #e0e0e0;
            margin-bottom: 10px;
            border-radius: 5px;
        }
        footer {
            background-color: #003366;
            color: white;
            text-align: center;
            padding: 10px;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        .button {
            background-color: #ff0000;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .button:hover {
            background-color: #cc0000;
        }
    </style>
</head>
<body>

<header>
    Games1234.com
</header>

<div class="container">
    <h2>Top 10 hier</h2>
    <ul class="game-list">
        <li>1. Minecraft - PC, iOS, Android, konzoly</li>
        <li>2. Fortnite - PC, iOS, Android</li>
        <li>3. Roblox - PC, iOS, Android, Xbox</li>
        <li>4. Call of Duty: Warzone - PC, PS5, Xbox</li>
        <li>5. GTA V - PC, PS4/PS5, Xbox</li>
        <li>6. Brawl Stars - iOS, Android</li>
        <li>7. FIFA 24 - PC, PS5, Xbox</li>
        <li>8. Asphalt 9 - iOS, Android, PC</li>
        <li>9. Among Us - PC, iOS, Android, konzoly</li>
        <li>10. Clash Royale - iOS, Android</li>
    </ul>

    <h2>Nákup hier a konzol</h2>
    <p><a href="https://www.amazon.com" target="_blank">Kúp konzoly a hry na Amazon</a></p>
    <p><a href="https://www.alza.sk" target="_blank">Kúp konzoly a hry na Alza.sk</a></p>
    <p><a href="https://www.xbox.com" target="_blank">Xbox Cloud Gaming</a></p>
    <p><a href="https://www.nvidia.com/en-us/geforce-now/" target="_blank">Nvidia Cloud Gaming</a></p>
    <p><a href="https://www.microsoft.com" target="_blank">Xbox Store</a></p>
    <p><a href="https://www.apple.com/app-store/" target="_blank">App Store</a></p>
    <p><a href="https://play.google.com/store" target="_blank">Google Play Store</a></p>

    <h2>Prihlásenie</h2>
    <button class="button" onclick="signUp()">Zaregistrovať sa</button>
    <button class="button" onclick="signIn()">Prihlásiť sa</button>

    <div id="loginMessage"></div>

    <footer>
        <a href="https://www.canva.com/design/DAGl1sfyhWI/ppQMRrIkkzY1cRTj1S2CWA/view?utm_content=DAGl1sfyhWI&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=ha604754848" target="_blank">Canva Design</a>
    </footer>
</div>

<script src="https://www.gstatic.com/firebasejs/9.6.1/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.6.1/firebase-auth.js"></script>
<script>
    const firebaseConfig = {
        apiKey: "YOUR_API_KEY",
        authDomain: "YOUR_AUTH_DOMAIN",
        projectId: "YOUR_PROJECT_ID",
        storageBucket: "YOUR_STORAGE_BUCKET",
        messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
        appId: "YOUR_APP_ID"
    };
    const app = firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();

    function signUp() {
        const email = prompt("Zadaj svoj e-mail");
        const password = prompt("Zadaj svoje heslo");
        auth.createUserWithEmailAndPassword(email, password)
            .then((userCredential) => {
                document.getElementById("loginMessage").innerHTML = "Úspešne ste sa zaregistrovali!";
            })
            .catch((error) => {
                const errorMessage = error.message;
                document.getElementById("loginMessage").innerHTML = "Chyba: " + errorMessage;
            });
    }

    function signIn() {
        const email = prompt("Zadaj svoj e-mail");
        const password = prompt("Zadaj svoje heslo");
        auth.signInWithEmailAndPassword(email, password)
            .then((userCredential) => {
                document.getElementById("loginMessage").innerHTML = "Úspešne ste prihlásení!";
            })
            .catch((error) => {
                const errorMessage = error.message;
                document.getElementById("loginMessage").innerHTML = "Chyba: " + errorMessage;
            });
    }
</script>

</body>
</html>
