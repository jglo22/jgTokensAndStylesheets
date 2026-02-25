# globalDesignTokens — Rehydration

status: active

**GitHub Issues:** Open tasks tracked in [Project #1](https://github.com/users/jglo22/projects/1) — filter by Feature: `globalDesignTokens`

## What this is

W3C DTCG format design tokens defining Jim's visual identity. Token files + use-case stylesheets live in the public repo [`jgTokensAndStylesheets`](https://github.com/jglo22/jgTokensAndStylesheets). This lifeOS folder is context/docs only — no token files here.

## Current state

Simplified architecture agreed. Token files edited directly in the public repo. Use-case CSS files (`cv.css`, `website.css` etc.) live in same public repo. `sample.html` visual preview also in public repo.

## Decisions made

1. **W3C DTCG format** — industry standard, tool-agnostic
2. **Split token files** — organised by category (color, typography, spacing, border, page)
3. **Tokens + stylesheets in one public repo** (`jgTokensAndStylesheets`) — public so Figma, browsers, and future tools can pull directly
4. **Token units stored as px** — CSS files handle any conversion needed per medium
5. **Use-case CSS files** — `cv.css`, `website.css` etc. each handle their own layout/print rules alongside token consumption
6. **No context mapping** — no `print.json` / `digital.json`; per-medium decisions handled in each CSS file

## What consumes these tokens

| Consumer | Where | How |
|----------|-------|-----|
| CV builder | `cv.css` in public repo | CSS custom properties, px→pt conversion in CSS |
| sample.html | Public repo | Token values embedded directly for browser preview |
| Figma (future) | `tokens.json` via GitHub | Tokens Studio plugin |
| Website (future) | `tokens.json` via GitHub | Fetched as raw URL |

## To investigate

- Combine Figma files with design tokens? How to extract them from Figma — 2026-02-05

## Updates

- 2026-02-18 by Claude (Sonnet 4.6) [desktop] — merged CLAUDE.md into README, deleted stale token files from lifeOS, pushed sample.html to public repo, simplified architecture: px tokens, use-case CSS files, no context mapping
- 2026-02-11 by Claude (Opus 4.6) [laptop] — designed contextual token mapping (now removed)
- 2026-02-10 by Claude (Sonnet 4.5) [desktop] — scoped design tokens system, public repo strategy
