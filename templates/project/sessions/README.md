# Sessions

This folder holds one short summary per meaningful session: what happened, what changed, decisions made, pending items.

Session entities are records, not rules. They do not steer future behavior on their own — decisions and operating stances do. But they are the durable narrative that explains how those decisions got made, and they point to the underlying transcripts that are the verbatim record.

## What counts as "meaningful"

Not every chat. A session is worth a summary entity when:

- Decisions were made.
- Substantial work landed (a deliverable, a structural change, a published artifact).
- A multi-session thread reached a closure point.
- An open thread was opened, advanced, or closed.
- Something happened that a future session would benefit from being able to find again.

A short conversation that produced no commitments or substantive work does not need an entity. The transcript still lives in `evidence/` if extracted; the entity layer stays focused on what mattered.

## File naming

Use the date plus a short kebab-case title:

```text
2026-05-08-continuity-phase-2a-spec-cross-pollination.md
2026-05-07-meridianstandard-migration-cutover.md
```

The slug should be specific enough that the filename alone hints at the work.

## Recommended structure

```markdown
# YYYY-MM-DD — Title

- **Type:** Session
- **Date:** YYYY-MM-DD
- **Agent:** <AI tool, model/version, surface as specifically as known>
- **Tags:** <3–8 compact kebab-case tags>
- **Related entities:** <links to decisions, prior sessions, work entities>
- **Transcript:** <pointer to evidence/ or "Not yet extracted">

---

## What Happened

Three to six paragraphs summarizing the session. Not a transcript replacement — the transcript is the verbatim record.

## Files Modified

Bulleted list. Or "None / session was planning/thinking."

## Decisions Made

If decisions were made, link to the decision entities. Otherwise "None."

## Pending

What remains open, what the next session should pick up, any deploy or follow-up steps still needed.
```

## Agent and Tags discipline

`Agent` should identify the AI system, model/version, and surface as specifically as the session reveals. If the exact model version is not exposed, write that explicitly rather than guessing.

`Tags` support retrieval. Prefer project, domain, process, and artifact tags — for example: `continuity`, `decisions-briefing`, `consolidation-pass`, `roadmap`, `deploy`. Use 3 to 8 tags, kebab-case.

## Transcript pointer

When the session has a transcript in `evidence/` (or wherever transcripts live), point to it. Future sessions can read the transcript when exact wording or sequence matters; for everything else, the entity is the durable narrative.

## What does **not** go here

- Decisions in their own right (those are individual entities in `decisions/`)
- The transcripts themselves (those are evidence and live in `evidence/`)
- Briefings (those are derived from these entities, not vice versa)

## Auto-graduation

A consolidation pass (SPEC §14.1) may write session entities directly when a transcript exists but no entity has been authored. Auto-graduated session entities carry no `status` field — session entities are records, not rules, and do not need a provisional/confirmed dance.
