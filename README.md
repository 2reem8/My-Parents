<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>العائلة العزيزة</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f2f2f2;
            text-align: center;
            margin: 0;
            padding: 0;
            position: relative;
        }
        header {
            background-color: #ffcccc;
            padding: 20px;
        }
        header h1 {
            color: #7a3e48;
            margin: 0;
        }
        nav {
            margin: 20px;
        }
        nav button {
            margin: 5px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            color: white;
            font-size: 16px;
            transition: background-color 0.3s ease, transform 0.3s ease;
        }
        nav button:hover {
            transform: scale(1.1);
        }
        .btn-mom {
            background-color: #ff9999;
        }
        .btn-mom:hover {
            background-color: #ff6666;
        }
        .btn-dad {
            background-color: #66b3ff;
        }
        .btn-dad:hover {
            background-color: #3399ff;
        }
        .btn-brother {
            background-color: #4CAF50;
        }
        .btn-brother:hover {
            background-color: #45a049;
        }
        .btn-sister {
            background-color: #9932cc;
        }
        .btn-sister:hover {
            background-color: #8a2be2;
        }
        section {
            padding: 20px;
            margin: 20px;
            border-radius: 10px;
            background-color: #fff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        footer {
            background-color: #ffe6e6;
            padding: 20px;
        }
        footer p {
            margin: 0;
            color: #7a3e48;
        }
        .heart {
            animation: float 2s infinite;
            position: absolute;
            font-size: 50px;
            z-index: 1;
        }
        .heart-mom {
            color: #ff6666;
        }
        .heart-dad {
            color: #3399ff;
        }
        .heart-brother {
            color: #4CAF50;
        }
        .heart-sister {
            color: #9932cc;
        }
        @keyframes float {
            0% {
                transform: translateY(0);
                opacity: 1;
            }
            100% {
                transform: translateY(-20px);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>العائلة العزيزة</h1>
    </header>
    <nav>
        <button class="btn-mom" onclick="showSection('mom')">أمي الحبيبة</button>
        <button class="btn-dad" onclick="showSection('dad')">أبي العزيز</button>
        <button class="btn-brother" onclick="showSection('brother')">الأخ العزيز</button>
        <button class="btn-sister" onclick="showSection('sister')">الأخت العزيزة</button>
    </nav>
    <section id="content">
        <h2>مرحبًا بك في صفحة العائلة</h2>
        <p>هنا تجد كل ما يتعلق بأفراد العائلة ودورهم العظيم في حياتنا.</p>
    </section>
    <footer>
        <p>© 2024 صفحة العائلة - جميع الحقوق محفوظة</p>
    </footer>
    <script>
        const messages = {
            mom: {
                message: "أمي الحبيبة، أنتِ النور الذي يضيء حياتي، شكراً لكل شيء تقدمينه لي بحب وعطاء.",
                poetry: "إذا ما جئتُ لأكتبَ حبًّا، فكل حروفي عاجزةٌ أن تُوفيكِ وصفًا.",
                advice: "احترمي أطفالك واستمعي لهم، اجعلي الحب والتوجيه هما أساس العلاقة."
            },
            dad: {
                message: "أبي العزيز، أنت السند والقوة، شكراً لحمايتك لنا دائمًا.",
                poetry: "يا أبي الحبيب، أنت القدوة والنجمة التي تضيء سمائي.",
                advice: "كن قدوة حسنة لأطفالك وتواصل معهم بلطف واحترام."
            },
            brother: {
                message: "أخي العزيز، أنت السند والصديق الذي لا يعوّض.",
                poetry: "أخي هو النور الذي يضيء دربي، وصديق العمر الذي لا يخذلني.",
                advice: "كن داعماً لعائلتك واحتفظ بروح المسؤولية والمحبة."
            },
            sister: {
                message: "أختي الحبيبة، أنتِ القلب الدافئ والملاك الحارس لي.",
                poetry: "أختي هي زهرة العمر ورفيقة الدرب، حضورها يملأ الحياة سعادة.",
                advice: "كوني دائماً الحنونة التي تضيف السعادة للعائلة."
            }
        };

        function showSection(role) {
            const content = document.getElementById('content');
            content.innerHTML = `
                <h2>${role === 'mom' ? 'أمي الحبيبة' : role === 'dad' ? 'أبي العزيز' : role === 'brother' ? 'الأخ العزيز' : 'الأخت العزيزة'}</h2>
                <button onclick="showSubSection('${role}', 'message')">رسالة</button>
                <button onclick="showSubSection('${role}', 'poetry')">شعر</button>
                <button onclick="showSubSection('${role}', 'advice')">نصائح</button>
            `;
            createHeart(role);
        }

        function showSubSection(role, section) {
            const content = document.getElementById('content');
            content.innerHTML = `<h2>${section === 'message' ? 'رسالة' : section === 'poetry' ? 'شعر' : 'نصائح'}</h2><p>${messages[role][section]}</p>`;
        }

        function createHeart(role) {
            const heart = document.createElement('div');
            heart.classList.add('heart', `heart-${role}`);
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 3 + 's';
            heart.textContent = '❤';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
    </script>
</body>
</html>
