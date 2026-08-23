# Oracle

A personal LLM wiki. Sources go into `raw/` once; Claude incrementally
builds and maintains an interlinked markdown wiki from them under
`research/` and `projects/`, instead of re-deriving answers from scratch
each time.

```
raw/                       permanent inbox of ingested sources (immutable)
research/<topic>/wiki/     open-ended exploration topics
projects/<topic>/wiki/     topics tied to something concrete being built
templates/                 blank page/index/log skeletons
```

## Operations

- `/new-topic` — scaffold a new topic
- `/ingest` — file a source into the wiki
- `/query` — answer a question from the wiki, with citations
- `/lint` — health-check a topic for contradictions, stale claims, orphans

See `CLAUDE.md` for full conventions (frontmatter schema, log format, etc).

