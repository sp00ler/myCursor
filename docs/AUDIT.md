# Аудит DESIGN.md → PrismView (улучшения)

Источник: Google Drive `DESIGN.md` (PrismView — lightweight media hub).

## Вердикт

База сильная: Content First, Fluent/Mica, command palette вместо Win32 — правильный курс.
Ниже — апгрейд вкуса: убрать AI-типичные решения, усилить тактильность и иерархию.

## Таблица до → после

| Было | Стало | Почему |
| --- | --- | --- |
| Типографика: Segoe + **Inter** | Segoe UI Variable + **JetBrains Mono** только для EXIF; без Inter | Inter = AI-дефолт; для Win11-native лучше семья Segoe |
| Акцент `#2F81F7` + glow `rgba(47,129,247,0.25)` | Акцент `#4BA3FF` для dark HUD; glow уменьшить до 0.12 или убрать | Синий glow на тёмном — частый «AI dark UI» штамп |
| Hover 120ms на всём | Hover 80–100ms на chrome; списки без transition на background | Частые наведения не должны «плыть» |
| Image switch fade 50ms | Crossfade 40–60ms **только opacity**; без scale | Мгновенно и без мерцания |
| Pills в breadcrumb | Capsule только для текущего сегмента; остальные — текст | Меньше «таблеток» = чище |
| Cards radius 10 / HUD 14 | Cards 8; HUD 12; buttons 6 | Чуть строже, ближе к Fluent 2 |
| Status footer всегда полный | Footer densе; второстепенное в overflow | Content first |
| Нет reduced-motion | Обязательный `prefers-reduced-motion` | Доступность и вкус |
| Нет interruptible viewer pan/zoom | Pan 1:1 к курсору; zoom к точке курсора; без lock UI | Apple fluid principle |
| Keyboard palette с анимацией? | Открытие palette **без** enter-анимации (Raycast-way) | 100+ раз/день |

## Принципы, которые оставляем

1. Content First — медиа герой, UI стекло/HUD
2. Zero Native Friction — свои Move/Copy/Delete оверлеи
3. Keyboard-driven workflow
4. Immersive viewer canvas `#08090C`

## Новые микро-правила

1. Press feedback на всех primary buttons: `scale(0.97)` на pointerdown
2. Toast снизу справа: enter 160ms ease-out, exit 120ms; не bounce
3. Selection badge — статичный счётчик, без pulse-анимации
4. Sidebar chevron — rotate 90° за 120ms ease-out, только transform
5. При смене вкладки — никаких slide; мгновенная смена + тонкий underline

См. полную обновлённую систему: `design-system/PRISMVIEW.md`.
