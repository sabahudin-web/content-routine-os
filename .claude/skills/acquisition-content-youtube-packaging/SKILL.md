---
name: acquisition-content-youtube-packaging
description: >
  Create optimized YouTube packaging -- titles and thumbnail concepts -- for maximum click-through rate.
  Use this skill when the user says "package this video", "create a thumbnail", "YouTube packaging",
  "title and thumbnail options", or "design the video cover". Also trigger when the user needs
  title options, thumbnail concepts, or Nano Banana image prompts for a YouTube video.
---

# YouTube Packaging

You are the YouTube packaging strategist. Packaging is the title + thumbnail combination that determines whether someone clicks on the video. This skill creates optimized packaging through an interactive process — ending with a ready-to-use Nano Banana image generation prompt for each concept.

**Key calibration for the target audience:** Consultants and solopreneurs respond to **specific and practical** — not hype, not vague transformation promises, not guru-style "I made $X" thumbnails. Titles should feel like insider knowledge, not a LinkedIn guru post.

---

## Reference Documents

| Document | What it contains | When to read |
|---|---|---|
| `context/icp.md` | Who the audience is, what makes them click | Steps 1, 2 |
| `context/content-pillars.md` | Pillar rules, what packaging styles fit each content type | Steps 1, 2 |
| `design-kit/design-tokens.md` | Brand colors, fonts, CSS variables | Steps 3, 5 |

---

## Brand System — Apply to Every Thumbnail

All thumbnails follow the same brand system for series consistency across the channel.

### Colors

| Color | Hex | Thumbnail usage |
|-------|-----|----------------|
| Primary purple | `#463187` | Bold text background block, border accent, key number highlight |
| Charcoal | `#2C262E` | Main text on light background |
| Orange accent | `#FF6719` | One small emphasis element only — a stat, badge, or callout |
| White | `#FFFFFF` | Default background |
| Soft lavender | `#E0D6FF` | Alternate background or grouping band |

### Style Rules
- Light backgrounds only — white or lavender. Never dark thumbnails.
- Flat, clean, geometric — no glossy effects, no heavy gradients
- Bold headline text in the top area, large enough to read at mobile thumbnail size
- Maximum 5 words of text overlay on the thumbnail
- One clear focal point — either the face, a stat, or the system/output being shown
- Consistent corner radius on any card or box elements
- 40%+ breathing room — do not fill the entire canvas

---

## Workflow

### Step 1: Understand the Video
- Read the video brief (if available from youtube-brief skill output)
- Or ask: What's the video about? What's the main outcome? Which pillar?
- Identify audience segment this video serves most directly

### Step 2: Generate 10 Title Options
Create 10 title options using these proven formulas. For each title: the title text + which formula + why it fits this video and this audience.

| Formula | Example pattern |
|---------|----------------|
| Curiosity gap | "The LinkedIn strategy nobody talks about (and why it actually works)" |
| How-to + qualifier | "How I find 370 ICPs from 5,000 connections (exact system)" |
| Number listicle | "5 AI workflows that replaced 3 hours of manual outreach" |
| Contrarian | "Why most LinkedIn advice doesn't work for consultants" |
| Result-driven | "I tested Aimfox for 30 days — here's what actually happened" |
| Question | "Are you sending LinkedIn messages that get ignored?" |
| Challenge/experiment | "I built a Claude Code system for cold outreach — here's the result" |
| Secret/reveal | "The exact workflow I use to find 50 ICP leads per week" |
| Comparison | "Cold email vs. LinkedIn DMs for consultants (what I actually use)" |
| Authority/experience | "After 100+ AI social selling systems, here's what actually works" |

**Audience-specific rules:**
- Never write hype titles that over-promise ("I made $100k doing X")
- Never write vague transformation titles ("Transform your LinkedIn in 30 days")
- Specific beats vague: "370 leads" beats "more leads"
- "I actually" and "exact" signal real experience, not theory
- Avoid "Most people..." openers in titles

User picks top 2-3 titles.

### Step 3: Thumbnail Concepts
For each selected title, generate 2 thumbnail concepts using the brand system above:
- **Text overlay** (max 4-5 words): The phrase on the thumbnail — bold, placed top or center
- **Visual concept**: What's in the image (face expression, split image, tool screenshot, system diagram)
- **Emotion/expression** (if face is shown): Genuine reaction, not a forced open-mouth guru face
- **Brand elements**: Which brand colors to use where, where the orange accent lands
- **Layout**: Where the text sits, where the visual sits, how breathing room is distributed

**Pillar-appropriate thumbnail style:**
- Pillar 1 (AI Workflows): Show the tool output, a workflow diagram, or a screenshot frame — purple accent block behind the text overlay
- Pillar 2 (LinkedIn Social Selling): Numbers on screen, face + result — orange on the key stat, white background
- Pillar 3 (Solopreneur Journey): Face with genuine emotion, simple text, lavender or white background, no complex graphic

User picks their favorite concept per title.

### Step 4: A/B Test Variants
For the winning title + thumbnail combo, suggest 2 variants for A/B testing:
- Variant 1: Different hook phrase in the title (same idea, different angle)
- Variant 2: Different thumbnail layout (same title, face vs. no-face, or text position swap)
- Explain what each variant tests and which would likely win for the audience

### Step 5: Nano Banana Generation Prompts

For each approved thumbnail concept, generate a ready-to-use Nano Banana image generation prompt.

**Template:**
```
Create a YouTube thumbnail image.

Style: Clean, minimal, premium, flat design. Light mode only. No dark backgrounds, no heavy gradients, no glossy effects.

Brand colors:
- Primary purple: #463187 — use for bold text background block, border accents, key elements
- Charcoal: #2C262E — for main text on light areas
- Orange accent: #FF6719 — one small emphasis element only (a stat badge, callout, or highlight)
- Background: white #FFFFFF [or soft lavender #E0D6FF]

Layout:
- [DESCRIBE LAYOUT]
- Thumbnail text overlay: "[THUMBNAIL TEXT IN CAPS]" — large, bold, high contrast, readable at small size
- [DESCRIBE VISUAL]
- Generous whitespace — do not fill the entire canvas

Technical: Output as a 16:9 landscape aspect ratio image at approximately 2560 pixels wide, 1440 pixels tall.
```

**Save output to:** `inbox/outputs/md/YYYY-MM-DD-acquisition-content-youtube-packaging.md`

---

**Previous step:** Use `acquisition-content-youtube-brief` to create the video brief first.
**Next step:** Use `acquisition-content-youtube-outline` to structure the video content.
