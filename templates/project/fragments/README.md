# Fragments

This folder is **optional** in Project mode. Use it if your project produces enough generative material that it benefits from a dedicated low-authority register. Skip it if not — fragments are not load-bearing.

## What belongs here

- Meaningful insights surfaced in a conversation that don't yet have a permanent home
- Paragraphs cut from a draft that may be reused
- Candidate concepts not yet developed enough for a concept entity or decision
- Generative material from thinking sessions
- Ideas waiting for their right context

## What fragments are **not**

- **Decisions.** Provisional leanings live as `status: provisional` decision entities in `decisions/`, not here. A fragment is orphan content; a provisional decision is a settled-enough leaning to record as a candidate decision.
- **Open threads.** Open threads are unresolved questions, tensions, or watchpoints — things that may need to be resolved. Fragments are orphan content without a question attached. An open thread that decays unread is drift to detect; a fragment that decays unused is fine.
- **Evidence.** Fragments are generative; they don't support claims by pointing back to sources.

## Authority

**Low.** Fragments are candidates, not commitments. They should not steer future behavior unless they graduate into another register — typically by being absorbed into a decision, a concept, a published artifact, or a section of current context.

## Decay rule

Fragments are allowed to age. A fragment that is never reused is a normal outcome, not drift. Periodic merge/prune passes (SPEC §11.8) may consolidate or prune the register.

## File shape

Each fragment is a small file. There is no required template — the looseness is the point. A reasonable starter:

```markdown
# Fragment title or first line

- **Created:** YYYY-MM-DD
- **Source:** brief context or transcript pointer

---

The fragment itself. A paragraph, an insight, a draft passage — whatever was worth saving.

## Why I kept it

Optional. One sentence on what makes this worth preserving.
```

## Failure modes

- Fragments become a dumping ground large enough that nothing can be found. Periodic pruning is the cure.
- Fragments are mistaken for decisions or settled positions because they read as polished prose. Keep them visibly separate from `decisions/` and `current.md`.

## Promotion

When a fragment finds its home — a decision absorbs it, a section of a published artifact uses it, a concept entity is authored from it — move it out of `fragments/` rather than leaving a duplicate. A fragment that has graduated is not a fragment anymore.
