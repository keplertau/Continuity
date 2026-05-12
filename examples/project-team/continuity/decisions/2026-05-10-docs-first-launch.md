---
type: decision
date: 2026-05-10
status: confirmed
scope: project
supersedes:
superseded_by:
related:
  - sessions/2026-05-10-launch-scope.md
  - evidence/transcripts/2026/05/2026-05-10-launch-scope.md
---

# Docs-First v1.0 Launch

## The Decision

v1.0 launch work is docs-first. Quickstart, Concepts, and Maintainer Guide must be shippable before the team adds new public feature promises or expands example scope.

## What It Constrains

- Public copy should not promise examples that rely on unreleased features.
- The launch note should wait until the core docs are reviewed.
- Roadmap items may mention post-v1 ideas, but they must not blur into launch commitments.

## Rationale

Early testers are failing before their first successful run. The highest-leverage launch improvement is not a broader feature story; it is a clearer path from installation to visible success.

## Evidence

- `evidence/transcripts/2026/05/2026-05-10-launch-scope.md`

## Briefing Guidance

- Tier 1 inclusion: yes.
- Briefing form: v1.0 launch is docs-first; Quickstart, Concepts, and Maintainer Guide outrank new feature promises.
- Retirement condition: after v1.0 ships and the launch constraint is replaced by a post-launch docs strategy.
