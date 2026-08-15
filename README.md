# Cobra-kai
sekai taikei
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Cobra Kai – Sekai Taikai</title>

    <style>

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: Arial, sans-serif;

            min-height: 100vh;

            display: flex;
            justify-content: center;
            align-items: center;

            padding: 20px;

            background:
                radial-gradient(circle at center, #250000 0%, #080000 45%, #000000 100%);

            color: white;
        }

        /* Roter Glow im Hintergrund */

        body::before {
            content: "";
            position: fixed;

            width: 500px;
            height: 500px;

            background: rgba(190, 0, 0, 0.15);

            filter: blur(100px);

            border-radius: 50%;

            z-index: -1;
        }

        /* Hauptbox */

        .container {
            width: 100%;
            max-width: 470px;

            background: rgba(10, 10, 10, 0.96);

            border: 2px solid #c00000;

            border-radius: 18px;

            padding: 35px 28px;

            text-align: center;

            box-shadow:
                0 0 15px rgba(255, 0, 0, 0.5),
                0 0 50px rgba(180, 0, 0, 0.25);

            animation: erscheinen 0.8s ease;
        }

        @keyframes erscheinen {
            from {
                opacity: 0;
                transform: translateY(25px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Cobra Kai Logo */

        .logo {
            width: 220px;
            height: 220px;

            object-fit: contain;

            margin-bottom: 10px;

            filter:
                drop-shadow(0 0 10px rgba(255, 0, 0, 0.5));

            animation: logoGlow 2s infinite alternate;
        }

        @keyframes logoGlow {
            from {
                filter:
                    drop-shadow(0 0 5px rgba(255, 0, 0, 0.3));
            }

            to {
                filter:
                    drop-shadow(0 0 20px rgba(255, 0, 0, 0.8));
            }
        }

        /* Überschrift */

        h1 {
            font-size: 28px;

            font-weight: 900;

            text-transform: uppercase;

            letter-spacing: 1px;

            color: #e00000;

            text-shadow:
                0 0 10px rgba(255, 0, 0, 0.5);

            margin-bottom: 10px;
        }

        .subtitle {
            color: #aaa;

            font-size: 16px;

            margin-bottom: 28px;
        }

        /* Trennlinie */

        .linie {
            width: 80%;

            height: 2px;

            background: linear-gradient(
                to right,
                transparent,
                #d00000,
                transparent
            );

            margin: 20px auto 25px;
        }

        /* Eingabefelder */

        input {
            width: 100%;

            padding: 16px;

            margin-bottom: 14px;

            background: #181818;

            border: 1px solid #444;

            border-radius: 8px;

            color: white;

            font-size: 16px;

            transition: 0.2s;
        }

        input::placeholder {
            color: #777;
        }

        input:focus {
            outline: none;

            border-color: #e00000;

            box-shadow:
                0 0 10px rgba(220, 0, 0, 0.4);
        }

        /* Anmelden Button */

        button {
            width: 100%;

            padding: 16px;

            margin-top: 8px;

            background: linear-gradient(
                135deg,
                #8b0000,
                #e00000
            );

            color: white;

            border: none;

            border-radius: 8px;

            font-size: 18px;

            font-weight: 900;

            letter-spacing: 1px;

            cursor: pointer;

            transition: 0.2s;

            box-shadow:
                0 5px 15px rgba(200, 0, 0, 0.3);
        }

        button:hover {
            transform: scale(1.03);

            background: linear-gradient(
                135deg,
                #b00000,
                #ff0000
            );

            box-shadow:
                0 0 20px rgba(255, 0, 0, 0.6);
        }

        button:active {
            transform: scale(0.98);
        }

        /* Willkommensseite */

        #welcome {
            display: none;
        }

        .welcome-title {
            color: #e00000;

            font-size: 30px;

            font-weight: 900;

            margin-bottom: 15px;

            text-transform: uppercase;
        }

        .welcome-text {
            color: #ddd;

            font-size: 18px;

            line-height: 1.6;

            margin-bottom: 25px;
        }

        .name {
            color: white;

            font-size: 23px;

            font-weight: bold;
        }

        .cobra {
            font-size: 60px;

            margin: 20px 0;
        }

        /* Handy */

        @media (max-width: 500px) {

            .container {
                padding: 28px 20px;
            }

            .logo {
                width: 180px;
                height: 180px;
            }

            h1 {
                font-size: 23px;
            }

        }

    </style>
</head>

<body>

    <div class="container">

        <!-- DEIN COBRA KAI LOGO -->

        <img
            width="447"
            height="447"
            alt="Cobra Kai Logo"
            src="https://github.com/user-attachments/assets/a2ee4797-7302-4c97-8aff-139559e06132"
            class="logo"
        >

        <!-- ANMELDUNG -->

        <div id="login">

            <h1>
                Anmeldung für das Sekai Taikai
            </h1>

            <div class="linie"></div>

            <p class="subtitle">
                Melde dich für das größte Karate-Turnier der Welt an.
            </p>

            <input
                type="text"
                id="firstName"
                placeholder="Vorname"
            >

            <input
                type="text"
                id="lastName"
                placeholder="Nachname"
            >

            <button onclick="login()">
                🥋 ANMELDEN
            </button>

        </div>


        <!-- WILLKOMMEN -->

        <div id="welcome">

            <div class="welcome-title">
                Anmeldung erfolgreich!
            </div>

            <div class="welcome-text">

                Willkommen beim
                <strong>Sekai Taikai</strong>!

                <br><br>

                Teilnehmer:

                <div class="name" id="welcomeName"></div>

            </div>

            <div class="cobra">
                🐍
            </div>

            <button onclick="logout()">
                ABMELDEN
            </button>

        </div>

    </div>


    <script>

        function login() {

            let firstName =
                document.getElementById("firstName").value.trim();

            let lastName =
                document.getElementById("lastName").value.trim();


            if (firstName === "" || lastName === "") {

                alert(
                    "Bitte gib deinen Vor- und Nachnamen ein!"
                );

                return;
            }


            document.getElementById("welcomeName").innerHTML =
                firstName + " " + lastName;


            document.getElementById("login").style.display =
                "none";

            document.getElementById("welcome").style.display =
                "block";
        }


        function logout() {

            document.getElementById("login").style.display =
                "block";

            document.getElementById("welcome").style.display =
                "none";


            document.getElementById("firstName").value = "";

            document.getElementById("lastName").value = "";
        }

    </script>

</body>
</html>
