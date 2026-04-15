# Automation Levels Rule

Every skill has one of four automation levels:

## AUTONOMOUS
Runs without asking for approval. Used for low-risk, repeatable tasks.
Examples: morning-brief, score-enrich, repurpose-linkedin

## CHECKPOINT
Pauses at key points for human approval. Used for anything client-facing or irreversible.
Examples: create-proposal, onboard-client, draft-campaign-msgs

## SCHEDULED
Runs on a timer automatically. Used for monitoring tasks.
Examples: monitor-replies (every 4 hours)

## MANUAL
Human does the work, agent supports with research and formatting.
Examples: audit-tools, update-sop

## Default
If not specified, default to CHECKPOINT. Better to pause and ask than to produce something wrong.

## Routine Mode Override

When a skill runs inside a routine command (`/content`, `/offer`, `/morning`, etc.), its automation level shifts toward AUTONOMOUS — because the user already committed to running the full routine. Specifically:

- **CHECKPOINT skills in routine mode** skip their internal confirmation pauses. They still stop for genuinely missing data (e.g., no Offer Doc exists), but not for "are you sure?" style confirmations.
- **Standalone mode** (user calls the skill directly) keeps the normal CHECKPOINT behavior with all interactive pauses.
- **How to detect:** If the skill was invoked by a routine command, it is in routine mode. If the user called it directly by name, it is in standalone mode.
- **Exception:** Aimfox campaign launch always pauses for review regardless of mode — that is an irreversible action.
