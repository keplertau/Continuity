# Continuity Specification

Draft v0.1  
Date: 2026-05-08

**Tagline:** Stop starting over with your AI.

## 1. Purpose

Continuity is a provider-neutral context system for human-AI work.

It helps a human and AI keep a coherent working relationship across chats, projects, tools, and time by separating memory into functional registers: current context, stable preferences, decisions, open threads, evidence, session notes, and optional process records.

Continuity is not tied to one storage system. It can be implemented in plain markdown, GitHub, Obsidian, a wiki, a project folder, an AI project space, managed agent memory stores, databases, or future AI memory tools.

The purpose of this specification is to define the placement rules that make Continuity work across all of those substrates.

## 2. Core Claim

AI memory becomes more useful when it is governed by function and authority.

A human-AI continuity layer should make clear:

- what matters right now
- what is stable but still reviewable
- what has been decided
- what is only provisional or inferred
- what remains unresolved
- what evidence supports a claim
- what should be read before strong advice or action
- what belongs in history rather than near the surface

The system fails when all of that becomes one undifferentiated memory bucket.

## 3. Scope

Continuity defines a pattern, not a platform.

It specifies:

- memory registers
- authority levels
- update rules
- retrieval discipline
- consolidation rules
- minimum useful setup levels
- interoperability expectations

It does not require:

- a database
- a vector store
- a knowledge graph
- a command-line workflow
- a hosted service
- a specific AI provider
- a specific notes app

Those can be useful substrates. They are not required.

## 4. Definitions

**Continuity layer**  
The set of files, notes, records, or memory stores that a human and AI use to preserve working context across time.

**Substrate**  
The place the continuity layer lives. Examples: a markdown folder, GitHub repo, Obsidian vault, wiki, chat project, managed agent memory store, local database, or hosted workspace.

**Register**  
A functional memory category. Each register has a different job and a different level of authority.

**Authority**  
How strongly future AI sessions should treat a memory item. A confirmed decision has higher authority than a provisional hypothesis. A transcript has higher evidential authority than a summary.

**Evidence**  
The source material that supports or corrects a memory item: transcript, note, document, link, file, citation, chat export, or other record.

**Consolidation**  
The process of reviewing previous conversations, notes, and records to update the continuity layer. This may be done manually, by an AI assistant at session end, by a scheduled task, or by an agent memory process.

**Staleness**  
The risk that a memory item used to be true but no longer reflects the human, project, situation, or evidence.

## 5. Design Requirements

### 5.1 Accessibility

Continuity must remain usable by a nontechnical person.

The default setup should require no server, database, installation, command line, plugin, or paid platform.

### 5.2 Substrate Neutrality

Continuity must work with whatever memory or storage setup the human already uses.

Implementations should prefer the user's existing tools over introducing a new system.

### 5.3 Inspectability

The human must be able to inspect and edit the continuity layer.

Opaque learned memory may be useful, but it should not be the only place important continuity lives.

### 5.4 Register Separation

Different memory functions must be separated clearly enough that future AI sessions can treat them differently.

At minimum, an implementation should distinguish current context, preferences, decisions, open threads, evidence, and session notes.

### 5.5 Human Authority Over Identity

Stable claims about the human's identity, values, preferences, relationships, health, habits, or boundaries must remain reviewable.

AI assistants may infer patterns, but inferred identity-level claims must be marked as inferred until confirmed by the human.

### 5.6 Evidence Before Certainty

Important claims should point back to evidence when possible.

Summaries are useful orientation. They are not the same as the record.

### 5.7 Continuity Without Captivity

Continuity should preserve coherence without trapping the human in stale preferences, old self-descriptions, superseded decisions, or outdated concerns.

The system must make it possible to revise, supersede, archive, or discard memory.

### 5.8 Minimum Useful Setup

The smallest useful setup is valid.

A single `CONTINUITY.md` file can be a complete Continuity implementation if it separates memory clearly enough for the user's needs.

## 6. Setup Levels

Continuity has three recommended setup levels.

### 6.1 Lite

Lite is one file:

```text
CONTINUITY.md
```

Lite is best for:

- personal use
- first experiments
- simple ongoing context
- users who do not want folders or process overhead

Lite should include headings for:

- current context
- stable preferences
- decisions
- open threads
- evidence
- session notes

### 6.2 Standard

Standard is a small folder:

```text
continuity/
  current.md
  preferences.md
  decisions.md
  open-threads.md
  evidence.md
  session-log.md
```

Standard is best for:

- ongoing projects
- writing and research
- serious personal planning
- repeated AI work
- users who want separation without heavy structure

### 6.3 Project

Project adds more formal structure:

```text
continuity/
  briefings/
  decisions/
  sessions/
  evidence/
  processes/
  open-threads.md
  roadmap.md
```

Project is best for:

- long-running workspaces
- teams
- software projects
- governance work
- agents operating across many sessions
- situations where decisions and evidence need stronger auditability

Project should not be the default for ordinary users.

## 7. Register Model

### 7.1 Current Context

**Job:** Tell the next AI session what matters first.

**Typical file:** `current.md` or the "Current Context" section of `CONTINUITY.md`.

**Includes:**

- active goals
- current concerns
- immediate constraints
- what is in motion
- next steps
- files or evidence to read before acting

**Authority:** High for present orientation, low for long-term identity.

**Update cadence:** Often. Revise whenever the situation changes.

**Failure mode:** Old current context keeps steering future sessions after it stops being current.

### 7.2 Preferences And Identity Context

**Job:** Preserve stable but reviewable information about how the human likes to work and what matters to them.

**Typical file:** `preferences.md`.

**Includes:**

- communication preferences
- recurring boundaries
- durable working style
- stable project conventions
- confirmed personal preferences
- inferred preferences marked clearly as inferred

**Authority:** Medium to high when confirmed, low when inferred.

**Update cadence:** Periodic review. Revise when the human corrects it.

**Failure mode:** The AI turns a temporary mood, old preference, or weak inference into a permanent identity claim.

### 7.3 Decisions

**Job:** Preserve choices already made so future sessions do not casually contradict or re-litigate them.

**Typical file:** `decisions.md` or individual records under `decisions/`.

**Includes:**

- date
- decision
- rationale
- what the decision constrains
- evidence or source pointer
- supersession notes if replaced

**Authority:** High when confirmed.

**Update cadence:** Event-driven. Add when decisions are made. Mark superseded decisions rather than deleting them silently.

**Failure mode:** Provisional leanings harden into decisions, or confirmed decisions disappear from working context.

### 7.4 Open Threads

**Job:** Preserve unresolved questions, tensions, hypotheses, risks, and watchpoints.

**Typical file:** `open-threads.md`.

**Includes:**

- live questions
- unresolved tensions
- hypotheses
- risks
- watchpoints
- items to revisit later

**Authority:** Medium. Open threads are not conclusions.

**Update cadence:** Review when the topic resurfaces or during periodic consolidation.

**Failure mode:** The AI cleans up uncertainty by inventing a settled answer.

### 7.5 Evidence

**Job:** Keep important claims connected to their sources.

**Typical file:** `evidence.md`, `evidence/`, transcript folders, source documents, links, or citation indexes.

**Includes:**

- transcript pointers
- document links
- source files
- notes
- citations
- chat exports
- fidelity notes
- unverified claims

**Authority:** Highest when the source is direct, complete, and relevant.

**Update cadence:** Add when a claim becomes load-bearing.

**Failure mode:** Summaries become treated as evidence, or evidence pointers disappear.

### 7.6 Session Log

**Job:** Record meaningful changes after important conversations.

**Typical file:** `session-log.md` or records under `sessions/`.

**Includes:**

- what happened
- what changed
- decisions made
- open threads
- evidence added
- next steps

**Authority:** Medium. Session logs summarize. Evidence records outrank them when exact wording matters.

**Update cadence:** End of meaningful sessions. Do not log every small exchange.

**Failure mode:** Too much logging creates noise, or too little logging breaks continuity.

### 7.7 Process Context

**Job:** Preserve recurring workflows, triggers, reminders, cadences, or maintenance rules.

**Typical file:** `processes.md` or `processes/`.

**Includes:**

- end-of-session routines
- review cadences
- update triggers
- backup rules
- audit processes
- recurring maintenance

**Authority:** High when the process is active and confirmed.

**Update cadence:** When a process is created, revised, paused, or retired.

**Failure mode:** A process exists in theory but does not run in practice.

### 7.8 Briefings

**Job:** Provide near-surface orientation for complex projects.

**Typical file:** `brief.md`, `briefings/current.md`, or equivalent.

**Includes:**

- project overview
- current priorities
- operating constraints
- recent work
- links to deeper records

**Authority:** High for orientation, lower than evidence for exact claims.

**Update cadence:** When project shape changes or after consolidation.

**Failure mode:** Briefings drift from the underlying records.

## 8. Authority Levels

Continuity implementations should mark authority when it matters.

Recommended authority labels:

- `Confirmed` - reviewed or directly stated by the human, currently operative.
- `Provisional` - useful but not settled.
- `Inferred` - inferred by the AI, awaiting confirmation.
- `Superseded` - replaced by a later decision or description.
- `Historical` - preserved for context but should not steer current behavior.
- `Unverified` - plausible or useful, but no clear evidence yet.

Not every item needs a label. Items that can affect future behavior should be labelled when there is any ambiguity.

## 9. Update Rules

### 9.1 Capture

At the end of a meaningful session, capture:

- changed current context
- new or changed decisions
- new open threads
- confirmed or corrected preferences
- evidence pointers
- next steps

Do not capture everything.

### 9.2 Placement

Place each item in the register where it belongs.

A decision does not belong in current context only. A temporary worry does not belong in stable preferences. A transcript pointer does not belong only in a summary.

### 9.3 Review

Review identity-level and preference-level memory with care.

If the AI is not sure whether something is stable, mark it as inferred or provisional.

### 9.4 Supersession

When something changes, do not silently erase the old item if the change matters.

Mark it as superseded, historical, or retired. Note what replaced it.

### 9.5 Deletion

The human may delete any continuity item.

AI assistants should not resist deletion. They may ask whether evidence should be preserved when deletion would remove the only source pointer for a load-bearing claim.

## 10. Retrieval Discipline

At the start of a session, an AI assistant should read the smallest set of Continuity records needed for the task.

Default read order:

1. Current context
2. Preferences or working agreements
3. Decisions relevant to the task
4. Open threads relevant to the task
5. Evidence only when claims matter or action is high-impact

For simple tasks, do not over-read.

For high-impact tasks, read evidence before making strong claims.

If records conflict:

1. Direct evidence outranks summaries.
2. Confirmed decisions outrank provisional notes.
3. Newer records usually outrank older records unless the older record is explicitly marked canonical.
4. Human correction in the current session outranks stored memory.

## 11. Consolidation Rules

Consolidation may happen manually, at session end, on a schedule, or through an AI memory process.

A consolidation pass may:

- merge duplicates
- update stale current context
- promote confirmed items
- mark old items historical
- link summaries to evidence
- identify contradictions
- propose cleanup

A consolidation pass must not:

- silently turn inference into fact
- erase unresolved tensions
- overwrite confirmed decisions without noting supersession
- convert temporary states into identity claims
- discard evidence pointers for important claims
- make the system larger than the user can maintain

When possible, consolidation should produce reviewable changes rather than silent mutation.

If an AI platform offers background memory consolidation, dream-like memory updates, or agent memory refinement, Continuity can use it as a consolidation engine. The output should still be treated as a proposed update to a governed continuity layer, not as unquestioned truth.

## 12. Interoperability

Continuity can be implemented in many substrates.

### 12.1 Plain Files

Use markdown files in a folder. This is the default and most portable implementation.

### 12.2 GitHub

Use a repository for templates, versioning, issue tracking, and collaboration.

Nontechnical users do not need to understand Git. They can point an AI assistant at the repository and ask it to set up the files.

### 12.3 Obsidian Or Wikis

Use notes, folders, backlinks, and tags. Keep the register separation visible.

### 12.4 AI Project Spaces

Use project instructions, project files, saved context, or uploaded markdown. Keep stable context separate from current context where the platform allows.

### 12.5 Managed Agent Memory Stores

Use memory stores for persistent agent-readable records. If the platform supports separate stores, separate shared reference context from user-specific or project-specific memory.

### 12.6 Databases Or Knowledge Graphs

Use structured storage only when it helps. The human-readable continuity layer remains the reference interface.

## 13. Minimum Compatibility Standard

A system is Continuity-compatible if it satisfies these minimum conditions:

1. A human can inspect the memory that matters.
2. Current context is distinguishable from stable context.
3. Confirmed decisions are distinguishable from provisional or inferred notes.
4. Open questions can remain open.
5. Important claims can point to evidence.
6. The human can revise, supersede, archive, or delete memory.
7. A future AI assistant can read the continuity layer and know how strongly to treat each kind of record.

Everything beyond that is implementation detail.

## 14. AI Assistant Responsibilities

When an AI assistant is asked to use Continuity, it should:

- read the relevant Continuity files before answering
- keep setup as small as practical
- ask only necessary setup questions
- mark inference as inference
- distinguish decisions from leanings
- preserve unresolved questions
- connect important claims to evidence
- update only the relevant registers
- avoid overbuilding
- defer identity-level claims to human review

The assistant should not:

- import everything by default
- treat stored memory as unquestionable
- treat old context as current without checking
- hide uncertainty in clean summaries
- make the system dependent on tools the human did not choose

## 15. Human Responsibilities

The human does not need to maintain a perfect system.

The human should:

- correct memory when it is wrong
- confirm or reject inferred preferences
- mark decisions when they are real decisions
- allow old context to be retired
- ask for updates after meaningful sessions

Continuity is meant to reduce repetition, not create homework.

## 16. Version Notes

This is draft v0.1.

The immediate next refinements are:

- project-mode templates
- example implementations
- consolidation-pass prompt
- retrieval-discipline prompt
- managed-agent memory store example
- license and repository publication materials

The specification should evolve through use.
