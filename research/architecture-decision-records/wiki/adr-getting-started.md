---
title: Getting Started with ADRs
tags: [architecture, documentation, decision-making, adoption]
source: ["[[adr-fundamentals.md]]", "[[adr-templates.md]]"]
source_type: query
created: 2026-08-18
updated: 2026-08-18 18:00
---

# Getting Started with ADRs

## Overview
What an ADR is, why it's worth writing one, and how to start using them on a
project that's already underway (not just greenfield). Synthesized from
[[ADR Fundamentals|adr-fundamentals.md]] and [[ADR Templates|adr-templates.md]],
plus general practical knowledge not sourced from the wiki (flagged below).

## Key Points

### What an ADR is
- An Architecture Decision Record captures one architecturally significant
  decision, its context, and its consequences — nothing more.
- Nygard's original format (still the most common) has 5 sections: **title,
  status, context, decision, consequences**. See [[ADR Templates|adr-templates.md]].
- Lighter (Y-Statement) and heavier (MADR, ISO 42010) formats exist for less
  or more ceremony — pick by how many real alternatives you're weighing.

### Why it helps
- Kills re-litigation: "why Postgres over Mongo" is answered by the file,
  not a chat-archaeology dig.
- Forces the tradeoff to be written down, not just the choice, so the
  rejected options and reasoning survive past the decision itself.
- Cheap: plain markdown in the repo, no tooling required to start.

### Adding ADRs to an existing project (not sourced from wiki — general practice)
- ADRs aren't tied to a project's start date — a file-based practice can be
  adopted at any point in a project's life.
- Start numbering from `0001` now; don't backfill every past decision that
  was never written down.
- Only write a retroactive ADR for a past decision that's still **live** —
  actively confusing people, or about to be revisited/reversed.
- Reversing or replacing an old undocumented decision is a natural first
  ADR: the "context" section just states what's there today.
- Tooling (`adr-tools` CLI, `log4brains`) scaffolds the folder/numbering
  instantly — no migration step needed, since ADRs are just files.

## Related
- [[ADR Fundamentals|adr-fundamentals.md]] — vocabulary and origins this page assumes.
- [[ADR Templates|adr-templates.md]] — template choice referenced above.
- [[AD Practices|ad-practices.md]] — process detail (readiness/DoD criteria) for teams formalizing this further.

## Open questions / gaps
- The "existing project" adoption guidance is general practice knowledge,
  not yet sourced from an ingested article — worth ingesting a dedicated
  source (e.g. one of the MADR-maintainer practice series articles, #3 "How
  to create ADRs") if this needs firmer backing.
