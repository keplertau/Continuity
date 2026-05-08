# Start Here

Continuity is meant to be usable without technical setup.

If you can open this project and talk to an AI assistant, you can begin.

## The Fastest Path

Tell your AI:

```text
I want to use Continuity.

Please read this project, especially AI-SETUP-PROMPT.md, and help me create the simplest useful continuity layer for my situation. Keep it lightweight. Use plain files unless I already have a better place for this.
```

The AI should help you choose a setup level, create the initial files, and fill them with a first version of your context.

If the AI needs the deeper rules, ask it to read `SPEC.md`.

Continuity works best when you treat it as a shared context discipline, not a memory dump. The AI can help maintain it, but the human owns the distinctions.

## Choose A Setup Level

Choose **Lite** if you want the simplest possible version.

Lite creates one file:

```text
CONTINUITY.md
```

Use this for personal AI use, early experiments, or any situation where a folder structure would feel like too much.

Template: `templates/lite/CONTINUITY.md`

Choose **Standard** if you have ongoing work or want better separation.

Standard creates:

```text
continuity/
  current.md
  preferences.md
  decisions.md
  open-threads.md
  evidence.md
  session-log.md
```

Use this for projects, repeated personal planning, writing, research, or anything that keeps coming back across conversations.

Templates: `templates/standard/`

Choose **Project** if you are maintaining a serious long-running workspace.

Project adds more explicit structure for briefings, decision records, evidence, and periodic consolidation. You do not need this on day one unless your work already has that complexity.

## What Goes Where

**Current context** is what the AI should know first in the next conversation: current goals, active concerns, near-term priorities, and what is in motion.

**Preferences** are stable but reviewable patterns: how you like to work, communication preferences, recurring boundaries, and durable project conventions.

**Decisions** are things that should not be casually contradicted: choices already made, with dates and short rationales.

**Open threads** are unresolved questions, tensions, watchpoints, or hypotheses. They should not be collapsed just because the AI wants a clean summary.

**Evidence** is where important claims point back to their sources: transcripts, documents, links, notes, files, or citations.

**Session notes** record what changed after a meaningful conversation.

## Status Markers

Use a small shared notation when ambiguity matters:

```text
[CONFIRMED 2026-05-08]
[PROVISIONAL 2026-05-08]
[INFERRED 2026-05-08]
[ACTIVE 2026-05-08]
[ARCHIVED 2026-05-08]
[SUPERSEDED 2026-05-08]
[STALE - REVIEW]
[UNVERIFIED]
```

You do not need to label everything. Label anything that could shape future AI behavior.

## What The AI Should Not Do

The AI should not dump every old chat into the current context.

The AI should not turn a passing mood into a permanent identity claim.

The AI should not erase unresolved tensions just to make the memory cleaner.

The AI should not require a database, server, plugin, or command-line workflow unless you explicitly want one.

The AI should not make the setup bigger than you can maintain.

The AI should not silently resolve contradictions between files. If current context and decisions disagree, it should flag the conflict.

## First Session

In the first session, the AI should help you create the initial continuity layer by asking a few practical questions:

- What is this continuity layer for?
- Where should it live?
- What should future AI sessions know first?
- What decisions, preferences, or open questions already matter?
- What existing notes, chats, projects, or documents should be treated as evidence?

The first version can be incomplete. It only needs to be useful enough that the next conversation starts better than the last one.

## Ongoing Use

At the start of a future chat, ask the AI to read the relevant Continuity files before answering.

At the end of a meaningful chat, ask the AI to update the continuity layer:

```text
Please update Continuity: current context, decisions, open threads, preferences, session notes, and any evidence pointers that changed. Use the status markers from SPEC.md where ambiguity matters. Keep the session log focused on what changed and what was updated elsewhere.
```

That is the basic rhythm.

Read, work, update.
