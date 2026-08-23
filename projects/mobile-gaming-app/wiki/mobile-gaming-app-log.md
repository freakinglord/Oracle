<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-08-03 20:43] new-topic | Mobile Gaming App
Scaffolded projects/mobile-gaming-app/wiki/ — building a mobile asteroid survival game as a non-programmer using Godot 4/GDScript.

## [2026-08-03 20:43] ingest | game-planning-for-non-programmers.md
Created page game-planning-for-non-programmers.md — game planning framework (core loop, 5 systems, Godot engine choice, difficulty curve, 7-week build order) from an exported Claude chat conversation.

## [2026-08-03 20:47] query | Name Ideas
Created page name-ideas.md — brainstormed name candidates for the game (short/punchy, survival-themed, playful/punny), filed back from a /query-style discussion.

## [2026-08-03 20:54] lint | rename index.md/log.md to slug-qualified names
Renamed index.md → mobile-gaming-app-index.md and log.md → mobile-gaming-app-log.md (repo-wide convention change to avoid identically-named nodes/ambiguous [[index]] links across topics in Obsidian). Fixed the internal log link in the index page and the [[index]] reference in game-planning-for-non-programmers.md.

## [2026-08-03 20:59] lint | fix source field to use Obsidian wikilinks
game-planning-for-non-programmers.md's `source` frontmatter was a plain `raw/...` path, which Obsidian doesn't render as a link or graph edge. Changed to a quoted wikilink `"[[game-planning-for-non-programmers.md]]"` (repo-wide convention change; see CLAUDE.md, templates/page.md, skills/ingest/SKILL.md).

## [2026-08-08 17:55] lint | apply updated Key Points template (### sub-headers)
Reformatted name-ideas.md's Key Points from bold-lead groups into `###` sub-headers, per the templates/page.md update allowing thematic sub-headers when points cluster 3+ per theme.

## [2026-08-08 18:17] lint | delete empty Details section
game-planning-for-non-programmers.md's `## Details` only said "None beyond Key Points" — templates/page.md says to delete the section rather than leave a placeholder note. Removed it.
