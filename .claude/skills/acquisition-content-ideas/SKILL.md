---
name: acquisition-content-ideas
description: >
  Research trending content ideas using Trigify + WebSearch, grounded in what's actually resonating
  in Your niche. Use this skill when the user says "content ideas", "what should I post about",
  "trending topics", "what's working on LinkedIn", "find content ideas", or "research ideas".
  Also trigger automatically as Step 1 of the /content routine.
---

# Content Ideas Research

Find 5-10 ranked content ideas by pulling from live Trigify monitoring data (LinkedIn + YouTube + Twitter) and supplementing with WebSearch. Every idea is grounded in real engagement signals — not guesses.

**This skill is Step 1 of the /content routine.** Its output feeds into youtube-ideation and all downstream skills.

Pull a maximum of 3 results per search — we want the freshest, highest-signal items, not volume.

---

## Step 1: Read Context Files

Read these files before anything else:
- `context/offers.md` — what you sell and position around
- `context/content-pillars.md` — the 3 pillars and their mix (40/35/25)
- `context/trigify-search-ids.md` — your Trigify search IDs (fill these in during /onboard)

---

## Step 2: Pull LinkedIn Data

Run via Bash:
```
trigify search results --id [YOUR_LINKEDIN_TRIGIFY_ID] --limit 3 --job-title "Consultant" --seniority "Senior"
```

Remove the `--job-title` and `--seniority` filters if you want broader results (e.g. when the filtered set returns fewer than 3 results).

| Search | ID |
|--------|-----|
| LinkedIn AI Tools & Automation | `[YOUR_LINKEDIN_TRIGIFY_ID]` |

For each result, note: post text snippet, author name/title, reaction count, comment count, post date.

> If you need to create or modify a Trigify search, consult the `trigify-tools` skill first — it has Boolean query rules and keyword strategy patterns that prevent common mistakes.

---

## Step 3: Pull YouTube Data

Run via Bash for each channel (run in parallel if possible):
```
trigify search results --id <id> --limit 3
```

| Channel | ID |
|---------|-----|
| Your Creator 1 | `[YOUTUBE_CHANNEL_1_TRIGIFY_ID]` |
| Your Creator 2 | `[YOUTUBE_CHANNEL_2_TRIGIFY_ID]` |
| Your Creator 3 | `[YOUTUBE_CHANNEL_3_TRIGIFY_ID]` |
| Your Creator 4 | `[YOUTUBE_CHANNEL_4_TRIGIFY_ID]` |

For each result, note: video title, channel name, publish date.

**If a search returns 0 results:** The channel may not have published recently. Note it as "no recent data" and continue with what's available.

---

## Step 4: Pull Twitter (X) Data

Run via Bash for each search (run in parallel if possible):
```
trigify search results --id <id> --limit 3
```

| Search | ID | What it monitors |
|--------|-----|-----------------|
| Claude Code X posts | `[TWITTER_SEARCH_1_TRIGIFY_ID]` | Posts in your niche |
| Twitter Search 2 | `[TWITTER_SEARCH_2_TRIGIFY_ID]` | Your monitored profile |

For each result, note: post text, engagement (likes/retweets if available), post date.

---

## Step 5: WebSearch Supplement

Run 2 targeted WebSearch queries to catch anything Trigify missed:

1. `"[your main topic]" trending 2026` — angle validation
2. `[your niche] content ideas 2026` — topic performance signals

Use results to fill gaps, not to replace Trigify data.

---

## Step 6: Score and Filter

For each item collected, score it silently on 3 factors (1-3 each):

| Factor | What it means |
|--------|--------------|
| **Signal strength** | Engagement relative to the source's typical performance |
| **Pillar fit** | Does it map cleanly to one of Your 3 pillars? (P1: Your Pillar 1, P2: Your Pillar 2, P3: Your Pillar 3) |
| **Uniqueness** | Could you add a distinct angle that doesn't already exist on the topic? |

Total score = Signal + Pillar fit + Uniqueness (max 9). Keep top 10.

---

## Step 7: Build the Ideas Report

Present **5-10 ranked ideas** in this format for each:

```
## Idea #N — [Title / Topic]

**Pillar:** P1 / P2 / P3
**Source:** [LinkedIn | YouTube by X | Twitter | WebSearch]
**Signal:** [engagement data — reactions, comments, views, likes]
**Why it fits Your audience:** [1 sentence connecting to ICP pain point]
**Suggested post type:** [one of the 6 LinkedIn types or YouTube]
**Your unique angle:** [what makes HIS take different from what already exists]
```

End the report with:

> **Pillar balance check:** X ideas for P1 / Y for P2 / Z for P3 (target: ~4/3/3)
>
> **Recommended starting point:** [which idea has the best signal + lowest production friction]

---

## Step 8: Save Output

Save to `inbox/outputs/md/YYYY-MM-DD-acquisition-content-ideas.md`

Tell the user:
> "Ready. Run `acquisition-content-youtube-ideation` to pick one and go deep on it, or call me again tomorrow for a fresh batch."

---

## Edge Cases

| Situation | Action |
|-----------|--------|
| All Trigify searches return 0 results | Fall back fully to WebSearch for this run. Note in output. |
| Only some searches have results | Use what's available, note which searches returned nothing |
| Results are older than 2 weeks | Flag as stale. Run WebSearch harder to compensate. |
| No strong pillar P3 ideas emerge | Generate 1-2 P3 ideas manually from `.claude/skills/acquisition-content-newsletter-repurpose/references/my-story-doc.md` to maintain 40/35/25 balance |
| User runs this standalone (not in /content) | Same workflow — still reads context files, still saves output |
