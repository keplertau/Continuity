# Continuity Index

This file tells future AI sessions what to read first.

## Setup Provenance

Created from Continuity version: 0.1.0
Created from Continuity commit: [fill in commit hash or unknown]
Created on: [YYYY-MM-DD]

## Location

Continuity folder location: [write the human-findable path here]

Use a location the human can find again: a project folder, Desktop, Documents, iCloud Drive, Google Drive, Shared Drive, Dropbox, OneDrive, Obsidian vault, Notion export folder, or a GitHub repository.

Do not place Continuity inside a hidden app folder, temp folder, assistant sandbox, cache directory, or deep cloud path unless the human explicitly chooses that location.

## Loading Priority

Hot files are read at `Start continuity`:

- `current.md`
- `decisions.md`

Warm files are read when relevant to the task:

- `preferences.md`
- `open-threads.md`

Cold files are read when evidence, history, or exact wording matters:

- `evidence.md`
- `session-log.md`

If a task is sensitive, high-impact, identity-shaping, or contradictory, read the relevant warm and cold files before acting strongly.

## File Map

- `current.md` - what matters now, including the next-session handoff
- `preferences.md` - stable but reviewable working preferences
- `decisions.md` - active, archived, superseded, and provisional decisions
- `open-threads.md` - unresolved questions, tensions, hypotheses, risks, and watchpoints
- `evidence.md` - sources and pointers
- `session-log.md` - meaningful changes after sessions

## Maintenance

Last reviewed: [YYYY-MM-DD]
Last edited: [YYYY-MM-DD]
Last edited by: [AI/tool/person]
Meaningful sessions since cleanup: 0

After roughly 10 meaningful sessions, propose a merge/prune pass.
