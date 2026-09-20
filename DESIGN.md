# NextCar Design Language

Brief for Claude Design and any AI or human building NextCar screens. Read this first, then use `tokens/` and `components/`.

Source of truth: the live site https://nextcar.is (Next.js, Tailwind v4, shadcn/ui). Values below were extracted from its production CSS in September 2026.

## Character in one line

Dark workshop at night, lit by one red signal light. Bold flat, industrial, condensed, confident. Think motorsport pit lane and premium tool brand, not luxury car dealer.

Style family: **bold flat on dark** with a single signal colour. No glass, no gradients as decoration, no rounded "friendly SaaS" shapes.

## Colour rules

| Token | Hex | Use |
|---|---|---|
| background | `#0c0c0e` | page |
| card | `#131416` | cards, tiles, inputs |
| muted | `#1a1a1d` | raised surfaces, popovers |
| accent | `#212124` | hover fill |
| border | `#262629` | every hairline and divider |
| foreground | `#e9e9eb` | headings and key text |
| muted-foreground | `#9e9ea2` | body copy, idle nav, captions |
| primary | `#c9302d` | filled buttons, icons, active underline, outlines |
| primary-text | `#e24942` | red used as text on dark (eyebrows, links, accent line) |

1. Red is a signal, not a fill. Roughly 5 to 10 percent of any screen. Buttons, icons, eyebrows, one italic accent line, active states. Never red section backgrounds.
2. Red text uses `primary-text` (#e24942), filled red uses `primary` (#c9302d).
3. Near-black neutrals have a very slight cool tint. Do not use pure #000 for surfaces.
4. No other brand colours. Status colours (error #eb827b, warning #edb200) only for real states.
5. The site is dark only. If a light variant is ever needed, invert surfaces but keep red and type unchanged.

## Typography

- **Barlow Condensed** (display): all headings, nav, card titles, FAQ questions, the wordmark. Always UPPERCASE, weight 700 (wordmark 800 italic), tracking +0.025em.
- **Barlow** (text): body, buttons, eyebrows, inputs. Body 16px/1.5, secondary 14px.
- Hero: 48 to 60px, line-height 1.08. Two lines: first in foreground, second in *italic red* (`.nc-accent-line`). Example: "NEXT LEVEL 5D ALIGNMENT. / NEXT LEVEL PERFORMANCE."
- Section title: 30px condensed uppercase.
- Eyebrow above every section title: 12px Barlow bold, tracking 0.18em, uppercase, red. Example: `EQUIPMENT & SOLUTIONS`.
- Nav: 13px condensed semibold, tracking 0.1em, muted grey, active item red with a 2px red underline sitting on the header border.
- Body copy is grey (`muted-foreground`), never white. White is for headings.

## Shape and structure

- **Square corners.** Buttons, cards, tiles and image panels have radius 0. Only inputs use a small radius (0.3rem). The single pill is the floating "Ask a question" chat button.
- Structure is drawn with 1px `#262629` hairlines: header bottom border, full-width section dividers, vertical dividers between service columns, FAQ rows.
- Layouts are grids of equal columns: 5 service columns, 7 product cards, 5 trust items, 4-column split (text, photo, text, photo).
- Container max 86rem (1376px), 2rem side padding on desktop, 1rem on mobile. Sections breathe: about 5rem vertical.
- No drop shadows at rest. Depth comes from the surface steps (background, card, muted) and borders.

## Components (see `components/components.css`)

- Primary button: red fill, white uppercase bold 14px, 48px tall, 28px side padding, arrow icon that nudges right on hover. The hero primary button "breathes" with a soft red glow (`.nc-glow`).
- Outline button: 1px white border, white text, turns red on hover. Outline red variant for "View all products".
- Arrow link: red uppercase 12px bold plus arrow ("SHOP NOW ->").
- Service tile: red line icon 36px (stroke 1.5, Lucide style), condensed uppercase title, grey two-line description, bordered column.
- Product card: card surface, 1px border, product PNG on transparent background, condensed title, grey text, red arrow link. Hover lifts 4px with a red under-glow and a red light that travels around the border.
- Boxed label: red 1px outline, condensed red uppercase text with wide tracking ("NOVEMBER 2026", "PRICES 30-40% LOWER").
- FAQ: condensed uppercase questions, red "+" on the right, hairline between rows.
- Brand marquee: greyscale partner logos scrolling in a bordered strip (MAHLE, redats, FCAR, adler, LAUNCH, HOFMANN, NEXION).
- Footer: column headings are red condensed with wide tracking, links grey, contact rows with small red line icons.

## Imagery

- Real photos of the workshop and showroom: dark interiors, red equipment, red LED strips. Moody, low key, high contrast.
- Hero photos sit under a left-to-right dark gradient so the text column on the left stays readable.
- Product imagery is cut-out PNG on transparent background, placed on the dark card.
- Icons: Lucide line icons, stroke 1.5, red. Never filled or multicolour icons.

## Motion

- Content rises 18px and fades in on load or scroll (`.nc-rise`, expo-out easing).
- Hover: lift plus red glow on cards, arrow nudge on buttons, rotating border light on product cards.
- Primary hero CTA breathes on a 3.2s loop.
- Partner logos scroll in a continuous marquee.
- Respect `prefers-reduced-motion`: all of the above switch off.

## Voice

Short, confident, technical. Uppercase headings of 2 to 6 words. Body sentences plain and factual ("21 calendar days from the payment clearing."). Repeated brand phrase: "Next level". Languages: English, Icelandic, Polish.

## Do

- One red accent per view, dark everything else.
- Condensed uppercase headings with an eyebrow above.
- Square buttons with arrows.
- Hairline grids.
- Real workshop photography.

## Don't

- Rounded cards, pill buttons (except the chat FAB), soft pastel shadows.
- Gradients or glassmorphism as decoration.
- White or light page backgrounds.
- Serif fonts, script fonts, emoji.
- Stock photos of smiling mechanics.
- Red body text or red backgrounds behind long text.
