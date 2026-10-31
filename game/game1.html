<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

<title>METEOR DODGE</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #080b18;
    overflow: hidden;
    font-family: Arial, sans-serif;
    color: white;
    touch-action: none;
}

canvas {
    display: block;
    width: 100vw;
    height: 100dvh;
}

#ui {
    position: fixed;
    top: 25px;
    left: 0;
    width: 100%;
    text-align: center;
    pointer-events: none;
    z-index: 2;
}

#score {
    font-size: 32px;
    font-weight: bold;
    letter-spacing: 2px;
}

#label {
    font-size: 11px;
    color: #8291b5;
    letter-spacing: 4px;
    margin-top: 5px;
}

#status {
    margin-top: 12px;
    font-size: 13px;
    font-weight: bold;
    letter-spacing: 1px;
    text-shadow: 0 0 10px currentColor;
}

#message {
    position: fixed;
    top: 115px;
    left: 0;
    width: 100%;
    text-align: center;
    font-size: 18px;
    font-weight: bold;
    pointer-events: none;
    opacity: 0;
    transition: opacity 0.2s;
    z-index: 3;
}

#overlay {
    position: fixed;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background: rgba(5, 8, 20, 0.85);
    z-index: 5;
    text-align: center;
    padding: 20px;
}

#overlay h1 {
    font-size: clamp(30px, 8vw, 48px);
    letter-spacing: 3px;
    margin-bottom: 15px;
}

#overlay p {
    color: #aab5d0;
    line-height: 1.9;
    font-size: 14px;
    margin-bottom: 30px;
}

button {
    background: #738cff;
    color: white;
    border: none;
    border-radius: 10px;
    padding: 15px 45px;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
}

button:active {
    transform: scale(0.95);
}

.hidden {
    display: none !important;
}
</style>
</head>

<body>

<canvas id="game"></canvas>

<div id="ui">
    <div id="score">0</div>
    <div id="label">SCORE</div>
    <div id="status"></div>
</div>

<div id="message"></div>

<div id="overlay">
    <h1 id="title">METEOR<br>DODGE</h1>

    <p id="description">
        떨어지는 운석을 피하세요.<br>
        별을 획득하면 특별한 능력을 얻습니다.<br><br>

        🟡 노란 별 : +10점<br>
        🟠 주황 별 : 이동 속도 증가<br>
        🔴 빨간 별 : 무적 및 운석 파괴<br><br>

        PC : 방향키 / A, D<br>
        MOBILE : 화면 드래그
    </p>

    <button id="startBtn">게임 시작</button>
</div>

<script>

/* ==============================
   기본 설정
============================== */

const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

const scoreText = document.getElementById("score");
const statusText = document.getElementById("status");
const messageText = document.getElementById("message");

const overlay = document.getElementById("overlay");
const titleText = document.getElementById("title");
const description = document.getElementById("description");
const startBtn = document.getElementById("startBtn");

let W, H;

let running = false;

let score = 0;
let elapsed = 0;

let lastTime = 0;
let meteorTimer = 0;
let starTimer = 0;

let meteors = [];
let stars = [];
let particles = [];

let messageTimer = 0;

let speedBoost = 0;
let invincible = 0;

let keys = {
    left: false,
    right: false
};


/* ==============================
   화면 크기
============================== */

function resize() {

    const dpr = Math.min(
        window.devicePixelRatio || 1,
        2
    );

    W = window.innerWidth;
    H = window.innerHeight;

    canvas.width = W * dpr;
    canvas.height = H * dpr;

    ctx.setTransform(dpr, 0, 0, dpr, 0, 0);

    if (ship) {
        ship.y = H - 100;

        ship.x = Math.max(
            ship.width / 2,
            Math.min(W - ship.width / 2, ship.x)
        );
    }
}

window.addEventListener("resize", resize);


/* ==============================
   우주선
============================== */

const ship = {
    x: 0,
    y: 0,

    width: 42,
    height: 48,

    speed: 430
};


/* ==============================
   별 배경
============================== */

let backgroundStars = [];

function createStars() {

    backgroundStars = [];

    for (let i = 0; i < 100; i++) {

        backgroundStars.push({

            x: Math.random() * W,
            y: Math.random() * H,

            size: Math.random() * 2 + 0.5,

            speed: Math.random() * 25 + 10
        });
    }
}


function drawStars(dt) {

    ctx.fillStyle = "#080b18";

    ctx.fillRect(0, 0, W, H);

    for (const star of backgroundStars) {

        star.y += star.speed * dt;

        if (star.y > H) {

            star.y = 0;
            star.x = Math.random() * W;
        }

        ctx.fillStyle = "rgba(180,200,255,0.7)";

        ctx.beginPath();

        ctx.arc(
            star.x,
            star.y,
            star.size,
            0,
            Math.PI * 2
        );

        ctx.fill();
    }
}


/* ==============================
   우주선 그리기
============================== */

function drawShip() {

    ctx.save();

    ctx.translate(ship.x, ship.y);

    // 무적 상태 효과
    if (invincible > 0) {

        ctx.beginPath();

        ctx.arc(0, 0, 34, 0, Math.PI * 2);

        ctx.fillStyle = "rgba(255,70,70,0.15)";
        ctx.fill();

        ctx.strokeStyle = "#ff5555";
        ctx.lineWidth = 2;

        ctx.stroke();

        ctx.shadowBlur = 25;
        ctx.shadowColor = "#ff3333";
    }

    // 엔진 불꽃
    ctx.fillStyle = "#ff9d50";

    ctx.beginPath();

    ctx.moveTo(-7, 16);
    ctx.lineTo(0, 32 + Math.random() * 8);
    ctx.lineTo(7, 16);

    ctx.fill();

    // 우주선 본체
    ctx.fillStyle = "#91b9ff";

    ctx.beginPath();

    ctx.moveTo(0, -25);
    ctx.lineTo(19, 19);
    ctx.lineTo(0, 12);
    ctx.lineTo(-19, 19);

    ctx.closePath();
    ctx.fill();

    // 조종석
    ctx.fillStyle = "#273c75";

    ctx.beginPath();

    ctx.ellipse(
        0, -5,
        6, 11,
        0, 0, Math.PI * 2
    );

    ctx.fill();

    ctx.fillStyle = "#d6e5ff";
    ctx.fillRect(-17, 12, 34, 3);

    ctx.restore();
}


/* ==============================
   운석 생성
============================== */

function createMeteor() {

    const size = Math.random() * 18 + 15;

    meteors.push({

        x: Math.random() * (W - size * 2) + size,

        y: -size,

        radius: size,

        speed: 170 + elapsed * 7 + Math.random() * 80,

        rotation: Math.random() * Math.PI,

        rotationSpeed: (Math.random() - 0.5) * 3
    });
}


/* ==============================
   운석 그리기
============================== */

function drawMeteor(meteor, dt) {

    meteor.rotation += meteor.rotationSpeed * dt;

    ctx.save();

    ctx.translate(meteor.x, meteor.y);
    ctx.rotate(meteor.rotation);

    ctx.fillStyle = "#a36c58";

    ctx.beginPath();

    const points = 9;

    for (let i = 0; i < points; i++) {

        const angle = Math.PI * 2 / points * i;

        const radius =
            meteor.radius *
            (0.85 + Math.sin(i * 3) * 0.12);

        const x = Math.cos(angle) * radius;
        const y = Math.sin(angle) * radius;

        if (i === 0) ctx.moveTo(x, y);
        else ctx.lineTo(x, y);
    }

    ctx.closePath();
    ctx.fill();

    ctx.fillStyle = "#704b43";

    ctx.beginPath();
    ctx.arc(-5, -4, meteor.radius * 0.2, 0, Math.PI * 2);
    ctx.fill();

    ctx.beginPath();
    ctx.arc(7, 5, meteor.radius * 0.13, 0, Math.PI * 2);
    ctx.fill();

    ctx.restore();
}


/* ==============================
   별 아이템 생성
============================== */

function createPowerStar() {

    // 0 = 노란색
    // 1 = 주황색
    // 2 = 빨간색

    const random = Math.random();

    let type;

    if (random < 0.6) {
        type = 0;
    }
    else if (random < 0.85) {
        type = 1;
    }
    else {
        type = 2;
    }

    const colors = [
        "#ffe45c",
        "#ff963c",
        "#ff4242"
    ];

    stars.push({

        x: Math.random() * (W - 60) + 30,

        y: -30,

        radius: 13,

        speed: 130 + Math.random() * 50,

        type: type,

        color: colors[type],

        rotation: 0
    });
}


/* ==============================
   별 그리기
============================== */

function drawPowerStar(star, dt) {

    star.rotation += dt * 3;

    ctx.save();

    ctx.translate(star.x, star.y);
    ctx.rotate(star.rotation);

    ctx.shadowBlur = 18;
    ctx.shadowColor = star.color;

    ctx.fillStyle = star.color;

    ctx.beginPath();

    // 별 모양
    for (let i = 0; i < 10; i++) {

        const angle = Math.PI * 2 / 10 * i - Math.PI / 2;

        const radius =
            i % 2 === 0 ? 15 : 6;

        const x = Math.cos(angle) * radius;
        const y = Math.sin(angle) * radius;

        if (i === 0) ctx.moveTo(x, y);
        else ctx.lineTo(x, y);
    }

    ctx.closePath();
    ctx.fill();

    ctx.restore();
}


/* ==============================
   파티클 효과
============================== */

function createParticles(x, y, color) {

    for (let i = 0; i < 15; i++) {

        const angle = Math.random() * Math.PI * 2;

        const speed = Math.random() * 150 + 50;

        particles.push({

            x: x,
            y: y,

            vx: Math.cos(angle) * speed,
            vy: Math.sin(angle) * speed,

            life: 0.6,

            color: color
        });
    }
}


function updateParticles(dt) {

    for (let i = particles.length - 1; i >= 0; i--) {

        const p = particles[i];

        p.x += p.vx * dt;
        p.y += p.vy * dt;

        p.life -= dt;

        if (p.life <= 0) {
            particles.splice(i, 1);
            continue;
        }

        ctx.globalAlpha = p.life / 0.6;

        ctx.fillStyle = p.color;

        ctx.beginPath();

        ctx.arc(p.x, p.y, 3, 0, Math.PI * 2);

        ctx.fill();

        ctx.globalAlpha = 1;
    }
}


/* ==============================
   충돌 판정
============================== */

function isColliding(a, b, distance) {

    const dx = a.x - b.x;
    const dy = a.y - b.y;

    return Math.sqrt(dx * dx + dy * dy) < distance;
}


/* ==============================
   아이템 획득
============================== */

function collectStar(star) {

    createParticles(
        star.x,
        star.y,
        star.color
    );

    // 노란색 별
    if (star.type === 0) {

        score += 10;

        showMessage(
            "★ +10 BONUS!",
            "#ffe45c"
        );
    }

    // 주황색 별
    else if (star.type === 1) {

        speedBoost = 5;

        showMessage(
            "⚡ SPEED UP!",
            "#ff963c"
        );
    }

    // 빨간색 별
    else if (star.type === 2) {

        invincible = 5;

        showMessage(
            "★ INVINCIBLE!",
            "#ff4242"
        );
    }
}


/* ==============================
   아이템 획득 메시지
============================== */

function showMessage(text, color) {

    messageText.textContent = text;

    messageText.style.color = color;

    messageText.style.opacity = 1;

    messageTimer = 1.5;
}


/* ==============================
   키보드 조작
============================== */

window.addEventListener("keydown", (e) => {

    if (
        ["ArrowLeft", "ArrowRight", " "].includes(e.key)
    ) {
        e.preventDefault();
    }

    if (
        e.key === "ArrowLeft" ||
        e.key.toLowerCase() === "a"
    ) {
        keys.left = true;
    }

    if (
        e.key === "ArrowRight" ||
        e.key.toLowerCase() === "d"
    ) {
        keys.right = true;
    }
});


window.addEventListener("keyup", (e) => {

    if (
        e.key === "ArrowLeft" ||
        e.key.toLowerCase() === "a"
    ) {
        keys.left = false;
    }

    if (
        e.key === "ArrowRight" ||
        e.key.toLowerCase() === "d"
    ) {
        keys.right = false;
    }
});


/* ==============================
   터치 및 마우스 조작
============================== */

let touching = false;

function moveShip(e) {

    if (!running) return;

    const rect = canvas.getBoundingClientRect();

    ship.x = e.clientX - rect.left;

    ship.x = Math.max(
        ship.width / 2,
        Math.min(W - ship.width / 2, ship.x)
    );
}


canvas.addEventListener("pointerdown", (e) => {

    touching = true;

    moveShip(e);
});

canvas.addEventListener("pointermove", (e) => {

    if (touching) moveShip(e);
});

window.addEventListener("pointerup", () => {
    touching = false;
});

window.addEventListener("pointercancel", () => {
    touching = false;
});


/* ==============================
   게임 초기화
============================== */

function startGame() {

    score = 0;
    elapsed = 0;

    meteorTimer = 0;
    starTimer = 0;

    meteors = [];
    stars = [];
    particles = [];

    speedBoost = 0;
    invincible = 0;

    ship.x = W / 2;
    ship.y = H - 100;

    keys.left = false;
    keys.right = false;

    running = true;

    messageText.style.opacity = 0;

    overlay.classList.add("hidden");

    lastTime = performance.now();

    requestAnimationFrame(gameLoop);
}


/* ==============================
   게임 오버
============================== */

function endGame() {

    running = false;

    titleText.innerHTML = "GAME OVER";

    description.innerHTML =
        `최종 점수 : ${score}점<br><br>` +
        `생존 시간 : ${Math.floor(elapsed)}초<br><br>` +
        "우주선이 운석에 충돌했습니다!";

    startBtn.textContent = "다시 시작";

    overlay.classList.remove("hidden");
}


/* ==============================
   게임 진행
============================== */

function gameLoop(time) {

    if (!running) return;

    let dt = (time - lastTime) / 1000;

    dt = Math.min(dt, 0.04);

    lastTime = time;

    elapsed += dt;

    // 생존 시간 점수
    score = Math.floor(elapsed) + bonusScore;

    drawStars(dt);

    // 능력 지속 시간 감소
    if (speedBoost > 0) {
        speedBoost = Math.max(0, speedBoost - dt);
    }

    if (invincible > 0) {
        invincible = Math.max(0, invincible - dt);
    }

    // 능력 상태 표시
    let status = [];

    if (speedBoost > 0) {
        status.push("⚡ SPEED " + speedBoost.toFixed(1) + "s");
    }

    if (invincible > 0) {
        status.push("★ INVINCIBLE " + invincible.toFixed(1) + "s");
    }

    statusText.textContent = status.join("  |  ");

    statusText.style.color =
        invincible > 0 ? "#ff5555" :
        speedBoost > 0 ? "#ff963c" :
        "#8291b5";

    // 메시지 시간
    if (messageTimer > 0) {

        messageTimer -= dt;

        if (messageTimer <= 0) {
            messageText.style.opacity = 0;
        }
    }

    // 키보드 이동
    const currentSpeed =
        speedBoost > 0 ? ship.speed * 1.8 : ship.speed;

    if (keys.left) {
        ship.x -= currentSpeed * dt;
    }

    if (keys.right) {
        ship.x += currentSpeed * dt;
    }

    ship.x = Math.max(
        ship.width / 2,
        Math.min(W - ship.width / 2, ship.x)
    );

    // 운석 생성
    const spawnInterval = Math.max(
        0.22,
        0.95 - elapsed * 0.012
    );

    meteorTimer += dt;

    if (meteorTimer >= spawnInterval) {

        createMeteor();

        meteorTimer = 0;
    }

    // 별 생성
    starTimer += dt;

    if (starTimer >= 5 + Math.random() * 4) {

        createPowerStar();

        starTimer = 0;
    }

    // 운석 업데이트
    for (let i = meteors.length - 1; i >= 0; i--) {

        const meteor = meteors[i];

        meteor.y += meteor.speed * dt;

        // 무적 상태라면 운석 파괴
        if (invincible > 0) {

            if (
                isColliding(meteor, ship, meteor.radius + 22)
            ) {

                createParticles(
                    meteor.x,
                    meteor.y,
                    "#ff5555"
                );

                meteors.splice(i, 1);

                continue;
            }
        }

        // 일반 충돌
        else {

            if (
                isColliding(meteor, ship, meteor.radius + 15)
            ) {

                endGame();

                return;
            }
        }

        drawMeteor(meteor, dt);

        if (meteor.y > H + meteor.radius) {

            meteors.splice(i, 1);
        }
    }

    // 별 업데이트
    for (let i = stars.length - 1; i >= 0; i--) {

        const star = stars[i];

        star.y += star.speed * dt;

        drawPowerStar(star, dt);

        // 우주선과 별 충돌
        if (
            isColliding(star, ship, star.radius + 20)
        ) {

            collectStar(star);

            stars.splice(i, 1);

            continue;
        }

        // 화면 밖으로 나간 별 제거
        if (star.y > H + 30) {

            stars.splice(i, 1);
        }
    }

    // 파티클
    updateParticles(dt);

    // 우주선
    drawShip();

    // 점수
    scoreText.textContent = score;

    requestAnimationFrame(gameLoop);
}


/* ==============================
   보너스 점수
============================== */

let bonusScore = 0;

// 노란 별 획득 시 보너스 점수 누적
const originalCollectStar = collectStar;

collectStar = function(star) {

    if (star.type === 0) {
        bonusScore += 10;
    }

    originalCollectStar(star);
};


/* ==============================
   시작 버튼
============================== */

startBtn.addEventListener("click", () => {

    titleText.innerHTML = "METEOR<br>DODGE";

    bonusScore = 0;

    startGame();
});


/* ==============================
   최초 실행
============================== */

resize();

createStars();

ship.x = W / 2;
ship.y = H - 100;

drawStars(0);
drawShip();

</script>

</body>
</html>
