---
title: ADR Templates
tags: [architecture, documentation, decision-making, templates]
source: https://adr.github.io/adr-templates/
source_type: url
created: 2026-08-18
updated: 2026-08-18 13:48
---

# ADR Templates

## Overview
Survey of the main ADR template formats — variations on a common `ADR` concept rather than independent formats. Complements [[ADR Fundamentals|adr-fundamentals.md]] (vocabulary/origins) and [[AD Practices|ad-practices.md]] (process).

## Key Points

### MADR (Markdown Architectural Decision Records)
- Maintained within the ADR GitHub org; deeper explanation in [[MADR Template|madr-template.md]] (Zimmermann's primer).
- Plain Markdown, no special tooling needed.
- Comes in **full**/**minimal** variants, each in **annotated**/**bare** form.
- Name puns on "matter" — decisions that matter.
- Emphasizes documenting **considered options** with pros/cons as central to capturing rationale; suggests metadata fields for decision makers, confirmation status, decision status.
- A VS Code extension exists (may be outdated / missing latest features).

### Nygard ADR
- The original/foundational format, from Michael Nygard's 2011 blog post "Documenting Architecture Decisions."
- Five core sections: **title, status, context, decision, consequences**.
- A Markdown rendering exists via Joel Parker Henderson's repository.

### Y-Statement
- Single-sentence, fill-in-the-blank capture — short and long forms.
- Short form: *"In the context of `<use case/user story>`, facing `<concern>` we decided for `<option>` to achieve `<quality>`, accepting `<downside>`."*
- Long form adds a "because" clause plus explicit neglected alternatives and desired/undesired consequences.
- Adopted by cards42 as a German-language ADR card (English version adds state info).
- Explained further in the Medium article "Y-Statements - A Light Template for Architectural Decision Capturing."

### Other templates
- Joel Parker Henderson's GitHub repo catalogs many more formats.
- **ISO/IEC/IEEE 42010:2011** — Appendix A proposes nine information items for architecture decision records, plus guidance on identifying which decisions are "key" enough to document.

### Choosing a template
No explicit head-to-head guidance given, but the page implies a spectrum by structure/depth:
- Lightweight, single-statement → **Y-Statement**
- Structured but simple (5 sections) → **Nygard**
- Detailed, tradeoff-focused (options + pros/cons + metadata) → **MADR**
- Standards-driven, formal contexts → **ISO/IEC/IEEE 42010**

## Related
- [[ADR Fundamentals|adr-fundamentals.md]] — the Y-Statement format traces to the same Zdun et al. "Sustainable Architectural Decisions" lineage noted there.
- [[AD Practices|ad-practices.md]] — practice article #4 in that series ("The MADR Template Explained and Distilled") is now ingested in full as [[MADR Template|madr-template.md]].
- [[MADR Template|madr-template.md]] — full 10-section structure, version history, and worked example for MADR.
- [[Decision Capturing Tools|adr-tooling.md]] — tooling that implements each of these templates.

## Open questions / gaps
- Joel Parker Henderson's full template catalog wasn't enumerated — only referenced as a collection.
