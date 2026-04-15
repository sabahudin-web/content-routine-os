---
name: acquisition-repurpose-linkedin-story
description: >
  Repurpose a YouTube script, transcript, or topic into a LinkedIn storytelling post using
  [Your Name]'s documented struggle arc. Use this skill when the user says "write a LinkedIn story
  post", "turn this into a story", "repurpose this as storytelling", "I want a personal post about
  this", or "LinkedIn story". Also trigger when the /content routine reaches Step 10 and user picks
  the storytelling format.
---

# LinkedIn Story Post

Write a LinkedIn storytelling post using the Creator Story Arc. This is your highest-engagement format (2.3x - 4.1x) because you don't tell fairy tales — you tell "I almost quit" stories with real people, real places, and the loop still running.

**Engagement multiplier:** 2.3x - 4.1x average
**Dial settings:** Emotion 7-10 / Humor 2-4 / Technical 1-3

---

## Step 1: Read Reference Files

Read before writing anything:
- `context/my-voice-dna.md` — voice rules
- `context/linkedin-content-universe.md` — cult mechanics, storytelling DNA
- `.claude/skills/acquisition-content-newsletter-repurpose/references/my-story-doc.md` — personal stories available

---

## Step 2: Get Source Content

If source content (script, transcript, topic) is not already in context, ask:
> "Paste the content or topic you want to turn into a story post."

---

## Step 3: Find the Story Anchor

**Command mode check:** If this skill is running as part of the `/content` command and a story has already been locked in this session (logged as `SESSION STORY LOCK: [story title]`), use that story directly — do not re-evaluate or propose alternatives. The lock exists so newsletter and LinkedIn story use the same story for the same topic.

**Individual run (not part of /content):** Read `my-story-doc.md` in full. Match source topic to the best available personal story using:
- Emotional resonance: does the story feel connected to this topic?
- Thematic alignment: same underlying lesson?
- Unexpected connection: a surprising bridge (higher engagement than obvious ones)
- Freshness: hasn't been used recently

Present 2-3 story options with a one-line rationale each. Wait for selection before writing.

When a story is selected, log it: `SESSION STORY LOCK: [story title]` — this locks it for any subsequent repurpose skills in this session.

If no story fits: ask them to provide a rough personal moment related to the topic. Never invent stories.

---

## Step 4: Write the Post

Use the confirmed story. Apply the Creator Story Arc:

**Structure:**
1. **HOOK** — Specific moment or confession. Under 10 words. Present tense or punchy past. No "Let me tell you a story."
2. **CONTEXT** — Where you were (the low point). Real specifics: time, place, people.
3. **TURNING POINT** — What changed. Name the person, realization, or system.
4. **TRANSFORMATION** — What's different now. With specifics, not vague "everything changed."
5. **LESSON** — What this taught you. Framed as ongoing, not finished ("I'm still learning...").
6. **P.S.** — Question that invites their story.

**Storytelling triggers to consider:**
- "3 years ago, I was..."
- "Two years ago, I was trapped in..."
- "Life hit me hard in..."
- "I was outperformed by..."
- "[Person's name] taught me something I didn't expect."

---

## Step 5: Apply Belonging Checklist

Before finalizing, check:
- [ ] Named character present? (Jasmin, Charlie, your girlfriend, your nephew, community)
- [ ] Struggle visible? (Not just the win)
- [ ] Geographic anchor? (Sarajevo, Bosnia, or specific place)
- [ ] Positioned as "still figuring it out"? (Not guru)
- [ ] P.S. invites conversation?

Target: 3+ YES. If under 3, revise.

---

## Step 6: Format and Voice Check

**Format rules (non-negotiable):**
- Short sentences. No compound sentences stacked together.
- Each idea gets its own line break.
- No em dashes (—)
- No "Here's what happened"
- No "Most people"
- No generic hooks that could be anyone's
- No AI slop: game-changing, unlock, leverage, optimize, transform
- Digits not words: "3 years" not "three years"
- P.S. at the end, always

**Length:** 150-300 words. Story posts are NOT long essays. Cut ruthlessly.

**Creator Voice Test (self-audit — answer before saving):**

Run these yourself. If any answer is "no", revise before proceeding.

1. Does this sound like you or a polished LinkedIn guru?
2. Is there a real experience or opinion here — not generic advice?
3. Is there a belief that's actually his (not what the internet says)?
4. Would his past self find this genuinely useful?
5. Is it fog-free — no buzzwords, no empty promises, nothing vague?

---

## Step 7: Save Output

Save to `inbox/outputs/md/YYYY-MM-DD-acquisition-repurpose-linkedin-story.md`

Include at the top:
```
Post type: Storytelling (Type 1)
Story used: [story name from my-story-doc]
Pillar: P3 (Solopreneur Journey) or P1/P2 if relevant
Dial: Emotion [X] / Humor [X] / Technical [X]
```

---

## Step 8: Push to LinkedIn Content Dashboard

Push to Notion after saving the file:

1. Call `mcp__claude_ai_Notion__notion-search` with query "LinkedIn Content Dashboard" to find the database ID.
2. Call `mcp__claude_ai_Notion__notion-create-pages` to create the record:
   - **Post title:** First line (hook) of the post — keep under 100 characters
   - **Notes:** Topic context — use the Trigify research summary if available in this session; otherwise write a 1-sentence description of the post topic
   - **Post status:** "Draft"
   - **Content pillar:** Match the closest pillar from `context/content-pillars.md` — if no clear match, skip this field
   - **Draft:** Full text of the LinkedIn post
   - **Post format:** "Story"
3. Confirm: "Pushed to LinkedIn Content Dashboard."

---

## Edge Cases

| Situation | Action |
|-----------|--------|
| No story in my-story-doc fits | Ask them for a rough personal moment — never invent |
| Source content has no personal angle | Use the topic as LESSON, find the story that leads there |
| User wants a P1 or P2 story | Use technical story (built something that broke, client situation) — still applies Arc |
| Post feels too polished | Add one line of "still figuring it out" energy before saving |
