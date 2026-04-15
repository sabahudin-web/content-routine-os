---
name: acquisition-repurpose-linkedin-carousel
description: >
  Repurpose a YouTube script, topic, or framework into a LinkedIn carousel (document post) with
  slide-by-slide structure and caption. Use this skill when the user says "write a LinkedIn
  carousel", "make a carousel post", "turn this into slides", "LinkedIn document post", or
  "swipe post". Also trigger when the /content routine reaches Step 10 and user picks carousel.
---

# LinkedIn Carousel Post

Write a full LinkedIn carousel — slide structure + caption — using Your Swipe format. Each slide is a standalone insight. First slide stops the scroll. Last slide drives action.

**Engagement range:** 0.9x - 1.4x
**Dial settings:** Emotion 4-6 / Humor 4-6 / Technical 4-7

---

## Step 1: Read Reference Files

Read before writing:
- `context/my-voice-dna.md` — voice rules
- `context/linkedin-content-universe.md` — carousel DNA and the Creator Swipe structure

---

## Step 2: Get Source Content

If not in context, ask:
> "Paste the script, topic, or framework you want to turn into a carousel."

---

## Step 3: Extract the Core Insight

Before building slides, identify:
- **One core promise**: What will the reader learn by the end?
- **Main insight count**: How many distinct insights does the source contain? (Ideal: 5-7 for carousel)
- **Personal story thread**: Is there one story that can run through it (optional but powerful)?
- **Collaboration angle**: Is there a collaborator to tag? (Charlie, Walid, Hristo, etc.)

---

## Step 4: Build the Slide Structure

**The Creator Swipe:**

| Slide | Purpose | Length |
|-------|---------|--------|
| Slide 1 | Hook + Promise — what they'll learn | 1 punchy line + subtitle |
| Slides 2-7 | One insight per slide — standalone, punchy, visual | 1 headline + 2-3 bullet points or 1 short paragraph |
| Slide 8 | Summary or "The truth is..." — the big takeaway | 2-3 sentences max |
| Slide 9 | CTA — follow, link, or question | 1 line |

**Slide writing rules:**
- Each slide must work standalone — if someone screenshots slide 4, it makes sense on its own
- Use "you" directly — speak to the reader, not about them
- Include your opinion, not just facts — "I think...", "In my experience..."
- One self-deprecating or honest line somewhere (builds trust)
- Slide 1 headline = biggest hook, biggest font concept
- No walls of text on any slide — max 40 words per slide

---

## Step 5: Write the Caption

The caption accompanies the carousel post. It's NOT a summary of the slides.

**Caption structure:**
1. Brief context (1-2 lines) — why this carousel exists
2. Why it matters (1-2 lines) — the real-world problem it solves
3. Collaboration credit if applicable — "Built this with [Name]"
4. P.S. — question that invites conversation

**Caption length:** 60-120 words. Short. The carousel is the content.

---

## Step 6: Voice Check

**Non-negotiable rules:**
- No em dashes (—)
- No "Here's what happened"
- No "Most people"
- Conversational, not textbook — sounds like you talking, not a LinkedIn post template
- Include Your opinion somewhere, not just facts
- P.S. at the end of caption, always

**Carousel topics that work best for you:**
- LinkedIn profile mistakes (wrong vs. right)
- DM strategy breakdowns
- AI workflow step-by-steps
- Content templates with examples
- Before/after comparisons (his own journey)

**Creator Voice Test (self-audit — answer before saving):**

Run these yourself. If any answer is "no", revise before proceeding.

1. Does this sound like you or a polished LinkedIn guru?
2. Is there a real experience or opinion here — not generic advice?
3. Is there a belief that's actually his (not what the internet says)?
4. Would his past self find this genuinely useful?
5. Is it fog-free — no buzzwords, no empty promises, nothing vague?

---

## Step 7: Save Output

Save to `inbox/outputs/md/YYYY-MM-DD-acquisition-repurpose-linkedin-carousel.md`

Format the output clearly:

```
## SLIDES

**Slide 1:** [Headline] / [Subtitle]
**Slide 2:** [Headline] / [Content]
...
**Slide 9:** [CTA]

---

## CAPTION

[Full caption text]
```

Include at the top:
```
Post type: Carousel (Type 4)
Slide count: [N]
Pillar: P1 / P2 / P3
Collaboration: [name or none]
Dial: Emotion [X] / Humor [X] / Technical [X]
```

Note: PDF/carousel visual production is manual. This skill outputs the text structure only.
To generate the visual, use the design tool or Canva with Your brand colors:
- Primary purple: #463187
- Orange accent: #FF6719
- Background: white #FFFFFF

---

## Step 8: Push to LinkedIn Content Dashboard

Push to Notion after saving the file:

1. Call `mcp__claude_ai_Notion__notion-search` with query "LinkedIn Content Dashboard" to find the database ID.
2. Call `mcp__claude_ai_Notion__notion-create-pages` to create the record:
   - **Post title:** Headline from Slide 1 — the hook — keep under 100 characters
   - **Notes:** Topic context — use the Trigify research summary if available in this session; otherwise write a 1-sentence description of the post topic
   - **Post status:** "Draft"
   - **Content pillar:** Match the closest pillar from `context/content-pillars.md` — if no clear match, skip this field
   - **Draft:** Full caption text (not the slides — the caption is the post body on LinkedIn)
   - **Post format:** "Carousel"
3. Confirm: "Pushed to LinkedIn Content Dashboard."

---

## Edge Cases

| Situation | Action |
|-----------|--------|
| Source has too many insights (10+) | Pick the 6-7 strongest. Don't try to fit everything. |
| Source has too few insights (under 4) | Ask: "Is there more context you want to add, or should I expand each insight with examples?" |
| Topic is too technical for general LinkedIn | Dial back technical depth (Technical dial: 4-5 max), lead with the problem not the solution |
| Collaboration post | Ask who the collaborator is and their LinkedIn handle before writing — include tag in caption |
