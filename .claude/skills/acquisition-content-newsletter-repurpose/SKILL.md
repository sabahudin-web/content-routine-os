---
name: acquisition-content-newsletter-repurpose
description: >
  Convert a video transcript, blog post, or LinkedIn post into a complete Substack newsletter edition.
  Use this skill when the user says "turn this into a newsletter", "repurpose this for Substack",
  "write a newsletter from this transcript", or "convert this post to an email". Also trigger when
  the user provides source content (transcript, article, post) and wants a newsletter edition from it.
---

# Newsletter Repurpose (Content to Newsletter)

Convert source content into a complete newsletter edition using a 6-part story-first structure.

## Phase 1 — Story Angle Selection

### Step 1: Get source content
If not pasted, ask: "Paste the content to repurpose — transcript, post, article, anything."

### Step 2: Analyze source
Identify: core topic, key problem solved, one-line lesson, practical value.

### Step 3: Read the Story Doc
Read `references/my-story-doc.md` in FULL. Go through every story. For each: what happened, emotional core, underlying theme.

### Step 4: Find best match

**Command mode check:** If this skill is running as part of the `/content` command and a story has already been locked in this session (logged as `SESSION STORY LOCK: [story title]`), use that story directly — skip to Phase 2 without presenting options. The lock ensures newsletter and LinkedIn story post use the same story for the same topic.

**Individual run (not part of /content):** Match source topic to best story using: emotional resonance, thematic alignment, unexpected connection, freshness.

When a story is selected, log it: `SESSION STORY LOCK: [story title]` — this locks it for any subsequent repurpose skills in this session.

### Step 5: Present 3 options

**PRIMARY ANGLE** with: Story, Summary, Why it works, Angle type, Structure plan (HOOK/BRIDGE/TRUTH/SYSTEM), Signature lesson.

**BACKUP #1 and #2** — shorter.

Wait for approval before writing.

## Phase 2 — Newsletter Writing

Use confirmed angle. No section labels in output.

### The 6-Part Structure

**1. HOOK** (2-4 paragraphs) — Drop into the story moment. First sentence under 10 words. Present tense. Visual. Three patterns: Moment Drop, Confession, Direct Truth.

**2. BRIDGE** (2-3 paragraphs) — Connect story to business reality. Must use "you" or "your." Never say "Let me tell you why this matters."

**3. TRUTH** (3-5 paragraphs) — What most people get wrong. Call out behavior, not person.

**4. SYSTEM** (3-5 paragraphs) — Practical content from source. Preserve exact language — numbers, tool names, specific steps.

**5. INVITATION** — Primary CTA (link to video) + soft secondary sell.

**6. SIGNATURE** — "To your next client, [Name] '[phrase]' [Last Name]" — phrase captures the one thing to walk away with. Different every time.

## Voice Rules (Non-Negotiable)

**Rhythm:**
- 30% ultra-short: 1-5 words
- 50% medium: 6-15 words
- 20% longer: 16-25 words max
- NEVER exceed 25 words per sentence
- Max 3 sentences per paragraph

**Simplicity:** 4th-6th grade reading level

**Forbidden words:** game-changer, leverage, optimize, crush it, life-changing, transform, next level, unlock, skyrocket, utilize, implement, facilitate, synergy, breakthrough, revolutionary, paradigm, level up, mindset shift

**Hard rules:**
- No em dashes (—)
- No "Stop X / Start Y" hooks — ever
- No "Most people think" as an opener

**Voice fingerprints (use naturally, never forced):**
"The thing is..." / "Here's the deal" / "Let me be real" / "Look..." / "That's it." / "LoL" / P.S. and P.P.S. for secondary CTAs

**Show don't tell.** **Minimal formatting.** Bold 1-2 times max.

## Length Guide

| Source | Newsletter target |
|--------|-----------------|
| 5-7 min transcript | 400-600 words |
| 7-10 min | 600-800 words |
| 10+ min | 800-1000 words |

## Quality Check

- Sounds like a friend at a party, not a professor
- Specific language preserved from source
- Story connected naturally
- Rhythm varies
- CTA clear but not pushy
- Signature phrase unique to this edition

**Creator Voice Test (self-audit — answer before saving):**

Run these yourself. If any answer is "no", revise before proceeding.

1. Does this sound like you or a polished LinkedIn guru?
2. Is there a real experience or opinion here — not generic advice?
3. Is there a belief that's actually his (not what the internet says)?
4. Would his past self find this genuinely useful?
5. Is it fog-free — no buzzwords, no empty promises, nothing vague?

Save to `inbox/outputs/md/YYYY-MM-DD-acquisition-content-newsletter-repurpose.md`

---

## Phase 3 — Push to Notion

Push the newsletter edition to the `Unstuck - Newsletter Database`:

**Notion database:** `Unstuck - Newsletter Database`
**Data source:** `[YOUR_NEWSLETTER_NOTION_DB_ID]`

Fields:
| Notion Field | Type | Value |
|---|---|---|
| `Subject Line` | title | Use date + topic as placeholder: e.g. `2026-03-30 — Context Architecture` — the subject-lines skill will update this later |
| `Newsletter Edition` | text | Full newsletter body text |
| `Status` | status | `Draft` |

1. Call `mcp__claude_ai_Notion__notion-create-pages` with parent data source `[YOUR_NEWSLETTER_NOTION_DB_ID]`
2. Note the Notion page URL — downstream skills (subject-lines, substack-note, thumbnail) will update this same page using `mcp__claude_ai_Notion__notion-update-page`
3. Confirm: "Newsletter edition saved to Notion. Running companion skills now."

**If Notion MCP not available:** Save locally and note the page ID as "not created — companion skills will save locally too."

---

## Important

This skill writes the edition only. Subject lines, Substack note, and thumbnail prompt are each handled by their own dedicated skills — they run automatically after this step in the /content routine. Do not generate them here.
