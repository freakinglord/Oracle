---
title: Loop Engineering
tags: [ai-agents, claude-code, codex, agentic-workflows, automation]
source: https://newsletter.pragmaticengineer.com/p/what-is-loop-engineering
source_type: url
created: 2026-08-05
updated: 2026-08-23 16:03
---

# Loop Engineering

## Overview
"Loop engineering" is the practice of designing automated systems that
repeatedly prompt an AI coding agent toward a goal, rather than a human
crafting each prompt by hand. Term gained traction in mid-2026 after Boris
Cherny (Claude Code creator) and Peter Steinberger (OpenClaw creator) said
they now spend their time "writing loops" instead of prompts. Source:
Gergely Orosz, "What is 'loop engineering'?", The Pragmatic Engineer
newsletter, 2026-07-15.

## Key Points

### Background & origin
- **Origin — "Ralph Wiggum" loop**: coined by Geoffrey Huntley a year prior
  (mid-2025), named after the naive-but-persistent Simpsons character. In
  its purest form: `while:; do cat PROMPT.md | claude-code; done`. Huntley
  called it "deterministically bad in a nondeterministic world" and
  stressed senior engineering skill is still required to guide it.
- Ralph's structure: give the agent a goal + a plan with success criteria
  per item; loop one plan item at a time; start each iteration with a
  fresh/clean context window to avoid "context rot"; let the agent revise
  the plan and spawn subagents as needed.
- The technique exists to work around context-window limits (~200K tokens
  as of mid-2025) — too small for ambitious tasks, so work is chunked
  across fresh agent runs with state persisted externally (logs, an
  updated plan file) rather than kept in one long context.
- **Matt Pocock's "dynamic Kanban" variant**: instead of a fixed upfront
  plan, the agent's loop prompt is: (1) pick the highest-priority feature,
  (2) run tests, (3) update the master PRD/tracker, (4) log progress to
  `progress.txt`, (5) commit. The plan itself stays continuously editable
  rather than fixed, unlike the original two-step (plan-then-execute)
  approach.

### `/goal` command shipped across major harnesses in rapid succession
- **April 2026** — OpenAI Codex ships "Goals": a durable target
  ("keep working until this outcome is true") vs. a normal prompt
  ("do this next thing"). After each turn Codex checks whether the goal
  condition holds against current evidence, and continues if not (within
  budget).
- **May 2, 2026** — Hermes agent ships its own `/goal`, explicitly
  crediting Codex's `/goal` (by Eric Traut, OpenAI) as direct inspiration.
- **May 12, 2026** — Claude Code ships `/goal`: sets a completion
  condition, and "a small fast model" checks after each turn whether the
  condition holds; if not, Claude keeps going instead of returning
  control. Clears automatically once satisfied.
- Claude Code had already shipped `/loop` in March 2026 — simpler
  scheduled/repeated-prompt execution (analogous to `setTimeout`), distinct
  from the goal-seeking `/goal`.
- Open-source harnesses (OpenCode, Pi) added `/goal` via plugins rather
  than native support.

### How devs actually use loops
From ~210 crowdsourced replies on X/LinkedIn — dominated by two patterns
that predate AI:
- **Triggers/automations**: agent kicks off on an event (error logged,
  ticket created, feedback received) — conceptually the AI-era version of
  a webhook.
- **Cron jobs**: agent runs on a fixed schedule — functionally identical
  to traditional cron.
- Skeptical take from engineering director Oded Messer: a workflow
  repeatable/automatable enough to loop either (a) becomes plain
  tactical automation (cron/trigger) if repeatable, or (b) requires AI so
  capable that calling it "loop engineering" oversells what is really
  execution, not strategy.
- **Throughline**: loop engineering isn't a new primitive so much as
  applying old automation patterns (webhooks/triggers, cron) with an LLM
  agent as the worker instead of a fixed script — the design effort shifts
  to defining the completion condition, state persistence (logs, plan/PRD
  files), and escalation path when the agent gets stuck.

### Concrete dev examples cited
- Auto-open a PR when a new Sentry issue appears; only one PR open at a
  time; Slack-ping devs if a PR sits unreviewed (Ivan Pantić).
- Pull the next flaky test from a trunk API, reproduce locally, open a
  fix PR — netted 13 PRs to stabilize tests (Paul D'Ambra, PostHog).
- Triage new alerts/incidents/customer tickets before a human even joins
  the Slack channel — investigate, implement fix if it's a code issue,
  open PR, ping for review (Ivan Abad).
- Loop a design/implementation-plan review until the agent finds "0 new
  major issues" on a run, since a single pass only surfaces a few issues
  (Artem Nikitin, Elastic).
- Daily loop reading last-24h logs + user feedback to produce PRs with
  fixes, still human-reviewed (Jack D, Schematic).
- Nightly e2e test babysitting: on failure, agent investigates
  real-regression vs. flake, attempts a fix, reruns, iterates until pass
  or hits a retry cap and escalates — lands as a morning PR (Utku K).
- Building/verifying new telemetry integrations by looping
  execute-query → verify correctness → iterate on query plan/output
  format (Lawrence Jones, Incident.io).
- Full React → React Native/Expo migration done via a cron-scheduled
  "skill" (runs every 30 min) that finds a small/medium chunk of code to
  convert and tracks migration progress — chosen over a traditional
  50-100 ticket epic plan, which felt like too much upfront
  infrastructure to build (Rafel Mendiola, startup founder).

## Related
- [[claude-code-extensibility]] — extensibility primitives (skills, hooks,
  plugins) vs. this page's focus on agentic loop patterns.
- [[opencode-vs-cline-vs-claude-code]] — Claude Code's `/loop`/`/goal`
  commands discussed here are part of its differentiation vs. other
  harnesses on that page.

## Open questions / gaps
- The source article is paywalled beyond section 4. Not yet captured:
  section 5 (disappointment/"tokenmaxxing" — devs rejecting loops after
  agent drift or cost blowup at API pricing), section 6 (Max
  Kanat-Alexander's view that looping was a temporary hack pending native
  harness support), and section 7 (argument that "context engineering"
  matters more than loop engineering for most devs, vs. AI-infra
  engineers). Revisit if the rest of the article becomes available.
- Aaron Stannard's productivity-workflow example (Akka.NET creator) was cut
  off by the paywall before any detail was given.
