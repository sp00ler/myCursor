# PrismView Design System (v2 — upgraded)

Легковесный просмотрщик и каталогизатор медиа для Windows 11.
Язык: Fluent Design 2 + Content First + тактильный отклик.

## Vision

Соединить скорость классического ACDSee с современным Fluent:
Mica/Acrylic, плавающий HUD, command palette вместо серых Win32-диалогов.

## Principles

1. **Content First** — медиа главный герой; chrome вторичен
2. **Zero Native Friction** — Move/Copy/Rename/Tags только в своих оверлеях
3. **Instant Feedback** — реакция на pointer-down, не на click
4. **Keyboard First** — шорткаты без анимации открытия
5. **Restraint** — один акцент, минимум glow, никакого декора ради декора

## Tokens

```css
:root {
  /* Surfaces */
  --surface-base: #0D1117;
  --surface-mica: rgba(22, 27, 34, 0.75);
  --surface-card: #161B22;
  --surface-card-hover: #1C2128;
  --surface-hud: rgba(22, 27, 34, 0.88);
  --surface-viewer: #08090C;

  /* Borders */
  --border-subtle: rgba(255, 255, 255, 0.08);
  --border-focus: rgba(75, 163, 255, 0.55);

  /* Accent — cooler, less “glow UI” */
  --accent: #4BA3FF;
  --accent-muted: rgba(75, 163, 255, 0.14);
  --danger: #F85149;

  /* Text */
  --text-primary: #F0F6FC;
  --text-secondary: #8B949E;
  --text-muted: #484F58;

  /* Type */
  --font-ui: "Segoe UI Variable", "Segoe UI", sans-serif;
  --font-mono: "JetBrains Mono", "Cascadia Mono", ui-monospace, monospace;

  /* Radii */
  --r-btn: 6px;
  --r-card: 8px;
  --r-hud: 12px;

  /* Motion */
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
  --dur-press: 100ms;
  --dur-chrome: 120ms;
  --dur-toast: 160ms;

  /* Elevation */
  --shadow-subdued: 0 4px 12px rgba(0, 0, 0, 0.25);
  --shadow-hud: 0 12px 32px rgba(0, 0, 0, 0.45),
    inset 0 0 1px rgba(255, 255, 255, 0.1);
}
```

## Typography

| Role | Font | Size / weight |
| --- | --- | --- |
| Title bar / headings | Segoe UI Variable Display | 13–16 SemiBold |
| File names / labels | Segoe UI Variable Text | 12–14 Medium |
| EXIF / technical | JetBrains Mono | 11 Regular |

Inter не используем.

## Screens

### Catalog `/catalog`

- Custom titlebar 44px, browser-like tabs
- Breadcrumb: текст + одна capsule на текущем сегменте
- Modes: Grid / Detail List / Masonry
- Sidebar: Favorites сверху, дерево с chevron (rotate only)
- Status footer: densе — путь, счётчик, zoom slider

### Viewer `/viewer`

- Canvas `--surface-viewer`
- Top header auto-hide on idle
- Bottom floating HUD (Acrylic): prev/next, fit/1:1, rotate, move/copy/delete, rating
- Info flyout: histogram + EXIF
- Pan 1:1; zoom to cursor; interruptible

### Command palette (Ctrl+M / Ctrl+Shift+C)

- Без enter/exit анимации (частота высокая)
- Live search + pinned destinations `[1][2][3][4]`
- Toast с Undo (Ctrl+Z): 160ms ease-out

## Micro-interactions

| Element | Behavior |
| --- | --- |
| Button press | `scale(0.97)` 100ms ease-out on `:active` |
| Row hover | background swap ≤80ms или без transition |
| Image change | opacity crossfade 50ms |
| Toast | 160ms in / 120ms out, no bounce |
| Sidebar chevron | rotate 120ms transform only |
| Palette | instant open |

## Accessibility

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

Focus ring: `--border-focus`, visible for keyboard only where possible.
