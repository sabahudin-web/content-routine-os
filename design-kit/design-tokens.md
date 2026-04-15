# Design Tokens

**Last updated:** [Fill in during /onboard]

> Run `/onboard` — Claude will help you set up your brand colors, fonts, and visual identity. This file will be filled in during the Design System phase.

The single source of truth for every color, font, size, and CSS variable in your brand. Every visual skill reads this file before generating output.

---

## Google Fonts Import

Once you choose your fonts during `/onboard`, paste the import here:

```html
<!-- Replace with your chosen fonts from fonts.google.com -->
<link href="https://fonts.googleapis.com/css2?family=[YOUR_HEADLINE_FONT]&family=[YOUR_BODY_FONT]&display=swap" rel="stylesheet">
```

Local font files (if you have them):
- `design-kit/assets/typography and fonts/[headline-font]/[filename].ttf`
- `design-kit/assets/typography and fonts/[body-font]/[filename].ttf`

---

## CSS Root Block

Fill these in during `/onboard`:

```css
:root {
  /* === TYPOGRAPHY === */
  --font-display: '[YOUR_HEADLINE_FONT]', serif;
  --font-body: '[YOUR_BODY_FONT]', sans-serif;

  /* === BRAND COLORS === */
  --color-primary:     [YOUR_PRIMARY_COLOR];       /* Main brand color — buttons, titles, key shapes */
  --color-primary-bg:  [YOUR_PRIMARY_LIGHT];       /* Light version of primary — fills, backgrounds */
  --color-accent:      [YOUR_ACCENT_COLOR];        /* ONE emphasis color — use sparingly */
  --color-accent-bg:   [YOUR_ACCENT_LIGHT];        /* Light version of accent — fills */
  --color-text:        [YOUR_TEXT_COLOR];          /* All body text */
  --color-canvas:      [YOUR_BACKGROUND];          /* Page/canvas background */

  /* === FONT SIZES === */
  --text-xl:     [size];    /* Hero headlines */
  --text-lg:     [size];    /* Section titles */
  --text-md:     [size];    /* Sub-headers */
  --text-sm:     [size];    /* Body text */
  --text-xs:     [size];    /* Labels, captions */
}
```

---

## Color Palette

| Role | Hex | Use |
|------|-----|-----|
| Primary | `[YOUR_PRIMARY]` | Titles, main shapes, borders on key elements |
| Primary light | `[YOUR_PRIMARY_LIGHT]` | Fills, card backgrounds |
| Accent | `[YOUR_ACCENT]` | ONE focal point per visual — use max once |
| Accent light | `[YOUR_ACCENT_LIGHT]` | Accent fills |
| Text | `[YOUR_TEXT]` | All readable text |
| Canvas | `[YOUR_CANVAS]` | Background |

---

## Typography

| Role | Font | Size |
|------|------|------|
| Display / Hero | [Headline font] | [size] |
| H1 / Section title | [Headline font] | [size] |
| H2 / Sub-header | [Body font] | [size] |
| Body | [Body font] | [size] |
| Label / Caption | [Body font] | [size] |

---

## Visual Modes

**Light mode:** White/cream background, dark text, primary color accents
**Dark mode:** Dark background, light text, accent pops

*Decide your default mode during /onboard. Note it here:*

**Your default mode:** [light / dark]

---

## Grain Texture

A PNG grain texture overlay adds texture to your visuals:
- File: `design-kit/assets/textures/grain-texture.png`
- Usage: `mix-blend-mode: overlay` at `0.12–0.18` opacity
- Works in both light and dark mode
