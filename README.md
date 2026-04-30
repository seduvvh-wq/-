
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>زَادُ المُكَلَّف</title>
    <style>
        :root {
            --primary: #1a3a5f;
            --accent: #c5a059;
            --bg: #f8f9fa;
            --white: #ffffff;
        }
        body {
            direction: rtl;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg);
            margin: 0;
            line-height: 1.6;
        }
        header {
            background: var(--primary);
            color: white;
            text-align: center;
            padding: 40px 20px;
            border-bottom: 5px solid var(--accent);
        }
        .container {
            padding: 20px;
            max-width: 800px;
            margin: auto;
        }
        .search-box {
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            border: 2px solid var(--accent);
            border-radius: 8px;
            font-size: 16px;
        }
        .fatwa-card {
            background: var(--white);
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 15px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            border-right: 6px solid var(--primary);
            transition: 0.3s;
        }
        .fatwa-card:hover {
            transform: translateY(-5px);
        }
        .fatwa-card h3 {
            color: var(--primary);
            margin-top: 0;
        }
        .footer {
            text-align: center;
            padding: 20px;
            font-size: 14px;
            color: #666;
        }
    </style>
</head>
<body>

<header>
    <h1>زَادُ المُكَلَّف</h1>
    <p>أحكام وفتاوى المذهب الجعفري الكرام</p>
</header>

<div class="container">
    <input type="text" id="searchInput" class="search-box" placeholder="ابحث في الأحكام والفتاوى...">

    <div id="results">
        <div class="fatwa-card">
            <h3>الصلاة في السفر</h3>
            <p>يجب القصر في الصلاة الرباعية إذا تحققت شروط السفر الشرعي...</p>
        </div>
        
        <div class="fatwa-card">
            <h3>أحكام الصوم</h3>
            <p>يعتبر الصوم من الواجبات المؤكدة، ويبدأ من طلوع الفجر الصادق إلى الغروب الشرعي...</p>
        </div>
    </div>
</div>

<div class="footer">
    هذا الموقع مخصص لنشر المعرفة الفقهية
</div>

<script>
    const searchInput = document.getElementById('searchInput');
    const cards = document.querySelectorAll('.fatwa-card');

    searchInput.addEventListener('input', function() {
        const filter = searchInput.value.toLowerCase();
        cards.forEach(card => {
            const text = card.textContent.toLowerCase();
            card.style.display = text.includes(filter) ? "block" : "none";
        });
    });
</script>

</body>
</html>
