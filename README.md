<title>Azii, Will You Be My Valentine????</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: 'new romans', sans-serif;
        background: linear-gradient(135deg, #ff5f8f, #ff9a9e);
        overflow: hidden;
        text-align: center;
        color: white;
    }

    .container {
        background: rgba(255, 255, 255, 0.15);
        padding: 50px;
        border-radius: 25px;
        backdrop-filter: blur(15px);
        box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        max-width: 600px;
    }

    h1 {
        font-size: 3rem;
        min-height: 60px;
    }

    .message {
        font-size: 2rem;
        margin: 20px 0;
        min-height: 90px;
    }

    .countdown {
        font-size: 1.5rem;
        margin-bottom: 25px;
        font-weight: bold;
    }

    button {
        padding: 20px 28px;
        font-size: 1.9rem;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        margin: 10px;
        transition: 0.3s;
        font-weight: bold;
    }

    .yes1 {
        background-color: white;
        color: #ff4e88;
    }

    .yes2 {
        background-color: #ff2e63;
        color: white;
    }

    button:hover {
        transform: scale(1.1);
    }

    #buttons {
        display: none;
    }

    #celebration {
        display: none;
        font-size: 3.4rem;
        margin-top: 25px;
        animation: pop 10.0s ease forwards;
    }

    .signature {
        margin-top: 30px;
        font-size: 1rem;
        opacity: 0.9;
    }

    @keyframes pop {
        0% { transform: scale(0); }
        100% { transform: scale(1); }
    }

    .hearts {
        position: fixed;
        bottom: -20px;
        font-size: 20px;
        animation: float 10s linear infinite;
        opacity: 0.8;
    }

    @keyframes float {
        0% { transform: translateY(0); }
        100% { transform: translateY(-110vh); }
    }
</style>
</head>

<body>

<div class="container">
    <h1 id="title"></h1>
    <div class="message" id="typedText"></div>

    <div class="countdown" id="countdown"></div>

    <div id="buttons">
        <button class="yes1" onclick="sayYes()">Yesssss!!!!</button>
        <button class="yes2" onclick="sayYes()">Yesssss!!</button>
    </div>

    <div id="celebration">
        U betta 🫵🏽🙂‍↕️🎉
    </div>

    <div class="signature">
        Forever and always🫶🏽,<br>
        Kev 
    </div>
</div>

<script>
const titleText = "Azii 💕";
const messageText = "To my chipolet bag and my beautiful tight pussy wife🙂‍↕️🙂‍↕️. 💖\n\nWill you be my Valentine?";

let i = 0;
let j = 0;

function typeTitle() {
    if (i < titleText.length) {
        document.getElementById("title").innerHTML += titleText.charAt(i);
        i++;
        setTimeout(typeTitle, 100);
    } else {
        typeMessage();
    }
}

function typeMessage() {
    if (j < messageText.length) {
        document.getElementById("typedText").innerHTML += messageText.charAt(j);
        j++;
        setTimeout(typeMessage, 40);
    } else {
        document.getElementById("buttons").style.display = "block";
    }
}

// Countdown to Feb 14
function updateCountdown() {
    const now = new Date();
    let year = now.getFullYear();
    let valentine = new Date(year, 1, 14); // Feb = month 1

    if (now > valentine) {
        valentine = new Date(year + 1, 1, 14);
    }

    const diff = valentine - now;

    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
    const minutes = Math.floor((diff / (1000 * 60)) % 60);
    const seconds = Math.floor((diff / 1000) % 60);

    document.getElementById("countdown").innerHTML =
        "Countdown to Valentine's Day 💘<br>" +
        days + "d " + hours + "h " + minutes + "m " + seconds + "s";
}

setInterval(updateCountdown, 1000);

// Celebration
function sayYes() {
    document.getElementById("celebration").style.display = "block";
    createHearts();
}

function createHearts() {
    for (let i = 0; i < 25; i++) {
        let heart = document.createElement("div");
        heart.className = "hearts";
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 5000);
    }
}

window.onload = function() {
    typeTitle();
    updateCountdown();
};
</script>

</body>
</html>
