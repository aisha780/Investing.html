<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InvestIQ - Образовательная платформа по инвестированию</title>
    <style>
        :root {
            --primary: #2E5BFF;
            --secondary: #8C54FF;
            --accent: #00C6FF;
            --light: #F5F7FF;
            --dark: #2E384D;
            --success: #36B37E;
            --warning: #FFAB00;
            --danger: #FF5630;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 30px;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        .user-profile {
            display: flex;
            align-items: center;
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
        }
        
        .hero {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 80px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 20px;
            max-width: 700px;
            margin: 0 auto 30px;
        }
        
        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: white;
            color: var(--primary);
            border: none;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .btn-primary {
            background-color: var(--accent);
            color: white;
        }
        
        .section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 36px;
            color: var(--dark);
            margin-bottom: 15px;
        }
        
        .section-title p {
            color: #666;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background-color: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
        }
        
        .feature-icon {
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
        }
        
        .feature-icon i {
            color: white;
            font-size: 30px;
        }
        
        .feature-card h3 {
            margin-bottom: 15px;
            font-size: 22px;
        }
        
        .quiz-container {
            background-color: white;
            border-radius: 10px;
            padding: 40px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            max-width: 800px;
            margin: 0 auto;
        }
        
        .quiz-progress {
            height: 8px;
            background-color: #eee;
            border-radius: 4px;
            margin-bottom: 30px;
            overflow: hidden;
        }
        
        .quiz-progress-bar {
            height: 100%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            width: 30%;
        }
        
        .quiz-question {
            font-size: 24px;
            margin-bottom: 30px;
        }
        
        .quiz-options {
            display: grid;
            gap: 15px;
            margin-bottom: 30px;
        }
        
        .quiz-option {
            padding: 15px 20px;
            background-color: var(--light);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .quiz-option:hover {
            background-color: #e6e9ff;
        }
        
        .quiz-option.selected {
            background-color: var(--primary);
            color: white;
        }
        
        .quiz-navigation {
            display: flex;
            justify-content: space-between;
        }
        
        .dashboard {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
        }
        
        .dashboard-card {
            background-color: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .dashboard-card h3 {
            margin-bottom: 20px;
            font-size: 22px;
        }
        
        .progress-item {
            margin-bottom: 20px;
        }
        
        .progress-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }
        
        .progress-bar {
            height: 8px;
            background-color: #eee;
            border-radius: 4px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
        }
        
        .portfolio-value {
            font-size: 32px;
            font-weight: 700;
            margin: 20px 0;
            color: var(--primary);
        }
        
        .portfolio-change {
            color: var(--success);
            font-weight: 600;
        }
        
        .portfolio-assets {
            margin-top: 30px;
        }
        
        .asset {
            display: flex;
            justify-content: space-between;
            padding: 15px 0;
            border-bottom: 1px solid #eee;
        }
        
        .asset:last-child {
            border-bottom: none;
        }
        
        .leaderboard {
            margin-top: 30px;
        }
        
        .leaderboard-item {
            display: flex;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid #eee;
        }
        
        .leaderboard-position {
            width: 30px;
            height: 30px;
            background-color: var(--light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            font-weight: 600;
        }
        
        .leaderboard-item.current-user {
            background-color: #e6e9ff;
            margin: 0 -30px;
            padding: 15px 30px;
            border-radius: 8px;
        }
        
        .leaderboard-name {
            flex-grow: 1;
        }
        
        .leaderboard-score {
            font-weight: 600;
            color: var(--primary);
        }
        
        .hidden {
            display: none;
        }
        
        footer {
            background-color: var(--dark);
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .footer-column h4 {
            margin-bottom: 20px;
            font-size: 18px;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #aaa;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid #444;
            color: #aaa;
            font-size: 14px;
        }
        
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
            }
            
            .nav-links {
                margin-top: 20px;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .dashboard {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">InvestIQ</div>
                <ul class="nav-links">
                    <li><a href="#" class="active">Главная</a></li>
                    <li><a href="#">Обучение</a></li>
                    <li><a href="#">Портфель</a></li>
                    <li><a href="#">Рейтинги</a></li>
                    <li><a href="#">О нас</a></li>
                </ul>
                <div class="user-profile">
                    <div class="user-avatar">ИИ</div>
                    <span>Иван Инвесторов</span>
                </div>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h1>Стань успешным инвестором</h1>
            <p>Пройдите тестирование, получите индивидуальную программу обучения и практикуйтесь на виртуальном инвестиционном портфеле без риска</p>
            <a href="#" class="btn btn-primary" id="startQuizBtn">Начать тестирование</a>
        </div>
    </section>

    <section class="section" id="quizSection" style="display: none;">
        <div class="container">
            <div class="quiz-container">
                <div class="quiz-progress">
                    <div class="quiz-progress-bar"></div>
                </div>
                <div class="quiz-question">Какой из перечисленных активов обычно считается наименее рискованным для инвестиций?</div>
                <div class="quiz-options">
                    <div class="quiz-option">Акции технологических компаний</div>
                    <div class="quiz-option">Криптовалюты</div>
                    <div class="quiz-option">Государственные облигации</div>
                    <div class="quiz-option">Недвижимость в развивающихся странах</div>
                </div>
                <div class="quiz-navigation">
                    <button class="btn" id="prevQuestionBtn">Назад</button>
                    <button class="btn btn-primary" id="nextQuestionBtn">Далее</button>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="featuresSection">
        <div class="container">
            <div class="section-title">
                <h2>Как работает платформа</h2>
                <p>Мы предлагаем комплексный подход к обучению инвестированию</p>
            </div>
            <div class="features">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i>?</i>
                    </div>
                    <h3>Тестирование уровня</h3>
                    <p>Определите ваш текущий уровень знаний в области инвестирования с помощью нашего теста</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i>📚</i>
                    </div>
                    <h3>Индивидуальная программа</h3>
                    <p>Получите персонализированный план обучения на основе результатов тестирования</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i>🎮</i>
                    </div>
                    <h3>Игровые задания</h3>
                    <p>Закрепляйте знания через интерактивные задания, викторины и симуляции</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i>📈</i>
                    </div>
                    <h3>Виртуальный портфель</h3>
                    <p>Практикуйтесь в инвестировании с игровыми деньгами без финансового риска</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i>🏆</i>
                    </div>
                    <h3>Система рейтингов</h3>
                    <p>Сравнивайте свои достижения с другими участниками и отслеживайте прогресс</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i>👨‍🏫</i>
                    </div>
                    <h3>Экспертная поддержка</h3>
                    <p>Получайте обратную связь от опытных инвесторов и финансовых консультантов</p>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="dashboardSection" style="display: none;">
        <div class="container">
            <div class="section-title">
                <h2>Ваш учебный кабинет</h2>
                <p>Здесь вы можете отслеживать свой прогресс и управлять обучением</p>
            </div>
            <div class="dashboard">
                <div class="dashboard-left">
                    <div class="dashboard-card">
                        <h3>Прогресс обучения</h3>
                        <div class="progress-item">
                            <div class="progress-label">
                                <span>Основы инвестирования</span>
                                <span>75%</span>
                            </div>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 75%"></div>
                            </div>
                        </div>
                        <div class="progress-item">
                            <div class="progress-label">
                                <span>Анализ рынка</span>
                                <span>40%</span>
                            </div>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 40%"></div>
                            </div>
                        </div>
                        <div class="progress-item">
                            <div class="progress-label">
                                <span>Портфельные стратегии</span>
                                <span>15%</span>
                            </div>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 15%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="dashboard-card">
                        <h3>Игровой инвестиционный портфель</h3>
                        <div class="portfolio-value">1 250 000 ₽</div>
                        <div class="portfolio-change">+5.2% за месяц</div>
                        <div class="portfolio-assets">
                            <div class="asset">
                                <span>Акции Сбербанка</span>
                                <span>+3.4%</span>
                            </div>
                            <div class="asset">
                                <span>Облигации ОФЗ</span>
                                <span>+1.2%</span>
                            </div>
                            <div class="asset">
                                <span>ETF на американские акции</span>
                                <span>+7.8%</span>
                            </div>
                            <div class="asset">
                                <span>Золото</span>
                                <span>-0.5%</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="dashboard-right">
                    <div class="dashboard-card">
                        <h3>Рейтинг участников</h3>
                        <div class="leaderboard">
                            <div class="leaderboard-item">
                                <div class="leaderboard-position">1</div>
                                <div class="leaderboard-name">Алексей Финансов</div>
                                <div class="leaderboard-score">9850</div>
                            </div>
                            <div class="leaderboard-item">
                                <div class="leaderboard-position">2</div>
                                <div class="leaderboard-name">Мария Инвест</div>
                                <div class="leaderboard-score">9320</div>
                            </div>
                            <div class="leaderboard-item">
                                <div class="leaderboard-position">3</div>
                                <div class="leaderboard-name">Дмитрий Капиталов</div>
                                <div class="leaderboard-score">8750</div>
                            </div>
                            <div class="leaderboard-item current-user">
                                <div class="leaderboard-position">12</div>
                                <div class="leaderboard-name">Иван Инвесторов</div>
                                <div class="leaderboard-score">6450</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="dashboard-card">
                        <h3>Ближайшие задания</h3>
                        <div class="upcoming-tasks">
                            <div class="task">
                                <div class="task-title">Викторина "Основы фондового рынка"</div>
                                <div class="task-date">Доступно через 2 дня</div>
                            </div>
                            <div class="task">
                                <div class="task-title">Симуляция торговли</div>
                                <div class="task-date">Доступно через 5 дней</div>
                            </div>
                            <div class="task">
                                <div class="task-title">Анализ компании</div>
                                <div class="task-date">Доступно через 1 неделю</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h4>InvestIQ</h4>
                    <p>Образовательная платформа для начинающих и опытных инвесторов. Учитесь, практикуйтесь и становитесь финансово грамотными.</p>
                </div>
                <div class="footer-column">
                    <h4>Разделы</h4>
                    <ul class="footer-links">
                        <li><a href="#">Главная</a></li>
                        <li><a href="#">Обучение</a></li>
                        <li><a href="#">Портфель</a></li>
                        <li><a href="#">Рейтинги</a></li>
                        <li><a href="#">О нас</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>Ресурсы</h4>
                    <ul class="footer-links">
                        <li><a href="#">Блог</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Поддержка</a></li>
                        <li><a href="#">Партнеры</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>Контакты</h4>
                    <ul class="footer-links">
                        <li><a href="#">info@investiq.ru</a></li>
                        <li><a href="#">+7 (495) 123-45-67</a></li>
                        <li><a href="#">Москва, ул. Инвестиционная, 15</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                &copy; 2023 InvestIQ. Все права защищены.
            </div>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const startQuizBtn = document.getElementById('startQuizBtn');
            const quizSection = document.getElementById('quizSection');
            const featuresSection = document.getElementById('featuresSection');
            const dashboardSection = document.getElementById('dashboardSection');
            const nextQuestionBtn = document.getElementById('nextQuestionBtn');
            const prevQuestionBtn = document.getElementById('prevQuestionBtn');
            const quizOptions = document.querySelectorAll('.quiz-option');
            
            // Начало тестирования
            startQuizBtn.addEventListener('click', function(e) {
                e.preventDefault();
                quizSection.style.display = 'block';
                featuresSection.style.display = 'none';
                window.scrollTo(0, 0);
            });
            
            // Выбор варианта ответа
            quizOptions.forEach(option => {
                option.addEventListener('click', function() {
                    quizOptions.forEach(opt => opt.classList.remove('selected'));
                    this.classList.add('selected');
                });
            });
            
            // Переход к следующему вопросу (имитация завершения теста)
            nextQuestionBtn.addEventListener('click', function() {
                quizSection.style.display = 'none';
                dashboardSection.style.display = 'block';
                window.scrollTo(0, 0);
            });
            
            // Возврат к предыдущему вопросу
            prevQuestionBtn.addEventListener('click', function() {
                // В реальном приложении здесь была бы логика перехода к предыдущему вопросу
                alert('Возврат к предыдущему вопросу');
            });
        });
    </script>
</body>
</html>
