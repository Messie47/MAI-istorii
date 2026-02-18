<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>МАИ истории</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    :root {
      --mai-blue: #0271FF;
      --bg-light: #ffffff;
      --bg-dark: #0b1750;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    body {
      background: #f2f5ff;
      color: #111;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      background: var(--mai-blue);
      color: #fff;
      padding: 16px 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 16px;
      position: relative;
    }

    header .logo {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    header h1 {
      font-size: 1.6rem;
      font-weight: 700;
      letter-spacing: 0.04em;
    }

    header .subtitle {
      font-size: 0.9rem;
      opacity: 0.9;
    }

    .header-logo-img {
      height: 50px;
      width: auto;
      position: absolute;
      right: 24px;
      top: 50%;
      transform: translateY(-50%);
    }

    .main-tabs {
      display: flex;
      gap: 12px;
      padding: 0 24px;
      border-bottom: 2px solid rgba(2, 113, 255, 0.1);
      background: #ffffff;
      overflow-x: auto;
    }

    .main-tab-btn {
      background: none;
      border: none;
      padding: 12px 16px;
      font-size: 0.95rem;
      color: #666;
      cursor: pointer;
      border-bottom: 3px solid transparent;
      margin-bottom: -2px;
      transition: all 0.2s ease;
      box-shadow: none;
      font-weight: 500;
      white-space: nowrap;
    }

    .main-tab-btn.active {
      color: var(--mai-blue);
      border-bottom-color: var(--mai-blue);
    }

    .main-tab-btn:hover {
      color: var(--mai-blue);
      background: rgba(2, 113, 255, 0.05);
    }

    .main-tab-content {
      display: none;
    }

    .main-tab-content.active {
      display: block;
    }

    main {
      flex: 1;
      padding: 24px;
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: minmax(0, 1.2fr) minmax(0, 0.9fr);
      gap: 24px;
      align-items: flex-start;
      width: 100%;
    }

    main.full-width {
      grid-template-columns: 1fr;
    }

    @media (max-width: 900px) {
      main {
        grid-template-columns: 1fr;
      }
      .info-card {
        max-width: 100%;
        margin-left: 0;
      }
    }

    .card {
      background: #ffffff;
      border-radius: 16px;
      padding: 20px 20px 18px;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.06);
      border: 1px solid rgba(2, 113, 255, 0.15);
    }

    .info-card {
      max-width: 360px;
      margin-left: auto;
    }

    .card h2 {
      font-size: 1.15rem;
      margin-bottom: 12px;
      color: #072654;
    }

    .card small {
      display: block;
      margin-bottom: 12px;
      color: #666;
    }

    label {
      font-size: 0.9rem;
      font-weight: 600;
      display: block;
      margin-bottom: 6px;
    }

    select, textarea, input[type="text"], input[type="password"], button {
      width: 100%;
      border-radius: 10px;
      border: 1px solid rgba(0, 0, 0, 0.1);
      padding: 10px 12px;
      font-size: 0.95rem;
    }

    textarea {
      resize: vertical;
      min-height: 120px;
    }

    button {
      margin-top: 10px;
      background: var(--mai-blue);
      color: #fff;
      border: none;
      font-weight: 600;
      cursor: pointer;
      transition: background 0.2s ease, transform 0.1s ease, box-shadow 0.2s ease;
      box-shadow: 0 4px 10px rgba(2, 113, 255, 0.35);
    }

    button:hover {
      background: #0053c3;
      transform: translateY(-1px);
    }

    button:active {
      transform: translateY(0);
      box-shadow: 0 2px 5px rgba(2, 113, 255, 0.25);
    }

    .story-form-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      margin-bottom: 8px;
    }

    .story-form-top .select-wrap {
      flex: 1;
    }

    .cat-wrapper {
      width: 110px;
      height: 90px;
      position: relative;
      cursor: pointer;
      flex-shrink: 0;
    }

    .pixel-cat {
      position: absolute;
      inset: 0;
      image-rendering: pixelated;
    }

    .pixel-cat svg {
      width: 100%;
      height: 100%;
      display: block;
    }

    .pixel-cat.awake {
      opacity: 0;
      transition: opacity 0.15s ease-out;
    }

    .cat-wrapper:hover .pixel-cat.awake {
      opacity: 1;
    }

    .cat-wrapper:hover .pixel-cat.sleep {
      opacity: 0;
    }

    .admin-login {
      margin-top: 8px;
      border-top: 1px dashed rgba(0, 0, 0, 0.1);
      padding-top: 10px;
      font-size: 0.85rem;
    }

    .admin-login summary {
      cursor: pointer;
      color: var(--mai-blue);
      font-weight: 600;
      margin-bottom: 4px;
    }

    .admin-login form {
      margin-top: 8px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px;
    }

    .admin-login form button {
      grid-column: 1 / -1;
      margin-top: 4px;
      padding-block: 8px;
      font-size: 0.9rem;
    }

    .admin-panel {
      display: none;
      margin-top: 14px;
      border-top: 1px solid rgba(0, 0, 0, 0.08);
      padding-top: 12px;
    }

    .admin-panel h3 {
      font-size: 1rem;
      margin-bottom: 8px;
      color: #072654;
    }

    .admin-tabs {
      display: flex;
      gap: 8px;
      margin-bottom: 12px;
      border-bottom: 2px solid rgba(0, 0, 0, 0.08);
    }

    .admin-tab-btn {
      background: none;
      border: none;
      padding: 8px 12px;
      font-size: 0.9rem;
      color: #666;
      cursor: pointer;
      border-bottom: 3px solid transparent;
      margin-bottom: -2px;
      transition: all 0.2s ease;
      box-shadow: none;
      margin-top: 0;
      font-weight: 500;
    }

    .admin-tab-btn.active {
      color: var(--mai-blue);
      border-bottom-color: var(--mai-blue);
    }

    .admin-tab-btn:hover {
      color: var(--mai-blue);
      background: rgba(2, 113, 255, 0.05);
      transform: none;
    }

    .admin-tab-content {
      display: none;
    }

    .admin-tab-content.active {
      display: block;
    }

    .stats {
      margin-top: 4px;
      margin-bottom: 10px;
    }

    .stats-row {
      display: flex;
      justify-content: space-between;
      font-size: 0.85rem;
      margin-bottom: 4px;
    }

    .chart {
      margin-top: 6px;
      background: #f5f8ff;
      border-radius: 10px;
      padding: 10px;
      display: flex;
      align-items: flex-end;
      gap: 10px;
      height: 200px;
    }

    .chart-bar {
      flex: 1;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 4px;
      font-size: 0.75rem;
      height: 100%;
    }

    .chart-bar-inner {
      width: 100%;
      border-radius: 8px 8px 0 0;
      background: #0271FF;
      height: 0;
      transition: height 0.3s ease;
      min-height: 2px;
    }

    .chart-bar-inner.zero {
      background: #ddd;
      min-height: 0;
    }

    .chart-percent {
      font-size: 0.75rem;
      font-weight: 600;
      color: #0271FF;
      text-align: center;
      min-height: 16px;
    }

    .chart-label {
      text-align: center;
      word-break: break-word;
      padding-top: 4px;
    }

    .filters {
      margin-top: 10px;
      font-size: 0.85rem;
      display: flex;
      flex-wrap: wrap;
      gap: 8px 14px;
    }

    .filters label {
      display: flex;
      align-items: center;
      gap: 4px;
      font-weight: 500;
      margin-bottom: 0;
    }

    .filters input[type="checkbox"] {
      width: auto;
      accent-color: var(--mai-blue);
    }

    .stories-list {
      margin-top: 10px;
      max-height: 400px;
      overflow-y: auto;
      padding-right: 4px;
    }

    .story-item {
      border-radius: 10px;
      border: 1px solid rgba(2, 113, 255, 0.1);
      padding: 8px 10px;
      margin-bottom: 8px;
      background: #f9fbff;
      font-size: 0.88rem;
    }

    .story-item.published {
      background: #f0f7ff;
      border-color: #38c975;
    }

    .story-meta {
      display: flex;
      justify-content: space-between;
      gap: 8px;
      font-size: 0.75rem;
      color: #555;
      margin-bottom: 4px;
    }

    .story-category {
      padding: 2px 6px;
      border-radius: 999px;
      background: rgba(2, 113, 255, 0.08);
      color: #08408f;
      font-weight: 600;
    }

    .story-name {
      font-size: 0.8rem;
      color: #333;
      margin-bottom: 4px;
    }

    .story-text {
      white-space: pre-wrap;
    }

    .story-buttons {
      display: flex;
      gap: 6px;
      margin-top: 6px;
      flex-wrap: wrap;
    }

    .story-delete-btn,
    .story-publish-btn {
      padding: 4px 12px;
      font-size: 0.78rem;
      color: #fff;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-weight: 600;
      box-shadow: none;
      width: auto;
      transition: background 0.2s ease;
      margin-top: 0;
      background: none;
    }

    .story-delete-btn {
      background: #e53935;
    }

    .story-delete-btn:hover {
      background: #b71c1c;
    }

    .story-publish-btn {
      background: #38c975;
    }

    .story-publish-btn:hover {
      background: #2e9e5f;
    }

    .story-publish-btn.published {
      background: #999;
      cursor: default;
    }

    .story-publish-btn.published:hover {
      background: #999;
    }

    .published-badge {
      display: inline-block;
      background: #38c975;
      color: white;
      padding: 2px 6px;
      border-radius: 999px;
      font-size: 0.7rem;
      font-weight: 600;
      margin-left: 4px;
    }

    .published-date {
      font-size: 0.75rem;
      color: #38c975;
      font-weight: 600;
    }

    footer {
      text-align: center;
      padding: 10px 12px 16px;
      font-size: 0.8rem;
      color: #444;
      background: #ffffff;
      border-top: 1px solid rgba(0, 0, 0, 0.05);
    }

    .info-button {
      position: fixed;
      top: 70px;
      right: 24px;
      width: 50px;
      height: 50px;
      background: var(--mai-blue);
      border: none;
      border-radius: 50%;
      font-size: 1.8rem;
      cursor: pointer;
      color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 4px 12px rgba(2, 113, 255, 0.3);
      transition: all 0.2s ease;
      z-index: 100;
    }

    .info-button:hover {
      transform: scale(1.1);
      box-shadow: 0 6px 16px rgba(2, 113, 255, 0.4);
    }

    .info-button:active {
      transform: scale(0.95);
    }

    .info-modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 1000;
      align-items: center;
      justify-content: center;
      animation: fadeIn 0.2s ease;
    }

    .info-modal.active {
      display: flex;
    }

    .info-modal-content {
      background: #ffffff;
      border-radius: 16px;
      padding: 28px;
      max-width: 450px;
      width: 90%;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
      animation: slideIn 0.3s ease;
      position: relative;
    }

    .info-modal-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 16px;
    }

    .info-modal-header h2 {
      font-size: 1.3rem;
      color: #072654;
      margin: 0;
    }

    .info-close-btn {
      background: none;
      border: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: #999;
      width: 32px;
      height: 32px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      transition: all 0.2s ease;
    }

    .info-close-btn:hover {
      background: rgba(0, 0, 0, 0.05);
      color: #333;
    }

    .info-modal-text p {
      font-size: 0.95rem;
      color: #333;
      line-height: 1.6;
      margin-bottom: 14px;
    }

    .info-modal-text p:last-child {
      margin-bottom: 0;
    }

    @keyframes slideIn {
      from {
        opacity: 0;
        transform: scale(0.95);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }

    @media (max-width: 600px) {
      .info-button {
        top: 60px;
        right: 16px;
        width: 45px;
        height: 45px;
        font-size: 1.5rem;
      }
    }
  </style>
</head>
<body>
<header>
  <div class="logo">
    <div>
      <h1>МАИ истории</h1>
      <div class="subtitle">Истории и традиции МАИ:</div>
      <div class="subtitle">голоса студентов, преподавателей и гостей института</div>
    </div>
  </div>
  <img src="https://mai.ru/press/brand/download_2026/Сокращённая%20версия%20на%20синем%20фоне/PNG/МАИ%20лого%20-%20щит%20без%20подложки%20белый.png" alt="Логотип МАИ" class="header-logo-img">
</header>

<nav class="main-tabs">
  <button class="main-tab-btn active" data-tab="form">✍️ Поделиться историей</button>
  <button class="main-tab-btn" data-tab="publications">📖 Опубликовано</button>
</nav>

<button id="infoButton" class="info-button" title="Информация о сайте">?</button>

<div id="infoModal" class="info-modal">
  <div class="info-modal-content">
    <div class="info-modal-header">
      <h2>Как работает этот сайт</h2>
      <button id="infoCloseBtn" class="info-close-btn">✕</button>
    </div>
    <div class="info-modal-text">
      <p>
        Любой желающий может оставить историю, выбрав свою роль -
        студент, преподаватель или человек, не связанный с МАИ.
      </p>
      <p>
        Таким образом вы сможите оставить след в цифривизации историй
        и традиций нашего университета 🩵🐈‍⬛.
      </p>
    </div>
  </div>
</div>

<main class="main-tab-content active" id="tab-form">
  <section class="card">
    <h2>Оставить свою историю</h2>
    <small>Выберите, кем вы являетесь, и расскажите историю, связанную с МАИ.</small>

    <div class="story-form-top">
      <div class="select-wrap">
        <label for="category">Категория</label>
        <select id="category">
          <option value="student">Я студент</option>
          <option value="teacher">Я преподаватель</option>
          <option value="guest">Я не из МАИ</option>
        </select>
      </div>

      <div class="cat-wrapper" title="Наведи курсор — кошка проснётся">
        <div class="pixel-cat sleep">
          <svg viewBox="0 0 24 18" xmlns="http://www.w3.org/2000/svg">
            <rect x="4" y="8" width="12" height="3" fill="#000"/>
            <rect x="3" y="11" width="14" height="1" fill="#000"/>
            <rect x="16" y="9" width="1" height="4" fill="#000"/>
            <rect x="17" y="12" width="1" height="1" fill="#000"/>
            <rect x="18" y="13" width="1" height="1" fill="#000"/>
            <rect x="6" y="5" width="5" height="3" fill="#000"/>
            <rect x="6" y="4" width="1" height="1" fill="#000"/>
            <rect x="10" y="4" width="1" height="1" fill="#000"/>
            <rect x="7" y="6" width="3" height="2" fill="#ffffff"/>
            <rect x="7" y="6" width="1" height="1" fill="#000"/>
            <rect x="9" y="6" width="1" height="1" fill="#000"/>
            <rect x="8" y="7" width="1" height="1" fill="#000"/>
          </svg>
        </div>

        <div class="pixel-cat awake">
          <svg viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <rect x="6" y="9" width="6" height="6" fill="#000"/>
            <rect x="6" y="15" width="2" height="3" fill="#000"/>
            <rect x="10" y="15" width="2" height="3" fill="#000"/>
            <rect x="6" y="18" width="2" height="1" fill="#555"/>
            <rect x="10" y="18" width="2" height="1" fill="#555"/>
            <rect x="12" y="10" width="1" height="5" fill="#000"/>
            <rect x="13" y="9" width="1" height="1" fill="#000"/>
            <rect x="14" y="8" width="1" height="1" fill="#000"/>
            <rect x="5" y="4" width="8" height="5" fill="#000"/>
            <rect x="5" y="3" width="2" height="1" fill="#000"/>
            <rect x="11" y="3" width="2" height="1" fill="#000"/>
            <rect x="6" y="6" width="6" height="3" fill="#ffffff"/>
            <rect x="7" y="6" width="1" height="2" fill="#FFCC33"/>
            <rect x="10" y="6" width="1" height="2" fill="#FFCC33"/>
            <rect x="7" y="6" width="1" height="1" fill="#000"/>
            <rect x="10" y="6" width="1" height="1" fill="#000"/>
            <rect x="8" y="8" width="2" height="1" fill="#000"/>
          </svg>
        </div>
      </div>
    </div>

    <label for="userName">
      Имя <span style="font-weight:400; color:#666;">(не обязательно)</span>
    </label>
    <input type="text" id="userName" placeholder="Например: Анна">

    <label for="storyText">Текст истории</label>
    <textarea id="storyText" placeholder="Напишите здесь вашу историю о МАИ..."></textarea>

    <button id="submitStory" type="button">Отправить историю</button>

    <div class="admin-login">
      <details>
        <summary>Вход администратора для просмотра историй и статистики</summary>
        <form id="adminLoginForm">
          <div>
            <label for="adminLogin">Логин</label>
            <input type="text" id="adminLogin" placeholder="Логин администратора">
          </div>
          <div>
            <label for="adminPassword">Пароль</label>
            <input type="password" id="adminPassword" placeholder="Пароль администратора">
          </div>
          <button type="submit">Войти</button>
        </form>
      </details>
    </div>

    <div class="admin-panel" id="adminPanel">
      <h3>Панель администратора</h3>
      <small>Здесь отображаются все сохранённые истории и диаграмма по категориям.</small>

      <div class="admin-tabs">
        <button class="admin-tab-btn active" data-tab="statistics">📊 Статистика</button>
        <button class="admin-tab-btn" data-tab="pending">📝 На модерации</button>
        <button class="admin-tab-btn" data-tab="published">✅ Опубликовано</button>
      </div>

      <div class="admin-tab-content active" id="tab-statistics">
        <div class="stats">
          <div class="stats-row">
            <span>Всего историй:</span>
            <span id="totalCount">0</span>
          </div>
          <div class="stats-row">
            <span>Опубликовано:</span>
            <span id="publishedCount">0</span>
          </div>
          <div class="stats-row">
            <span>На модерации:</span>
            <span id="pendingCount">0</span>
          </div>
          <div class="stats-row">
            <span>Студенты:</span>
            <span id="studentCount">0</span>
          </div>
          <div class="stats-row">
            <span>Преподаватели:</span>
            <span id="teacherCount">0</span>
          </div>
          <div class="stats-row">
            <span>Не из МАИ:</span>
            <span id="guestCount">0</span>
          </div>
        </div>

        <div class="chart" aria-label="Диаграмма распределения историй по категориям">
          <div class="chart-bar">
            <div class="chart-percent" id="pctStudent">0%</div>
            <div class="chart-bar-inner" id="barStudent"></div>
            <div class="chart-label">Студенты</div>
          </div>
          <div class="chart-bar">
            <div class="chart-percent" id="pctTeacher">0%</div>
            <div class="chart-bar-inner" id="barTeacher"></div>
            <div class="chart-label">Преподаватели</div>
          </div>
          <div class="chart-bar">
            <div class="chart-percent" id="pctGuest">0%</div>
            <div class="chart-bar-inner" id="barGuest"></div>
            <div class="chart-label">Не из&nbsp;МАИ</div>
          </div>
        </div>
      </div>

      <div class="admin-tab-content" id="tab-pending">
        <div class="filters">
          <span>Фильтр:</span>
          <label>
            <input type="checkbox" id="filterPendingStudent" checked>
            Студенты
          </label>
          <label>
            <input type="checkbox" id="filterPendingTeacher" checked>
            Преподаватели
          </label>
          <label>
            <input type="checkbox" id="filterPendingGuest" checked>
            Не из МАИ
          </label>
        </div>
        <div class="stories-list" id="storiesListPending"></div>
      </div>

      <div class="admin-tab-content" id="tab-published">
        <div class="stories-list" id="storiesListPublished"></div>
      </div>
    </div>
  </section>

  <aside class="card info-card" style="display: none;"></aside>
</main>

<main class="main-tab-content full-width" id="tab-publications">
  <section class="card" style="width: 100%;">
    <h2>📖 Опубликованные истории</h2>
    <small>Истории и традиции МАИ, одобренные модератором</small>
    <div class="published-stories-grid" id="publicationsGrid"></div>
  </section>
</main>

<footer>
  Сайт создан студентом 10 института «Иностранных языков» Карташовой Анной, группа МИО-208БВк-24.
</footer>

<script>
  const ADMIN_CREDENTIALS = {
    login: "Messie47",
    passwordHash: "7531Anna"
  };

  const categorySelect = document.getElementById("category");
  const storyText = document.getElementById("storyText");
  const userNameInput = document.getElementById("userName");
  const submitStoryBtn = document.getElementById("submitStory");

  const adminLoginForm = document.getElementById("adminLoginForm");
  const adminPanel = document.getElementById("adminPanel");

  const totalCountSpan = document.getElementById("totalCount");
  const publishedCountSpan = document.getElementById("publishedCount");
  const pendingCountSpan = document.getElementById("pendingCount");
  const studentCountSpan = document.getElementById("studentCount");
  const teacherCountSpan = document.getElementById("teacherCount");
  const guestCountSpan = document.getElementById("guestCount");

  const barStudent = document.getElementById("barStudent");
  const barTeacher = document.getElementById("barTeacher");
  const barGuest = document.getElementById("barGuest");

  const pctStudent = document.getElementById("pctStudent");
  const pctTeacher = document.getElementById("pctTeacher");
  const pctGuest = document.getElementById("pctGuest");

  const storiesListPending = document.getElementById("storiesListPending");
  const storiesListPublished = document.getElementById("storiesListPublished");

  let cachedStories = [];
  let isAdmin = false;

  document.querySelectorAll(".main-tab-btn").forEach(btn => {
    btn.addEventListener("click", () => {
      const tabName = btn.dataset.tab;
      
      document.querySelectorAll(".main-tab-btn").forEach(b => b.classList.remove("active"));
      document.querySelectorAll(".main-tab-content").forEach(c => c.classList.remove("active"));
      
      btn.classList.add("active");
      document.getElementById(`tab-${tabName}`).classList.add("active");

      if (tabName === "publications") {
        renderPublicationsPage();
      }
    });
  });

  document.querySelectorAll(".admin-tab-btn").forEach(btn => {
    btn.addEventListener("click", () => {
      const tabName = btn.dataset.tab;
      
      document.querySelectorAll(".admin-tab-btn").forEach(b => b.classList.remove("active"));
      document.querySelectorAll(".admin-tab-content").forEach(c => c.classList.remove("active"));
      
      btn.classList.add("active");
      document.getElementById(`tab-${tabName}`).classList.add("active");
    });
  });

  async function loadStoriesFromGithub() {
    try {
      const stored = localStorage.getItem("mai_stories");
      cachedStories = stored ? JSON.parse(stored) : [];
      return cachedStories;
    } catch (e) {
      console.error("Ошибка загрузки историй:", e);
      return [];
    }
  }

  async function saveStoriesToGithub() {
    try {
      localStorage.setItem("mai_stories", JSON.stringify(cachedStories));
    } catch (e) {
      console.error("Ошибка сохранения историй:", e);
    }
  }

  async function addStory(category, text, name) {
    const story = {
      id: Date.now(),
      category,
      text,
      name: name || "Аноним",
      createdAt: new Date().toISOString(),
      published: false,
      publishedAt: null
    };
    cachedStories.push(story);
    await saveStoriesToGithub();
    return story;
  }

  async function deleteStory(id) {
    cachedStories = cachedStories.filter(s => s.id !== id);
    await saveStoriesToGithub();
    updateStatsAndChart();
    renderStories();
  }

  async function publishStory(id) {
    const story = cachedStories.find(s => s.id === id);
    if (story) {
      story.published = true;
      story.publishedAt = new Date().toISOString();
      await saveStoriesToGithub();
      updateStatsAndChart();
      renderStories();
    }
  }

  function formatCategory(cat) {
    switch (cat) {
      case "student": return "Я студент";
      case "teacher": return "Я преподаватель";
      case "guest":   return "Не из МАИ";
      default:        return cat;
    }
  }

  function formatDate(iso) {
    if (!iso) return "";
    const d = new Date(iso);
    if (isNaN(d.getTime())) return "";
    const day = d.toLocaleDateString("ru-RU");
    const time = d.toLocaleTimeString("ru-RU", { hour: "2-digit", minute: "2-digit" });
    return day + " " + time;
  }

  function updateStatsAndChart() {
    const stories = cachedStories;
    const total = stories.length;
    const published = stories.filter(s => s.published).length;
    const pending = total - published;
    const student = stories.filter(s => s.category === "student").length;
    const teacher = stories.filter(s => s.category === "teacher").length;
    const guest = stories.filter(s => s.category === "guest").length;

    totalCountSpan.textContent = total;
    publishedCountSpan.textContent = published;
    pendingCountSpan.textContent = pending;
    studentCountSpan.textContent = student;
    teacherCountSpan.textContent = teacher;
    guestCountSpan.textContent = guest;

    const studentPct = total > 0 ? Math.round(student / total * 100) : 0;
    const teacherPct = total > 0 ? Math.round(teacher / total * 100) : 0;
    const guestPct = total > 0 ? Math.round(guest / total * 100) : 0;

    pctStudent.textContent = studentPct + "%";
    pctTeacher.textContent = teacherPct + "%";
    pctGuest.textContent = guestPct + "%";

    const max = Math.max(student, teacher, guest, 1);
    barStudent.style.height = (student / max * 100) + "%";
    barTeacher.style.height = (teacher / max * 100) + "%";
    barGuest.style.height = (guest / max * 100) + "%";

    barStudent.classList.toggle("zero", student === 0);
    barTeacher.classList.toggle("zero", teacher === 0);
    barGuest.classList.toggle("zero", guest === 0);
  }

  function renderStories() {
    renderPendingStories();
    renderPublishedStories();
  }

  function renderPendingStories() {
    const showStudent = document.getElementById("filterPendingStudent").checked;
    const showTeacher = document.getElementById("filterPendingTeacher").checked;
    const showGuest = document.getElementById("filterPendingGuest").checked;

    storiesListPending.innerHTML = "";

    const pending = cachedStories.filter(s => !s.published);
    const filtered = pending.filter(s => {
      if (s.category === "student" && showStudent) return true;
      if (s.category === "teacher" && showTeacher) return true;
      if (s.category === "guest" && showGuest) return true;
      return false;
    });

    if (filtered.length === 0) {
      const empty = document.createElement("div");
      empty.textContent = "Нет историй на модерации.";
      empty.style.fontSize = "0.85rem";
      empty.style.color = "#666";
      storiesListPending.appendChild(empty);
      return;
    }

    filtered
      .sort((a, b) => b.id - a.id)
      .forEach(story => {
        storiesListPending.appendChild(createStoryElement(story, "pending"));
      });
  }

  function renderPublishedStories() {
    storiesListPublished.innerHTML = "";

    const published = cachedStories.filter(s => s.published).sort((a, b) => new Date(b.publishedAt) - new Date(a.publishedAt));

    if (published.length === 0) {
      const empty = document.createElement("div");
      empty.textContent = "Опубликованных историй ещё нет.";
      empty.style.fontSize = "0.85rem";
      empty.style.color = "#666";
      storiesListPublished.appendChild(empty);
      return;
    }

    published.forEach(story => {
      storiesListPublished.appendChild(createStoryElement(story, "published"));
    });
  }

  function renderPublicationsPage() {
    const publicationsGrid = document.getElementById("publicationsGrid");
    publicationsGrid.innerHTML = "";

    const published = cachedStories.filter(s => s.published).sort((a, b) => new Date(b.publishedAt) - new Date(a.publishedAt));

    if (published.length === 0) {
      const empty = document.createElement("div");
      empty.innerHTML = `
        <div style="text-align: center; padding: 40px 20px; color: #999;">
          <p style="font-size: 1rem; margin-bottom: 10px;">📖 Опубликованные истории появятся здесь</p>
          <p style="font-size: 0.9rem;">Поделитесь вашей историей с МАИ!</p>
        </div>
      `;
      publicationsGrid.appendChild(empty);
      return;
    }

    published.forEach(story => {
      const card = document.createElement("article");
      card.style.cssText = `
        background: #f9fbff;
        border: 1px solid rgba(2, 113, 255, 0.15);
        border-radius: 12px;
        padding: 16px;
        margin-bottom: 16px;
        transition: all 0.2s ease;
      `;
      card.onmouseover = () => {
        card.style.boxShadow = "0 8px 24px rgba(2, 113, 255, 0.15)";
        card.style.borderColor = "rgba(2, 113, 255, 0.3)";
      };
      card.onmouseout = () => {
        card.style.boxShadow = "none";
        card.style.borderColor = "rgba(2, 113, 255, 0.15)";
      };

      const header = document.createElement("div");
      header.style.cssText = "display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; margin-bottom: 8px;";

      const nameAndCategory = document.createElement("div");
      nameAndCategory.style.cssText = "flex: 1;";

      const name = document.createElement("div");
      name.style.cssText = "font-weight: 600; color: #072654; font-size: 0.95rem; margin-bottom: 4px;";
      name.textContent = story.name || "Аноним";
      nameAndCategory.appendChild(name);

      const category = document.createElement("span");
      category.style.cssText = "display: inline-block; background: rgba(2, 113, 255, 0.12); color: #08408f; padding: 3px 8px; border-radius: 999px; font-size: 0.75rem; font-weight: 600;";
      category.textContent = formatCategory(story.category);
      nameAndCategory.appendChild(category);

      const date = document.createElement("div");
      date.style.cssText = "font-size: 0.8rem; color: #38c975; font-weight: 600; text-align: right;";
      date.textContent = formatDate(story.publishedAt);

      header.appendChild(nameAndCategory);
      header.appendChild(date);
      card.appendChild(header);

      const text = document.createElement("div");
      text.style.cssText = "color: #333; font-size: 0.95rem; line-height: 1.6; white-space: pre-wrap; word-wrap: break-word;";
      text.textContent = story.text;
      card.appendChild(text);

      publicationsGrid.appendChild(card);
    });
  }

  function createStoryElement(story, mode) {
    const item = document.createElement("article");
    item.className = mode === "published" ? "story-item published" : "story-item";

    const meta = document.createElement("div");
    meta.className = "story-meta";

    const catSpan = document.createElement("span");
    catSpan.className = "story-category";
    catSpan.textContent = formatCategory(story.category);

    const dateSpan = document.createElement("span");
    if (mode === "published" && story.publishedAt) {
      dateSpan.className = "published-date";
      dateSpan.textContent = "Опубликовано: " + formatDate(story.publishedAt);
    } else {
      dateSpan.textContent = formatDate(story.createdAt);
    }

    meta.appendChild(catSpan);
    meta.appendChild(dateSpan);
    item.appendChild(meta);

    if (story.name) {
      const nameDiv = document.createElement("div");
      nameDiv.className = "story-name";
      nameDiv.textContent = "Имя: " + story.name;
      item.appendChild(nameDiv);
    }

    const textDiv = document.createElement("div");
    textDiv.className = "story-text";
    textDiv.textContent = story.text;
    item.appendChild(textDiv);

    if (isAdmin) {
      const buttons = document.createElement("div");
      buttons.className = "story-buttons";

      const publishBtn = document.createElement("button");
      publishBtn.className = "story-publish-btn";
      publishBtn.textContent = story.published ? "✓ Опубликовано" : "Опубликовать";
      if (story.published) publishBtn.classList.add("published");
      publishBtn.addEventListener("click", async () => {
        if (!story.published) {
          await publishStory(story.id);
        }
      });
      buttons.appendChild(publishBtn);

      const deleteBtn = document.createElement("button");
      deleteBtn.className = "story-delete-btn";
      deleteBtn.textContent = "Удалить";
      deleteBtn.addEventListener("click", async () => {
        if (!confirm("Подтвердить удаление этой истории?")) return;
        deleteBtn.disabled = true;
        deleteBtn.textContent = "Удаление...";
        try {
          await deleteStory(story.id);
        } catch (e) {
          alert("Ошибка при удалении.");
          deleteBtn.disabled = false;
          deleteBtn.textContent = "Удалить";
        }
      });
      buttons.appendChild(deleteBtn);

      item.appendChild(buttons);
    }

    return item;
  }

  submitStoryBtn.addEventListener("click", async () => {
    const category = categorySelect.value;
    const text = storyText.value.trim();
    const name = userNameInput.value.trim();

    if (!text) {
      alert("Пожалуйста, напишите текст истории.");
      return;
    }

    submitStoryBtn.disabled = true;
    submitStoryBtn.textContent = "Сохранение...";

    try {
      await addStory(category, text, name);
      storyText.value = "";
      userNameInput.value = "";
      alert("Спасибо! Ваша история сохранена.");

      if (isAdmin) {
        updateStatsAndChart();
        renderStories();
      }
    } catch (e) {
      alert("Ошибка при сохранении истории.");
      console.error(e);
    } finally {
      submitStoryBtn.disabled = false;
      submitStoryBtn.textContent = "Отправить историю";
    }
  });

  adminLoginForm.addEventListener("submit", async (e) => {
    e.preventDefault();
    const login = document.getElementById("adminLogin").value.trim();
    const password = document.getElementById("adminPassword").value;

    if (login === ADMIN_CREDENTIALS.login && password === ADMIN_CREDENTIALS.passwordHash) {
      isAdmin = true;
      adminPanel.style.display = "block";
      await loadStoriesFromGithub();
      updateStatsAndChart();
      renderStories();
      document.getElementById("adminLogin").value = "";
      document.getElementById("adminPassword").value = "";
    } else {
      alert("Неверный логин или пароль.");
    }
  });

  [
    document.getElementById("filterPendingStudent"),
    document.getElementById("filterPendingTeacher"),
    document.getElementById("filterPendingGuest")
  ].forEach(cb => {
    cb.addEventListener("change", renderPendingStories);
  });

  loadStoriesFromGithub().then(() => {
    if (cachedStories.length > 0) {
      updateStatsAndChart();
      const published = cachedStories.filter(s => s.published);
      if (published.length > 0) {
        document.querySelector("[data-tab='publications']").style.display = "inline-block";
      }
    }
  });

  const infoButton = document.getElementById("infoButton");
  const infoModal = document.getElementById("infoModal");
  const infoCloseBtn = document.getElementById("infoCloseBtn");

  infoButton.addEventListener("click", () => {
    infoModal.classList.add("active");
  });

  infoCloseBtn.addEventListener("click", () => {
    infoModal.classList.remove("active");
  });

  infoModal.addEventListener("click", (e) => {
    if (e.target === infoModal) {
      infoModal.classList.remove("active");
    }
  });

  setInterval(async () => {
    const oldLength = cachedStories.length;
    await loadStoriesFromGithub();
    if (cachedStories.length !== oldLength) {
      updateStatsAndChart();
      renderStories();
      const published = cachedStories.filter(s => s.published);
      if (published.length > 0) {
        document.querySelector("[data-tab='publications']").style.display = "inline-block";
      }
    }
  }, 5000);
</script>
</body>
</html>
