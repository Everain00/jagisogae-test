<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>임연우 | 자기소개와 목표</title>

    <!-- ===== D-day 설정: 날짜와 이름을 여기서 변경하세요! ===== -->
    <script>
        const TARGET_DATE = "2027-11-18";
        const TARGET_NAME = "수능까지";
    </script>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            min-height: 100vh;
            padding: 24px 12px 40px;
            font-family: "Malgun Gothic", sans-serif;
            color: #30384a;
            background: linear-gradient(135deg, #e8efff, #f7edfa, #e5f5f3);
        }

        /* D-day와 자기소개 카드 */
        .profile-container {
            width: 100%;
            max-width: 360px;
            margin: 0 auto 36px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* D-day 카운터 */
        .dday-box {
            width: 100%;
            padding: 24px 20px;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #dce6ff, #eadcf7);
            border-radius: 24px;
            box-shadow: 0 12px 35px rgba(65, 75, 110, 0.12);
            text-align: center;
            color: #30384a;
        }

        .dday-number {
            margin: 0;
            font-size: clamp(48px, 12vw, 68px);
            font-weight: 800;
            letter-spacing: -2px;
            line-height: 1.2;
        }

        .dday-label {
            margin: 8px 0 0;
            font-size: 14px;
            color: #6674b8;
            font-weight: 600;
        }

        /* 자기소개 카드 */
        .card {
            width: 100%;
            padding: 40px 28px;
            background-color: #ffffff;
            border-radius: 24px;
            text-align: center;
            box-shadow: 0 12px 35px rgba(65, 75, 110, 0.12);
        }

        .emoji {
            font-size: 72px;
            line-height: 1.3;
            margin-bottom: 20px;
        }

        h1 {
            margin: 0 0 12px;
            font-size: 28px;
            font-weight: 700;
            letter-spacing: -1px;
        }

        .intro {
            margin: 0;
            font-size: 14px;
            line-height: 1.8;
            color: #7a8293;
            word-break: keep-all;
        }

        .favorites {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 8px;
            margin: 28px 0;
        }

        .tag {
            padding: 9px 16px;
            background-color: #f0f3ff;
            color: #6674b8;
            border-radius: 999px;
            font-size: 14px;
        }

        .github-button {
            display: block;
            width: 100%;
            padding: 14px 20px;
            background-color: #30384a;
            color: #ffffff;
            border-radius: 12px;
            text-decoration: none;
            font-size: 15px;
            font-weight: 600;
            transition: background-color 0.2s, transform 0.2s;
        }

        .github-button:hover {
            background-color: #4c5873;
            transform: translateY(-2px);
        }

        /* 만다라트 영역 */
        .mandalart-section {
            width: 100%;
            max-width: 720px;
            margin: 0 auto;
        }

        .mandalart-header {
            text-align: center;
            margin-bottom: 22px;
        }

        .mandalart-header h2 {
            margin: 0 0 8px;
            font-size: clamp(26px, 6vw, 36px);
            letter-spacing: -1px;
        }

        .mandalart-hint {
            margin: 0;
            color: #7a8293;
            font-size: 14px;
        }

        .mandalart-grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 8px;
            width: 100%;
        }

        .goal-cell {
            aspect-ratio: 1 / 1;
            min-width: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: clamp(5px, 2vw, 14px);
            border: 1px solid #e2e7f2;
            border-radius: 16px;
            background: #ffffff;
            box-shadow: 0 5px 16px rgba(65, 75, 110, 0.08);
            color: #39445c;
            font-family: inherit;
            font-size: clamp(11px, 2.7vw, 16px);
            line-height: 1.45;
            text-align: center;
            overflow-wrap: anywhere;
            word-break: keep-all;
            cursor: text;
            outline: none;
            transition: border-color 0.15s, box-shadow 0.15s;
        }

        .goal-cell:focus {
            border-color: #8c9ee8;
            box-shadow: 0 0 0 3px rgba(140, 158, 232, 0.2);
        }

        .goal-cell.center {
            background: linear-gradient(145deg, #cddaff, #e6d5f5);
            border: 2px solid #9aa9e8;
            color: #303b70;
            font-weight: 700;
        }

        .goal-cell.center:focus {
            border-color: #6f80d4;
        }

        .mandalart-note {
            margin: 16px 0 0;
            text-align: center;
            color: #7a8293;
            font-size: 12px;
            line-height: 1.6;
        }

        @media (max-width: 400px) {
            body {
                padding: 16px 8px 32px;
            }

            .card {
                padding: 32px 22px;
            }

            .emoji {
                font-size: 64px;
            }

            h1 {
                font-size: 26px;
            }
        }

        @media (max-width: 360px) {
            .mandalart-grid {
                gap: 5px;
            }

            .goal-cell {
                border-radius: 10px;
                padding: 4px;
                font-size: 11px;
            }
        }
    </style>
</head>

<body>
    <!-- D-day와 자기소개 카드 -->
    <section class="profile-container">
        <div class="dday-box" aria-label="D-day 카운터">
            <p class="dday-number" id="dday-number">D-0</p>
            <p class="dday-label" id="dday-label">수능까지</p>
        </div>

        <main class="card">
            <div class="emoji" aria-label="눈 내리는 날">🌨️</div>

            <h1>임연우</h1>
            <p class="intro">겨울과 음악을 좋아하는 고등학교 2학년입니다</p>

            <div class="favorites">
                <span class="tag">📚 책</span>
                <span class="tag">🎧 음악</span>
                <span class="tag">❄️ 눈</span>
            </div>

            <!-- 실제 깃허브 프로필 주소로 바꿀 수 있습니다. -->
            <a
                class="github-button"
                href="https://github.com/"
                target="_blank"
                rel="noopener noreferrer"
            >내 깃허브 ↗</a>
        </main>
    </section>

    <!-- 만다라트 목표판 -->
    <section class="mandalart-section">
        <header class="mandalart-header">
            <h2>나의 목표</h2>
            <p class="mandalart-hint">칸을 눌러서 고칠 수 있어요</p>
        </header>

        <div class="mandalart-grid" aria-label="3x3 만다라트 목표판">
            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 1" spellcheck="false">매일 30분 영어 듣기</div>
            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 2" spellcheck="false">수학 오답노트</div>
            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 3" spellcheck="false">주 3회 운동</div>

            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 4" spellcheck="false">독서 월 2권</div>
            <div class="goal-cell center" contenteditable="true" role="textbox" aria-label="중심 목표" spellcheck="false">해양생물학과 진학</div>
            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 5" spellcheck="false">과학 동아리 발표</div>

            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 6" spellcheck="false">7시간 수면</div>
            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 7" spellcheck="false">봉사활동 20시간</div>
            <div class="goal-cell" contenteditable="true" role="textbox" aria-label="세부 목표 8" spellcheck="false">코딩 포트폴리오</div>
        </div>

        <p class="mandalart-note">수정한 내용은 자동으로 저장돼요. 같은 브라우저에서 다시 열어도 유지됩니다.</p>
    </section>

    <script>
        // D-day 자동 계산
        function updateDday() {
            const today = new Date();
            const target = new Date(TARGET_DATE + "T00:00:00");
            today.setHours(0, 0, 0, 0);

            const difference = target.getTime() - today.getTime();
            const days = Math.ceil(difference / (1000 * 60 * 60 * 24));

            let display;
            if (days > 0) {
                display = `D-${days}`;
            } else if (days === 0) {
                display = "D-DAY";
            } else {
                display = `D+${Math.abs(days)}`;
            }

            document.getElementById("dday-number").textContent = display;
            document.getElementById("dday-label").textContent = TARGET_NAME;
        }

        updateDday();

        // 만다라트 목표를 브라우저에 자동 저장
        const goalCells = document.querySelectorAll(".goal-cell");
        const STORAGE_KEY = "mandalart-goals-v1";

        // 저장된 목표가 있으면 불러오기
        try {
            const savedGoals = JSON.parse(localStorage.getItem(STORAGE_KEY));
            if (Array.isArray(savedGoals) && savedGoals.length === goalCells.length) {
                goalCells.forEach((cell, index) => {
                    cell.textContent = savedGoals[index];
                });
            }
        } catch (error) {
            console.warn("저장된 목표를 불러오지 못했습니다.", error);
        }

        // 칸의 글자가 바뀔 때마다 저장
        function saveGoals() {
            const goals = Array.from(goalCells, cell => cell.innerText.trim());
            try {
                localStorage.setItem(STORAGE_KEY, JSON.stringify(goals));
            } catch (error) {
                console.warn("목표를 저장하지 못했습니다.", error);
            }
        }

        goalCells.forEach(cell => {
            cell.addEventListener("input", saveGoals);
            cell.addEventListener("keydown", event => {
                // Enter 키로 줄바꿈하지 않고 편집을 마칩니다.
                if (event.key === "Enter") {
                    event.preventDefault();
                    cell.blur();
                }
            });
        });
    </script>
</body>
</html>
