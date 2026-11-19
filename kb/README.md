# OKF Bundle — Operational Knowledge Files

OKF v0.1. Generated 2026-11-19T10:12:52.093964 for project `95120843-ced5-4d3e-88bf-c8ff1116f410`.

One markdown file per node of an application knowledge graph. Every file
opens with YAML front-matter carrying the same six fields:

| Field | Meaning |
|---|---|
| `type` | node type (SERVICE, FUNCTION, MODULE, …) |
| `title` | human-readable name |
| `description` | curated summary if one exists, else derived from the graph |
| `resource` | source file path, or `null` when nothing is linked |
| `tags` | filterable labels derived from graph facts |
| `timestamp` | when this bundle was generated |

## Reading it

Plain UTF-8 markdown in a plain directory. No SDK, no database, no API:

- **Any editor / GitHub** — files render as ordinary markdown.
- **Obsidian** — open the directory as a vault; `[[wikilinks]]` under
  "Connections" become graph edges.
- **grep** — `grep -rl "tags:.*external-call" .`
- **RAG / agents** — parse the front-matter as YAML, embed the body.

`index.md` lists every node id and its file.

## Contents

- 175 node document(s)
- 0 carrying curated runbook prose
- 2 under `nodes/` (node id prefix has no dedicated directory)
