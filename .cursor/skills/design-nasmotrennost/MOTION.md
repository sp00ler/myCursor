# Motion: правила вкуса

Сжатая выжимка Emil Kowalski + Apple Fluid Interfaces для веба.

## Решать: анимировать ли вообще

| Частота | Решение |
| --- | --- |
| 100+ раз/день (шорткаты, command palette toggle) | Никогда |
| Десятки/день (hover списка) | Убрать или сильно укоротить |
| Иногда (модалка, toast, drawer) | Стандарт 150–250ms |
| Редко / первый раз | Можно delight |

Клавиатурные действия — **без** анимации открытия/закрытия.

## Технические правила

```css
/* Хорошо */
.btn {
  transition: transform 120ms ease-out, opacity 120ms ease-out;
}
.btn:active {
  transform: scale(0.97);
}

/* Плохо */
.btn {
  transition: all 300ms ease-in;
}
```

- Анимируй только `transform` и `opacity`
- Не `scale(0)` → используй `scale(0.95)` + opacity
- `ease-out` на вход; `ease-in` на появлении ощущается вялым
- Popover: `transform-origin` от триггера
- Modal: origin по центру ок

## Springs (жесты)

Для drag/swipe/sheet — springs, не фиксированный CSS keyframes:

- По умолчанию critically damped (без лишнего bounce)
- Bounce только если жест нёс momentum (flick)
- Анимация должна прерываться пальцем в любой момент
- На release — передать velocity в spring

## Сайт: минимум 2–3 движения

Примеры хорошего набора для лендинга:

1. Hero: мягкий fade/rise текста (~400ms, once)
2. CTA: press scale 0.97
3. Ниже fold: лёгкий stagger секций при scroll (с `IntersectionObserver`, уважать reduced-motion)

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```
