# Archive

This folder holds cold storage: full session exports, older documents, retired drafts, bulky notes, and historical reference material.

Archived material may still be evidential when relevant, but it should not steer current behavior by default. The archive is what the working layer leaves behind when it stays compact.

## What goes here

- Full session exports that no longer affect current work
- Older documents superseded by current versions
- Retired drafts (writing, design, code)
- Older context snapshots from earlier project phases
- Bulky notes that would clutter `evidence/` if kept near the surface
- Attachments or source files no longer actively referenced

## What does **not** go here

- Active decisions (those stay in `decisions/`)
- Live current context, next steps, or ongoing handoffs
- Evidence that currently supports an active claim (that stays in `evidence/`)
- Open threads or watchpoints
- Anything still being worked

## How to use it

Move material to `archive/` when:

- A session has been summarized and the transcript no longer needs to be near the surface (move the transcript here; keep a pointer from the session entity).
- A draft has been retired or superseded.
- An older document has been replaced by a current version.
- A merge/prune pass concludes that material should be preserved but no longer surfaced by default.

When archived material supports a current claim, leave a pointer from `evidence/` or from the relevant session entity. The archive should be reachable through pointers, not searched cold.

## Reading discipline

The archive is **not** read at `Start continuity`. Future AI sessions should reach the archive only when:

- Exact history matters (and the session entity is not enough).
- Old source material is needed for current evidence.
- A merge/prune or audit pass is reviewing what to surface or further prune.

Treat archive depth as a sign the system is working, not as a problem to solve. A growing archive that the active layer ignores by default is healthier than a flat folder where everything still steers behavior.
