# Inbox Routing Rule

All inputs and outputs flow through inbox/. No exceptions.

## Inputs
- Raw material goes to inbox/inputs/
- Transcripts, CSVs, briefs, screenshots, client docs
- Named descriptively: call-transcript-acme.md, prospect-list-march.csv

## Outputs
- Everything Claude produces goes to inbox/outputs/ — in the correct subfolder by file type
- Naming convention: `YYYY-MM-DD-[skill-name].[ext]` — the skill name identifies what made it, the date when

| File type | Subfolder |
|-----------|-----------|
| Markdown (.md) | `inbox/outputs/md/` |
| HTML (.html) | `inbox/outputs/html/` |
| PDF (.pdf) | `inbox/outputs/pdf/` |
| Images (.png, .jpg, .jpeg) | `inbox/outputs/images/` |
| Excalidraw (.excalidraw) | `inbox/outputs/excalidraw/` |
| JSON (.json) | `inbox/outputs/json/` |

- Persistent trackers (task-log.md, proposal-tracker.md) stay at `inbox/outputs/` root — they are never dated outputs
- For client/person-specific files, append an identifier: `YYYY-MM-DD-[skill-name]-[client-name].[ext]`

## Archive
- Completed work moves to inbox/archive/
- Only on explicit user confirmation
- Never auto-archive

## Never
- Never write outputs directly into areas/ (those are knowledge, not live work)
- Never write outputs into projects/ (use inbox, then reference from project log)
- Never delete from inbox/ without confirmation
