---
name: handoff
description: "Write a session handoff doc to ~/continue where i left off.md so work can be resumed after a restart"
allowed-tools:
  - Read
  - Write
  - Bash
  - Glob
  - Grep
---

<objective>
Write (or overwrite) `~/continue where i left off.md` with a complete, accurate summary of the current session so the next Claude session can pick up immediately without re-explaining context.
</objective>

<process>
1. Review everything discussed and done in this conversation — what was the goal, what was attempted, what worked, what didn't, what decisions were made, what the current state is, and what needs to happen next.

2. If there are relevant files, configs, or credentials involved, include the exact values or paths so the next session doesn't have to rediscover them.

3. Write the file using this structure:

```
# [Topic] — Session Handoff

## What We Did
[Numbered list of completed actions with specifics — file paths, commands run, outcomes]

## Current State
[Honest snapshot: what's working, what's broken, what's pending]

## TODO After Restart
[Ordered list of next steps, most important first]

## Key Details
[Credentials, config snippets, paths, or anything the next session needs to not start from scratch]
```

4. Keep it factual and specific — no fluff. The next Claude session will read this cold.

5. Confirm to the user that the file has been written and where it is.
</process>
