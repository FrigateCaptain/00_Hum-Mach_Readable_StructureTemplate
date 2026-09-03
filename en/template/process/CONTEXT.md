# CONTEXT

## Why this file exists

This file explains why the process exists and in which operational loop it runs.

## What belongs here

- the source of the need for the process;
- participants, roles, and external dependencies;
- agreements that explain the current way of working.

## What does not belong here

- stable reference parameters with no context;
- a list of process steps instead of `workflows/`;
- product-level goals if the folder has already become a project.

---

## Example

> For the process “Managing AI-assistant rules”

The process appeared when LLM rules (`.cursor/rules/`) started changing often and without coordination — a change in one place broke behavior in another. An operational loop was needed for systematic updates.

Participants:
- **Process owner:** Иван К. (initiates changes, final verification).
- **AI assistant:** applies file changes following the workflow instructions.
- **Dependency:** the `llm-rules-base` repository — the external source of base rules.

Agreements:
- Rule changes are recorded in the `SERVICE_CHANGES_LOG.md` of the project they affect.
- Experimental rules live in `BACKLOG.md` until verified, not in the main set.
