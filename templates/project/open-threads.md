# Open Threads

This file holds unresolved questions, tensions, hypotheses, risks, and watchpoints.

Open threads are not conclusions. They are the live edges of the project — the questions that have not been answered, the tensions that have not been settled, the hypotheses that have not been tested, the risks that have not been mitigated.

## Maintenance

Last reviewed: [YYYY-MM-DD]
Last edited: [YYYY-MM-DD]
Last edited by: [AI/tool/person]

## Status markers

Use these from SPEC §9 when ambiguity matters:

- `[STALE - REVIEW]` — open more than four weeks without resurfacing in session work; revisit or retire before treating as live.
- `[CONFLICTS-WITH file#section-or-item]` — when a thread points to a tension with another record.

You do not need to label every thread. Label the ones where the marker would change how the next session reads them.

## Active Threads

Use this format:

- **Thread title.** Brief description. What needs to happen for this to resolve. Pointers to related sessions, decisions, or evidence.

[add threads]

## Stale or Quietly Resolved

When a thread has been open more than four weeks without resurfacing, mark it `[STALE - REVIEW]` and surface it for human review. Do not auto-resolve threads — if the work has landed under a different name, leave the marker on and ask in-session whether to retire the thread or rewrite it.

## Resolution

When a thread resolves, do one of:

1. Move the result into `decisions/` (if the resolution is a decision worth preserving as an operating stance) and remove the thread.
2. Move the result into `current.md` (if it changed the immediate situation but is not a stable decision) and remove the thread.
3. Annotate the thread as resolved with a short note pointing to where the resolution lives, and move it to a "Resolved" section at the bottom of this file. Periodic merge/prune passes may move the resolved section to `archive/`.

Do not leave resolved questions open forever. The failure mode is a file that accumulates settled questions until nothing here is actually open.

## Splitting

When threads multiply or develop substantial discussion, split them into individual files under an `open-threads/` folder. Either form is valid — keep the one that fits the project's volume.
