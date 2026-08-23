<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-07-31 15:16] new-topic | Test Topic
Scaffolded projects/test-topic/wiki/ — scratch topic used to verify the /new-topic, /ingest, /query, and /lint skills end-to-end.

## [2026-07-31 15:17] ingest | dummy-test-source.md
Created dummy-test-source.md from raw/dummy-test-source.md. Confirmed raw/ untouched.

## [2026-07-31 15:18] lint | projects/test-topic
No issues found.

## [2026-08-03 20:54] lint | rename index.md/log.md to slug-qualified names
Renamed index.md → test-topic-index.md and log.md → test-topic-log.md (repo-wide convention change to avoid identically-named nodes/ambiguous [[index]] links across topics in Obsidian). Fixed the internal log link in the index page.

## [2026-08-03 20:59] lint | fix source field to use Obsidian wikilinks
dummy-test-source.md's `source` frontmatter was a plain `raw/...` path, which Obsidian doesn't render as a link or graph edge. Changed to a quoted wikilink `"[[dummy-test-source.md]]"` (repo-wide convention change; see CLAUDE.md, templates/page.md, skills/ingest/SKILL.md).

## [2026-08-08 18:07] lint | fix dummy-test-source.md missing template sections
Page had no `## Overview` / `## Key Points` headers at all — just a bare paragraph and bullet. Added both headings per templates/page.md; content unchanged.
