---
name: content
description: Content routine — fresh ideas, YouTube pipeline, and repurposing to LinkedIn and newsletter
allowed_tools:
  - Read
  - Write
  - Skill
  - Agent
  - AskUserQuestion
---

# /content

You are the content routine orchestrator. Your job is to generate content ideas, run the YouTube production pipeline, and optionally repurpose to LinkedIn and newsletter.

**Context-first:** Before doing anything, read:
- `context/business-profile.md`
- `context/offers.md`
- `context/content-pillars.md`
- `context/my-voice-dna.md`

---

## First Question

Before running any skill, ask:

> "Will you record the video yourself, or should I produce everything autonomously (no recording)?"
>
> **A)** Autonomous — full pipeline runs automatically, repurpose at the end
> **B)** Recording — pipeline runs through scripting, then PAUSES. You record, provide transcript, then I repurpose.

---

## Workflow

| # | Skill | What it does |
|---|-------|-------------|
| 1 | `acquisition-content-ideas` | Trigify (LinkedIn + YouTube + Twitter) + WebSearch → 5-10 ranked ideas |
| 1.5 | `acquisition-content-extraction` | Map top ideas to full content calendar: YouTube angle + LinkedIn post type + Newsletter story + Substack note |
| 2 | `acquisition-content-youtube-ideation` | Pick winning idea from extraction report, gather fresh context via WebSearch |
| 3 | `acquisition-content-youtube-brief` | Create detailed video brief from idea + context |
| 4 | `acquisition-content-youtube-outline` | Structure the video: sections, timing, demos, visuals |
| 5 | `acquisition-content-youtube-scripting` | Write the script using outline + brief + voice DNA |
| 6 | `acquisition-content-youtube-excalidraw-visuals` | Create Excalidraw diagrams/maps for the video |
| 7 | `acquisition-content-youtube-packaging` | Thumbnail concepts via Nano Banana + title options |
| 8 | `acquisition-content-youtube-description` | SEO-optimized YouTube description |
| 9 | `acquisition-content-youtube-title-generation` | Final title lock |
| 9.5 | `acquisition-operations-youtube-save` | **Auto-runs** — saves Title, Brief, Outline, Script, Description, Thumbnail Prompt to Notion YT Content Dashboard. ExcaliDraw is manual upload. |
| — | **PAUSE if user chose B (recording)** | Wait for transcript |
| 10 | LinkedIn repurpose — pick one or more post types (see below) | Runs each selected type, then immediately pushes to Notion |
| 10a | `acquisition-repurpose-linkedin-story` → `acquisition-operations-linkedin-save` | Write post → push to Notion immediately |
| 10b | `acquisition-repurpose-linkedin-lead-magnet` → `acquisition-operations-linkedin-save` | Write post → push to Notion immediately |
| 10c | `acquisition-repurpose-linkedin-infographic` → `acquisition-operations-linkedin-save` | Write post → push to Notion immediately |
| 10d | `acquisition-repurpose-linkedin-carousel` → `acquisition-operations-linkedin-save` | Write post → push to Notion immediately |
| 10e | `acquisition-repurpose-linkedin-contrarian` → `acquisition-operations-linkedin-save` | Write post → push to Notion immediately |
| 10f | `acquisition-repurpose-linkedin-funny` → `acquisition-operations-linkedin-save` | Write post → push to Notion immediately |
| 11 | `acquisition-content-newsletter-repurpose` | Write the newsletter edition only (story angle + 6-part structure). Saves to your Notion Newsletter Database. |
| 11a | `acquisition-content-newsletter-subject-lines` | **Auto-runs** — generates 5-10 subject line options from the edition |
| 11b | `acquisition-content-newsletter-substack-note` | **Auto-runs** — writes the Substack note. Pushes to your Notion Newsletter Database → Substack Note field |
| 11c | `acquisition-content-newsletter-thumbnail` | **Auto-runs** — generates torn-paper collage thumbnail prompt. Pushes to your Notion Newsletter Database → Thumbnail Prompt field |

---

## Step 3.5 — Brief Quality Gate (self-evaluated, no user prompt)

After the brief from `acquisition-content-youtube-brief` is locked and before `acquisition-content-youtube-outline` begins, evaluate these 5 criteria yourself. Do not ask the user.

1. **Is the target viewer specific?** (not "everyone who uses AI" — a named segment from icp.md)
2. **Does the video have one clear outcome?** (one thing the viewer walks away with — not three things)
3. **Are there at least 2 concrete proof points or demos?** (real results, actual tools, specific steps — not "I'll explain this")
4. **Is there a hook direction specific to this video?** (not a generic opener that could go on any video)
5. **Does it fit the pillar without trying to serve all three at once?**

If all 5 pass: proceed to outline automatically.

If any fail: identify which criteria failed, explain in one line what's missing, and strengthen the brief before proceeding. Do not ask the user to fix it — fix it yourself using the context already available in the session. Only flag it to the user if information is genuinely missing (e.g., no proof point exists anywhere in the session context).

---

## Step 9.5 — YouTube Save (Auto)

After `acquisition-content-youtube-title-generation` completes, immediately invoke:

```
Skill: acquisition-operations-youtube-save
```

No user prompt. No pause. Runs automatically and reports what was saved.

---

## Step 10: LinkedIn Post Type Selection

Before running Step 10, ask:

> "Which LinkedIn post type(s) do you want for this video? You can pick more than one."
>
> 1. **Story** — personal moment + struggle arc (highest engagement: 2.3x-4.1x)
> 2. **Lead Magnet** — giving away a resource or system
> 3. **Infographic** — visual 4:5 portrait image
> 4. **Carousel** — multi-slide document post
> 5. **Contrarian** — challenge a widely-held belief
> 6. **Funny** — short observation, no forced lesson
> 7. **Skip LinkedIn** — newsletter only

For each selected type, invoke the matching repurpose skill immediately followed by the save skill — one pair per post:

```
1 → Skill: acquisition-repurpose-linkedin-story
    → Skill: acquisition-operations-linkedin-save   ← runs immediately after, same post
2 → Skill: acquisition-repurpose-linkedin-lead-magnet
    → Skill: acquisition-operations-linkedin-save
3 → Skill: acquisition-repurpose-linkedin-infographic
    → Skill: acquisition-operations-linkedin-save
4 → Skill: acquisition-repurpose-linkedin-carousel
    → Skill: acquisition-operations-linkedin-save
5 → Skill: acquisition-repurpose-linkedin-contrarian
    → Skill: acquisition-operations-linkedin-save
6 → Skill: acquisition-repurpose-linkedin-funny
    → Skill: acquisition-operations-linkedin-save
```

**Rule:** Never wait until all posts are done to push. Push each post to Notion the moment it is written. If the session ends early or one skill fails, posts already pushed are safe.

Run them in sequence (write then push, write then push). Pass the full script and brief as context to each repurpose skill.

After the last post is pushed, ask:
> "Want a newsletter edition too? (Step 11)"

---

## Step 11 — Newsletter Chain

If user says yes, invoke in sequence — each skill reads the output of the previous one:

```
Step 11  → Skill: acquisition-content-newsletter-repurpose
Step 11a → Skill: acquisition-content-newsletter-subject-lines   (auto — no prompt)
Step 11b → Skill: acquisition-content-newsletter-substack-note   (auto — no prompt)
Step 11c → Skill: acquisition-content-newsletter-thumbnail        (auto — no prompt)
```

Each skill runs with the newsletter edition in context. Do not generate any of these inline — always invoke the dedicated skill.

---

## Story Lock Rule (Command Mode Only)

When running as `/content` command, one video topic is repurposed across all three outputs — LinkedIn story post, newsletter, and script. Because it's the same topic, one story is selected and locked for the entire repurpose chain.

**How it works:**
- The first repurpose skill that selects a story (either Step 10a or Step 11, whichever runs first) locks the story for that topic
- Log it as: `SESSION STORY LOCK: [story title from my-story-doc.md]`
- All subsequent repurpose skills in this session use the same locked story — no re-evaluation
- This applies to: `acquisition-repurpose-linkedin-story` and `acquisition-content-newsletter-repurpose`

**Exception — individual skill runs:** When either skill is called directly (not as part of `/content`), this lock does not apply. Each skill proposes its own best story match for the given topic.

---

## Context Chain

Every skill reads outputs from ALL previous skills. Skill 3 reads from 1+2. Skill 5 reads from 1+2+3+4. This is critical — no skill runs blind.

---

## Output

Save all outputs to `inbox/outputs/` with date prefix:
- `YYYY-MM-DD-content-ideas.md`
- `YYYY-MM-DD-content-extraction.md`
- `YYYY-MM-DD-youtube-brief.md`
- `YYYY-MM-DD-youtube-script.md`
- `YYYY-MM-DD-linkedin-[type].md` — one file per post type generated
- `YYYY-MM-DD-newsletter-repurpose.md`
- `YYYY-MM-DD-newsletter-subject-lines.md`
- `YYYY-MM-DD-newsletter-substack-note.md`
- `YYYY-MM-DD-newsletter-thumbnail-prompt.md`

---

## Rules

- Skills work standalone too — user can call any skill directly without the full routine
- If user chose recording (B), STOP after skill 9.5 and wait for transcript before repurposing
- This command orchestrates — it does NOT contain skill logic
- LinkedIn type selection is always a user choice — never auto-pick. Multiple types are allowed.
- Each LinkedIn post is pushed to Notion immediately after it's written — never wait and batch at the end
- Steps 11a, 11b, 11c are always auto-run — no prompting needed after their trigger step completes
- Newsletter companion skills (11a/11b/11c) use the newsletter edition from Step 11 as their context automatically
