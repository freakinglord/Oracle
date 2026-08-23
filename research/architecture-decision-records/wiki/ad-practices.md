---
title: AD Practices
tags: [architecture, documentation, decision-making, process]
source: https://adr.github.io/ad-practices/
source_type: url
created: 2026-08-18
updated: 2026-08-18 13:48
---

# AD Practices

## Overview
Curated resources on the *process* of making and documenting architectural decisions (ADs) — as opposed to [[ADR Fundamentals|adr-fundamentals.md]], which covers vocabulary and origins. From adr.github.io's AD Practices page (posted 2024-10-27, updated 2026-05-11); the org notes it does not necessarily endorse every listed resource.

## Key Points

### AD making (arriving at a decision)
- **Design Practice Repository (DPR)** — GitHub resource + companion LeanPub e-book by Mirko Stocker and Olaf Zimmermann (2021–2024), treats decision making/capturing as a core design activity.
- Jacqui Read (2024): tip to "normalise your criteria DOWN to the same level of abstraction" when weighting decision criteria.
- Olaf Zimmermann (2025): "Seven Architectural Decision Making Fallacies (and Ways Around Them)."

### MADR-maintainer practice series (Zimmermann et al.)
Eight numbered articles, cross-published on Medium:
1. Definition of Ready for Architectural Decisions — five readiness criteria, acronym **START**.
2. Architectural Significance Test — helps identify which decisions merit formal capture.
3. How to create ADRs — and how not to (good practices + anti-patterns).
4. The MADR Template Explained and Distilled — now ingested in full as [[MADR Template|madr-template.md]].
5. A Definition of Done for Architectural Decision Making — five completion criteria: evidence, criteria/alternatives, agreement, documentation, realization/review plan.
6. Strong vs. weak justifications in decision records (context + examples).
7. How to review ADRs — and how not to (review practices, anti-patterns, checklist).
8. An Adoption Model for Architectural Decision Making and Capturing — organizational maturity model.

### Broadening scope
- Two Medium posts argue for extending ADR practice beyond architecture: "From Architectural Decisions to Design Decisions" and "ADR = Any Decision Record?" — consistent with [[ADR Fundamentals|adr-fundamentals.md]]'s note that the practice can extend to "any decision record."

## Related
- [[ADR Fundamentals|adr-fundamentals.md]] — vocabulary, origins (Nygard, Y-statements), adoption. This page's "any decision record" framing echoes that page's note on AKM scope.
- [[ADR Templates|adr-templates.md]] — practice article #4 in this page's series covers the MADR format detailed there.
- [[MADR Template|madr-template.md]] — full ingest of practice article #4.

## Open questions / gaps
- The other 7 practice articles (START criteria detail, significance test, anti-patterns, Definition of Done, review checklist, adoption model) were only summarized at the list level — not read in full. Worth a deeper ingest if adopting these as a concrete team process.
