# Changelog

All notable changes to Continuity are documented here.

Continuity uses Git tags such as `v0.1.0` for public release points. Template, prompt, and specification changes should be noted here so generated setups can be traced back to the version they came from.

## [Unreleased]

### Added

- **`examples/project-team/`.** Populated Project-mode worked example for a fictional open-source documentation team. The example shows hot/warm/cold loading, derived briefings, individual decision entities, session summaries, fidelity-labelled evidence records, process files, open threads, a roadmap, and a low-authority fragment in use together.

### Changed

- **README.md.** Worked example section now points to both the Lite personal-writer example and the Project-mode project-team example.
- **AGENTS.md.** Removed the Project-mode worked example from the next-work list now that it exists.

## [0.2.1] - 2026-05-08

Project-mode template, consolidation-pass prompt, and small README/AGENTS edits to align the public surfaces with v0.2.0 SPEC additions. No SPEC changes.

### Added

- **`templates/project/`.** Full Project-mode starter mirroring SPEC §6.3's folder layout: `index.md`, `current.md`, `roadmap.md`, `open-threads.md`, plus `briefings/`, `decisions/`, `sessions/`, `evidence/`, `archive/`, `processes/`, and `fragments/` each with a substantive `README.md` that encodes the operating logic from §6.3 and §14.1. The template reads as an executable form of the spec — populating it gives an AI assistant or human enough scaffolding to run a Project-mode workspace without parsing the prose first.
- **`prompts/consolidation-pass.md`.** New pasteable prompt implementing the Sleep-Cycle Distillation recipe from SPEC §14.1. Substrate-neutral and schedule-agnostic: documents the five phases (extract, distill, graduate, promote, log) as a recipe, with adaptation notes for non-markdown substrates, lighter setup levels, and varying cadences. Conservative on automation — frames manual end-of-session use as the baseline; scheduled or agent-driven execution is named as a richer implementation.

### Changed

- **README.md.** Setup Levels Project description expanded to name the full v0.2.0 §6.3 register set (briefings, decisions, sessions, evidence, processes, fragments, open threads, roadmap), and points readers to SPEC §6.3 and §14.1 for the operating logic. Earlier wording elided fragments and roadmap.
- **AGENTS.md.** Added generative context (fragments) to the "Registers, Not One Memory Bucket" section so the cognitive-register list matches SPEC §7. Updated the "Possible Product Shape" sketch to reflect what's actually built (`templates/lite/`, `templates/standard/`, `templates/project/`, `prompts/consolidation-pass.md`). Pruned resolved items from "Next work" — the project name is locked, the v0.1.0 release-marker question is settled by actual releases — and added the worked-example follow-up, additional-substrate examples, and optional retrieval-discipline / end-of-session prompts as forward-looking items.

### Provenance Bumps

- `templates/lite/CONTINUITY.md`, `templates/standard/index.md`, `templates/standard/current.md`, and `examples/personal-writer/CONTINUITY.md` provenance lines bumped from `0.2.0` to `0.2.1`. Generated setups created under v0.2.1 should record `0.2.1` rather than `0.2.0`.

## [0.2.0] - 2026-05-08

Cross-pollination release. Incorporates lessons from a live working-memory implementation that has run in continuous use for several weeks. Six SPEC additions, plus the unreleased changes that had accumulated since v0.1.0.

### Added

- **Cognitive register framing in §7.** Introductory paragraph mapping the operational registers (current context, preferences, decisions, open threads, evidence, session log, archive, process context, briefings, fragments) to the cognitive functions they support: working awareness, normative memory, commitment memory, open-tension memory, evidence memory, episodic memory, process memory, and generative memory. Explains why the register separation isn't arbitrary.
- **Fragments register (§7.10).** A new low-authority register for orphan ideas, paragraphs, or insights worth preserving but not yet placed elsewhere. Distinct from open threads: open threads are unresolved questions; fragments are orphan content. Optional in Lite and Standard, more useful in Project mode.
- **Project-mode operating logic (§6.3).** Replaces the bare folder layout with operating logic: how briefings get derived from entities, how session entities relate to transcripts, how decisions accumulate as individual files with status, when to auto-graduate, when to promote provisional → confirmed, what indexing role `index.md` plays, how the roadmap stays forward-looking.
- **Sleep-Cycle Distillation recipe (§14.1).** Promotes the consolidation pattern (extract → distill → graduate → promote → log) into a named Project-mode recipe, validated in live use. The recipe is portable across substrates: it can run on a schedule, at session end manually, or through an AI memory process. Includes the safety rail that provisional decisions cannot flow into the decisions briefing until promoted.
- **Plug-and-Play Evolution Points (§15).** New section naming the seams where implementations can evolve as AI tools improve: retrieval layer, distillation engine, graph layer, storage and synchronization. Reads the architecture as designed-for-upgrade rather than as permanent.

### Changed

- **§7.5 Evidence tightened with fidelity discipline.** Adds an explicit extraction-fidelity header convention (`full verbatim | partial | compressed`), partial-extraction labeling rules, and the rule that summaries cannot be substituted for evidence records or relabeled as verbatim.
- **§7 introduction.** Now opens with the cognitive-function framing before listing the operational registers.
- **§6.3 Project mode.** Folder layout adds `fragments/`. New operating-logic section follows the layout.
- **§14 Consolidation Rules.** Broad rules retained; new §14.1 names the Sleep-Cycle Distillation recipe.

### Renumbered

- Sections after §14 shifted by one to accommodate the new §15 (Plug-And-Play Evolution Points): Versioning is now §16, Interoperability §17, Minimum Compatibility §18, AI Assistant Responsibilities §19, Human Responsibilities §20, Version Notes §21.

### Also rolled in from the post-v0.1.0 unreleased work

- Replaced the original illustrative raster logo with a cleaner vector mark and regenerated the 512 x 512 PNG export.
- Added lightweight maintenance conventions for review markers, conflict pointers, graduated context loading, session handoff notes, merge/prune cleanup, multi-agent edit metadata, and human-findable install locations.
- Added an archive convention for full sessions, older documents, retired drafts, and bulky reference material.

## [0.1.0] - 2026-05-08

First public pattern-kit baseline.

### Added

- Public README with the tagline "Stop starting over with your AI."
- Lite and Standard markdown templates.
- Provider-neutral specification for registers, authority, status markers, conflict rules, update rules, retrieval discipline, and consolidation.
- AI setup prompt for creating the smallest useful Continuity layer.
- `Start continuity` and `Stop continuity` command interface.
- Compatibility guidance for file-access tools, browser chat, partial project-file environments, and mobile use.
- Citation and attribution files.
- Visual identity assets and README section visuals.

### Template Notes

- Lite setup starts from one `CONTINUITY.md` file.
- Standard setup starts from a small `continuity/` folder with an index, current context, preferences, decisions, open threads, evidence, and session log files.
- Generated setups should record the Continuity version and source commit when available.

### Spec Notes

- The first release defines Continuity as a shared context discipline the human owns, not only memory the AI uses.
- The first release formalizes status markers, staleness rules, conflict hierarchy, and the AI behavioral contract.
