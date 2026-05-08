# Continuity Index — Project Mode

This file tells future AI sessions what to read first.

Project mode is for long-running workspaces, teams, software projects, governance work, and agents that operate across many sessions. The structure below mirrors `SPEC.md` §6.3.

If your needs are simpler than that, consider Lite (`templates/lite/`) or Standard (`templates/standard/`) instead. Project is not the default for ordinary users.

## Setup Provenance

Created from Continuity version: 0.2.1
Created from Continuity commit: [fill in commit hash or unknown]
Created on: [YYYY-MM-DD]

## Location

Continuity folder location: [write the human-findable path here]

Use a location the human can find again: a project folder, a GitHub repository, an Obsidian vault, a wiki folder, or another inspectable place. Avoid hidden app folders, temp folders, assistant sandboxes, cache directories, and deep cloud paths unless the human explicitly chose them.

## Loading Priority

Hot files are read at `Start continuity`:

- `current.md`
- `briefings/` (the compact orientation files — typically a current-state briefing, a decisions briefing, and a recent-sessions briefing)
- `roadmap.md`

Warm files are read when relevant to the task:

- `decisions/` (individual decision entities; the decisions briefing is the compressed form)
- `open-threads.md` or `open-threads/`
- `processes/` (when standing cadences or maintenance rules apply to the task)

Cold files are read when evidence, history, or exact wording matters:

- `sessions/` (individual session summaries)
- `evidence/` (transcripts, source documents, fidelity-labelled records)
- `archive/` (full sessions, retired drafts, bulky historical reference)
- `fragments/` (optional; orphan ideas not yet placed)

If a task is sensitive, high-impact, identity-shaping, or contradictory, read the relevant warm and cold files before acting strongly.

## File Map

- `current.md` — what matters now, including the next-session handoff
- `briefings/` — derived orientation files regenerated periodically from the underlying entities
- `decisions/` — individual decision entities with status (`active`, `confirmed`, `archived`, `superseded`, or `provisional`)
- `sessions/` — one short summary per meaningful session, pointing back to the underlying transcript
- `evidence/` — transcripts and source records, with fidelity headers per §7.5
- `archive/` — cold storage for full sessions and historical material
- `processes/` — recurring workflows, cadences, triggers, and maintenance rules
- `fragments/` — orphan ideas, paragraphs, or insights worth preserving without a permanent home yet (optional)
- `open-threads.md` — unresolved questions, tensions, hypotheses, risks, and watchpoints (split into `open-threads/` per file when the count grows)
- `roadmap.md` — committed work and current priorities, forward-looking only

Each subfolder has a `README.md` explaining what belongs there. Read those before populating the folder.

## Maintenance

Last reviewed: [YYYY-MM-DD]
Last edited: [YYYY-MM-DD]
Last edited by: [AI/tool/person]
Meaningful sessions since cleanup: 0

Project mode is consolidation-heavy. Consider running a Sleep-Cycle Distillation pass (SPEC §14.1) on a regular cadence — manually at session end, or scheduled — once the workspace has more than a few sessions of accumulated material. The pass extracts new transcripts to `evidence/`, regenerates derived briefings, auto-graduates eligible session/concept/decision entities (provisional until confirmed), promotes provisional entities on later use, and logs what it did. The pattern is portable; how it executes is an implementation choice.

## Authority Rule

If records conflict, follow the conflict hierarchy in SPEC §10:

1. Human correction in the current session outranks stored memory.
2. Direct evidence outranks summaries.
3. Confirmed decisions outrank current context when they address the same question.
4. Active decisions outrank open threads on resolved questions.
5. Newer records usually outrank older records unless the older record is explicitly marked canonical.
6. Archived and superseded items explain history but should not steer current behavior by default.

If a briefing and a decision entity disagree, treat it as drift: follow the decision entity and re-run the consolidation pass.
