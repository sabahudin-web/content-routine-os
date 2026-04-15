---
name: acquisition-content-newsletter-thumbnail
description: >
  Generate a detailed image generation prompt for a newsletter thumbnail in 16:9 aspect ratio —
  torn-paper collage illustration style. Analyzes the newsletter edition, identifies a visual
  metaphor, chooses light or dark color mode, and outputs a ready-to-use prompt. Pure illustration,
  no text on the image.

  Use this skill when the user says "make a thumbnail for my newsletter", "I need a newsletter
  image", "generate a thumbnail prompt", "newsletter cover image", "Nano Banana prompt for the
  thumbnail", or wants a 16:9 branded image to accompany a Substack or email send. Also triggers
  automatically as part of the newsletter-repurpose pipeline.
---

# Newsletter Thumbnail Prompt Generator

Read the newsletter edition, identify a visual metaphor, choose a color mode, and output one
complete torn-paper collage illustration prompt — ready to paste into Nano Banana or any AI image tool.

**Style:** Monochromatic torn-paper collage. No text on the image. Consistent visual language
across all editions — only the subject changes.

**Brand override:** Dark mode is permitted for newsletter thumbnails, even though Brand-Guidelines.md
says "light mode only." you explicitly authorized this.

---

## Step 1 — Get the Newsletter

If newsletter text is already in session (running inside a pipeline) — use it directly, skip to Step 2.

If running standalone and no newsletter text has been provided, ask:

> "Paste in the newsletter edition you want a thumbnail for."

---

## Step 2 — Analyze & Identify Visual Metaphor

Read the newsletter and extract:

1. **Core topic** — what is this edition fundamentally about? (1 sentence)
2. **Main takeaway** — what does the reader walk away with? (1 sentence)
3. **Emotional undercurrent** — what feeling does this edition carry? (e.g., tension, relief, discovery, transformation, confrontation, clarity, empowerment)

Brainstorm 2-3 visual metaphors that could represent the topic symbolically. These should be:
- Understandable without text — the image alone communicates the concept
- Concrete enough to render as a torn-paper collage (objects, scenes, abstract compositions)
- Not literal illustrations of the topic (e.g., for an article about email automation, don't show an envelope — show a clockwork mechanism or a river splitting into tributaries)

Pick the strongest metaphor — the one that is most immediately recognizable and works best as a layered torn-paper composition.

---

## Step 3 — Choose Light or Dark Mode

Pick one color mode based on the edition's mood. This is a creative judgment call — do not ask the user.

### Light Mode
- **Background paper:** `#E0D6FF` (soft lavender paper texture)
- **Primary torn layers:** `#463187` (deep purple paper)
- **Supporting fragments:** `#FFFFFF` (white paper pieces for contrast and depth)
- **Accent element:** `#FF6719` (orange — one torn strip or revealed detail only)
- **Base imagery tones:** Monochromatic grayscale with purple tinting

**Use for:** Growth, clarity, optimism, simplicity, fresh starts, lightness, opportunity

### Dark Mode
- **Background paper:** `#463187` (deep purple paper texture)
- **Primary torn layers:** `#FFFFFF` (white paper) and `#E0D6FF` (lavender paper)
- **Accent element:** `#FF6719` (orange — one torn strip or revealed detail only)
- **Base imagery tones:** Monochromatic grayscale with cool or neutral tinting

**Use for:** Depth, intensity, transformation, confrontation, drama, weight, seriousness

Note in the output which mode was chosen and why (1 sentence).

---

## Step 4 — Generate the Prompt

The prompt must be detailed enough that Nano Banana (or any image tool) can produce the exact
image without guessing. Every visual element needs: what it looks like, where it sits, what color
it is, and how it relates to the torn-paper layers. Think of it as writing instructions for a
collage artist who cannot ask questions.

```
ROLE: You are the visual art director for the newsletter "Unstuck." Generate one conceptual editorial illustration using a monochromatic torn-paper collage aesthetic.

ARTICLE CONTEXT:
- Core topic: [1 sentence]
- Main takeaway: [1 sentence]
- Visual metaphor: [the chosen metaphor — describe what the viewer sees]

---

IMAGE SPEC:
- Size: 1456 x 1048 pixels (16:9 landscape)
- Orientation: Landscape
- No text. No letters. No numbers. No logos. No UI elements. No diagrams.

---

STYLE — TORN-PAPER COLLAGE (apply to every element):
- Layered torn paper strips and shapes revealing portions of monochromatic imagery
- Horizontal and diagonal ripped paper strips — some wide, some narrow
- Visible paper fibers and rough torn edges on every paper piece
- Physical analog collage texture — the image should look like a photographed handmade collage
- Paper grain texture visible on all surfaces
- Slight physical shadows where paper layers overlap (natural stacking shadow, not digital drop shadow)
- Irregularly torn edges — never clean-cut, never geometric
- Fine-art editorial aesthetic — calm, thoughtful, slightly intellectual mood
- Subtle surreal or symbolic composition

---

COLOR MODE: [Light / Dark]

PALETTE:
[If Light Mode:]
- Background: textured paper in #E0D6FF (soft lavender) — visible paper grain
- Primary torn layers: paper in #463187 (deep purple) — these carry the main subject imagery
- Supporting fragments: #FFFFFF (white paper pieces) — add contrast and layering depth
- Accent: #FF6719 (warm orange) — appears as exactly ONE torn strip, revealed shape, or edge highlight
- Base imagery: monochromatic grayscale with subtle purple tinting
- Allow multiple grayscale tones within torn openings for depth

[If Dark Mode:]
- Background: textured paper in #463187 (deep purple) — visible paper grain
- Primary torn layers: paper in #FFFFFF (white) and #E0D6FF (soft lavender) — these carry the main subject imagery
- Accent: #FF6719 (warm orange) — appears as exactly ONE torn strip, revealed shape, or edge highlight
- Base imagery: monochromatic grayscale with cool or neutral tinting
- Allow multiple grayscale tones within torn openings for depth

COLOR RULES:
- No colors outside the palette above — zero exceptions
- The base imagery revealed through torn openings stays monochromatic grayscale
- Orange (#FF6719) appears as a moderate accent — one element, not splashed everywhere
- The palette should feel coherent and restrained

---

VISUAL SUBJECT:
[Describe the chosen metaphor rendered as a torn-paper collage. Be specific:
- What objects or forms appear in the monochromatic imagery revealed through the torn paper?
- How are the torn paper layers arranged to reveal the subject?
- What is partially hidden and what is fully visible?
- Which element gets the orange accent and how does it appear?
- How does the layering create depth and visual interest?

Write 3-5 sentences. Be concrete — name shapes, positions, and relationships between elements.]

---

COMPOSITION:
- Landscape editorial header layout
- Multiple horizontal and diagonal torn strips revealing parts of the underlying image
- Layered collage structure — at least 3-4 visible paper depth layers
- Clear central conceptual subject — slightly off-center for dynamic balance
- Generous negative space — the composition should breathe
- Asymmetric balance — avoid perfect symmetry
- Focal point sits in the visual "power zone" (slightly left or right of center, slightly above middle)

---

CONSTRAINTS:
- No text, no letters, no numbers, no labels, no watermarks — absolutely zero typography
- No digital effects, no gradients, no glow, no lens flare
- No clean-cut edges — all paper pieces have organic, irregular torn edges
- No photographic realism — this is a collage of paper, not a photograph
- Orange appears in exactly one element — not scattered
- The collage must feel handmade and tactile, not digitally composited
- Maintain enough negative space for the image to breathe (30%+ of canvas)
```

---

## Step 5 — Decide Which Reference Images to Pass

Before calling Nano Banana, decide which of the 3 assets to include:

**Always pass:**
- `assets/thumbnail-example.png` — style and composition reference (always pass as input_image_path_1)
- `assets/logo.png` — Unstuck logo for bottom-right corner (always pass as input_image_path_2)

**Only pass if the newsletter explicitly mentions "Claude" or "Claude Code":**
- `assets/icon-claude-code.png` — Claude Code pixel robot icon (pass as input_image_path_3 only when relevant)

If the newsletter topic is not about Claude or Claude Code — skip icon-claude-code.png entirely and only pass 2 reference images. Never place a Claude icon on a thumbnail about an unrelated topic.

---

## Step 6 — Generate the Image with Nano Banana

After constructing the full prompt and deciding on reference images, call `mcp__nano-banana__generate_image` immediately — do not wait for user confirmation:

```
mcp__nano-banana__generate_image(
  prompt: [the full prompt constructed in Step 4, including element placement instructions for logo bottom-right and icon upper-center if used],
  aspect_ratio: "16:9",
  model_tier: "nb2",
  negative_prompt: "text, typography, letters, numbers, labels, watermarks, logos, clean cut edges, photographic realism, digital effects, gradients, glow, scattered orange, perfect symmetry",
  input_image_path_1: ".claude/skills/acquisition-content-newsletter-thumbnail/assets/thumbnail-example.png",
  input_image_path_2: ".claude/skills/acquisition-content-newsletter-thumbnail/assets/logo.png",
  input_image_path_3: ".claude/skills/acquisition-content-newsletter-thumbnail/assets/icon-claude-code.png",  [only if Claude/Claude Code mentioned]
  output_path: "inbox/outputs/images/YYYY-MM-DD-acquisition-content-newsletter-thumbnail.png"
)
```

Always include in the prompt:
- "The Unstuck logo (reference image 2) placed in the bottom-right corner, small badge size"
- If Claude icon used: "The Claude Code pixel robot icon (reference image 3) floats upper-center above the main subject — same position and scale as in the reference thumbnail"

If the call returns a 503 (model overloaded), retry once. If it fails a second time, output the prompt only and tell the user to paste it into Nano Banana manually.

---

## Step 6 — Output & Save

Output the prompt with no explanation before it, followed by the image result:

```
---
**Your Thumbnail Prompt**
**Color Mode:** [Light / Dark] — [1 sentence reason]
**Visual Metaphor:** [the chosen metaphor in 5 words or fewer]
---

[full prompt here]

---
**Image generated:** inbox/outputs/images/[YYYY-MM-DD]-newsletter-thumbnail.png
```

**Save locally** to `inbox/outputs/md/YYYY-MM-DD-acquisition-content-newsletter-thumbnail.md`

**Save to Notion** — update the newsletter record in `Unstuck - Newsletter Database` (`2e07fe00-204d-8026-aba8-000bd2c450af`):
- Call `mcp__claude_ai_Notion__notion-update-page` on the current newsletter edition page (page ID from the repurpose skill's session output)
- Field: `newsletter-thumbnail-prompt` → paste the full prompt text (exact field name — all lowercase with hyphens)
- If no existing page is found in session, note in the local file: "Notion update skipped — no newsletter page ID in session. Paste manually into Unstuck - Newsletter Database → newsletter-thumbnail-prompt column."

---

## Quality Check (Run Before Outputting)

- Does the prompt contain absolutely zero text, typography, letters, or numbers?
- Does it describe torn-paper texture with visible paper fibers and irregular edges?
- Is the visual metaphor clearly connected to the newsletter topic — not generic?
- Does the color palette match the chosen mode exactly — no extra colors?
- Is orange used for exactly ONE element — not sprinkled throughout?
- Does the composition describe specific spatial relationships — not just "balanced layout"?
- Would this image look visually consistent with other editions in the same collage series?
- Is there enough detail for an AI image generator to produce the image without guessing?
- Is the Claude icon only included if the newsletter explicitly mentions Claude or Claude Code?

If any answer is "no" — fix it before outputting.

---

## Edge Cases

| Situation | Action |
|-----------|--------|
| Newsletter text already in session | Use it directly — do not ask |
| No newsletter text provided | Ask once: "Paste the newsletter edition." |
| Edition has no clear single topic | Pick the dominant thread, note it in output |
| Topic is highly abstract (e.g., "mindset shifts") | Lean into symbolic/surreal metaphors |
| Topic is very similar to a previous edition | Vary the metaphor — the collage style stays identical |
| User specifies a mode | Override creative judgment and use what they asked for |
| User asks for both modes | Generate two separate prompts, one per mode |
| Notion page ID not in session | Save locally and note manual paste instruction |
