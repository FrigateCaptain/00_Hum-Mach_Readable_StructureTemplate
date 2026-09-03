# FACTS

## Why this file exists

This file stores the stable settings and rules the process relies on.

## What belongs here

- confirmed links, parameters, roles, and agreements;
- stable start conditions;
- canonical definitions of the entities in use.

## What does not belong here

- temporary decisions that are not yet confirmed;
- a history of changes instead of facts;
- detailed execution steps instead of `workflows/`;
- the log of choosing a standard: “chose A, rejected B” belongs in `DECISION_LOG.md`; put the current value here after the decision.

---

## Example

> For the process “Managing AI-assistant rules”

**Rule locations:**
- Cursor rules: `~/.cursor/rules/` (`.mdc` files).
- Base rules from the public repository: `https://github.com/your-username/llm-rules-base`.

**Roles in the process:**
- Owner: Иван К. — the only person who can approve moving a rule from draft into the main set.

**Start conditions:**
- Scheduled review of the full ruleset — once a month, on the first Monday.
- Unscheduled review — when AI behavior breaks.

**Rule categories (adopted classification):**
- `always` — apply to all files, always.
- `auto-attached` — apply to files by glob pattern.
- `agent-requestable` — only on agent request.
