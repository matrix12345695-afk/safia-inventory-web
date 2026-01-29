[form.html](https://github.com/user-attachments/files/24930743/form.html)
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Инвентаризация</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <script src="https://telegram.org/js/telegram-web-app.js"></script>

  <style>
    body {
      margin: 0;
      padding: 16px;
      background: #0f0f0f;
      color: #fff;
      font-family: system-ui;
    }

    h1 {
      font-size: 20px;
      margin-bottom: 12px;
    }

    .box {
      background: #1c1c1c;
      border-radius: 12px;
      padding: 16px;
    }
  </style>
</head>

<body>

<h1 id="title">Инвентаризация</h1>

<div class="box">
  <p>Форма открыта успешно ✅</p>
  <p>Раздел: <b id="section"></b></p>
</div>

<script>
  const tg = Telegram.WebApp;
  tg.ready();
  tg.expand();

  const params = new URLSearchParams(window.location.search);
  const section = params.get("section") || "неизвестно";

  document.getElementById("section").textContent = section;

  const titles = {
    kitchen: "🧑‍🍳 Кухня",
    bar: "🍹 Бар",
    shop: "🏪 Магазин",
    freezer: "❄️ Морозилка"
  };

  document.getElementById("title").textContent =
    titles[section] || "Инвентаризация";
</script>

</body>
</html>
