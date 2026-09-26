# Библиотека насмотренности (источники пользователя)

Это **канонический список**. Перед дизайном сайта сверяйся с ним.
Собрано пользователем специально для апгрейда агента.

## A. Промпт-библиотеки целых сайтов / слоёв

| Ресурс | Зачем | Как использовать |
| --- | --- | --- |
| [motionsites.ai](https://motionsites.ai) | 500+ промптов сайтов, 100+ 3D, 100+ интерактивных градиентов, 300+ фонов, секции с анимацией | Открыть шаблон (пример: `?prompt=vintage-care`), скачать/скопировать промпт, перенести стиль+motion |
| [getlayers.ai](https://getlayers.ai) | 50+ промптов, 300+ 3D, 1000+ градиентов, секции со scroll/mouse motion | Copy prompt → агент → self-contained HTML / Next |
| [supahero.io](https://supahero.io) | Галерея hero-секций | Взять структуру героя + тип motion |
| [vibeprompts.dev](https://vibeprompts.dev) | 286 компонентов с готовыми промптами | Блоки UI |
| [kage.design](https://kage.design) | Реальные UI продуктов → промпт / MCP | Скопировать как prompt для Cursor |

## B. Паттерны отдельных частей

| Ресурс | Зачем |
| --- | --- |
| [cta.gallery](https://cta.gallery) | CTA, на которые кликают (типы: button, form, modal, pricing…) |
| [navbar.gallery](https://navbar.gallery) | Паттерны навигации |
| [loadmo.re](https://loadmo.re) | Смелые мобильные сайты |
| [60fps.design](https://60fps.design) | Микро-взаимодействия: morph, spring, stagger, rubber-band, shared element… |
| [recent.design](https://recent.design) | Лучшее «сегодня» |
| [posts.design](https://posts.design) | Острые соцпосты |

## C. Design systems / DESIGN.md

| Ресурс | Зачем |
| --- | --- |
| [styles.refero.design](https://styles.refero.design) | 2000+ AI-readable design systems + DESIGN.md |
| [obsidianui.dev](http://obsidianui.dev) | UI kit / компоненты |
| [ui.xiod.dev](https://ui.xiod.dev) | UI библиотека |

## D. AI-product UI

| Ресурс | Зачем |
| --- | --- |
| [aicss.dev](https://aicss.dev) | UI-блоки для AI-агентов |
| [ui.halaska.com](https://ui.halaska.com) | Компоненты AI-продуктов |
| [21st.dev](https://21st.dev) | 1000+ community UI |

## E. Инфра для агента

| Ресурс | Зачем |
| --- | --- |
| [agent-memory.dev](https://agent-memory.dev) | Постоянная память кодинг-агентов |
| [Agent-Reach](https://github.com/Panniantong/Agent-Reach) | Глаза агента: поиск/чтение сети |
| motionsites MCP | В nav motionsites есть MCP — подключать когда доступен |

## F. Эталонный пример от пользователя

- Скрин + URL: [Vintage Care на motionsites](https://motionsites.ai/?prompt=vintage-care)
- Урок: смелый visual hero, выразительная типографика, воздух, не «дашборд», готовность к motion/интерактиву, код через GitHub/prompt

## Как выбирать референсы (30 секунд)

1. Тип страницы → motionsites / getlayers / supahero
2. Нужен «дорогой» клик-feel → 60fps + cta.gallery
3. Mobile-first смелость → loadmo.re
4. Токены/система → refero DESIGN.md
5. Записать в комментарий кода: `// refs: motionsites/vintage-care, 60fps/morph, cta.gallery`

## Правило цитирования

Не копируй чужой бренд/фото/текст один-в-один в прод клиента.
Бери: **композицию, motion-логику, плотность, ритм, приёмы**.
