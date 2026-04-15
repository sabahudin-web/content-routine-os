---
name: acquisition-operations-linkedin-save
description: >
  Push a single LinkedIn post to the Notion LinkedIn Content Dashboard immediately after it
  is written. Runs automatically after each individual LinkedIn repurpose skill completes —
  one call per post, not a batch at the end. Also trigger when the user says "save the
  LinkedIn post", "push to LinkedIn dashboard", or "push this post to Notion".
---

# LinkedIn Save (Per Post)

Push one LinkedIn post to the Notion `LinkedIn Content DASHBOARD` database immediately after it is written. This skill runs once per post type — not once for all posts at the end.

**Why per post, not batch:** If a batch push fails or the session ends early, individual posts that were already written get lost. Pushing immediately after each one ensures nothing is missed.

**Notion database:** `LinkedIn Content Workspace` 
**Data source:** `[YOUR_LINKEDIN_NOTION_DB_ID]`

---

## Database Schema Reference

| Notion Field | Type | Source |
|---|---|---|
| `Post Title - Hook` | title | First line (hook) of the post — keep under 100 characters |
| `Draft` | text | Full post text |
| `Post Status` | status | Always `Draft` |
| `Content Pillar` | select | One of: `Content Marketing` / `Social selling` / `AI Worklfows` / `LinkedIn Growth` |
| `Post Format` | select | One of: `Text Only` / `Carousel` / `Infographic` / `Video` / `Poll` / `Text+image (quote style)` |

**Pillar mapping:**
- P1 (AI Workflows & Automation) → `AI Worklfows` ← note: intentional typo in Notion, must match exactly
- P2 (LinkedIn Social Selling) → `Social selling`
- P3 (Solopreneur Journey) → `Content Marketing`

**Format mapping:**
- Story / Lead Magnet / Contrarian / Funny → `Text Only`
- Carousel → `Carousel`
- Infographic → `Infographic`

---

## Workflow

### Step 1: Collect the Post to Save

Take the post that was just written. Identify:
- **Hook** — the first line of the post (becomes the Notion record title)
- **Full text** — the complete post
- **Post type** — Story / Lead Magnet / Infographic / Carousel / Contrarian / Funny
- **Pillar** — P1 / P2 / P3 (from the post's metadata or context)

### Step 2: Push to Notion

Call `mcp__claude_ai_Notion__notion-create-pages` with:
- Parent: data source `[YOUR_LINKEDIN_NOTION_DB_ID]`
- `Post Title - Hook` → first line of the post (under 100 characters)
- `Draft` → full post text
- `Post Status` → `Draft`
- `Content Pillar` → mapped from pillar (see schema reference above)
- `Post Format` → mapped from post type (see schema reference above)

### Step 3: Confirm

After the record is created, confirm:

```
Pushed to LinkedIn Content Dashboard.
  [Post type] → [Notion page URL]
```

This confirmation tells the /content pipeline to continue to the next post type or move on.

---

## Error Handling

| Problem | Action |
|---------|--------|
| Notion MCP not available | Note it, continue pipeline — post is already saved locally in `inbox/outputs/` |
| Hook line is longer than 100 chars | Truncate at the last full word before the 100-char limit |
| Pillar is unclear | Default to `AI Worklfows` for P1 content, ask if still unsure |
| Notion record creation fails | Display the full post text so user can paste manually, note the failure |
| Infographic post type | Set `Post Format` to `Infographic` — note that image file requires manual upload to the record |
