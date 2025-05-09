<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Премиум кофейня "Arabica"</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary: #6F4E37;
            --secondary: #E3DCD5;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f9f9f9;
            color: #333;
            overflow-x: hidden;
        }
        
        /* Анимированная шапка */
        header {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), 
                        url('https://images.unsplash.com/photo-1509042239860-f550ce710b93?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            position: relative;
            animation: fadeIn 1.5s ease-in-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        /* Навигация */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: rgba(0,0,0,0.8);
            z-index: 100;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: white;
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        /* Герой-секция */
        .hero {
            margin-top: 80px;
        }
        
        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            animation: slideUp 1s ease-out;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 30px;
            animation: slideUp 1.2s ease-out;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: slideUp 1.4s ease-out;
        }
        
        .btn:hover {
            background-color: #5a3c2a;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        @keyframes slideUp {
            from { 
                opacity: 0;
                transform: translateY(50px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Секция меню */
        .menu-section {
            padding: 100px 0;
            background-color: white;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            font-size: 2.5rem;
            color: var(--primary);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--primary);
            margin: 15px auto 0;
        }
        
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .menu-item {
            background-color: var(--secondary);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }
        
        .menu-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }
        
        .menu-img {
            height: 200px;
            overflow: hidden;
        }
        
        .menu-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .menu-item:hover .menu-img img {
            transform: scale(1.1);
        }
        
        .menu-content {
            padding: 20px;
        }
        
        .menu-content h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .menu-content p {
            color: #666;
            margin-bottom: 15px;
        }
        
        .price {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--primary);
        }
        
        /* Секция отзывов */
        .testimonials {
            padding: 100px 0;
            background-color: var(--secondary);
        }
        
        .testimonial-slider {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }
        
        .testimonial {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            text-align: center;
            display: none;
        }
        
        .testimonial.active {
            display: block;
            animation: fadeIn 0.5s ease-in-out;
        }
        
        .testimonial img {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 20px;
            border: 3px solid var(--primary);
        }
        
        .testimonial p {
            font-style: italic;
            margin-bottom: 20px;
            font-size: 1.1rem;
        }
        
        .testimonial h4 {
            color: var(--primary);
        }
        
        .slider-nav {
            display: flex;
            justify-content: center;
            margin-top: 30px;
            gap: 10px;
        }
        
        .slider-dot {
            width: 12px;
            height: 12px;
            background-color: #ccc;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .slider-dot.active {
            background-color: var(--primary);
            transform: scale(1.2);
        }
        
        /* Секция бронирования */
        .booking {
            padding: 100px 0;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), 
                        url('https://images.unsplash.com/photo-1517701550927-30cf4ba1dba5?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-attachment: fixed;
            color: white;
            text-align: center;
        }
        
        .booking-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            padding: 40px;
            border-radius: 10px;
            border: 1px solid rgba(255,255,255,0.2);
        }
        
        .form-group {
            margin-bottom: 20px;
            text-align: left;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        
        .form-group input, 
        .form-group select, 
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border-radius: 5px;
            border: none;
            background-color: rgba(255,255,255,0.2);
            color: white;
        }
        
        .form-group input::placeholder {
            color: rgba(255,255,255,0.7);
        }
        
        .submit-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
            width: 100%;
        }
        
        .submit-btn:hover {
            background-color: #5a3c2a;
            transform: translateY(-3px);
        }
        
        /* Футер */
        footer {
            background-color: #222;
            color: white;
            padding: 50px 0 20px;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .footer-section {
            flex: 1;
            min-width: 250px;
            margin-bottom: 30px;
        }
        
        .footer-section h3 {
            color: var(--primary);
            margin-bottom: 20px;
            font-size: 1.3rem;
        }
        
        .footer-section p, 
        .footer-section a {
            color: #bbb;
            margin-bottom: 10px;
            display: block;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-section a:hover {
            color: white;
        }
        
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-icons a {
            color: white;
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }
        
        .social-icons a:hover {
            color: var(--primary);
            transform: translateY(-3px);
        }
        
        .copyright {
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid #444;
            color: #777;
        }
        
        /* Адаптивность */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .menu-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Навигация -->
    <nav>
        <div class="logo">Arabica</div>
        <div class="nav-links">
            <a href="#home">Главная</a>
            <a href="#menu">Меню</a>
            <a href="#about">О нас</a>
            <a href="#contact">Контакты</a>
        </div>
    </nav>
    
    <!-- Шапка -->
    <header id="home">
        <div class="hero">
            <h1>Искусство в каждой чашке</h1>
            <p>Откройте для себя непревзойденный вкус нашего кофе из отборных зерен</p>
            <a href="#booking" class="btn">Забронировать столик</a>
        </div>
    </header>
    
    <!-- Секция меню -->
    <section class="menu-section" id="menu">
        <div class="container">
            <h2 class="section-title">Наше меню</h2>
            <div class="menu-grid">
                <!-- Кофе -->
                <div class="menu-item">
                    <div class="menu-img">
                        <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Эспрессо">
                    </div>
                    <div class="menu-content">
                        <h3>Эспрессо</h3>
                        <p>Крепкий и насыщенный вкус с плотной пенкой</p>
                        <span class="price">180₽</span>
                    </div>
                </div>
                
                <!-- Десерты -->
                <div class="menu-item">
                    <div class="menu-img">
                        <img src="https://images.unsplash.com/photo-1551024506-0bccd828d307?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Тирамису">
                    </div>
                    <div class="menu-content">
                        <h3>Тирамису</h3>
                        <p>Классический итальянский десерт с кофейным вкусом</p>
                        <span class="price">320₽</span>
                    </div>
                </div>
                
                <!-- Завтраки -->
                <div class="menu-item">
                    <div class="menu-img">
                        <img src="https://images.unsplash.com/photo-1484723091739-30a097e8f929?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Бранч">
                    </div>
                    <div class="menu-content">
                        <h3>Бранч-сет</h3>
                        <p>Яичница, тосты, свежие овощи и кофе на выбор</p>
                        <span class="price">450₽</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Секция отзывов -->
    <section class="testimonials" id="about">
        <div class="container">
            <h2 class="section-title">Отзывы</h2>
            <div class="testimonial-slider">
                <div class="testimonial active">
                    <img src="https://randomuser.me/api/portraits/women/43.jpg" alt="Отзыв 1">
                    <p>"Лучший кофе в городе! Атмосфера просто волшебная, всегда прихожу сюда для вдохновения."</p>
                    <h4>Анна С.</h4>
                </div>
                
                <div class="testimonial">
                    <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Отзыв 2">
                    <p>"Тирамису здесь - это нечто! Как будто снова оказался в Италии. Обязательно вернусь!"</p>
                    <h4>Дмитрий К.</h4>
                </div>
                
                <div class="testimonial">
                    <img src="https://randomuser.me/api/portraits/women/65.jpg" alt="Отзыв 3">
                    <p>"Идеальное место для работы. Быстрый Wi-Fi, вкусный кофе и уютные места у окна."</p>
                    <h4>Елена М.</h4>
                </div>
                
                <div class="slider-nav">
                    <div class="slider-dot active" data-slide="0"></div>
                    <div class="slider-dot" data-slide="1"></div>
                    <div class="slider-dot" data-slide="2"></div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Секция бронирования -->
    <section class="booking" id="booking">
        <div class="container">
            <h2 class="section-title">Забронировать столик</h2>
            <div class="booking-form">
                <form id="reservation-form">
                    <div class="form-group">
                        <label for="name">Ваше имя</label>
                        <input type="text" id="name" placeholder="Введите ваше имя" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="phone">Телефон</label>
                        <input type="tel" id="phone" placeholder="+7 (XXX) XXX-XX-XX" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="date">Дата</label>
                        <input type="date" id="date" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="time">Время</label>
                        <input type="time" id="time" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="guests">Количество гостей</label>
                        <select id="guests" required>
                            <option value="1">1 человек</option>
                            <option value="2">2 человека</option>
                            <option value="3">3 человека</option>
                            <option value="4">4 человека</option>
                            <option value="5+">5+ человек</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Особые пожелания</label>
                        <textarea id="message" rows="3" placeholder="Укажите особые пожелания..."></textarea>
                    </div>
                    
                    <button type="submit" class="submit-btn">Забронировать</button>
                </form>
            </div>
        </div>
    </section>
    
    <!-- Футер -->
    <footer id="contact">
        <div class="footer-content">
            <div class="footer-section">
                <h3>О нас</h3>
                <p>Кофейня Arabica - это место, где рождается настоящий кофе. Мы работаем с 2010 года.</p>
            </div>
            
            <div class="footer-section">
                <h3>Контакты</h3>
                <p><i class="fas fa-map-marker-alt"></i> ул. Кофейная, 15</p>
                <p><i class="fas fa-phone"></i> +7 (123) 456-78-90</p>
                <p><i class="fas fa-envelope"></i> info@arabica-cafe.ru</p>
            </div>
            
            <div class="footer-section">
                <h3>Часы работы</h3>
                <p>Пн-Пт: 8:00 - 22:00</p>
                <p>Сб-Вс: 9:00 - 23:00</p>
                <div class="social-icons">
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-vk"></i></a>
                    <a href="#"><i class="fab fa-telegram"></i></a>
                </div>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 Кофейня Arabica. Все права защищены.</p>
        </div>
    </footer>
    
    <script>
        // Слайдер отзывов
        const testimonials = document.querySelectorAll('.testimonial');
        const dots = document.querySelectorAll('.slider-dot');
        let currentSlide = 0;
        
        function showSlide(n) {
            testimonials.forEach(testimonial => testimonial.classList.remove('active'));
            dots.forEach(dot => dot.classList.remove('active'));
            
            currentSlide = (n + testimonials.length) % testimonials.length;
            testimonials[currentSlide].classList.add('active');
            dots[currentSlide].classList.add('active');
        }
        
        dots.forEach((dot, index) => {
            dot.addEventListener('click', () => showSlide(index));
        });
        
        // Автоматическая смена слайдов
        setInterval(() => {
            showSlide(currentSlide + 1);
        }, 5000);
        
        // Обработка формы
        const form = document.getElementById('reservation-form');
        form.addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Спасибо! Ваша заявка принята. Мы свяжемся с вами для подтверждения.');
            form.reset();
        });
        
        // Плавная прокрутка
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
        
        // Анимация при скролле
        window.addEventListener('scroll', function() {
            const nav = document.querySelector('nav');
            if (window.scrollY > 100) {
                nav.style.backgroundColor = 'rgba(0,0,0,0.9)';
            } else {
                nav.style.backgroundColor = 'rgba(0,0,0,0.8)';
            }
        });
    </script>
</body>
</html>
