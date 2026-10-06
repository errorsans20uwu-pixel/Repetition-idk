<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Tutor Hub — Обучение программированию и IT-разработке</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #0b0f19;
            --card-bg: rgba(22, 28, 45, 0.7);
            --card-border: rgba(255, 255, 255, 0.08);
            --primary-gradient: linear-gradient(135deg, #6366f1 0%, #a855f7 100%);
            --accent-glow: rgba(99, 102, 241, 0.35);
            --text-main: #f3f4f6;
            --text-muted: #9ca3af;
            --accent-purple: #a855f7;
            --accent-blue: #6366f1;
            --radius-lg: 16px;
            --radius-md: 10px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
        }
        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 15% 15%, rgba(99, 102, 241, 0.12) 0%, transparent 40%),
                radial-gradient(circle at 85% 65%, rgba(168, 85, 247, 0.12) 0%, transparent 40%);
            background-attachment: fixed;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }
        /* HEADER */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(11, 15, 25, 0.8);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--card-border);
        }
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 80px;
        }
        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        nav ul {
            display: flex;
            list-style: none;
            gap: 32px;
        }
        nav a {
            color: var(--text-muted);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            transition: var(--transition);
        }
        nav a:hover {
            color: var(--text-main);
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
        }
        .nav-btn {
            background: var(--primary-gradient);
            color: #fff !important;
            padding: 10px 20px;
            border-radius: 30px;
            box-shadow: 0 4px 15px var(--accent-glow);
        }
        .nav-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(168, 85, 247, 0.4);
        }
        /* HERO SECTION */
        .hero {
            padding: 180px 0 100px;
            text-align: center;
            position: relative;
        }
        .hero::before {
            content: '';
            position: absolute;
            top: 30%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 300px;
            height: 300px;
            background: var(--primary-gradient);
            filter: blur(140px);
            opacity: 0.4;
            z-index: -1;
            border-radius: 50%;
        }
        .hero-badge {
            display: inline-block;
            padding: 6px 16px;
            background: rgba(99, 102, 241, 0.1);
            border: 1px solid rgba(99, 102, 241, 0.3);
            border-radius: 20px;
            font-size: 0.85rem;
            color: #818cf8;
            margin-bottom: 24px;
            font-weight: 600;
        }
        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.15;
            margin-bottom: 24px;
            letter-spacing: -0.02em;
        }
        .hero h1 span {
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
            max-width: 650px;
            margin: 0 auto 40px;
        }
        .btn-primary {
            display: inline-block;
            background: var(--primary-gradient);
            color: #fff;
            padding: 16px 36px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 1.05rem;
            text-decoration: none;
            border: none;
            cursor: pointer;
            box-shadow: 0 8px 25px var(--accent-glow);
            transition: var(--transition);
        }
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(168, 85, 247, 0.5);
        }
        /* SECTION COMMON */
        section {
            padding: 90px 0;
        }
        .section-title {
            text-align: center;
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 16px;
        }
        .section-subtitle {
            text-align: center;
            color: var(--text-muted);
            margin-bottom: 50px;
            font-size: 1rem;
        }
        /* ABOUT SECTION */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }
        .about-card {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: var(--radius-lg);
            padding: 40px;
            backdrop-filter: blur(10px);
        }
        .about-card h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #fff;
        }
        .about-card p {
            color: var(--text-muted);
            margin-bottom: 24px;
        }
        .skills-list {
            list-style: none;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 30px;
        }
        .skills-list li {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--card-border);
            padding: 6px 14px;
            border-radius: 8px;
            font-size: 0.85rem;
            color: #d1d5db;
        }
        .contacts-info {
            display: flex;
            flex-direction: column;
            gap: 12px;
            border-top: 1px solid var(--card-border);
            padding-top: 20px;
        }
        .contact-item {
            display: flex;
            align-items: center;
            gap: 12px;
            color: var(--text-main);
            text-decoration: none;
            font-size: 0.95rem;
        }
        .contact-item span {
            color: var(--accent-purple);
        }
        /* REVIEWS SECTION */
        .reviews-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 24px;
        }
        .review-card {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: var(--radius-lg);
            padding: 28px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: var(--transition);
        }
        .review-card:hover {
            transform: translateY(-5px);
            border-color: rgba(99, 102, 241, 0.4);
        }
        .review-text {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 20px;
            font-style: italic;
        }
        .author-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        .avatar {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background: var(--primary-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            color: #fff;
        }
        .author-details h4 {
            font-size: 0.95rem;
            color: #fff;
        }
        .author-details p {
            font-size: 0.8rem;
            color: var(--text-muted);
        }
        /* CHATBOT SECTION */
        .chat-container {
            max-width: 700px;
            margin: 0 auto;
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: var(--radius-lg);
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
        }
        .chat-header {
            background: rgba(255, 255, 255, 0.03);
            padding: 16px 24px;
            border-bottom: 1px solid var(--card-border);
            display: flex;
            align-items: center;
            gap: 12px;
        }
        .status-dot {
            width: 10px;
            height: 10px;
            background: #10b981;
            border-radius: 50%;
            box-shadow: 0 0 8px #10b981;
        }
        .chat-messages {
            height: 320px;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 14px;
        }
        .message {
            max-width: 80%;
            padding: 12px 18px;
            border-radius: 18px;
            font-size: 0.9rem;
            line-height: 1.4;
        }
        .bot-message {
            background: rgba(255, 255, 255, 0.08);
            align-self: flex-start;
            border-bottom-left-radius: 4px;
            color: var(--text-main);
        }
        .user-message {
            background: var(--primary-gradient);
            align-self: flex-end;
            border-bottom-right-radius: 4px;
            color: #fff;
        }
        .chat-input-area {
            display: flex;
            padding: 14px;
            border-top: 1px solid var(--card-border);
            background: rgba(0, 0, 0, 0.2);
            gap: 10px;
        }
        .chat-input-area input {
            flex: 1;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--card-border);
            border-radius: 20px;
            padding: 10px 18px;
            color: #fff;
            outline: none;
            transition: var(--transition);
        }
        .chat-input-area input:focus {
            border-color: var(--accent-blue);
        }
        .chat-send-btn {
            background: var(--primary-gradient);
            border: none;
            color: #fff;
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
        }
        .chat-send-btn:hover {
            opacity: 0.9;
        }
        /* REGISTRATION FORM */
        .form-container {
            max-width: 550px;
            margin: 0 auto;
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: var(--radius-lg);
            padding: 40px;
            position: relative;
        }
        .form-group {
            margin-bottom: 20px;
        }
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 500;
        }
        .form-group input, .form-group select {
            width: 100%;
            background: rgba(255, 255, 255, 0.04);
            border: 1px solid var(--card-border);
            border-radius: var(--radius-md);
            padding: 12px 16px;
            color: #fff;
            outline: none;
            font-size: 0.95rem;
            transition: var(--transition);
        }
        .form-group input:focus, .form-group select:focus {
            border-color: var(--accent-purple);
            box-shadow: 0 0 10px rgba(168, 85, 247, 0.2);
        }
        .form-group select option {
            background-color: #111827;
            color: #fff;
        }
        .submit-btn {
            width: 100%;
            margin-top: 10px;
        }
        .notification {
            display: none;
            background: rgba(16, 185, 129, 0.15);
            border: 1px solid #10b981;
            color: #34d399;
            padding: 14px;
            border-radius: var(--radius-md);
            text-align: center;
            margin-top: 20px;
            font-size: 0.9rem;
        }
        /* FOOTER */
        footer {
            border-top: 1px solid var(--card-border);
            padding: 40px 0;
            text-align: center;
            color: var(--text-muted);
            font-size: 0.85rem;
            background: rgba(5, 8, 15, 0.9);
        }
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 16px;
        }
        .footer-links a {
            color: var(--text-muted);
            text-decoration: none;
            transition: var(--transition);
        }
        .footer-links a:hover {
            color: var(--accent-purple);
        }
        /* MOBILE RESPONSIVE */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                justify-content: center;
                gap: 12px;
                height: auto;
                padding: 16px 0;
            }
            nav ul {
                gap: 16px;
                font-size: 0.85rem;
            }
            .hero {
                padding: 140px 0 60px;
            }
            .hero h1 {
                font-size: 2.2rem;
            }
            .about-grid {
                grid-template-columns: 1fr;
            }
            .form-container {
                padding: 24px;
            }
        }
    </style>
</head>
<body>
    <!-- HEADER -->
    <header>
        <div class="container header-content">
            <a href="#" class="logo">⚡ IT Tutor Hub</a>
            <nav>
                <ul>
                    <li><a href="#about">Обо мне</a></li>
                    <li><a href="#reviews">Отзывы</a></li>
                    <li><a href="#chatbot">Чат-бот</a></li>
                    <li><a href="#register" class="nav-btn">Записаться</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- HERO SECTION -->
    <section class="hero">
        <div class="container">
            <span class="hero-badge">🚀 Твой быстрый старт в IT</span>
            <h1>Обучение программированию<br>и <span>IT-разработке</span></h1>
            <p>Индивидуальные онлайн-занятия, менторство, поддержка на всех этапах: от написания первой строчки кода до прохождения собеседования.</p>
            <a href="#register" class="btn-primary">Записаться на занятие</a>
        </div>
    </section>

    <!-- ABOUT SECTION -->
    <section id="about">
        <div class="container">
            <h2 class="section-title">Обо мне</h2>
            <p class="section-subtitle">Практикующий разработчик и опытный преподаватель</p>
            
            <div class="about-grid">
                <div class="about-card">
                    <h3>Привет! Я твой IT-ментор</h3>
                    <p>Помогаю освоить современные технологии веб-разработки с нуля, систематизировать знания и подготовить портфолио из реальных проектов.</p>
                    <ul class="skills-list">
                        <li>HTML5 & CSS3</li>
                        <li>JavaScript (ES6+)</li>
                        <li>React / Vue.js</li>
                        <li>Git & GitHub</li>
                        <li>Разбор кода</li>
                        <li>Помощь с домашкой</li>
                    </ul>
                </div>
                <div class="about-card">
                    <h3>Контакты для связи</h3>
                    <p>Есть вопросы по обучению или формату? Свяжись со мной напрямую любым удобным способом:</p>
                    <div class="contacts-info">
                        <a href="tel:+79990001234" class="contact-item">
                            <span>📞</span> +7 (999) 000-12-34
                        </a>
                        <a href="mailto:tutor.demo.fake@example.com" class="contact-item">
                            <span>✉️</span> tutor.demo.fake@example.com
                        </a>
                        <div class="contact-item">
                            <span>📍</span> Онлайн (Zoom, Telegram, Discord)
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- REVIEWS SECTION -->
    <section id="reviews">
        <div class="container">
            <h2 class="section-title">Отзывы учеников</h2>
            <p class="section-subtitle">Истории успеха тех, кто уже сделал шаг в IT</p>
            <div class="reviews-grid">
                <div class="review-card">
                    <p class="review-text">«Благодаря занятиям смог с нуля разобраться в JS и собрать свой первый pet-проект. Объяснения очень понятные, без лишней "воды".»</p>
                    <div class="author-info">
                        <div class="avatar">АМ</div>
                        <div class="author-details">
                            <h4>Алексей Михайлов</h4>
                            <p>Junior Frontend Разработчик</p>
                        </div>
                    </div>
                </div>
                <div class="review-card">
                    <p class="review-text">«Отличный подход! Преподаватель помог подготовиться к техническому собеседованию и разобрать сложные темы по асинхронности.»</p>
                    <div class="author-info">
                        <div class="avatar">ЕК</div>
                        <div class="author-details">
                            <h4>Елена Ковалева</h4>
                            <p>Студентка курса</p>
                        </div>
                    </div>
                </div>
                <div class="review-card">
                    <p class="review-text">«Занимаемся уже 3 месяца. Очень нравится, что упор делается на реальную практику и написание чистого кода. Рекомендую!»</p>
                    <div class="author-info">
                        <div class="avatar">ДC</div>
                        <div class="author-details">
                            <h4>Дмитрий Сергеев</h4>
                            <p>Сменил профессию на IT</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CHATBOT SECTION -->
    <section id="chatbot">
        <div class="container">
            <h2 class="section-title">Интерактивный консультант</h2>
            <p class="section-subtitle">Задайте вопрос боту и узнайте подробности об обучении</p>
            <div class="chat-container">
                <div class="chat-header">
                    <div class="status-dot"></div>
                    <strong>TutorAssistant Bot</strong>
                </div>
                <div class="chat-messages" id="chatMessages">
                    <div class="message bot-message">
                        Привет! 👋 Я онлайн-помощ
