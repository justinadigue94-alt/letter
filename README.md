<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Blue Confession 💙</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    font-family: 'Segoe UI', sans-serif;
    transition: 0.5s;
}

body.dark {
    background: #071525;
    color: #e0f2fe;
}

body.light {
    background: #eaf5ff;
    color: #23496b;
}

.container {
    width: 100%;
    max-width: 440px;
    padding: 30px 20px;
    text-align: center;
    border-radius: 25px;
    transition: 0.5s;
}

.dark .container {
    background: #10243b;
    box-shadow: 0 0 35px #38bdf833;
}

.light .container {
    background: #ffffff;
    box-shadow: 0 0 35px #60a5fa33;
}

h1 {
    margin: 20px 0 10px;
}

.subtitle {
    opacity: 0.7;
    font-size: 14px;
}

button {
    padding: 12px 20px;
    margin: 10px;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    transition: 0.3s;
}

.dark button {
    background: #60a5fa;
    color: #071525;
}

.light button {
    background: #93c5fd;
    color: #123456;
}

button:hover {
    transform: scale(1.05);
}

/* ENVELOPE */

.envelope-wrapper {
    width: 260px;
    height: 180px;
    margin: 100px auto 50px;
    position: relative;
    cursor: pointer;
    perspective: 1000px;
}

.envelope {
    width: 240px;
    height: 160px;
    position: absolute;
    left: 10px;
    bottom: 0;
    border-radius: 5px;
    background: #2563eb;
}

/* LETTER */

.letter {
    position: absolute;
    width: 220px;
    height: 140px;
    left: 10px;
    bottom: 5px;
    padding: 20px;
    overflow-y: auto;
    border-radius: 8px;
    background: #f8fcff;
    color: #23496b;
    z-index: 2;

    transition:
        transform 0.8s ease,
        height 0.8s ease;

    box-shadow: 0 5px 15px #0002;
}

.letter h2 {
    text-align: center;
    color: #2563eb;
    margin-bottom: 15px;
}

.letter p {
    line-height: 1.8;
    margin-bottom: 15px;
    font-size: 14px;
}

/* ENVELOPE FRONT */

.front {
    position: absolute;
    inset: 0;
    background: #1d4ed8;
    clip-path: polygon(
        0 0,
        50% 55%,
        100% 0,
        100% 100%,
        0 100%
    );
    z-index: 3;
}

/* ENVELOPE FLAP */

.flap {
    position: absolute;
    inset: 0;
    background: #60a5fa;
    clip-path: polygon(
        0 0,
        100% 0,
        50% 65%
    );
    transform-origin: top;
    transition: transform 0.7s ease;
    z-index: 4;
}

/* HEART SEAL */

.seal {
    position: absolute;
    top: 55px;
    left: 105px;
    font-size: 30px;
    z-index: 5;
    transition: 0.4s;
}

/* OPEN ANIMATION */

.envelope-wrapper.open .flap {
    transform: rotateX(180deg);
    z-index: 1;
}

.envelope-wrapper.open .seal {
    opacity: 0;
    transform: scale(0);
}

.envelope-wrapper.open .letter {
    height: 260px;
    transform: translateY(-150px);
    z-index: 6;
}

/* HINT */

.hint {
    font-size: 14px;
    opacity: 0.7;
    margin-top: 20px;
}

.footer {
    margin-top: 30px;
    font-size: 12px;
    opacity: 0.6;
}

</style>
</head>

<body class="dark">

<div class="container">

    <button id="modeBtn" onclick="toggleMode()">
        ☀️ Light Mood
    </button>

    <h1>A Little Confession 💙</h1>

    <p class="subtitle">
        There's a letter waiting for you...
    </p>

    <div class="envelope-wrapper" id="envelope"
         onclick="openEnvelope()">

        <div class="envelope">

            <div class="letter">

                <h2>Oming , 💙</h2>

                <p>
                    Hello meng i have been admiring you since nag start ako mag chat sa imo yes, san una lanags la pero eventually nag ka igwa ako feelings sa imo, I don't know why, pero you're so atractive to me sabi ko bawal d pwede and the way you smirk it gets mee
tf sana mag toud ka. HAHAHA
                I don't know how to say this properly,
                but I've been wanting to tell you something.
                </p>

                <p>
                Every time I see you, somehow my day becomes
                a little brighter. Your smile and your presence
                make ordinary moments feel special.
                </p>

                <p>
                I don't know if you feel the same way,
                and I don't want to pressure you.
                I just want to be honest about my feelings.
                </p>

                <p>
                <b>I think I have a crush on you. ♡</b>
                </p>

                <p>
                Whatever your response may be,
                I just want to say thank you for being
                someone who makes me smile. kaurogot pero d ko ma pigilan ini sabi sa imo. Love youu ugoton!
                </p>

                <p style="text-align:center">
                — Someone who secretly admires you HAHAHAH 💌
                </p>

            </div>

            <div class="front"></div>
            <div class="flap"></div>
            <div class="seal">💙</div>

        </div>

    </div>

    <p class="hint" id="hint">
        Click the envelope to open 💌
    </p>

    <button onclick="closeEnvelope()">
        Close Envelope
    </button>

    <div class="footer">
        Made with courage and a little love ♡
    </div>

</div>

<script>

function openEnvelope() {
    document.getElementById("envelope")
        .classList.add("open");

    document.getElementById("hint").innerText =
        "A little message just for you 💙";
}

function closeEnvelope() {
    document.getElementById("envelope")
        .classList.remove("open");

    document.getElementById("hint").innerText =
        "Click the envelope to open 💌";
}

function toggleMode() {
    document.body.classList.toggle("dark");
    document.body.classList.toggle("light");

    const isLight =
        document.body.classList.contains("light");

    document.getElementById("modeBtn").innerText =
        isLight ? "🌙 Dark Mood" : "☀️ Light Mood";
}

</script>

</body>
</html>
