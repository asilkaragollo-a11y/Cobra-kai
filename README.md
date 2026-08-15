
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>COBRA KAI | DOJO</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Anton&family=Inter:wght@400;500;600;700;800;900&display=swap');

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

:root {
    --red: #e50914;
    --bright-red: #ff2733;
    --dark-red: #680006;
    --black: #030303;
    --card: rgba(15,15,17,.82);
    --line: rgba(255,255,255,.09);
    --gray: #858585;
}

body {
    min-height: 100vh;
    background:
        radial-gradient(circle at 50% -10%, #480005 0%, #160001 22%, #050505 55%, #000 100%);
    color: white;
    font-family: Inter, Arial, sans-serif;
    overflow-x: hidden;
}

/* Hintergrund */

body::before {
    content: "";
    position: fixed;
    inset: 0;
    pointer-events: none;
    opacity: .35;

    background-image:
        linear-gradient(rgba(255,255,255,.018) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.018) 1px, transparent 1px);

    background-size: 45px 45px;
}

body::after {
    content: "";
    position: fixed;
    width: 500px;
    height: 500px;
    background: rgba(229,9,20,.08);
    filter: blur(120px);
    border-radius: 50%;
    top: 15%;
    left: -200px;
    pointer-events: none;
}

/* HEADER */

header {
    position: sticky;
    top: 0;
    z-index: 100;

    height: 76px;
    padding: 0 6%;

    display: flex;
    align-items: center;
    justify-content: space-between;

    background: rgba(2,2,2,.72);
    backdrop-filter: blur(22px);

    border-bottom: 1px solid var(--line);
}

.logo {
    font-family: Anton, sans-serif;
    font-size: 28px;
    letter-spacing: 3px;
}

.logo span {
    color: var(--red);
}

.nav-right {
    display: flex;
    align-items: center;
    gap: 12px;
}

.member-mini {
    display: none;
    padding: 8px 13px;
    border: 1px solid #292929;
    border-radius: 50px;
    color: #aaa;
    font-size: 12px;
}

.logout {
    display: none;
    border: 1px solid #333;
    background: #101010;
    color: white;
    border-radius: 8px;
    padding: 10px 16px;
    cursor: pointer;
}

/* PAGES */

.page {
    min-height: calc(100vh - 76px);
}

.hidden {
    display: none !important;
}

/* HERO */

.hero {
    min-height: calc(100vh - 76px);
    display: flex;
    align-items: center;
    justify-content: center;

    text-align: center;
    padding: 40px 20px;

    position: relative;
}

.hero-content {
    max-width: 950px;
    position: relative;
    z-index: 2;
}

.kicker {
    color: #999;
    font-size: 12px;
    font-weight: 800;
    letter-spacing: 8px;
    margin-bottom: 25px;

    animation: fadeUp .8s ease;
}

.hero-title {
    font-family: Anton, sans-serif;
    font-size: clamp(70px, 14vw, 155px);
    line-height: .82;
    letter-spacing: 5px;

    animation: titleIn 1s ease;

    text-shadow:
        0 0 40px rgba(229,9,20,.20),
        0 25px 70px #000;
}

.hero-title span {
    color: var(--red);
}

.hero-sub {
    margin-top: 30px;
    color: #888;
    letter-spacing: 3px;
    font-size: 15px;
}

.hero-line {
    width: 100px;
    height: 3px;
    background: var(--red);
    margin: 25px auto;
    box-shadow: 0 0 20px var(--red);
}

.buttons {
    display: flex;
    justify-content: center;
    gap: 14px;
    flex-wrap: wrap;
    margin-top: 35px;
}

.btn {
    border: none;
    padding: 15px 27px;
    border-radius: 9px;
    cursor: pointer;

    font-weight: 900;
    letter-spacing: .5px;

    transition: .25s;
}

.btn:hover {
    transform: translateY(-3px);
}

.btn-red {
    color: white;

    background:
        linear-gradient(135deg, #ff1d29, #a50008);

    box-shadow:
        0 12px 35px rgba(229,9,20,.28);
}

.btn-red:hover {
    box-shadow:
        0 16px 45px rgba(229,9,20,.45);
}

.btn-dark {
    color: white;
    background: #111;
    border: 1px solid #303030;
}

/* FORM */

.center {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 60px 20px;
}

.form-card {
    width: 100%;
    max-width: 500px;
}

.card {
    position: relative;

    background:
        linear-gradient(
            145deg,
            rgba(25,25,27,.94),
            rgba(8,8,9,.94)
        );

    border: 1px solid var(--line);
    border-radius: 22px;

    padding: 32px;

    box-shadow:
        0 30px 100px rgba(0,0,0,.55);

    backdrop-filter: blur(20px);
}

.card::before {
    content: "";
    position: absolute;
    top: 0;
    left: 25px;
    right: 25px;
    height: 1px;

    background:
        linear-gradient(
            90deg,
            transparent,
            rgba(229,9,20,.7),
            transparent
        );
}

.card h2 {
    font-size: 30px;
    font-weight: 900;
}

.subtitle {
    color: #777;
    margin-top: 8px;
    margin-bottom: 28px;
}

.field {
    margin-bottom: 17px;
}

.field label {
    display: block;
    margin-bottom: 8px;

    color: #999;
    font-size: 11px;
    font-weight: 800;
    letter-spacing: 1.5px;
}

.field input {
    width: 100%;

    padding: 15px 16px;

    background: #050505;
    border: 1px solid #292929;
    border-radius: 9px;

    color: white;
    outline: none;

    transition: .2s;
}

.field input:focus {
    border-color: var(--red);
    box-shadow: 0 0 0 3px rgba(229,9,20,.1);
}

.full {
    width: 100%;
}

.switch {
    text-align: center;
    color: #666;
    margin-top: 22px;
    font-size: 14px;
}

.switch span {
    color: var(--red);
    cursor: pointer;
    font-weight: 800;
}

/* DASHBOARD */

.dashboard {
    max-width: 1250px;
    margin: auto;
    padding: 60px 20px 100px;
}

.dashboard-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    gap: 20px;
    margin-bottom: 35px;
}

.dashboard-top small {
    color: var(--red);
    letter-spacing: 4px;
    font-size: 11px;
    font-weight: 900;
}

.dashboard-top h1 {
    font-size: clamp(38px, 6vw, 65px);
    margin-top: 7px;
    letter-spacing: -2px;
}

.dashboard-top p {
    color: #777;
    margin-top: 10px;
}

.status-big {
    display: flex;
    align-items: center;
    gap: 8px;

    background: rgba(0,200,60,.07);
    border: 1px solid rgba(0,255,80,.15);

    color: #54ff7b;

    padding: 11px 16px;
    border-radius: 50px;

    font-size: 12px;
    font-weight: 800;
}

.green-dot {
    width: 7px;
    height: 7px;
    background: #45ff70;
    border-radius: 50%;
    box-shadow: 0 0 12px #45ff70;
}

/* GRID */

.grid {
    display: grid;
    grid-template-columns: 1.15fr .85fr;
    gap: 22px;
}

/* DIGITAL PASS */

.digital-pass {
    overflow: hidden;

    background:
        radial-gradient(
            circle at 90% 0%,
            rgba(229,9,20,.28),
            transparent 35%
        ),
        linear-gradient(
            145deg,
            #1a0002,
            #0a0808 60%,
            #030303
        );

    min-height: 500px;
}

.digital-pass::after {
    content: "KAI";

    position: absolute;
    right: -15px;
    bottom: -35px;

    font-family: Anton, sans-serif;
    font-size: 180px;

    color: rgba(255,255,255,.025);

    transform: rotate(-12deg);
    pointer-events: none;
}

.pass-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.pass-brand {
    font-family: Anton, sans-serif;
    font-size: 28px;
    letter-spacing: 3px;
}

.pass-brand span {
    color: var(--red);
}

.active {
    padding: 7px 12px;

    border-radius: 50px;

    background: rgba(0,180,60,.09);
    border: 1px solid rgba(0,255,80,.17);

    color: #55ff7c;

    font-size: 10px;
    font-weight: 900;
}

.pass-member {
    margin-top: 55px;
}

.pass-member small {
    color: #666;
    font-size: 10px;
    letter-spacing: 2px;
}

.pass-member h2 {
    font-family: Anton, sans-serif;
    font-size: 43px;
    letter-spacing: 1px;
    margin-top: 5px;
}

.pass-id {
    color: #777;
    font-family: monospace;
    margin-top: 5px;
}

.pass-stats {
    display: flex;
    gap: 55px;
    margin-top: 35px;
}

.stat span {
    display: block;
    color: #555;
    font-size: 10px;
    letter-spacing: 2px;
    margin-bottom: 6px;
}

.stat strong {
    font-size: 20px;
}

/* QR */

.qr-section {
    position: relative;
    z-index: 2;

    display: flex;
    align-items: center;
    gap: 22px;

    margin-top: 35px;
}

.qr-box {
    width: 135px;
    height: 135px;

    padding: 9px;

    background: white;
    border-radius: 12px;

    box-shadow:
        0 10px 35px rgba(0,0,0,.5);
}

.qr-box img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}

.qr-info {
    max-width: 240px;
    color: #777;
    font-size: 12px;
    line-height: 1.6;
}

.qr-info strong {
    color: white;
}

/* PROFILE */

.profile-card h3 {
    margin-top: 5px;
    color: #777;
    font-size: 12px;
    letter-spacing: 2px;
}

.profile-row {
    display: flex;
    justify-content: space-between;
    align-items: center;

    padding: 17px 0;

    border-bottom: 1px solid #222;
}

.profile-row:last-child {
    border-bottom: none;
}

.profile-row span:first-child {
    color: #666;
}

.profile-row span:last-child {
    font-weight: 800;
}

/* INFO CARDS */

.info-card {
    min-height: 220px;
}

.info-icon {
    width: 48px;
    height: 48px;

    display: flex;
    align-items: center;
    justify-content: center;

    border-radius: 13px;

    background: rgba(229,9,20,.10);
    border: 1px solid rgba(229,9,20,.18);

    font-size: 22px;

    margin-bottom: 20px;
}

.info-card h2 {
    font-size: 22px;
}

.info-card p {
    color: #777;
    line-height: 1.7;
    margin-top: 10px;
}

/* ANIMATION */

@keyframes fadeUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes titleIn {
    from {
        opacity: 0;
        transform: scale(.92);
    }

    to {
        opacity: 1;
        transform: scale(1);
    }
}

/* MOBILE */

@media(max-width: 800px) {

    header {
        padding: 0 20px;
    }

    .member-mini {
        display: none !important;
    }

    .grid {
        grid-template-columns: 1fr;
    }

    .dashboard-top {
        align-items: flex-start;
        flex-direction: column;
    }

    .card {
        padding: 25px;
    }

    .pass-stats {
        gap: 30px;
    }

    .hero-title {
        letter-spacing: 2px;
    }
}

@media(max-width: 450px) {

    .logo {
        font-size: 22px;
    }

    .pass-member h2 {
        font-size: 35px;
    }

    .qr-box {
        width: 110px;
        height: 110px;
    }

    .qr-section {
        gap: 14px;
    }
}
</style>
</head>


<body>

<header>

    <div class="logo">
        COBRA <span>KAI</span>
    </div>

    <div class="nav-right">

        <div
            id="memberMini"
            class="member-mini">
        </div>

        <button
            id="logoutButton"
            class="logout"
            onclick="logout()">
            Abmelden
        </button>

    </div>

</header>


<!-- ================= STARTSEITE ================= -->

<section id="homePage" class="page hero">

    <div class="hero-content">

        <div class="kicker">
            ENTER THE DOJO
        </div>

        <h1 class="hero-title">
            COBRA <span>KAI</span>
        </h1>

        <div class="hero-line"></div>

        <p class="hero-sub">
            STRIKE FIRST. STRIKE HARD. NO MERCY.
        </p>

        <div class="buttons">

            <button
                class="btn btn-red"
                onclick="showPage('registerPage')">
                MITGLIED WERDEN
            </button>

            <button
                class="btn btn-dark"
                onclick="showPage('loginPage')">
                ANMELDEN
            </button>

        </div>

    </div>

</section>


<!-- ================= REGISTER ================= -->

<section id="registerPage" class="page center hidden">

    <div class="card form-card">

        <h2>Neues Mitglied</h2>

        <p class="subtitle">
            Erstelle deinen persönlichen Dojo-Account.
        </p>

        <form onsubmit="register(event)">

            <div class="field">
                <label>VOLLSTÄNDIGER NAME</label>

                <input
                    id="registerName"
                    type="text"
                    required
                    placeholder="Dein Name">
            </div>

            <div class="field">
                <label>E-MAIL-ADRESSE</label>

                <input
                    id="registerEmail"
                    type="email"
                    required
                    placeholder="name@email.de">
            </div>

            <div class="field">
                <label>PASSWORT</label>

                <input
                    id="registerPassword"
                    type="password"
                    required
                    minlength="6"
                    placeholder="Mindestens 6 Zeichen">
            </div>

            <div class="field">
                <label>GRÖSSE</label>

                <input
                    id="registerHeight"
                    type="number"
                    required
                    min="50"
                    max="250"
                    placeholder="z. B. 175 cm">
            </div>

            <div class="field">
                <label>GEWICHT</label>

                <input
                    id="registerWeight"
                    type="number"
                    required
                    min="20"
                    max="300"
                    step="0.1"
                    placeholder="z. B. 70 kg">
            </div>

            <button class="btn btn-red full">
                ACCOUNT ERSTELLEN
            </button>

        </form>

        <div class="switch">
            Bereits Mitglied?

            <span onclick="showPage('loginPage')">
                Anmelden
            </span>
        </div>

    </div>

</section>


<!-- ================= LOGIN ================= -->

<section id="loginPage" class="page center hidden">

    <div class="card form-card">

        <h2>Willkommen zurück</h2>

        <p class="subtitle">
            Betritt wieder dein Dojo.
        </p>

        <form onsubmit="login(event)">

            <div class="field">

                <label>E-MAIL-ADRESSE</label>

                <input
                    id="loginEmail"
                    type="email"
                    required>

            </div>

            <div class="field">

                <label>PASSWORT</label>

                <input
                    id="loginPassword"
                    type="password"
                    required>

            </div>

            <button class="btn btn-red full">
                ANMELDEN
            </button>

        </form>

        <div class="switch">

            Noch kein Account?

            <span onclick="showPage('registerPage')">
                Registrieren
            </span>

        </div>

    </div>

</section>


<!-- ================= DASHBOARD ================= -->

<section id="dashboardPage" class="page hidden">

    <div class="dashboard">

        <div class="dashboard-top">

            <div>

                <small>COBRA KAI • MEMBER AREA</small>

                <h1>
                    Willkommen,
                    <span id="dashboardName"></span>
                </h1>

                <p>
                    Dein persönlicher Dojo-Bereich.
                </p>

            </div>

            <div class="status-big">

                <span class="green-dot"></span>

                MITGLIED AKTIV

            </div>

        </div>


        <div class="grid">


            <!-- DIGITALER PASS -->

            <div class="card digital-pass">

                <div class="pass-top">

                    <div class="pass-brand">
                        COBRA <span>KAI</span>
                    </div>

                    <div class="active">
                        ● AKTIV
                    </div>

                </div>


                <div class="pass-member">

                    <small>
                        MEMBER
                    </small>

                    <h2 id="passName">
                    </h2>

                    <div
                        id="passId"
                        class="pass-id">
                    </div>

                </div>


                <div class="pass-stats">

                    <div class="stat">

                        <span>GRÖSSE</span>

                        <strong id="passHeight">
                        </strong>

                    </div>


                    <div class="stat">

                        <span>GEWICHT</span>

                        <strong id="passWeight">
                        </strong>

                    </div>

                </div>


                <div class="qr-section">

                    <div class="qr-box">

                        <img
                            id="qrCode"
                            alt="Mitglieder QR-Code">

                    </div>


                    <div class="qr-info">

                        <strong>
                            DIGITAL MEMBER ID
                        </strong>

                        <br><br>

                        Dieser Code gehört
                        zu deinem persönlichen
                        Cobra-Kai-Mitgliedsprofil.

                        <br><br>

                        <strong id="qrMemberId">
                        </strong>

                    </div>

                </div>

            </div>


            <!-- PROFIL -->

            <div class="card profile-card">

                <h2>Mein Profil</h2>

                <h3>
                    PERSONAL INFORMATION
                </h3>


                <div style="margin-top:25px">

                    <div class="profile-row">

                        <span>Name</span>

                        <span id="profileName">
                        </span>

                    </div>


                    <div class="profile-row">

                        <span>E-Mail</span>

                        <span id="profileEmail">
                        </span>

                    </div>


                    <div class="profile-row">

                        <span>Größe</span>

                        <span id="profileHeight">
                        </span>

                    </div>


                    <div class="profile-row">

                        <span>Gewicht</span>

                        <span id="profileWeight">
                        </span>

                    </div>


                    <div class="profile-row">

                        <span>Member ID</span>

                        <span id="profileId">
                        </span>

                    </div>

                </div>

            </div>


            <!-- DOJO -->

            <div class="card info-card">

                <div class="info-icon">
                    🥋
                </div>

                <h2>
                    Dein Dojo
                </h2>

                <p>
                    Dein persönlicher Cobra-Kai-
                    Mitgliederbereich. Hier kannst
                    du später Training, Fortschritte
                    und Termine verwalten.
                </p>

            </div>


            <!-- STATUS -->

            <div class="card info-card">

                <div class="info-icon">
                    🔥
                </div>

                <h2>
                    Mitgliedschaft
                </h2>

                <p>
                    Dein digitaler Mitgliedsausweis
                    ist dauerhaft auf dieser Website
                    verfügbar.
                </p>

                <div style="
                    margin-top:20px;
                    color:#54ff7b;
                    font-weight:800;
                    font-size:13px;
                ">
                    ● STATUS: AKTIV
                </div>

            </div>

        </div>

    </div>

</section>


<script>

/* ==========================================================
   COBRA KAI MEMBER SYSTEM
   ========================================================== */

const MEMBER_KEY =
    "cobraKaiMember_v3";

const SESSION_KEY =
    "cobraKaiSession_v3";


/* ================= SEITEN ================= */

function showPage(id) {

    document
        .querySelectorAll(".page")
        .forEach(page => {
            page.classList.add("hidden");
        });

    document
        .getElementById(id)
        .classList.remove("hidden");

    const logout =
        document.getElementById("logoutButton");

    const mini =
        document.getElementById("memberMini");


    if (id === "dashboardPage") {

        logout.style.display = "block";
        mini.style.display = "block";

    } else {

        logout.style.display = "none";
        mini.style.display = "none";

    }

}


/* ================= PASSWORT HASH ================= */

async function hashPassword(password) {

    const data =
        new TextEncoder()
        .encode(password);

    const hash =
        await crypto.subtle.digest(
            "SHA-256",
            data
        );

    return Array
        .from(new Uint8Array(hash))
        .map(
            b =>
            b.toString(16)
            .padStart(2, "0")
        )
        .join("");
}


/* ================= MEMBER ID ================= */

function createMemberId() {

    const chars =
        "ABCDEFGHJKLMNPQRSTUVWXYZ23456789";

    let id = "";

    for (let i = 0; i < 6; i++) {

        id += chars[
            Math.floor(
                Math.random() *
                chars.length
            )
        ];

    }

    return "CK-" + id;
}


/* ================= QR CODE ================= */

function createQR(memberId) {

    return (
        "https://api.qrserver.com/v1/create-qr-code/" +
        "?size=300x300&margin=10&data=" +
        encodeURIComponent(memberId)
    );

}


/* ================= REGISTER ================= */

async function register(event) {

    event.preventDefault();


    const name =
        document
        .getElementById("registerName")
        .value
        .trim();


    const email =
        document
        .getElementById("registerEmail")
        .value
        .trim()
        .toLowerCase();


    const password =
        document
        .getElementById("registerPassword")
        .value;


    const height =
        document
        .getElementById("registerHeight")
        .value;


    const weight =
        document
        .getElementById("registerWeight")
        .value;


    const existing =
        localStorage.getItem(
            MEMBER_KEY
        );


    if (existing) {

        const old =
            JSON.parse(existing);

        if (old.email === email) {

            alert(
                "Für diese E-Mail existiert bereits ein Account."
            );

            return;
        }
    }


    const passwordHash =
        await hashPassword(password);


    const member = {

        name,
        email,
        passwordHash,
        height,
        weight,

        memberId:
            createMemberId(),

        createdAt:
            Date.now()

    };


    localStorage.setItem(
        MEMBER_KEY,
        JSON.stringify(member)
    );


    createSession();


    loadDashboard(member);

}


/* ================= SESSION ================= */

function createSession() {

    const session = {

        createdAt:
            Date.now(),

        expiresAt:
            Date.now() +
            (30 *
             24 *
             60 *
             60 *
             1000)

    };


    localStorage.setItem(
        SESSION_KEY,
        JSON.stringify(session)
    );

}


/* ================= LOGIN ================= */

async function login(event) {

    event.preventDefault();


    const email =
        document
        .getElementById("loginEmail")
        .value
        .trim()
        .toLowerCase();


    const password =
        document
        .getElementById("loginPassword")
        .value;


    const saved =
        localStorage.getItem(
            MEMBER_KEY
        );


    if (!saved) {

        alert(
            "Kein Account gefunden."
        );

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

        alert(
            "E-Mail oder Passwort ist falsch."
        );

        return;
    }


    const sessionData =
        localStorage.getItem(
            SESSION_KEY
        );


    if (!sessionData) {

        createSession();

        loadDashboard(member);

        return;
    }


    const session =
        JSON.parse(sessionData);


    if (
        Date.now() >
        session.expiresAt
    ) {

        localStorage.removeItem(
            SESSION_KEY
        );

        alert(
            "Deine 30-Tage-Anmeldung ist abgelaufen."
        );

        return;
    }


    loadDashboard(member);

}


/* ================= DASHBOARD ================= */

function loadDashboard(member) {

    document
        .getElementById("dashboardName")
        .textContent =
        member.name;


    document
        .getElementById("passName")
        .textContent =
        member.name;


    document
        .getElementById("passId")
        .textContent =
        member.memberId;


    document
        .getElementById("qrMemberId")
        .textContent =
        member.memberId;


    document
        .getElementById("passHeight")
        .textContent =
        member.height +
        " cm";


    document
        .getElementById("passWeight")
        .textContent =
        member.weight +
        " kg";


    document
        .getElementById("profileName")
        .textContent =
        member.name;


    document
        .getElementById("profileEmail")
        .textContent =
        member.email;


    document
        .getElementById("profileHeight")
        .textContent =
        member.height +
        " cm";


    document
        .getElementById("profileWeight")
        .textContent =
        member.weight +
        " kg";


    document
        .getElementById("profileId")
        .textContent =
        member.memberId;


    document
        .getElementById("memberMini")
        .textContent =
        member.memberId;


    document
        .getElementById("qrCode")
        .src =
        createQR(
            member.memberId
        );


    showPage(
        "dashboardPage"
    );

}


/* ================= LOGOUT ================= */

function logout() {

    /*
       Der Account bleibt gespeichert.
       Nur die 30-Tage-Session wird gelöscht.
    */

    localStorage.removeItem(
        SESSION_KEY
    );

    showPage("homePage");

}


/* ================= AUTO LOGIN ================= */

function checkSession() {

    const memberData =
        localStorage.getItem(
            MEMBER_KEY
        );


    const sessionData =
        localStorage.getItem(
            SESSION_KEY
        );


    if (
        !memberData ||
        !sessionData
    ) {

        showPage("homePage");

        return;
    }


    const member =
        JSON.parse(memberData);


    const session =
        JSON.parse(sessionData);


    if (
        Date.now() >
        session.expiresAt
    ) {

        localStorage.removeItem(
            SESSION_KEY
        );

        showPage("homePage");

        return;
    }


    loadDashboard(member);

}


/* ================= START ================= */

checkSession();

</script>

</body>
</html>
