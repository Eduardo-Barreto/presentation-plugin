# Presentation Style Guide

Dark mode minimalist aesthetic inspired by Vercel/Apple design language.

## Color Palette

### Backgrounds
```css
--bg-primary: #0a0a0a;    /* Main background */
--bg-secondary: #141414;  /* Cards, elevated surfaces */
--bg-tertiary: #1a1a1a;   /* Subtle elevation */
```

### Text
```css
--text-primary: #fafafa;    /* Headings, important text */
--text-secondary: #a0a0a0;  /* Body text, descriptions */
--text-tertiary: #777;      /* Labels, captions, muted */
```

### Borders
```css
--border-default: #2a2a2a;  /* Default state */
--border-hover: #404040;    /* Hover state */
```

### Accents (use sparingly)
```css
--accent-blue: #3b82f6;   /* Primary actions, links */
--accent-green: #22c55e;  /* Success, positive */
--accent-amber: #f59e0b;  /* Warning, attention */
```

## Typography

### Font Stack
```css
--font-sans: 'Geist', -apple-system, BlinkMacSystemFont, sans-serif;
--font-mono: 'Geist Mono', 'SF Mono', Consolas, monospace;
```

### Headings
| Element | Size | Weight | Letter-spacing |
|---------|------|--------|----------------|
| h1 | 56-96px (clamp) | 600 | -0.03em |
| h2 | 42-68px (clamp) | 600 | -0.02em |
| h3 | 24-36px (clamp) | 500 | -0.01em |

### Body & Labels
| Type | Size | Weight | Style |
|------|------|--------|-------|
| Subtitle | 18-24px | 400 | Secondary color |
| Body | 14-16px | 400 | Secondary color |
| Label | 11-12px | 500 | Uppercase, mono, wide tracking |

### Label Pattern
```css
.label {
  font-family: var(--font-mono);
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  color: var(--text-tertiary);
}
```

## Spacing

### Border Radius
```css
--radius-sm: 8px;   /* Buttons, small elements */
--radius-md: 12px;  /* Cards, containers */
--radius-lg: 14px;  /* Large cards, modals */
```

**Rule**: Never exceed 14px border-radius.

### Padding
| Context | Value |
|---------|-------|
| Slide | 80px vertical, 48px horizontal |
| Card | 32px all sides |
| Button | 14px 28px |
| Badge | 6px 12px |

### Gaps
| Context | Value |
|---------|-------|
| Grid items | 12-16px |
| Stacked elements | 16-24px |
| Sections | 40-48px |

## Dot Grid Background

```css
.dot-grid {
  position: fixed;
  inset: 0;
  background-image: radial-gradient(
    circle at center,
    rgba(255, 255, 255, 0.15) 1px,
    transparent 1px
  );
  background-size: 32px 32px;
  mask-image: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 1) 0%,
    rgba(0, 0, 0, 0.5) 50%,
    rgba(0, 0, 0, 0) 100%
  );
  pointer-events: none;
  z-index: 0;
}
```

## Animations

### Keyframes
```css
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes scaleIn {
  from { opacity: 0; transform: scale(0.95); }
  to { opacity: 1; transform: scale(1); }
}

@keyframes slideRight {
  from { opacity: 0; transform: translateX(-30px); }
  to { opacity: 1; transform: translateX(0); }
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}
```

### Timing
| Property | Duration | Easing |
|----------|----------|--------|
| Hover transitions | 0.2s | ease |
| Entry animations | 0.4-0.6s | ease |
| Stagger delay | 100-150ms | - |

### Stagger Pattern
```css
.delay-1 { animation-delay: 0.1s; }
.delay-2 { animation-delay: 0.2s; }
.delay-3 { animation-delay: 0.3s; }
.delay-4 { animation-delay: 0.4s; }
.delay-5 { animation-delay: 0.5s; }
.delay-6 { animation-delay: 0.6s; }
```

## Hover States

### Cards
```css
.card:hover {
  transform: translateY(-2px);
  border-color: var(--border-hover);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}
```

### Buttons
```css
.btn:hover {
  /* Primary: lighten background */
  /* Secondary: brighten border */
}
```

### Interactive Elements
```css
.interactive:hover {
  border-color: var(--accent-blue);
}
```

## Avoid

- Emojis
- Colored gradients or gradient orbs
- Glassmorphism / backdrop-blur
- Saturated colors as backgrounds
- Border-radius > 14px
- Slow animations (> 0.6s)
- Colored shadows
- Decorative elements without purpose
