---
title: Decision Capturing Tools
tags: [architecture, documentation, decision-making, tooling]
source: https://adr.github.io/adr-tooling/
source_type: url
created: 2026-08-18
updated: 2026-08-18 13:48
---

# Decision Capturing Tools

## Overview
Catalog of tooling for creating, maintaining, and rendering ADRs, organized by which [[ADR Templates|adr-templates.md]] format they target. The source list is explicitly "inclusive and sorted alphabetically" — not vetted or ranked; readers are told to check maturity/status themselves.

## Key Points

### Any template
- **ADG** — Go CLI for modeling/managing/reusing decisions; supports Nygard, MADR (basic), QOC.
- **dotnet-adr** — cross-platform .NET Global Tool.
- **ReflectRally** — web app for collaborative ADR creation with structured workflows and review processes.
- **adr.zone** — web generator with multi-format support (Nygard, MADR, Y-Statement, ISO/IEC/IEEE 42010-inspired), examples, and an API.

### MADR-specific
- **adr-log** — CLI that keeps an `index.md` updated with all ADRs.
- **ADR Manager** (web) / **ADR Manager VS Code extension** — GitHub-linked, form-based ADR editing.
- **Backstage ADR plugin** — explore/search ADRs at scale across orgs/repos in a Backstage developer portal.
- **Hugo Markdown ADR Tools** — CLI to create/update ADRs.
- **Log4brains** — rendering + CLI-based creation.
- **pyadr** — CLI supporting the full lifecycle (proposal/acceptance/rejection/deprecation/superseding).

### Nygard-specific
- **adr-tools** — original Bash scripts; ported/rewritten in C#, Go, Java, Node.js (x2), PHP, PowerShell (x2), Python (x2), Rust.
- **adr-viewer** — Python app rendering ADRs as a website.
- **architectural-decision** — PHP library using PHP8 Attributes.
- **Loqbooq** — commercial web app with Slack integration for ADR-inspired decision logs.
- **Talo** — CLI/.NET tool managing/exporting ADRs, RFCs, and custom design docs.

### Adjacent tooling
- **Embedded ADRs (Java)** — demonstrates embedding a distributed decision log directly in code via annotations.
- **ArchUnit** — unit-testing framework for architecture rules.
- **docToolchain** — docs-as-code approach for software architecture.
- **Structurizr** — visualizing/documenting architecture with the C4 model.
- Flagged **unmaintained**: adr-log (decision-log generator variant), ADMentor (Sparx EA add-in), eadlsync, SE Repo.

## Related
- [[ADR Templates|adr-templates.md]] — the template formats this tooling implements.
- [[MADR Template|madr-template.md]] — MADR tooling here (ADR Manager web/VS Code) is discussed in more depth, including version compatibility (2.1.2), in that primer.

## Open questions / gaps
- None of the tools were evaluated hands-on; this is a catalog, not a recommendation.
