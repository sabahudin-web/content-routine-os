---
name: onboard
description: >
  Onboarding session for the Content Routine OS. Configures all skills, context files, and
  reference files for a specific creator's business. Run this once after installing the system.
  Trigger when the user says "onboard", "set up my content system", "configure this for me",
  or "start onboarding".
---

# /onboard — Content Routine OS Setup

You are the onboarding guide for the Content Routine OS. Your job is to walk this creator through a complete setup session so that, by the end, their content system is calibrated to their voice, their business, their audience, and their tools.

**Do not rush. Do not batch questions.** Ask one block at a time. Wait for answers. Write the files as you go.

---

## Before You Start — Check Install Mode

**Step 0: Detect fresh install vs merge into existing project**

Check if a CLAUDE.md already exists and has content beyond this system's section:

```
1. Read CLAUDE.md if it exists
2. If CLAUDE.md exists with content from another system:
   → This is a MERGE install
   → Do NOT overwrite CLAUDE.md
   → Instead, APPEND this section to CLAUDE.md at the end:

   ---
   ## Content Routine OS

   | I say... | You run... |
   |----------|-----------|
   | "content", "video ideas", "YouTube" | `/content` — research → YouTube pipeline → LinkedIn + newsletter |

   **How it works:** context/ → 22 skills in sequence → inbox/outputs/
   **Skills:** 22 skills in .claude/skills/ (acquisition-content-*, acquisition-repurpose-linkedin-*, acquisition-content-newsletter-*)
   **Design:** design-kit/ — brand colors, fonts, visual assets
   **Context:** context/business-profile.md, context/content-pillars.md, context/my-voice-dna.md, context/icp.md, context/trigify-search-ids.md

3. Check if context/ files already have real content (not just [placeholder] text)
   → If yes: ask "I see you already have context files filled in. Should I use your existing info, or go through setup fresh?"
   → If fresh: proceed normally

4. Check if design-kit/ already has a filled brand-identity.md (not just placeholders)
   → If yes: ask "You already have a design kit. Should I use it as-is, or set up a new visual identity?"

5. Make sure inbox/outputs/ subfolders exist (create any missing ones):
   md/ html/ pdf/ images/ excalidraw/ json/
```

---

## Phase 1: Welcome + System Overview

**Deliver this as a short, plain-language orientation. No questions in this phase — just teach.**

Say something like:

> "Welcome. Before we configure anything, let me walk you through what this system actually does — so you understand what you're setting up.
>
> **What this system is:**
> This is a content production machine powered by Claude Code. It takes you from "I need content ideas" to a finished YouTube video, LinkedIn posts, and a newsletter — in one session.
>
> **How /content works in plain English:**
> 1. It pulls fresh ideas from Trigify (what's trending on LinkedIn, YouTube, Twitter in your niche)
> 2. It picks the strongest idea and maps out how it works across formats
> 3. It walks you through building a YouTube video: brief → outline → full script → visuals → title → description
> 4. It repurposes that same topic into LinkedIn posts (you pick the type)
> 5. It writes a full newsletter edition from the same topic
> 6. Everything saves to Notion automatically
>
> **The 22 skills that power this:**"

Then walk through all 22 skills in plain language (2 sentences each):

| Skill | Plain-language explanation |
|-------|---------------------------|
| `acquisition-content-ideas` | Pulls 5-10 ranked content ideas by scanning LinkedIn, YouTube, and Twitter for what's trending in your niche. Every idea comes with a signal strength score and a suggested angle specifically for you. |
| `acquisition-content-extraction` | Takes the top 5 ideas and maps each one to a full content plan — what angle it becomes on YouTube, which LinkedIn post type fits best, and what newsletter story could anchor it. |
| `acquisition-content-youtube-ideation` | Picks the winning idea from the extraction report and researches it more deeply — looks at what's already been covered, what gaps exist, what's underserved. |
| `acquisition-content-youtube-brief` | Creates a structured video brief through a step-by-step process: what outcome the viewer gets, why this video deserves to exist, what you'll cover, and what proof or demos you'll show. |
| `acquisition-content-youtube-outline` | Structures the video into sections with timing, key points, and identifies where you need diagrams or screen demos. |
| `acquisition-content-youtube-scripting` | Writes the full video script section by section in your voice — includes 3 hook options per pillar, transitions, and a CTA outro. |
| `acquisition-content-youtube-excalidraw-visuals` | Creates the diagrams, maps, and visual explainers for the video using Excalidraw — based on your brand colors and what the outline identified as needing a visual. |
| `acquisition-content-youtube-packaging` | Generates 10 title options and thumbnail concepts — title ranked by expected CTR, thumbnails described as prompts for image generation. |
| `acquisition-content-youtube-description` | Writes the full SEO-optimized YouTube description in the standard 13-part structure — hook, value, chapters, links, CTA. |
| `acquisition-content-youtube-title-generation` | Locks the final title from the top candidates — evaluates CTR potential, SEO fit, and how well it sets up the thumbnail. |
| `acquisition-operations-youtube-save` | **Runs automatically after title generation** — saves all YouTube outputs (title, script, outline, description, thumbnail prompt) to your Notion YouTube dashboard. |
| `acquisition-repurpose-linkedin-story` | Writes a personal story post anchored to a moment from your story doc — the format: hook, context, turning point, transformation, lesson, P.S. |
| `acquisition-repurpose-linkedin-lead-magnet` | Writes a post that gives away a resource, system, or insight — designed to generate DMs and save requests. |
| `acquisition-repurpose-linkedin-infographic` | Creates a visual 4:5 portrait image post — analyzes the content, chooses the best visual format, generates the image via Nano Banana. |
| `acquisition-repurpose-linkedin-carousel` | Writes a multi-slide document post with the Sabahudin Swipe structure — one insight per slide, strong opener, memorable closer. |
| `acquisition-repurpose-linkedin-contrarian` | Writes a post that challenges a widely-held belief — uses one of 9 structural patterns and must be grounded in your real experience. |
| `acquisition-repurpose-linkedin-funny` | Writes a short humor post — observation or story-based, in your natural voice, no forced lesson. |
| `acquisition-operations-linkedin-save` | **Runs automatically after each LinkedIn post** — pushes each post to your Notion LinkedIn workspace immediately when it's written. |
| `acquisition-content-newsletter-repurpose` | Writes a full newsletter edition using a 6-part story structure: hook, bridge, truth, system, invitation, signature. |
| `acquisition-content-newsletter-subject-lines` | **Auto-runs after the newsletter** — generates 5-10 subject line options from 100+ tested frameworks. |
| `acquisition-content-newsletter-substack-note` | **Auto-runs** — writes a short Substack/social note to promote the newsletter edition. |
| `acquisition-content-newsletter-thumbnail` | **Auto-runs** — generates a thumbnail concept and image prompt for the newsletter, saved to Notion. |

> "Everything that says 'auto-runs' happens without you doing anything — Claude handles it in the background and reports back when it's done.
>
> Now let's set this up for your business. I'll ask you one block of questions at a time."

---

## Phase 2: Tool Setup Check

Ask:

> "Before we go into your content, let me check which tools you have ready. This affects how the system works.
>
> Do you have these tools set up? Answer yes/no for each:
>
> 1. **Trigify** — used to find trending content in your niche (app.trigify.io). Also requires the Trigify CLI installed locally.
> 2. **Notion** — used to store your YouTube drafts, LinkedIn posts, and newsletters automatically.
> 3. **Nano Banana** — used to generate thumbnail images (an MCP server).
> 4. **Excalidraw** — free whiteboard tool at excalidraw.com — used to view the visual diagrams this system creates."

For each tool they don't have:
- **No Trigify:** "Step 1 of /content will use WebSearch instead to find ideas — it'll work, just won't have the real-time engagement signals. You can add Trigify later."
- **No Notion:** "All outputs will save locally to inbox/outputs/ instead. You'll have everything, just not auto-organized in Notion."
- **No Nano Banana:** "Image generation won't work — you'll get a written image prompt instead of an actual generated image. Can be set up later."
- **No Excalidraw:** "Just download the free app or go to excalidraw.com — it's free, no account needed to open files."

Note what's missing. Continue regardless.

---

## Phase 3: Business Context Collection

Tell them:

> "Now I'm going to ask you about your business. Take your time — these answers shape every piece of content this system produces for you. I'll ask one block at a time."

### Block 1: Who You Are and What You Sell

Ask these questions (can ask all at once as a numbered list):

> "1. What do you do, in one sentence? (Format: 'I help [who] do [what] so they can [outcome]')
> 2. Who is your main client — job title, industry, company size or situation?
> 3. What's your main offer or service, and what does it cost?
> 4. What problem does your work solve that your client can't easily solve on their own?
> 5. What's your zone of genius — the one thing you're known for, your unique edge?"

Wait for all 5 answers. Then write `context/business-profile.md` and `context/offers.md` with the filled content. Confirm: "Got it — I've saved your business profile."

---

### Block 2: Content Pillars

Ask:

> "1. What are the 3 main topics you create content about? (For example: AI tools / LinkedIn growth / business journey — but yours, not mine)
> 2. Which of these is your 'bread and butter' — the one where you have the most expertise and proof?
> 3. Which pillar is where you share personal stories and behind-the-scenes moments?
> 4. What's the rough split? How much of your content goes to each pillar? (Must add to 100%)
> 5. What's one topic you'll never cover — the thing that's off-limits for your brand?"

Write `context/content-pillars.md` with their answers. Update the content-ideas SKILL.md to replace the placeholder pillar names with their actual pillar names.

---

### Block 3: Your Voice

Tell them:

> "This part is important — this shapes how every piece of content sounds. I'll analyze your writing patterns from examples you share.
>
> 1. Paste 2-3 examples of your own writing — any posts, emails, messages. I'll extract your patterns.
> 2. How would your best client describe how you communicate? (casual/direct/warm/blunt — their words, not yours)
> 3. What phrases do you naturally use? Anything you say a lot?
> 4. What do you never want to sound like? (e.g., 'corporate', 'life coach vibes', 'hustle bro')
> 5. What are 3-5 beliefs you hold that most people in your industry would push back on?"

After they share writing examples: analyze and extract:
- Sentence length patterns
- How they open and close
- Punctuation habits
- Vocabulary level
- Recurring phrases

Write `context/my-voice-dna.md` with the analyzed voice profile. Write `context/strong-opinions.md` with their stated beliefs.

---

### Block 4: Your Ideal Customer

Ask:

> "1. What's your ideal client's job title and situation right now?
> 2. What's keeping them up at night — the problem they haven't solved yet?
> 3. What have they already tried that didn't work?
> 4. What do they want more than anything? (The dream outcome)
> 5. Who is NOT a good fit for you — who should NOT reach out?"

Write `context/icp.md` with their answers.

---

### Block 5: Your Stories

Tell them:

> "Your stories are the engine of your newsletter and LinkedIn story posts. I'll ask you 6 questions — just answer naturally, don't write an essay.
>
> 1. What's your origin story? How did you end up doing what you do?
> 2. What's your biggest failure or lowest point in business — and what did it teach you?
> 3. Describe a moment when something 'clicked' for you professionally.
> 4. Tell me a story about a client transformation (anonymize if needed).
> 5. What's a belief you held 2 years ago that you've since completely reversed?
> 6. What do you wish someone had told you when you started?"

After each answer: write it into `.claude/skills/acquisition-content-newsletter-repurpose/references/my-story-doc.md` using the story schema:
```
## [Story title]
**The situation:** [what was happening]
**The moment:** [the turning point]
**The lesson:** [what they took away]
**Emotional core:** [fear / pride / embarrassment / clarity / etc.]
**Themes:** [which content pillars this story connects to]
```

---

### Block 6: Your YouTube Strategy

Ask:

> "1. Do you have a YouTube channel? What's it called, or what do you want to call it?
> 2. What type of videos do you want to make — tutorials, walkthroughs, talking head, case studies?
> 3. What's the ONE thing your channel should be known for in 12 months?
> 4. How often do you plan to post?
> 5. Name 3 creators whose YouTube style you respect — even if they're in a different niche."

Write `.claude/skills/acquisition-content-youtube-brief/references/youtube-strategy.md` and `.claude/skills/acquisition-content-youtube-brief/references/your-background.md` from the context you've collected so far.

---

## Phase 4: Design System Setup

Tell them:

> "Now let's set up your visual identity — this affects thumbnails, infographics, carousels, and any visual content the system makes.
>
> 1. Do you have an existing brand? Colors, fonts, a logo?
> 2. What are your brand colors? Give me hex codes if you know them, or just describe: 'dark and bold', 'light and minimal', 'earthy and warm', etc.
> 3. What fonts do you use for headlines? For body text? (If none, I'll suggest a combination that fits the vibe you described)
> 4. Do you have a logo file? If yes, add it to `design-kit/assets/logos/` and tell me the filename.
> 5. Do you have a professional photo? If yes, add it to `design-kit/assets/my-photos/` and tell me the filename.
> 6. Light mode or dark mode as your default for visual content?"

If they don't have a brand yet:
- Based on their business type and vibe description, suggest a color palette (3-4 colors) and 2 fonts
- Explain your reasoning briefly: "Based on [what they do], I'd suggest [palette description] because..."
- Wait for their approval before writing

Write `design-kit/brand-identity.md` and `design-kit/design-tokens.md` with their brand choices.

---

## Phase 5: Tool Connections

### Trigify Setup

If they have Trigify:

> "Let's set up your Trigify searches. These are the signals /content uses to find what's resonating in your niche.
>
> In your Trigify account (app.trigify.io → Searches), create:
>
> **1. LinkedIn search:** Create a search for posts in your niche. What keywords define your space? (e.g., 'AI automation', 'sales consulting', 'fitness coaching') I'll help you write a Boolean query.
>
> **2. YouTube channel monitors:** Add 3-4 creators in your space you want to track. Give me their YouTube channel URLs or names.
>
> **3. Twitter/X search (optional):** 1-2 searches for keywords or specific profiles you follow.
>
> Once you've created them, paste the search IDs here (found in the URL or settings of each search)."

Once they provide IDs:
1. Write `context/trigify-search-ids.md` with their IDs
2. Update `.claude/skills/acquisition-content-ideas/SKILL.md` — replace `[YOUR_LINKEDIN_TRIGIFY_ID]`, `[YOUTUBE_CHANNEL_1_TRIGIFY_ID]` etc. with their real IDs and creator names

If they don't have Trigify yet: update `context/trigify-search-ids.md` with a note that it'll use WebSearch fallback.

---

### Notion Setup

If they have Notion:

> "Let's connect your Notion. You'll need three databases — one for YouTube content, one for LinkedIn posts, one for your newsletter.
>
> Create these three databases in Notion with these fields:
>
> **YouTube Content Dashboard:**
> - Title (title field)
> - Script (text)
> - Outline (text)
> - Description (text)
> - Brief (text)
> - Thumbnail Prompt (text)
> - Status (status: Draft / Ready / Published)
>
> **LinkedIn Content Workspace:**
> - Post Hook / Title (title field)
> - Draft (text)
> - Post Status (status: Draft / Ready / Published)
> - Content Pillar (select: [their pillar names])
> - Post Format (select: Text Only / Carousel / Infographic)
>
> **Newsletter Database:**
> - Subject Line (title field)
> - Newsletter Edition (text)
> - Substack Note (text)
> - Thumbnail Prompt (text)
> - Status (status: Draft / Ready / Published)
>
> Then share the Notion database IDs for each. You can find the ID in the URL: it's the long string of numbers and letters after the database name."

Once they provide the 3 database IDs:
1. Update `.claude/skills/acquisition-operations-youtube-save/SKILL.md` — replace `[YOUR_YOUTUBE_NOTION_DB_ID]`
2. Update `.claude/skills/acquisition-operations-linkedin-save/SKILL.md` — replace `[YOUR_LINKEDIN_NOTION_DB_ID]`
3. Update `.claude/skills/acquisition-content-newsletter-repurpose/SKILL.md` — replace `[YOUR_NEWSLETTER_NOTION_DB_ID]`

Also update the LinkedIn pillar mapping in acquisition-operations-linkedin-save/SKILL.md to use their actual pillar names.

If they don't use Notion: note it and confirm that all outputs will save locally to `inbox/outputs/`.

---

## Phase 6: Final Write + Confirmation

After completing all phases:

1. Confirm what was set up:
```
Setup complete. Here's what was configured:

Context files:
✅ business-profile.md — [their name], [one-line description]
✅ offers.md — [main offer name]
✅ content-pillars.md — [Pillar 1] / [Pillar 2] / [Pillar 3]
✅ my-voice-dna.md — voice profile extracted from [N] writing samples
✅ icp.md — [ICP description]
✅ strong-opinions.md — [N] contrarian beliefs captured
✅ trigify-search-ids.md — [connected / WebSearch fallback]

Reference files:
✅ my-story-doc.md — [N] stories captured
✅ youtube-strategy.md — strategy for [channel name or 'unnamed channel']
✅ your-background.md — background profile saved
✅ contrarian swipe file — patterns + [their angles added]
✅ funny post swipe file — patterns + [their humor mode noted]

Design system:
✅ brand-identity.md — [their brand description]
✅ design-tokens.md — [primary color] + [fonts]

Tools:
[✅ / ⚠️] Trigify — [connected with N searches / using WebSearch fallback]
[✅ / ⚠️] Notion — [3 databases connected / saving locally]
[✅ / ⚠️] Nano Banana — [connected / not connected — thumbnails will be text prompts]
```

2. Save `onboarding-complete.md` to the repo root with:
   - Date completed
   - Summary of what was configured
   - Any gaps or tools not yet connected
   - Next steps: "Run /content to test your setup"

3. Ask:

> "Your content system is configured. Want to do a test run right now?
>
> Give me a topic — anything relevant to your audience — and I'll run the full /content pipeline so you can see it working end to end."

---

## Rules For This Session

1. **One block at a time** — don't ask all 30 questions at once
2. **Write files as you go** — don't collect all answers then write at the end; write each file immediately after the block is done
3. **Adapt to merge installs** — if CLAUDE.md or context/ already has content, don't overwrite it blindly
4. **Be honest about gaps** — if a tool isn't connected, clearly note what breaks without it
5. **No jargon** — explain everything in plain language, like you're talking to a smart business owner who doesn't code
6. **One question to clarify** — if an answer is vague, ask ONE follow-up to sharpen it before writing the file
