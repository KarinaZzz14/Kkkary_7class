# Kkkary_7class
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spotlight 7 · Module 8 · Eco Design Pro</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Roboto', 'Helvetica Neue', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0a4f32 0%, #1f7a55 40%, #0f6b44 70%, #0a4f32 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 15px;
            position: relative;
            overflow-x: hidden;
        }

        /* Анимированный фон с листьями */
        body::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 200" opacity="0.15"><path d="M40,160 Q60,130 80,160 T120,160 T160,160" stroke="%23ffffff" fill="none" stroke-width="3"/><circle cx="70" cy="50" r="18" fill="%23ffffff" opacity="0.25"/><circle cx="150" cy="100" r="25" fill="%23ffffff" opacity="0.2"/><path d="M20,180 L35,150 L50,180" fill="%23ffffff" opacity="0.2"/><path d="M160,170 L175,140 L190,170" fill="%23ffffff" opacity="0.2"/><path d="M100,30 L110,10 L120,30" fill="%23ffffff" opacity="0.2"/><path d="M30,70 L45,40 L60,70" fill="%23ffffff" opacity="0.2"/></svg>') repeat;
            pointer-events: none;
            z-index: 0;
            animation: floatingLeaves 60s linear infinite;
        }

        @keyframes floatingLeaves {
            0% { background-position: 0 0; }
            100% { background-position: 200px 200px; }
        }

        .main-container {
            max-width: 1800px;
            width: 100%;
            background: rgba(255, 252, 240, 0.98);
            backdrop-filter: blur(10px);
            border-radius: 70px 70px 50px 50px;
            box-shadow: 0 30px 60px rgba(0, 40, 20, 0.6), 0 0 0 4px #8fc0a9, 0 0 0 8px #f4b53240;
            overflow: hidden;
            border: 2px solid #f4b532;
            position: relative;
            z-index: 10;
            transition: all 0.4s ease;
        }

        .main-container:hover {
            box-shadow: 0 35px 70px rgba(0, 60, 30, 0.7), 0 0 0 4px #7fba9a, 0 0 0 12px #f4b53280;
        }

        /* Декоративная верхняя полоса */
        .main-container::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 20px;
            background: linear-gradient(90deg, #4c9f70, #f4b532, #6bb46e, #f4b532, #4c9f70, #f4b532, #4c9f70);
            background-size: 400% 100%;
            animation: gradientMove 8s ease infinite;
            z-index: 20;
            border-radius: 70px 70px 0 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .tabs-header {
            display: flex;
            flex-wrap: wrap;
            background: linear-gradient(145deg, #d0e8c8, #b8dcb0);
            border-bottom: 5px solid #3b7850;
            position: relative;
            padding: 8px 8px 0 8px;
            gap: 8px;
        }

        .tabs-header::after {
            content: "🌿🌱🍃🌳";
            position: absolute;
            right: 30px;
            top: 12px;
            font-size: 2.2rem;
            color: #2d6a4f;
            opacity: 0.4;
            text-shadow: 2px 2px 4px rgba(255,255,255,0.5);
        }

        .tab-btn {
            flex: 1 0 auto;
            padding: 18px 12px;
            border: none;
            background: rgba(255, 255, 245, 0.8);
            font-size: 1.3rem;
            font-weight: 700;
            color: #1c4d3a;
            cursor: pointer;
            border-top-left-radius: 35px;
            border-top-right-radius: 35px;
            transition: all 0.25s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-transform: uppercase;
            letter-spacing: 1.5px;
            border: 2px solid transparent;
            border-bottom: 5px solid transparent;
            backdrop-filter: blur(5px);
            box-shadow: 0 -2px 5px rgba(0,20,0,0.1);
        }

        .tab-btn.active {
            background: #f5ffe0;
            color: #0f4d2e;
            border-bottom: 5px solid #f4b532;
            border-left: 2px solid #9fc98f;
            border-right: 2px solid #9fc98f;
            border-top: 2px solid #9fc98f;
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0,60,0,0.4);
            text-shadow: 0 2px 4px rgba(0,60,0,0.2);
        }

        .tab-btn.active::before {
            content: "🌱";
            margin-right: 10px;
            font-size: 1.3rem;
            display: inline-block;
            animation: bounce 1.2s ease infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-4px); }
        }

        .tab-btn:hover:not(.active) {
            background: #e0f0d5;
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0,70,0,0.3);
            border-bottom: 3px solid #8fc98f;
        }

        .pages-content {
            padding: 40px 35px;
            background: linear-gradient(145deg, #fafff0, #f2fce8);
            background-image: radial-gradient(circle at 10% 20%, rgba(120, 200, 120, 0.1) 0%, transparent 40%),
                              radial-gradient(circle at 90% 80%, rgba(244, 181, 50, 0.1) 0%, transparent 40%);
            position: relative;
        }

        .page {
            display: none;
            animation: fadeScale 0.3s ease-out;
        }

        .page.active-page {
            display: block;
        }

        @keyframes fadeScale {
            from { opacity: 0; transform: scale(0.97) translateY(5px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        h2 {
            color: #1b5e3a;
            border-left: 15px solid #f4b532;
            padding-left: 25px;
            margin-bottom: 30px;
            font-size: 2.4rem;
            text-shadow: 3px 3px 0 #e0f0d8;
            display: flex;
            align-items: center;
            gap: 15px;
            background: linear-gradient(to right, #ffffffb0, transparent);
            border-radius: 0 60px 60px 0;
            padding: 15px 25px;
            box-shadow: 0 5px 10px rgba(0,30,0,0.1);
        }

        h2::after {
            content: "🌍";
            font-size: 2.5rem;
            margin-left: auto;
            opacity: 0.8;
            filter: drop-shadow(2px 2px 4px rgba(0,60,0,0.3));
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Блок с правилами - улучшенный */
        .rules-box {
            background: linear-gradient(145deg, #e8f7e0, #d4ecd0);
            border: 4px solid #4a8b6e;
            border-radius: 60px 60px 40px 40px;
            padding: 30px 35px;
            margin-bottom: 40px;
            box-shadow: 0 12px 0 #2a5e45, 0 20px 30px -10px #1e4a33, inset 0 2px 10px #ffffffc0;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .rules-box:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 0 #2a5e45, 0 25px 35px -8px #0f3a24;
        }

        .rules-box::before {
            content: "🌿🌱🍃🌳🌲";
            position: absolute;
            bottom: -20px;
            right: -20px;
            font-size: 7rem;
            opacity: 0.15;
            transform: rotate(10deg);
            pointer-events: none;
        }

        .rules-box h3 {
            color: #0b472b;
            font-size: 2rem;
            margin-bottom: 20px;
            border-bottom: 4px solid #f4b532;
            padding-bottom: 10px;
            display: inline-block;
            background: #ffffff80;
            padding: 8px 30px;
            border-radius: 50px;
            backdrop-filter: blur(4px);
            box-shadow: 0 4px 8px rgba(0,30,0,0.2);
        }

        .rules-box p {
            font-size: 1.25rem;
            margin: 15px 0;
            color: #1c4a33;
            line-height: 1.7;
            background: rgba(255, 255, 255, 0.6);
            padding: 8px 20px;
            border-radius: 40px;
            backdrop-filter: blur(2px);
        }

        .rules-box ul {
            margin-left: 40px;
            font-size: 1.2rem;
            color: #1c4a33;
            background: rgba(255, 255, 255, 0.5);
            padding: 15px 30px;
            border-radius: 40px;
            list-style-type: none;
            backdrop-filter: blur(2px);
        }

        .rules-box li {
            margin: 12px 0;
            padding-left: 35px;
            position: relative;
        }

        .rules-box li::before {
            content: "🌿";
            position: absolute;
            left: 0;
            top: -2px;
            font-size: 1.4rem;
        }

        .rules-box .example {
            background: linear-gradient(145deg, #fffff0, #f5ffe0);
            padding: 20px 30px;
            border-radius: 50px;
            border-left: 12px solid #f4b532;
            margin: 25px 0;
            box-shadow: 0 8px 0 #9bbc8b, 0 10px 20px -8px #2a5a2a;
            font-weight: 500;
            border: 2px solid #b8daa8;
        }

        .rules-box .highlight {
            background: #f4b532;
            color: #0a3a20;
            padding: 5px 18px;
            border-radius: 50px;
            font-weight: 700;
            display: inline-block;
            box-shadow: 0 4px 0 #9e7127;
        }

        /* Сетка карточек */
        .vocab-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 35px;
            margin: 35px 0;
        }

        /* КАРТОЧКИ С 3D-ПЕРЕВОРОТОМ - ИСПРАВЛЕНО */
        .voc-card {
            background: transparent;
            perspective: 1800px;
            min-height: 340px;
            cursor: pointer;
        }

        .voc-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.6s cubic-bezier(0.23, 1, 0.32, 1);
            transform-style: preserve-3d;
            border-radius: 45px;
            box-shadow: 0 18px 30px -10px #1a4a1a;
        }

        .voc-card.revealed .voc-card-inner {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            position: relative;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 45px;
            padding: 20px 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 340px;
            border: 3px solid;
            box-shadow: inset 0 2px 10px rgba(255,255,200,0.5);
        }

        .card-front {
            background: linear-gradient(145deg, #ffffff, #f8ffe8);
            border-color: #9fc98f;
            transform: rotateY(0deg);
            z-index: 2;
        }

        .card-back {
            background: linear-gradient(145deg, #fff5d0, #f0f5d0);
            border-color: #f4b532;
            transform: rotateY(180deg);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .word-image {
            width: 130px;
            height: 130px;
            font-size: 5.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 15px;
            background: radial-gradient(circle at 30% 30%, #e0f0d0, #c0e0b0);
            border-radius: 50%;
            padding: 10px;
            border: 4px solid #6b9e6b;
            box-shadow: inset 0 -5px 0 #3b6e3b, 0 10px 0 #3b6e3b, 0 10px 15px -5px #1a4a1a;
            transition: all 0.3s;
        }

        .word-text {
            font-size: 1.5rem;
            font-weight: 700;
            color: #1e5a3a;
            margin-bottom: 15px;
            text-align: center;
            background: #e0f0d0;
            padding: 8px 22px;
            border-radius: 60px;
            border: 2px solid #7fa07f;
            box-shadow: 0 4px 0 #5f805f;
            width: 100%;
            word-break: break-word;
        }

        .translation-text {
            font-size: 1.5rem;
            color: #0c5a3a;
            margin-bottom: 15px;
            text-align: center;
            font-weight: 600;
            background: #fffaec;
            padding: 8px 22px;
            border-radius: 60px;
            border: 3px dashed #7da06d;
            width: 100%;
            word-break: break-word;
        }

        .sound-icon {
            margin-top: 12px;
            font-size: 2.3rem;
            cursor: pointer;
            background: linear-gradient(145deg, #c4e0b8, #b4d4a8);
            border-radius: 50%;
            width: 65px;
            height: 65px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: none;
            box-shadow: 0 7px 0 #6f8f60, 0 5px 15px rgba(0,30,0,0.3);
            transition: all 0.12s ease;
            align-self: center;
            border: 3px solid #4a7e4a;
            font-size: 2.5rem;
        }

        .sound-icon:active {
            transform: translateY(7px);
            box-shadow: 0 0px 0 #6f8f60;
        }

        .sound-icon:hover {
            background: linear-gradient(145deg, #b2d6a2, #a2c692);
            transform: scale(1.08);
        }

        /* Блоки упражнений - улучшенные */
        .exercise-block {
            background: linear-gradient(145deg, #e2f2e0, #d2e8d0);
            border-radius: 70px;
            padding: 35px;
            margin: 30px 0;
            border: 4px solid #6f9e7a;
            box-shadow: inset 0 0 0 3px #ffffffc0, 0 18px 0 #4f7353, 0 25px 35px -8px #1a4a1a;
        }

        .question-item {
            background: #ffffff;
            border-radius: 50px;
            padding: 25px 30px;
            margin: 25px 0;
            box-shadow: 0 10px 0 #9fb893, 0 15px 25px -8px #2a5a2a;
            border: 2px solid #b8d9a8;
            transition: all 0.2s;
        }

        .question-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 13px 0 #9fb893, 0 20px 30px -5px #1d4a1d;
        }

        .question-text {
            font-size: 1.25rem;
            margin-bottom: 20px;
            font-weight: 600;
            color: #1d5435;
            background: #e8f5e0;
            padding: 12px 25px;
            border-radius: 50px;
            border-left: 8px solid #f4b532;
        }

        .options {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 15px;
        }

        .option-btn {
            background: linear-gradient(145deg, #d6eaca, #c6daba);
            border: none;
            border-radius: 60px;
            padding: 14px 30px;
            font-size: 1.15rem;
            font-weight: 600;
            color: #1b4a2e;
            cursor: pointer;
            box-shadow: 0 7px 0 #7f9f73, 0 5px 12px rgba(0,30,0,0.2);
            transition: all 0.1s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 2px solid #6f9a6f;
            flex: 0 1 auto;
        }

        .option-btn:active {
            transform: translateY(7px);
            box-shadow: 0 0px 0 #7f9f73;
        }

        .option-btn.correct {
            background: linear-gradient(145deg, #44b875, #34a865);
            color: white;
            box-shadow: 0 4px 0 #166635;
            transform: translateY(3px);
            border-color: #1e7e4a;
            cursor: default;
        }

        .option-btn.wrong {
            background: linear-gradient(145deg, #da6060, #ca5050);
            color: white;
            box-shadow: 0 4px 0 #771d1d;
            transform: translateY(3px);
            border-color: #a13a3a;
            cursor: default;
        }

        .write-answer {
            display: flex;
            gap: 15px;
            align-items: center;
            flex-wrap: wrap;
        }

        .answer-input {
            padding: 16px 25px;
            font-size: 1.15rem;
            border: 3px solid #7d9f72;
            border-radius: 70px;
            flex: 1;
            min-width: 250px;
            outline: none;
            background: #fffef5;
            box-shadow: inset 0 3px 8px rgba(0,20,0,0.1), 0 5px 0 #6f8f60;
            transition: all 0.2s;
        }

        .answer-input:focus {
            border-color: #f4b532;
            box-shadow: inset 0 3px 8px rgba(0,20,0,0.1), 0 5px 0 #f4b532, 0 0 15px #a9d68e;
            transform: translateY(-2px);
        }

        .check-btn {
            background: linear-gradient(145deg, #f4b43a, #e4a42a);
            border: none;
            border-radius: 70px;
            padding: 16px 38px;
            font-size: 1.3rem;
            font-weight: bold;
            color: #1f542f;
            cursor: pointer;
            box-shadow: 0 7px 0 #9c7127, 0 5px 15px rgba(0,30,0,0.3);
            transition: all 0.1s ease;
            border: 2px solid #daa545;
            letter-spacing: 1px;
        }

        .check-btn:active {
            transform: translateY(7px);
            box-shadow: 0 0px 0 #9c7127;
        }

        .explanation {
            background: linear-gradient(145deg, #f0fce8, #e0f0d8);
            border-left: 10px solid #f4b532;
            padding: 15px 20px;
            margin-top: 15px;
            border-radius: 40px;
            font-size: 1.1rem;
            color: #1d4a33;
            display: none;
            border: 2px solid #b1d4a1;
            box-shadow: 0 4px 0 #8fb08b;
        }

        .explanation.show {
            display: block;
            animation: slideDown 0.2s ease;
        }

        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .score-area {
            background: linear-gradient(145deg, #d8eac8, #c8daa8);
            padding: 20px 40px;
            border-radius: 70px;
            font-size: 1.9rem;
            font-weight: bold;
            color: #0f5a30;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 40px;
            border: 4px solid #4e8a5e;
            box-shadow: 0 12px 0 #3a6b44, 0 20px 30px -8px #1e4a1e;
        }

        .reset-btn {
            background: linear-gradient(145deg, #f4b43a, #e4a42a);
            border: none;
            border-radius: 70px;
            padding: 16px 45px;
            font-size: 1.5rem;
            font-weight: bold;
            color: #1b522c;
            cursor: pointer;
            box-shadow: 0 7px 0 #9c7127;
            transition: all 0.1s ease;
            border: 2px solid #e2ad42;
        }

        .reset-btn:active {
            transform: translateY(7px);
            box-shadow: 0 0px 0 #9c7127;
        }

        .footer {
            text-align: right;
            margin-top: 50px;
            color: #3a6a45;
            border-top: 4px solid #a6c89a;
            padding-top: 25px;
            font-size: 1.2rem;
            font-style: italic;
            background: linear-gradient(to left, #ffffffb0, transparent);
            padding: 20px 35px;
            border-radius: 70px;
        }

        .british-badge {
            display: inline-block;
            background: linear-gradient(145deg, #1f7042, #0f6032);
            color: white;
            padding: 10px 28px;
            border-radius: 60px;
            font-size: 1.2rem;
            margin-left: 20px;
            border: 3px solid #f4b532;
            box-shadow: 0 5px 0 #0f3a1f;
            text-shadow: 0 2px 2px rgba(0,0,0,0.2);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.02); }
            100% { transform: scale(1); }
        }

        /* Анимация для карточек при наведении */
        .voc-card:hover .voc-card-inner {
            box-shadow: 0 25px 35px -8px #0f4a0f;
        }

        /* Стили для скролла */
        ::-webkit-scrollbar {
            width: 12px;
        }

        ::-webkit-scrollbar-track {
            background: #d0e8c0;
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb {
            background: #4c9f70;
            border-radius: 10px;
            border: 2px solid #f4b532;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #3b7850;
        }

        /* Адаптивность */
        @media (max-width: 700px) {
            .tab-btn { font-size: 0.9rem; padding: 12px 5px; }
            h2 { font-size: 1.6rem; }
            .pages-content { padding: 20px; }
        }
    </style>
</head>
<body>
<div class="main-container">
    <div class="tabs-header">
        <button class="tab-btn active" onclick="switchTab('vocab')">🌿 VOCABULARY</button>
        <button class="tab-btn" onclick="switchTab('ppc')">⏳ P. PERFECT CONTINUOUS</button>
        <button class="tab-btn" onclick="switchTab('haveto')">⚡ HAVE TO</button>
        <button class="tab-btn" onclick="switchTab('phrasal')">🔤 PHRASAL (MAKE)</button>
        <button class="tab-btn" onclick="switchTab('tag')">❓ TAG QUESTIONS</button>
    </div>

    <div class="pages-content">
        <!-- Page 1: Vocabulary с идеальными карточками -->
        <div id="vocab-page" class="page active-page">
            <h2>🌱 MODULE 8 · ECO VOCABULARY <span class="british-badge">🇬🇧 BRITISH AUDIO</span></h2>
            <div class="rules-box">
                <h3>🌍 Как работать с карточками</h3>
                <p>• 🌿 <strong>Нажми на карточку</strong> — она плавно перевернётся, покажет перевод и картинку</p>
                <p>• 🔊 <strong>Нажми 🇬🇧</strong> — услышишь британское произношение (карточка не перевернётся)</p>
                <p>• 🌎 Попробуй вспомнить слово до переворота</p>
                <div class="example">
                    🌟 Все слова из твоего списка · 47 слов
                </div>
            </div>
            <div class="vocab-grid" id="vocab-container"></div>
            <p style="text-align:right; color:#3e6b45; font-size:1.2rem;">🌳 Нажми на карточку — она перевернётся! ✨</p>
        </div>

        <!-- Page 2: Present Perfect Continuous -->
        <div id="ppc-page" class="page">
            <h2>⏳ PRESENT PERFECT CONTINUOUS</h2>
            <div class="rules-box">
                <h3>📘 PRESENT PERFECT CONTINUOUS — правило</h3>
                <div class="example">
                    <p><span class="highlight">ФОРМУЛА:</span> <strong>have/has + been + глагол с -ing</strong></p>
                    <p>✅ <strong>Утверждение:</strong> I <u>have been waiting</u> for an hour. (Я жду уже час)</p>
                    <p>❌ <strong>Отрицание:</strong> She <u>hasn't been sleeping</u> well. (Она плохо спала)</p>
                    <p>❓ <strong>Вопрос:</strong> <u>Have you been working</u> all day? (Ты работал весь день?)</p>
                </div>
                <p><span class="highlight">КОГДА ИСПОЛЬЗУЕМ:</span></p>
                <ul>
                    <li><strong>Действие началось в прошлом и всё ещё продолжается</strong><br> <em>They <u>have been building</u> this house since 2020.</em></li>
                    <li><strong>Действие недавно закончилось, и виден результат</strong><br> <em>It <u>has been raining</u>. The ground is wet.</em></li>
                </ul>
                <p><span class="highlight">СЛОВА-ПОДСКАЗКИ:</span> for, since, all day, lately, recently</p>
            </div>
            <div class="exercise-block" id="ppc-container"></div>
            <div class="score-area">
                <span>🌿 Score: <span id="ppc-score">0</span>/17</span>
                <button class="reset-btn" onclick="resetExercise('ppc')">⟲ Reset</button>
            </div>
        </div>

        <!-- Page 3: Have to -->
        <div id="haveto-page" class="page">
            <h2>⚡ HAVE TO / HAS TO</h2>
            <div class="rules-box">
                <h3>📘 HAVE TO / HAS TO — обязанность</h3>
                <div class="example">
                    <p><span class="highlight">УТВЕРЖДЕНИЕ (обязанность):</span></p>
                    <p>• I/You/We/They <u>have to</u> recycle.</p>
                    <p>• He/She/It <u>has to</u> sort rubbish.</p>
                    <p><span class="highlight">ОТРИЦАНИЕ (нет обязанности):</span></p>
                    <p>• I/You/We/They <u>don't have to</u> pay.</p>
                    <p>• He/She/It <u>doesn't have to</u> go.</p>
                </div>
                <p><strong>💚 Запомни:</strong> "have to" = должен, "don't have to" = не нужно</p>
            </div>
            <div class="exercise-block" id="haveto-container"></div>
            <div class="score-area">
                <span>🌿 Score: <span id="haveto-score">0</span>/13</span>
                <button class="reset-btn" onclick="resetExercise('haveto')">⟲ Reset</button>
            </div>
        </div>

        <!-- Page 4: Phrasal verbs -->
        <div id="phrasal-page" class="page">
            <h2>🔤 PHRASAL VERBS (MAKE)</h2>
            <div class="rules-box">
                <h3>📘 ФРАЗОВЫЕ ГЛАГОЛЫ С MAKE</h3>
                <div class="example">
                    <p><span class="highlight">1. make up</span> = <strong>придумывать (историю, отговорку)</strong></p>
                    <p><em>He <u>made up</u> an excuse for being late.</em></p>
                    
                    <p><span class="highlight">2. make up with</span> = <strong>помириться с кем-то</strong></p>
                    <p><em>She <u>made up with</u> her brother after the fight.</em></p>
                    
                    <p><span class="highlight">3. make out</span> = <strong>разобрать, понять с трудом</strong></p>
                    <p><em>I can't <u>make out</u> his handwriting.</em></p>
                </div>
            </div>
            <div class="exercise-block" id="phrasal-container"></div>
            <div class="score-area">
                <span>🌿 Score: <span id="phrasal-score">0</span>/11</span>
                <button class="reset-btn" onclick="resetExercise('phrasal')">⟲ Reset</button>
            </div>
        </div>

        <!-- Page 5: Tag Questions -->
        <div id="tag-page" class="page">
            <h2>❓ TAG QUESTIONS</h2>
            <div class="rules-box">
                <h3>📘 РАЗДЕЛИТЕЛЬНЫЕ ВОПРОСЫ</h3>
                <div class="example">
                    <p><span class="highlight">ОСНОВНОЕ ПРАВИЛО:</span></p>
                    <p>✅ Утверждение → отрицательный хвостик: <em>It is beautiful, <u>isn't it?</u></em></p>
                    <p>❌ Отрицание → положительный хвостик: <em>They won't pollute, <u>will they?</u></em></p>
                </div>
                
                <p><span class="highlight">⚠️ СЛОВА С ОТРИЦАТЕЛЬНЫМ ЗНАЧЕНИЕМ:</span></p>
                <p><strong>never, hardly, seldom, rarely</strong> = отрицание → хвостик положительный:</p>
                <ul>
                    <li><em>She <u>never</u> recycles, <u>does she?</u></em></li>
                    <li><em>They <u>hardly</u> ever pollute, <u>do they?</u></em></li>
                </ul>
                
                <p><span class="highlight">ОСОБЫЕ СЛУЧАИ:</span></p>
                <ul>
                    <li><em>Let's go green, <u>shall we?</u></em></li>
                    <li><em>I'm right, <u>aren't I?</u></em></li>
                    <li><em>Close the window, <u>will you?</u></em></li>
                </ul>
            </div>
            <div class="exercise-block" id="tag-container"></div>
            <div class="score-area">
                <span>🌿 Score: <span id="tag-score">0</span>/14</span>
                <button class="reset-btn" onclick="resetExercise('tag')">⟲ Reset</button>
            </div>
        </div>
    </div>
</div>

<script>
    // Переключение вкладок
    function switchTab(tabName) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active-page'));
        document.querySelectorAll('.tab-btn').forEach(t => t.classList.remove('active'));
        document.getElementById(tabName + '-page').classList.add('active-page');
        event.target.classList.add('active');
    }

    // Британское произношение
    function speakBritish(text) {
        window.speechSynthesis.cancel();
        const utterance = new SpeechSynthesisUtterance(text);
        utterance.lang = 'en-GB';
        utterance.rate = 0.85;
        utterance.pitch = 1.0;
        
        const voices = window.speechSynthesis.getVoices();
        const preferredVoices = [
            'Google UK English Female',
            'Microsoft Hazel - English (United Kingdom)',
            'Samantha (en-GB)',
            'Kate (en-GB)',
            'Daniel (en-GB)'
        ];
        
        let selectedVoice = null;
        for (let preferred of preferredVoices) {
            selectedVoice = voices.find(voice => 
                voice.name.includes(preferred) && voice.lang.includes('GB')
            );
            if (selectedVoice) break;
        }
        
        if (!selectedVoice) {
            selectedVoice = voices.find(voice => voice.lang.includes('GB'));
        }
        
        if (selectedVoice) utterance.voice = selectedVoice;
        window.speechSynthesis.speak(utterance);
    }

    // Загрузка голосов
    window.speechSynthesis.onvoiceschanged = function() {};

    // ПОЛНЫЙ СПИСОК СЛОВ (47 слов)
    const vocabData = [
        { en: "a power station", ru: "электростанция", img: "🏭" },
        { en: "factory", ru: "фабрика", img: "🏭" },
        { en: "toxic fumes", ru: "токсичные испарения", img: "💨" },
        { en: "factory waste", ru: "фабричные отходы", img: "🏭" },
        { en: "acid rain", ru: "кислотный дождь", img: "☔" },
        { en: "polluted clouds", ru: "загрязненные облака", img: "☁️" },
        { en: "loss of natural habitats", ru: "потеря естественной среды обитания", img: "🌳" },
        { en: "air pollution", ru: "загрязнение воздуха", img: "💨" },
        { en: "water pollution", ru: "загрязнение воды", img: "💧" },
        { en: "soil pollution", ru: "загрязнение почвы", img: "🌱" },
        { en: "fish and plants species dying", ru: "гибель видов рыб и растений", img: "🐟" },
        { en: "burn", ru: "сжигать", img: "🔥" },
        { en: "emit", ru: "выбрасывать (в атмосферу)", img: "💨" },
        { en: "gathered", ru: "собранный", img: "📦" },
        { en: "oxygen", ru: "кислород", img: "💨" },
        { en: "atmosphere", ru: "атмосфера", img: "☁️" },
        { en: "land", ru: "приземляться", img: "🛬" },
        { en: "sleet", ru: "дождь со снегом", img: "🌨️" },
        { en: "wipe out", ru: "уничтожить", img: "💥" },
        { en: "poison", ru: "отравлять", img: "☠️" },
        { en: "reduce", ru: "сокращать", img: "📉" },
        { en: "harmful", ru: "вредный", img: "⚠️" },
        { en: "solar power", ru: "солнечная энергия", img: "☀️" },
        { en: "heat", ru: "тепло", img: "🔥" },
        { en: "plant flowers", ru: "сажать цветы", img: "🌷" },
        { en: "recycle cans", ru: "перерабатывать банки", img: "🥫" },
        { en: "collect rubbish", ru: "собирать мусор", img: "🗑️" },
        { en: "build nesting boxes", ru: "строить скворечники", img: "🏠" },
        { en: "teach the cycle of life", ru: "учить циклу жизни", img: "🔄" },
        { en: "clean out a pond", ru: "чистить пруд", img: "💧" },
        { en: "read a book about ecology", ru: "читать книгу об экологии", img: "📚" },
        { en: "a ladder", ru: "лестница", img: "🪜" },
        { en: "a hammer and nails", ru: "молоток и гвозди", img: "🔨" },
        { en: "a spade", ru: "лопата", img: "⛏️" },
        { en: "a watering can", ru: "лейка", img: "🚿" },
        { en: "a rake", ru: "грабли", img: "🪚" },
        { en: "a net", ru: "сачок", img: "🥅" },
        { en: "gardening gloves", ru: "садовые перчатки", img: "🧤" },
        { en: "a plastic bag", ru: "полиэтиленовый пакет", img: "🛍️" },
        { en: "leave/left", ru: "покидать/оставлять", img: "🚪" },
        { en: "woods", ru: "лес", img: "🌲" },
        { en: "tropical rainforest", ru: "тропический лес", img: "🌴" },
        { en: "desert", ru: "пустыня", img: "🏜️" },
        { en: "polar regions", ru: "полярные регионы", img: "❄️" },
        { en: "wetlands", ru: "водно-болотные угодья", img: "💧" },
        { en: "savannah", ru: "саванна", img: "🦁" },
        { en: "grassland", ru: "луга", img: "🌾" }
    ];

    // ОТРИСОВКА КАРТОЧЕК (с 3D-переворотом)
    const vocabContainer = document.getElementById('vocab-container');
    vocabData.forEach(item => {
        const card = document.createElement('div');
        card.className = 'voc-card';
        
        // Внутренний контейнер для 3D-эффекта
        const inner = document.createElement('div');
        inner.className = 'voc-card-inner';
        
        // Лицевая сторона
        const frontDiv = document.createElement('div');
        frontDiv.className = 'card-front';
        
        const wordText = document.createElement('div');
        wordText.className = 'word-text';
        wordText.textContent = item.en;
        
        const soundBtn = document.createElement('button');
        soundBtn.className = 'sound-icon';
        soundBtn.innerHTML = '🇬🇧';
        soundBtn.title = 'Слушать произношение';
        soundBtn.onclick = (e) => {
            e.stopPropagation(); // Останавливаем всплытие, чтобы карточка не переворачивалась
            speakBritish(item.en);
        };
        
        frontDiv.appendChild(wordText);
        frontDiv.appendChild(soundBtn);
        
        // Обратная сторона
        const backDiv = document.createElement('div');
        backDiv.className = 'card-back';
        
        const imgDiv = document.createElement('div');
        imgDiv.className = 'word-image';
        imgDiv.textContent = item.img;
        
        const translationText = document.createElement('div');
        translationText.className = 'translation-text';
        translationText.textContent = item.ru;
        
        const wordEnText = document.createElement('div');
        wordEnText.className = 'word-text';
        wordEnText.style.fontSize = '1.2rem';
        wordEnText.textContent = item.en;
        
        const soundBtnBack = document.createElement('button');
        soundBtnBack.className = 'sound-icon';
        soundBtnBack.innerHTML = '🇬🇧';
        soundBtnBack.style.marginTop = '5px';
        soundBtnBack.onclick = (e) => {
            e.stopPropagation(); // Останавливаем всплытие
            speakBritish(item.en);
        };
        
        backDiv.appendChild(imgDiv);
        backDiv.appendChild(translationText);
        backDiv.appendChild(wordEnText);
        backDiv.appendChild(soundBtnBack);
        
        inner.appendChild(frontDiv);
        inner.appendChild(backDiv);
        card.appendChild(inner);
        
        // Клик по карточке для переворота (только если не по кнопке)
        card.addEventListener('click', function(e) {
            // Если кликнули по кнопке звука или её родителю - не переворачиваем
            if (e.target.classList.contains('sound-icon') || e.target.closest('.sound-icon')) {
                return;
            }
            this.classList.toggle('revealed');
        });
        
        vocabContainer.appendChild(card);
    });

    // Данные упражнений
    const exercises = {
        ppc: [
            { type: 'mc', question: "The Earth ______ (get) warmer for many years.", options: ["has been getting", "have been getting", "has got"], correct: "has been getting", explanation: "✅ 'The Earth' is singular → 'has been getting'." },
            { type: 'mc', question: "Scientists ______ (study) climate change since 1990.", options: ["have been studying", "has been studying", "are studying"], correct: "have been studying", explanation: "✅ 'Scientists' is plural → 'have been studying'." },
            { type: 'mc', question: "She ______ (work) at the recycling centre all day.", options: ["has been working", "have been working", "is working"], correct: "has been working", explanation: "✅ 'She' → 'has been working'." },
            { type: 'mc', question: "______ he ______ (work) on the project long?", options: ["Has / been working", "Have / been working", "Is / working"], correct: "Has / been working", explanation: "✅ Question with 'he' → 'Has he been working?'" },
            { type: 'mc', question: "The children ______ (not/sleep) well lately.", options: ["haven't been sleeping", "hasn't been sleeping", "aren't sleeping"], correct: "haven't been sleeping", explanation: "✅ Plural → 'haven't been sleeping'." },
            { type: 'mc', question: "How long ______ you ______ (learn) English?", options: ["have / been learning", "has / been learning", "are / learning"], correct: "have / been learning", explanation: "✅ Question with 'you' → 'have you been learning?'" },
            { type: 'mc', question: "She ______ (not/feel) well recently.", options: ["hasn't been feeling", "haven't been feeling", "isn't feeling"], correct: "hasn't been feeling", explanation: "✅ 'She' negative → 'hasn't been feeling'." },
            { type: 'write', question: "I ________ (wait) for you since 2 o'clock.", correct: "have been waiting", explanation: "✅ 'I' → 'have been waiting'." },
            { type: 'write', question: "________ you ________ (watch) TV all morning?", correct: "Have you been watching", explanation: "✅ Question: 'Have you been watching'?" },
            { type: 'write', question: "It ________ (rain) for hours. That's why the streets are wet.", correct: "has been raining", explanation: "✅ 'It' → 'has been raining'." },
            { type: 'write', question: "They ________ (build) this school for two years.", correct: "have been building", explanation: "✅ 'They' → 'have been building'." },
            { type: 'write', question: "He ________ (not/study) enough, so he's tired.", correct: "hasn't been studying", explanation: "✅ 'He' negative → 'hasn't been studying'." }
        ],
        haveto: [
            { type: 'mc', question: "You ______ recycle paper. It's the law.", options: ["have to", "has to", "don't have to"], correct: "have to", explanation: "✅ 'You' → 'have to' (obligation)." },
            { type: 'mc', question: "She ______ sort the rubbish every day.", options: ["has to", "have to", "doesn't have to"], correct: "has to", explanation: "✅ 'She' → 'has to'." },
            { type: 'mc', question: "We ______ use plastic bags – we can use reusable ones.", options: ["don't have to", "doesn't have to", "have to"], correct: "don't have to", explanation: "✅ 'We' → 'don't have to' (no obligation)." },
            { type: 'mc', question: "He ______ go to the eco-club if he doesn't want.", options: ["doesn't have to", "don't have to", "has to"], correct: "doesn't have to", explanation: "✅ 'He' → 'doesn't have to'." },
            { type: 'mc', question: "I ______ turn off the lights before leaving.", options: ["have to", "has to", "don't have to"], correct: "have to", explanation: "✅ 'I' → 'have to'." },
            { type: 'mc', question: "They ______ wear a uniform at the recycling plant.", options: ["have to", "has to", "doesn't have to"], correct: "have to", explanation: "✅ 'They' → 'have to'." },
            { type: 'mc', question: "My brother ______ take the glass bottles to the bin.", options: ["has to", "have to", "don't have to"], correct: "has to", explanation: "✅ 'My brother' (he) → 'has to'." },
            { type: 'mc', question: "You ______ buy a new notebook – use the old one.", options: ["don't have to", "doesn't have to", "have to"], correct: "don't have to", explanation: "✅ 'You' → 'don't have to'." },
            { type: 'write', question: "I ________ (wear) a uniform at work. It's the rule.", correct: "have to wear", explanation: "✅ 'I' → 'have to wear'." },
            { type: 'write', question: "She ________ (go) to school on Saturdays. It's closed.", correct: "doesn't have to go", explanation: "✅ 'She' → 'doesn't have to go'." },
            { type: 'write', question: "We ________ (recycle) glass bottles. It's the law here.", correct: "have to recycle", explanation: "✅ 'We' → 'have to recycle'." },
            { type: 'write', question: "He ________ (work) today. It's his day off.", correct: "doesn't have to work", explanation: "✅ 'He' → 'doesn't have to work'." },
            { type: 'write', question: "You ________ (pay) for plastic bags in some shops.", correct: "have to pay", explanation: "✅ 'You' → 'have to pay'." }
        ],
        phrasal: [
            { type: 'mc', question: "He ________ an excuse for being late.", options: ["made up", "made up with", "made out"], correct: "made up", explanation: "✅ 'made up' = придумал." },
            { type: 'mc', question: "She finally ________ her brother after the fight.", options: ["made up with", "made up", "made out"], correct: "made up with", explanation: "✅ 'made up with' = помирилась с." },
            { type: 'mc', question: "I can't ________ what he's saying.", options: ["make out", "make up", "make up with"], correct: "make out", explanation: "✅ 'make out' = разобрать." },
            { type: 'mc', question: "He always ________ interesting stories.", options: ["makes up", "makes out", "makes up with"], correct: "makes up", explanation: "✅ 'makes up' = придумывает." },
            { type: 'mc', question: "I couldn't ________ his handwriting.", options: ["make out", "make up", "make up with"], correct: "make out", explanation: "✅ 'make out' = разобрать." },
            { type: 'mc', question: "Kate decided to ________ Tom.", options: ["make up with", "make up", "make out"], correct: "make up with", explanation: "✅ 'make up with' = помириться с." },
            { type: 'write', question: "They will ________ soon.", correct: "make up", explanation: "✅ 'make up' = помирятся." },
            { type: 'write', question: "I can't ________ the address.", correct: "make out", explanation: "✅ 'make out' = разобрать." },
            { type: 'write', question: "She ________ an excuse.", correct: "made up", explanation: "✅ 'made up' = придумала." },
            { type: 'write', question: "He ________ his best friend.", correct: "made up with", explanation: "✅ 'made up with' = помирился с." },
            { type: 'write', question: "Can you ________ what he's saying?", correct: "make out", explanation: "✅ 'make out' = разобрать." }
        ],
        tag: [
            { type: 'mc', question: "It's a beautiful day, ______?", options: ["isn't it", "is it", "doesn't it"], correct: "isn't it", explanation: "✅ Positive → negative tag." },
            { type: 'mc', question: "You recycle paper, ______?", options: ["don't you", "do you", "aren't you"], correct: "don't you", explanation: "✅ Present simple → 'don't you?'" },
            { type: 'mc', question: "They won't pollute, ______?", options: ["will they", "won't they", "do they"], correct: "will they", explanation: "✅ Negative → positive tag." },
            { type: 'mc', question: "She never recycles, ______?", options: ["does she", "doesn't she", "is she"], correct: "does she", explanation: "✅ 'never' = отрицание → положительный хвостик." },
            { type: 'mc', question: "Let's protect nature, ______?", options: ["shall we", "will you", "don't we"], correct: "shall we", explanation: "✅ 'Let's' → 'shall we?'" },
            { type: 'mc', question: "Close the window, ______?", options: ["will you", "do you", "isn't it"], correct: "will you", explanation: "✅ Imperative → 'will you?'" },
            { type: 'mc', question: "There are many organisations, ______?", options: ["aren't there", "are there", "isn't there"], correct: "aren't there", explanation: "✅ 'There are' → 'aren't there?'" },
            { type: 'mc', question: "I'm right, ______?", options: ["aren't I", "am I", "amn't I"], correct: "aren't I", explanation: "✅ 'I am' → 'aren't I?'" },
            { type: 'mc', question: "She hardly ever pollutes, ______?", options: ["does she", "doesn't she", "is she"], correct: "does she", explanation: "✅ 'hardly' = отрицание → положительный хвостик." },
            { type: 'write', question: "You like recycling, ________?", correct: "don't you", explanation: "✅ Present simple → 'don't you?'" },
            { type: 'write', question: "He hasn't finished, ________?", correct: "has he", explanation: "✅ Отрицание → положительный хвостик." },
            { type: 'write', question: "Let's go green, ________?", correct: "shall we", explanation: "✅ 'Let's' → 'shall we?'" },
            { type: 'write', question: "I'm right, ________?", correct: "aren't I", explanation: "✅ 'I am' → 'aren't I?'" },
            { type: 'write', question: "They never throw rubbish, ________?", correct: "do they", explanation: "✅ 'never' = отрицание → 'do they?'" }
        ]
    };

    // Отрисовка упражнений
    function renderExercise(type) {
        const container = document.getElementById(type + '-container');
        if (!container) return;
        
        let html = '';
        exercises[type].forEach((ex, index) => {
            html += `<div class="question-item" id="${type}-q${index}">`;
            html += `<div class="question-text">${index+1}. ${ex.question}</div>`;
            
            if (ex.type === 'mc') {
                html += `<div class="options">`;
                ex.options.forEach(opt => {
                    html += `<button class="option-btn" onclick="checkMC('${type}', ${index}, '${opt}')">${opt}</button>`;
                });
                html += `</div>`;
            } else {
                html += `<div class="write-answer">`;
                html += `<input type="text" class="answer-input" id="${type}-input${index}" placeholder="Type your answer" autocomplete="off">`;
                html += `<button class="check-btn" onclick="checkWrite('${type}', ${index})">Check</button>`;
                html += `</div>`;
            }
            
            html += `<div class="explanation" id="${type}-exp${index}">${ex.explanation}</div>`;
            html += `</div>`;
        });
        container.innerHTML = html;
        updateScore(type);
    }

    // Проверка множественного выбора
    window.checkMC = function(type, qIndex, selected) {
        const question = exercises[type][qIndex];
        const buttons = document.querySelectorAll(`#${type}-q${qIndex} .option-btn`);
        const explanation = document.getElementById(`${type}-exp${qIndex}`);
        
        buttons.forEach(btn => {
            btn.disabled = true;
            if (btn.textContent === question.correct) {
                btn.classList.add('correct');
            } else if (btn.textContent === selected) {
                btn.classList.add('wrong');
            }
        });
        
        explanation.classList.add('show');
        updateScore(type);
    };

    // Проверка письменного ответа
    window.checkWrite = function(type, qIndex) {
        const question = exercises[type][qIndex];
        const input = document.getElementById(`${type}-input${qIndex}`);
        const explanation = document.getElementById(`${type}-exp${qIndex}`);
        const userAnswer = input.value.trim().toLowerCase();
        const correctAnswer = question.correct.toLowerCase();
        
        input.disabled = true;
        
        if (userAnswer === correctAnswer) {
            input.style.backgroundColor = '#d4edda';
            input.style.border = '3px solid #28a745';
        } else {
            input.style.backgroundColor = '#f8d7da';
            input.style.border = '3px solid #dc3545';
            explanation.innerHTML = question.explanation + `<br><span style="color:#c00;">Correct answer: "${question.correct}"</span>`;
        }
        
        explanation.classList.add('show');
        updateScore(type);
    };

    // Обновление счета
    function updateScore(type) {
        let score = 0;
        exercises[type].forEach((ex, index) => {
            if (ex.type === 'mc') {
                const buttons = document.querySelectorAll(`#${type}-q${index} .option-btn`);
                buttons.forEach(btn => {
                    if (btn.classList.contains('correct')) score++;
                });
            } else {
                const input = document.getElementById(`${type}-input${index}`);
                if (input && input.disabled) {
                    const question = exercises[type][index];
                    if (input.value.trim().toLowerCase() === question.correct.toLowerCase()) {
                        score++;
                    }
                }
            }
        });
        document.getElementById(`${type}-score`).textContent = score;
    }

    // Сброс упражнения
    window.resetExercise = function(type) {
        exercises[type].forEach((ex, index) => {
            if (ex.type === 'mc') {
                const buttons = document.querySelectorAll(`#${type}-q${index} .option-btn`);
                buttons.forEach(btn => {
                    btn.disabled = false;
                    btn.classList.remove('correct', 'wrong');
                });
            } else {
                const input = document.getElementById(`${type}-input${index}`);
                if (input) {
                    input.disabled = false;
                    input.value = '';
                    input.style.backgroundColor = '';
                    input.style.border = '3px solid #7d9f72';
                }
            }
            const explanation = document.getElementById(`${type}-exp${index}`);
            if (explanation) {
                explanation.innerHTML = exercises[type][index].explanation;
                explanation.classList.remove('show');
            }
        });
        updateScore(type);
    };

    // Инициализация
    renderExercise('ppc');
    renderExercise('haveto');
    renderExercise('phrasal');
    renderExercise('tag');
</script>
</body>
</html>
