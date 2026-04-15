---
name: acquisition-content-extraction
description: >
  Takes the top ranked ideas from content-ideas and maps each one to the full content calendar
  (YouTube angle, LinkedIn post type, Newsletter story angle, Substack note) before committing to
  production. Use this skill when the user says "extract content ideas", "map ideas to platforms",
  "what can I make from these ideas", or "show me the full content plan". Also triggers automatically
  as Step 1.5 of the /content routine, after content-ideas and before youtube-ideation.
---

# Content Extraction

You are taking the ranked ideas from Step 1 (content-ideas) and mapping each one to Your full content workflow. The goal is to see the complete content calendar potential of each idea — YouTube + LinkedIn + Newsletter — before deciding which one to produce.

This gives a smarter starting point: instead of picking an idea and discovering mid-production that it doesn't repurpose well, you see the full chain upfront.

**This skill is Step 1.5 of the /content routine.** It reads the content-ideas output and feeds a structured extraction into youtube-ideation.

---

## Step 1: Read Context and Source

Read:
- `inbox/outputs/md/YYYY-MM-DD-acquisition-content-ideas.md` — today's ranked ideas from Step 1
- `context/content-pillars.md` — the 3 pillars and their mix
- `.claude/skills/acquisition-content-newsletter-repurpose/references/my-story-doc.md` — Your personal stories (for newsletter angle matching)

Take the top 5 ideas from the content-ideas report (or all ideas if fewer than 5).

---

## Step 2: Extract Each Idea Across Platforms

For each idea, map it to all three output formats. Every angle must feel native to that platform — not copy-pasted from the original idea.

### YouTube Angle
- What is the core video concept? (1 sentence)
- What type of video does it call for? (Tutorial / System breakdown / Story / Contrarian / Comparison)
- What pillar does it serve? (P1 / P2 / P3)
- What hook direction would open the video? (1 sentence — the thing that makes someone not click away in the first 30 seconds)

### LinkedIn Best Fit
- Which of the 6 post types fits best? (Story / Lead Magnet / Infographic / Carousel / Contrarian / Funny)
- Why that type? (1 sentence)
- Opening hook line for the post (1 line — stops the scroll)

### Newsletter Angle
- Which story from `my-story-doc.md` connects most naturally to this idea?
- What is the story angle? (1 sentence — the emotional or thematic bridge between the story and the idea)

### Substack Note
- 1-2 sentence tease that makes someone curious without giving away the lesson

---

## Step 3: Build the Extraction Report

Output a summary section followed by one block per idea.

```
# Content Extraction Report
**Date:** YYYY-MM-DD
**Ideas processed:** [N]
**Source:** inbox/outputs/md/YYYY-MM-DD-acquisition-content-ideas.md

---

## Idea #1 — [Title from content-ideas]

**Score from Step 1:** [X/9] | **Pillar:** P[X]

### YouTube
- **Concept:** [1 sentence]
- **Format:** [Tutorial / Story / Contrarian / etc.]
- **Hook direction:** [1 sentence]

### LinkedIn
- **Post type:** [type]
- **Why:** [1 sentence]
- **Opening hook:** "[line]"

### Newsletter
- **Story match:** [story name from story-doc]
- **Angle:** [1 sentence bridge]

### Substack Note
"[1-2 sentence tease]"

---

[repeat for each idea]
```

End with:

> **Recommended winner:** Idea #[X] — [reason in 1 sentence: best signal + strongest repurpose chain]

---

## Step 4: Save Output

Save to `inbox/outputs/md/YYYY-MM-DD-acquisition-content-extraction.md`

Pass this file's contents forward to `acquisition-content-youtube-ideation` as context. The ideation step uses the YouTube angle from the winning idea as its starting point.

---

## Edge Cases

| Situation | Action |
|-----------|--------|
| content-ideas output not found | Ask: "Paste your ranked content ideas, or run acquisition-content-ideas first." |
| Fewer than 3 ideas in content-ideas | Extract what's available — do not invent ideas to pad the report |
| No story in story-doc connects naturally | Note "no strong story match — newsletter angle TBD" and continue |
| User running this standalone | Same workflow — still reads context files, still saves output |
