# handoff

A Claude Code plugin that writes a session handoff doc to `~/continue where i left off.md` so work can be resumed after a restart, in a new context, or by a Dispatch-spawned Desktop session.

## Install

From a local path (development):
```
/plugin install /Users/samanthashiro/projects/claude-handoff-plugin
```

From git (after pushing to GitHub):
```
/plugin install https://github.com/sammori77/claude-handoff-plugin
```

## Use

In any Claude Code session (CLI, Desktop, or Dispatch-spawned Desktop):
```
/handoff
```

Claude reviews the conversation and writes a structured handoff document to `~/continue where i left off.md` covering what was done, current state, TODO, and key details.

Pair with the `resume` skill (or just `/resume` if you have it as a plugin too) to pick up cleanly in the next session.
