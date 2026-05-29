# Framer Theme — Agent Session Log

## Version 1.2.2 (2026-05-29)

### Fixes & Improvements
- **WCAG Contrast**: Replaced pink-accent grayscale light palette with warm rose gold (`#C4837A` brand, `#FDF8F5` base, `#4A3F3D` text). Resolved all light-theme contrast warnings.
- **Inline Code**: Fixed dark `#221A20` hard-code → `var(--code-background)`, eliminating black-block rendering of `* / + -` in light theme.
- **Code Comments**: Adjusted `--code-comment` from `#A0938E` (2.6:1 on code‑bg) to `#8A7A72` (~4.8:1).
- **Bold Pink Snippet**: Replaced hard-coded `#FF69B4` with `var(--bold-color)`.
- **`accent-blue` Class**: Added full heading‑gradient and canvas‑color support for both dark and light modes.
- **Tab Indicator**: Replaced hard-coded pink gradient with `var(--color-brand)` based gradient.
- **Table Styles**: Unified duplicate table rules into single minimal-rule set; removed redundant "Minimal Tables" snippet.
- **Dark Table Header**: Added `.theme-dark .markdown-rendered th { background: rgba(255,255,255,0.04) }` for subtle visibility.
- **Light Theme `--text-accent-hover`**: Changed hard-coded `#A8615A` to `color-mix(in srgb, var(--color-brand) 80%, black)`, so it follows accent variants.
- **`--color-warning` / `--color-error`**: Defined in both themes; warning/error notification borders now visible.
- **CM6 Active Line**: Fixed dead `.cm-active.*` selectors → `.cm-activeLine.cm-line` / `.cm-activeLineGutter` for CodeMirror 6.
- **Unresolved Links**: Replaced hard-coded `#666666`/`#999999` grays with `var(--text-muted)` for theme adaptation.
- **`--graph-node-tag`**: Light mode now uses `var(--color-hot)` consistent with dark mode.
- **`--code-important`**: Light mode now uses `var(--color-brand)` instead of hard-coded `#C4837A`.
- **Removed dead code**: `--italic-color`, `--search-background-color`, `--color-pink-soft/rose/dusty/lavender`, `-moz-appearance: textfield`.

### Unchanged
- Canvas node color variants 2–6 remain hard-coded (semantic colors).
- Canvas snap-point `#FFFFFF` borders retained (decorative, functional without them).
- Universal `*` transition selector retained (common theme pattern; risky to refactor).

### Files
- `theme.css` — main theme (2695 lines)
- `manifest.json` — version 1.2.2
