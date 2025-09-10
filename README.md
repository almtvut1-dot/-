# -<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>توزيع زوار واتساب</title>
  <script>
    // أرقام الواتساب بصيغة دولية صحيحة (wa.me)
    const numbers = [
      "",
      "",
      "https://wa.me/964 7830434655,
      "https://wa.me/964 7872588256"
    ];

    function redirectVisitor() {
      try {
        // قراءة العداد من التخزين المحلي
        const raw = localStorage.getItem("whatsappCounter");
        const counter = Number.isInteger(parseInt(raw, 10)) ? parseInt(raw, 10) : 0;

        // اختيار الرابط بالتناوب
        const link = numbers[counter % numbers.length];

        // تحديث العداد
        localStorage.setItem("whatsappCounter", String(counter + 1));

        // تنفيذ التحويل الفوري
        window.location.assign(link);
      } catch (err) {
        // في حال منع التخزين المحلي أو خطأ، التحويل لأول رقم
        window.location.assign(numbers);
      }
    }

    // تشغيل التحويل بمجرد جاهزية DOM لضمان التنفيذ المبكر
    document.addEventListener("DOMContentLoaded", redirectVisitor);
  </script>
</head>
<body>
  <h2>جارٍ تحويلك إلى الواتساب...</h2>
  <noscript>الرجاء تفعيل الجافاسكربت لإتمام التحويل.</noscript>
</body>
</html>
اهلا وسهلا
