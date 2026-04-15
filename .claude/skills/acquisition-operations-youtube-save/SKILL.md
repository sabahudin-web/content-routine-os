---
name: acquisition-operations-youtube-save
description: >
  Save all YouTube video production outputs to Notion automatically. This skill runs automatically
  at the end of every YouTube production pipeline — after youtube-title-generation completes and
  before LinkedIn repurpose begins. Do not wait to be called manually. Also trigger when the user
  says "save the video", "archive this video", "push to Notion", or "save to YouTube archive".
---

# YouTube Save

Save all YouTube production outputs to the Notion `YT - Content Dashboard` database. This runs automatically after title generation — no user input needed.

**Notion database:** `YT - Content Dashboard`
**Data source:** `collection://[YOUR_YOUTUBE_NOTION_DB_ID]`

---

## Database Schema Reference

| Notion Field | Type | Source |
|---|---|---|
| `YouTube Title Video` | title | Final title from youtube-title-generation |
| `YouTub Outline` | text | Output from youtube-outline |
| `Script` | text | Output from youtube-scripting |
| `YouTube Description` | text | Description opening line from youtube-description |
| `Brief` | text | Full brief from youtube-brief |
| `YouTube Thumbnail` | text | Nano Banana prompt from youtube-packaging (Step 5) |
| `Status` | status | Always `Draft` |
| `ExcaliDraw YouTube` | file | Cannot be set via MCP — manual upload |

---

## Workflow

### Step 1: Collect Outputs from Session

Scan the current session for these outputs. Only save what was actually produced — never invent or summarize content that doesn't exist.

Collect:
- **Title** — finalized title string from youtube-title-generation
- **Outline** — structured outline from youtube-outline
- **Script** — full script from youtube-scripting
- **Description** — full description from youtube-description
- **Brief** — full brief from youtube-brief
- **Thumbnail prompt** — the Nano Banana generation prompt from youtube-packaging Step 5
- **ExcaliDraw JSON** — from youtube-visuals (for local save only)

### Step 2: Create the Notion Record

Call `mcp__claude_ai_Notion__notion-create-pages` with:
- Parent: data source `[YOUR_YOUTUBE_NOTION_DB_ID]`
- `YouTube Title Video` → the finalized title
- `YouTub Outline` → the full outline text
- `Script` → the full script text
- `YouTube Description` → the full description
- `Brief` → the full brief text
- `YouTube Thumbnail` → the Nano Banana thumbnail prompt text
- `Status` → `Draft`

Skip any field that has no content from this session. Do not set `Scheduling` — omit it entirely.

After the record is created, note the Notion page URL.

**If Notion MCP is not available:** Save all outputs as local markdown files in `inbox/outputs/[date]-youtube-package/` instead.

### Step 3: Handle ExcaliDraw — Save Path to Notion

The ExcaliDraw field in Notion cannot receive binary files via MCP. Instead, save the local file path as a text note directly into the Notion page body so it's findable when ready to upload.

If excalidraw output exists from the session:
1. Save it to `inbox/outputs/excalidraw/YYYY-MM-DD-[video-slug].excalidraw` if not already there
2. Call `mcp__claude_ai_Notion__notion-update-page` on the page created in Step 2 and append this to the page body (as a paragraph block):
   ```
   ExcaliDraw file: inbox/outputs/excalidraw/YYYY-MM-DD-[video-slug].excalidraw
   To attach: open this Notion row → ExcaliDraw YouTube field → upload the file above
   ```
3. This means the file path lives inside the Notion record — no hunting for where it is.

If no excalidraw output in session: note it in the summary as "not produced this run." Do not add anything to Notion.

### Step 4: Report Summary

```
YouTube saved to Notion — [TITLE]
  URL: [notion page URL]

Fields saved: Title, Outline, Script, Description, Brief, Thumbnail Prompt, Status: Draft
ExcaliDraw: path written into Notion page body — inbox/outputs/excalidraw/[slug].excalidraw
```

---

## Error Handling

| Problem | Action |
|---------|--------|
| Notion MCP not available | Save all outputs as local markdown in `inbox/outputs/[date]-youtube-package/` |
| No title in session | Use the top title candidate from youtube-packaging as fallback |
| Brief not in session | Skip the Brief field — note in summary |
| Thumbnail prompt not in session | Skip the YouTube Thumbnail field — note in summary |
| ExcaliDraw JSON not in session | Note in summary: "no diagram this run" |
| Notion record creation fails | Display all field values as formatted text for manual paste |
