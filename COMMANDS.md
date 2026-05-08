# Continuity Commands

Continuity has two everyday commands.

## Start continuity

Use this at the start of a session.

```text
Start continuity
```

When an AI assistant sees this command, it should:

1. Read the relevant Continuity files.
2. Use current context, active decisions, open threads, preferences, and evidence pointers as needed.
3. Flag stale, inferred, provisional, contradictory, archived, or superseded items before relying on them.
4. Keep the response brief unless the human asks for detail.

The AI does not need to recite every file it read. It should mention records used only when they materially affect the task.

If the AI does not know where the Continuity files are, it should ask for the folder or file location once. After that, it should keep using the same location unless the human changes it.

## Stop continuity

Use this at the end of a meaningful session.

```text
Stop continuity
```

When an AI assistant sees this command, it should:

1. Update only the Continuity records that changed.
2. Keep current context short.
3. Record decisions, open threads, preference updates, evidence pointers, and session notes in the right places.
4. Use status markers when ambiguity matters.
5. Avoid turning temporary states into permanent identity claims.
6. Keep the session log focused on what changed and what was updated elsewhere.

## Important

These commands work best when the AI assistant has access to the Continuity files.

If the AI cannot read or write local files, it should say so and offer a manual fallback: draft the files or updates in chat for the human to copy into place.

On a phone, tablet, or browser chat, `Start continuity` may require the human to paste or upload the Continuity file first. `Stop continuity` may mean the AI drafts an update block rather than editing the file directly.
