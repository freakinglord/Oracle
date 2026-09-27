---
title: OpenCode vs. Cline vs. Claude Code
tags: [claude-code, opencode, cline, coding-agents, harness-comparison]
source: query
source_type: query
created: 2026-08-23
updated: 2026-08-23 15:16
---

# OpenCode vs. Cline vs. Claude Code

## Overview
Three coding-agent harnesses compared on vendor lock-in, surface (terminal
vs. editor), and license. Answered from model knowledge (cutoff Jan 2026),
not verified against current docs/repos — see Open questions.

## Key Points

### Claude Code
- Anthropic's own CLI/IDE agent. Anthropic-only (no other model providers).
- First-party integration with the Claude API: prompt caching, native tool
  use, MCP support built in.
- Ships the skills/subagents/hooks extensibility system — see
  [[claude-code-extensibility]].
- Closed source.
- Terminal-first surface.

### Cline
- VS Code extension (fork lineage from "Claude Dev").
- Model-agnostic: Claude, GPT, local models via Ollama, OpenRouter, etc.
- Diff-based edits shown inline in the editor; human-in-the-loop approval
  per file change; plan/act mode split.
- Open source.
- Editor-embedded surface only — no standalone terminal agent.

### OpenCode
- Open-source terminal-based coding agent (TUI).
- Model-agnostic like Cline, but terminal-first like Claude Code — pitched
  as a "Claude Code alternative" usable with any provider (Anthropic,
  OpenAI, local models).
- Configurable providers/agents; session/tool-call UX similar to Claude
  Code but not tied to Anthropic.

### Comparison axes
- **Vendor lock-in**: Claude Code = Anthropic-only. Cline and OpenCode =
  bring-your-own-model.
- **Surface**: Claude Code and OpenCode = terminal-first. Cline =
  editor-embedded (VS Code sidebar).
- **License**: Cline and OpenCode = open source. Claude Code = closed
  source.
- **Approval model**: Cline = heavy diff-review-per-change. Claude Code =
  permission modes (auto-accept, plan mode, etc.) plus built-in
  orchestration (subagents, skills, hooks). OpenCode = closer to Claude
  Code's terminal-agent shape but provider-neutral.

## Related
- [[claude-code-extensibility]] — detail on the skills/hooks/plugins system
  that's part of Claude Code's differentiation here.

## Open questions / gaps
- Not verified against live docs/repos as of 2026-08-23 (`web_search` tool
  unavailable this session). OpenCode in particular moves fast; feature
  specifics may have shifted since Jan 2026 knowledge cutoff.
- Pricing/licensing terms for each not captured.
- No first-hand usage comparison (speed, reliability, context handling)
  yet — this page is landscape/positioning only.
