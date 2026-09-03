# Workflow: Forming a workspace structure

## Purpose

This workflow is an instruction for an LLM assistant. It runs a dialogue with the user and, from the templates in this repository, forms or restructures the user's **entire** workspace (many folders, types, registries, an installation plan).

The long installation checklist lives **only in this file**. The `structure-workspace` skill (if the kit includes it) only locates this file and executes it.

Related kit instructions cover **one folder**, not the whole workspace:

- `structure-template` — create a skeleton or add only missing files; leave existing text untouched;
- `structure-revise` — revision, type change, renaming, splitting, edits to skeleton files that are already present.

Before this workflow starts, the user should have read [`STRUCTURE_GUIDE.en.md`](../STRUCTURE_GUIDE.en.md) — at least a skim — and have a picture of the folder types and skeleton files. If `STRUCTURE_GUIDE.en.md` is missing, read `STRUCTURE_GUIDE.md` beside it.

## Canon of composition — from disk, not from memory

The canon of file counts and names is **not** stored in this workflow as a memorized list.

1. Read the top section of [`CHANGELOG.en.md`](../CHANGELOG.en.md) (`## [X.Y.Z]`). If that file is missing, read `CHANGELOG.md` beside it. State the version number in one sentence.
2. Read [`STRUCTURE_GUIDE.en.md`](../STRUCTURE_GUIDE.en.md) in full (stage 1) and the section for the chosen type when working on a specific folder. If `STRUCTURE_GUIDE.en.md` is missing, read `STRUCTURE_GUIDE.md` beside it.
3. Capture the actual skeleton: `find en/template/<type> -type f` (paths from this kit's root).
4. If the type tree in the GUIDE does not match `find` — stop and show both lists. Do not choose silently.
5. Do not reconstruct the skeleton from chat memory and do not insert files “as they usually are”.

Treat as the kit root the directory that contains both `STRUCTURE_GUIDE.md` and `template/`. English texts sit beside those Russian paths; they do not replace them as the kit identifier. If this workflow was opened from a different copy — ask for the path. Do not invent the composition.

---

## Stage 1. Eliciting needs

Read [`STRUCTURE_GUIDE.en.md`](../STRUCTURE_GUIDE.en.md) in full. If that file is missing, read `STRUCTURE_GUIDE.md` beside it. Then ask the user:

1. **Folder types.** Show the user the list of six types (project, process, settings-n-servers, groundwork, meta-registry, storage) with brief explanations. Ask:
   - Do all of these types fit, and are they needed?
   - Are there other kinds that are not listed here that they would like to create?

2. **Groundwork and RELEVANT_GROUNDWORK.md — required elements.** A groundwork-type folder and the file `RELEVANT_GROUNDWORK.md` are part of the standard template skeleton (like `README.md`) and are created by default. Do not ask whether “they are needed”. Clarify only the particulars:
   - What to name the groundwork folder (or what name is already in use)?
   - Are there already scattered working materials across the workspace that should be taken into account?
   - Should existing working materials be gathered into groundwork right away, or should the absence of a single folder be recorded as a temporary state (with a mandatory plan to create it)?
   - Are there wishes for the fields and contents of `RELEVANT_GROUNDWORK.md` in folders of types project, process, storage, settings-n-servers, and meta-registry (not about including or excluding the file)?

3. **Additions and remarks.** Ask:
   - Are there additions, remarks, or wishes for particular types?
   - Are there wishes for the skeleton-file composition of specific types, or for their fields?

4. **Logs.** Show the matrix:
   - project and process: `DECISION_LOG.md` and `WORK_LOG.md` are required (like `README.md`);
   - settings-n-servers, groundwork, meta-registry, storage: the same two files are an optional slot; clarify whether to start a live log;
   - process additionally: three optional slots `CYCLE_LOG.md` (cycle execution), `VERSION_LOG.md` (internal versions), `RELEASE_LOG.md` (external releases). The slot name can be chosen at install time. Ask which of the three to start.
   Do not ask whether the required project and process logs “are needed”. Clarify only whether there are wishes for the fields of the entries.

5. **Workspace context.** Clarify:
   - Is this a new workspace from scratch or a restructuring of an existing one?
   - Which LLM tools are in use?
   - Are there already established conventions for naming folders?

Wait for answers to all questions before moving to the next stage.

---

## Stage 2. Forming the structure template

Based on the user's answers and the types in `STRUCTURE_GUIDE.en.md` (if that file is missing, `STRUCTURE_GUIDE.md` beside it):

1. Assemble a custom set of folder types — taking into account which standard types the user accepted, which they declined, and which they want to add. Groundwork and `RELEVANT_GROUNDWORK.md` belong in the standard skeleton by default. The logs `DECISION_LOG.md` and `WORK_LOG.md` are required in project and process; in the other four types — according to the user's answer about the optional slot.
2. For each accepted type, determine the skeleton-file composition — taking into account the user's wishes for fields and contents (including wishes for the contents of `RELEVANT_GROUNDWORK.md`, but not a decision to “include or not”: the file is part of the standard skeleton). For process, include the chosen slots `CYCLE_LOG.md` / `VERSION_LOG.md` / `RELEASE_LOG.md`, or do not copy slots that were not started. Check the file-name composition against `find en/template/<type>`, not against memory.
3. **Registries.** Ask the user whether registries already exist that list all workspace folders with purpose, description, and status. If the user does not know or there are no registries — look through the workspace and suggest where they might be (typical places: workspace root, a meta folder, `registries/`). Based on the result, determine what to do with the registries:
   - **they exist and are current** — treat them as the source of truth for further work;
   - **they exist but are incomplete or outdated** — plan an update;
   - **they do not exist** — plan to create them inside the meta folder.
   Do **not** create the meta layer “while you are at it” if it was not established at this stage.
4. Show the user the resulting structure template as a tree and get confirmation.

---

## Stage 3. Planning actions

Ask the user:

1. **Analysis of existing folders.** Which folders already exist? What does the assistant already see in the workspace? What needs a closer look?

   For **each** such folder:

   - Propose a type (or the current type and the **target** type, if the type is changing). If the target is not named — show the six types from the GUIDE and ask. Do not guess.
   - Capture two lists: the folder's files and `find en/template/<target-type>`.
   - Show three columns:
     - present in the template and in the folder;
     - present in the template, absent from the folder;
     - present in the folder, absent from the template.
   - For the “present in both” column: do not plan replacing the file with the template. If the role in the GUIDE does not match what is in the file (for example, decisions in `FACTS.md` instead of `DECISION_LOG.md`), propose a split: which fragments go into which file, what stays.
   - For the “present in the folder, absent from the template” column: do not plan deletion or a move until the user has named that file and the action.
   - In what form to enter it in the registry (if a meta-registry was established at stage 2 or already exists).

   If the folder **changes type** (it is not receiving a type for the first time) — additionally run the “Changing a folder type” sub-stage below and include its answers in the plan.

2. **Creating new folders.** Which folders need to be created right now? For each — clarify the name and type.

3. Draw up a concrete work plan. The plan is a **list of specific files and actions**, not a general phrase “bring it in line with the template”. In the plan: what to create, what to supplement with missing files, what to split, what to rename, what to leave as extra, what to register in the registries.

Show the plan to the user and get confirmation before executing. Rename nothing, delete nothing, merge nothing, and split nothing across files until the plan is confirmed.

### Changing a folder type

Separate from “just add the files of the new skeleton”.

1. Name the source type and the target type. Show which slots exist only on the source, only on the target, and which match by name (`find en/template/<source>` and `find en/template/<target>`).
2. For each file that is not in the target skeleton, or whose role is changing, ask in **one list**; do not choose silently:

   - **keep** the name and location (a file that is extra relative to the new type stays);
   - **rename** into a slot of the new type (give the new name);
   - **split** the contents across several files of the new type (say which section goes where);
   - **keep a copy** under the former name and open a new slot separately;
   - **move** to another folder / archive — only if the owner said so themselves.

3. Do not overwrite files that match by name (`README.md`, `FACTS.md`, and so on) with the template. If the role boundaries in the GUIDE are different — propose fragment-level edits, not replacing the whole file.
4. Execute only after the answers. If there is no answer for some of the files — leave those files alone.

---

## Stage 4. Execution

Methodically execute **only the approved** plan:

1. Create folders and skeleton files for new entities. Replace the template placeholder with the contents of this folder. Do not copy the instructional “Why this file exists” blocks as the final text unless the user asked to keep the blank. Optional slots — only those chosen at stages 1–2; do not create them silently.
2. Supplement existing folders with **missing** files (column “present in the template, absent from the folder”). Do **not** overwrite files already present under the same name with the template. If the plan includes a split — execute only the confirmed fragments. Do not delete text that has no place in the plan: ask first where to put it.
3. Do not delete or move files that are extra relative to the template unless that was in the confirmed plan.
4. Update registries in the meta-registry **if** the meta layer was established at stage 2 or already existed. Do not create a meta folder “while you are at it”.
5. Links in `RELEVANT_GROUNDWORK.md` — only in the affected folders and only per the plan.
6. If a folder's file composition changed — update that folder's `README.md` (what this is, why it exists, where to look next).
7. After each major block — briefly tell the user what was done.

---

## Guiding principles and the sequence of working through each folder

When working through each folder, also rely on the criteria in the “General structure quality criteria” section below.

When forming and assessing structure, follow these principles.

### Principle 1. Determine the folder's role first

Before creating structure, one question must be answered: is this a project, a process, settings/servers, groundwork, a meta-registry, or storage. An error at this step usually leads to mixed documents and a loss of navigational clarity.

### Principle 2. Provide an explicit entry point

Every significant folder must have a `README.md` that answers at least three questions:

- what this folder is;
- why it exists;
- where to look next.

### Principle 3. Separate kinds of content into different files

Do not mix facts, plans, constraints, backlog, and instructions into one long “universal” document. One file should own one role.

A decision (a norm that could have been otherwise) → `DECISION_LOG.md`. Work (who did it, which artifact) → `WORK_LOG.md`. Do not mix a decision and work in one entry.

### Principle 4. Make canonical storage locations

If a fact belongs with facts, it should have a predictable storage place, for example `FACTS.md`. If a task is deferred, it should go into `BACKLOG.md`. If a step-by-step order of actions is needed, it should live in `workflows/` or a separate instructional document. If a link to groundwork materials is needed — it lives in that folder's `RELEVANT_GROUNDWORK.md`, not in copies of how-tos.

### Principle 5. Explicitly link neighbouring entities

The structure should show relationships with links: to related projects, registries, upstream/downstream folders, public repositories, groundwork materials, and key documents.

---

## General structure quality criteria

These criteria are mandatory at the stage “Guiding principles and the sequence of working through each folder” — when assessing and forming each folder.

- `Findability`: the needed file can be found by name and location without extra explanation.
- `Predictability`: folders and files of the same role are organised the same way.
- `Traceability`: it is clear where the canonical source of a fact is, and where a reference or a derived description is.
- `Separation of concerns`: facts, processes, registries, backlog, and instructions are not mixed into one unreadable document.
- `Navigability`: from `README.md` one can reach the key documents without wandering.
- `Maintainability`: the structure can be extended without chaotic growth and without constant renaming.

---

*Created: 24 April 2026, 22:30*
*Last updated: 4 September 2026, 00:25*
