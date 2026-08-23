<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-08-06 16:23] new-topic | GenAI in the SDLC
Scaffolded topic under research/. First source: IBM internal course table
mapping GenAI capabilities to SDLC phases/personas.

## [2026-08-06 16:23] ingest | Web Component Examples: lk-course (IBM w3 course table)
Created [[persona-phase-map.md]] from the IBM hybrid-cloud-console course
table (URL source, no raw/ file). Maps GenAI capabilities to SDLC
phases/personas.

## [2026-08-08 09:33] query | Industry generalization of persona-phase map
Created [[industry-generalization.md]] answering how much of the
persona-phase map holds outside IBM/software (phase/persona/verb structure
generalizes; specific tooling does not). Cross-linked from
persona-phase-map.md.

## [2026-08-08 18:07] lint | fix genai-sdlc-log.md to match templates/log.md
Stripped frontmatter and `# ... — Log` heading this log file had picked up — every other topic's log is just the HTML-comment header + entries per templates/log.md. Also fixed loop-engineering.md's section order (Related before Open questions/gaps), added the missing `## Overview` header to coffee-resting-degassing.md, and restructured dummy-test-source.md to include Overview/Key Points headers — all to align with templates/page.md.

## [2026-08-08 18:17] lint | fold Details into Key Points on both pages
templates/page.md now allows a Key Points bullet to run a few sentences for a single mechanism, reserving Details for content needing multiple steps/facts. Both pages' Details sections were single short takeaways, so folded each into a new Key Points bullet ("Net" on industry-generalization.md, "Source note" on persona-phase-map.md) and deleted the now-empty Details sections.
