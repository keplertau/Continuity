# AI Setup Prompt

Use this prompt when you want an AI assistant to set up Continuity for you.

You can paste the whole prompt into a chat, or point your AI assistant at this file.

```text
I want to use Continuity.

Continuity is an open-source context system for keeping human-AI work coherent across chats, projects, tools, and time. Its tagline is: Stop starting over with your AI.

Your task is to help me set up the simplest useful continuity layer for my situation.

Core goal:
Help future AI sessions remember the right things in the right way, using whatever memory or storage setup I already have. Treat Continuity as a shared context discipline the human owns, not only as memory the AI uses.

Hard constraints:
- Start with the smallest useful setup.
- Keep this accessible to a nontechnical person.
- Do not require a database, server, plugin, command-line workflow, or paid platform unless I explicitly ask for that.
- If you cannot create or edit files, say so clearly and offer a manual fallback.
- Do not import everything. Place memory carefully.
- Do not treat your own inference as confirmed fact.
- Do not turn passing moods, temporary preferences, or old self-descriptions into permanent identity claims.
- Preserve unresolved questions instead of smoothing them away.
- Keep important claims connected to evidence when possible.
- Flag contradictions between files instead of silently choosing a side.

Default preferences:
- Use plain markdown files unless my existing system clearly calls for another format.
- Work with the tools I already use: folders, GitHub, Obsidian, a wiki, project files, chat history, Claude Projects, managed agent memory stores, or something else.
- Reuse the templates in this repository when available.
- Ask only the questions you need beyond the required setup questions below.

First, check whether this environment lets you create and edit files.

Then ask only these required setup questions:
1. Ask me what this continuity layer is for: personal use, a project, a team, research, writing, software, ordinary life, or something else.
2. Ask where you can create or update the Continuity files.

If the answer is obvious from the environment, proceed without asking.

If you do not have file access:
- Say that automatic setup will not work in this chat.
- Offer to create the Lite `CONTINUITY.md` content in the chat for me to copy manually.
- Do not pretend you created files.
- Do not ask for more setup detail than you need to produce that Lite file.

Then recommend one of these setup levels:

Lite:
- One file called CONTINUITY.md.
- Best for personal use, simple contexts, or a first experiment.

Standard:
- A small continuity folder:
  continuity/current.md
  continuity/preferences.md
  continuity/decisions.md
  continuity/open-threads.md
  continuity/evidence.md
  continuity/session-log.md
- Best for ongoing projects, writing, research, serious personal planning, or repeated AI work.

Project:
- A more structured system with briefings, decision records, session notes, evidence, and process files.
- Best for long-running workspaces, teams, agents, or high-stakes projects.
- Do not choose Project unless the extra structure is actually useful.

Default choice:
- If I am unsure, start with Lite.
- If there is already an ongoing project, start with Standard.
- If the project already has many decisions, evidence files, and recurring processes, suggest Project but do not force it.
- If Lite grows beyond roughly 1,500 words or covers several unrelated domains, propose Standard.

Memory placement rules:

Use these status markers when ambiguity matters:
- [CONFIRMED YYYY-MM-DD]
- [PROVISIONAL YYYY-MM-DD]
- [INFERRED YYYY-MM-DD]
- [ACTIVE YYYY-MM-DD]
- [ARCHIVED YYYY-MM-DD]
- [SUPERSEDED YYYY-MM-DD]
- [STALE - REVIEW]
- [UNVERIFIED]

Current context:
- Keep short.
- Include what matters now.
- Remove or revise when it stops being current.
- Review at session start.

Preferences:
- Include stable working preferences, communication preferences, boundaries, recurring needs, and project conventions.
- Mark inferred preferences as [INFERRED YYYY-MM-DD] until I confirm them.
- Keep identity claims reviewable.
- Add a last-reviewed date for preferences that may shape future behavior.
- If an old preference may be stale, mark it [STALE - REVIEW] instead of relying on it strongly.

Decisions:
- Record date, decision, rationale, and what it constrains.
- Distinguish confirmed decisions from provisional leanings.
- Do not re-litigate confirmed decisions unless new evidence appears.
- Mark decisions [ACTIVE YYYY-MM-DD], [ARCHIVED YYYY-MM-DD], or [SUPERSEDED YYYY-MM-DD] when their current status matters.

Open threads:
- Preserve unresolved questions, tensions, hypotheses, risks, and watchpoints.
- Do not collapse open tensions into fake certainty.
- Make it easy to resume thinking later.
- If an open thread resolves, move the result into decisions or current context and mark the thread resolved.

Evidence:
- Point to transcripts, notes, links, documents, files, citations, or source material.
- A summary is not the same as evidence.
- If evidence is missing or uncertain, say so.

Session log:
- Record meaningful changes after a session.
- Do not record every small exchange.
- Capture what changed, what files were updated, what was not captured elsewhere, evidence pointers, and what should happen next.
- Do not duplicate every item from current context, decisions, and open threads.

Conflict rules:
- Human correction in the current session outranks stored memory.
- Direct evidence outranks summaries.
- Confirmed decisions outrank current context when they address the same question.
- Active decisions outrank open threads on resolved questions.
- If files conflict, flag the conflict instead of choosing silently.

When creating files, include simple headings and short instructions inside each file so future AI assistants know how to use them.

After setup, give me:
1. A short explanation of what you created.
2. The start command: `Start continuity`.
3. The end command: `Stop continuity`.
4. Any open questions that should be resolved later.

Do not overbuild. The first version only needs to make the next conversation better than the last one.
```

## Start-Of-Session Command

Use this at the start of a future chat:

```text
Start continuity
```

## End-Of-Session Command

Use this after a meaningful chat:

```text
Stop continuity
```

The detailed command behavior lives in [`COMMANDS.md`](COMMANDS.md).
