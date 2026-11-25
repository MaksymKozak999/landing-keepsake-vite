# Keepsake — Digital & Branding Agency

Адаптивний лендінг цифрової та брендингової агенції **Keepsake**, мігрований на компонентну архітектуру з використанням **Vite**, **Vituum**, **Pug** та модульного **SCSS** за методологією **БЕМ**.

---

## 🛠️ Технологічний стек

- **Збірка:** [Vite](https://vitejs.dev/) + [Vituum](https://vituum.dev/)
- **Шаблонізатор:** [Pug](https://pugjs.org/) (layouts, includes, mixins, дані у вигляді масивів об'єктів)
- **Стилі:** [Sass / SCSS](https://sass-lang.com/) (`@use` / `@forward`, дизайн-токени, функції, міксіни, mobile-first)
- **Якість коду:** [Stylelint](https://stylelint.io/) (конфігурація `stylelint-config-standard-scss`), [Prettier](https://prettier.io/), [Husky](https://typicode.github.io/husky/) + `lint-staged`
- **Графіка та медіа:** інлайн SVG-спрайт та адаптивні растрові зображення у форматах **AVIF**, **WebP** і **JPG** (`<picture>`)

---

## 📋 Вимоги до середовища

Для роботи з проєктом потрібен **Node.js** (версії 20 або новішої) та **npm**.

```bash
node -v
npm -v
```

---

## 🚀 Встановлення та запуск

### 1. Встановлення залежностей

```bash
npm install
```

### 2. Запуск сервера розробки

```bash
npm run dev
```

Після запуску сайт буде доступний за локальною адресою (зазвичай `http://localhost:5173/`).

### 3. Перевірка якості коду та форматування

```bash
npm run lint        # перевірка SCSS через Stylelint та форматування через Prettier
npm run lint:styles # перевірка лише SCSS-файлів
npm run format      # автоматичне форматування коду через Prettier
```

### 4. Продакшн-збірка та попередній перегляд

```bash
npm run build       # збірка оптимізованого проєкту в директорію dist/
npm run preview     # локальний перегляд зібраної версії з dist/
```

---

## 🧩 Архітектура проєкту

```text
landing-keepsake-vite/
├─ .husky/                   # Git pre-commit хуки (автоматичний запуск lint-staged)
├─ src/
│  ├─ assets/
│  │  ├─ fonts/              # локальні шрифти
│  │  └─ images/             # оптимізовані зображення (AVIF, WebP, JPG)
│  ├─ components/
│  │  ├─ sections/           # секції лендінгу (hero, works, cta, services, stats, clients, journal)
│  │  ├─ header.pug          # шапка сайту та мобільне меню
│  │  └─ footer.pug          # підвал сайту з формою підписки
│  ├─ data/
│  │  └─ data.pug            # структуровані дані (навігація, портфоліо, послуги, статистика, блог)
│  ├─ includes/
│  │  ├─ meta.pug            # мета-теги сторінки
│  │  ├─ fonts.pug           # підключення Google Fonts
│  │  ├─ head.pug            # секція <head>
│  │  └─ sprite.pug          # SVG-спрайт іконок
│  ├─ layouts/
│  │  └─ main.pug            # базовий шаблон сторінки
│  ├─ mixins/
│  │  ├─ icon.pug            # міксін SVG-іконок зі спрайту
│  │  ├─ btn.pug             # міксін кнопок і посилань
│  │  ├─ picture.pug         # міксін адаптивних зображень (AVIF / WebP / JPG)
│  │  └─ work-card.pug       # міксін картки портфоліо
│  ├─ pages/
│  │  └─ index.pug           # головна сторінка лендінгу
│  └─ styles/
│     ├─ utils/              # дизайн-токени (_variables.scss), функції (_functions.scss), міксіни (_mixins.scss)
│     ├─ base/               # CSS-змінні :root, скидання стилів (_reset.scss) та типографія (_typography.scss)
│     ├─ layout/             # контейнер (_grid.scss) та відступи секцій (_sections.scss)
│     ├─ components/         # ізольовані БЕМ-блоки компонентів і секцій
│     └─ main.scss           # єдина точка входу стилів
├─ .prettierrc               # налаштування Prettier
├─ .stylelintrc.json         # правила Stylelint та БЕМ
├─ package.json              # залежності та npm-скрипти
└─ vite.config.js            # конфігурація Vite + Vituum
```
