---
name: acquisition-repurpose-linkedin-infographic
description: >
  Create a professional LinkedIn infographic using Nano Banana MCP image generation
  with the Unstuck brand system. Use this skill when the user says "create a LinkedIn
  infographic", "make a visual for this post", "build an infographic", "infographic for
  LinkedIn", "visual guide", "visual cheat sheet", "make this into an image", or provides
  content (post, transcript, topic) and wants a shareable visual. Also trigger when the
  /content routine reaches Step 10c (Infographic type). Works standalone — user can paste
  any content and get a polished branded PNG without running the full content routine.
---

# LinkedIn Infographic Generator (Nano Banana)

Generate polished, branded LinkedIn infographics using Nano Banana MCP image generation.

**Format:** Always 4:5 portrait ratio. This maximizes feed real estate on LinkedIn.
**Output:** Nano Banana generates the PNG directly — no HTML intermediate step needed.
**Brand:** Your Unstuck design system — read `design-kit/design-tokens.md` and `design-kit/brand-identity.md` before building.

---

## Routine Mode vs Standalone Mode

**How to detect:** If this skill was invoked by a routine command (`/content` Step 10c), it is in **routine mode**. If the user called it directly ("create a LinkedIn infographic"), it is in **standalone mode**.

**Routine mode (autonomous):** Skip all interactive checkpoints. Auto-decide the output mode (Phase 2), auto-pick the strongest concept (Phase 3), auto-pick the best visualization approach (Phase 4), skip prompt confirmation (Phase 5), generate immediately, and skip the review loop (Phase 7) — present the result and move on. The routine already asked the user which post types they want, so no further confirmation is needed.

**Standalone mode (interactive):** Run all phases with user input as described below — concept selection, visualization approach, prompt review, and iterate loop.

---

## Phase 1: Content Intake

1. Read `context/business-profile.md` and `context/content-pillars.md` for brand context.
2. Read `design-kit/design-tokens.md` and `design-kit/brand-identity.md` for visual specs.

If content is not already in context, ask:

> "Paste the content to turn into an infographic — LinkedIn post, transcript, topic, or idea."

Acknowledge receipt briefly and move to Phase 2 silently.

---

## Phase 2: Analysis + Mode Decision

3. Read `references/visualization-patterns.md` now.

### 2.1: Four-Layer Analysis (silent)

Extract meaning at all four layers:
- **Layer 1 (Narrative):** What happened? (story, event, experience)
- **Layer 2 (Themes):** What is it about? (concepts, ideas)
- **Layer 3 (Claims):** What does it say is TRUE? (opinions, beliefs, assertions)
- **Layer 4 (Information):** What concrete data, frameworks, or comparisons exist?

### 2.2: Auto-Decide Output Mode

| Layer Strengths | Decision |
|---|---|
| Layer 3 strongest | Editorial Illustration |
| Layer 4 strongest | Information Graphic |
| Both strong | Hybrid (data-led by default) |
| Both weak | Ask the user what to emphasize |

State the decision briefly: "This reads as a strong information graphic — I'll use a structured layout."

### 2.3: Type Confirmation (optional override)

If auto-decision is clear, state it and proceed. Only ask if content is ambiguous:

Options: Infographic / Editorial illustration / Risograph analog / Minimalist conceptual

---

## Phase 3: Concept Selection

4. Extract 5+ visualizable concepts — always from BOTH Layer 3 and Layer 4. Label each:

- Layer 4 concepts -> "Information Graphic: [what it shows]"
- Layer 3 concepts -> "Editorial: [what it expresses]"

Present all 5+ and let the user pick. Sort by the locked mode first (Layer 4 first for info graphics, Layer 3 first for editorial).

If the user picks a concept from the other layer, silently switch mode and note it.

---

## Phase 4: Visualization Approach

5. Propose 5 ways to visualize the chosen concept, matching the locked mode.

**For Information Graphic:** Propose data structures only — Card Grid, Vertical Flow, Comparison, Hierarchy, Funnel, Single Hero, Stat Row, Numbered Steps, Tangled vs Straight, U-Curve. Describe what data goes where and what the viewer learns in 1 second. See `references/visualization-patterns.md` for full archetypes.

**For Editorial Illustration:** Propose cinematic scenes — physical spaces, objects, spatial relationships, emotional register. NOT layout types.

6. After the user picks, do the following silently before building:
   1. Map the exact content to the chosen structure (what text goes where)
   2. Run the 2-second test: "A scrolling person sees this for 2 seconds — what do they get?"
   3. If the answer is vague, go back and pick a stronger approach

---

## Phase 5: Build the Prompt

7. Read `references/infographic-prompt.md` now.

Construct the Nano Banana prompt using the template from `references/infographic-prompt.md`. The prompt must include:

1. **Scene description** — what the infographic shows, the specific layout archetype, what data goes where
2. **Style block** — bold street-poster meets editorial, NOT corporate clean
3. **Typography block** — heavy slab serif headlines (Alfa Slab One style) + handwritten body (Schoolbell style)
4. **Color palette block** — the exact 6 Unstuck colors with hex values, emphasizing orange discipline (ONE accent only)
5. **Texture block** — film grain on all backgrounds
6. **Composition block** — header bar, body layout, mandatory footer strip
7. **Footer block** — thin charcoal black strip, text only: "[Your Name] Murtic" left, "Unstuck" right, max 5% height. No photos, no logos, no content-specific elements.

Show the full prompt to the user before generating. Ask: "Ready to generate?"

---

## Phase 6: Generate with Nano Banana

8. Call `mcp__nano-banana__generate_image` with these parameters:

```
prompt: [the full prompt from Phase 5]
aspect_ratio: "4:5"
model_tier: "nb2"
resolution: "high"
negative_prompt: "No gradients within shapes. No blue, green, teal, cyan, or colors outside the 6-color palette. No thin modern sans-serif fonts (no Inter, Roboto, Arial, Montserrat, Poppins). No corporate clean aesthetic. No stock photography. No emojis as design elements. No 3D renders or glossy surfaces. No pure white backgrounds without texture. No generic AI infographic look."
system_instruction: "You are creating a branded LinkedIn infographic for youahudin Murtic's 'Unstuck' brand. The style is bold street-poster meets editorial — heavy slab serif headlines, handwritten body text, film grain texture, deep purple signature color with one orange accent pop. Dense with content, textured, commanding. Never corporate or minimal."
output_path: "inbox/outputs/images/YYYY-MM-DD-acquisition-repurpose-linkedin-infographic.png"
enable_grounding: false
```

Replace `YYYY-MM-DD` with today's date.

9. Show the generated image to the user.

---

## Phase 7: Review + Iterate

10. Ask: "How is this?"

Options:
- **Done** — save as final, wrap up
- **Tweak it** — describe what to change in free text. Adjust the prompt and regenerate. Increment version: append `-v2`, `-v3` to filename
- **Different approach** — go back to Phase 4 with the same concept
- **Different concept** — go back to Phase 3 with the cached concept list

11. Before pushing to Notion, run the Creator Voice Test on the caption text (not the image itself):

**Creator Voice Test (self-audit — answer before saving):**

1. Does the caption sound like you or a polished LinkedIn guru?
2. Is there a real experience or opinion here — not generic advice?
3. Is there a belief that's actually his (not what the internet says)?
4. Would his past self find this genuinely useful?
5. Is it fog-free — no buzzwords, no empty promises, nothing vague?

If any answer is "no", revise the caption before proceeding.

12. When user confirms Done, push to Notion:

   1. Call `mcp__claude_ai_Notion__notion-search` with query "LinkedIn Content Dashboard" to find the database ID.
   2. Call `mcp__claude_ai_Notion__notion-create-pages` to create the record:
      - **Post title:** Headline/title of the infographic — keep under 100 characters
      - **Notes:** Topic context — use the Trigify research summary if available in this session; otherwise write a 1-sentence description of what the infographic shows
      - **Post status:** "Draft"
      - **Content pillar:** Match the closest pillar from `context/content-pillars.md` — if no clear match, skip this field
      - **Draft:** The concept description — visualization approach chosen + what the viewer learns in 2 seconds
      - **Post format:** "Infographic"
   3. Confirm: "Pushed to LinkedIn Content Dashboard."

---

## Rules

1. Always 4:5 portrait — never change the aspect ratio
2. Footer on every infographic — thin dark strip, text only: "[Your Name] Murtic" left, "Unstuck" right. No photos, no logos. Max 5% of total height.
3. Footer is ALWAYS the same — never put content-specific elements (numbers, stats, conclusions) in the footer. Those belong in the main content area above.
4. One key message per infographic — if content covers three things, pick one
5. Information Graphics: propose DATA STRUCTURES only, never metaphorical scenes
6. Editorial Illustrations: propose SCENES, never layout types
7. Dense over empty — fill space with real content, not decorative whitespace
8. 2-second test before building — if you can't state what someone gets in 2 seconds, rethink
9. No emojis, no colors outside the 6-color Unstuck palette
10. Orange discipline — ONE orange accent element per infographic, maximum
11. Always show the prompt to the user before generating — no surprise generations
12. Use the Unstuck brand system from `design-kit/` — never fall back to generic styles

---

## Edge Cases

| Situation | Action |
|---|---|
| No content provided | Ask for it before proceeding |
| Nano Banana MCP unavailable | Tell user the image generation service is down, try again later |
| Footer looks too big | Re-emphasize "MINIMAL — no more than 5% of total height" and "small text" in the prompt |
| Generated image doesn't match brand | Adjust prompt — add more specific color hex values, re-emphasize font descriptions, and regenerate |
| Both layers are weak | Ask: "What's the one thing you want someone to walk away knowing?" |
| User wants dark background | Fine — charcoal black (#2C262E) is a brand color. Use it with white text and grain texture. |
| User wants colors outside palette | Explain only 6 Unstuck colors exist. Offer lavender or peach as alternatives for "softer" requests. |
| Generated text in image is wrong | AI image generation can produce imperfect text. If text accuracy is critical, note this limitation and suggest an HTML approach instead. |
