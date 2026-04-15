# Nano Banana Infographic Prompt Guide

> Master prompt reference for generating LinkedIn infographics via Nano Banana MCP.
> Every prompt must embed the Unstuck brand identity so the output is recognizably Your.
> For full brand specs, read `design-kit/design-tokens.md` and `design-kit/brand-identity.md`.

---

## Brand DNA (embed in every prompt)

The Unstuck visual identity is **bold, punchy, street-poster meets editorial**. Think wheat-paste poster on a city wall — commanding, textured, unapologetic. NOT corporate. NOT minimal. NOT "clean and professional."

### The Two Fonts

| Role | Font | Character |
|------|------|-----------|
| Headlines, titles, numbers, stats, labels | **Alfa Slab One** | Heavy slab serif. Commanding. Takes up space. Demands attention. |
| Body text, descriptions, annotations, captions | **Schoolbell** | Handwritten. Human. Warm. Makes the heavy headlines approachable. |

The contrast between these two IS the brand personality: heavy authority meets casual approachability.

**Prompt phrasing:** "Bold slab serif headline font (Alfa Slab One style — heavy, chunky, commanding) with handwritten body text (Schoolbell style — casual, warm, slightly imperfect)"

### The 6 Brand Colors (nothing else exists)

| Color | Hex | Role | Prompt phrasing |
|-------|-----|------|-----------------|
| Purple | `#463187` | Signature — titles, structure, borders, backgrounds | "deep purple (#463187)" |
| Black | `#2C262E` | Dark backgrounds, text on light surfaces | "warm charcoal black (#2C262E)" |
| Orange | `#FF6719` | ONE accent pop per section — CTAs, highlights | "vibrant orange (#FF6719)" |
| White | `#FFFFFF` | Text on dark, light backgrounds | "clean white" |
| Lavender | `#E0D6FF` | Soft backgrounds, fills, section breaks | "soft lavender (#E0D6FF)" |
| Peach | `#FFE8DC` | Warm backgrounds, fills | "warm peach (#FFE8DC)" |

**Orange discipline:** Orange is powerful because it's rare. ONE orange element per infographic. If everything is orange, nothing is orange.

**Never invent colors.** No grays, no blues, no greens, no gradients within shapes. Only these 6.

### Grain Texture

Every background gets a subtle film grain / paper texture overlay. This is a brand signature.

**Prompt phrasing:** "subtle film grain texture overlay on all backgrounds, like a vintage risograph print"

### Visual Density

Fill space with meaning. Content-rich, not airy. "40% whitespace" is NOT our rule — use whitespace where it serves communication, not as a default. Aim for 7/10 density.

---

## Prompt Construction Template

Build every Nano Banana prompt using this structure:

```
[SCENE DESCRIPTION]
A professional LinkedIn infographic in 4:5 portrait format.
[Describe what the infographic shows — the concept, the data, the layout]

[STYLE]
Bold, punchy editorial infographic style — like a wheat-paste street poster meets a magazine data visualization. NOT corporate clean. NOT minimal. Textured and commanding.

[TYPOGRAPHY]
Bold heavy slab serif headlines (Alfa Slab One style — chunky, thick, demanding attention).
Handwritten casual body text (Schoolbell style — warm, human, slightly imperfect letterforms).
The contrast between heavy authority headlines and casual handwritten body IS the visual personality.

[COLOR PALETTE — strict, no other colors]
- Deep purple (#463187) — titles, structure, borders, key backgrounds
- Warm charcoal black (#2C262E) — dark backgrounds, body text on light
- Vibrant orange (#FF6719) — ONE single accent highlight (used sparingly)
- Clean white (#FFFFFF) — text on dark surfaces, light backgrounds
- Soft lavender (#E0D6FF) — light fills, section backgrounds
- Warm peach (#FFE8DC) — warm fills, alternating sections

[TEXTURE]
Subtle film grain texture on all backgrounds. Slight paper roughness. Vintage print feel — not digital-smooth.

[COMPOSITION]
- Header bar at top: deep purple or charcoal black background with white title text
- Main body: structured layout with clear visual hierarchy
- Footer bar at bottom: charcoal black (#2C262E) background with small circular profile photo on left, "Sabahudin Murtic" name, and Unstuck logo on right
- Dense with content — fill space with meaning, not decorative emptiness

[NEGATIVE — avoid these]
No gradients within shapes. No blues, greens, teals, or colors outside the palette. No thin sans-serif fonts. No corporate clean aesthetic. No stock photo look. No emojis. No 3D renders. No glossy or shiny surfaces.
```

---

## Footer Block (mandatory on every infographic)

Always include this in the prompt. The footer is ALWAYS the same — never put content-specific elements in it.

```
FOOTER: A very thin, compact strip at the very bottom — warm charcoal black (#2C262E) background. Small text only, no images, no photos, no logos. Left side: "Sabahudin Murtic" in small white handwritten font. Right side: "Unstuck" in small white slab serif. The footer should be MINIMAL — no more than 5% of total height. Just a thin branded strip, not a prominent section.
```

---

## Negative Prompt (always include)

```
No gradients within shapes. No blue, green, teal, cyan, or colors outside the 6-color palette. No thin modern sans-serif fonts (no Inter, Roboto, Arial, Montserrat, Poppins). No corporate clean aesthetic. No stock photography. No emojis as design elements. No 3D renders or glossy surfaces. No pure white backgrounds without texture. No generic AI infographic look.
```

---

## System Instruction (pass to Nano Banana)

```
You are creating a branded LinkedIn infographic for youahudin Murtic's "Unstuck" brand. The style is bold street-poster meets editorial — heavy slab serif headlines, handwritten body text, film grain texture, deep purple signature color with one orange accent pop. Dense with content, textured, commanding. Never corporate or minimal.
```

---

=================================================================
HOW TO CHOOSE YOUR VISUAL METAPHOR
=================================================================

Read the LinkedIn post and ask: "What is the SHAPE of this idea?"

If the insight is about...
- "Hidden work behind visible results" -> ICEBERG
- "Levels of quality/value" -> PYRAMID
- "Complex vs simple approach" -> TANGLED VS STRAIGHT LINE
- "Journey with struggle then success" -> U-CURVE
- "Two groups need to connect" -> HOURGLASS
- "Components of one concept" -> SILHOUETTE WITH BRANCHES
- "Most people vs few people" -> DONUT CHART
- "Old way vs new way" -> SPLIT COMPARISON
- "Overwhelmed by too many inputs" -> CONCENTRIC CIRCLES

The metaphor should feel INEVITABLE — like "of course this idea is an iceberg."

=================================================================
SPECIFIC LAYOUT EXAMPLES
=================================================================

LAYOUT: ICEBERG

    "The Iceberg of [Topic]"
    
              "Results everyone wants"
        +------------------------------+
        |    Leads   Revenue           | <- floating labels in water area
        |  Followers   Growth          |
        +------------------------------+
    ~~~~~~~~ Surface Level ~~~~~~~~~  <- water line with label
        /                            \
       /   Copywriting   Design       \
      /    SEO    Content   Email      \
     /-------- Deeper Level -----------\  <- dashed line
    /                                    \
   /  Strategy  Positioning  Research     \
  /----------------------------------------\
  
  "What most forget" <- annotation with arrow


LAYOUT: PYRAMID WITH LEVELS

    "The 4 Levels of [Topic]"
    
                    ^ The 1% (peak label)
                   / \   "Description of top tier"
     High         /---\
     Impact      /     \  Strategic Level
        ^       /-------\  "Description"
        |      /         \
        |     /-----------\  Basic Level
        |    /             \  "Description"
        v   /---------------\
     Low   /                 \  Commoditized
    Impact -------------------  "Description"
    
           <--- Volume Available --->


LAYOUT: TANGLED VS STRAIGHT

    "[Topic] Fundamentals"
    
    "Make it EASY to [Action]"
    
         +--+                        
        /    \                       
    o--/  X   \----+        o--------------------->
       \      /    |                 
        +----+     |        
                   v        
         "Hard way"              "Easy way"
         (red label)             (green label)


LAYOUT: SPLIT COMPARISON WITH SIMPLE ICONS

    "What [A] Want vs What [B] Want"
    +-------------------------------------------+
    |  [Green header: A]  |  [Blue header: B]   |
    +---------------------+---------------------+
    |                     |                     |
    |  Concept phrase     |  Concept phrase     |
    |  mail -> mail -> ph |  [messy icon web]   |
    |                     |                     |
    +---------------------+---------------------+
    |                     |                     |
    |  Concept phrase     |  Concept phrase     |
    |  pie chart          |  donut chart        |
    |                     |                     |
    +---------------------+---------------------+
    
Icons are ULTRA-SIMPLE: stick figures, basic shapes, simple charts


LAYOUT: SILHOUETTE WITH BRANCHES

    "[Central Concept]"
    
                                    +- [Label 1] -+
                                    |  (subtext)  | <- soft colored pill
        +-----------+               |             |
        |  MAIN     |--------------+
        | CONCEPT   |               +- [Label 2] -+
        |           |--------------  |  (subtext)  |
        +-----------+               |             |
             |                      +- [Label 3] -+
        [stick figure]--------------  |  (subtext)  |
                                    +-------------+
                                    
Each branch pill is a different soft pastel color


LAYOUT: U-CURVE JOURNEY

    "The Link Between [A] and [B]"
    
    +----------------------------------------------+
    |           [ZONE A - soft pink]               |
    |   1.Start      2.Step                        |  <- labels on curve
    |      o--------o                     o        |
    |                 \                 / 6.End     |
    +------------------\---------------/------------+
    |                   \             /             |
    |          3.Step    o-----------o  5.Step      |
    |                        4.Low                 |
    |           [ZONE B - soft green]              |
    +----------------------------------------------+

=================================================================
FINAL CHECK
=================================================================

Before sending the prompt to Nano Banana, verify:

- [ ] 4:5 aspect ratio specified
- [ ] Both font styles described (heavy slab serif + handwritten)
- [ ] Only 6 brand colors referenced (purple, black, orange, white, lavender, peach)
- [ ] Orange used maximum ONCE in the entire infographic
- [ ] Grain/texture mentioned for backgrounds
- [ ] Footer bar described (profile photo + name + logo on dark bar)
- [ ] Negative prompt included
- [ ] System instruction included
- [ ] ONE clear concept — not trying to show three ideas
- [ ] Is there ONE memorable illustrative shape?
- [ ] Does the shape EMBODY the insight (not just decorate)?
- [ ] Is it simple enough to sketch in 2 minutes?
- [ ] Is it interesting enough to screenshot and share?

The goal: Someone sees your visual, instantly gets the concept,
and thinks "that's clever — I'm saving this."
