# CLAUDE.md — Content Routine OS

This system gives you a complete AI-powered content production pipeline — from finding trending ideas to publishing a YouTube video, LinkedIn posts, and a newsletter. All in one session.

---

## How to Use This System

| I say... | You run... |
|----------|-----------|
| "content", "video ideas", "YouTube", "create content" | `/content` — research → YouTube pipeline → LinkedIn + newsletter |
| "set up my content system", "configure this for me", "onboard" | `/onboard` — guided setup session to configure everything for your business |

---

## Quick Start

If you haven't run `/onboard` yet, do that first. The onboard session:
1. Explains the system in plain language
2. Asks targeted questions about your business, voice, and audience
3. Fills all context files and skill references automatically
4. Connects your tools (Trigify, Notion, Nano Banana)

**After onboarding: just run `/content` and go.**

---

## How /content Works

```
Research → YouTube Pipeline → LinkedIn Repurpose → Newsletter
```

| Step | What happens |
|------|-------------|
| 1 | `acquisition-content-ideas` — pull trending ideas from Trigify + WebSearch |
| 1.5 | `acquisition-content-extraction` — map ideas to YouTube + LinkedIn + Newsletter angles |
| 2-9 | YouTube pipeline — ideation → brief → outline → script → visuals → packaging → description → title |
| 9.5 | Auto-save to Notion YouTube Dashboard |
| 10 | LinkedIn repurpose — you pick the post type(s) |
| 11-11c | Newsletter chain — edition + subject lines + Substack note + thumbnail (all auto) |

---

## The 22 Skills

All skills live in `.claude/skills/`. Each skill can run standalone OR as part of `/content`.

**Research:**
- `acquisition-content-ideas` — trending ideas from signals
- `acquisition-content-extraction` — map ideas to content calendar

**YouTube pipeline:**
- `acquisition-content-youtube-ideation`
- `acquisition-content-youtube-brief`
- `acquisition-content-youtube-outline`
- `acquisition-content-youtube-scripting`
- `acquisition-content-youtube-excalidraw-visuals`
- `acquisition-content-youtube-packaging`
- `acquisition-content-youtube-description`
- `acquisition-content-youtube-title-generation`
- `acquisition-operations-youtube-save` (auto)

**LinkedIn repurpose (pick one or more per session):**
- `acquisition-repurpose-linkedin-story`
- `acquisition-repurpose-linkedin-lead-magnet`
- `acquisition-repurpose-linkedin-infographic`
- `acquisition-repurpose-linkedin-carousel`
- `acquisition-repurpose-linkedin-contrarian`
- `acquisition-repurpose-linkedin-funny`
- `acquisition-operations-linkedin-save` (auto, runs after each post)

**Newsletter chain:**
- `acquisition-content-newsletter-repurpose`
- `acquisition-content-newsletter-subject-lines` (auto)
- `acquisition-content-newsletter-substack-note` (auto)
- `acquisition-content-newsletter-thumbnail` (auto)

---

## Context Files — What Each Skill Reads

| Skill type | Context files loaded |
|------------|---------------------|
| All skills | `context/business-profile.md` + `context/content-pillars.md` |
| Content, writing, posts, scripts | + `context/my-voice-dna.md` + `context/strong-opinions.md` |
| YouTube and video | + `context/icp.md` + `context/offers.md` |
| Acquisition/targeting | + `context/icp.md` |
| Visual output | + `design-kit/design-tokens.md` + `design-kit/brand-identity.md` |

---

## Where Outputs Go

All outputs save to `inbox/outputs/` with date prefix `YYYY-MM-DD-[skill-name].[ext]`:

| File type | Folder |
|-----------|--------|
| Markdown (.md) | `inbox/outputs/md/` |
| HTML (.html) | `inbox/outputs/html/` |
| PDF (.pdf) | `inbox/outputs/pdf/` |
| Images | `inbox/outputs/images/` |
| Excalidraw | `inbox/outputs/excalidraw/` |
| JSON | `inbox/outputs/json/` |

---

## Tools Required

| Tool | Used for | Required? |
|------|---------|-----------|
| Trigify CLI + app | Content idea signals from LinkedIn, YouTube, Twitter | Recommended (WebSearch fallback if missing) |
| Notion MCP | Auto-saving YouTube, LinkedIn, newsletter outputs | Recommended (saves locally if missing) |
| Nano Banana MCP | Generating thumbnail images | Optional (text prompts if missing) |
| Claude Code CLI | Everything | Required |

---

## Critical Rules

1. Read `context/` files before executing any skill — no blind runs
2. All outputs go to `inbox/outputs/[subfolder]/` named `YYYY-MM-DD-[skill-name].[ext]`
3. Skills pass context forward — Skill 5 reads outputs from Skills 1-4
4. Confirm before any irreversible action
5. Never auto-push content to live platforms — always show for review first
6. Each LinkedIn post pushes to Notion immediately when written — never batch at the end
7. Steps 9.5, 11a, 11b, 11c are always auto-run — no prompting needed
