---
name: design-nasmotrennost
description: >-
  Глобальный навык насмотренности для КРАСИВЫХ ДИНАМИЧНЫХ сайтов (не статичных).
  Motion-first: интерактивные градиенты, scroll/cursor/physics, hero/CTA/nav паттерны.
  Обязательно опираться на библиотеку SOURCES.md (motionsites, getlayers, 60fps,
  cta.gallery, loadmo.re, supahero, navbar.gallery, kage, refero, 21st…).
  Использовать при любом запросе «сделай красивый сайт / лендинг / анимацию / UI».
---

# Design Насмотренность — Motion First

Ты строишь сайты, которые **движутся и реагируют**, а не лежат мёртвой вёрсткой.
Статичная страница без cursor/scroll/physics = провал навыка.

## Жёсткое правило

1. **Сначала источники** — открой `SOURCES.md`, выбери 2–4 референса под задачу
2. **Потом курс** — один визуальный язык (не мешать 5 стилей)
3. **Потом motion-план** — минимум 3 живых поведения (см. ниже)
4. **Потом код** — без «красивой картинки без взаимодействия»

Не выдумывай продукт пользователя. Если сайта/URL нет — спроси или сделай демо-лабу навыка, но **не подставляй чужой DESIGN.md**.

## Минимум динамики (обязателен)

Каждый новый сайт/лендинг должен иметь **≥3** из списка:

| # | Поведение | Откуда вкус |
| --- | --- | --- |
| 1 | Cursor-reactive фон/градиент/spotlight | getlayers, motionsites |
| 2 | Scroll-linked reveal / scrub / parallax | 60fps, loadmo.re |
| 3 | Magnetic / morph CTA | cta.gallery, 60fps |
| 4 | Живая навигация (blur/hide/morph) | navbar.gallery |
| 5 | Stagger + spring на появление | 60fps Motion tags |
| 6 | Shared/continuity transition между блоками | 60fps Shared Element |
| 7 | Idle micro-motion (дыхание, drift) | motionsites backgrounds |

Плюс всегда: `:active` press (`scale ~0.97`), `prefers-reduced-motion`.

## Откуда брать вкус (обязательный стек)

Полный каталог: **`SOURCES.md`**. Быстрый маршрут:

| Задача | Открыть |
| --- | --- |
| Целый лендинг / промпт сцены | motionsites.ai · getlayers.ai |
| Hero | supahero.io · motionsites Hero |
| CTA | cta.gallery |
| Navbar | navbar.gallery |
| Мелкий «дорогой» motion | 60fps.design |
| Смелый mobile | loadmo.re |
| Свежие релизы | recent.design |
| Соцпосты | posts.design |
| DESIGN.md / токены | styles.refero.design |
| UI → промпт | kage.design · 21st.dev · vibeprompts.dev |
| AI-product UI | aicss.dev · ui.halaska.com · ui.xiod.dev · obsidianui.dev |

## Композиция (не ломай)

- Первый экран = **одна композиция**: бренд, 1 headline, 1 фраза, CTA, доминирующий visual plane
- Бренд сильнее headline
- Full-bleed hero по умолчанию
- Карточки не в герое
- Не AI-клише: purple-gradient, cream+terracotta+serif, broadsheet, emoji-декор
- Шрифты выразительные (не Inter/Roboto/Arial как единственный стек)

## Техника motion

```txt
Свойства: transform + opacity (+ filter осторожно)
Не: transition: all; scale(0); ease-in на вход
Частые действия (клавиатура, toggle 100+/день): без анимации
Жесты: springs / interruptible, velocity handoff
Scroll: IntersectionObserver или scroll-driven animations
Cursor: rAF + lerp (сглаживание), не прыгать за мышью 1:1 грубо
```

Детали: `MOTION.md`. Паттерны: `PATTERNS.md`. Чеклист: `CHECKLIST.md`.

## Рабочий цикл

1. Уточни продукт/URL (не додумывай)
2. Выбери референсы из `SOURCES.md` → запиши в комментарий/отчёт
3. Motion-план (≥3 поведения)
4. Токены CSS + шрифты
5. Собери hero динамичным
6. Секции с одной работой + scroll life
7. Проверь mobile + reduced-motion
8. Покажи скрин/видео живого движения

## Антипаттерны навыка (ИИ-грязь — НЕМЕДЛЕННЫЙ FAIL)

Если страница похожа на это — **переделать с нуля**, не «подкрутить»:

- Мягкий **светящийся blob / orb / mesh-шар** как главный визуал
- Неон (mint/cyan/purple glow) на почти-чёрном фоне
- Particle sparkles + cursor spotlight вместо реального кадра
- Декоративный градиент / abstract glow как «идея» героя
- Dark SaaS-шаблон с двумя pill-кнопками и пустым космосом

**Главный визуал = реальное фото / продукт / место / сильная типографическая композиция.**  
Движение обслуживает кадр, а не маскирует пустоту.

Смотри эталон пользователя: [Vintage Care](https://motionsites.ai/?prompt=vintage-care) — воздух, объект, serif, без blob.

Другие антипаттерны:

- Статичный HTML и назвать динамикой
- Додумать чужой продукт без запроса
- 12 анимаций сразу → шум (лучше 3 точных)
