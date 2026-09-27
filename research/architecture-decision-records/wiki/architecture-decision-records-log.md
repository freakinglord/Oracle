<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-08-18 13:16] new-topic | Architecture Decision Records
Scaffolded research/architecture-decision-records/wiki/ — Architectural Decision Records: what they are, why teams use them, templates and tooling.

## [2026-08-18 13:16] ingest | adr.github.io homepage
Created adr-fundamentals.md from https://adr.github.io/ — ADR vocabulary (AD, ASR, ADR, decision log), origins (Nygard 2011, Y-statements), and adoption. Updated index with the new page.

## [2026-08-18 13:20] ingest | adr.github.io/ad-practices/
Created ad-practices.md — AD making resources, MADR-maintainer 8-article practice series (START readiness criteria, significance test, Definition of Done, review checklist, adoption model), and "any decision record" scope-broadening posts. Cross-linked with adr-fundamentals.md; updated index.

## [2026-08-18 13:38] ingest | adr.github.io/adr-templates/
Created adr-templates.md — MADR, Nygard ADR, Y-Statement, and ISO/IEC/IEEE 42010 template formats, plus a lightweight-to-detailed spectrum for choosing between them. Cross-linked with adr-fundamentals.md and ad-practices.md; updated index.

## [2026-08-18 13:48] ingest | adr.github.io/adr-tooling/ + ozimmer.ch MADR Template Primer
Created adr-tooling.md (Decision Capturing Tools catalog by template) and madr-template.md (full MADR structure, version history, CALM benefits, worked example — fills the practice-article-#4 gap noted in ad-practices.md). Cross-linked all four existing pages; updated index.

## [2026-08-18 18:00] query | What is an ADR, and can I add one to an existing project?
Filed as adr-getting-started.md. Synthesized from: adr-fundamentals.md, adr-templates.md, plus general practice knowledge (flagged as not wiki-sourced) on retrofitting ADRs into an existing project. Cross-linked with adr-fundamentals.md, adr-templates.md, ad-practices.md; updated index.

## [2026-08-23 16:03] lint | whole wiki
Fixed: adr-fundamentals.md's Open questions/gaps still said ADR Templates and Decision Capturing Tools were "not yet ingested" (stale — both exist and are already linked in this page's Related section). Rewrote to point at the ingested pages instead.
