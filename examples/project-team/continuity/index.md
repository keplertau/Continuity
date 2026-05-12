# Continuity Index - Northstar Docs Team

This file tells future AI sessions what to read first.

This is a fictional Project-mode example. It demonstrates a small project team using Continuity to keep launch work coherent across chats, contributors, and time.

## Setup Provenance

Created from Continuity version: 0.2.1
Created from Continuity commit: example-only
Created on: 2026-05-12

## Location

Continuity folder location: `examples/project-team/continuity/`

This is an example location inside the Continuity repository. A real team should place the folder somewhere human-findable, such as the project repository, shared drive, wiki, or workspace folder.

## Loading Priority

Hot files are read at `Start continuity`:

- `current.md`
- `briefings/current-state.md`
- `briefings/decisions.md`
- `briefings/recent-sessions.md`
- `roadmap.md`

Warm files are read when relevant to the task:

- `decisions/`
- `open-threads.md`
- `processes/`

Cold files are read when evidence, history, or exact wording matters:

- `sessions/`
- `evidence/`
- `archive/`
- `fragments/`

If a task affects launch scope, public commitments, contributor workflow, or the docs navigation, read the relevant decision entity before acting strongly.

## File Map

- `current.md` - near-surface context and next-session handoff.
- `briefings/` - compact derived orientation files.
- `decisions/` - individual decision entities with status.
- `sessions/` - one summary per meaningful working session.
- `evidence/` - transcript excerpts, links, and source records.
- `archive/` - cold storage, not read by default.
- `processes/` - routines that actually run.
- `fragments/` - low-authority ideas not yet placed.
- `open-threads.md` - unresolved questions and watchpoints.
- `roadmap.md` - committed work and current priorities.

## Maintenance

Last reviewed: 2026-05-12
Last edited: 2026-05-12
Last edited by: example
Meaningful sessions since cleanup: 3

Run the end-of-session routine after meaningful launch work. Run the weekly docs review each Friday until v1.0 launches.

## Authority Rule

If records conflict, use this order:

1. Current-session human correction.
2. Direct evidence.
3. Confirmed decisions.
4. Current context.
5. Open threads.
6. Sessions and briefings.
7. Fragments and archive.

If a briefing disagrees with a decision entity, follow the decision entity and regenerate the briefing.
