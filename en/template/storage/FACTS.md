# FACTS

## Why this file exists

This file stores canonical reference information that you need to check quickly.

## What belongs here

- confirmed parameters, addresses, identifiers, and decisions;
- stable definitions and conventions;
- links to more detailed reference sections.

## What does not belong here

- temporary notes and drafts;
- a plan for developing the system;
- disconnected data with no confirmed source;
- the log of choosing a standard: “selected A, rejected B” — that goes in `DECISION_LOG.md` if the slot is in use; this file holds the current value after the decision.

---

## Example

> For an “AI tools knowledge base” storage folder

**Base contents:**
- `reference/llm-prompting/` — prompting techniques for different tasks.
- `reference/tools/` — tool cards (Cursor, Claude, ChatGPT).
- `inventories/bookmarks.md` — confirmed links to articles and videos.

**Key parameters:**
- Language of materials: Russian (translations from English — only after verification).
- Tool card format: name, category, link, short description, date added.
- Primary verification sources: official documentation, arxiv.org.

**Conventions:**
- Unverified links are stored in `BACKLOG.md`, not in `inventories/`.
- Materials older than 1 year are tagged `[outdated]` before archiving.
