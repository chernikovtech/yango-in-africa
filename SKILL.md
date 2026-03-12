---
name: yango-web-style
description: >
  Produce HTML/CSS/JS websites that exactly match the tech.yango.com visual identity. Use this
  skill whenever the user asks to build a web page, landing page, microsite, pitch site, demo,
  dashboard, or any browser-rendered deliverable that should look like Yango Tech. Triggers on
  phrases like "Yango style", "match tech.yango.com", "Yango website", "Yango landing page",
  "pitch site", "demo site", "microsite", or any request for a web page where the user expects
  Yango Tech branding. Also use when restyling an existing page to Yango Tech look-and-feel.
  Covers single-page landing pages, multi-page sites, interactive demos/dashboards, and pitch
  microsites. Includes complete CSS boilerplate, font declarations, component patterns, logo URLs,
  and an HTML skeleton template.
---

# Yango Tech Web Style Skill

**Read this file completely before writing any HTML, CSS, or JS for a Yango-branded web page.**

This skill replicates the exact design system used on [tech.yango.com](https://tech.yango.com/).
Every rule below was extracted directly from the production site source code.

## Quick-Start

1. Read `references/boilerplate.css` — copy-paste the entire file into your `<style>` block or link it as an external stylesheet. It contains all font-face declarations, CSS variables, resets, and base styles.
2. Read `references/template.html` — use it as the skeleton for every new page.
3. Read `references/components.md` — for nav, hero, cards, CTAs, footer, and form patterns.

---

## Design Principles

The Yango Tech aesthetic is defined by:

- **Monochrome + one red accent.** Almost everything is black, white, and grey. `#FF1A1A` red is used sparingly for CTAs and interactive highlights only.
- **All-caps typography with wide letter-spacing** on body text. Headlines use the proprietary `Yango Headline` display font at weight 900 with extremely tight line-height (85-90%).
- **Generous rounded corners** — cards at `1.875rem`, pills at `2rem`, dropdowns at `2.5rem`. Nothing is sharp-cornered.
- **Dark hero, light body.** Hero sections are always near-black (`#141414` / `#000`) with white text. The rest of the page uses `#F5F5F5` body background.
- **Subtle motion.** Image hovers scale 1.1x over 1.2s. Transitions are `ease-in-out`. No bouncy or spring animations.
- **No shadows, no gradients on surfaces.** Cards rely on background color contrast (white card on `#F5F5F5` body) rather than box-shadow or gradients.

---

## Fonts

Two font families, both hosted on `yastatic.net`:

### Yango Headline (display font)
- **Weight**: 900 only (normal + italic)
- **Usage**: Hero text, section headings (H1, H2, H3)
- **CSS**: `font-family: "Yango Headline", Helvetica, Arial, sans-serif`
- **Always pair with**: `letter-spacing: calc(1em / 50); line-height: 85%` (hero) or `line-height: 90%` (section heads)

### Yango Group Text (body/UI font)
- **Weights**: 100 (Thin), 300 (Light), 400 (Regular), 500 (Medium), 600 (Bold), 900 (Black)
- **Usage**: All body text, labels, navigation, buttons, form inputs
- **CSS**: `font-family: "Yango Group Text", "YS Text", Helvetica, Arial, sans-serif`
- **Body text always uses**: `text-transform: uppercase; letter-spacing: 0.2em; font-weight: 400`
- **Labels/small text**: `font-size: 0.75rem; font-weight: 500`

All `@font-face` declarations with exact URLs are in `references/boilerplate.css`.

---

## Color Palette

| Token               | Value                    | Usage                              |
|----------------------|--------------------------|------------------------------------|
| `--primary-color`    | `#FF1A1A`                | CTAs, selection highlight, accents |
| `--body-color`       | `#F5F5F5`                | Page background                    |
| `--text-primary`     | `#141414`                | Primary text on light bg           |
| `--surface-dark`     | `#232323`                | Dark nav, dark card backgrounds    |
| `--surface-mid`      | `#323232`                | Map markers, tooltips, secondary   |
| `--text-secondary`   | `#7A7A7A`                | Muted/secondary text               |
| `--input-bg`         | `rgb(226, 226, 226)`     | Form input backgrounds             |
| `--border-color`     | `rgba(196, 196, 196, 1)` | Dividers, borders                  |
| `--dropdown-bg`      | `rgb(245, 245, 245)`     | Dropdown/flyout backgrounds        |
| `--text-on-dark`     | `#F5F5F5`                | White text on dark surfaces        |

**Selection highlight**: `::selection { background: var(--primary-color); color: white; }`

---

## Typography Scale

| Element        | Font Family      | Size              | Weight | Line-Height | Letter-Spacing      |
|----------------|------------------|-------------------|--------|-------------|---------------------|
| Hero / H1      | Yango Headline   | `4rem` – `6.25rem`| 900    | 85%         | `calc(1em / 50)`    |
| H2             | Yango Headline   | `2.5rem` – `3.85rem`| 900  | 90%         | `calc(1em / 50)`    |
| H3             | Yango Headline   | `2rem` – `3rem`   | 900    | 90%         | `calc(1em / 50)`    |
| Body           | Yango Group Text | `1rem`            | 400    | 1.4         | `0.2em`             |
| Small / Label  | Yango Group Text | `0.75rem`         | 500    | 1.2         | `0.2em`             |
| Nav item       | Yango Group Text | `0.75rem`         | 500    | 1           | `0.2em`             |

**All body-level text** MUST be `text-transform: uppercase`.
Headlines can be mixed-case or uppercase depending on context.

---

## Layout

- **Max content width**: `116rem` (1856px)
- **Horizontal padding**: `1.87rem` (desktop ≥1440px), `1.25rem` (tablet/mobile <1440px)
- **Content centering**: Use the `.yt-container` utility (defined in boilerplate)
- **Grid**: Use CSS Grid or Flexbox — the site uses a 2-column grid system for many sections
- **Section spacing**: Generous — typically `6rem` – `10rem` vertical padding between major sections
- **All elements**: `font-variant-numeric: proportional-nums`

---

## Border Radii Reference

| Element              | Radius     |
|----------------------|------------|
| Cards                | `1.875rem` |
| Tag pills            | `2rem`     |
| Dropdown/flyout      | `2.5rem`   |
| Form inputs          | `1.25rem`  |
| Social icons         | `1rem`     |
| Tooltips             | `1.5rem`   |
| Small markers        | `0.2rem`   |
| CTA buttons (pill)   | `2rem`     |

---

## Logo

**Yango Tech logo (dark, for light backgrounds)**:
```
https://avatars.mds.yandex.net/get-lpc/14837328/21641dca-3288-4eeb-8d99-81f8cb31a763/orig
```
- Dimensions: 176 × 30
- On dark backgrounds: apply `filter: invert(1)` to make it white

---

## Theme Rules

**Always follow this page structure:**

1. **Hero section** — dark background (`#000` or `#141414`), white text, optional video/animation bg
2. **Body sections** — `#F5F5F5` background, dark text
3. **Optional dark sections** — can intersperse dark-bg sections within the body for variety (e.g., map, testimonials)
4. **Footer** — dark background

Never use gradient backgrounds on surfaces. Never use box-shadow on cards (use background color contrast instead).

---

## DO / DON'T Checklist

### DO ✓
- Use Yango Headline for ALL headings (H1–H3)
- Use Yango Group Text for ALL other text
- Apply `text-transform: uppercase` and `letter-spacing: 0.2em` to body text
- Use `#FF1A1A` only for CTAs and interactive accents
- Use generous border-radius (1.25rem minimum on cards and inputs)
- Use `backdrop-filter: blur(5px)` for overlaid tag pills on images
- Provide hover states: images scale, buttons change color, links fade
- Use `transition: 0.2s ease-in-out` for most interactions, `1.2s ease-in-out` for image scale
- Keep sections spaced with generous vertical padding (6rem+)
- Start every page from `references/template.html`

### DON'T ✗
- Use system fonts (Arial, Helvetica, Inter, Roboto) as primary
- Use emoji as icons — use clean SVG icons or text-only design
- Use gradient backgrounds on cards or sections
- Use box-shadow on cards
- Use bright/saturated colors besides `#FF1A1A` red
- Use small border-radius (4px, 8px) — everything is generously rounded
- Use lowercase body text — it must always be uppercase
- Use tight letter-spacing on body text — it must be `0.2em`
- Mix fonts — only Yango Headline and Yango Group Text, nothing else
- Use decorative borders or outlines on cards — cards are flat with background color

---

## File Reference

| File                         | What it contains                                          | When to read it            |
|------------------------------|-----------------------------------------------------------|----------------------------|
| `references/boilerplate.css` | All @font-face, CSS variables, reset, base styles         | Always — copy into project |
| `references/template.html`   | Complete HTML skeleton with nav, hero, body, footer        | Always — start pages here  |
| `references/components.md`   | Detailed component patterns: nav, cards, CTAs, forms, etc. | When building specific UI  |
