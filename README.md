# emaar

**[English](README.en.md)** · Русский

Одностраничный лендинг недвижимости Emaar (Dubai Creek Harbour) — адаптивная статическая вёрстка без сборщика и серверной части.

| | |
|---|---|
| **Демо** | [murodjon-dev-uz.github.io/emaar](https://murodjon-dev-uz.github.io/emaar) |
| **Репозиторий** | [github.com/murodjon-dev-uz/emaar](https://github.com/murodjon-dev-uz/emaar) |
| **Автор** | Murodjon Nuritdinov |
| **Год** | 2023 |

---

## О проекте

**emaar** — учебно-портфельный проект: визуальная часть промо-страницы девелопера Emaar Properties с фокусом на Dubai Creek Harbour. Одна HTML-страница показывает типичный UX лендинга недвижимости — hero, каталог проектов, интерактивную карту локаций, блоки оплаты и контактный экран.

Контент и цены зафиксированы в разметке; сценарии «заявка», «скачать брошюру» и «детали проекта» реализованы как **статический макет** — ссылки ведут на `#`, отправка форм не обрабатывается.

В репозитории только production-артефакты (`style.min.css`, `app.min.js`); исходники SCSS/JS и сборщик не включены.

---

## Особенности реализации

- **Hero и статистика** — полноэкранный фон (`ibg`), ключевые цифры (бронь, рассрочка, цена от).
- **Три карусели Swiper** — слайдеры доступных юнитов у Creek Rise, The Cove и Creek Gate с пагинацией и стрелками.
- **Карта локаций** — интерактивные подсказки Tippy.js на трёх районах (Dubai Creek Harbour, Dubai Hills Estate, Emaar South).
- **Блок projects** — липкий сайдбар (`data-sticky`), фильтр community (radio), спойлеры (`data-spoller`), якорная навигация `data-goto` и подсветка секций `data-watch="navigator"`.
- **Попапы** — брошюра, спецпредложение, детальная карточка проекта (карта с POI, lightGallery, планы этажей, payment, форма).
- **Анимации** — GSAP 3.12 и ScrollTrigger (CDN) для скролл-сцен; параллакс курсора на info-block (`data-prlx-mouse`).
- **Галерея** — lightGallery 2.7.1 в модальном окне проекта (`data-gallery`).
- **Изображения** — `<picture>` (WebP + JPG/PNG), отложенная загрузка через `data-src` / `data-srcset` и placeholder 1×1.
- **Адаптив** — перенос блоков через `data-da` (popup offer, breakpoint 767.98px).
- **Типографика** — Lato, Alethia Pro, Manrope (Google Fonts), иконочный шрифт `_icon-*`.
- **Кэш статики** — query-параметры версии на CSS/JS (`?_v=...`) и favicon (`?v=...`); при обновлении файла увеличьте номер в `index.html`.

Фирменные цвета в CSS: `#071c35` (фон/тёмный), `#3fb1ce` (акцент), `#ffffff`.

---

## Стек

| Слой | Технологии |
|------|------------|
| Разметка | HTML5, семантика (`header`, `main`, `section`, `article`, `footer`) |
| Стили | CSS3, BEM-подобные классы, mobile-first |
| Скрипты | Vanilla JS в `app.min.js` (Swiper, Tippy, popups, lazy-load, spollers, sticky, навигация) + GSAP/ScrollTrigger с CDN |
| Шрифты | Self-hosted: Lato, Alethia Pro, icons; Manrope — Google Fonts |
| Хостинг | GitHub Pages |

Сборщик (npm, Vite, Webpack) не используется.

---

## Структура

```
emaar/
├── index.html
├── favicon.ico
├── css/style.min.css
├── js/app.min.js
├── fonts/
├── img/
│   ├── header/, homes/, top-projects/, location/
│   ├── projects/ (creek-rise, the-cove, creek-gate)
│   ├── info-block/, footer/, gallery/
│   └── popup-*/ (brochure, offer, project)
└── README.md, README.en.md
```

---

## Быстрый старт

```bash
git clone https://github.com/murodjon-dev-uz/emaar.git
cd emaar
python3 -m http.server 8000
```

Откройте [http://localhost:8000](http://localhost:8000). Альтернатива: `npx --yes serve .`

---

## Деплой

Сайт опубликован на **GitHub Pages**:

**https://murodjon-dev-uz.github.io/emaar**

Источник — репозиторий [murodjon-dev-uz/emaar](https://github.com/murodjon-dev-uz/emaar), ветка `main`, корень `/`. После правок CSS/JS увеличьте `?_v=`; после смены favicon — `?v=` в `index.html`.

---

## Секции страницы

| Секция / модуль | Содержание |
|-----------------|------------|
| Header | Логотип, заголовок Dubai Creek Harbour, KPI, CTA «See project» |
| Homes | О компании, финансовые показатели, CTA «see more» → popup брошюры |
| Top projects | Три карточки проектов с ценами |
| Location | Карта с Tippy-подсказками по районам |
| Projects | Сайдбар + три проекта со Swiper юнитов |
| Info block | Payment Option и More About Emaar (параллакс) |
| Contact | Блок «Speak to a specialist» (UI формы) |
| Footer | Навигация, телефон-заглушка, мессенджеры |
| Popups | Brochure, unique offer, детальный popup-project |

---

## Ограничения

- Нет API, CRM и обработки заявок — `action="#"`, телефон `+971 56XXX-XX-XX`.
- Ссылки и соцсети — заглушки (`href="#"`).
- Open Graph / Twitter Card в разметке не заданы (только `meta description`).
- Правки вёрстки — в минифицированных файлах или в исходном проекте вне репозитория.

---

## Лицензия

© 2023 **Murodjon Nuritdinov**. Все права защищены. Копирование, распространение и коммерческое использование без разрешения автора запрещены.
