# Continuity - Project Context

Continuity is a living context system for keeping human-AI relationships and communications alive and coherent across chats, projects, and time.

AI becomes much more useful when the human and AI share a living continuity layer: one that keeps stable identity, ideas, opinions, current concerns, unresolved questions, evidence, and boundaries in different registers instead of flattening everything into generic memory.

Stop starting over with your AI. Continuity is a shared working context for humans and AI: a personal human-AI continuity system.

---

## What This Project Is

Continuity is a pattern for better memory placement, better relationship continuity, and better context governance between a human and AI over time. It improves whatever memory setup a person already uses.

Many AI memory systems focus on recall: store, retrieve, and make prior material available. Continuity adds a second question: what should a human-AI relationship keep near the surface, what should settle into structured memory, what should remain archived as evidence, and what confidence should future AI agents assign to each layer?

The project grows out of the Archive system built for Carsten's work across the Meridian Codex and related projects. The Archive proved that a layered memory architecture can make AI collaboration feel less like repeated prompting and more like a continuing relationship. Continuity generalizes that pattern beyond one project.

## The Core Claim

The weak point in human-AI collaboration is not only that AI forgets facts. The deeper weakness is that the human and AI do not share durable continuity. Every new chat risks flattening the relationship back into prompt-and-response. Stable preferences, prior decisions, unresolved tensions, current concerns, boundaries, and evidence all blur together or disappear.

Continuity treats this as a communication and relationship problem, not only a technical memory problem.

The aim is to help the partnership know:

- what is alive right now
- what has already been decided
- what should not be contradicted casually
- what is only provisional
- what evidence supports a claim
- what needs to be re-read before strong action
- what belongs near the surface and what can live deeper down

The public-facing tagline for the project:

**Stop starting over with your AI.**

## Who It Is For

Continuity should work for serious project collaboration and for ordinary personal AI use.

In project mode, it helps a human and AI carry context across long-running work: strategy, writing, code, decisions, research, governance, publication, deployment, and unresolved threads.

In personal mode, it should help someone keep coherence across many ordinary chats: health, family, food, relationships, work, habits, private concerns, recurring questions, and personal preferences. The user should not need to be building a formal project for Continuity to matter.

The broader value may be strongest here: helping an individual maintain a living, inspectable context layer across months and years of AI conversations without relying entirely on opaque platform memory.

## What It Does Not Require

Continuity does not require a vector database.

It does not require a knowledge graph.

It does not require a wiki, though it can work inside one.

It does not require a second-brain productivity system.

It does not require replacing an AI model's native memory. Native memory may improve, but an external continuity layer remains useful because it is inspectable, portable, editable by the human, and capable of assigning different kinds of authority to different kinds of records.

## Current Working Model

The current live implementation is the Archive in `/Users/carsten/Projects/Archive`. It uses layered memory registers:

- **Working awareness:** briefings, current priorities, live context
- **Commitment memory:** confirmed decisions and operating constraints
- **Episodic memory:** session entities and summaries of what happened
- **Evidence memory:** transcripts, source files, and fidelity-labelled records
- **Process memory:** recurring cadences, triggers, audits, and protocols
- **Normative memory:** the collaboration posture and drift-detection commitments
- **Open-tension memory:** unresolved questions, aporias, watchpoints, and pending work

The nightly consolidation pass is one mechanism inside this larger architecture. It extracts transcripts, regenerates derived briefings, auto-graduates eligible entities, promotes provisional records on later use, and logs fidelity issues. But Continuity should not be reduced to "nightly archiving." The more important idea is memory placement: deciding where a piece of context belongs and what authority it has.

## Registers, Not One Memory Bucket

Continuity depends on separating memory by function.

**Near-surface context** is what the AI should know immediately at session start: current priorities, active concerns, standing constraints, recent work.

**Stable identity context** is what should persist across time: communication preferences, durable values, recurring patterns, self-descriptions, relationships, and boundaries.

**Decision context** is what has been decided and should not be re-litigated unless new evidence appears.

**Open-thread context** is what remains unresolved: questions, tensions, watchpoints, hypotheses, and items that should resurface later.

**Evidence context** is the record that supports or corrects the summaries: transcripts, notes, documents, source files, citations, and extracted records.

The system works when future AI sessions can tell the difference between these registers. It fails when everything becomes generic "memory."

## Design Principles

**Inspectable over opaque.** The human must be able to see and edit what the system remembers.

**Placement over accumulation.** The system should not hoard context. It should decide what belongs near the surface, what belongs in structure, and what belongs as evidence.

**Continuity without captivity.** The system should preserve coherence without locking the human into old self-descriptions, stale decisions, or outdated concerns.

**Human authority over identity.** AI may infer patterns, but stable identity claims about the human should remain reviewable and revisable by the human.

**Evidence before certainty.** A summary is not the same thing as the record. When a claim matters, the system should know what source supports it.

**Project and personal use both matter.** The architecture should support formal workspaces and ordinary life conversations.

## Possible Product Shape

The first public version should probably be a pattern kit, not an app.

Possible repository shape:

```text
continuity/
  README.md
  AGENTS.md
  templates/
    briefings/
    entities/
    personal-context/
    transcripts/
  prompts/
    retrieval-discipline.md
    end-of-session.md
    consolidation-pass.md
  examples/
    personal-use/
    project-use/
```

The first user should be able to say to an AI:

> I want to use Continuity for this workspace. Read the Continuity instructions, create the folder structure if missing, and help me maintain a living context layer across chats, projects, and time.

Later versions might become a Codex skill, MCP server, local app, or provider-neutral protocol. That comes later. The first task is to get the pattern clear.

## Near-Term Work

First public-facing draft created 2026-05-08:

- `README.md` - public front door with the tagline "Stop starting over with your AI."
- `START-HERE.md` - nontechnical onboarding path
- `AI-SETUP-PROMPT.md` - pasteable prompt for any AI assistant
- `SPEC.md` - provider-neutral register model and implementation rules
- `templates/lite/CONTINUITY.md` - one-file starter
- `templates/standard/` - current context, preferences, decisions, open threads, evidence, session log
- `LICENSE`, `CITATION.cff`, and `NOTICE` - permissive use with preserved attribution
- `assets/` - first visual identity package for the GitHub landing surface
- `examples/personal-writer/CONTINUITY.md` - first Lite worked example

Protocol hardening landed 2026-05-08 after Opus 4.7 review:

- Continuity is framed as a shared context discipline the human owns, not only memory the AI uses.
- Status markers formalized: `[CONFIRMED]`, `[PROVISIONAL]`, `[INFERRED]`, `[ACTIVE]`, `[ARCHIVED]`, `[SUPERSEDED]`, `[STALE - REVIEW]`, `[UNVERIFIED]`.
- Staleness and decay rules added for current context, preferences, decisions, and open threads.
- Conflict hierarchy added: current-session human correction and evidence outrank summaries; confirmed active decisions outrank current context on resolved questions.
- Session log role narrowed to changes, file updates, evidence pointers, and uncaptured residue rather than a duplicate diary.
- AI behavioral contract added for start-of-session reading, contradiction handling, and end-of-session updates.

Dogfood testing on 2026-05-08 clarified the adoption surface:

- Cold-start Codex with file access worked well.
- Chat-only or limited-file environments need a manual fallback because they cannot reliably create folders or update files.
- User-facing session commands are now `Start continuity` and `Stop continuity`; the detailed behavior lives in the docs and templates rather than in long user prompts.
- Setup should ask only what is needed to create the first useful layer. Do not ask gating questions about willingness to maintain distinctions.

Next work:

1. Decide whether "Continuity" remains the final public name or only the working title.
2. Add project-mode templates without making the default setup too heavy.
3. Add examples for project use, Obsidian/wiki use, and managed-agent memory stores.
4. Decide whether the first GitHub repo should include a minimal release marker before publication.
5. Continue compatibility testing across file-access agents, project-file assistants, and browser-only chat tools.

## Current Positioning

Continuity can be described as:

- a living context system for human-AI relationships
- a continuity layer across chats, projects, and time
- context governance for human-AI communication
- a memory-placement system for whatever memory substrate someone already uses
- a way to stop starting over with your AI
- a shared working context for humans and AI

The public frame should stay simple:

**Continuity**  
*A living context system for keeping human-AI relationships alive and coherent across chats, projects, and time.*

**Stop starting over with your AI.**
