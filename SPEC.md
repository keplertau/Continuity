# Continuity Specification

Draft v0.2.0
Date: 2026-05-08

**Tagline:** Stop starting over with your AI.

## 1. Purpose

Continuity is a provider-neutral context discipline for human-AI work.

It helps a human and AI keep a coherent working relationship across chats, projects, tools, and time by separating memory into functional registers: current context, stable preferences, decisions, open threads, evidence, session notes, and optional process records.

Continuity is not tied to one storage system. It can be implemented in plain markdown, GitHub, Obsidian, a wiki, a project folder, an AI project space, managed agent memory stores, databases, or future AI memory tools.

The purpose of this specification is to define the placement rules and reading behavior that make Continuity work across all of those substrates.

## 2. Core Claim

Human-AI context becomes more useful when memory is governed by function and authority.

A human-AI continuity layer should make clear:

- what matters right now
- what is stable but still reviewable
- what has been decided
- what is only provisional or inferred
- what remains unresolved
- what evidence supports a claim
- what should be read before strong advice or action
- what belongs in history rather than near the surface

The system fails when all of that becomes one undifferentiated memory bucket. It also fails when the human stops curating the distinctions. Continuity is not only memory the AI uses; it is a shared discipline the human owns.

## 3. Scope

Continuity defines a pattern, not a platform.

It specifies:

- memory registers
- authority levels
- simple start and stop commands
- versioning and provenance
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

**Archive**
Cold storage for full sessions, older documents, retired drafts, bulky notes, and historical reference material. Archive material may be evidence, but it should not steer current work by default.

**Consolidation**
The process of reviewing previous conversations, notes, and records to update the continuity layer. This may be done manually, by an AI assistant at session end, by a scheduled task, or by an agent memory process.

**Staleness**
The risk that a memory item used to be true but no longer reflects the human, project, situation, or evidence.

**Status marker**
A compact label that tells future AI sessions how strongly to treat an item, for example `[CONFIRMED 2026-05-08]` or `[INFERRED 2026-05-08]`.

**Active**
Currently operative. The item should affect future AI behavior unless contradicted by newer evidence or human correction.

**Archived**
Preserved for history but not currently operative. The item may explain why something changed, but should not steer behavior by default.

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

### 5.9 Staleness Resistance

Continuity must make old context easier to detect.

Current context should be reviewed at session start. Preferences should carry a last-reviewed date when they may shape future behavior. Decisions should distinguish active from archived or superseded items.

### 5.10 Human-Findable Location

Continuity should live somewhere the human can find again.

Good default locations include a project folder, Desktop, Documents, iCloud Drive, Google Drive, Shared Drive, Dropbox, OneDrive, Obsidian vault, Notion export folder, wiki folder, or GitHub repository.

Implementations should avoid hidden app folders, temp folders, assistant sandboxes, cache directories, deep cloud paths, and ephemeral workspaces unless the human explicitly chooses them.

### 5.11 Multi-Agent Awareness

When multiple AI tools or sessions may use the same Continuity layer, files should include lightweight edit metadata such as:

```text
Last edited:
Last edited by:
```

This is not a locking system. It is a visibility aid that helps humans and AIs notice possible overlap.

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

Lite should propose upgrading to Standard when the file becomes hard to scan, covers several unrelated domains, or grows beyond roughly 1,500 words.

### 6.2 Standard

Standard is a small folder:

```text
continuity/
  index.md
  current.md
  preferences.md
  decisions.md
  open-threads.md
  evidence.md
  session-log.md
  archive/
```

Standard is best for:

- ongoing projects
- writing and research
- serious personal planning
- repeated AI work
- users who want separation without heavy structure

Standard should propose upgrading to Project when decisions, evidence, session notes, or recurring processes become difficult to audit in a single folder.

### 6.3 Project

Project adds more formal structure:

```text
continuity/
  index.md
  current.md
  briefings/
  decisions/
  sessions/
  evidence/
  archive/
  processes/
  fragments/
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

#### How Project Mode Operates

In Project mode, the registers stop being a single-file mosaic and become a small system that produces and consumes derived layers. The following operating logic is recommended.

**Briefings are derived, not authored.** `briefings/` holds compact orientation files that future sessions read first — typically a current-state briefing, a decisions briefing, a recent-sessions briefing, and (when the project has standing cadences) a process briefing. These are regenerated periodically from the underlying entities; they are not the source of truth. If a briefing and a decision entity disagree, treat it as drift: follow the decision entity and re-run the consolidation pass. The roadmap in `roadmap.md` is an exception — it is authored manually during sessions, not derived.

**Sessions are records; transcripts are evidence.** `sessions/` holds one short summary per meaningful session: what happened, what changed, decisions made, pending items. Each session entity should point to the underlying transcript when one exists. Transcripts are stored under `evidence/` (or a transcripts subfolder) and follow the fidelity discipline in §7.5. The session entity is the durable narrative; the transcript is the verbatim record. When exact wording or sequence matters, future sessions should read the transcript rather than the summary.

**Decisions accumulate as individual entities.** `decisions/` holds one file per significant decision rather than a single rolling document. Each entity carries rationale, what the decision constrains, supersession notes when relevant, and a status field (`active`, `confirmed`, `archived`, `superseded`, or `provisional`). The decisions briefing in `briefings/` is regenerated from entities with `active` or `confirmed` status — provisional decisions stay out of the briefing until promoted (see §14.1).

**Fragments are optional and low-authority.** `fragments/` holds orphan ideas, paragraphs, or insights worth preserving but not yet placed into another register. See §7.10. Project users without much generative material can omit the folder entirely.

**Open threads stay flat or split per thread.** A single `open-threads.md` works until threads multiply or develop substantial discussion. When that happens, a Project may split open threads into individual files under an `open-threads/` folder. Either form is valid.

**Auto-graduation and provisional status.** When a consolidation pass — manual, scheduled, or AI-driven — creates new concept or decision entities from recent transcripts, those entities should be written with `status: provisional` and stay out of the decisions briefing. They graduate to `confirmed` when a later session uses them without objection. This is the safety rail that lets the consolidation pass run without supervision: it cannot reshape operating stances by inference alone. See §14.1 for the recommended Sleep-Cycle Distillation recipe.

**Indexing.** `index.md` carries the loading priorities (hot, warm, cold), the file map, and lightweight maintenance metadata (last reviewed, last edited, meaningful sessions since cleanup). Future AI sessions should read the index before reading individual registers.

**Roadmap is forward-looking only.** `roadmap.md` carries committed work and current priorities. Completed items should be removed; their record lives in session entities and decision entities. This keeps the roadmap small enough to stay useful at session start.

## 7. Register Model

The registers below correspond to distinct cognitive functions a continuity layer needs to support, not to arbitrary file divisions. The split exists because future AI sessions need to treat each kind of memory differently — what to read first, what carries highest evidential weight, what merely orients, what is still open, and what should not steer behavior at all.

The cognitive functions and their operational counterparts:

- **Working awareness** — what matters now. Maps to current context (§7.1) and briefings (§7.9).
- **Normative memory** — stable preferences, identity context, durable working agreements. Maps to preferences (§7.2).
- **Commitment memory** — what has been decided and should not be casually re-litigated. Maps to decisions (§7.3).
- **Open-tension memory** — what remains unresolved. Maps to open threads (§7.4).
- **Evidence memory** — the source record that supports or corrects summaries. Maps to evidence (§7.5) and archive (§7.7).
- **Episodic memory** — what happened in a session and what changed because of it. Maps to session log (§7.6).
- **Process memory** — recurring cadences, triggers, and maintenance rules. Maps to process context (§7.8).
- **Generative memory** — orphan ideas worth preserving without a permanent home yet. Maps to fragments (§7.10).

A continuity layer that flattens these into one undifferentiated bucket loses the ability to tell future sessions which records steer behavior, which carry highest evidential weight, which merely orient, and which are still open. Implementations may merge the operational categories below — a Lite setup typically keeps all of this in a single file — but the cognitive distinctions should remain visible inside whatever structure the implementation uses.

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

**Decay rule:** Review at session start. If an item no longer matters now, move it to session notes, evidence, an archive section, or remove it.

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

**Decay rule:** Items that shape future behavior should carry a last-reviewed date. If a preference has not been reviewed for six months, the AI should surface it as possibly stale before relying on it strongly.

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

**Decay rule:** Decisions should be marked `Active`, `Archived`, or `Superseded` when their status matters. Archived decisions explain history but should not steer current behavior by default.

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

**Decay rule:** If an open thread resolves, move the result into decisions or current context and mark the thread resolved. Do not leave resolved questions open forever.

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

**Fidelity discipline.** Evidence records should declare their fidelity — especially transcripts, chat exports, and any record produced by an extraction step where size limits, host-path access, or tool constraints may produce a partial or compressed result. Recommended header field for any extracted record:

```text
Extraction fidelity: full verbatim | partial | compressed
```

If the record is partial or compressed, a short note immediately under the header should name what is missing or summarized and why. The same note should appear in the consolidation log that produced the file. A summary file may live alongside an evidence record and point to it, but a summary must not be substituted for the evidence record or relabeled as verbatim. When a claim depends on exact wording, sequence, or attribution, future AI sessions should read the evidence record itself and check its fidelity header before treating its content as load-bearing.

### 7.6 Session Log

**Job:** Record meaningful changes after important conversations without duplicating every register.

**Typical file:** `session-log.md` or records under `sessions/`.

**Includes:**

- what happened
- what changed
- what was updated in other files
- what was not captured elsewhere
- transcript or source pointers
- next steps

**Authority:** Medium. Session logs summarize. Evidence records outrank them when exact wording matters.

**Update cadence:** End of meaningful sessions. Do not log every small exchange.

**Failure mode:** The session log becomes a redundant diary that duplicates current context, decisions, and open threads instead of recording what changed.

### 7.7 Archive

**Job:** Preserve full sessions, older documents, retired drafts, bulky notes, and historical reference material without keeping them near the surface.

**Typical location:** `archive/`.

**Includes:**

- full session exports
- old documents
- retired drafts
- older context snapshots
- bulky notes
- attachments or source files

**Authority:** Evidential when relevant, but not operative by default.

**Update cadence:** Add when material should be preserved for later reference. Prune or reorganize during merge/prune passes.

**Failure mode:** The archive becomes either a dump that nobody can search or an active memory source that overwhelms session start.

### 7.8 Process Context

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

### 7.9 Briefings

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

### 7.10 Fragments

**Job:** Preserve orphan ideas, insights, or paragraphs worth keeping that do not yet have a permanent home in another register.

**Typical file:** `fragments.md` or records under `fragments/`. Optional in Lite and Standard; more useful in Project mode.

**Includes:**

- meaningful insights surfaced in a conversation
- paragraphs cut from a draft that may be reused
- candidate concepts not yet developed enough for a concept entity or decision
- generative material from thinking sessions
- ideas waiting for their right context

**Authority:** Low. Fragments are candidates, not commitments. They should not steer behavior unless they graduate into another register.

**Update cadence:** Add when material is worth preserving but does not fit cleanly into current context, decisions, open threads, or evidence.

**Decay rule:** Fragments are allowed to age. A fragment that is never reused is a normal outcome, not drift. Periodic merge/prune passes may consolidate or prune the register.

**Failure mode:** Fragments become a dumping ground large enough that nothing can be found, or fragments are mistaken for decisions and settled positions because they read as polished prose.

**How fragments differ from open threads.** Open threads are unresolved questions, tensions, hypotheses, or risks — things that may need to be resolved. Fragments are orphan content worth preserving without a question attached. An open thread that decays unread is drift to detect; a fragment that decays unused is fine.

## 8. Command Interface

Continuity has two everyday commands.

### 8.1 Start continuity

At the start of a session, the human can say:

```text
Start continuity
```

The AI should read the relevant Continuity files, use current context and active decisions, and flag stale, inferred, provisional, contradictory, archived, or superseded items before relying on them.

The AI should keep this light. It does not need to recite every file it read. It should mention records used only when they materially affect the task.

If `index.md` exists, the AI should use its hot, warm, and cold loading priorities.

If the AI does not know where the Continuity files live, it should ask for the file or folder location once.

### 8.2 Stop continuity

At the end of a meaningful session, the human can say:

```text
Stop continuity
```

The AI should update only the Continuity records that changed. It should keep current context short, preserve decisions and open threads in their proper places, update evidence pointers, and keep the session log focused on what changed.

If the AI cannot access files, it should say so and offer a manual fallback rather than pretending it updated the continuity layer.

## 9. Status Markup

Continuity implementations should use a small shared notation for load-bearing distinctions.

Recommended markers:

- `[CONFIRMED YYYY-MM-DD]` - reviewed or directly stated by the human, currently operative.
- `[PROVISIONAL YYYY-MM-DD]` - useful but not settled.
- `[INFERRED YYYY-MM-DD]` - inferred by the AI, awaiting human confirmation.
- `[ACTIVE YYYY-MM-DD]` - currently operative.
- `[ARCHIVED YYYY-MM-DD]` - preserved for history, not steering current behavior by default.
- `[SUPERSEDED YYYY-MM-DD]` - replaced by a later decision or description.
- `[STALE - REVIEW]` - may be outdated and should be checked before use.
- `[UNVERIFIED]` - plausible or useful, but no clear evidence yet.
- `[LAST-REVIEWED YYYY-MM-DD]` - reviewed on this date for current usefulness.
- `[CONFLICTS-WITH file#section-or-item]` - may contradict another continuity record.

Not every item needs a marker. Items that can affect future behavior should be marked when there is any ambiguity.

AI assistants should preserve existing markers unless the human changes them or the session clearly updates the item.

## 10. Authority And Conflict Rules

Continuity implementations should make authority explicit when it matters.

Canonicality rules:

1. Human correction in the current session outranks stored memory.
2. Direct evidence outranks summaries.
3. Confirmed decisions outrank current context when they address the same question.
4. Active decisions outrank open threads on resolved questions.
5. Current context outranks older preferences for immediate situational facts.
6. Newer records usually outrank older records unless the older record is explicitly marked canonical.
7. Archived and superseded items explain history but should not steer current behavior by default.

If records conflict, the AI should flag the conflict rather than silently choosing a side.

Example:

```text
I see a conflict: current.md says X, but decisions.md has an active confirmed decision saying not-X. I will treat decisions.md as authoritative unless you want to revise it.
```

## 11. Update Rules

### 11.1 Capture

At the end of a meaningful session, capture:

- changed current context
- new or changed decisions
- new open threads
- confirmed or corrected preferences
- evidence pointers
- archive pointers for full sessions or old documents when useful
- next steps

Do not capture everything.

### 11.2 Placement

Place each item in the register where it belongs.

A decision does not belong in current context only. A temporary worry does not belong in stable preferences. A transcript pointer does not belong only in a summary. A full session export does not belong in current context; it belongs in the archive, with a pointer from evidence or the session log.

### 11.3 Review

Review identity-level and preference-level memory with care.

If the AI is not sure whether something is stable, mark it as inferred or provisional.

### 11.4 Supersession

When something changes, do not silently erase the old item if the change matters.

Mark it as superseded, historical, or retired. Note what replaced it.

### 11.5 Deletion

The human may delete any continuity item.

AI assistants should not resist deletion. They may ask whether evidence should be preserved when deletion would remove the only source pointer for a load-bearing claim.

### 11.6 Staleness And Decay

At session start, the AI should check whether current context appears stale.

During updates, the AI should:

- remove stale items from current context
- mark old preferences `[STALE - REVIEW]` when they may affect behavior and have not been reviewed recently
- move resolved open threads to decisions or a resolved section
- mark decisions active, archived, or superseded when their status changes
- preserve evidence pointers before deleting load-bearing summaries

Decay is normal. The goal is not permanent memory. The goal is memory that knows when it should stop steering behavior.

### 11.7 Session Handoff

Continuity layers should preserve a short handoff for the next session when useful.

Recommended wording:

```text
Next session should start by:
```

The handoff should contain one or two concrete starting points, not a second session summary.

### 11.8 Merge/Prune Ritual

After roughly 10 meaningful sessions, the AI should propose a merge/prune pass.

The pass should check whether:

- current context has grown stale
- decisions should be archived or superseded
- open threads have quietly resolved
- preferences need review
- session notes can be compressed
- evidence pointers are preserved before summaries are removed

This should remain a lightweight cleanup ritual, not a database migration.

## 12. Retrieval Discipline

At the start of a session, an AI assistant should read the smallest set of Continuity records needed for the task.

Default read order:

1. `index.md`, if present
2. Current context
3. Decisions relevant to the task
4. Preferences or working agreements relevant to the task
5. Open threads relevant to the task
6. Evidence only when claims matter or action is high-impact

If the Continuity layer defines hot, warm, and cold files:

- hot files are read at `Start continuity`
- warm files are read when relevant
- cold files are read when evidence, history, or exact wording matters

Archives are cold by default. Do not read full archived sessions or old documents unless the task needs exact history, evidence, or old source material.

For simple tasks, do not over-read.

For high-impact tasks, read evidence before making strong claims.

If records conflict, use the authority and conflict rules above. Do not invent a private ranking.

When the task is sensitive, high-impact, or identity-shaping, the AI should briefly tell the human what continuity records it used and flag any stale or conflicting items.

## 13. AI Behavioral Contract

When an AI assistant uses a Continuity layer, it should follow this contract.

At session start:

1. Read the relevant Continuity files before answering.
2. Identify stale markers, conflicts, and load-bearing decisions relevant to the task.
3. Briefly restate what it is using when the task depends on stored context.
4. Ask for clarification before relying on an inferred or stale identity-level claim.

During the session:

1. Prefer confirmed decisions over its own inference.
2. Preserve open questions as open.
3. Mark uncertainty visibly.
4. Do not turn a temporary emotional state or passing preference into stable memory.
5. Flag contradictions between registers.

At session end:

1. Update only the registers that changed.
2. Use the status markup convention.
3. Keep session log entries focused on what changed and what was updated elsewhere.
4. Preserve evidence pointers for load-bearing claims.
5. Propose cleanup when Lite or Standard has outgrown its setup level.

## 14. Consolidation Rules

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

### 14.1 Sleep-Cycle Distillation (Project-Mode Recipe)

For long-running Project-mode workspaces, a recurring distillation pass tends to outperform real-time curation. The pattern below has been validated in live use and is recommended for projects with regular session activity. The recipe is portable across substrates: it can run on a schedule (overnight, weekly), at session end as a manual step, or through an AI memory process. The pattern is what matters; how it executes is an implementation choice.

Phases:

1. **Extract.** Pull new session transcripts (or chat exports, or notes) into the evidence layer. Label extraction fidelity per §7.5. Deduplicate against a state record of previously extracted sessions so the pass is idempotent.

2. **Distill.** Regenerate the derived briefings — typically the decisions briefing and a recent-sessions briefing — from the underlying entities and recently extracted records. Briefings must remain compact: prefer source pointers to rationale; prefer signal to completeness. Manually authored briefings (project structure, roadmap) are not regenerated by the pass.

3. **Graduate.** Write new entity pages directly for candidates surfaced in recent material:
   - **session entities** for any session that has a transcript but no summary entity
   - **concept entities** for named ideas used multiple times across recent sessions
   - **decision entities** for operational stances established in transcript but not yet recorded
   New concept and decision entities are written with `status: provisional`. Session entities carry no status flag.

4. **Promote.** Check existing `provisional` entities against newer transcripts. If a provisional entity's slug, title, or distinctive phrase appears in a later session without objection, promote it to `confirmed`. If the logic is ambiguous, leave it provisional.

5. **Log.** Append a record of what the pass did to a consolidation log: transcripts extracted, briefings regenerated, entities auto-graduated, entities promoted, fidelity issues. The log is the audit trail for an otherwise-silent process.

**Safety rail.** Provisional decisions must not flow into the decisions briefing until promoted. This is the rule that lets the pass run without supervision: it cannot reshape operating stances by inference alone.

**No forced output.** If a phase has nothing to do — no new transcripts, no graduation candidates, no promotions — write nothing for that phase. The pass should be quiet when nothing has changed.

The sleep-cycle pattern complements but does not replace the broader rules above. A project may also run manual end-of-session passes, periodic merge/prune passes (§11.8), or one-off cleanup sessions.

## 15. Plug-And-Play Evolution Points

Continuity is designed to be upgraded, not replaced. Layer boundaries are deliberate so any single layer can be swapped without rebuilding the others. The following are explicit seams where implementations can evolve as AI tools improve:

- **Retrieval layer.** A baseline implementation may rely on filename conventions, plain-text search, or grep over markdown. A later implementation may add a SQLite index, a vector store, embeddings-based semantic search, or a native AI retrieval primitive. The substrate — the markdown layer the human inspects and edits — does not change; only the query tool changes.

- **Distillation engine.** Consolidation may begin as a manual end-of-session step, run on a scheduled task, or rely on a custom AI skill. It may later move to a more capable model, an always-on agent, or a different pipeline entirely. The briefing files and entity pages are the interface; who or what generates them is replaceable.

- **Graph layer.** Relationships between entities may begin implicit, expressed through filenames, wikilinks, and tags. A later implementation may add an explicit graph index — derived from the markdown layer, not authoritative over it — for queries that text search cannot answer well, such as temporal validity, supersession chains, or neighborhood retrieval. Markdown stays canonical; the graph is derived and disposable.

- **Storage and synchronization.** A baseline implementation may live in a local folder with no remote. Later, the same folder can be backed by Git, synchronized through cloud storage, or replicated across devices. Because the canonical form is plain text in a folder, storage choice is portable — the layer moves.

These seams are not promises about specific tools. They are commitments to keep the architecture replaceable.

## 16. Versioning And Provenance

Continuity releases should be traceable.

The project should maintain:

- `VERSION` for the current project version
- `CHANGELOG.md` for release notes
- Git tags such as `v0.1.0` for public release points
- release notes for template, prompt, and specification changes

Generated Continuity setups should include setup provenance in the first file an AI is likely to read:

```text
Created from Continuity version:
Created from Continuity commit:
Created on:
```

If the source commit is not available, write `unknown`. Do not invent a commit hash.

Provenance is not bureaucracy. It lets a future AI or human know which template and specification baseline shaped the continuity layer.

## 17. Interoperability

Continuity can be implemented in many substrates.

Practical compatibility depends on access. A model in a browser chat with no local file access can discuss Continuity and draft files, but it cannot automatically install or maintain a local continuity folder. A file-access agent can create, read, and update the layer directly.

### 17.1 Plain Files

Use markdown files in a folder. This is the default and most portable implementation.

### 17.2 GitHub

Use a repository for templates, versioning, issue tracking, and collaboration.

Nontechnical users do not need to understand Git. They can point an AI assistant at the repository and ask it to set up the files.

### 17.3 Obsidian Or Wikis

Use notes, folders, backlinks, and tags. Keep the register separation visible.

### 17.4 AI Project Spaces

Use project instructions, project files, saved context, or uploaded markdown. Keep stable context separate from current context where the platform allows.

If the project space can store files but not let the AI create folders or save edits, treat it as a partial implementation and use manual updates.

### 17.5 Mobile Or Browser Chat

Use Lite Manual Mode when the AI cannot access local files. The AI can draft `CONTINUITY.md` content or update blocks in chat, and the human can copy them into Notes, Files, Drive, Obsidian, Notion, GitHub, or another accessible place.

Mobile implementations are still valid Continuity implementations when the register distinctions, status markers, and update discipline remain visible.

### 17.6 Managed Agent Memory Stores

Use memory stores for persistent agent-readable records. If the platform supports separate stores, separate shared reference context from user-specific or project-specific memory.

### 17.7 Databases Or Knowledge Graphs

Use structured storage only when it helps. The human-readable continuity layer remains the reference interface.

## 18. Minimum Compatibility Standard

A system is Continuity-compatible if it satisfies these minimum conditions:

1. A human can inspect the memory that matters.
2. Current context is distinguishable from stable context.
3. Confirmed decisions are distinguishable from provisional or inferred notes.
4. Open questions can remain open.
5. Important claims can point to evidence.
6. The human can revise, supersede, archive, or delete memory.
7. A future AI assistant can read the continuity layer and know how strongly to treat each kind of record.
8. Stale, archived, superseded, inferred, and provisional records are visibly distinguishable when they matter.
9. The human can use `Start continuity` and `Stop continuity` instead of long prompts once setup is complete.
10. Generated setups record the Continuity version and source commit when available.
11. The continuity layer lives somewhere the human can find again, or the location is recorded clearly.

Everything beyond that is implementation detail.

## 19. AI Assistant Responsibilities

When an AI assistant is asked to use Continuity, it should:

- read the relevant Continuity files before answering
- keep setup as small as practical
- ask only necessary setup questions
- use a human-findable location and show the full path when location may be unclear
- mark inference as inference
- distinguish decisions from leanings
- use the status markup convention when ambiguity matters
- record setup provenance when creating a new continuity layer
- use graduated loading when an index or equivalent priority map exists
- flag conflicts between registers
- preserve unresolved questions
- connect important claims to evidence
- update only the relevant registers
- avoid overbuilding
- defer identity-level claims to human review

The assistant should not:

- import everything by default
- treat stored memory as unquestionable
- treat old context as current without checking
- resolve contradictions silently
- hide uncertainty in clean summaries
- invent a source version or commit
- hide Continuity inside an obscure folder unless the human explicitly chose it
- make the system dependent on tools the human did not choose

## 20. Human Responsibilities

The human does not need to maintain a perfect system.

The human should:

- correct memory when it is wrong
- confirm or reject inferred preferences
- mark decisions when they are real decisions
- allow old context to be retired
- ask for updates after meaningful sessions
- review stale preferences and identity-level memory when surfaced

Continuity is meant to reduce repetition, not create homework.

## 21. Version Notes

This is draft v0.2.0.

v0.2.0 incorporates lessons from a live working-memory implementation that has run in continuous use for several weeks: cognitive-register framing for §7, fidelity discipline for evidence records (§7.5), a Fragments register (§7.10), operating logic for Project mode (§6.3), the Sleep-Cycle Distillation recipe as a named Project-mode pattern (§14.1), and an explicit Plug-and-Play Evolution Points section (§15) that names the seams along which implementations can evolve.

The immediate next refinements are:

- project-mode templates
- example implementations
- consolidation-pass prompt
- retrieval-discipline prompt
- managed-agent memory store example

The specification should evolve through use.
