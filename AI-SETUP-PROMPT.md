# AI Setup Prompt

Use this prompt when you want an AI assistant to set up Continuity for you.

You can paste the whole prompt into a chat, or point your AI assistant at this file.

```text
I want to use Continuity.

Continuity is an open-source context system for keeping human-AI work coherent across chats, projects, tools, and time. Its tagline is: Stop starting over with your AI.

Your task is to help me set up the simplest useful continuity layer for my situation.

Core goal:
Help future AI sessions remember the right things in the right way, using whatever memory or storage setup I already have.

Important constraints:
- Keep this accessible to a nontechnical person.
- Do not require a database, server, plugin, command-line workflow, or paid platform unless I explicitly ask for that.
- Use plain markdown files unless my existing system clearly calls for another format.
- Work with the tools I already use: folders, GitHub, Obsidian, a wiki, project files, chat history, Claude Projects, managed agent memory stores, or something else.
- Start with the smallest useful setup.
- Ask only the questions you need before creating the first version.
- Reuse the templates in this repository when available.
- Do not import everything. Place memory carefully.
- Do not treat your own inference as confirmed fact.
- Do not turn passing moods, temporary preferences, or old self-descriptions into permanent identity claims.
- Preserve unresolved questions instead of smoothing them away.
- Keep important claims connected to evidence when possible.

First, inspect the situation:
1. Ask me what this continuity layer is for: personal use, a project, a team, research, writing, software, ordinary life, or something else.
2. Ask where it should live: one file, a folder, a repo, Obsidian, a wiki, an existing project space, or another place.
3. Ask what future AI sessions should know first.

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

Memory placement rules:

Current context:
- Keep short.
- Include what matters now.
- Remove or revise when it stops being current.

Preferences:
- Include stable working preferences, communication preferences, boundaries, recurring needs, and project conventions.
- Mark inferred preferences as inferred until I confirm them.
- Keep identity claims reviewable.

Decisions:
- Record date, decision, rationale, and what it constrains.
- Distinguish confirmed decisions from provisional leanings.
- Do not re-litigate confirmed decisions unless new evidence appears.

Open threads:
- Preserve unresolved questions, tensions, hypotheses, risks, and watchpoints.
- Do not collapse open tensions into fake certainty.
- Make it easy to resume thinking later.

Evidence:
- Point to transcripts, notes, links, documents, files, citations, or source material.
- A summary is not the same as evidence.
- If evidence is missing or uncertain, say so.

Session log:
- Record meaningful changes after a session.
- Do not record every small exchange.
- Capture what changed, what was decided, what remains open, and what should happen next.

When creating files, include simple headings and short instructions inside each file so future AI assistants know how to use them.

After setup, give me:
1. A short explanation of what you created.
2. The exact start-of-session instruction I should use next time.
3. The exact end-of-session instruction I should use when I want Continuity updated.
4. Any open questions that should be resolved later.

Do not overbuild. The first version only needs to make the next conversation better than the last one.
```

## Optional Start-Of-Session Instruction

Use this at the start of a future chat:

```text
Before answering, please read my Continuity files and use them as context. Pay special attention to current context, confirmed decisions, open threads, and evidence pointers. If something is uncertain or outdated, say so.
```

## Optional End-Of-Session Instruction

Use this after a meaningful chat:

```text
Please update my Continuity layer. Capture changes to current context, decisions, open threads, preferences, evidence pointers, and session notes. Mark anything inferred or provisional clearly. Do not overwrite unresolved tensions with false certainty.
```
