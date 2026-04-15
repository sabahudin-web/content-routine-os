# Content Routine OS

An AI-powered content production system for Claude Code.

You go from "I need content ideas" to a finished YouTube video, LinkedIn posts, and a newsletter — in one session. Powered by Claude Code and 22 specialized skills.

---

## What This Does

**One command. Full content pipeline.**

```
/content
```

1. Pulls trending ideas from your niche (Trigify + WebSearch)
2. Maps the best idea across YouTube, LinkedIn, and newsletter formats
3. Builds a full YouTube video: brief → outline → script → visuals → title → description
4. Repurposes to LinkedIn (you pick the post type)
5. Writes the newsletter edition + subject lines + Substack note + thumbnail
6. Saves everything to Notion automatically

**22 skills. All working together.**

---

## Installation

### Option A — Fresh install (starting from scratch)

```bash
# Clone the repo
git clone https://github.com/sabahudinmurtic/content-routine-os.git my-content-os

# Open in Claude Code
claude my-content-os

# Run onboarding
# Type: /onboard
```

---

### Option B — Add to your existing Claude Code project

Already have a Claude Code setup (another routine OS, existing agent system)?

```bash
# In your existing project folder, open Claude Code
claude .
```

Then tell Claude:

> "Clone https://github.com/sabahudinmurtic/content-routine-os into a temp folder, then copy the .claude/skills/, .claude/commands/onboard.md, design-kit/, and context/ template files into my project. Don't overwrite any existing files."

Claude will merge the content routine into your setup without disrupting anything else. Then type `/onboard`.

---

## Setup (One-Time)

After installation, run the onboarding session:

```
/onboard
```

The onboard session takes ~30-45 minutes and will:

1. **Explain the system** — walk you through every skill in plain English
2. **Check your tools** — Trigify, Notion, Nano Banana (explains what breaks without each one)
3. **Collect your business info** — offer, ICP, content pillars
4. **Capture your voice** — analyzes your writing examples to extract your patterns
5. **Collect your stories** — 6 guided questions to build your story library
6. **Set up your YouTube strategy** — channel goals, video types, creators you respect
7. **Build your design system** — brand colors, fonts, visual identity
8. **Connect your tools** — Trigify search IDs, Notion database IDs

**After onboarding:** All 22 skills are configured for your business. Just run `/content` and go.

---

## Requirements

| Tool | Purpose | Required? |
|------|---------|-----------|
| **Claude Code** | Runs everything | Required |
| **Trigify** (app + CLI) | Content signal research | Recommended — WebSearch fallback if missing |
| **Notion MCP** | Auto-save outputs | Recommended — saves locally if missing |
| **Nano Banana MCP** | Thumbnail image generation | Optional — text prompts if missing |

---

## How It Works

```
context/ (your business info)
    ↓
22 skills (the production pipeline)
    ↓
inbox/outputs/ (everything you produce, organized by file type)
    ↓
Notion (if connected)
```

---

## Repo Structure

```
├── .claude/
│   ├── commands/
│   │   ├── content.md          ← /content — the main pipeline
│   │   └── onboard.md          ← /onboard — setup session
│   ├── skills/                 ← 22 skills
│   └── rules/                  ← naming, routing, automation rules
├── context/                    ← your business context (filled by /onboard)
├── design-kit/                 ← visual identity + brand assets
├── inbox/outputs/              ← everything you produce
└── CLAUDE.md                   ← system instructions
```

---

## Running Content

```bash
# Full pipeline
/content

# Individual skills also work standalone:
# "Run acquisition-content-ideas" — just get ideas
# "Run acquisition-repurpose-linkedin-story" — just write a story post
# "Run acquisition-content-newsletter-repurpose" — just write a newsletter
```

---

## Questions / Issues

Open an issue on this repo.
