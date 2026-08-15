<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Cobra Kai | Member Portal</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

:root {
    --red: #e50914;
    --dark-red: #8b0000;
    --black: #050505;
    --gray: #111;
    --light: #f5f5f5;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background:
        radial-gradient(circle at top, #250000 0%, #070707 40%, #000 100%);
    color: white;
    min-height: 100vh;
    overflow-x: hidden;
}

body::before {
    content: "";
    position: fixed;
    inset: 0;
    background:
        linear-gradient(rgba(255,255,255,.02) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.02) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
}

/* ================= HEADER ================= */

header {
    width: 100%;
    padding: 25px 7%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    z-index: 10;
}

.logo {
    font-size: 30px;
    font-weight: 900;
    letter-spacing: 4px;
    color: white;
}

.logo span {
    color: var(--red);
}

.header-btn {
    background: transparent;
    border: 1px solid #444;
    color: white;
    padding: 10px 18px;
    border-radius: 8px;
    cursor: pointer;
}

/* ================= MAIN ================= */

.container {
    width: min(1100px, 92%);
    margin: auto;
}

.hero {
    min-height: 88vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
}

.hero-content {
    max-width: 800px;
}

.hero h1 {
    font-size: clamp(55px, 11vw, 120px);
    font-weight: 1000;
    letter-spacing: 8px;
    text-transform: uppercase;
    line-height: .9;
    text-shadow:
        0 0 15px rgba(229,9,20,.5),
        0 10px 40px #000;
}

.hero h1 span {
    color: var(--red);
}

.hero p {
    margin-top: 30px;
    color: #aaa;
    font-size: 18px;
}

.buttons {
    display: flex;
    gap: 15px;
    justify-content: center;
    margin-top: 35px;
    flex-wrap: wrap;
}

.btn {
    border: none;
    padding: 15px 28px;
    border-radius: 8px;
    font-weight: 800;
    cursor: pointer;
    transition: .25s;
}

.btn-red {
    background: var(--red);
    color: white;
}

.btn-red:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 35px rgba(229,9,20,.4);
}

.btn-dark {
    background: #151515;
    border: 1px solid #333;
    color: white;
}

.btn-dark:hover {
    border-color: var(--red);
}

/* ================= CARDS ================= */

.card {
    background: rgba(15,15,15,.88);
    border: 1px solid #292929;
    border-radius: 18px;
    padding: 35px;
    box-shadow: 0 20px 60px rgba(0,0,0,.5);
    backdrop-filter: blur(12px);
}

.form-card {
    max-width: 520px;
    margin: 80px auto;
}

.card h2 {
    font-size: 32px;
    margin-bottom: 10px;
}

.subtitle {
    color: #888;
    margin-bottom: 30px;
}

.field {
    margin-bottom: 18px;
}

.field label {
    display: block;
    color: #bbb;
    margin-bottom: 8px;
    font-size: 14px;
}

.field input {
    width: 100%;
    padding: 15px;
    border-radius: 9px;
    border: 1px solid #333;
    background: #090909;
    color: white;
    outline: none;
}

.field input:focus {
    border-color: var(--red);
    box-shadow: 0 0 0 3px rgba(229,9,20,.12);
}

.full {
    width: 100%;
}

.switch {
    text-align: center;
    margin-top: 20px;
    color: #888;
}

.switch span {
    color: var(--red);
    cursor: pointer;
    font-weight: bold;
}

/* ================= DASHBOARD ================= */

.dashboard {
    padding: 50px 0 100px;
}

.dashboard-title {
    margin-bottom: 35px;
}

.dashboard-title h1 {
    font-size: 45px;
}

.dashboard-title p {
    color: #888;
    margin-top: 8px;
}

.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 25px;
}

/* ================= PROFILE ================= */

.profile-item {
    display: flex;
    justify-content: space-between;
    padding: 17px 0;
    border-bottom: 1px solid #292929;
}

.profile-item:last-child {
    border-bottom: none;
}

.profile-item span:first-child {
    color: #777;
}

.profile-item span:last-child {
    font-weight: bold;
}

/* ================= DIGITAL PASS ================= */

.pass {
    position: relative;
    overflow: hidden;
    background:
        linear-gradient(135deg, #170000, #080808 55%, #1d0000);
    border: 1px solid #5c1111;
}

.pass::after {
    content: "COBRA KAI";
    position: absolute;
    right: -20px;
    bottom: 20px;
    font-size: 60px;
    font-weight: 1000;
    color: rgba(255,255,255,.025);
    transform: rotate(-15deg);
}

.pass-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.pass-title {
    font-size: 25px;
    font-weight: 900;
    letter-spacing: 3px;
}

.status {
    background: #092b12;
    color: #53ff78;
    padding: 7px 12px;
    border-radius: 50px;
    font-size: 12px;
    font-weight: bold;
}

.pass-name {
    margin-top: 40px;
    font-size: 32px;
    font-weight: 900;
}

.member-id {
    margin-top: 8px;
    color: #888;
}

.pass-info {
    display: flex;
    gap: 35px;
    margin-top: 30px;
}

.pass-info div span {
    display: block;
    color: #777;
    font-size: 12px;
    margin-bottom: 5px;
}

.pass-info div strong {
    font-size: 18px;
}

.barcode {
    margin-top: 30px;
    height: 55px;
    background:
        repeating-linear-gradient(
            90deg,
            white 0px,
            white 2px,
            transparent 2px,
            transparent 5px,
            white 5px,
            white 7px,
            transparent 7px,
            transparent 11px
        );
    border-radius: 4px;
}

/* ================= FEATURES ================= */

.feature {
    padding: 25px 0;
}

.feature h3 {
    margin-bottom: 8px;
}

.feature p {
    color: #888;
    line-height: 1.5;
}

/* ================= HIDDEN ================= */

.hidden {
    display: none !important;
}

/* ================= RESPONSIVE ================= */

@media(max-width: 750px) {
    .grid {
        grid-template-columns: 1fr;
    }

    header {
        padding: 20px 5%;
    }

    .hero h1 {
        letter-spacing: 3px;
    }

    .card {
        padding: 25px;
    }

    .dashboard-title h1 {
        font-size: 34px;
    }
}
</style>
</head>

<body>

<header>
    <div class="logo">COBRA <span>KAI</span></div>
    <button id="logoutButton" class="header-btn hidden" onclick="logout()">
        Abmelden
    </button>
</header>

<!-- ================= STARTSEITE ================= -->

<section id="homePage" class="hero">
    <div class="hero-content">
        <h1>COBRA <span>KAI</span></h1>

        <p>
            ENTER THE DOJO. BUILD YOURSELF.
        </p>

        <div class="buttons">
            <button class="btn btn-red" onclick="showPage('registerPage')">
                Mitglied werden
            </button>

            <button class="btn btn-dark" onclick="showPage('loginPage')">
                Anmelden
            </button>
        </div>
    </div>
</section>

<!-- ================= REGISTRIERUNG ================= -->

<section id="registerPage" class="container hidden">

    <div class="card form-card">

        <h2>Mitglied werden</h2>
        <p class="subtitle">
            Erstelle dein persönliches Cobra-Kai-Profil.
        </p>

        <form onsubmit="register(event)">

            <div class="field">
                <label>Name</label>
                <input id="registerName" type="text" required placeholder="Dein Name">
            </div>

            <div class="field">
                <label>E-Mail-Adresse</label>
                <input id="registerEmail" type="email" required placeholder="name@email.de">
            </div>

            <div class="field">
                <label>Passwort</label>
                <input id="registerPassword" type="password" required minlength="6" placeholder="Mindestens 6 Zeichen">
            </div>

            <div class="field">
                <label>Größe (cm)</label>
                <input id="registerHeight" type="number" min="50" max="250" required placeholder="z. B. 175">
            </div>

            <div class="field">
                <label>Gewicht (kg)</label>
                <input id="registerWeight" type="number" min="20" max="300" step="0.1" required placeholder="z. B. 70">
            </div>

            <button class="btn btn-red full">
                REGISTRIEREN
            </button>

        </form>

        <div class="switch">
            Bereits Mitglied?
            <span onclick="showPage('loginPage')">Anmelden</span>
        </div>

    </div>

</section>

<!-- ================= LOGIN ================= -->

<section id="loginPage" class="container hidden">

    <div class="card form-card">

        <h2>Willkommen zurück</h2>
        <p class="subtitle">
            Melde dich bei deinem Dojo-Profil an.
        </p>

        <form onsubmit="login(event)">

            <div class="field">
                <label>E-Mail-Adresse</label>
                <input id="loginEmail" type="email" required>
            </div>

            <div class="field">
                <label>Passwort</label>
                <input id="loginPassword" type="password" required>
            </div>

            <button class="btn btn-red full">
                ANMELDEN
            </button>

        </form>

        <div class="switch">
            Noch kein Mitglied?
            <span onclick="showPage('registerPage')">Registrieren</span>
        </div>

    </div>

</section>

<!-- ================= DASHBOARD ================= -->

<section id="dashboardPage" class="container dashboard hidden">

    <div class="dashboard-title">
        <h1>Willkommen, <span id="dashboardName"></span></h1>
        <p>Dein persönlicher Cobra-Kai-Mitgliederbereich.</p>
    </div>

    <div class="grid">

        <!-- DIGITAL PASS -->

        <div class="card pass">

            <div class="pass-top">
                <div class="pass-title">
                    COBRA KAI
                </div>

                <div class="status">
                    AKTIV
                </div>
            </div>

            <div class="pass-name" id="passName"></div>

            <div class="member-id" id="memberId"></div>

            <div class="pass-info">

                <div>
                    <span>GRÖSSE</span>
                    <strong id="passHeight"></strong>
                </div>

                <div>
                    <span>GEWICHT</span>
                    <strong id="passWeight"></strong>
                </div>

            </div>

            <div class="pass-info">

                <div>
                    <span>GÜLTIG BIS</span>
                    <strong id="expiryDate"></strong>
                </div>

            </div>

            <div class="barcode"></div>

            <div class="buttons">
                <button class="btn btn-red full" onclick="walletInfo()">
                    🍎 Zu Apple Wallet hinzufügen
                </button>
            </div>

        </div>

        <!-- PROFIL -->

        <div class="card">

            <h2>Mein Profil</h2>
            <p class="subtitle">Deine gespeicherten Daten</p>

            <div class="profile-item">
                <span>Name</span>
                <span id="profileName"></span>
            </div>

            <div class="profile-item">
                <span>E-Mail</span>
                <span id="profileEmail"></span>
            </div>

            <div class="profile-item">
                <span>Größe</span>
                <span id="profileHeight"></span>
            </div>

            <div class="profile-item">
                <span>Gewicht</span>
                <span id="profileWeight"></span>
            </div>

            <div class="profile-item">
                <span>Mitgliedsnummer</span>
                <span id="profileId"></span>
            </div>

        </div>

        <!-- DOJO -->

        <div class="card">

            <h2>DOJO</h2>
            <p class="subtitle">Dein Mitgliederbereich</p>

            <div class="feature">
                <h3>🥋 Training</h3>
                <p>
                    Dein persönlicher Bereich für Training und Fortschritt.
                </p>
            </div>

            <div class="feature">
                <h3>🔥 Status</h3>
                <p>
                    Deine Mitgliedschaft ist momentan aktiv.
                </p>
            </div>

        </div>

        <!-- ZUGANG -->

        <div class="card">

            <h2>Zugang</h2>
            <p class="subtitle">
                Dein digitaler Mitgliedsausweis
            </p>

            <div class="feature">
                <h3>🎫 Digital Pass</h3>
                <p>
                    Zeige deinen digitalen Pass beim Eingang des Dojos.
                </p>
            </div>

            <div class="feature">
                <h3>⏳ 30 Tage</h3>
                <p>
                    Dein Login bleibt auf diesem Gerät für 30 Tage aktiv.
                </p>
            </div>

        </div>

    </div>

</section>

<script>

/* ==================================================
   COBRA KAI MEMBER SYSTEM
   ================================================== */

const STORAGE_KEY = "cobraKaiMember";
const SESSION_KEY = "cobraKaiSession";

/* ---------- PAGE SYSTEM ---------- */

function hideAllPages() {
    document.querySelectorAll("section").forEach(section => {
        section.classList.add("hidden");
    });
}

function showPage(pageId) {
    hideAllPages();

    document.getElementById(pageId).classList.remove("hidden");

    const logoutButton = document.getElementById("logoutButton");

    if (pageId === "dashboardPage") {
        logoutButton.classList.remove("hidden");
    } else {
        logoutButton.classList.add("hidden");
    }
}

/* ---------- HASH PASSWORD ---------- */

async function hashPassword(password) {

    const data = new TextEncoder().encode(password);

    const hash = await crypto.subtle.digest(
        "SHA-256",
        data
    );

    return Array.from(
        new Uint8Array(hash)
    )
    .map(b => b.toString(16).padStart(2, "0"))
    .join("");
}

/* ---------- REGISTER ---------- */

async function register(event) {

    event.preventDefault();

    const name =
        document.getElementById("registerName").value.trim();

    const email =
        document.getElementById("registerEmail").value.trim().toLowerCase();

    const password =
        document.getElementById("registerPassword").value;

    const height =
        document.getElementById("registerHeight").value;

    const weight =
        document.getElementById("registerWeight").value;

    const passwordHash =
        await hashPassword(password);

    const memberId =
        "CK-" +
        Math.random()
        .toString(36)
        .substring(2, 8)
        .toUpperCase();

    const createdAt = Date.now();

    const expiresAt =
        createdAt + (30 * 24 * 60 * 60 * 1000);

    const member = {

        name,
        email,
        passwordHash,
        height,
        weight,
        memberId,
        createdAt,
        expiresAt

    };

    localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify(member)
    );

    createSession(expiresAt);

    loadDashboard(member);
}

/* ---------- SESSION ---------- */

function createSession(expiresAt) {

    const session = {

        token:
            crypto.randomUUID(),

        expiresAt

    };

    localStorage.setItem(
        SESSION_KEY,
        JSON.stringify(session)
    );
}

/* ---------- LOGIN ---------- */

async function login(event) {

    event.preventDefault();

    const email =
        document.getElementById("loginEmail").value
        .trim()
        .toLowerCase();

    const password =
        document.getElementById("loginPassword").value;

    const saved =
        localStorage.getItem(STORAGE_KEY);

    if (!saved) {

        alert("Kein Konto gefunden. Bitte registriere dich zuerst.");

        return;
    }

    const member =
        JSON.parse(saved);

    const passwordHash =
        await hashPassword(password);

    if (
        member.email !== email ||
        member.passwordHash !== passwordHash
    ) {

        alert("E-Mail oder Passwort ist falsch.");

        return;
    }

    if (Date.now() > member.expiresAt) {

        localStorage.removeItem(STORAGE_KEY);
        localStorage.removeItem(SESSION_KEY);

        alert("Deine 30-Tage-Anmeldung ist abgelaufen.");

        showPage("loginPage");

        return;
    }

    createSession(member.expiresAt);

    loadDashboard(member);
}

/* ---------- CHECK SESSION ---------- */

function checkSession() {

    const memberData =
        localStorage.getItem(STORAGE_KEY);

    const sessionData =
        localStorage.getItem(SESSION_KEY);

    if (!memberData || !sessionData) {

        showPage("homePage");

        return;
    }

    const member =
        JSON.parse(memberData);

    const session =
        JSON.parse(sessionData);

    if (
        Date.now() > member.expiresAt ||
        Date.now() > session.expiresAt
    ) {

        localStorage.removeItem(STORAGE_KEY);
        localStorage.removeItem(SESSION_KEY);

        showPage("homePage");

        return;
    }

    loadDashboard(member);
}

/* ---------- DASHBOARD ---------- */

function loadDashboard(member) {

    document.getElementById("dashboardName")
        .textContent = member.name;

    document.getElementById("passName")
        .textContent = member.name;

    document.getElementById("memberId")
        .textContent = member.memberId;

    document.getElementById("passHeight")
        .textContent = member.height + " cm";

    document.getElementById("passWeight")
        .textContent = member.weight + " kg";

    document.getElementById("profileName")
        .textContent = member.name;

    document.getElementById("profileEmail")
        .textContent = member.email;

    document.getElementById("profileHeight")
        .textContent = member.height + " cm";

    document.getElementById("profileWeight")
        .textContent = member.weight + " kg";

    document.getElementById("profileId")
        .textContent = member.memberId;

    const date =
        new Date(member.expiresAt);

    document.getElementById("expiryDate")
        .textContent =
        date.toLocaleDateString("de-DE");

    showPage("dashboardPage");
}

/* ---------- LOGOUT ---------- */

function logout() {

    localStorage.removeItem(SESSION_KEY);

    showPage("homePage");
}

/* ---------- APPLE WALLET ---------- */

function walletInfo() {

    alert(
        "Der Apple-Wallet-Pass muss über einen Apple PassKit-Server erstellt werden. " +
        "Die Website ist bereits für diesen Button vorbereitet."
    );

}

/* ---------- START ---------- */

checkSession();

</script>

</body>
</html>
