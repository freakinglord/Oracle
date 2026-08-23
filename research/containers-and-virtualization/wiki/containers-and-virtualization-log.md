<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-08-04 18:29] new-topic | Containers and Virtualization
Scaffolded research/containers-and-virtualization/wiki/ — comparing container/virtualization technologies (LXC, Docker, Kubernetes, VMs), tradeoffs, and adoption assessments.

## [2026-08-04 18:29] query | What is LXC and how does it differ from Docker, Kubernetes, and VMs?
Answered from general knowledge (not wiki-sourced — no existing topic covered this). Filed as lxc-vs-docker-vs-kubernetes-vs-vms.md, including a Technology-Radar-style ring assessment (Adopt/Trial/Assess/Caution) per technology, cross-referencing the ring methodology from [technology-radar](../../technology-radar/wiki/thoughtworks-technology-radar-vol-34.md).
