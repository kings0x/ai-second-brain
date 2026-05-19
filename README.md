# Four Verbs Second Brain

An AI-assisted second brain vault built around four actions only: ingest sources, query knowledge, lint the wiki, and log new thoughts.

## What This Is

This repository is an Obsidian-friendly knowledge vault with a strict separation between:

- `raw/`: original source material
- `wiki/`: maintained knowledge pages
- `journal/`: daily notes
- `content/`: content pipeline work

The idea is simple:

- keep source material untouched
- compile it into useful wiki pages
- ask questions against the wiki instead of the raw files
- keep the system healthy with linting
- capture lightweight notes in the log

## The Four Verbs

These are the only things the agent should do inside this second brain:

- `/ingest`: read from `raw/` and compile source-backed pages into `wiki/`
- `/query`: answer questions from `wiki/` with citations
- `/lint`: scan `wiki/` for broken links, stale pages, missing frontmatter, or contradictions
- `/log`: append a one-line note to `wiki/log.md` and update related existing pages when relevant

## Project Structure

```text
.
├── .agents/
│   └── commands/
│       ├── ingest.md
│       ├── query.md
│       ├── lint.md
│       └── log.md
├── raw/
│   ├── claude-exports/
│   ├── chatgpt-exports/
│   ├── notion-exports/
│   ├── granola-exports/
│   ├── articles/
│   └── notes/
├── wiki/
│   ├── concepts/
│   ├── projects/
│   ├── people/
│   ├── index.md
│   └── log.md
├── journal/
├── content/
└── AGENTS.md
```

Key files:

- `AGENTS.md`: the operating rules for the vault
- `wiki/index.md`: the catalog of wiki pages
- `wiki/log.md`: the append-only activity log
- `.agents/commands/*.md`: slash-command definitions for the workflow

## How It Works

### 1. Add source material

Drop files into `raw/` without editing them. Typical examples:

- exported chats from Claude or ChatGPT
- Notion exports
- meeting notes
- saved articles
- loose notes

### 2. Run `/ingest`

The agent reads unread files from `raw/` and then:

- creates a `source-summary` page in `wiki/`
- creates or updates related concept, project, and person pages
- adds `[[wiki-links]]` between related pages
- updates `wiki/index.md`
- appends a timestamped note to `wiki/log.md`

Example:

```text
/ingest
/ingest 5
```

### 3. Run `/query`

Ask a question against the wiki instead of searching raw files manually.

Example:

```text
/query What patterns keep showing up in my notes about distributed systems?
```

The answer should:

- read `wiki/index.md` and the most relevant pages
- synthesize a response grounded in the wiki
- cite claims by wiki page name
- flag disagreements between sources

### 4. Run `/lint`

Check the health of the wiki.

Example:

```text
/lint
```

This should report:

- broken `[[wiki-links]]`
- orphan pages
- missing required frontmatter
- stale pages
- contradictions

### 5. Run `/log`

Capture a thought quickly without doing a full ingest.

Example:

```text
/log Need to compare the technical notes tool idea with the watchlist app before choosing one.
```

This appends a timestamped note to `wiki/log.md` and may update an existing related page if one already exists.

## Wiki Page Standard

Every wiki page should include YAML frontmatter with:

- `title`
- `type`
- `sources`
- `related`
- `created`
- `last-updated`

Allowed `type` values:

- `concept`
- `entity`
- `source-summary`
- `comparison`
- `project`
- `person`

Pages should:

- stay atomic
- use `[[wiki-links]]`
- keep a consistent heading structure
- cite every claim
- note contradictions explicitly

## How To Use This Repo

### In Obsidian

1. Open the repository folder as an Obsidian vault.
2. Browse the wiki from `wiki/index.md`.
3. Add new source material to `raw/`.
4. Use your agent workflow to run `/ingest`, `/query`, `/lint`, and `/log`.

### With an AI coding agent

This repo is designed to work with an agent that reads:

- `AGENTS.md` for vault rules
- `.agents/commands/` for slash-command behavior

The agent should treat `raw/` as read-only source input and `wiki/` as the maintained knowledge layer.

## Suggested Use Cases

- personal knowledge management
- research synthesis
- technical learning notes
- project memory
- people and relationship context
- content idea development

## Repository Setup

There is no build step.

To use the project:

1. clone the repository
2. open it as an Obsidian vault
3. add source files into `raw/`
4. use the four commands through your AI agent


