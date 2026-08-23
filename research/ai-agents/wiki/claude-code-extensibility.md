---
title: Claude Code Extensibility — Skills, Plugins, Hooks
tags: [claude-code, skills, plugins, hooks, ponytail]
source: query
source_type: query
created: 2026-08-23
updated: 2026-08-23 14:30
---

# Claude Code Extensibility — Skills, Plugins, Hooks

## Overview
How Claude Code's extensibility primitives — skills, hooks, and plugins —
relate to each other, using the `ponytail` plugin as a worked example.

## Key Points

### Skills
- On-demand: invoked per-task (e.g. `/ponytail-audit`), instructions load
  into that one turn, then it's over. Scoped to a single task.
- Often exposed as custom slash commands.

### Hooks
- Event-driven shell commands that fire on harness events (`SessionStart`,
  `PreToolUse`, etc.), configured in `settings.json`.
- A `SessionStart` hook can inject instructions/persona into context
  automatically at session start — this is how `ponytail`'s persistent mode
  activates without being explicitly invoked, and it stays active for every
  response until toggled off ("stop ponytail") or the session ends.

### Plugins
- A packaging mechanism, not a primitive itself. A plugin can bundle any
  combination of: skills/slash-commands, hooks, MCP server configs, and
  custom agents.
- Plugins ≠ hooks — a hook is just one optional component a plugin can ship.
  A plugin could skip hooks entirely and only ship skills, or only an MCP
  server.

### Worked example: ponytail
- Ships a `SessionStart` hook that auto-injects its "lazy senior developer"
  persona/ruleset every session — ambient, persistent, not invoked.
- Also ships standalone skills (`ponytail-review`, `ponytail-audit`,
  `ponytail-debt`, `ponytail-gain`, `ponytail-help`) for one-off checks,
  invoked the normal on-demand way.
- So the same plugin combines an always-on hook-driven mode with
  task-scoped skills — illustrating that plugins are a superset container,
  not synonymous with either primitive.

## Related
- None yet — first page in this topic covering harness extensibility
  mechanics specifically (vs. [[loop-engineering]]'s focus on agentic loop
  patterns).

## Open questions / gaps
- Not yet covered: MCP server bundling in plugins, custom agent bundling in
  plugins, plugin marketplace/distribution mechanics.
