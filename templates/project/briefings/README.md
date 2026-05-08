# Briefings

This folder holds compact orientation files that future AI sessions read first.

Briefings are **derived, not authored.** They are regenerated periodically from the underlying entities — typically by an end-of-session pass, a scheduled consolidation pass (SPEC §14.1), or a manual rebuild after a substantial change. They are not the source of truth.

If a briefing and a decision entity disagree, treat it as drift: follow the decision entity and re-run the consolidation pass.

## Typical files

- **`current-state.md`** — what is in motion right now, what just landed, what is open, what is blocked. Compact rolling summary covering roughly the last four to six weeks.
- **`decisions.md`** — operating stances grouped into Active, On Hold / Deferred, and Superseded. Compressed; prefers source pointers over rationale. Generated only from `decisions/` entities with `active`, `confirmed`, or no status field — provisional entities stay out until promoted (see SPEC §14.1).
- **`recent-sessions.md`** — what happened in recent sessions and what changed because of them. Loaded at session start to prevent cold-start.
- **`processes.md`** *(optional)* — recurring cadences, triggers, audits, and standing maintenance rules. Useful when the project has more than a handful of standing processes.

A roadmap is **not** a briefing. `roadmap.md` lives at the project root and is authored manually during sessions, not derived. Completed items are removed from the roadmap entirely; their record lives in session and decision entities.

## Compression rule

Briefings loaded at session start must carry operational signal, not archival completeness. Prefer source pointers over explanation. If a detail is recoverable from a decision entity or session entity and is not needed to prevent immediate contradiction, leave it in the entity layer.

A briefing entry that takes more than three sentences to describe a single item probably needs shortening — unless the extra detail is required to avoid operational error.

## What does **not** go here

- Active decisions (those go in `decisions/` as individual entities; the briefing is the compressed view)
- Session summaries (those go in `sessions/`; the recent-sessions briefing is the compressed view)
- The roadmap (that lives at the project root)
- Evidence records (those go in `evidence/`)
- Fragments (those go in `fragments/` if the folder exists)

## When to regenerate

Regenerate briefings when:

- A consolidation pass runs (manual end-of-session, scheduled, or AI-driven).
- A new decision entity has shifted what should be visible at session start.
- A briefing and the underlying entities have visibly drifted apart.

Briefings can be overwritten because they are derived files. Underlying entities cannot.
