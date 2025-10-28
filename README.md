<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0" />
  <title>Brikola — تسجيل الدخول</title>

  <style>
    :root {
      --accent: #ffb86b;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html, body {
      height: 100%;
      width: 100%;
      overflow: hidden;
      font-family: 'Poppins', sans-serif;
    }

    /* خلفية الصورة مع تأثير بارالاكس */
    body {
      background: url("copilot_image_1761237877305.webp") center/cover no-repeat fixed;
      position: relative;
    }

    /* طبقة تغيم */
    .overlay {
      position: absolute;
      inset: 0;
      background: rgba(0,0,0,0.55);
      backdrop-filter: blur(2px);
    }

    /* تأثيرات إضاءة متحركة */
    .glow {
      position: absolute;
      width: 450px;
      height: 450px;
      background: radial-gradient(circle, rgba(0,255,146,0.25), transparent 70%);
      filter: blur(80px);
      animation: moveGlow 10s infinite alternate ease-in-out;
    }
    .glow:nth-child(2) {
      left: 70%;
      bottom: 10%;
      animation-delay: 4s;
    }

    @keyframes moveGlow {
      0% { transform: translateY(0px) translateX(0px); }
      100% { transform: translateY(-40px) translateX(-50px); }
    }

    /* صندوق تسجيل الدخول */
    .login-container {
      position: relative;
      z-index: 10;
      background: rgba(255,255,255,0.08);
      border-radius: 20px;
      padding: 2rem;
      width: 90%;
      max-width: 400px;
      margin: auto;
      top: 12%;
      color: white;
      text-align: center;
      backdrop-filter: blur(12px);
      box-shadow: 0 8px 25px rgba(0,0,0,0.4);
      animation: fadeIn 1.2s ease;
    }

    .login-container h1 {
      margin-bottom: 1.5rem;
      font-size: 1.9rem;
    }

    input {
      width: 100%;
      padding: 0.8rem;
      margin-bottom: 1rem;
      border-radius: 10px;
      border: none;
      outline: none;
      background: rgba(255,255,255,0.15);
      color: white;
      font-size: 1rem;
    }

    button {
      width: 100%;
      padding: 0.9rem;
      border: none;
      border-radius: 10px;
      background: var(--accent);
      color: #111;
      font-size: 1.1rem;
      font-weight: bold;
      cursor: pointer;
      transition: .3s ease-in-out;
    }
    button:hover {
      transform: scale(1.06);
      background: #ffd79b;
    }

    /* الأزرار الخاصة باللغات */
    .lang-switch {
      display: flex;
      justify-content: center;
      gap: 0.4rem;
      margin: 1rem 0;
    }
    .lang-switch button {
      padding: 0.45rem 1rem;
      border-radius: 8px;
      font-size: 0.9rem;
      border: 1px solid rgba(255,255,255,0.4);
      background: rgba(255,255,255,0.18);
      color: white;
    }
    .lang-switch button.active {
      background: var(--accent);
      color: #000;
      border: none;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(25px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 600px) {
      .login-container {
        padding: 1.4rem;
        top: 8%;
      }
      .login-container h1 {
        font-size: 1.5rem;
      }
    }
  </style>
</head>

<body>

  <div class="overlay"></div>
  <div class="glow"></div>
  <div class="glow"></div>

  <div class="lang-switch">
    <button id="lang-ar" class="active">AR</button>
    <button id="lang-en">EN</button>
    <button id="lang-fr">FR</button>
  </div>

  <div class="login-container">
    <h1 id="title">تسجيل الدخول</h1>
    <input id="username" type="text" placeholder="اسم المستخدم" />
    <input id="phone" type="tel" placeholder="رقم الهاتف" />
    <input id="password" type="password" placeholder="كلمة المرور" />
    <button onclick="doLogin()" id="login-btn">دخول</button>
  </div>

<script>
  const translations = {
    ar: { title: 'تسجيل الدخول', username: 'اسم المستخدم', phone: 'رقم الهاتف', password: 'كلمة المرور', login: 'دخول' },
    en: { title: 'Login', username: 'Username', phone: 'Phone number', password: 'Password', login: 'Sign in' },
    fr: { title: 'Connexion', username: 'Nom d’utilisateur', phone: 'Numéro de téléphone', password: 'Mot de passe', login: 'Se connecter' }
  };

  function switchLang(lang) {
    document.documentElement.lang = lang;
    document.documentElement.dir = (lang === 'ar') ? 'rtl' : 'ltr';
    document.getElementById('title').textContent = translations[lang].title;
    document.getElementById('username').placeholder = translations[lang].username;
    document.getElementById('phone').placeholder = translations[lang].phone;
    document.getElementById('password').placeholder = translations[lang].password;
    document.getElementById('login-btn').textContent = translations[lang].login;

    document.querySelectorAll('.lang-switch button').forEach(btn => btn.classList.remove('active'));
    document.getElementById(`lang-${lang}`).classList.add('active');
  }

  document.getElementById('lang-ar').onclick = () => switchLang('ar');
  document.getElementById('lang-en').onclick = () => switchLang('en');
  document.getElementById('lang-fr').onclick = () => switchLang('fr');

  function doLogin() {
    window.location.href = "l;ol.html";
  }
</script>

</body>
</html>
