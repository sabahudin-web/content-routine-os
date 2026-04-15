---
name: acquisition-content-newsletter-substack-note
description: >
  Write a high-performing Substack note using proven structural patterns and Your voice.
  Use this skill when the user says "write a Substack note", "promote my newsletter on Substack",
  "write a teaser note", "write a note", or "I need a Substack post". Also triggers automatically
  as part of the /content pipeline and newsletter-repurpose skill — reads previous step context
  directly without asking. When run standalone, asks for context if none is provided.
---

# Newsletter Substack Note

Write a short, high-performing Substack note using proven structural formulas while maintaining
Your authentic voice. Formulas provide the structure — Your rules govern the format.

---

## Step 1 — Determine Mode

**Pipeline mode** (running inside /content or after newsletter-repurpose):
- Read the previous step output directly — newsletter edition, script, or brief already in session
- Do NOT ask for context — extract the core idea from what's already there
- Skip to Step 2 immediately

**Standalone mode** (called directly):
- Check if the user has provided content, topic, or a note idea
- If yes — use it and go to Step 2
- If no — ask: "What's the topic, insight, or newsletter edition you want the note for? Give it rough — I'll sharpen it."

---

## Step 2 — Choose Note Type

Pick the type that best fits the content and goal:

| # | Type | Best For |
|---|------|---------|
| 1 | **Single-Punch Wisdom** | One quotable statement (1-2 sentences) |
| 2 | **Pattern Observation** | Authority-building insight — "I've noticed..." |
| 3 | **Contrarian Statement** | Challenge a widely-held belief |
| 4 | **Problem → Solution** | Hidden root cause → better path |
| 5 | **Vulnerable Personal Story** | Connection through a real moment |
| 6 | **Build-in-Public Update** | Transparent progress with numbers |
| 7 | **List-Based Tactical** | Actionable steps, scannable |
| 8 | **Direct Advice** | Clear instruction with reasoning |
| 9 | **Philosophical Observation** | Life principle or worldview |
| 10 | **Newsletter Tease** | Promote an edition — not a summary, a reason to read |

If goal is unclear, recommend:
- Teaching or giving value → List-Based Tactical or Problem → Solution
- Building authority → Pattern Observation
- Deep connection → Vulnerable Story
- Quick strong take → Contrarian or Single-Punch Wisdom
- Promoting an edition → Newsletter Tease

---

## Step 3 — Apply the Structural Formula

Each type has a pattern. Use it as a skeleton, then write in Your voice.

**Single-Punch Wisdom**
```
[One powerful statement that stands alone]
[Optional: 1 supporting thought]
```

**Pattern Observation**
```
[Hook: "I've noticed..." or "A pattern I keep seeing..."]
[Examples or list of observations]
[Why it matters or the implication]
```

**Contrarian Statement**
```
[Bold claim that contradicts common belief]
[Why conventional thinking is wrong]
[What's actually true or better]
```

**Problem → Solution**
```
["You don't have X because..."]
[Root cause explanation]
[What to do instead]
```

**Vulnerable Personal Story**
```
[Real personal moment or realization]
[Emotional turning point]
[Universal lesson]
```

**Build-in-Public Update**
```
[What you're working on]
[Specific metric or progress]
[Learning or next step]
```

**List-Based Tactical**
```
[Hook: "How to X:" or "If you want Y:"]
- [Action 1]
- [Action 2]
- [Action 3]
[Optional punchy close]
```

**Direct Advice**
```
[Imperative: "Do X" or "Stop Y"]
[Why it matters]
[What happens if you do/don't]
```

**Philosophical Observation**
```
[Core principle or belief]
[Supporting explanation]
[Implication for the reader]
```

**Newsletter Tease**
```
[Polarizing hook related to the topic]
[2-4 lines of tension]
[Door line — newsletter has the full story + link]
```

---

## Step 4 — Apply the Polarization Method

Find the strong version of the opinion — the one that makes someone uncomfortable. Lead with that.

**Examples:**
- Boring: "You should hang around successful people."
- Polarized: "I've never met a successful person surrounded by unsuccessful people. Audit your environment."

- Boring: "Balance consuming and creating."
- Polarized: "Stop bragging that you read 25 books a year. Publish one. Stop telling everyone about the podcasts you listen to. Record one."

Would someone strongly agree or disagree? "Meh" = not polarizing enough. Push the opening harder.

---

## Step 5 — Write the Note

**Format Rules (Non-Negotiable):**
- **4-7 lines total.** If longer, cut.
- **~8 words per sentence.** No compound sentences.
- **No colons** after phrases
- **No emojis**
- **No em dashes** (—)
- **No exclamation points** unless in a quote
- **No "I" to start**
- **No "Stop X / Start Y"** hooks
- **No "Most people"** as an opener
- **Digits not words:** "25" not "twenty five"
- **Single idea only**
- **Each line is its own line** — no wall of text

**Forbidden words:** unlock, discover, skyrocket, revolutionize, leverage, optimize, transform, game-changer, cutting edge, next level, paradigm, synergy, breakthrough, mindset shift, life-changing

**Your Voice Fingerprints** (use sparingly, only when natural):
"The thing is..." / "Look..." / "Let me be real" / "That's it." / "The question is..."

**Opening techniques:**
1. Bold declarative — strong claim that demands attention
2. Personal admission — vulnerable or honest opening
3. Pattern observation — "I've noticed..." builds authority
4. Direct address — "You don't need..." makes it about the reader
5. Contrarian hook — challenges a belief immediately

**Closing techniques:**
1. Punchy restatement — echo the opening memorably
2. Actionable implication — clear next step
3. Quotable one-liner — screenshot-worthy ending
4. Door line (tease only) — link goes last

---

## Quality Check

- Would someone strongly agree or strongly disagree? (not just nod politely)
- Is the hook the bluntest version of the idea?
- Fits 4-7 lines?
- Ends on a landing line?
- No forbidden words or format violations?

If not there yet, push the opening harder.

---

## Step 6 — Save Output

**Save locally** to `inbox/outputs/md/YYYY-MM-DD-acquisition-content-newsletter-substack-note.md`

**Save to Notion** — update the newsletter record in `Unstuck - Newsletter Database` (`2e07fe00-204d-8026-aba8-000bd2c450af`):
- Call `mcp__claude_ai_Notion__notion-update-page` on the current newsletter edition page (page ID from the repurpose skill's session output)
- Field: `Substack Note` → paste the full note text
- If no existing page is found in session, note in the local file: "Notion update skipped — no newsletter page ID in session. Paste manually into Unstuck - Newsletter Database → Substack Note column."

---

## Edge Cases

| Situation | Action |
|-----------|--------|
| No context provided in standalone mode | Ask once: "What's the topic or insight? Give it rough." |
| Pipeline context is vague | Extract the single strongest idea from what's in session — do not invent |
| User doesn't know which type | Recommend based on their goal (see Step 2 table) |
| Note runs long | Cut to 4-7 lines — prefer cutting to compromising format |
| User wants multiple options | Generate 2 versions using different note types, label each |
