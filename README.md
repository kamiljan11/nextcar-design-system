# NextCar Design System

Design style of [nextcar.is](https://nextcar.is) (NextCar, Service & Performance, Keflavík), packaged so Claude Design and other tools can reproduce it.

## Files

| Path | What it is |
|---|---|
| `DESIGN.md` | The design brief: character, colour rules, type, shapes, components, imagery, motion, voice, do and don't. Start here. |
| `tokens/tokens.css` | CSS custom properties (`--nc-*`) plus Google Fonts import. |
| `tokens/tokens.json` | Same tokens in W3C Design Tokens JSON. |
| `tokens/tailwind-theme.css` | Tailwind v4 `@theme` block matching the live site's shadcn variables. |
| `components/components.css` | Ready classes: buttons, header/nav, hero, service grid, product card, split feature, trust row, FAQ, input, marquee, footer, motion. |
| `preview/index.html` | Living style guide page using every component. |
| `assets/logo.svg` | Text wordmark (NEXT white, CAR red, italic Barlow Condensed). |

## Using it with Claude Design

1. In Claude Design, set up a design system and point it at this repository (or upload `DESIGN.md`, `tokens/tokens.css` and `components/components.css`).
2. Prompt with the brand name, for example: "Landing page for the NextCar tyre service, use the NextCar design system."
3. For quick one-off prompts without the repo, paste the "Character in one line" and "Colour rules" sections of `DESIGN.md`.

## Quick recipe

Dark `#0c0c0e`, one red `#c9302d` (text red `#e24942`), grey body `#9e9ea2`, Barlow Condensed uppercase headings with a red eyebrow above, Barlow body, square buttons with arrows, 1px `#262629` hairline grids, moody workshop photos, Lucide red line icons.

## Source

Extracted from the production CSS and computed styles of nextcar.is on 2026-09-20. Photos referenced in the preview are served from nextcar.is/brand/.
