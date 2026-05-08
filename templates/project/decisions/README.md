# Decisions

This folder holds individual decision entities — one file per significant decision — rather than a single rolling document.

Decisions are higher-authority than briefings, evidence summaries, or session notes. The decisions briefing in `briefings/` is the compressed view; the entity files here are the source.

## File naming

Use kebab-case, descriptive titles. Optionally prefix with the decision date for chronological ordering:

```text
2026-05-08-archive-renamed-to-continuity.md
no-co-authored-by-trailer.md
deploy-instruction-format.md
```

## Recommended structure

Each decision entity should carry, at minimum:

```markdown
---
type: decision
date: YYYY-MM-DD
status: active | confirmed | provisional | archived | superseded
scope: global | project-area | tool | other
supersedes:
superseded_by:
related:
  - sessions/...
  - decisions/...
---

# Decision Title

## The Decision

What was decided, in one or two sentences.

## What It Constrains

The behaviors, choices, or future decisions this rules out or rules in.

## Rationale

Why the decision was made. Brief. Detailed reasoning belongs in evidence records or transcripts.

## Briefing Guidance

- Tier 1 inclusion: yes / no / conditional
- Briefing form: one compact sentence suitable for the decisions briefing
- Retirement condition: when this should move out of Tier 1, if known
```

## Status field

Use the `status` field in frontmatter as the load-bearing status mechanism:

- **`active`** or **`confirmed`** — currently operative; flows into the decisions briefing.
- **`provisional`** — useful but not settled. Stays out of the decisions briefing until promoted. This is the safety rail that lets a consolidation pass run without supervision: it cannot reshape operating stances by inference alone.
- **`archived`** — preserved for history but not currently operative. Explains why something changed.
- **`superseded`** — replaced by a later decision. Note the replacement in `superseded_by`.

A consolidation pass may promote `provisional` to `confirmed` when a later session uses the entity without objection. If the logic is ambiguous, leave it provisional.

## Inline markers

Inline status markers from SPEC §9 (`[CONFIRMED]`, `[ACTIVE]`, `[CONFLICTS-WITH]`, etc.) are useful inside prose contexts where the YAML status field cannot carry the nuance — for example, calling out a partial supersession in body text. Use them where they add signal; the YAML field is the canonical record.

## What does **not** go here

- Session summaries (those go in `sessions/`)
- Evidence records (those go in `evidence/`)
- Open questions or watchpoints (those go in `open-threads.md` or `open-threads/`)
- Briefings (those are derived and live in `briefings/`)
- Provisional leanings or generative ideas (those go in `fragments/` until they harden into decisions)

## Supersession discipline

When a decision changes, do not silently erase the old entity. Mark its status `superseded`, set `superseded_by:` to the new entity's filename, and create a new entity for the replacement decision. The old entity stays in place as historical record.

If a decision is partially superseded — a piece of it falls away while the rest holds — the entity can stay `active` with a marker in the prose noting the partial change. Use judgment.
