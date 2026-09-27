---
title: ADR Fundamentals
tags: [architecture, documentation, decision-making]
source: https://adr.github.io/
source_type: url
created: 2026-08-18
updated: 2026-08-23 16:03
---

# ADR Fundamentals

## Overview
Core vocabulary, motivation, and provenance of the Architecture Decision Record (ADR) practice, from the ADR GitHub organization's homepage.

## Key Points

### Vocabulary
- **Architectural Decision (AD)** — a justified design choice that addresses a functional or non-functional requirement that is architecturally significant.
- **Architecturally Significant Requirement (ASR)** — a requirement that has a measurable effect on the architecture and quality of a software and/or hardware system.
- **Architectural Decision Record (ADR)** — captures a single AD and its rationale, including trade-offs and consequences.
- **Decision log** — the accumulated set of ADRs maintained across a project.
- ADR practice sits under the broader umbrella of **Architectural Knowledge Management (AKM)**, and can extend to other kinds of decisions beyond architecture ("any decision record").

### Origins and background
- **Michael Nygard's 2011 blog post** "Documenting Architecture Decisions" is credited with popularizing the ADR concept.
- The **Y-statement format** (Zdun et al., "Sustainable Architectural Decisions," InfoQ) underlies the ADR org's approach.
- A WICSA 2015 paper compared seven different ADR templates and covered decision backlog management.
- Mark Richards has a video lesson on ADRs and "Architecture Stories," building on Nygard's original template.

### Adoption / notable coverage
- Microsoft's Azure Well-Architected Framework references ADRs.
- AWS Prescriptive Guidance recommends ADRs to streamline technical decision-making.
- IEEE Software published a 2022 column by Michael Keeling on ADRs bridging architecture and Agile practice.
- "Patterns for API Design" (book) devotes a chapter to 29 recurring API decisions using this style.

### Site structure (adr.github.io)
- Organizes resources into three areas not yet ingested in depth: **ADR Templates**, **Decision Capturing Tools**, **AD Practices**.

## Related
- [[AD Practices|ad-practices.md]] — process-focused resources on making and reviewing ADs (MADR-maintainer practice series, adoption maturity model).
- [[ADR Templates|adr-templates.md]] — the concrete template formats (MADR, Nygard, Y-Statement, ISO 42010) referenced here at a high level.
- [[Decision Capturing Tools|adr-tooling.md]] — tooling implementing these templates.

## Open questions / gaps
- The homepage is a landing/motivation page; it doesn't cover a specific
  template's structure or a tooling recommendation itself — see
  [[ADR Templates|adr-templates.md]] and [[Decision Capturing Tools|adr-tooling.md]]
  for that detail (both now ingested).
