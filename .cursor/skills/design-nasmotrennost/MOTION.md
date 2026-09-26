# Motion Playbook — динамика, не декорация

Вкус: [60fps.design](https://60fps.design) tags + Apple fluid + Emil Kowalski.

## Обязательный набор для лендинга

### 1. Cursor field (фон живой)
- Spotlight / mesh / gradient следует за курсором с **lerp** (0.08–0.15)
- На mobile: гироскоп или медленный idle drift
- refs: getlayers gradients, motionsites Animated Backgrounds

### 2. Scroll life
- Секции появляются stagger’ом (y: 24→0, opacity)
- Хотя бы один scrub/parallax слой
- Progress hint (линия/точка) опционально
- refs: 60fps Scroll / Parallax / Stagger

### 3. CTA magnetism
- Кнопка слегка тянется к курсору в радиусе ~80px
- Press: `scale(0.97)` мгновенно
- refs: cta.gallery + 60fps Button / Spring

### 4. Nav behavior
- Scroll down → compact / blur / hide
- Scroll up → показать
- refs: navbar.gallery

## Словарь эффектов (из 60fps)

Используй точные имена: Morph, Stagger, Spring Physics, Shared Element, Reveal, Rubber-banding, Shimmer, Parallax, Idle Animation, Liquid Glass, Card Stack, Flick.

## Код-скелет (идея)

```js
// lerp cursor
cx += (tx - cx) * 0.12;
cy += (ty - cy) * 0.12;
root.style.setProperty('--mx', cx + 'px');
root.style.setProperty('--my', cy + 'px');

// magnetic
const dx = mx - bx, dy = my - by;
if (Math.hypot(dx, dy) < 80) btn.style.transform = `translate(${dx*0.25}px, ${dy*0.25}px)`;
```

## Reduced motion

```css
@media (prefers-reduced-motion: reduce) {
  * { animation: none !important; transition: none !important; }
}
```
При reduce: оставь статичный красивый кадр, убери cursor chase.
