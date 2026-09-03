# README

## Why this file exists

This file is the entry point to a **groundwork** folder: the workspace's central store of work products (indexes, a catalog, and cross-domain overviews) without copying domain canons.

## What belongs here

- the folder's purpose and the “canon stays with the domain + catalog + cross-domain overviews” model;
- a map of its sections: `CATALOG.md`, `FACTS.md`, optional `DECISION_LOG.md` and `WORK_LOG.md`, `BACKLOG.md`, `INDEXES/`, `crosscutting/`, `_inbox/`;
- the rules for adding a work product and for how projects and processes find what they need through `RELEVANT_GROUNDWORK.md`.

## What does not belong here

- full copies of domain how-to guides kept “just in case”;
- secrets, tokens, or personal paths from a specific machine;
- a plan for a separate product (that is the role of the project type).

---

## Example

> For the “Training Center / personal structure lab” workspace

**Folder purpose:** a single place to find work products: what exists, where the canon lives, and which cross-domain overviews are already mature.

**Model:**
| What | Where it lives |
|-----|-----------|
| Domain canon (skills, rules, scripts, project FACTS) | With the domain owner: a project folder, a process folder, assistant rules… |
| Topic indexes | `INDEXES/` |
| Cross-domain overviews with no domain home | `crosscutting/` |
| Unified entry registry | `CATALOG.md` |
| Drafts awaiting classification | `_inbox/` |

**How to add a work product:**
1. If it has a strong domain home — leave the canon there; add a row to `CATALOG.md` and, when needed, to `INDEXES/`.
2. If it has no home (a cross-domain overview) — put it in `crosscutting/` and register it in `CATALOG.md`.
3. In the affected projects and processes — update their `RELEVANT_GROUNDWORK.md`.

**Symbolic links** are not used as a catalog-building system: only Markdown links and the table in `CATALOG.md`.
