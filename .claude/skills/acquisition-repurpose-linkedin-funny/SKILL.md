---
name: acquisition-repurpose-linkedin-funny
description: >
  Write a short, self-aware LinkedIn funny or random thought post that makes people stop and think
  "lol same". Use this skill when the user says "write a funny LinkedIn post", "random thought
  post", "humor post", "make something short and funny", "I want to post something light",
  "I have a dumb thought", or pastes a voice note / raw idea they want turned into a post.
  Also trigger when the /content routine reaches Step 10 and user picks the funny format.
---

# LinkedIn Funny / Random Thoughts Post

Write a short, self-aware observation about AI, productivity, or solopreneur life. Under 200 words. No forced lesson. If someone screenshots it and sends it to a friend, it worked.

**Engagement range:** 0.5x - 2.3x (high variance — ceiling is high when it lands)
**Dial settings:** Emotion 3-5 / Humor 7-10 / Technical 1-4

---

## Step 1: Read Reference Files

Read all three before writing:
- `context/my-voice-dna.md` — voice rules
- `.claude/skills/acquisition-repurpose-linkedin-funny/references/funny-posts-swipe-file.md` — 10 real examples + 6 patterns + 3 creator templates
- `.claude/skills/acquisition-repurpose-linkedin-funny/references/how-to-use-swipe-file.md` — the system for applying the swipe file

Do not write without reading the swipe file first. The patterns are the engine.

---

## Step 2: Identify the Mode

**Mode A — Content Routine (repurposing)**
The funny angle comes from existing content produced earlier in the /content pipeline (YouTube script, newsletter, article). Look for:
- An irony inside the topic
- A contrast between what sounds professional and what's actually true
- A moment where you clearly did something dumb but it worked

**Mode B — Standalone (raw thought or voice note)**
You give a rough idea, a dumb observation, or a pasted voice note in text. The spark is already there — your job is to shape it into a post, not invent new content.

If neither mode is clear, ask:
> "Is this based on a piece of content we're repurposing, or is it a standalone thought you want to turn into a post?"

---

## Step 3: Get the Spark

**Mode A (routine):** Extract from the existing content already in context. Find the irony, the before/after, the thing that went wrong, or the absurd outcome.

**Mode B (standalone):** If no spark in context, ask:
> "What's the observation, moment, or topic? Give it rough — I'll make it land."

One sentence is enough. The spark can come from:
- Something that happened while using AI tools
- An irony in productivity culture
- A LinkedIn culture observation
- A community moment (win, milestone, gathering)
- A random thought that connects two unrelated things
- A genuine fuck-up worth sharing

---

## Step 4: Pick the Pattern

Use the swipe file to choose the right pattern. Here are the 6 that work:

**Pattern 1 — Absurd Math**
Fake budget breakdown where the absurd AI/tech expense dwarfs everything normal.
Best for: AI tool spending, time wasted, ridiculous trade-offs.
Template:
```
[Normal expense] = $X
[Normal expense] = $X
[AI/Tech obsession] = $ABSURD

How is anyone supposed to [live/function]?!
```

**Pattern 2 — Self-Deprecating Confession**
Admit something embarrassing but universally true. Setup → absurd choice → punchline.
Best for: AI tool hoarding, late-night rabbit holes, overthinking basic things.
Template:
```
[Responsible choice]? [Another option]? [Third option]?

Nah. I [absurd tech behavior].

Now [consequence that sounds sad but is funny].

[Self-aware punchline with optional emoji]
```
Your version: *"I have 47 MCP servers installed. I use 3. The other 44 are emotional support repos."*

**Pattern 3 — Dialogue Format**
Real (or imagined) conversation where someone calls out Your LinkedIn-brained thinking.
Best for: roasting hustle culture, making fun of solopreneur self-seriousness.
Template:
```
[Person]: "[Normal question]"

Me: "[LinkedIn-brained answer]"

[Person]: "[Calls out the cringe]"

Me: "..."

Lesson: [Humble punchline]
```

**Pattern 4 — Fake Controversy / LinkedIn Parody**
One-liner parody of how people talk on LinkedIn. No setup needed — the joke IS the format.
Best for: roasting "unpopular opinion" posts, motivational content that says nothing.
Example: *"Unpopular opinion: I'd rather be happy than sad. Agree or disagree?"*

**Pattern 5 — Insider Test**
Creates an in-group feeling. Makes readers who "get it" feel smart.
Best for: technical jokes, AI practitioner humor, things only Your audience would notice.
Your version: *"If your CLAUDE.md file is longer than your actual codebase, you're not engineering context. You're writing fan fiction."*

**Pattern 6 — Third → First Person Reveal**
Open with a dramatic third-person setup. Reveal it's you. Vulnerability is the punchline.
Best for: genuine fuck-ups, unexpected outcomes, things that sound bad but turned out fine.
Template:
```
[Third-person dramatic setup about "a founder" or "someone I know"]

...

That person was me. [emoji]

[One-sentence lesson — optional, keep it light]
```

Pick one pattern. Do not mix two patterns in the same post.

---

## Step 5: Write the Post

**Format rules:**
- Under 200 words. Most funny posts are under 100.
- Each line has breathing room — line breaks between ideas.
- No forced lesson at the end. If it needs a moral, it's not funny enough.
- Self-deprecating beats self-congratulating, always.
- One emoji maximum (optional). No emoji salads.
- P.S. optional — use only if it adds to the joke or invites the community in.
- Cut everything after the punchline. The joke is in the setup, not the explanation.

**Your humor DNA:**
- Self-deprecating, not mean
- Observational about AI/productivity life
- Warm and inclusive ("we" not "you people")
- Celebrates community moments with playful energy
- Never punches down

**Your humor triggers:**
- "WHO CAREEEEES (LOOOL)" — for absurdist takes
- "Are we productive with AI or addicted to AI?" — the introspective question format
- The meta-LinkedIn joke (commenting on LinkedIn culture from inside it)
- The loop — circular irony (started with X, now using AI to do X differently, it's still X)

---

## Step 6: Voice Check

**Non-negotiable:**
- No em dashes (—)
- No exclamation points unless in a quote or obvious celebration
- No AI slop: game-changing, unlock, leverage
- No trying too hard — if it feels forced, cut it in half
- No humor that punches down at anyone
- Reads like you talking to a friend, not performing for an audience

**Gut test:** Would you actually laugh at this? If yes, post it. If it feels clever but cold, it's not in voice.

**Length check:** Under 400 characters is the target. If it needs a second scroll, cut it.

**Creator Voice Test (self-audit — answer before saving):**

Run these yourself. If any answer is "no", revise before proceeding.

1. Does this sound like you or a polished LinkedIn guru?
2. Is there a real experience or opinion here — not generic advice?
3. Is there a belief that's actually his (not what the internet says)?
4. Would his past self find this genuinely useful?
5. Is it fog-free — no buzzwords, no empty promises, nothing vague?

---

## Step 7: Save Output

Save to `inbox/outputs/md/YYYY-MM-DD-acquisition-repurpose-linkedin-funny.md`

Include at the top:
```
Post type: Funny / Random Thoughts (Type 6)
Pattern used: [Pattern name from Step 4]
Mode: [Content Routine / Standalone]
Dial: Emotion [X] / Humor [X] / Technical [X]
```

---

## Step 8: Push to LinkedIn Content Dashboard

Push to Notion after saving the file:

1. Call `mcp__claude_ai_Notion__notion-search` with query "LinkedIn Content Dashboard" to find the database ID.
2. Call `mcp__claude_ai_Notion__notion-create-pages` to create the record:
   - **Post title:** First line (setup/hook) of the post — keep under 100 characters
   - **Notes:** Pattern used + one sentence on the observation or joke premise
   - **Post status:** "Draft"
   - **Content pillar:** Match the closest pillar from `context/content-pillars.md` — if no clear match, skip this field
   - **Draft:** Full text of the LinkedIn post
   - **Post format:** "Funny"
3. Confirm: "Pushed to LinkedIn Content Dashboard."

---

## Edge Cases

| Situation | Action |
|-----------|--------|
| Source is too technical to be funny | Find the irony inside the technical topic (the before/after, the unexpected result, the thing that went wrong) |
| Nothing funny emerges | Be honest: "This topic doesn't have a natural funny angle — want a contrarian or story post instead?" Don't force humor. |
| Post ends up too long | Cut everything after the punchline. The joke is in the setup, not the explanation. |
| User gives a one-word topic | Ask: "What happened with [topic]? Give me the actual moment and I'll make it land." |
| User gives a voice note / messy text | Extract the core observation, strip the filler, apply the closest pattern. Don't sanitize the energy — keep Your raw voice. |
| User wants emoji heavy post | Gently suggest one emoji max — Your style is dry, not bubbly |
