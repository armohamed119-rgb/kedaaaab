<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>اختبار الصدق</title>
  <style>
    body { font-family: Arial; direction: rtl; text-align: right; background:#f5f5f5; }
    .box { max-width: 500px; margin: 50px auto; padding: 20px; background: white; border-radius: 10px; }
    button { padding: 10px; margin-top: 10px; cursor: pointer; }
  </style>
</head>
<body>

<div class="box">
  <h2>اختبار الصدق (للتسلية فقط)</h2>

  <p>1. في العادة، كم مرة تكذب في اليوم؟</p>
  <input type="number" id="q1" min="0" value="0">

  <p>2. هل سبق وكذبت في موقف بسيط لتجنب المشاكل؟ (0 لا / 1 نعم)</p>
  <input type="number" id="q2" min="0" max="1" value="0">

  <p>3. هل تعتبر نفسك صريح غالباً؟ (0 لا / 1 نعم)</p>
  <input type="number" id="q3" min="0" max="1" value="1">

  <button onclick="result()">شوف النتيجة</button>

  <h3 id="out"></h3>
</div>

<script>
function result() {
  let q1 = parseInt(document.getElementById("q1").value);
  let q2 = parseInt(document.getElementById("q2").value);
  let q3 = parseInt(document.getElementById("q3").value);

  let score = q1 + (q2 * 2) + ((1 - q3) * 2);

  let msg = "";

  if (score <= 1) {
    msg = "تبان شخص صريح غالباً 👍 (لكن هذا غير تحليل تقريبي)";
  } else if (score <= 3) {
    msg = "عندك كذب خفيف في مواقف معينة 🙂";
  } else {
    msg = "يبدو أنك تكذب بزاف نسبياً 😅 (تقييم للتسلية فقط)";
  }

  document.getElementById("out").innerText = msg;
}
</script>

</body>
</html>