
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أكاديمية البرمجة - تعلم لغات البرمجة</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <meta name="google-signin-client_id" content="YOUR_GOOGLE_CLIENT_ID">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Cairo', sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f8f9fa;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            text-decoration: none;
            color: white;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: opacity 0.3s;
        }

        .nav-links a:hover {
            opacity: 0.8;
        }

        .auth-buttons {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .btn {
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .btn-outline {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-outline:hover {
            background: white;
            color: #667eea;
        }

        /* User Profile */
        .user-profile {
            display: none;
            align-items: center;
            gap: 0.5rem;
        }

        .user-profile.active {
            display: flex;
        }

        .user-avatar {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            border: 2px solid white;
        }

        .user-name {
            font-weight: 600;
        }

        .logout-btn {
            background: rgba(255,255,255,0.2);
            color: white;
            border: none;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            cursor: pointer;
            font-size: 0.8rem;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 120px 0 80px;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .hero p {
            font-size: 1.25rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .hero-cta {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-bottom: 2rem;
        }

        /* Course Statistics */
        .course-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;
            margin: 2rem 0;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .stat-item {
            text-align: center;
            padding: 1rem;
            background: rgba(255,255,255,0.1);
            border-radius: 10px;
            backdrop-filter: blur(10px);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: #FFD700;
        }

        /* Share Buttons */
        .share-buttons {
            display: flex;
            gap: 10px;
            justify-content: center;
            margin-top: 20px;
        }

        .share-btn {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            border: none;
            color: white;
            cursor: pointer;
            transition: transform 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .share-btn:hover {
            transform: scale(1.1);
        }

        .whatsapp { background: #25D366; }
        .telegram { background: #0088cc; }
        .twitter { background: #1DA1F2; }
        .facebook { background: #4267B2; }

        /* Courses Section */
        .courses {
            padding: 80px 0;
            background: white;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
        }

        .courses-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .course-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .course-card:hover {
            transform: translateY(-10px);
        }

        .course-header {
            padding: 2rem;
            text-align: center;
        }

        .course-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .course-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .course-description {
            color: #666;
            margin-bottom: 1.5rem;
        }

        .course-features {
            list-style: none;
            padding: 0 2rem 2rem;
        }

        .course-features li {
            padding: 0.5rem 0;
            color: #555;
        }

        .course-features li:before {
            content: "✓";
            color: #28a745;
            font-weight: bold;
            margin-left: 0.5rem;
        }

        /* Interactive Course Section */
        .interactive-course {
            display: none;
            padding: 80px 0;
            background: #f8f9fa;
        }

        .course-container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .course-nav {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .lesson-content {
            padding: 2rem;
        }

        .lesson-title {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: #333;
        }

        .lesson-text {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 2rem;
            color: #555;
        }

        .code-example {
            background: #1e1e1e;
            color: #00ff00;
            padding: 1.5rem;
            border-radius: 10px;
            margin: 2rem 0;
            overflow-x: auto;
            font-family: 'Courier New', monospace;
            direction: ltr;
        }

        .quiz-section {
            background: #f8f9fa;
            padding: 2rem;
            border-radius: 10px;
            margin: 2rem 0;
        }

        .quiz-options {
            display: grid;
            gap: 1rem;
            margin-top: 1rem;
        }

        .quiz-option {
            padding: 1rem;
            background: white;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: right;
        }

        .quiz-option:hover {
            border-color: #667eea;
            background: #f8f9ff;
        }

        .quiz-option.correct {
            border-color: #28a745;
            background: #d4edda;
        }

        .lesson-navigation {
            display: flex;
            justify-content: space-between;
            padding: 2rem;
            border-top: 1px solid #e9ecef;
        }

        .progress-bar {
            width: 100%;
            height: 8px;
            background: #e9ecef;
            border-radius: 4px;
            overflow: hidden;
            margin: 1rem 0;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(45deg, #667eea, #764ba2);
            transition: width 0.5s ease;
        }

        /* Customer Service */
        .customer-service {
            padding: 80px 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .service-card {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-5px);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #FFD700;
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            padding: 3rem 0 1rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #FFD700;
        }

        .footer-section a {
            display: block;
            color: #bdc3c7;
            text-decoration: none;
            margin-bottom: 0.5rem;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background: #667eea;
            border-radius: 50%;
            text-align: center;
            line-height: 40px;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
        }

        .modal.active {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            max-width: 400px;
            width: 90%;
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 10px;
            left: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #999;
        }

        .google-signin {
            background: #4285f4;
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1rem;
            margin-top: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            justify-content: center;
            width: 100%;
        }

        .google-signin:hover {
            background: #3367d6;
        }

        /* Points and Achievements */
        .points-counter {
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            color: #333;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-weight: bold;
            display: none;
            align-items: center;
            gap: 0.5rem;
        }

        .notification-bell {
            position: relative;
            cursor: pointer;
            color: white;
            font-size: 1.2rem;
        }

        .notification-badge {
            position: absolute;
            top: -5px;
            right: -5px;
            background: #ff4757;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .achievements-badge {
            position: fixed;
            top: 50%;
            right: -300px;
            width: 280px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            padding: 20px;
            transition: right 0.5s ease;
            z-index: 2000;
        }

        .achievements-badge.show {
            right: 20px;
        }

        /* Floating Chat */
        .floating-chat {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
        }

        .chat-button {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 20px rgba(102, 126, 234, 0.4);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .chat-button:hover {
            transform: scale(1.1);
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s ease forwards;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Toast Notifications */
        .toast {
            position: fixed;
            top: 20px;
            right: 20px;
            background: #28a745;
            color: white;
            padding: 1rem 2rem;
            border-radius: 10px;
            z-index: 3000;
            transform: translateX(100%);
            transition: transform 0.3s ease;
        }

        .toast.show {
            transform: translateX(0);
        }

        .toast.error {
            background: #dc3545;
        }

        .toast.info {
            background: #17a2b8;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .course-stats {
                grid-template-columns: 1fr;
            }

            .hero-cta {
                flex-direction: column;
                align-items: center;
            }

            .lesson-navigation {
                flex-direction: column;
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <a href="#" class="logo">🎓 أكاديمية البرمجة</a>
            <ul class="nav-links">
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#courses">الدروس</a></li>
                <li><a href="#about">من نحن</a></li>
                <li><a href="#contact">اتصل بنا</a></li>
            </ul>
            <div class="auth-buttons">
                <div class="notification-bell" onclick="showNotifications()">
                    <i class="fas fa-bell"></i>
                    <span class="notification-badge">3</span>
                </div>
                <div class="points-counter" id="userPoints">
                    <i class="fas fa-star"></i>
                    <span id="pointsCount">0</span> نقطة
                </div>
                <button class="btn btn-outline" onclick="openModal()">
                    <i class="fab fa-google"></i>
                    تسجيل الدخول
                </button>
                <div class="user-profile" id="userProfile">
                    <img src="" alt="User Avatar" class="user-avatar" id="userAvatar">
                    <span class="user-name" id="userName"></span>
                    <button class="logout-btn" onclick="signOut()">خروج</button>
                </div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1 class="fade-in">تعلم البرمجة من الصفر إلى الاحتراف</h1>
            <p class="fade-in">اكتشف عالم البرمجة مع أفضل الدروس التفاعلية والمشاريع العملية</p>
            
            <!-- Course Statistics -->
            <div class="course-stats fade-in">
                <div class="stat-item">
                    <div class="stat-number">15,000+</div>
                    <div>طالب مسجل</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">6</div>
                    <div>لغة برمجة</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">95%</div>
                    <div>معدل النجاح</div>
                </div>
            </div>
            
            <div class="hero-cta fade-in">
                <a href="#courses" class="btn btn-primary">ابدأ التعلم الآن</a>
                <a href="#about" class="btn btn-outline">اعرف المزيد</a>
            </div>
            
            <!-- Share Buttons -->
            <div class="share-buttons fade-in">
                <button class="share-btn whatsapp" onclick="shareOnWhatsApp()">
                    <i class="fab fa-whatsapp"></i>
                </button>
                <button class="share-btn telegram" onclick="shareOnTelegram()">
                    <i class="fab fa-telegram"></i>
                </button>
                <button class="share-btn twitter" onclick="shareOnTwitter()">
                    <i class="fab fa-twitter"></i>
                </button>
                <button class="share-btn facebook" onclick="shareOnFacebook()">
                    <i class="fab fa-facebook"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Courses Section -->
    <section class="courses" id="courses">
        <div class="container">
            <h2 class="section-title">الدورات المتاحة</h2>
            <div class="courses-grid">
                <!-- HTML Course -->
                <div class="course-card fade-in">
                    <div class="course-header">
                        <div class="course-icon">🌐</div>
                        <h3 class="course-title">HTML & CSS</h3>
                        <p class="course-description">تعلم أساسيات تطوير المواقع</p>
                    </div>
                    <ul class="course-features">
                        <li>أساسيات HTML</li>
                        <li>تنسيق CSS</li>
                        <li>التصميم المتجاوب</li>
                        <li>مشاريع عملية</li>
                    </ul>
                    <div style="padding: 0 2rem 2rem;">
                        <button class="btn btn-primary" onclick="startInteractiveCourse('HTML')" style="width: 100%;">
                            ابدأ الدورة التفاعلية
                        </button>
                    </div>
                </div>

                <!-- JavaScript Course -->
                <div class="course-card fade-in">
                    <div class="course-header">
                        <div class="course-icon">⚡</div>
                        <h3 class="course-title">JavaScript</h3>
                        <p class="course-description">البرمجة التفاعلية للمواقع</p>
                    </div>
                    <ul class="course-features">
                        <li>المتغيرات والدوال</li>
                        <li>التعامل مع DOM</li>
                        <li>الأحداث والتفاعل</li>
                        <li>مشاريع ديناميكية</li>
                    </ul>
                    <div style="padding: 0 2rem 2rem;">
                        <button class="btn btn-primary" onclick="startInteractiveCourse('JavaScript')" style="width: 100%;">
                            ابدأ الدورة التفاعلية
                        </button>
                    </div>
                </div>

                <!-- Python Course -->
                <div class="course-card fade-in">
                    <div class="course-header">
                        <div class="course-icon">🐍</div>
                        <h3 class="course-title">Python</h3>
                        <p class="course-description">لغة البرمجة الأكثر شعبية</p>
                    </div>
                    <ul class="course-features">
                        <li>أساسيات البرمجة</li>
                        <li>هياكل البيانات</li>
                        <li>البرمجة الكائنية</li>
                        <li>مكتبات مفيدة</li>
                    </ul>
                    <div style="padding: 0 2rem 2rem;">
                        <button class="btn btn-primary" onclick="startInteractiveCourse('Python')" style="width: 100%;">
                            ابدأ الدورة التفاعلية
                        </button>
                    </div>
                </div>

                <!-- React Course -->
                <div class="course-card fade-in">
                    <div class="course-header">
                        <div class="course-icon">⚛️</div>
                        <h3 class="course-title">React</h3>
                        <p class="course-description">تطوير تطبيقات الويب الحديثة</p>
                    </div>
                    <ul class="course-features">
                        <li>مكونات React</li>
                        <li>إدارة الحالة</li>
                        <li>React Hooks</li>
                        <li>تطبيقات كاملة</li>
                    </ul>
                    <div style="padding: 0 2rem 2rem;">
                        <button class="btn btn-primary" onclick="startInteractiveCourse('React')" style="width: 100%;">
                            ابدأ الدورة التفاعلية
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Interactive Course Section -->
    <section class="interactive-course" id="interactiveCourse">
        <div class="container">
            <div class="course-container">
                <div class="course-nav">
                    <button onclick="backToCourses()" class="btn btn-outline">← العودة للدورات</button>
                    <h2 id="courseTitle">دورة HTML التفاعلية</h2>
                    <div class="points-counter">
                        <i class="fas fa-star"></i>
                        <span id="coursePoints">0</span> نقطة
                    </div>
                </div>
                
                <div class="progress-bar">
                    <div class="progress-fill" id="courseProgress" style="width: 0%"></div>
                </div>

                <div class="lesson-content">
                    <h3 class="lesson-title" id="lessonTitle">مقدمة في HTML</h3>
                    <p class="lesson-text" id="lessonText">
                        HTML هي لغة ترميز النصوص التشعبية، وهي اللغة الأساسية لإنشاء صفحات الويب.
                        تتكون من عناصر محاطة بوسوم تحدد نوع المحتوى وكيفية عرضه في المتصفح.
                    </p>

                    <div class="code-example" id="codeExample">
                        <pre><code>&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
    &lt;title&gt;صفحتي الأولى&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;h1&gt;أهلاً بالعالم!&lt;/h1&gt;
    &lt;p&gt;هذه أول صفحة HTML لي&lt;/p&gt;
&lt;/body&gt;
&lt;/html&gt;</code></pre>
                    </div>

                    <div class="quiz-section">
                        <h4>اختبر فهمك:</h4>
                        <p id="quizQuestion">ما هو الوسم المستخدم لإنشاء عنوان رئيسي في HTML؟</p>
                        <div class="quiz-options" id="quizOptions">
                            <div class="quiz-option" onclick="selectQuizOption(this, false)">&lt;title&gt;</div>
                            <div class="quiz-option" onclick="selectQuizOption(this, true)">&lt;h1&gt;</div>
                            <div class="quiz-option" onclick="selectQuizOption(this, false)">&lt;header&gt;</div>
                        </div>
                    </div>
                </div>

                <div class="lesson-navigation">
                    <button class="btn btn-outline" onclick="previousLesson()" id="prevBtn" disabled>
                        <i class="fas fa-arrow-right"></i> الدرس السابق
                    </button>
                    <button class="btn btn-primary" onclick="completeLesson()" id="completeBtn">
                        أكمل الدرس
                    </button>
                    <button class="btn btn-primary" onclick="nextLesson()" id="nextBtn">
                        الدرس التالي <i class="fas fa-arrow-left"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Customer Service Section -->
    <section class="customer-service" id="contact">
        <div class="container">
            <h2 class="section-title">خدمة العملاء</h2>
            <div class="service-grid">
                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-headset"></i>
                    </div>
                    <h3>دعم فني 24/7</h3>
                    <p>فريق الدعم الفني متاح لمساعدتك في أي وقت</p>
                    <div style="margin: 15px 0; font-size: 1.1rem;">
                        <i class="fas fa-phone" style="color: #FFD700; margin-left: 10px;"></i>
                        <strong>774633282</strong>
                    </div>
                    <a href="tel:774633282" class="btn btn-outline">اتصل الآن</a>
                </div>

                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fab fa-whatsapp"></i>
                    </div>
                    <h3>واتساب</h3>
                    <p>تواصل معنا عبر الواتساب للحصول على الدعم السريع</p>
                    <a href="https://wa.me/966774633282" class="btn btn-outline" target="_blank">راسلنا على واتساب</a>
                </div>

                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-comments"></i>
                    </div>
                    <h3>منتدى المناقشات</h3>
                    <p>انضم لمجتمع المطورين وتبادل الخبرات</p>
                    <button class="btn btn-outline" onclick="openForum()">انضم للمنتدى</button>
                </div>

                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-video"></i>
                    </div>
                    <h3>جلسات مباشرة</h3>
                    <p>جلسات تعليمية مباشرة مع أفضل المدربين</p>
                    <button class="btn btn-outline" onclick="bookSession()">احجز جلسة</button>
                </div>
            </div>
        </div>
    </section>

    
<!-- About Section -->
<section id="about" style="padding: 80px 0; background: #f0f0f0;">
    <div class="container">
        <h2 class="section-title">من نحن</h2>
        <p style="text-align: center; max-width: 800px; margin: auto; font-size: 1.2rem; color: #555;">
            نحن أكاديمية البرمجة، نقدم دروساً تفاعلية ومجانية لتعليم لغات البرمجة بأسلوب مبسط وعملي. انضم إلينا وابدأ رحلتك البرمجية الآن.
        </p>
    </div>
</section>

<!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>الدورات</h3>
                    <a href="#" onclick="startInteractiveCourse('HTML')">HTML & CSS</a>
                    <a href="#" onclick="startInteractiveCourse('JavaScript')">JavaScript</a>
                    <a href="#" onclick="startInteractiveCourse('Python')">Python</a>
                    <a href="#" onclick="startInteractiveCourse('React')">React</a>
                </div>
                <div class="footer-section">
                    <h3>المساعدة</h3>
                    <a href="#">الأسئلة الشائعة</a>
                    <a href="#contact">الدعم الفني</a>
                    <a href="#">سياسة الخصوصية</a>
                    <a href="#">شروط الاستخدام</a>
                </div>
                <div class="footer-section">
                    <h3>تواصل معنا</h3>
                    <a href="alinaser738162039@gmail.com">info@programming-academy.com</a>
                    <a href="tel:+966774633282">+966 77 463 3282</a>
                    <div class="social-links">
                        <a href="#" onclick="shareOnFacebook()"><i class="fab fa-facebook"></i></a>
                        <a href="#" onclick="shareOnTwitter()"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                    </div>
                </div>
            </div>
            <p style="text-align: center; margin-top: 2rem; padding-top: 2rem; border-top: 1px solid #34495e;">
                &copy; 2024 أكاديمية البرمجة. جميع الحقوق محفوظة.
            </p>
        </div>
    </footer>

    <!-- Auth Modal -->
    <div class="modal" id="authModal">
        <div class="modal-content">
            <button class="close-modal" onclick="closeModal()">&times;</button>
            <h2>تسجيل الدخول</h2>
            <p>سجل دخولك باستخدام حساب جوجل للوصول لجميع الدورات والمميزات المتقدمة</p>
            <button class="google-signin" onclick="signInWithGoogle()">
                <i class="fab fa-google"></i>
                تسجيل الدخول بجوجل
            </button>
        </div>
    </div>

    <!-- Floating Chat Button -->
    <div class="floating-chat">
        <button class="chat-button" onclick="openChat()">
            <i class="fas fa-comments"></i>
        </button>
    </div>

    <!-- Achievements Badge -->
    <div class="achievements-badge" id="achievementsBadge">
        <button onclick="hideAchievements()" style="float: left; background: none; border: none; font-size: 1.2rem; cursor: pointer;">&times;</button>
        <div style="text-align: center;">
            <i class="fas fa-trophy" style="font-size: 2rem; color: #FFD700; margin-bottom: 10px;"></i>
            <h4 id="achievementTitle">إنجاز جديد!</h4>
            <p id="achievementText">لقد أكملت أول درس لك!</p>
        </div>
    </div>

    <!-- Google APIs -->
    <script src="https://apis.google.com/js/platform.js" async defer></script>

    <script>
        // Global Variables
        let isSignedIn = false;
        let userPoints = 0;
        let currentLesson = 0;
        let completedLessons = [];
        let currentCourse = 'HTML';

        // Course Data
        const courses = {
            HTML: {
                title: 'دورة HTML التفاعلية',
                lessons: [
                    {
                        title: 'مقدمة في HTML',
                        content: 'HTML هي لغة ترميز النصوص التشعبية، وهي اللغة الأساسية لإنشاء صفحات الويب. تتكون من عناصر محاطة بوسوم تحدد نوع المحتوى وكيفية عرضه في المتصفح.',
                        code: `&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
    &lt;title&gt;صفحتي الأولى&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;h1&gt;أهلاً بالعالم!&lt;/h1&gt;
    &lt;p&gt;هذه أول صفحة HTML لي&lt;/p&gt;
&lt;/body&gt;
&lt;/html&gt;`,
                        question: 'ما هو الوسم المستخدم لإنشاء عنوان رئيسي في HTML؟',
                        options: ['&lt;title&gt;', '&lt;h1&gt;', '&lt;header&gt;'],
                        correct: 1
                    },
                    {
                        title: 'العناصر والوسوم',
                        content: 'تتكون HTML من عناصر محاطة بوسوم. كل وسم له وظيفة محددة في تحديد نوع المحتوى وطريقة عرضه.',
                        code: `&lt;h1&gt;عنوان رئيسي&lt;/h1&gt;
&lt;h2&gt;عنوان فرعي&lt;/h2&gt;
&lt;p&gt;فقرة نصية&lt;/p&gt;
&lt;a href="https://example.com"&gt;رابط&lt;/a&gt;
&lt;img src="image.jpg" alt="وصف الصورة"&gt;`,
                        question: 'أي وسم يستخدم لإنشاء رابط؟',
                        options: ['&lt;link&gt;', '&lt;a&gt;', '&lt;url&gt;'],
                        correct: 1
                    },
                    {
                        title: 'النماذج في HTML',
                        content: 'النماذج تسمح للمستخدمين بإدخال البيانات وإرسالها للخادم. تحتوي على عناصر مختلفة مثل input و select و textarea.',
                        code: `&lt;form&gt;
    &lt;label for="name"&gt;الاسم:&lt;/label&gt;
    &lt;input type="text" id="name" name="name"&gt;
    
    &lt;label for="email"&gt;البريد الإلكتروني:&lt;/label&gt;
    &lt;input type="email" id="email" name="email"&gt;
    
    &lt;button type="submit"&gt;إرسال&lt;/button&gt;
&lt;/form&gt;`,
                        question: 'ما هو نوع input المناسب للبريد الإلكتروني؟',
                        options: ['text', 'email', 'mail'],
                        correct: 1
                    }
                ]
            },
            JavaScript: {
                title: 'دورة JavaScript التفاعلية',
                lessons: [
                    {
                        title: 'مقدمة في JavaScript',
                        content: 'JavaScript هي لغة برمجة تفاعلية تجعل المواقع حية وديناميكية.',
                        code: `console.log("مرحباً بالعالم!");
let name = "أحمد";
alert("مرحباً " + name);`,
                        question: 'كيف نعرض رسالة في وحدة التحكم؟',
                        options: ['print()', 'console.log()', 'alert()'],
                        correct: 1
                    }
                ]
            }
        };

        // Authentication Functions
        function openModal() {
            document.getElementById('authModal').classList.add('active');
        }

        function closeModal() {
            document.getElementById('authModal').classList.remove('active');
        }

        function signInWithGoogle() {
            // Simulate Google Sign In
            setTimeout(() => {
                const fakeUser = {
                    name: 'المستخدم الجديد',
                    avatar: 'https://via.placeholder.com/40/667eea/ffffff?text=U',
                    email: 'user@example.com'
                };
                
                updateUserProfile(fakeUser);
                closeModal();
                showToast('تم تسجيل الدخول بنجاح!', 'success');
                addPoints(5); // Welcome bonus
            }, 1000);
        }

        function updateUserProfile(user) {
            const userProfile = document.getElementById('userProfile');
            const userAvatar = document.getElementById('userAvatar');
            const userName = document.getElementById('userName');
            const authButton = document.querySelector('.auth-buttons .btn-outline');
            const pointsCounter = document.getElementById('userPoints');

            userAvatar.src = user.avatar;
            userName.textContent = user.name;
            userProfile.classList.add('active');
            authButton.style.display = 'none';
            pointsCounter.style.display = 'flex';
            isSignedIn = true;
            
            // Welcome achievement
            setTimeout(() => {
                showAchievement('مرحباً بك!', 'مرحباً بك في أكاديمية البرمجة! ابدأ رحلتك الآن واحصل على 5 نقاط مجانية!');
            }, 2000);
        }

        function signOut() {
            const userProfile = document.getElementById('userProfile');
            const authButton = document.querySelector('.auth-buttons .btn-outline');
            const pointsCounter = document.getElementById('userPoints');

            userProfile.classList.remove('active');
            authButton.style.display = 'block';
            pointsCounter.style.display = 'none';
            isSignedIn = false;
            userPoints = 0;
            updatePointsDisplay();
            showToast('تم تسجيل الخروج بنجاح', 'info');
        }

        // Course Functions
        function startInteractiveCourse(courseName) {
            if (!isSignedIn) {
                openModal();
                return;
            }
            
            currentCourse = courseName;
            currentLesson = 0;
            
            // Show interactive course section
            document.getElementById('interactiveCourse').style.display = 'block';
            document.getElementById('courses').style.display = 'none';
            
            loadLesson();
            addPoints(5);
            showToast(`بدء ${courses[courseName].title}`, 'success');
            
            // Scroll to course section
            document.getElementById('interactiveCourse').scrollIntoView({
                behavior: 'smooth'
            });
        }

        function loadLesson() {
            const course = courses[currentCourse];
            const lesson = course.lessons[currentLesson];
            
            document.getElementById('courseTitle').textContent = course.title;
            document.getElementById('lessonTitle').textContent = lesson.title;
            document.getElementById('lessonText').textContent = lesson.content;
            document.getElementById('codeExample').innerHTML = `<pre><code>${lesson.code}</code></pre>`;
            document.getElementById('quizQuestion').textContent = lesson.question;
            
            // Load quiz options
            const optionsContainer = document.getElementById('quizOptions');
            optionsContainer.innerHTML = '';
            lesson.options.forEach((option, index) => {
                const optionDiv = document.createElement('div');
                optionDiv.className = 'quiz-option';
                optionDiv.innerHTML = option;
                optionDiv.onclick = () => selectQuizOption(optionDiv, index === lesson.correct);
                optionsContainer.appendChild(optionDiv);
            });
            
            // Update navigation buttons
            document.getElementById('prevBtn').disabled = currentLesson === 0;
            document.getElementById('nextBtn').disabled = currentLesson === course.lessons.length - 1;
            
            // Update progress
            updateProgress();
        }

        function selectQuizOption(element, isCorrect) {
            // Remove previous selections
            document.querySelectorAll('.quiz-option').forEach(opt => {
                opt.classList.remove('correct');
                opt.style.background = '';
                opt.style.borderColor = '';
            });
            
            if (isCorrect) {
                element.classList.add('correct');
                showToast('إجابة صحيحة! 🎉', 'success');
                addPoints(10);
            } else {
                element.style.background = '#f8d7da';
                element.style.borderColor = '#dc3545';
                showToast('إجابة خاطئة، حاول مرة أخرى', 'error');
            }
        }

        function completeLesson() {
            if (!completedLessons.includes(`${currentCourse}-${currentLesson}`)) {
                completedLessons.push(`${currentCourse}-${currentLesson}`);
                addPoints(20);
                showToast('تم إكمال الدرس بنجاح!', 'success');
                
                // Check for course completion
                if (currentLesson === courses[currentCourse].lessons.length - 1) {
                    setTimeout(() => {
                        showAchievement('مبروك!', `لقد أكملت ${courses[currentCourse].title} بنجاح! 🎊`);
                    }, 1000);
                }
            }
            
            updateProgress();
        }

        function nextLesson() {
            if (currentLesson < courses[currentCourse].lessons.length - 1) {
                currentLesson++;
                loadLesson();
            }
        }

        function previousLesson() {
            if (currentLesson > 0) {
                currentLesson--;
                loadLesson();
            }
        }

        function backToCourses() {
            document.getElementById('interactiveCourse').style.display = 'none';
            document.getElementById('courses').style.display = 'block';
            document.getElementById('courses').scrollIntoView({
                behavior: 'smooth'
            });
        }

        function updateProgress() {
            const totalLessons = courses[currentCourse].lessons.length;
            const completed = completedLessons.filter(l => l.startsWith(currentCourse)).length;
            const progress = (completed / totalLessons) * 100;
            
            document.getElementById('courseProgress').style.width = progress + '%';
        }

        // Points and Achievements
        function addPoints(points) {
            userPoints += points;
            updatePointsDisplay();
            checkAchievements();
        }

        function updatePointsDisplay() {
            document.getElementById('pointsCount').textContent = userPoints;
            document.getElementById('coursePoints').textContent = userPoints;
        }

        function checkAchievements() {
            if (userPoints >= 50 && !completedLessons.includes('achievement-50')) {
                completedLessons.push('achievement-50');
                showAchievement('المثابرة!', 'لقد حصلت على 50 نقطة - أنت على الطريق الصحيح! 🌟');
            }
            
            if (userPoints >= 100 && !completedLessons.includes('achievement-100')) {
                completedLessons.push('achievement-100');
                showAchievement('خبير البرمجة!', 'مبروك! لقد حصلت على 100 نقطة! 🏆');
            }
        }

        function showAchievement(title, description) {
            document.getElementById('achievementTitle').textContent = title;
            document.getElementById('achievementText').textContent = description;
            document.getElementById('achievementsBadge').classList.add('show');
            
            setTimeout(() => {
                document.getElementById('achievementsBadge').classList.remove('show');
            }, 5000);
        }

        function hideAchievements() {
            document.getElementById('achievementsBadge').classList.remove('show');
        }

        // Social Sharing
        function shareOnWhatsApp() {
            const text = 'تعلم البرمجة مجاناً مع أكاديمية البرمجة! 🎓';
            const url = window.location.href;
            window.open(`https://wa.me/?text=${encodeURIComponent(text + ' ' + url)}`, '_blank');
        }

        function shareOnTelegram() {
            const text = 'تعلم البرمجة مجاناً مع أكاديمية البرمجة!';
            const url = window.location.href;
            window.open(`https://t.me/share/url?url=${encodeURIComponent(url)}&text=${encodeURIComponent(text)}`, '_blank');
        }

        function shareOnTwitter() {
            const text = 'تعلم البرمجة مجاناً مع أكاديمية البرمجة!';
            const url = window.location.href;
            window.open(`https://twitter.com/intent/tweet?text=${encodeURIComponent(text)}&url=${encodeURIComponent(url)}`, '_blank');
        }

        function shareOnFacebook() {
            const url = window.location.href;
            window.open(`https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(url)}`, '_blank');
        }

        // Utility Functions
        function showNotifications() {
            showToast('لديك 3 إشعارات جديدة! 🔔', 'info');
        }

        function openChat() {
            window.open('https://wa.me/966774633282?text=مرحباً، أحتاج مساعدة في أكاديمية البرمجة 👋', '_blank');
        }

        function openForum() {
            showToast('جاري تحضير منتدى المناقشات...', 'info');
        }

        function bookSession() {
            if (!isSignedIn) {
                openModal();
                return;
            }
            showToast('جاري فتح نظام حجز الجلسات...', 'info');
        }

        function showToast(message, type = 'success') {
            const toast = document.createElement('div');
            toast.className = `toast ${type}`;
            toast.textContent = message;
            document.body.appendChild(toast);
            
            setTimeout(() => {
                toast.classList.add('show');
            }, 100);
            
            setTimeout(() => {
                toast.classList.remove('show');
                setTimeout(() => {
                    document.body.removeChild(toast);
                }, 300);
            }, 3000);
        }

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Animation on Scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            setTimeout(() => {
                showToast('مرحباً بك في أكاديمية البرمجة المطورة! 🚀', 'success');
            }, 1000);
        });

        // Close modal when clicking outside
        window.onclick = function(event) {
            const modal = document.getElementById('authModal');
            if (event.target === modal) {
                closeModal();
            }
        };
    </script>
</body>
</html>
