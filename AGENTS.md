<!-- project-context-logger:managed:start schema=1 sha256=7cede3fbf8cf5b5fdf0d97fcbdfe2d2c68c2aa08d75abc05613788819c68ca74 -->
## Handoff Plugin Engineer

Purpose: A Claude Code plugin that writes a session handoff doc to '~/continue where i left off.md' so work can be resumed after a restart, in a new context, or by a Dispatch-spawned Desktop session.

### Operating contract

- Treat repository files as the source of truth for current implementation; Context Logger stores history, reasoning, and handoff state.
- Treat `Hi, Jarvis`—and the `Hey, Jarvis` or `Hello, Jarvis` variants—as an explicit visible catch-up request, regardless of capitalization or punctuation. Greet briefly, then use the already-injected `PROJECT CONTEXT LOGGER — HISTORICAL BRIEF` when available; otherwise run `.ai/context-logger/run brief --max-chars 4200`. Summarize current state, recent meaningful work, active issues, and the next likely step in concise bullets. Include a past decision or failed approach only when it affects what to do next. Never initialize a Context Logger session for catch-up alone, and never invent the user's name; use it only when a reliable stored preference provides it.
- At the start of meaningful work, use the injected `PROJECT CONTEXT LOGGER — HISTORICAL BRIEF` when present; otherwise run `.ai/context-logger/run brief --max-chars 4200`. Reconcile memory against the repository.
- When code does not explain why it exists, run `.ai/context-logger/run search --query "<topic>" --limit 8` before repeating an old approach.
- Start a Context Logger session only for distinct, substantial work: `.ai/context-logger/run init --user-context "<goal>" --session-title "<title>"`.
- Record architecture decisions, root causes, constraints, direction changes, meaningful implementation milestones, and failed approaches worth remembering.
- Do not log formatting, typo fixes, routine command output, every file touched, or other facts obvious from the repository.
- Before ending substantial work, record a handoff with `.ai/context-logger/run checkpoint --summary "<done>" --current-state "<state>" --next-step "<next>"` plus issues, failures, and verification when relevant.
- The primary agent owns Context Logger writes. Spawned specialists return durable findings to the primary instead of writing memory concurrently.
- Review this generated setup with `.ai/context-logger/run agent update --dry-run`; apply only conflict-free changes.

### Stable project signals

- Stack: Inspect repository evidence before choosing tools
- Important areas: `.claude-plugin/`, `.skillshare/`, `skills/`
- Discover and use the repository's own validation commands before changing behavior.
<!-- project-context-logger:managed:end -->

# claude-handoff-plugin

