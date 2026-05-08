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

## Where It Works

Continuity works best in tools where the AI can read and write files: local coding agents, desktop workspaces, project folders, and similar environments.

A browser chat window usually cannot reach your Desktop or project folders by itself. In that case, Continuity can still help, but setup becomes manual: the AI can draft the file contents, and you copy them into place.

Some desktop or app-based AI tools are also partial if they can read uploaded files but cannot create folders or save changes. That is a tool-access limitation, not a problem with Continuity.

If you are on an iPhone, Android phone, or tablet, start with Lite and Manual Mode. Ask the AI to draft a `CONTINUITY.md` file in chat, then save it somewhere you can reopen: Notes, Files, Drive, Obsidian, Notion, GitHub, or another notes app.

If the AI says it cannot access folders, use Manual Mode:

```text
Please create a Lite CONTINUITY.md for me in this chat so I can copy it into a file myself.
```

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

In the first session, the AI should help you create the initial continuity layer by asking only what it needs:

- What is this continuity layer for?
- Where can it create or update the files?

If you already have important decisions, preferences, open questions, notes, chats, or documents, the AI may ask about those too. It should not turn setup into an interview.

The first version can be incomplete. It only needs to be useful enough that the next conversation starts better than the last one.

## Ongoing Use

At the start of a future chat, say:

```text
Start continuity
```

At the end of a meaningful chat, say:

```text
Stop continuity
```

That is the basic rhythm.

Start, work, stop.

The detailed behavior behind those two commands lives in [`COMMANDS.md`](COMMANDS.md).

If you are using a phone or a browser chat, `Start continuity` may mean pasting or uploading your `CONTINUITY.md` file first. `Stop continuity` may mean asking the AI to draft the changes for you to apply manually.
