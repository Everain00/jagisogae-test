<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>EVERAIN | HOME</title>
  <style>
    * { box-sizing: border-box; }

    body {
      margin: 0;
      min-height: 100vh;
      color: #20251f;
      background: #f6f7f1;
      font-family: "Noto Sans KR", sans-serif;
    }

    .wrap {
      width: min(1080px, calc(100% - 48px));
      margin: auto;
      padding: 34px 0;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      display: flex;
      justify-content: space-between;
      padding: 8px 0 24px;
      border-bottom: 1px solid #ddd;
    }

    .logo {
      font-weight: 800;
      letter-spacing: .22em;
    }

    .edition {
      color: #737b70;
      font-size: 11px;
      letter-spacing: .16em;
    }

    main {
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .intro { padding: 72px 0 44px; }

    .eyebrow {
      color: #52745d;
      font-size: 11px;
      font-weight: bold;
      letter-spacing: .2em;
      margin-bottom: 20px;
    }

    h1 {
      margin: 0;
      font-size: clamp(42px, 7vw, 76px);
      line-height: 1.08;
      letter-spacing: -.065em;
    }

    h1 span { color: #52745d; }

    .intro p {
      margin-top: 22px;
      color: #737b70;
      font-size: 15px;
      line-height: 1.8;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 18px;
      padding-bottom: 58px;
    }

    .card {
      min-height: 260px;
      padding: 30px;
      border: 1px solid #ddd;
      border-radius: 22px;
      background: rgba(255,255,255,.8);
      text-decoration: none;
      color: inherit;
      display: flex;
      flex-direction: column;
      transition: .22s;
    }

    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 18px 42px rgba(42,58,43,.09);
    }

    .card-number {
      color: #52745d;
      font-size: 11px;
      letter-spacing: .16em;
      font-weight: bold;
    }

    .icon {
      font-size: 31px;
      margin: 22px 0 14px;
    }

    .card h2 {
      margin: 0;
      font-size: 27px;
    }

    .card p {
      color: #737b70;
      font-size: 14px;
      line-height: 1.65;
    }

    .go {
      margin-top: auto;
      display: flex;
      justify-content: space-between;
      color: #52745d;
      font-size: 12px;
      font-weight: bold;
      letter-spacing: .12em;
    }

    .arrow { font-size: 20px; }

    footer {
      border-top: 1px solid #ddd;
      padding-top: 18px;
      color: #92988e;
      font-size: 10px;
      letter-spacing: .14em;
      display: flex;
      justify-content: space-between;
    }

    @media(max-width:650px) {
      .cards { grid-template-columns: 1fr; }
      .card { min-height: 225px; }
      footer { flex-direction: column; gap: 12px; }
    }
  </style>
</head>

<body>
<div class="wrap">

  <header>
    <div class="logo">EVERAIN</div>
    <div class="edition">PERSONAL SPACE · 2026</div>
  </header>

  <main>
    <section class="intro">
      <div class="eyebrow">WELCOME TO MY SPACE</div>

      <h1>
        바이브 코딩<br>
        <span>허브</span>
      </h1>

      <p>
        목표를 기록하고, 직접 만든 게임을 즐기는 공간입니다.<br>
        아래에서 원하는 페이지를 선택해 주세요.
      </p>
    </section>

    <nav class="cards">

      <a class="card"
         href="https://everain00.github.io/everain-vibecoding/goal/index.html">

        <div class="card-number">01 / MY GOALS</div>
        <div class="icon">✳</div>
        <h2>만다라트</h2>

        <p>
          생각과 목표를 정리하고<br>
          매일의 작은 실천을 기록하는 곳.
        </p>

        <div class="go">
          <span>EXPLORE GOALS</span>
          <span class="arrow">↗</span>
        </div>
      </a>

      <a class="card"
         href="https://everain00.github.io/everain-vibecoding/game/main.html">

        <div class="card-number">02 / PLAYGROUND</div>
        <div class="icon">✦</div>
        <h2>게임 아카이브</h2>

        <p>
          직접 만든 작은 게임들을 모아 둔<br>
          나만의 플레이그라운드.
        </p>

        <div class="go">
          <span>LET'S PLAY</span>
          <span class="arrow">↗</span>
        </div>
      </a>

    </nav>
  </main>

  <footer>
    <span>© EVERAIN · PERSONAL PROJECT</span>
    <span>MAKE · LEARN · PLAY</span>
  </footer>

</div>
</body>
</html>
