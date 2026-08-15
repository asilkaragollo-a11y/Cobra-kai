<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cobra Kai - Portal</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Arial Black', Gadget, sans-serif;
        }

        body {
            background-color: #000000;
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
        }

        .badge-header {
            border-bottom: 2px solid #ffcc00;
            padding-bottom: 15px;
            margin-bottom: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .logo {
            width: 140px;
            height: auto;
            margin-bottom: 10px;
            border-radius: 8px;
        }

        h1 {
            color: #ffcc00;
            font-size: 1.8rem;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        /* Tabs für Umschalten zwischen Registrieren und Anmelden */
        .tab-container {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 2px solid #333;
        }

        .tab-btn {
            flex: 1;
            padding: 12px;
            background: none;
            border: none;
            color: #888;
            font-size: 0.9rem;
            font-weight: bold;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s;
        }

        .tab-btn.active {
            color: #ffcc00;
            border-bottom: 3px solid #ffcc00;
            background-color: rgba(255, 204, 0, 0.05);
        }

        /* Hinweisboxen */
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

        .health-warning {
            background-color: rgba(255, 165, 0, 0.15);
            border: 1px solid #ffa500;
            color: #ffcc00;
            padding: 10px;
            border-radius: 6px;
            font-size: 0.8rem;
            margin-bottom: 20px;
            text-align: left;
            font-family: Arial, sans-serif;
            font-weight: bold;
        }

        .message-box {
            display: none;
            padding: 12px;
            border-radius: 6px;
            margin-bottom: 15px;
            font-size: 0.85rem;
            text-transform: uppercase;
        }

        .message-success {
            background-color: rgba(40, 167, 69, 0.2);
            border: 1px solid #28a745;
            color: #28a745;
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

        input {
            width: 100%;
            padding: 10px;
            background-color: #2b2b2b;
            border: 1px solid #444;
            border-radius: 6px;
            color: #fff;
            font-size: 0.95rem;
        }

        input:focus {
            outline: none;
            border-color: #ffcc00;
        }

        .submit-btn {
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
            margin-top: 10px;
        }

        .submit-btn:hover {
            background-color: #ff1a1a;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>

    <div class="pass-card">
        <div class="badge-header">
            <img class="logo" width="387" height="516" alt="Cobra Kai Logo" src="https://github.com/user-attachments/assets/7f080a3e-c052-4cf4-a299-ed6265007bad">
            <h1>Cobra Kai Studio</h1>
        </div>

        <!-- Navigation zwischen Registrierung & Anmelden -->
        <div class="tab-container">
            <button class="tab-btn active" id="tab-register" onclick="switchTab('register')">Registrieren</button>
            <button class="tab-btn" id="tab-login" onclick="switchTab('login')">Anmelden</button>
        </div>

        <!-- Benachrichtigung -->
        <div id="status-message" class="message-box"></div>

        <!-- Gesundheitshinweis -->
        <div class="health-warning">
            ⚠️ WICHTIGER HINWEIS: Bei offenen Wunden oder Verletzungen ist das Training strengstens untersagt!
        </div>

        <!-- REGISTRIERUNGSFORMULAR -->
        <form id="form-register" onsubmit="handleRegister(event)">
            <div class="notice-box">
                Zutrittspass ist nach der Registrierung 30 Tage lang gültig.
            </div>

            <div class="form-group">
                <label for="reg-name">Vollständiger Name</label>
                <input type="text" id="reg-name" placeholder="Vor- und Nachname" required>
            </div>

            <div class="form-group">
                <label for="reg-email">E-Mail-Adresse</label>
                <input type="email" id="reg-email" placeholder="deine@email.com" required>
            </div>

            <div class="form-row">
                <div class="form-group">
                    <label for="reg-height">Größe (cm)</label>
                    <input type="number" id="reg-height" placeholder="z. B. 175" min="100" max="250" required>
                </div>
                <div class="form-group">
                    <label for="reg-weight">Gewicht (kg)</label>
                    <input type="number" id="reg-weight" placeholder="z. B. 70" min="30" max="250" required>
                </div>
            </div>

            <div class="form-group">
                <label for="reg-pass">Passwort erstellen</label>
                <input type="password" id="reg-pass" placeholder="Passwort festlegen" required>
            </div>

            <button type="submit" class="submit-btn">Pass Anfordern & Registrieren</button>
        </form>

        <!-- ANMELDEFORMULAR -->
        <form id="form-login" class="hidden" onsubmit="handleLogin(event)">
            <div class="form-group">
                <label for="login-email">E-Mail-Adresse</label>
                <input type="email" id="login-email" placeholder="deine@email.com" required>
            </div>

            <div class="form-group">
                <label for="login-pass">Passwort</label>
                <input type="password" id="login-pass" placeholder="Dein Passwort" required>
            </div>

            <button type="submit" class="submit-btn">Einloggen</button>
        </form>
    </div>

    <script>
        // Tab-Umschaltung
        function switchTab(tab) {
            document.getElementById('form-register').classList.add('hidden');
            document.getElementById('form-login').classList.add('hidden');
            document.getElementById('tab-register').classList.remove('active');
            document.getElementById('tab-login').classList.remove('active');
            
            const msgBox = document.getElementById('status-message');
            msgBox.style.display = 'none';

            if (tab === 'register') {
                document.getElementById('form-register').classList.remove('hidden');
                document.getElementById('tab-register').classList.add('active');
            } else {
                document.getElementById('form-login').classList.remove('hidden');
                document.getElementById('tab-login').classList.add('active');
            }
        }

        // Registrierung verarbeiten
        function handleRegister(e) {
            e.preventDefault();
            const name = document.getElementById('reg-name').value;
            const email = document.getElementById('reg-email').value;
            const pass = document.getElementById('reg-pass').value;

            // In LocalStorage speichern
            const user = { name: name, email: email, pass: pass };
            localStorage.setItem('cobra_user_' + email, JSON.stringify(user));

            const msgBox = document.getElementById('status-message');
            msgBox.className = "message-box message-success";
            msgBox.innerText = "Registrierung erfolgreich! Du kannst dich jetzt anmelden.";
            msgBox.style.display = 'block';

            // Nach Registrierung auf Login umschalten und E-Mail vorausfüllen
            setTimeout(() => {
                switchTab('login');
                document.getElementById('login-email').value = email;
            }, 1500);
        }

        // Login verarbeiten
        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const pass = document.getElementById('login-pass').value;

            const storedUser = localStorage.getItem('cobra_user_' + email);

            if (storedUser) {
                const user = JSON.parse(storedUser);
                if (user.pass === pass) {
                    const msgBox = document.getElementById('status-message');
                    msgBox.className = "message-box message-success";
                    msgBox.innerText = "Anmeldung erfolgreich! Zutritt wird gewährt...";
                    msgBox.style.display = 'block';

                    setTimeout(() => {
                        window.location.href = `pass.html?fullname=${encodeURIComponent(user.name)}`;
                    }, 1200);
                    return;
                }
            }

            alert("E-Mail oder Passwort falsch!");
        }
    </script>

</body>
</html>
