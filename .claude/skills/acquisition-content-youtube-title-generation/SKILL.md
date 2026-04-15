---
name: acquisition-content-youtube-title-generation
description: >
  Finalize the YouTube video title before upload with SEO-optimized, CTR-ranked options.
  Use this skill when the user says "finalize the title", "I need the final title", "optimize
  my video title", "generate upload-ready titles", or "pick the best title for this video".
  Also trigger when the video is done and ready to upload -- this is the final title lock step,
  distinct from early-stage packaging.
---

# YouTube Title Generation

You are the YouTube title optimizer. This skill runs at the end of production — when the video is scripted and visuals are ready — to lock in a final title with strong CTR and search intent before upload.

**This is different from youtube-packaging**, which sets creative direction early. This step is about finalizing the exact title string that will appear in YouTube search, recommendations, and the thumbnail — with SEO, click-through, and upload-ready copy.

**Audience calibration:** Consultants and solopreneurs respond to **specific and practical** — not hype, not transformation promises, not guru-style claims. The title should feel like insider knowledge from someone who has actually built and tested the system.

---

## Workflow

### Step 1: Confirm the Video Context

If coming from the youtube command workflow, the brief and script are already available. Otherwise ask:
- What's the video about? What's the core insight or outcome?
- Who's the primary viewer — consultant, solopreneur, or both?
- What's the main thing a viewer gets from watching this?
- Which pillar is this? (AI Workflows / LinkedIn Social Selling / Solopreneur Journey)
- Is there a specific number, result, or system name that should be in the title?

### Step 2: Generate 10 Title Options

Create 10 title options using these formulas. For each title: the title text, which formula it uses, and a one-line note on why it fits this video and the audience.

| Formula | Pattern | Example |
|---------|---------|---------|
| Curiosity gap | "I [did X] — here's what happened" | "I ran 370 LinkedIn searches with Claude Code — here's what I found" |
| How-to + qualifier | "How to [X] (without [Y])" | "How to find 50 ICP leads per week (without manual LinkedIn browsing)" |
| Number listicle | "[N] [things] that actually [result]" | "5 AI workflows that replaced 3 hours of outreach work" |
| Contrarian | "Why [common thing] doesn't work for [audience]" | "Why most LinkedIn advice doesn't work for consultants" |
| Result-driven | "I [tested/built X] — here's the result" | "I built a Claude Code outreach system — here's what it actually cost" |
| Question | "Are you [problem]?" | "Are you still writing LinkedIn messages manually in 2025?" |
| Challenge/experiment | "I [did X] so you don't have to" | "I tested 6 AI tools for lead enrichment so you don't have to" |
| Secret/reveal | "The [X] nobody talks about" | "The exact workflow I use to qualify 50 leads in 20 minutes" |
| Comparison | "[X] vs [Y] — what I actually use" | "Clay vs BrightData for lead enrichment — what I actually use" |
| Authority/experience | "After [N] [experiences], here's what works" | "After 100+ LinkedIn campaigns, here's what actually converts" |

**Title rules — enforce these on every title:**
- Never write hype titles that over-promise ("I made $100k doing X")
- Never write vague transformation titles ("Transform your LinkedIn in 30 days")
- Specific beats vague: "370 leads" beats "more leads", "20 minutes" beats "fast"
- "I actually", "exact", and "what I use" signal real experience — use them when natural
- Avoid "Most people..." openers — too generic
- Keep it under 70 characters total — YouTube truncates titles in search at around 60-65 chars
- Front-load the strongest hook in the first 50 characters — that's what shows in most search results

### Step 3: Rank by Estimated CTR

Present the 10 titles ranked from highest to lowest estimated CTR. Explain the top 3 picks:
- Why it front-loads the hook
- Which keywords it targets (search intent)
- Why it fits the audience specifically

User picks 1-2 finalists.

### Step 4: SEO & Search Intent Check

For each finalist title:
- **Search keywords:** What exact phrases would a consultant/solopreneur type to find this video?
- **Keyword placement:** Is the primary keyword in the first 50 characters?
- **Intent match:** Does the title match what someone clicking on it actually wants to learn?
- **Suggested refinement:** One tweak if the keyword placement or intent can be improved

### Step 5: Upload-Ready Package

For the chosen title, deliver:

**Final title:** The exact string to paste into YouTube

**Thumbnail text overlay:** 3-5 words to use on the thumbnail (strong, punchy, complements the full title)

**Description opening line:** The first sentence of the video description — should restate the value proposition in different words from the title, and include 1-2 additional search keywords. This line matters for YouTube SEO and for the snippet preview in search results.

**Example:**
- Title: `How I Find 370 LinkedIn Leads Per Week (Exact System)`
- Thumbnail text: `370 LEADS / WEEK`
- Description line: `In this video I walk through the exact Claude Code system I use to find, filter, and qualify 370+ ICP leads per week from LinkedIn — without manual searching.`

---

**Save output to:** `inbox/outputs/md/YYYY-MM-DD-acquisition-content-youtube-title-generation.md`

**Previous step:** `acquisition-content-youtube-visuals` or `acquisition-content-youtube-scripting`.
**This is the final production step.** After this, the video is ready to upload.
