# AGENTS

## Core Workflow

The second brain is organized around four verbs. These are the only operations that should be performed inside the vault:

- `/ingest`: move knowledge from `raw/` into `wiki/` by compiling sources into pages.
- `/query`: read from `wiki/` to answer questions with citations.
- `/lint`: inspect `wiki/` and report structural or content issues.
- `/log`: append a short note to `wiki/log.md` and update existing related pages when relevant.

## 1. Project Structure

This vault is organized around a strict separation between `raw/` and `wiki/`.

- `raw/` contains source material provided by the user.
- Files in `raw/` are treated as original inputs and should not be modified.
- `wiki/` contains maintained knowledge pages created and updated by the agent.
- `journal/` contains daily notes and time-based entries.
- `content/` contains content pipeline material such as drafts, outlines, and publishing inputs.

Subfolders and purposes:

- `raw/claude-exports/`: exports from Claude.
- `raw/chatgpt-exports/`: exports from ChatGPT.
- `raw/notion-exports/`: exports from Notion.
- `raw/granola-exports/`: exports from Granola.
- `raw/articles/`: articles, PDFs, web captures, and reading material.
- `raw/notes/`: loose imported notes and legacy notes preserved as source material.
- `wiki/concepts/`: concept pages, topic overviews, definitions, and evergreen knowledge.
- `wiki/projects/`: project-specific pages, plans, decisions, and status notes.
- `wiki/people/`: people dossiers and relationship context.

Important wiki files:

- `wiki/index.md`: the master catalog of wiki pages. It should help users find and navigate the knowledge base.
- `wiki/log.md`: the append-only activity log for wiki maintenance. It should record additions, updates, imports, and notable changes.

## 2. Page Conventions

Every wiki page must begin with YAML frontmatter containing these fields:

- `title`
- `type`
- `sources`
- `related`
- `created`
- `last-updated`

Allowed values for `type`:

- `concept`
- `entity`
- `source-summary`
- `comparison`
- `project`
- `person`

All wiki pages should follow these conventions:

- Use `[[wiki-links]]` for internal references between pages.
- Keep pages atomic: one page should cover one idea, concept, entity, comparison, project, or person.
- Attribute statements to the source material listed in `sources`.
- Use a consistent heading structure when relevant:

```md
# Title

## Summary

## Key Points

## Sources

## Related
```

If a page does not need every section, keep the structure consistent by using the closest appropriate subset rather than inventing a new layout.

## 3. Style Guide

- Use clear, concise prose.
- Prefer bullet points over long paragraphs.
- Attribute every claim to its source.
- Note contradictions explicitly when sources disagree.
- Distinguish clearly between source-backed facts, interpretations, and open questions.
- Avoid filler, repetition, and vague summaries.

## 4. Domain Context

This vault will often cover movies and making money. It should also support thinking and learning about distributed systems and coding in general. Important recurring context includes friends and family, along with various projects. The wiki should help preserve what matters across those areas and make it easier to get smarter over time. When organizing knowledge, prioritize clarity around technical ideas, project context, and anything worth remembering from ongoing conversations and notes.
