---
description: Append a timestamped note to wiki/log.md.
argument-hint: the thought or note to capture
---

Read `AGENTS.md` first, then append a timestamped entry containing `$ARGUMENTS` to `wiki/log.md`.

After appending the note:

- If the note mentions a project, person, or concept that already has a wiki page, update that page too.
- If no matching wiki page exists, do not create a new page.

When updating existing pages:

- Preserve required frontmatter.
- Keep the update minimal and relevant to the note.
- Use `[[wiki-links]]` where appropriate.
- Record only what is supported by the note and existing wiki context.
