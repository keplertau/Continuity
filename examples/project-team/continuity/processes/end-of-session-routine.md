# End-of-Session Routine

- **Type:** Process
- **Status:** active
- **Cadence:** per-session
- **Owner:** shared
- **Trigger:** after a meaningful session changes project context, decisions, roadmap, evidence, or open threads
- **Created:** 2026-05-10

---

## What It Does

Keeps the Continuity layer current without turning every chat into an archive project.

## Steps

1. Update `current.md` only if the near-surface state changed.
2. Write or update a session summary in `sessions/` when the session was meaningful.
3. Create decision entities for confirmed decisions; use `status: provisional` for leanings that should not steer yet.
4. Update `open-threads.md` for unresolved questions, risks, and watchpoints.
5. Add evidence pointers when transcripts, links, documents, or notes support a claim.
6. Update `roadmap.md` only for forward-looking committed work.
7. Regenerate briefings when source records changed.

## Inputs

- Current conversation.
- Changed project files.
- Relevant decisions, sessions, and evidence.

## Outputs

- Updated current context.
- Session entity when warranted.
- Decision entity when warranted.
- Updated briefings.
- Updated roadmap or open threads when needed.

## Failure Modes

- Duplicating the whole session instead of recording what changed.
- Letting provisional ideas into the decisions briefing.
- Leaving completed work on the roadmap.

## Change History

- 2026-05-10 - created for launch documentation work.
