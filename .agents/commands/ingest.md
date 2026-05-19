---
description: Ingest new files from raw/ into wiki/.
argument-hint: optional number of sources to process
---

Read the vault structure and follow `AGENTS.md` before making changes.

For each unread file in `raw/`, skipping anything already summarised:

- Read the source file carefully.
- Write a `source-summary` page in `wiki/`.
- Create or update related concept, project, and person pages in `wiki/` as needed.
- Cross-link related pages using `[[wiki-links]]`.
- Update `wiki/index.md` so the new or changed pages are discoverable.
- Append a timestamped entry to `wiki/log.md` describing what was ingested and updated.

Processing rules:

- Process 5-10 sources thoroughly per run by default.
- If `$ARGUMENTS` is provided, limit the run to that many sources.
- Work thoroughly rather than maximizing file count.
- Do not modify files inside `raw/`.
- Do not re-summarise sources that already have a corresponding summary page unless explicitly asked.

When writing or updating wiki pages:

- Follow the required YAML frontmatter and page conventions from `AGENTS.md`.
- Attribute claims to the relevant source-summary or source material.
- Keep pages atomic and well-linked.
- Note contradictions explicitly when sources disagree.
