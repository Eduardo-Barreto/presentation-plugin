# Presentation Plugin for Claude Code

Generate professional HTML single-file presentations with a Vercel/Apple dark mode aesthetic.

## Installation

```bash
/plugin marketplace add Eduardo-Barreto/presentation-plugin
/plugin install presentation@presentation-tools
```

## Usage

```bash
/presentation:presentation "Your topic here"
```

With options:

```bash
/presentation:presentation "Introduction to Rust" 6 slides dark en
```

### Arguments

| Argument | Description | Default |
|----------|-------------|---------|
| Topic | Main subject of the presentation | Required |
| Slide count | Number of slides | 8 |
| Style | `dark` or `light` | dark |
| Language | `pt-BR` or `en` | pt-BR |

## Features

- Single HTML file output (no external dependencies)
- Dot grid background with fade effect
- Geist typography (loaded from Google Fonts)
- Keyboard navigation (arrows, space, page up/down)
- Touch/swipe support for mobile
- Scroll-snap between slides
- Intersection Observer animations
- Progress bar and slide counter
- Responsive design (mobile to projector)

## Visual Style

- Background: #0a0a0a (primary), #141414 (cards)
- Text: #fafafa (primary), #a0a0a0 (secondary)
- Accents: Blue (#3b82f6), Green (#22c55e), Amber (#f59e0b)
- Border radius: max 14px
- No emojis, gradients, or glassmorphism

## Components Included

- Cards with hover effects
- Grids (2, 3, 4 columns)
- Flow diagrams with arrows
- Progress bars (animated)
- Tables (minimal style)
- Terminal mockups
- Code blocks with syntax highlighting
- Badges with pulsing dot
- Stats with large numbers
- Comparison cards (before/after)
- Workflow steps
- Quotes

## Slide Structure

Default 8-slide structure:

1. **Hero** - Title, subtitle, CTA
2. **Problem** - Pain points, before/after comparison
3. **Solution** - How it works, workflow steps
4. **Features** - Grid of capabilities
5. **Demo** - Code, terminal, visual proof
6. **Stats** - Numbers that matter
7. **Details** - Table, specs, components
8. **CTA** - Call to action, next steps

## Dependencies

This plugin recommends using alongside:

- `frontend-design` skill - For distinctive interface design
- `web-design-guidelines` skill - For Vercel Web Interface Guidelines

## License

MIT
