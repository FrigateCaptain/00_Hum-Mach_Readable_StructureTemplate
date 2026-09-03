---
name: structure-template
description: >-
  English copy of this skill; Cursor reads SKILL.md by default. Creates one
  Structure Template folder from scratch or adds only missing skeleton files
  without rewriting existing text. Reads CHANGELOG.en.md, STRUCTURE_GUIDE.en.md
  and find en/template/, not memory (if the English GUIDE or changelog is
  missing, read the Russian file beside it). Use when creating a project,
  process, groundwork, meta-registry, storage or settings-n-servers folder, or
  filling missing blanks. Do not use for revision, type change, renames or
  splitting file contents — that is skill structure-revise. Do not use for
  whole-workspace install — that is structure-workspace /
  STRUCTURE_WORKFLOW.en.md.
---

# Folder skeleton: from scratch and missing files

The canon of file composition is **not** stored in this skill. Each time, read the Structure Template kit from disk.

Related skill `structure-revise`: revision, type change, edits to files that are already present.

Installing or rebuilding the **entire** workspace — `structure-workspace` / `workflows/STRUCTURE_WORKFLOW.en.md`, not this skill.

## Find the template kit

The directory that contains both `STRUCTURE_GUIDE.md` and `template/`. English texts sit beside those Russian paths; they do not replace them as the kit identifier:

1. The root the user named explicitly.
2. Walk up from this `SKILL.en.md` toward parent directories until both are found.
3. A folder whose name contains `StructureTemplate` or `structure-template`.
4. If not found — ask for the path. Do not substitute a skeleton from memory.

## When to apply

- A folder of one of the six types is being created: project, process, settings-n-servers, groundwork, meta-registry, storage.
- An existing folder is **missing** skeleton files: create only the absent ones, without rewriting the contents of files that are already there.

## When not to apply

- Compare a folder with the canon, moves, renames, splitting one file into several, type change — `structure-revise`.
- Edit the text of existing FACTS / PLAN / logs — `structure-revise`.
- Installing the entire workspace — `structure-workspace` / `workflows/STRUCTURE_WORKFLOW.en.md`.

## Steps

1. Read the top section of `CHANGELOG.en.md` (`## [X.Y.Z]`). If that file is missing, read `CHANGELOG.md` beside it. State the version number in one sentence.
2. If the folder type is not named — show the six types from the GUIDE and ask. Do not guess.
3. Read the section for the chosen type in `STRUCTURE_GUIDE.en.md`. If that file is missing, read `STRUCTURE_GUIDE.md` beside it.
4. Capture the actual composition: `find en/template/<type> -type f`. If the GUIDE tree and `find` diverge — stop and show both lists.
5. **From scratch:** create files from the current `en/template/<type>/`. Optional slots — ask, do not create silently. Replace the template placeholder with the contents of this folder. Do not copy the instructional “Why this file exists” blocks as the final text unless the user asked to keep the blank.
6. **Missing files:** compare `find` of the folder with `find en/template/<type>`. Create only what is absent. Do not overwrite files that are already there. Do not delete extras relative to the template.
7. Consumer types (every type except the groundwork folder itself): the file `RELEVANT_GROUNDWORK.md` from the template.
8. If the workspace already has a folder meta-registry — register the new entity **only** if the user asked for it or it follows from their rules for that registry. Do not create the meta layer “while you are at it”.
9. Do **not** delete extras relative to the template without being asked. If a move or a split of text is needed — stop and hand off to `structure-revise`.
