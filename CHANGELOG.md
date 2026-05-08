# Changelog

All notable changes to Continuity are documented here.

Continuity uses Git tags such as `v0.1.0` for public release points. Template, prompt, and specification changes should be noted here so generated setups can be traced back to the version they came from.

## [Unreleased]

- No unreleased changes yet.

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
- Standard setup starts from a small `continuity/` folder with current context, preferences, decisions, open threads, evidence, and session log files.
- Generated setups should record the Continuity version and source commit when available.

### Spec Notes

- The first release defines Continuity as a shared context discipline the human owns, not only memory the AI uses.
- The first release formalizes status markers, staleness rules, conflict hierarchy, and the AI behavioral contract.
