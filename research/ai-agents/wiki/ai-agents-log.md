<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-08-05 15:25] new-topic | AI Agents
Scaffolded new research topic to hold content on AI agent orchestration patterns.

## [2026-08-05 15:25] ingest | What is "loop engineering?" (Gergely Orosz, Pragmatic Engineer)
Created loop-engineering.md — covers the Ralph Wiggum loop origin, /goal command rollout across Codex/Hermes/Claude Code, and dev-reported use cases (triggers, cron jobs, migrations). First page in this topic.

## [2026-08-08 17:55] lint | apply updated Key Points template (### sub-headers)
Reformatted loop-engineering.md's Key Points into `###` sub-headers (Background & origin, /goal rollout, how devs use loops, concrete dev examples), per the templates/page.md update allowing thematic sub-headers when points cluster 3+ per theme.

## [2026-08-08 18:07] lint | fix loop-engineering.md section order
`## Open questions / gaps` was placed before `## Related`; templates/page.md orders Related before Open questions/gaps. Swapped to match.

## [2026-08-08 18:17] lint | fold loop-engineering.md Details into Key Points
templates/page.md now allows a Key Points bullet to run a few sentences for a single mechanism, reserving Details for content needing multiple steps/facts. loop-engineering.md's one-sentence Details synthesis fit that bar — moved into Key Points as a "Throughline" bullet and deleted the now-empty Details section.

## [2026-08-23 14:30] ingest | Claude Code extensibility: skills vs. plugins vs. hooks (conversation)
Created claude-code-extensibility.md — distinguishes on-demand skills, event-driven hooks (e.g. SessionStart), and plugins as a bundling mechanism for both plus MCP/agents, using the ponytail plugin as a worked example. First page in this topic on harness extensibility mechanics.
