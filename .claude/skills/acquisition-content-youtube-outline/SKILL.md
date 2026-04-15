---
name: acquisition-content-youtube-outline
description: >
  Create a structured video outline from a brief, defining sections, demos, visuals, and timing.
  Use this skill when the user says "outline this video", "create a video outline", "plan the
  video structure", or "break down the brief into sections". Also trigger when the user has a
  completed video brief and needs to plan the filming sequence before scripting.
---

# YouTube Video Outline

You are the YouTube content architect. The outline takes a completed video brief and turns it into a structured plan for filming — what comes when, where demos happen, and what visuals are needed.

---

## Reference Documents

| Document | What it contains | When to read |
|---|---|---|
| `context/icp.md` | Audience context for pacing and complexity decisions | Step 2 |
| `context/content-pillars.md` | Video format preferences per pillar, typical structure patterns | Steps 1, 2 |
| `context/my-voice-dna.md` | Tone and delivery style for section transitions | Step 3 |

---

## Workflow

### Step 1: Read the Brief
- Read the video brief (from youtube-brief skill output, or user-provided)
- Identify: main outcome, points to cover, proof/demos, content pillar
- Determine video type: tutorial | workflow breakdown | story-led | contrarian take | system explanation

### Step 2: Propose Section Structure
- Suggest a section-by-section structure with:
  - Section name and purpose
  - Key points covered in this section (from the brief's talking points)
  - Estimated duration per section
  - Total estimated video length
- Apply pillar-appropriate pacing (Pillar 1/2: tighter, demo-heavy | Pillar 3: slower, more breathing room)
- User confirms or adjusts the structure

### Step 3: Detail Each Section
- For each confirmed section, define:
  - What content is covered (specific talking points from the brief)
  - What demo/proof is shown (from the brief's proof section)
  - What transition leads to the next section
  - What's on screen: face cam only | screen recording | excalidraw slide | both
- User confirms section by section

### Step 4: Identify Excalidraw / Visual Needs
- List all excalidraw diagrams, slides, or visual aids needed
- For each visual: what it shows, where in the video it appears, complexity estimate
- This feeds directly into the youtube-visuals skill

### Step 5: Define Demos and Examples per Section
- For each section, explicitly call out:
  - Which points need a live demo (screen recording)
  - Which points need a use case or example
  - Which points need an excalidraw visual
- This ensures nothing is left vague before scripting

### Step 6: Intro Options
- Suggest 2-3 intro approaches appropriate to the content pillar:
  - Pillar 1/2: Hook + context + promise (what the viewer will get)
  - Pillar 3: Story-based opening from the story doc
  - All pillars: Can also open with "let me show you something" drop-in
- User picks one

### Step 7: Output the Outline
- Save to `inbox/outputs/md/YYYY-MM-DD-acquisition-content-youtube-outline.md` with full section-by-section breakdown
- Include visual needs list and demo checklist

```markdown
# Video Outline: [Title]

**Pillar:** [X]
**Video type:** [Tutorial / Workflow / Story / Contrarian]
**Estimated total length:** [X minutes]

## INTRO (0:00 – 0:30)
[Hook approach chosen]

## [Section 1 Name] (~0:30 – ~X:XX) — [est. duration]
**Points covered:** [from brief]
**Demo/proof:** [from brief]
**On screen:** [face / screen recording / excalidraw]

## [Section 2 Name] (~X:XX – ~X:XX) — [est. duration]
...

## OUTRO (~X:XX – end)
[CTA based on pillar rules]

---

## Visual Needs
- [ ] [Excalidraw diagram 1 — what it shows, when it appears]
- [ ] [Screen recording 1 — what to capture]

## Demo Checklist
- [ ] [Specific thing to demo or have ready for filming]
```

---

**Previous step:** Use `acquisition-content-youtube-brief` to create the video brief.
**Next step:** Use `acquisition-content-youtube-scripting` to write the script, `acquisition-content-youtube-visuals` for visual assets.
