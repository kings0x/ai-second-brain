---
description: Run a health check on the wiki.
argument-hint: optional focus area or page path
---

Read `AGENTS.md` first, then run a health check on `wiki/`.

Scan for:

- Broken `[[wiki-links]]`
- Orphan pages
- Pages missing required frontmatter
- Stale pages that have not been updated in 30+ days
- Contradictions between pages

Report findings as a structured list.

Do not fix anything yet.
Ask for permission before making any edits.

If `$ARGUMENTS` is provided, use it as a focus area or path while still reporting any major cross-wiki issues you discover.
