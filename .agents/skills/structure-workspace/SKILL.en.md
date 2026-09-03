---
name: structure-workspace
description: >-
  English copy of this skill; Cursor reads SKILL.md by default. Installs or
  rebuilds an entire workspace from the Structure Template kit: types
  dialogue, multi-folder plan, registries, then executes
  workflows/STRUCTURE_WORKFLOW.en.md. Use when forming or restructuring the
  whole workspace, first-time template install, or “bring the whole workspace
  to the template”. Do not use for a single folder (create/fill blanks →
  structure-template; revise, change type, split files → structure-revise).
---

# Installing and rebuilding an entire workspace

This skill does not contain the long checklist. The canonical procedure is the file `workflows/STRUCTURE_WORKFLOW.en.md` in the Structure Template kit. Open it and execute it **in full**. Do not reconstruct the steps from memory.

## When to apply

- A new workspace from scratch using this template.
- Restructuring the **entire** space (many folders, types, registries).

## When not to apply

- One folder: create a skeleton or add only missing files — `structure-template`.
- One folder: revision, type change, renaming, splitting, edits to text that is already there — `structure-revise`.

## Steps

1. Find the kit root: the directory that contains both `STRUCTURE_GUIDE.md` and `template/`. English texts sit beside those Russian paths; they do not replace them as the kit identifier. Order:
   - the path the user gave;
   - walk up from this `SKILL.en.md` toward parent directories until both are found;
   - a folder whose name contains `StructureTemplate` or `structure-template`;
   - if not found — ask for the path. Do not substitute a skeleton from memory.
2. Read the top section of `CHANGELOG.en.md`. If that file is missing, read `CHANGELOG.md` beside it. State the version in one sentence.
3. Open `workflows/STRUCTURE_WORKFLOW.en.md` in this root and follow it to the end.
