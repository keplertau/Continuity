# Processes

This folder holds recurring workflows, cadences, triggers, and standing maintenance rules.

Process records describe what runs and when. They are not commands; they are the durable record of a project's standing operations. A future session should be able to read this folder and answer: what runs continuously, what runs per-session, what runs on a schedule, what fires on an event, and what is named-but-not-built.

## What belongs here

- **End-of-session routines** — what should always happen at the close of a meaningful session.
- **Review cadences** — periodic audits of decisions, preferences, briefings, or evidence.
- **Update triggers** — "if X happens, run Y" rules.
- **Backup and consolidation rules** — including any Sleep-Cycle Distillation pass (SPEC §14.1) the project uses.
- **Recurring maintenance** — merge/prune cadences, link audits, link-rot checks, dependency reviews.
- **Standing audits** — quality, compliance, governance, or domain-specific audit cycles.

## What does **not** belong here

- One-off tasks (those go in `roadmap.md` or as session next-steps in `current.md`)
- Active decisions (those go in `decisions/`)
- Process *records* of past runs (those go in session entities or in a dedicated log under `evidence/`)
- Briefings about which processes are active (a process briefing is derived from these files; it lives in `briefings/`)

## File shape

Each process gets its own file. Recommended structure:

```markdown
# Process Name

- **Type:** Process
- **Status:** active | paused | retired
- **Cadence:** continuous | per-session | nightly | weekly | monthly | quarterly | event-driven
- **Owner:** human | AI tool | shared
- **Trigger:** what causes the process to run
- **Created:** YYYY-MM-DD

---

## What It Does

One paragraph describing the process's purpose and outcome.

## Steps

Numbered steps the process follows. Detailed enough that the next runner can execute without reconstructing the procedure from memory.

## Inputs

What the process reads.

## Outputs

What the process produces or modifies.

## Failure Modes

What can go wrong, and how to detect it.

## Change History

- YYYY-MM-DD — created / revised / paused / retired with reason
```

## Naming

Use kebab-case names that describe the process, not its current state:

```text
end-of-session-protocol.md
nightly-consolidation-pass.md
monthly-content-audit.md
deploy-procedure.md
```

## Status discipline

A process exists in this folder only if it is real. If a process is named-but-not-built, mark it `status: paused` or move it to `roadmap.md` until it actually runs. The folder should not accumulate aspirational processes.

When a process is retired, mark it `status: retired` rather than deleting the file. The history of what used to run is sometimes load-bearing.
