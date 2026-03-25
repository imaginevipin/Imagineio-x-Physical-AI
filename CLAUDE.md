This is an imagine.io project — apply the Prism Design System.

## Context

Always read `SUMMARY.md` first in every conversation. It contains the full project context, decisions, and build log. Update it after every significant build or decision.

## Outputs

All deliverables go in `outputs/` as flat versioned files — naming convention: `[page-name]-v[N].html` (e.g. `homepage-v5.html`). Never overwrite a version — always create a new version file.

## CSS / HTML Separation

From `homepage-v5` onwards, every HTML file has a paired external CSS file:

- HTML lives in `outputs/` → `outputs/homepage-vN.html`
- CSS lives in `css/` (project root) → `css/homepage-vN.css`
- The HTML file links to it as: `<link rel="stylesheet" href="../css/homepage-vN.css">`
- `tokens.css` (global Prism design tokens) stays at the project root and is always linked separately as `../tokens.css`
- Never write `<style>` blocks inside HTML files for v5 onwards — all styles go in the paired `.css` file

## Model Usage

| Task | Model |
|------|-------|
| Quick answers, small edits | Haiku `claude-haiku-4-5-20251001` |
| Most work (UI, coding, iteration) | Sonnet `claude-sonnet-4-6` |
| Deep research, complex tasks, advanced coding | Opus `claude-opus-4-6` |
