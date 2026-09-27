<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-07-31 16:37] new-topic | Technology Radar
Scaffolded research/technology-radar/wiki/ — tracking ThoughtWorks Technology Radar volumes over time.

## [2026-07-31 16:37] ingest | technology_radar.md (ThoughtWorks Technology Radar Vol 34)
Created thoughtworks-technology-radar-vol-34.md from raw/technology_radar.md (source PDF fetched and read directly, pages 1-13, since the raw file itself was a metadata-only clipper stub). Covers the 4 themes and the full 118-item ring index.

## [2026-07-31 17:35] ingest | technology_radar_vol_34.pdf (re-ingest, new template)
Re-ingested to apply the new Key-Points-first page template: rewrote thoughtworks-technology-radar-vol-34.md with an Overview + bulleted Key Points (4 themes distilled) and moved the full ring index into Details. Downloaded the source PDF and archived it at raw/technology_radar_vol_34.pdf for future ingest/query (previously only a metadata stub existed in raw/). Page frontmatter `source` updated to list both raw/technology_radar.md and the new PDF.

## [2026-08-03 20:23] query | What are blips?
Answered from general knowledge (not previously defined on the page). Expanded the existing quadrants/rings bullet on thoughtworks-technology-radar-vol-34.md into an explicit definition of "blip."

## [2026-08-03 20:54] lint | rename index.md/log.md to slug-qualified names
Renamed index.md → technology-radar-index.md and log.md → technology-radar-log.md (repo-wide convention change to avoid identically-named nodes/ambiguous [[index]] links across topics in Obsidian). Fixed the internal log link in the index page.

## [2026-08-03 20:59] lint | fix source field to use Obsidian wikilinks
thoughtworks-technology-radar-vol-34.md's `source` frontmatter was a plain YAML list of `raw/...` paths, which Obsidian doesn't render as links or graph edges. Changed to a YAML list of quoted wikilinks `["[[technology_radar.md]]", "[[technology_radar_vol_34.pdf]]"]` (repo-wide convention change; see CLAUDE.md, templates/page.md, skills/ingest/SKILL.md).

## [2026-08-04 18:29] query | cross-link from new containers-and-virtualization topic
Added Related link on thoughtworks-technology-radar-vol-34.md pointing to the new lxc-vs-docker-vs-kubernetes-vs-vms.md page, which reuses this radar's ring methodology (Adopt/Trial/Assess/Caution) for an independent assessment.

## [2026-08-08 17:55] lint | apply updated Key Points template (### sub-headers)
Reformatted thoughtworks-technology-radar-vol-34.md's Key Points into `###` sub-headers (Radar basics, Theme 1-4), per the templates/page.md update allowing thematic sub-headers when points cluster 3+ per theme.

## [2026-08-23 16:03] lint | whole wiki
Fixed: thoughtworks-technology-radar-vol-34.md's `## Details` section promised "the full 118-blip ring index" but contained no actual index (content gap) — deleted the empty section and adjusted the Overview, Key Points, Open questions/gaps, and technology-radar-index.md summary to state the full ring index isn't reproduced on the page and points to `raw/technology_radar_vol_34.pdf` instead.
