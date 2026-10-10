<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#080808" />
  <meta name="description" content="Cloudasic — создание стильных BIO-сайтов и современных веб-страниц." />
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='385 392 485 292'%3E%3Crect x='385' y='392' width='485' height='292' fill='%23080808'/%3E%3Cpath d='M558 677H498A95 95 0 0 1 506 492A130 130 0 1 1 760 530L757 548A70 70 0 1 1 785 677H595V513' fill='none' stroke='white' stroke-width='22' stroke-linejoin='round'/%3E%3C/svg%3E" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet" />
  <meta property="og:title" content="Cloudasic — цифровое пространство" />
  <meta property="og:description" content="Стильные BIO-сайты и современные веб-страницы." />
  <title>Cloudasic — цифровое пространство</title>
  <style>
    :root {
      --bg: #080808;
      --panel: rgba(255,255,255,.045);
      --panel-hover: rgba(255,255,255,.075);
      --text: #f5f5f5;
      --muted: #a4a4a4;
      --line: rgba(255,255,255,.12);
      --glow: rgba(255,255,255,.13);
      --radius: 22px;
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; scroll-padding-top: 88px; }
    body {
      margin: 0; background: var(--bg); color: var(--text);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.6; overflow-x: hidden;
    }
    body::before {
      content: ""; position: fixed; inset: -20%; z-index: -2; pointer-events: none;
      background:
        radial-gradient(ellipse at 18% 10%, rgba(255,255,255,.075), transparent 32%),
        radial-gradient(ellipse at 82% 38%, rgba(255,255,255,.045), transparent 28%),
        radial-gradient(ellipse at 45% 88%, rgba(255,255,255,.035), transparent 30%);
      animation: ambient 18s ease-in-out infinite alternate;
    }
    body::after {
      content: ""; position: fixed; inset: 0; z-index: -1; pointer-events: none; opacity: .12;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.13'/%3E%3C/svg%3E");
    }
    a { color: inherit; text-decoration: none; }
    button { font: inherit; }
    .container { width: min(1080px, calc(100% - 36px)); margin: 0 auto; }
    .header {
      position: sticky; top: 0; z-index: 20; backdrop-filter: blur(18px);
      background: rgba(8,8,8,.74); border-bottom: 1px solid rgba(255,255,255,.07);
    }
    .nav { min-height: 76px; display: flex; align-items: center; justify-content: space-between; gap: 20px; }
    .brand { display: inline-flex; align-items: center; gap: 12px; min-width: 0; }
    .brand-logo { width: 46px; height: auto; color: #fff; flex: none; filter: drop-shadow(0 0 14px rgba(255,255,255,.25)); transition: transform .35s ease, filter .35s ease; }
    .brand:hover .brand-logo { transform: translateY(-2px); filter: drop-shadow(0 0 18px rgba(255,255,255,.5)); }
    .brand-name { font-family: Montserrat, Inter, sans-serif; font-size: 15px; font-weight: 400; letter-spacing: .42em; text-transform: uppercase; white-space: nowrap; }
    .nav-links { display: flex; align-items: center; gap: 24px; color: #c5c5c5; font-size: 13px; }
    .nav-links a { transition: color .2s ease; }
    .nav-links a:hover { color: white; }
    .menu-toggle { display: none; border: 1px solid var(--line); background: var(--panel); color: white; border-radius: 12px; padding: 9px 12px; }
    .hero { min-height: 640px; display: grid; align-items: center; padding: 90px 0 82px; position: relative; }
    .hero-content { max-width: 790px; }
    .eyebrow {
      display: inline-flex; align-items: center; gap: 9px; padding: 8px 13px;
      border: 1px solid var(--line); border-radius: 999px; color: #c8c8c8;
      font-size: 12px; letter-spacing: .06em; background: rgba(255,255,255,.025);
    }
    .status-dot { width: 6px; height: 6px; border-radius: 50%; background: #eee; box-shadow: 0 0 12px #fff; }
    h1 { margin: 24px 0 18px; font-size: clamp(43px, 8vw, 86px); line-height: .99; letter-spacing: -.065em; font-weight: 560; }
    .gradient-text { color: #a8a8a8; background: linear-gradient(100deg,#fff 5%,#999 55%,#eee 100%); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; }
    .hero p { max-width: 570px; color: var(--muted); font-size: clamp(15px, 2vw, 18px); margin: 0; }
    .hero-actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 30px; }
    .button {
      display: inline-flex; justify-content: center; align-items: center; gap: 10px; min-height: 48px;
      border: 1px solid var(--line); border-radius: 14px; padding: 0 19px;
      font-size: 14px; font-weight: 550; transition: transform .22s ease, background .22s ease, box-shadow .22s ease, border-color .22s ease;
      cursor: pointer;
    }
    .button:hover { transform: translateY(-2px); }
    .button-primary { color: #080808; background: #f4f4f4; border-color: #f4f4f4; box-shadow: 0 0 26px rgba(255,255,255,.10); }
    .button-primary:hover { background: white; box-shadow: 0 0 32px rgba(255,255,255,.2); }
    .button-secondary { background: rgba(255,255,255,.035); color: #f5f5f5; }
    .button-secondary:hover { background: rgba(255,255,255,.09); border-color: rgba(255,255,255,.25); }
    .hero-orb {
      position: absolute; width: 230px; height: 230px; right: 4%; top: 24%; border-radius: 50%;
      border: 1px solid rgba(255,255,255,.1); opacity: .9; pointer-events: none;
      background: radial-gradient(circle at 35% 30%, rgba(255,255,255,.12), rgba(255,255,255,.015) 45%, transparent 68%);
      box-shadow: inset 0 0 65px rgba(255,255,255,.035), 0 0 100px rgba(255,255,255,.035);
      animation: float 8s ease-in-out infinite;
      display: grid; place-items: center;
    }
    .orb-logo { position: relative; z-index: 1; width: 62%; height: auto; aspect-ratio: 485 / 292; overflow: visible; color: #fff; filter: drop-shadow(0 0 22px rgba(255,255,255,.35)); }
    .orb-logo path { stroke-dasharray: 1; stroke-dashoffset: 1; animation: draw 2.6s .3s cubic-bezier(.6,.1,.2,1) forwards; }
    @keyframes draw { to { stroke-dashoffset: 0; } }
    .hero-orb::before, .hero-orb::after { content:""; position:absolute; inset: 12%; border:1px solid rgba(255,255,255,.09); border-radius:50%; transform:rotateX(65deg) rotateZ(22deg); }
    .hero-orb::after { inset: 0; transform: rotateY(66deg) rotateZ(-28deg); }
    section { padding: 72px 0; }
    .section-head { display: flex; justify-content: space-between; align-items: end; gap: 22px; margin-bottom: 28px; }
    .kicker { color: #8e8e8e; font-size: 11px; letter-spacing: .18em; text-transform: uppercase; }
    h2 { font-size: clamp(28px, 5vw, 43px); line-height: 1.1; letter-spacing: -.045em; font-weight: 540; margin: 9px 0 0; }
    .section-description { max-width: 420px; color: var(--muted); font-size: 14px; margin: 0; }
    .grid { display: grid; grid-template-columns: repeat(3, minmax(0,1fr)); gap: 14px; }
    .card {
      position: relative; padding: 24px; border: 1px solid var(--line); border-radius: var(--radius);
      background: linear-gradient(145deg, rgba(255,255,255,.055), rgba(255,255,255,.018));
      overflow: hidden; transition: transform .25s ease, border-color .25s ease, background .25s ease;
    }
    .card::before { content:""; position:absolute; inset:0; background: radial-gradient(circle at 0 0, rgba(255,255,255,.08), transparent 55%); opacity:0; transition:opacity .25s ease; pointer-events:none; }
    .card:hover { transform: translateY(-4px); border-color: rgba(255,255,255,.25); background: var(--panel-hover); }
    .card:hover::before { opacity:1; }
    .card-icon { width: 43px; height: 43px; border: 1px solid var(--line); background: rgba(255,255,255,.04); border-radius: 14px; display:grid; place-items:center; margin-bottom: 24px; color:#eee; }
    .card-icon svg { width: 20px; height: 20px; }
    h3 { font-size: 17px; letter-spacing: -.02em; font-weight: 550; margin: 0 0 9px; }
    .card p { font-size: 13px; color: var(--muted); margin: 0 0 20px; }
    .text-link { display: inline-flex; align-items:center; gap:8px; font-size:13px; color:#f2f2f2; }
    .text-link span { transition: transform .2s ease; }
    .text-link:hover span { transform: translateX(4px); }
    .about-panel { display:grid; grid-template-columns: 1.15fr .85fr; gap: 22px; align-items: stretch; }
    .about-copy, .wallet-card, .contact-panel { border:1px solid var(--line); border-radius:var(--radius); background:var(--panel); padding:clamp(23px,4vw,36px); }
    .about-copy p { color:var(--muted); font-size:15px; max-width:600px; margin:18px 0 0; }
    .principles { display:grid; gap:12px; margin-top:26px; }
    .principle { display:flex; align-items:center; gap:11px; color:#d5d5d5; font-size:13px; }
    .check { width:19px; height:19px; border:1px solid var(--line); border-radius:50%; display:grid; place-items:center; color:#fff; font-size:11px; flex:none; }
    .wallet-card { display:flex; flex-direction:column; justify-content:space-between; gap:25px; }
    .wallet-label { color:#9b9b9b; font-size:12px; letter-spacing:.12em; text-transform:uppercase; }
    .wallet-address { overflow-wrap:anywhere; color:#e9e9e9; font-family:ui-monospace, SFMono-Regular, Menlo, monospace; font-size:12px; line-height:1.8; padding:15px; border:1px solid rgba(255,255,255,.09); border-radius:13px; background:rgba(0,0,0,.25); }
    .contact-panel { display:flex; align-items:center; justify-content:space-between; gap:24px; background: radial-gradient(ellipse at 100% 0%, rgba(255,255,255,.07), transparent 55%), var(--panel); }
    .contact-panel p { color:var(--muted); font-size:14px; margin:12px 0 0; max-width:470px; }
    .contact-actions { display:flex; flex-wrap:wrap; gap:10px; flex:none; }
    .notice { min-height:20px; color:#d7d7d7; font-size:12px; margin-top:10px; }
    footer { border-top:1px solid rgba(255,255,255,.08); padding:25px 0 32px; color:#777; font-size:12px; }
    .footer-inner { display:flex; justify-content:space-between; align-items:center; gap:15px; }
    .footer-links { display:flex; gap:17px; flex-wrap:wrap; }
    .footer-links a:hover { color:#eee; }
    .reveal { opacity:0; transform:translateY(18px); transition: opacity .7s ease, transform .7s ease; }
    .reveal.visible { opacity:1; transform:translateY(0); }
    @keyframes float { 0%,100% { transform:translateY(0) rotate(0deg); } 50% { transform:translateY(-15px) rotate(4deg); } }
    @keyframes ambient { from { transform:translate3d(-1%,0,0) scale(1); } to { transform:translate3d(1%,1%,0) scale(1.05); } }
    @media (max-width: 760px) {
      .container { width:min(100% - 30px, 560px); }
      .nav { min-height:68px; }
      .brand-logo { width:40px; }
      .brand-name { font-size:12px; letter-spacing:.34em; }
      .menu-toggle { display:block; }
      .nav-links { display:none; position:absolute; top:68px; left:15px; right:15px; padding:15px; border:1px solid var(--line); border-radius:17px; background:rgba(12,12,12,.96); flex-direction:column; align-items:stretch; gap:0; box-shadow:0 18px 50px rgba(0,0,0,.45); }
      .nav-links.open { display:flex; }
      .nav-links a { padding:12px 10px; border-radius:9px; }
      .nav-links a:hover { background:rgba(255,255,255,.06); }
      .hero { min-height:590px; padding:76px 0 70px; }
      .hero-orb { width:120px; height:120px; top:18px; right:15px; opacity:.55; }
      .hero-content { position:relative; z-index:1; }
      .hero p { max-width:440px; }
      section { padding:55px 0; }
      .section-head { display:block; }
      .section-description { margin-top:14px; }
      .grid { grid-template-columns:1fr; }
      .card { padding:22px; }
      .card-icon { margin-bottom:18px; }
      .about-panel { grid-template-columns:1fr; }
      .contact-panel { display:block; }
      .contact-actions { margin-top:23px; }
      .contact-actions .button { flex:1 1 100%; }
      .footer-inner { align-items:flex-start; flex-direction:column; }
    }

    .faq { display:grid; gap:10px; max-width:760px; }
    .faq details { border:1px solid var(--line); border-radius:16px; background:var(--panel); padding:0 20px; transition:background .2s ease; }
    .faq details[open] { background:var(--panel-hover); }
    .faq summary { cursor:pointer; list-style:none; padding:18px 0; font-size:15px; display:flex; justify-content:space-between; gap:16px; }
    .faq summary::-webkit-details-marker { display:none; }
    .faq summary::after { content:"+"; color:#aaa; transition:transform .2s ease; }
    .faq details[open] summary::after { transform:rotate(45deg); }
    .faq details p { color:var(--muted); font-size:14px; margin:0 0 18px; }
    
    #bgCanvas { position: fixed; inset: 0; width: 100%; height: 100%; z-index: -1; pointer-events: none; }
    .bg-grid { position: fixed; inset: 0; z-index: -2; pointer-events: none; opacity: .5;
      background-image: linear-gradient(rgba(255,255,255,.035) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,.035) 1px, transparent 1px);
      background-size: 56px 56px;
      -webkit-mask-image: radial-gradient(ellipse at 50% 30%, #000 10%, transparent 70%); mask-image: radial-gradient(ellipse at 50% 30%, #000 10%, transparent 70%); }
    .bg-glow { position: fixed; z-index: -2; pointer-events: none; border-radius: 50%; filter: blur(80px); background: rgba(255,255,255,.07); animation: drift 22s ease-in-out infinite alternate; }
    .bg-glow.g1 { width: 420px; height: 420px; top: -120px; left: -100px; }
    .bg-glow.g2 { width: 360px; height: 360px; bottom: -120px; right: -80px; animation-duration: 28s; animation-direction: alternate-reverse; }
    @keyframes drift { from { transform: translate(0,0) scale(1); } to { transform: translate(60px,40px) scale(1.2); } }
    @media (max-width:760px) { .bg-glow { filter: blur(60px); } .bg-glow.g1 { width: 280px; height: 280px; } .bg-glow.g2 { width: 240px; height: 240px; } }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { scroll-behavior:auto !important; animation-duration:.01ms !important; animation-iteration-count:1 !important; transition-duration:.01ms !important; }
      .reveal { opacity:1; transform:none; }
      .orb-logo path { stroke-dashoffset:0; }
    }
  </style>
</head>
<body>
  <div class="bg-grid" aria-hidden="true"></div>
  <div class="bg-glow g1" aria-hidden="true"></div>
  <div class="bg-glow g2" aria-hidden="true"></div>
  <canvas id="bgCanvas" aria-hidden="true"></canvas>
  <header class="header">
    <div class="container nav">
      <a class="brand" href="#home" aria-label="Cloudasic — главная">
        <svg class="brand-logo" viewBox="385 392 485 292" fill="none" stroke="currentColor" stroke-width="15" stroke-linejoin="round" role="img" aria-label="Логотип Cloudasic"><path d="M558 677H498A95 95 0 0 1 506 492A130 130 0 1 1 760 530L757 548A70 70 0 1 1 785 677H595V513"/></svg>
        <span class="brand-name">cloudasic</span>
      </a>
      <button class="menu-toggle" id="menuToggle" aria-expanded="false" aria-controls="navLinks">Меню</button>
      <nav class="nav-links" id="navLinks">
        <a href="#services">Создание сайтов</a>
        <a href="#about">О Cloudasic</a>
        <a href="#faq">Вопросы</a>
        <a href="#wallet">Кошелёк</a>
        <a href="#contact">Связь</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="hero-orb" aria-hidden="true"><svg class="orb-logo" viewBox="385 392 485 292" fill="none" stroke="currentColor" stroke-width="15" stroke-linejoin="round" ><path pathLength="1" d="M558 677H498A95 95 0 0 1 506 492A130 130 0 1 1 760 530L757 548A70 70 0 1 1 785 677H595V513"/></svg></div>
      <div class="container hero-content reveal">
        <div class="eyebrow"><span class="status-dot"></span> Цифровые проекты и веб-дизайн</div>
        <h1>Идеи обретают<br><span class="gradient-text">цифровую форму.</span></h1>
        <p>Cloudasic — стильные BIO-сайты и современные веб-страницы с вниманием к деталям, удобству и визуальной атмосфере.</p>
        <div class="hero-actions">
          <a class="button button-primary" href="#services">Посмотреть услуги <span aria-hidden="true">↘</span></a>
          <a class="button button-secondary" href="https://t.me/cloudasic" target="_blank" rel="noopener noreferrer">Связаться в Telegram <span aria-hidden="true">↗</span></a>
        </div>
      </div>
    </section>

    <section id="services">
      <div class="container">
        <div class="section-head reveal">
          <div><div class="kicker">Что я делаю</div><h2>Создание сайтов</h2></div>
          <p class="section-description">От лаконичной личной страницы до индивидуального веб-проекта — с адаптацией под телефон и аккуратным дизайном.</p>
        </div>
        <div class="grid">
          <article class="card reveal">
            <div class="card-icon" aria-hidden="true"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="5" y="2.5" width="14" height="19" rx="3"/><path d="M9 6h6M10 18h4"/></svg></div>
            <h3>BIO-сайты</h3>
            <p>Персональная страница с информацией о тебе, ссылками и индивидуальным оформлением.</p>
            <a class="text-link" href="https://t.me/cloudasic" target="_blank" rel="noopener noreferrer">Обсудить заказ <span>↗</span></a>
          </article>
          <article class="card reveal">
            <div class="card-icon" aria-hidden="true"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="4" width="18" height="16" rx="2.5"/><path d="M3 9h18M7 6.5h.01M10 6.5h.01"/></svg></div>
            <h3>Сайты-визитки</h3>
            <p>Компактный сайт, который помогает представить человека, проект или личный бренд.</p>
            <a class="text-link" href="https://t.me/cloudasic" target="_blank" rel="noopener noreferrer">Обсудить заказ <span>↗</span></a>
          </article>
          <article class="card reveal">
            <div class="card-icon" aria-hidden="true"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M4 5.5 12 2l8 3.5v13L12 22l-8-3.5z"/><path d="m4 5.5 8 4 8-4M12 9.5V22"/></svg></div>
            <h3>Индивидуальные проекты</h3>
            <p>Необычная идея, особая атмосфера и нужные функции — детали можно обсудить лично.</p>
            <a class="text-link" href="https://t.me/cloudasic" target="_blank" rel="noopener noreferrer">Рассказать идею <span>↗</span></a>
          </article>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-head reveal"><div><div class="kicker">Немного обо мне</div><h2>О Cloudasic</h2></div></div>
        <div class="about-panel">
          <div class="about-copy reveal">
            <h3>Создаю и настраиваю цифровые проекты</h3>
            <p>Я работаю над сайтами с помощью ИИ и специальных приложений, а затем самостоятельно корректирую и дорабатываю код под свою задумку. Для меня важны визуальный стиль, удобство и внимание к мелочам.</p>
            <div class="principles">
              <div class="principle"><span class="check">✓</span> Дизайн с характером и без лишнего шума</div>
              <div class="principle"><span class="check">✓</span> Удобное отображение на смартфонах</div>
              <div class="principle"><span class="check">✓</span> Постепенная доработка под идею проекта</div>
            </div>
          </div>
          <div class="wallet-card reveal" id="wallet">
            <div>
              <div class="wallet-label">TON · Кошелёк</div>
              <h3 style="margin-top:12px">Мой кошелёк</h3>
              <p style="color:var(--muted);font-size:13px;margin:0 0 18px">Адрес для копирования</p>
              <div class="wallet-address" id="walletAddress">UQDjMXuHT4gYTMj-K-ekvpaJaOiSPmt7Pg9bCI65OdaVdPG1</div>
            </div>
            <div>
              <button class="button button-secondary" id="copyWallet" type="button" style="width:100%">Скопировать адрес <span aria-hidden="true">⧉</span></button>
              <div class="notice" id="copyNotice" role="status" aria-live="polite"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="faq">
      <div class="container">
        <div class="section-head reveal"><div><div class="kicker">FAQ</div><h2>Частые вопросы</h2></div></div>
        <div class="faq reveal">
          <details><summary>Сколько занимает создание сайта?</summary><p>Зависит от сложности: простые BIO-страницы делаются быстро, для индивидуальных проектов сроки обсуждаются лично.</p></details>
          <details><summary>Сайт будет удобен на телефоне?</summary><p>Да, все страницы адаптируются под смартфоны и планшеты.</p></details>
          <details><summary>Можно ли вносить правки после готовности?</summary><p>Да, доработки под вашу идею входят в процесс — просто напишите в Telegram.</p></details>
          <details><summary>Как оформить заказ?</summary><p>Напишите мне в Telegram, расскажите о задумке — обсудим детали и условия.</p></details>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="contact-panel reveal">
          <div>
            <div class="kicker">Остаёмся на связи</div>
            <h2>Есть идея для сайта?</h2>
            <p>Напиши мне, расскажи о задумке — обсудим, каким может быть твой проект.</p>
          </div>
          <div class="contact-actions">
            <a class="button button-primary" href="https://t.me/cloudasic" target="_blank" rel="noopener noreferrer">Мой Telegram ↗</a>
            <a class="button button-secondary" href="https://t.me/loffi_NFT" target="_blank" rel="noopener noreferrer">Наше сообщество ↗</a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <span style="display:inline-flex;align-items:center;gap:10px"><svg viewBox="385 392 485 292" width="22" fill="none" stroke="currentColor" stroke-width="22" stroke-linejoin="round" aria-hidden="true"><path d="M558 677H498A95 95 0 0 1 506 492A130 130 0 1 1 760 530L757 548A70 70 0 1 1 785 677H595V513"/></svg>© <span id="year"></span> cloudasic. Цифровое пространство.</span>
      <div class="footer-links">
        <a href="https://t.me/cloudasic" target="_blank" rel="noopener noreferrer">Telegram</a>
        <a href="https://t.me/loffi_NFT" target="_blank" rel="noopener noreferrer">Сообщество</a>
        <a href="#home">Наверх ↑</a>
      </div>
    </div>
  </footer>

  <script>

    (function () {
      const c = document.getElementById('bgCanvas');
      const ctx = c.getContext('2d');
      const reduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
      let w, h, dpr, pts = [], mouse = { x: -999, y: -999 };
      function resize() {
        dpr = Math.min(window.devicePixelRatio || 1, 2);
        w = c.width = innerWidth * dpr; h = c.height = innerHeight * dpr;
        const n = Math.round(Math.min(70, innerWidth * innerHeight / 14000));
        pts = Array.from({ length: n }, () => ({
          x: Math.random() * w, y: Math.random() * h,
          vx: (Math.random() - .5) * .22 * dpr, vy: (Math.random() - .5) * .22 * dpr,
          r: (Math.random() * 1.2 + .4) * dpr, a: Math.random() * .5 + .2
        }));
      }
      function frame() {
        ctx.clearRect(0, 0, w, h);
        const maxD = 130 * dpr;
        for (const p of pts) {
          if (!reduce) { p.x += p.vx; p.y += p.vy; }
          if (p.x < 0) p.x = w; if (p.x > w) p.x = 0;
          if (p.y < 0) p.y = h; if (p.y > h) p.y = 0;
          ctx.beginPath(); ctx.arc(p.x, p.y, p.r, 0, 6.283);
          ctx.fillStyle = 'rgba(255,255,255,' + p.a + ')'; ctx.fill();
        }
        for (let i = 0; i < pts.length; i++) {
          for (let j = i + 1; j < pts.length; j++) {
            const dx = pts[i].x - pts[j].x, dy = pts[i].y - pts[j].y, d = Math.hypot(dx, dy);
            if (d < maxD) {
              ctx.strokeStyle = 'rgba(255,255,255,' + (.09 * (1 - d / maxD)) + ')';
              ctx.lineWidth = dpr * .7; ctx.beginPath();
              ctx.moveTo(pts[i].x, pts[i].y); ctx.lineTo(pts[j].x, pts[j].y); ctx.stroke();
            }
          }
          const mx = pts[i].x - mouse.x, my = pts[i].y - mouse.y, md = Math.hypot(mx, my);
          if (md < 160 * dpr) {
            ctx.strokeStyle = 'rgba(255,255,255,' + (.22 * (1 - md / (160 * dpr))) + ')';
            ctx.lineWidth = dpr; ctx.beginPath();
            ctx.moveTo(pts[i].x, pts[i].y); ctx.lineTo(mouse.x, mouse.y); ctx.stroke();
          }
        }
        if (!reduce) requestAnimationFrame(frame);
      }
      addEventListener('resize', resize);
      addEventListener('pointermove', e => { mouse.x = e.clientX * dpr; mouse.y = e.clientY * dpr; });
      addEventListener('pointerleave', () => { mouse.x = mouse.y = -999; });
      resize(); frame();
    })();

    const menuToggle = document.getElementById('menuToggle');
    const navLinks = document.getElementById('navLinks');

    menuToggle.addEventListener('click', () => {
      const isOpen = navLinks.classList.toggle('open');
      menuToggle.setAttribute('aria-expanded', String(isOpen));
    });

    navLinks.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        navLinks.classList.remove('open');
        menuToggle.setAttribute('aria-expanded', 'false');
      });
    });

    document.getElementById('year').textContent = new Date().getFullYear();

    const copyButton = document.getElementById('copyWallet');
    const walletAddress = document.getElementById('walletAddress');
    const copyNotice = document.getElementById('copyNotice');

    copyButton.addEventListener('click', async () => {
      const address = walletAddress.textContent.trim();
      try {
        await navigator.clipboard.writeText(address);
        copyNotice.textContent = 'Адрес скопирован.';
      } catch (error) {
        const range = document.createRange();
        range.selectNodeContents(walletAddress);
        const selection = window.getSelection();
        selection.removeAllRanges();
        selection.addRange(range);
        copyNotice.textContent = 'Не удалось скопировать автоматически — выдели и скопируй адрес вручную.';
      }
    });

    const revealItems = document.querySelectorAll('.reveal');
    if ('IntersectionObserver' in window && !window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
      const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
            observer.unobserve(entry.target);
          }
        });
      }, { threshold: 0.12 });
      revealItems.forEach(item => observer.observe(item));
    } else {
      revealItems.forEach(item => item.classList.add('visible'));
    }
  </script>
</body>
</html>
