# Physical template

This folder materializes the set of types from `../STRUCTURE_GUIDE.en.md`.

## What is here

- `project/` — a folder template that has a goal, constraints, a plan, and accumulating facts.
- `process/` — a folder template for repeatable activity and work cycles.
- `storage/` — a folder template for reference materials and canonical records.
- `settings-n-servers/` — a folder template for configurations, servers, VPNs, and infrastructure documentation.
- `groundwork/` — a folder template for the central store of work-products (catalog, indexes, cross-cutting overviews).
- `meta-registry/` — a template for the overview layer and the workspace's canonical registries.

In the `project/` and `process/` types, the logs `DECISION_LOG.md` and `WORK_LOG.md` are required. In `storage/`, `settings-n-servers/`, `groundwork/`, and `meta-registry/`, those same two files are an optional slot. In `process/` there are three additional optional slots: `CYCLE_LOG.md`, `VERSION_LOG.md`, `RELEASE_LOG.md`.

The types `project/`, `process/`, `storage/`, `settings-n-servers/`, and `meta-registry/` include a `RELEVANT_GROUNDWORK.md` file — local links to relevant materials from a groundwork-type folder.

`meta-registry/` includes `WORKSPACE_EXTERNAL_FOLDERS.md` — a list of workspace root folders outside the main catalog.

## How to use

- Copy only the matching type, not the entire tree.
- Adapt the file set to the folder's role, while keeping content types separate.
- Check that you stay in sync with `../STRUCTURE_GUIDE.en.md` if you extend the template.

## What not to do

- Do not treat this folder as the only mandatory structure for every case.
- Do not fill the template with real secrets, addresses, tokens, or production data.
- Do not mix files of different roles into one catch-all document.
- Do not copy domain how-to guides into `groundwork/` “just in case” — put links to the owner's canon in the catalog and indexes.
