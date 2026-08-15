<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cobra Kai - Mitgliedspass Registrierung</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Arial Black', Gadget, sans-serif;
        }

        body {
            background-color: #111;
            color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        .pass-card {
            background-color: #1a1a1a;
            border: 4px solid #ffcc00;
            border-radius: 12px;
            padding: 35px;
            max-width: 500px;
            width: 100%;
            box-shadow: 0 0 25px rgba(255, 204, 0, 0.4);
            text-align: center;
            position: relative;
        }

        .badge-header {
            border-bottom: 2px solid #ffcc00;
            padding-bottom: 20px;
            margin-bottom: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Pure CSS Cobra Kai Badge */
        .cobra-badge {
            background-color: #000;
            border: 4px solid #CB2027;
            width: 140px;
            height: 140px;
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-family: 'Impact', sans-serif;
            color: #DDA314;
            text-align: center;
            box-shadow: 0 0 15px rgba(203, 32, 39, 0.5);
            margin-bottom: 15px;
        }

        .cobra-text {
            font-size: 22px;
            font-style: italic;
            letter-spacing: 1px;
            line-height: 1.1;
            text-transform: uppercase;
        }

        .cobra-sub {
            font-size: 10px;
            color: #E9E567;
            letter-spacing: 2px;
            margin-top: 5px;
        }

        h1 {
            color: #ffcc00;
            font-size: 1.8rem;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        p.subtitle {
            color: #e60000;
            font-size: 0.85rem;
            font-weight: bold;
            letter-spacing: 1px;
            text-transform: uppercase;
            margin-top: 5px;
        }

        .notice-box {
            background-color: rgba(230, 0, 0, 0.15);
            border: 1px solid #e60000;
            color: #ff4d4d;
            padding: 10px;
            border-radius: 6px;
            font-size: 0.8rem;
            margin-bottom: 20px;
            text-transform: uppercase;
        }

        .form-row {
            display: flex;
            gap: 15px;
        }

        .form-group {
            margin-bottom: 15px;
            text-align: left;
            flex: 1;
        }

        label {
            display: block;
            margin-bottom: 6px;
            color: #ccc;
            font-size: 0.75rem;
            text-transform: uppercase;
        }

        input, select {
            width: 100%;
            padding: 10px;
            background-color: #2b2b2b;
            border: 1px solid #444;
            border-radius: 6px;
            color: #fff;
            font-size: 0.95rem;
        }

        input:focus, select:focus {
            outline: none;
            border-color: #ffcc00;
        }

        button {
            width: 100%;
            padding: 14px;
            background-color: #e60000;
            color: #fff;
            border: none;
            border-radius: 6px;
            font-size: 1rem;
            font-weight: bold;
            text-transform: uppercase;
            cursor: pointer;
            transition: background-color 0.2s ease;
            margin-top: 15px;
        }

        button:hover {
            background-color: #ff1a1a;
        }
    </style>
</head>
<body>

    <div class="pass-card">
        <div class="badge-header">
            <!-- Cobra Kai CSS Badge -->
            <div class="cobra-badge">
                <div class="cobra-text">Cobra Kai</div>
                <div class="cobra-sub">EST. 1984</div>
            </div>
            
            <h1>Cobra Kai Pass</h1>
            <p class="subtitle">Registrierung für Fitnessstudio-Zutritt</p>
        </div>

        <div class="notice-box">
            Achtung: Dieser Zutrittspass ist nach der Registrierung genau 30 Tage lang gültig.
        </div>

        <form>
            <div class="form-group">
                <label for="fullname">Vollständiger Name</label>
                <input type="text" id="fullname" placeholder="Vor- und Nachname" required>
            </div>

            <div class="form-group">
                <label for="email">E-Mail-Adresse</label>
                <input type="email" id="email" placeholder="deine@email.com" required>
            </div>

            <div class="form-row">
                <div class="form-group">
                    <label for="height">Größe (cm)</label>
                    <input type="number" id="height" placeholder="z. B. 175" min="100" max="250" required>
                </div>
                <div class="form-group">
                    <label for="weight">Gewicht (kg)</label>
                    <input type="number" id="weight" placeholder="z. B. 70" min="30" max="250" required>
                </div>
            </div>

            <div class="form-group">
                <label for="password">Neues Passwort erstellen</label>
                <input type="password" id="password" placeholder="Passwort festlegen" required>
            </div>

            <div class="form-group">
                <label for="password-confirm">Passwort bestätigen</label>
                <input type="password" id="password-confirm" placeholder="Passwort wiederholen" required>
            </div>

            <button type="submit">Pass Anfordern & Registrieren</button>
        </form>
    </div>

</body>
</html>
