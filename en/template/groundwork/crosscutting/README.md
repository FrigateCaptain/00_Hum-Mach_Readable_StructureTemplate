# crosscutting — cross-domain overviews

## Why this file exists

Cross-domain how-to guides and overviews that have **no** natural domain home (or whose home is too narrow). The text lives here; `CATALOG.md` holds a pointer row.

## What belongs here

- overviews and workflows that apply to several projects or processes;
- documents with an explicit last-updated date and conditions of applicability.

## What does not belong here

- a runbook for a single service (leave it in the domain folder);
- copies of domain skills or rules that already exist;
- material with secrets and internal addresses that has not been sanitized.

---

## Example file `overview_versioning_docs_repo.md` (excerpt)

```markdown
# Overview: versioning a non-code repository

Purpose: when a repository is mostly documents rather than code —
how to declare a SemVer contract, when to cut a version, and why tags exist.

## When to apply
- you publish a body of rules, templates, or guides;
- readers need to tell a breaking layout change from a wording edit.

## Short contract (example)
- MAJOR — path changes or file deletions that require a manual migration;
- MINOR — new sections or substantial additions;
- PATCH — wording edits with no change to the set of files.
```
