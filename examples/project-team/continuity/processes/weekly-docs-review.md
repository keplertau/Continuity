# Weekly Docs Review

- **Type:** Process
- **Status:** active
- **Cadence:** weekly
- **Owner:** shared
- **Trigger:** Friday review until v1.0 launch
- **Created:** 2026-05-11

---

## What It Does

Checks whether launch documentation still matches confirmed decisions and whether open risks need action before publication.

## Steps

1. Read `briefings/current-state.md`, `briefings/decisions.md`, and `roadmap.md`.
2. Check Quickstart, Concepts, and Maintainer Guide against the docs-first launch decision.
3. Check public roadmap copy against the public-roadmap limits decision.
4. Review `open-threads.md` for launch risks.
5. Record findings in a session entity.
6. Update current context, roadmap, open threads, or decision entities only where the review changes them.

## Inputs

- Current docs draft.
- `decisions/`
- `open-threads.md`
- `roadmap.md`

## Outputs

- Session entity for the review.
- Updated open threads or roadmap if risk changed.

## Failure Modes

- Treating the review as a rewrite session and expanding scope.
- Publishing dates without an owner.
- Skipping accessibility risk because it feels like polish.

## Change History

- 2026-05-11 - created after docs navigation review.
