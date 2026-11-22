<div align="center">

# ⚡ Gemini Power UI

**Adaptive Minimap · Code & Prompt Spoilers · Default Model Lock · 5h/Weekly Usage Bar · Left Sidebar Makeover**

[![Install on GreasyFork](https://img.shields.io/badge/Install%20on-GreasyFork-670000?style=for-the-badge&logo=tampermonkey&logoColor=white)](https://greasyfork.org/ru/scripts/606781)
[![GitHub Repo](https://img.shields.io/badge/Source-GitHub-181717?style=for-the-badge&logo=github)](https://github.com/asimoneo/Gemini-Power-UI)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

[🇬🇧 English](#-english) · [🇷🇺 Русский](#-русский)

![Gemini Power UI Preview](./assets/preview.gif)

*✨ 100% vibecoded directly inside Gemini Web using **Neon High** — zero frameworks, zero external dependencies, pure stubbornness.*

</div>

---

## 🇬🇧 English

### 😩 The Pain You Know Too Well

Picture this: you're 40 turns deep into a debugging session with Gemini.
* You want to re-read that one prompt from 25 minutes ago, so your mouse wheel gets a full cardio workout scrolling past **14 uncollapsed 600-line code blocks**.
* You open a new tab, type a massive technical prompt, hit Enter… and only *after* a breezy 2-paragraph hallucination realize **Google silently switched your model back to a lighter default**.
* You're using a widescreen monitor, yet Gemini insists on squeezing your code into a narrow little newspaper column in the middle of the screen.
* Meanwhile, the left sidebar truncates every chat title to `"Fix the thing in..."`, refuses to let you resize it, and proudly dedicates two full rows at the bottom to reminding you what city your IP address is in. (Thanks, Google, I know where I live.)
* And you have no idea if you're at 12% or 98% of your 5-hour quota until you hit a brick wall mid-task.

**Gemini Power UI** fixes all of that in a single lightweight userscript.

---

### 🚀 Every Feature, Explained

#### 🗺️ 1. Adaptive Right Minimap & Dialogue Scrollbar
A docked, resizable (`272–460 px`, double-click to reset) navigation panel that automatically adapts to both **chat length** and **your chosen text scale**:
* **📄 Short chats — Content-Rich Capped Cards:** No giant empty gray rectangles. Cards show your wrapped prompt in bold, a clean divider, Gemini's reply excerpt, and code/media pills, capped cleanly so 2–3 turn chats stay tidy.
* **📏 Medium chats — Edge-to-Edge Fill:** Every turn occupies 100% of the sidebar height cleanly on a single line.
* **🏎️ Long chats — Scrollbar-Free Proportional Hover-Pan:** Tired of scrolling a scrollbar? Sweep your pointer vertically across the rail and the full-size readable rows glide smoothly from Turn 1 to the end (with 36 px edge deadzones, instant freeze on click so you never misclick, and auto-tracking of your active turn when idle).
* **📍 4 px Global Overview Rail:** In Hover-Pan mode, a micro-rail on the left edge shows your viewport position plus subtle color ticks marking turns with **code** or **media**.
* **🎯 Live Progress, Scrubbing & Rich Previews:** Shows an inside-left progress bar for every turn currently on screen, supports click-and-drag scrubbing through the whole chat, flashes the target turn on smooth jump, and displays an instant preview popup with prompt, reply, code language/line counts, and image/video badges.
* **🙈 Clean Native Integration:** Hides Gemini's redundant chat scrollbar while docked, shifts top-right buttons cleanly out of the way, and collapses via an icon mimicking Gemini's own sidebar toggle (reopen anytime via the slim edge tab).

#### 💾 2. Split Cache & Deep History Indexing
Gemini lazy-loads older turns as you scroll up — which normally blinds minimaps on long threads.
* **⚡ Split `localStorage` Architecture:** Stores a tiny index + lazy per-chat keys (up to 120 chats with LRU eviction and verified turn-ownership checks so turns never leak across chats).
* **⇈ Index Current Chat:** Automatically pages up to the very beginning of the current conversation (waiting out loading spinners) and caches every turn.
* **☰↑ Index ALL Sidebar Chats:** Walks through your entire left-sidebar chat list one by one and caches full history while you grab coffee. Press `Esc` or click the status bar to stop anytime.
* **🗑 Per-Chat Cache Clear:** Wipe and re-sync the current chat's cache in one click.

#### 🗜️ 3. Code Block & User Prompt Spoilers (Shared Line Limit)
* **✂️ Instant Pre-Paint Collapse:** Long code blocks collapse cleanly to your chosen line limit (default `10L`, configurable `1–200` via the `10L` button) before they ever lag your scroll.
* **📌 Sticky Expanded Headers:** When you open a 900-line block, its header sticks to the top of the viewport, complete with line count (`· 900 lines`), a **"Jump to top of block"** button, and a clickable faded bottom edge with a chevron.
* **⇕ Expand / Collapse All:** Toggle every code block in the conversation at once.
* **💬 Unclamped User Prompts:** Overrides Gemini's rigid 4-line user prompt truncation so your own prompts follow the exact same shared line limit.

#### 🔒 4. Flexible Default Model Lock & Inline 5h / Weekly Usage Bar
Packed neatly into the **Limits (`⏲`)** 4-state button (`Usage` → `Usage + Lock [L]` → `Lock only [M]` → `Off`):
* **📊 Slim Inline Usage Bar:** Sits discreetly beneath the input pill without clutter.
  * Shows your **5-hour session %**, elapsed-window pace tick, and reset countdown.
  * Hover to switch live to your **Weekly (7d)** pool.
  * While Gemini is generating, transforms into a live gradient bar tracking **elapsed time**, **active model**, and **character count**, then displays the quota delta (`+X%`) right after finishing.
  * Click to force-refresh (`Ctrl+click` opens `/usage`).
* **🔐 Zero-Hardcode Default Model Lock:** Google renames models every other Tuesday, so nothing is hardcoded.
  * Passively memorizes whatever model **and** reasoning level (e.g. `Neon High`) you pick manually (mouse click or `Ctrl+Shift+M`).
  * Silently re-applies your choice on reloads and chat switches (masking Angular menu flicker) and skips locked/out-of-quota options so it never loops.
  * **How to change your default:** Just pick another model in Gemini's normal menu — or **Right-click** the `⏲` button to pin the currently active model immediately.
  * Injects a subtle `🔒 Pre-selected by mod` note right into Gemini's native hover tooltip over the model switcher.

#### 🎛️ 5. Left Sidebar Makeover (100% Modular)
Controlled by two clean Row 2 buttons: **`#`** (chat sizing) and **`◧`** (layout mods & previews).
* **↔️ Resizable Left Sidebar:** Drag the right edge (`190–520 px`, double-click to reset).
* **🔽 Top Menu & Notebooks Spoilers:** Packs the top menu into 2 buttons per row — or collapses it into a single row of icons. Gives **Notebooks (`Блокноты`)** the same clean 2-per-row / collapsible spoiler.
* **🧹 Relocated History & Geo Buttons:** Moves the full-row **History** item into an organic circular icon right next to top **Search** beside the Gemini logo, and shrinks the 2-line **Geo** footer into a subtle map-pin icon beside **Settings** (hover shows city/IP info, click refreshes location).
* **🎨 3-State Chat Size Cards (`#`):** Instantly spot massive threads vs. quick one-offs:
  1. **Color stripes** (tier-tinted cards with per-message stripes)
  2. **Line-free B&W proportional fill (`G`)** (calm monochrome horizontal fill scaled smoothly by message count + bolder titles on heavy chats)
  3. **Off**
* **⚡ Instant (0 ms) Flash-Free Previews:** Hovering any left-sidebar chat immediately shows its full untruncated title, turn count, and last message — while cleanly suppressing Gemini's lagging native tooltips so nothing flashes during fast mouse flicks.

#### 🛋️ 6. Workspace Polish, Audio & Performance
* **🖥️ Wide Chat (`↔`):** Breaks Gemini's narrow column constraints so text, tables, and code actually use your monitor.
* **🔍 Independent Text Zoom (`70%–150%`):** Separate `− / +` controls for **Left Sidebar (`✦`)**, **Chat (`T`)**, and **Minimap (`◫`)**. Click any icon to reset to `100%`.
* **ⓘ Hide Disclaimer:** Hides the footer disclaimer while preserving clean `16 px` floating breathing room under the input pill when the usage bar is also off.
* **🔔 Built-in Web Audio Cues (`▷` / `🔔`):** 4 distinct synthesized chimes each for **generation start** and **generation complete** — look away from the tab while Gemini thinks for 3 minutes and hear when it's done.
* **🚀 Lag & UX Fixes:** Keeps the `"Answer now"` button lifted safely above the input pill, uses `content-visibility: auto` + `IntersectionObserver`, and pauses heavy DOM scanning during active streaming.
* **🌍 Lightweight Multilingual Core:** Uses browser-native `Intl` APIs + a lean dictionary (`EN`, `RU`, `UK`, `DE`, `ES`, `ZH`) and icon-first DOM selectors.

---

### 🕹️ Controls Cheat Sheet

| Row | Button | What it does |
| :---: | :---: | :--- |
| **1** | `⇈` / `☰↑` / `🗑` | Index current chat / Index ALL sidebar chats (`Esc` stops) / Clear current chat cache |
| **1** | `10L` / `⇕` / `↔` | Set shared line limit (`1–200`) / Expand or collapse all code / Toggle Wide Chat |
| **1** | `▷` / `🔔` / `◫` | Cycle Start sound (`1–4`/off) / Cycle Done sound (`1–4`/off) / Hide right minimap |
| **2** | `#` | Cycle left chat sizing: **Color stripes** → **B&W fill** (`G`) → **Off** |
| **2** | `◧` | Cycle left sidebar: **Mods + Previews** → **Mods** (`M`) → **Previews** (`T`) → **Off** |
| **2** | `⏲` | **Click:** `Usage` → `Usage+Lock` (`L`) → `Lock` (`M`) → `Off` · **Right-click:** pin current model |
| **2** | `ⓘ` | Hide/show Gemini's bottom disclaimer |
| **2** | `✦` `T` `◫` `− +` | Independent text zoom for Left bar, Chat, and Minimap (click icon to reset) |

---

### 📦 Installation

1. Install [Tampermonkey](https://www.tampermonkey.net/) or [Violentmonkey](https://violentmonkey.github.io/).
2. Install directly from **[GreasyFork](https://greasyfork.org/ru/scripts/606781)** (recommended for automatic updates) or copy the script from this **[GitHub repository](https://github.com/asimoneo/Gemini-Power-UI)**.
3. Open [gemini.google.com](https://gemini.google.com/) and enjoy a sane interface.

### 🔐 Privacy & Credits
* **100% local:** Zero external servers, zero telemetry, zero external libraries.
* When the usage bar is enabled, it only fetches your own `gemini.google.com/usage` page using your existing browser session.
* All preferences stay in `GM_setValue`; chat index previews stay locally in `localStorage`.
* **Built with ❤️ (and mild rage at narrow columns):** Fully vibecoded inside Gemini Web using **Neon High**.
* Feedback & bug reports: [GitHub Issues](https://github.com/asimoneo/Gemini-Power-UI/issues) · [GreasyFork Feedback](https://greasyfork.org/ru/scripts/606781/feedback)

---

## 🇷🇺 Русский

### 😩 Знакомая боль?

Представьте: вы уже на 40-м сообщении долгой отладки в Gemini.
* Нужно найти тот самый запрос 25-минутной давности — и ваш палец делает кардио-тренировку на колёсике мыши, прокручивая **14 развёрнутых простыней кода по 600 строк**.
* Вы открываете новый чат, пишете огромный технический промпт, жмёте Enter… и только по поверхностному ответу на два абзаца понимаете, что **Google втихую сбросил модель обратно на базовую**.
* Перед вами широкий монитор, но Gemini упорно жмёт код и таблицы в узкую газетную колонку по центру экрана.
* Левая панель обрезает все названия чатов до `"Сделай так чтобы..."`, не даёт изменить свою ширину и гордо тратит две строки внизу, чтобы напомнить, из какого города ваш IP. *(Спасибо, Google, я и так в курсе, где сижу.)*
* А сколько осталось от 5-часового лимита — 12% или уже 98% — вы узнаёте только в момент внезапного блока посреди задачи.

**Gemini Power UI** решает всё это одним лёгким скриптом.

---

### 🚀 Подробно обо всех функциях

#### 🗺️ 1. Адаптивная правая миникарта-скроллбар
Пристыкованная панель с изменяемой шириной (`272–460 px`, двойной клик — сброс), которая сама подстраивается под **длину диалога** и **ваш масштаб шрифта**:
* **📄 Короткие чаты — информативные карточки:** Никаких гигантских пустых серых прямоугольников. В карточке аккуратно отображается жирный заголовок вашего запроса, разделитель, фрагмент ответа Gemini и бейджи кода/медиа (с умным ограничением максимальной высоты).
* **📏 Средние чаты — заполнение на 100% высоты:** Все сообщения ровно заполняют панель от верха до низа в одну строку.
* **🏎️ Длинные чаты — плавный Hover-Pan без прокрутки:** Не нужно крутить скроллбар внутри скроллбара. Просто ведите курсор сверху вниз — и полноразмерные читаемые строки плавно скользят от первого сообщения до последнего (мёртвые зоны 36 px по краям, мгновенная фиксация при клике без промахов и авто-слежение за текущим сообщением в покое).
* **📍 4 px шкала глобального обзора:** В режиме Hover-Pan тонкая полоска слева показывает текущую позицию и цветные метки сообщений с **кодом** и **медиа**.
* **🎯 Живой индикатор, scrub и превью:** Синяя полоска слева внутри пунктов показывает, какая часть сообщения на экране; зажатие и перетаскивание плавно крутит чат; клик мягко подсвечивает нужное сообщение; при наведении всплывает подробное превью с языками кода, количеством строк, картинок и видео.
* **🙈 Органичная интеграция:** Скрывает лишний родной скроллбар чата, аккуратно сдвигает верхние правые кнопки, сворачивается кнопкой в стиле самого Gemini и возвращается через тонкий язычок у правого края.

#### 💾 2. Раздельный кэш и глубокая индексация истории
Gemini подгружает старые сообщения лениво, из-за чего обычные миникарты «слепы» на длинных диалогах.
* **⚡ Раздельный кэш в `localStorage`:** Крошечный индекс + отдельные ключи по чатам (до 120 чатов с автоочисткой старых и проверкой принадлежности сообщений, чтобы чаты никогда не перемешивались).
* **⇈ Индексация текущего чата:** Сама прокручивает историю вверх (дожидаясь спиннеров подгрузки) и сохраняет весь диалог в кэш.
* **☰↑ Индексация ВСЕХ чатов слева:** По очереди обходит чаты в левой панели и кеширует их полную историю, пока вы наливаете кофе. Остановка в любой момент по `Esc` или клику по статусу.
* **🗑 Очистка кэша чата:** Мгновенный сброс и переиндексация текущего диалога.

#### 🗜️ 3. Спойлеры кода и длинных запросов (общий лимит строк)
* **✂️ Сворачивание до отрисовки:** Длинные блоки кода сворачиваются по вашему лимиту (по умолчанию `10L`, настраивается `1–200` кнопкой `10L`) ещё до того, как начнут тормозить страницу.
* **📌 Липкая шапка при раскрытии:** В открытом блоке кода шапка прилипает к верху экрана, показывает точное число строк (`· 900 строк`), кнопку **«К началу блока»**, а у свёрнутого блока работает кликабельная нижняя грань со стрелкой.
* **⇕ Развернуть / свернуть всё:** Одним кликом управляет всеми блоками кода в чате.
* **💬 Снятие лимита в 4 строки для ваших запросов:** Ваши длинные промпты перестают обрезаться на 4-й строке и подчиняются тому же общему лимиту строк.

#### 🔒 4. Гибкая фиксация модели по умолчанию и полоска лимитов (5ч / неделя)
Живёт в 4-режимной кнопке **Лимитов (`⏲`)**: `Лимиты` → `Лимиты + Модель [L]` → `Только модель [M]` → `Выкл`.
* **📊 Ненавязчивая полоска лимитов под строкой ввода:**
  * В покое показывает расход за **5 часов**, метку прошедшего времени окна и таймер до сброса.
  * При наведении плавно переключается на **Недельный (7д)** лимит.
  * Во время генерации превращается в живую полосу с **таймером**, **именем модели** и **счётчиком символов**, а по завершении показывает дельту расхода (`+X%`).
  * Клик — принудительно обновить (`Ctrl+клик` открывает `/usage`).
* **🔐 Фиксация модели без зашитых списков:** Google переименовывает модели чаще, чем выходит погода, поэтому в коде нет жёстких имён.
  * Скрипт сам запоминает любую модель **и** уровень рассуждений (например, `Neon Высокий`), выбранные вами кликом или через `Ctrl+Shift+M`.
  * Тихо применяет выбор при обновлении страницы и смене чата (без мерцания меню), пропуская заблокированные/исчерпанные модели.
  * **Как сменить модель по умолчанию:** Просто выберите другую в обычном меню Gemini — или нажмите **ПКМ** по кнопке `⏲`, чтобы мгновенно закрепить текущую.
  * Добавляет аккуратную строку `🔒 Выбрано модом` прямо внутрь стандартной подсказки при наведении на переключатель модели.

#### 🎛️ 5. Прокачка левой панели (всё отключается)
Две аккуратные кнопки во втором ряду: **`#`** (визуализация размера чатов) и **`◧`** (моды и превью).
* **↔️ Изменение ширины панели:** Тяните за правый край (`190–520 px`, двойной клик — сброс).
* **🔽 Спойлеры верхнего меню и «Блокнотов»:** Верхнее меню укладывается по 2 кнопки в ряд или сворачивается в одну полоску иконок. Раздел **«Блокноты»** получает такой же аккуратный спойлер.
* **🧹 Перенос «Истории» и «Гео»:** Кнопка **«История»** (раньше занимавшая целую строку) переезжает компактной иконкой к поиску рядом с логотипом Gemini, а двухстрочная геолокация сворачивается в аккуратную иконку-метку слева от настроек (наведение показывает город, клик обновляет).
* **🎨 3 режима размера чатов (`#`):** Сразу видно, где 50 сообщений, а где один вопрос:
  1. **Цветные полосы** (цвет по объёму + штрихи по числу сообщений)
  2. **Чистая Ч/Б заливка (`G`)** (никаких отвлекающих линий — только мягкая пропорциональная заливка от 12% до 100% + более жирный шрифт у крупных чатов)
  3. **Выкл**
* **⚡ Мгновенные превью (0 мс) без мерцания:** При наведении на любой чат слева моментально показывается его полный необрезанный заголовок, число сообщений и текст последнего обмена — при этом родные запаздывающие тултипы Gemini надёжно подавляются даже при быстром движении мышью.

#### 🛋️ 6. Комфорт, звук и ускорение
* **🖥️ Широкий чат (`↔`):** Убирает искусственные рамки ширины у текста, списков, таблиц и блоков кода.
* **🔍 Раздельный масштаб текста (`70%–150%`):** Независимые `− / +` для **левой панели (`✦`)**, **чата (`T`)** и **миникарты (`◫`)**. Клик по иконке сбрасывает на `100%`.
* **ⓘ Скрытие дисклеймера:** Убирает подпись под строкой ввода, сохраняя аккуратный нижний отступ (`16 px`), чтобы поле ввода не «прилипало» к краю экрана.
* **🔔 Звуковые сигналы Web Audio (`▷` / `🔔`):** По 4 встроенных ненавязчивых сигнала на **старт** и **завершение** ответа (никаких внешних аудиофайлов) — можно переключиться на другую вкладку, пока модель думает, и услышать, когда ответ готов.
* **🚀 Анти-лаг и «Ответить сразу»:** Поднимает кнопку «Ответить сразу» над полем ввода, использует `content-visibility: auto` + `IntersectionObserver` и откладывает тяжёлую обработку DOM во время стриминга.
* **🌍 Лёгкая мультиязычность:** Нативный `Intl` для времени и чисел + компактный словарь (`RU`, `EN`, `UK`, `DE`, `ES`, `ZH`) и иконочные селекторы.

---

### 🕹️ Шпаргалка по кнопкам

| Ряд | Кнопка | Действие |
| :---: | :---: | :--- |
| **1** | `⇈` / `☰↑` / `🗑` | Индексировать чат / Индексировать ВСЕ чаты (`Esc` — стоп) / Очистить кэш чата |
| **1** | `10L` / `⇕` / `↔` | Общий лимит строк (`1–200`) / Развернуть-свернуть весь код / Широкий чат |
| **1** | `▷` / `🔔` / `◫` | Звук старта (`1–4`/выкл) / Звук финиша (`1–4`/выкл) / Скрыть правую миникарту |
| **2** | `#` | Индикатор объёма чатов слева: **Цветные полосы** → **Ч/Б заливка** (`G`) → **Выкл** |
| **2** | `◧` | Левая панель: **Моды + Превью** → **Моды** (`M`) → **Превью** (`T`) → **Выкл** |
| **2** | `⏲` | **Клик:** `Лимиты` → `Лимиты+Модель` (`L`) → `Модель` (`M`) → `Выкл` · **ПКМ:** закрепить модель |
| **2** | `ⓘ` | Скрыть/показать дисклеймер под строкой ввода |
| **2** | `✦` `T` `◫` `− +` | Раздельный масштаб текста: левая панель, чат, миникарта (клик по иконке — сброс) |

---

### 📦 Установка

1. Установите [Tampermonkey](https://www.tampermonkey.net/) или [Violentmonkey](https://violentmonkey.github.io/).
2. Установите скрипт напрямую с **[GreasyFork](https://greasyfork.org/ru/scripts/606781)** (рекомендуется для автообновлений) или возьмите исходник в этом **[репозитории GitHub](https://github.com/asimoneo/Gemini-Power-UI)**.
3. Откройте [gemini.google.com](https://gemini.google.com/) и наслаждайтесь удобным интерфейсом.

### 🔐 Приватность и благодарности
* **100% локально:** Никаких сторонних серверов, телеметрии и внешних библиотек.
* При включённой полоске лимитов скрипт обращается только к вашей собственной странице `gemini.google.com/usage` в рамках текущей сессии браузера.
* Настройки хранятся в `GM_setValue`, кэш миникарты — локально в `localStorage`.
* **Сделано с ❤️ (и лёгкой злостью на узкие колонки):** Полностью завайбкожено прямо в веб-версии Gemini на модели **Neon High**.
* Баги и идеи: [GitHub Issues](https://github.com/asimoneo/Gemini-Power-UI/issues) · [Отзывы на GreasyFork](https://greasyfork.org/ru/scripts/606781/feedback)
