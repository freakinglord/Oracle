---
title: Industry Generalization of the Persona-Phase Map
tags: ["genai", "sdlc", "devops"]
source: "[[persona-phase-map.md]]"
source_type: query
created: 2026-08-08
updated: 2026-08-08 18:17
---

# Industry Generalization of the Persona-Phase Map

## Overview
How much of [[persona-phase-map]] holds outside IBM/software delivery. The
specific tooling is DevOps-specific; the underlying phase/persona/verb
structure is not.

## Key Points
- The three-verb structure (**Discover → Generate → Perform**) maps onto any
  industry with a design-build-run lifecycle: manufacturing (product design
  → production automation → maintenance ops), healthcare IT (clinical
  workflow discovery → system config generation → incident triage), telecom
  (network design → provisioning automation → NOC ops), financial services
  (product/risk design → controls automation → ops monitoring).
- The persona split — **design-time roles** that generate artifacts vs.
  **run-time roles** that perform/monitor — is a generic org pattern, not
  SDLC-specific. Swap Architect/Developer for Process Engineer/Line
  Technician and Platform Engineer/SRE for Facilities Manager/Ops Analyst
  and the map still holds.
- What doesn't generalize: the specific artifacts (Terraform, Ansible,
  GitOps pipelines, vulnerability scanning, ticket auto-triage) are
  software-delivery-specific. An industrial or healthcare version would
  swap these for CAD/BOM generation, compliance documentation, equipment
  runbooks — same slots, different fillers. Named personas like "FinOps
  Consultant" and "Quality Engineer" are cloud/software org-chart terms.
- **Net**: useful as a template (phase × persona × GenAI-verb grid) for any
  ops-heavy industry, not useful as-is for the specific tooling column.

## Related
- [[persona-phase-map]] — the source table this generalizes from.

## Open questions / gaps
- Would be worth validating against a real non-software example (e.g. a
  manufacturing or healthcare GenAI adoption case study) rather than
  reasoning from the template alone.
