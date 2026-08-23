<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-08-08 09:36] new-topic | Coffee
Scaffolded research/coffee/wiki/ — learning how coffee beans are produced, the science behind coffee, and brewing methods.

## [2026-08-08 09:42] ingest | A Beginner's Guide to Resting Coffee (James Hoffmann)
Created coffee-resting-degassing.md covering CO2/degassing chemistry, quenching, storage temp, bag valves, vacuum-sealed container behavior, and rest-time guidelines for filter vs espresso by roast level.

## [2026-08-08 17:55] lint | apply updated Key Points template (### sub-headers)
Reformatted coffee-resting-degassing.md's Key Points into `###` sub-headers (CO2 chemistry, brewing effects, storage & containers, rest time recommendations, practical takeaways), per the templates/page.md update allowing thematic sub-headers when points cluster 3+ per theme.

## [2026-08-08 18:07] lint | add missing ## Overview header to coffee-resting-degassing.md
The overview sentence sat directly under the page's `#` title with no `## Overview` heading, unlike templates/page.md. Added the heading; text unchanged.
