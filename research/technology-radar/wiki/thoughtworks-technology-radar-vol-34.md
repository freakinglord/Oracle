---
title: ThoughtWorks Technology Radar Vol 34 (April 2026)
tags: [technology-radar, ai-agents, thoughtworks]
source: ["[[technology_radar.md]]", "[[technology_radar_vol_34.pdf]]"]
source_type: raw
created: 2026-07-31
updated: 2026-08-23 16:03
---

# ThoughtWorks Technology Radar Vol 34 (April 2026)

## Overview
ThoughtWorks' Vol 34 radar (April 2026), based on a Technology Advisory Board
meeting in Bengaluru, March 2026 — 4 themes on AI's effect on engineering
practice. Tracks 118 blips total across 4 quadrants; the full ring-by-ring
index is too long to reproduce on this page — see the archived PDF.

## Key Points

### Radar basics
- Published by ThoughtWorks; Technology Advisory Board = 22 senior
  technologists, met in Bengaluru, March 2026.
- A **blip** is a single tracked item on the Radar — one specific technology,
  tool, technique, platform, or framework (e.g. "Agent Skills," "LiteLLM").
  Each blip is placed in one of 4 quadrants (Techniques, Platforms, Tools,
  Languages and Frameworks) × 4 rings (Adopt, Trial, Assess, Caution)
  reflecting ThoughtWorks' recommendation strength; a blip's ring can move
  between editions as confidence in it changes, and new blips are marked as
  such. Vol 34 tracks 118 blips total.
- Full 118-item ring index (all 4 quadrants/rings) is not reproduced here —
  see `raw/technology_radar_vol_34.pdf` for the complete placement list.

### Theme 1 — evaluating tech is getting harder in an agentic world
"Semantic diffusion" blurs terms like *spec-driven development* and
*harness engineering* before meanings stabilize; many tools seen were
<1 month old, sometimes single-contributor + a coding agent; risk of
**codebase cognitive debt** as teams adopt AI-generated solutions without
building the mental models to reason about/debug/evolve them.

### Theme 2 — retaining principles, relinquishing patterns
AI is driving a return to craft fundamentals (pair programming, zero trust
architecture, mutation testing, DORA metrics, clean code, testability,
accessibility) as a counterweight to AI-generated complexity, plus a CLI
resurgence; may need to rethink team structure as "agent topologies"
alongside team topologies.

### Theme 3 — securing permission-hungry agents
The most useful agents (OpenClaw, Claude Cowork for supervised work; Gas
Town for coordinating agent swarms) need broad access to private
data/external comms/real systems, but safeguards lag. Prompt injection is
unsolved; Simon Willison's "lethal trifecta" (private data + untrusted
content + external action) now describes most useful agents by default.
Mitigations: zero trust, least privilege, defense in depth, pipelines of
constrained agents rather than monolithic ones. Emerging: Agent Skills as a
controlled alternative to MCP, durable agents, anti-instruction-bloat
techniques.

### Theme 4 — putting coding agents on a leash
Two control types: **feedforward** (Agent Skills, Superpowers skill
catalog, plugin marketplaces, spec-driven frameworks like GitHub Spec-Kit
and OpenSpec) and **feedback** (compilers/linters/type checkers/test suites
wired into agent workflows, e.g. cargo-mutants, WuppieFuzz, CodeScene; some
teams combine deterministic rules + LLM evaluation to cut architectural
drift).

## Related
- [LXC vs Docker vs Kubernetes vs VMs](../../containers-and-virtualization/wiki/lxc-vs-docker-vs-kubernetes-vs-vms.md) — reuses this page's Adopt/Trial/Assess/Caution ring methodology for an author's-own assessment of container/virtualization technologies.

## Open questions / gaps
This page covers the intro/themes only (pages 1-13 of the source PDF). The
full ring-placement index and the individual write-up for each of the 118
blips are not reproduced here — both live in the archived PDF at
`raw/technology_radar_vol_34.pdf`. If a specific blip needs deeper coverage
(e.g. why LiteLLM moved to Trial, or details on Agent Skills), pull it from
the PDF and either extend this page or split it into its own page
cross-linked from here.
