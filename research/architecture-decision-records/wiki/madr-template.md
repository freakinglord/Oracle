---
title: MADR Template
tags: [architecture, documentation, decision-making, templates, madr]
source: https://www.ozimmer.ch/practices/2022/11/22/MADRTemplatePrimer.html
source_type: url
created: 2026-08-18
updated: 2026-08-18 13:48
---

# MADR Template

## Overview
Olaf Zimmermann's deep-dive primer on the MADR template — practice article #4 in the MADR-maintainer series referenced (but not yet read) in [[AD Practices|ad-practices.md]]. Expands on the summary in [[ADR Templates|adr-templates.md]].

## Key Points

### Background
- Originated 2017, building on Nygard's ADR proposal and Zimmermann's own Y-statements; inherits *context*, *decision*, *consequences* as core elements. ~2,100 GitHub stars.
- **Version 3.0**: added optional metadata + optional "Confirmation" section; merged positive/negative consequences to ease copy-paste from the options section.
- **Version 4.0**: renamed some elements, introduced the minimal variant.
- **2026**: **YADR** (YAML ADRs) introduced — an abstract YAML-based version, "(almost) as human-readable as Markdown, but can be processed by tools much easier."

### CALM benefits
ADRs (per this author) support:
- **C**ollaborative content creation
- **A**ccountability, avoiding re-litigation of settled decisions
- **L**earning opportunities for newcomers and veterans
- **M**anagement appeal — fits familiar decision-making patterns

### Full template structure (10 sections)
1. **Title** — ideally captures both problem and chosen solution.
2. **Metadata** (all optional) — status, date, deciders, consulted, informed.
3. **Context and Problem Statement** — frames the issue, traceable to the relevant system/architecture parts.
4. **Decision Drivers** — forces, constraints, desired qualities.
5. **Considered Options** — alternatives at a *consistent level of abstraction* (chosen option listed first by convention); warns against comparing mismatched categories, e.g. a technology vs. a product.
6. **Decision Outcome** — chosen option + justification (e.g. best score, key criterion met).
7. **Consequences** — "Good, because…" / "Bad, because…", tied back to context and decision drivers.
8. **Confirmation (Validation)** — optional; how implementation will be verified (code review, ATAM, DCAR); maps to the "R" in the related Definition of Done framework.
9. **Pros and Cons of the Options** — deeper analysis using "Good/Bad/Neutral (w.r.t.)" framing.
10. **More Information** — supporting evidence, team agreement/confidence, realization/revisit plan, related-decision links.

### Minimal variant ("MADR Light")
- Distills to 3-5 essential elements; closely resembles Nygard's original 2011 format and aligns well with the Y-Statement sentence structure.

### Worked example
- Decomposition decision choosing the **Layers pattern** over pipes-and-filters and workflow approaches; includes YAML metadata, a context question, 2 decision drivers (complexity management, part exchangeability), 3 considered options, a justified outcome, consequences (flexibility/parallelism vs. performance penalty/replication), and pattern-reference links in More Information.

### Tooling mentioned
- **ADR Manager (VS Code)** and **ADR Manager (web)** — both University of Stuttgart student projects, GitHub-connected, full CRUD; compatible with template v2.1.2 as of Nov 2022. Broader directory: see [[Decision Capturing Tools|adr-tooling.md]].

### Author's closing guidance
- Markdown beats wikis/proprietary formats for being version-control-friendly and forcing focus on message over presentation.
- Teams should adapt which parts are optional/required to their context, but commit early and stay consistent: "Stick to what you have decided for."

## Related
- [[ADR Templates|adr-templates.md]] — MADR summarized alongside Nygard, Y-Statement, ISO 42010.
- [[AD Practices|ad-practices.md]] — this primer is practice article #4 in the MADR-maintainer series listed there.
- [[Decision Capturing Tools|adr-tooling.md]] — MADR-specific tooling.
- [[ADR Fundamentals|adr-fundamentals.md]] — shares the AD/ASR/ADR/decision-log definitions verbatim.

## Open questions / gaps
- The other 7 articles in the MADR-maintainer practice series (START readiness criteria, significance test, anti-patterns, Definition of Done, review checklist, adoption model) are still unread — only summarized at the list level in [[AD Practices|ad-practices.md]].
