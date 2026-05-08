# Evidence

This folder holds the source records that support or correct the summaries elsewhere in the continuity layer: transcripts, source documents, links, citations, fidelity-labelled extracts.

Evidence is the highest-authority register when exact wording, sequence, or attribution matters. Summaries — including session entities and briefings — outrank inferred or speculative claims, but they do not outrank the evidence that produced them.

## Subfolder shape

A common organization:

```text
evidence/
  transcripts/
    YYYY/
      MM/
        YYYY-MM-DD-session-slug.md
  sources/        # original migrated material that pre-dates the system
  documents/      # external documents, PDFs, attachments
  links.md        # external URLs cited in the project
```

Adapt the layout to the substrate. The discipline is what matters.

## Fidelity discipline (SPEC §7.5)

Every transcript and any record produced by an extraction step should declare its fidelity in the header:

```markdown
# Session Title

- **Session ID:** <id>
- **Extracted:** YYYY-MM-DD
- **Extraction fidelity:** full verbatim | partial | compressed

---

<transcript content, with [role] prefixes preserved>
```

If the record is `partial` or `compressed`, include a short note immediately under the header naming what is missing or summarized and why. The same note should appear in the consolidation log that produced the file.

## Hard rule

A summary file may live alongside an evidence record and point to it, but **a summary must not be substituted for the evidence record or relabeled as verbatim.** When a claim depends on exact wording, sequence, or attribution, future AI sessions should read the evidence record itself and check its fidelity header before treating the content as load-bearing.

## What goes here

- Session transcripts (verbatim where possible)
- Source documents the project relies on
- External documents, PDFs, attachments
- Links and citations
- Notes from research or interviews
- Anything that supports a load-bearing claim and would lose its weight if compressed into a summary

## What does **not** go here

- Session summaries (those are entities in `sessions/`)
- Decision entities (those are in `decisions/`)
- Briefings (those are derived files in `briefings/`)
- Bulky historical material that no longer steers current claims (that goes in `archive/`)

## Pruning

Evidence accumulates. Periodic merge/prune passes (SPEC §11.8) may move older or no-longer-load-bearing records to `archive/`. Do not delete evidence that supports an active decision or claim without first preserving a pointer.
