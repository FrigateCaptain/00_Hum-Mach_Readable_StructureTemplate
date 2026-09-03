# WORKSPACE_EXTERNAL_FOLDERS

## Why this file exists

A list of multi-root workspace root folders that sit **outside** the main catalog of rules and projects. A human-readable reference; the machine-readable source of the set is the workspace file (`.code-workspace` or equivalent).

## What belongs here

- terms: what counts as a workspace root folder and what counts as external relative to the main directory;
- the full list of root folders: display name, path as in the workspace file, purpose;
- separately — the list of external folders.

## What does not belong here

- the canonical registries of projects and processes (those are `registries/`);
- an overview of workspace layers (that is `WORKSPACE_REVIEW.md`);
- secrets, tokens, or personal data from a specific machine.

---

## Example

> For the “Your team name” team workspace

**Terms**

**Workspace root folder** — one of the entries in `folders` of a multi-root workspace: a separate tree in the editor sidebar.

**External folders** — root folders whose path does not start with the workspace's main directory (they sit beside it).

**Full list of root folders**

| Display name | Path (as in the workspace file) | Purpose |
|------------------|------------------------------|------------|
| Main | `./workspace-root` | Rules, projects, scripts |
| PublicRules | `../public-rules` | A separate git repository of rules |
| SiteWorkingCopy | `../site` | Working copy of the site |

**External folders** (not under the main directory): `../public-rules`, `../site`.
