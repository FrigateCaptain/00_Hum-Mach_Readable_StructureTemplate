---
name: structure-revise
description: >-
  English copy of this skill; Cursor reads SKILL.md by default. Revises one
  folder against the current Structure Template: three-axis type check (file
  set, folder registry, journals), three-column diff, type change, splits and
  edits of existing files. Plan in dialogue first; execute only after
  confirmation. Use for structure audit, “what is missing”, changing folder
  type, renaming skeleton files, splitting one file, FACTS vs journals. Do not
  use to only create a folder or add empty missing files — that is skill
  structure-template. Do not use for whole-workspace install —
  structure-workspace / STRUCTURE_WORKFLOW.en.md.
---

# Revising and restructuring a folder

This skill applies to any workspace that has a Structure Template kit (`STRUCTURE_GUIDE.md` + `template/`). English texts sit beside those Russian paths; they do not replace them as the kit identifier.

The canon of file composition is **not** stored in this skill. Each time, read from disk: the top section of `CHANGELOG.en.md` (if missing, `CHANGELOG.md` beside it), the type section in `STRUCTURE_GUIDE.en.md` (if missing, `STRUCTURE_GUIDE.md` beside it), `find en/template/<type>`.

Related skill `structure-template`: a folder from scratch and only missing files, with no edits to text that is already there.

Installing or rebuilding the **entire** workspace — `structure-workspace` / `workflows/STRUCTURE_WORKFLOW.en.md`, not this skill.

## When to apply

- Revision: compare a folder with the canon and show the gaps.
- Restructuring, or first-time structuring of a folder that already has content.
- Changing a folder's type.
- Edits to skeleton files that are already present, when the edits are about structure (the file's role, the boundaries of FACTS / logs / backlog).

## Find the template kit

Look for the directory that contains both `STRUCTURE_GUIDE.md` and `template/`:

1. The root the user named explicitly.
2. Walk up from this `SKILL.en.md` toward parent directories until both are found.
3. A folder whose name contains `StructureTemplate` or `structure-template`.
4. If not found — ask for the path. Do not substitute a skeleton from memory.

## Dialogue rule

Rename nothing, delete nothing, merge nothing, and split nothing across files until the owner has confirmed the plan. The plan is a list of specific files and actions, not a general phrase “bring it in line with the template”.

Files and folders that are not in `template/<type>/` are normal in a live folder. Do not delete them only because they are absent from the skeleton.

## Determining the folder type

Do not infer the type from a single clue, and do not guess.

If the user **explicitly named** the target type — that is the target type, even if the file set and the registry still belong to another type. Then the current type (how the folder was run) and the target may differ: that is a type change, not “the type is unclear”.

If the target type **is not named** — gather three axes, then decide.

1. **File set.** Compare names in the folder with `find en/template/<type>` (if `en/template/` is missing, `find template/<type>`) for the six types in the GUIDE. Which skeletons are closer (which required slots exist only on one type).
2. **Folder registry.** If the workspace has a folder registry (often `registries/PROJECTS_REGISTRY.md`, `PROCESSES_REGISTRY.md`, `STORES_REGISTRY.md` and the like) — how this folder is recorded there. No record — note “not marked in the registry”.
3. **Journals.** What `DECISION_LOG.md`, `WORK_LOG.md`, `CYCLE_LOG.md`, `VERSION_LOG.md`, `RELEASE_LOG.md`, and `CONTEXT.md` say: a goal with an end vs a repeating cycle, external releases, an internal version. No journals — note “no journals”.

**Doubt** (the axes disagree; two types are equally close; the picture is mixed) — show the facts on the three axes and ask which type it is. Do not choose silently.

**No doubt** — name the type at once and, in parentheses, the arguments on each axis: file set; registry; journals.

## Revision steps

1. Read the top section of `CHANGELOG.en.md`. If that file is missing, read `CHANGELOG.md` beside it. State the version.
2. Determine the current type and the target type per “Determining the folder type”. Do not substitute a type “as usual” without the three axes.
3. Capture two lists: the folder's files and `find en/template/<target-type>`.
4. Show the owner three columns:
   - present in the template and in the folder;
   - present in the template, absent from the folder;
   - present in the folder, absent from the template.
5. For files “present in both” — do not rewrite the contents silently. If the role in the GUIDE does not match what is in the file (for example, decisions in `FACTS.md` instead of `DECISION_LOG.md`), propose a split: which fragments go into which file, what stays.
6. Wait for a response on the plan. Then execute only what was confirmed.

Missing files **without** edits to files that are already present may be created in the same pass if the owner confirmed that. If the task was “only add blanks” — that is `structure-template`, not this skill.

## Changing a folder type

Separate from “just add the files of the new skeleton”.

1. Name the source type and the target type. Show which slots exist only on the source, only on the target, and which match by name.
2. For each file that is not in the target skeleton, or whose role is changing, ask in **one list**; do not choose silently:

   - **keep** the name and location (a file that is extra relative to the new type stays);
   - **rename** into a slot of the new type (give the new name);
   - **split** the contents across several files of the new type (say which section goes where);
   - **keep a copy** under the former name and open a new slot separately;
   - **move** to another folder / archive — only if the owner said so themselves.

3. Do not overwrite files that match by name (`README.md`, `FACTS.md`, and so on) with the template. If the role boundaries in the GUIDE are different — propose fragment-level edits, not replacing the whole file.
4. Execute only after the answers. If there is no answer for some of the files — leave those files alone.

## Content edits

Rely on the file roles in the current version of `STRUCTURE_GUIDE.en.md` (if missing, `STRUCTURE_GUIDE.md` beside it): FACTS vs DECISION_LOG vs WORK_LOG vs BACKLOG vs PLAN. Do not mix a decision and work in one entry. Do not delete text that has no place in the plan — ask first where to put it.

## After confirmed changes

- Update the folder's `README.md` if the file composition changed.
- If this workspace has a folder meta-registry — update it only if the owner keeps such a registry; do not create the meta layer “while you are at it”.
- If there is a pointer file to working materials (`RELEVANT_GROUNDWORK.md`) — fix links only in the affected folders and only per the confirmed plan.
