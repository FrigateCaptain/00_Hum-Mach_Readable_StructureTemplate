# STRUCTURE_GUIDE

*[Russian version: STRUCTURE_GUIDE.md](STRUCTURE_GUIDE.md)*

*A structured layout of the workspace is needed*: for stores, where things live; for projects, what the goals and constraints are and which decisions have already been taken; for processes, which stage of the cycle is underway, and so on.
Then both a human and an LLM can read the same workspace more easily, and the structure itself makes it possible to *accumulate context in a structured way and hand it on correctly*.
That means the LLM will act more appropriately: it will not miss what matters, will not repeat itself, and will not drift off course.

## What this document is

This is a compact, precise description of the different entity types and folders in your workspace, and of the skeleton files that support them.
Read it at least once, even if only by skimming, and form your own picture of what fits you and what you still need to add. Then tell your AI to run the [whole-workspace workflow](workflows/STRUCTURE_WORKFLOW.en.md) or a single-folder skill (`structure-template` / `structure-revise` in `.agents/skills/` — a Cursor agent reads `.agents/skills/<name>/SKILL.md`; an English copy sits beside it as `SKILL.en.md`) — and it will first gather the details from you, then bring the files into the structure you chose. Which file to open is in the root [README](README.md), in the “How to use” section.

These are the types present here:

1. **Project** (project) — a folder with a goal, a plan, constraints, and accumulating facts.
2. **Process** (process) — recurring activity: cycles, distribution, content release.
3. **Settings and servers** (settings-n-servers) — configurations, servers, VPN, infrastructure information.
4. **Work products** (groundwork) — the workspace's central store of work products, structured so that what was produced in one project is easy to reuse in others.
5. **Meta-folder / shared registry** (meta-registry) — an overview of every folder in the workspace, canonical registries, routing.
6. **Store / reference collection** (storage) — reference materials, knowledge, topical collections; materials that did not belong in configurations, work products, or meta-overviews and registries.

Now, more on each type; below that, a reference to the specific skeleton files.

## Map of structural patterns

### 1. Project

Use the project pattern when a folder has a goal, an outcome, constraints, a plan, and accumulating facts.

Typical skeleton:

```text
NN_ProjectName/
├── README.md
├── CONTEXT.md
├── GOALS.md
├── CONDITIONS_n_CONSTRAINTS.md
├── PLAN.md
├── FACTS.md
├── DECISION_LOG.md
├── WORK_LOG.md
├── BACKLOG.md
├── RELEVANT_GROUNDWORK.md
├── subprojects/
└── workflows/
```

How to read this pattern:

- `README.md` is the entry point and navigation.
- `CONTEXT.md` explains why the project exists and what led to it.
- `GOALS.md` records the target state.
- `CONDITIONS_n_CONSTRAINTS.md` describes working conditions and constraints.
- `PLAN.md` shows the stages and the current focus.
- `FACTS.md` stores canonical facts, and also the current outcomes of decisions.
- `DECISION_LOG.md` is the log of decisions taken during the project; it makes it easy to reconstruct the picture and answer “why this way, and not otherwise.”
- `WORK_LOG.md` is the log of work done: each event has a responsible person and an artifact.
- `BACKLOG.md` holds what has been deferred but not lost.
- `RELEVANT_GROUNDWORK.md` points to relevant work products — without copying or duplicating them.
- `subprojects/` is added when a distinct research or work stream appears inside the project.
- `workflows/` holds instructions; a workflow is not a process and does not replace a separate process folder.

### 2. Process

Use the process pattern when the folder describes recurring activity: distributing rules, an operational cycle, content release, service operations, regular analytics.

Typical skeleton:

```text
NN_ProcessName/
├── README.md
├── CONTEXT.md
├── PLAN.md
├── FACTS.md
├── DECISION_LOG.md
├── WORK_LOG.md
├── CYCLE_LOG.md
├── VERSION_LOG.md
├── RELEASE_LOG.md
├── BACKLOG.md
├── RELEVANT_GROUNDWORK.md
└── workflows/
```

How to read this pattern:

- a process has an owner of the working logic, but not the same goal frame that a project has;
- `README.md` explains what is performed regularly;
- `PLAN.md` describes stages, cycles, or current tasks for improving the process;
- `FACTS.md` stores stable settings, links, parameters, and agreements;
- `DECISION_LOG.md` is the log of decisions about the process logic;
- `WORK_LOG.md` is the log of work on adjusting the process;
- `CYCLE_LOG.md`, `VERSION_LOG.md`, `RELEASE_LOG.md` are optional slots; create them according to the criterion; the name can be chosen at install time;
  - `CYCLE_LOG.md` — execution of a repeating cycle (do not confuse with `WORK_LOG.md`: that one is about adjusting the process);
  - `VERSION_LOG.md` — internal versions of the process and/or of the system that serves it;
  - `RELEASE_LOG.md` — external releases of the process, its results, or the serving system;
- `RELEVANT_GROUNDWORK.md` points to work products this cycle uses — without copying or duplicating them;
- `workflows/` contains the concrete instructions for performing the steps.

If a process over time acquires a separate product goal, a set of stakeholders, and a standalone roadmap, it should be split out as a project rather than continuing to masquerade as a process.

### 3. Settings and servers

Use this type when the folder stores configurations, server documentation, VPN settings, infrastructure parameters, and related change logs.

Typical skeleton:

```text
NN_Servers/
├── README.md
├── FACTS.md
├── DECISION_LOG.md
├── WORK_LOG.md
├── SERVICE_CHANGES_LOG.md
├── INCIDENTS.md
├── RELEVANT_GROUNDWORK.md
├── reference/
└── inventories/
```

How to read this type:

- the folder is responsible for infrastructure documentation, not for general-purpose reference knowledge;
- `FACTS.md` stores addresses, ports, identifiers, and key parameters of servers and networks;
- `SERVICE_CHANGES_LOG.md` keeps a log of service changes: what, where, when, why, and with what effect; this is not the folder's `WORK_LOG.md`;
- `INCIDENTS.md` records infrastructure incidents: symptoms, causes, consequences, investigation status;
- `RELEVANT_GROUNDWORK.md` points to cross-cutting groundwork materials that help when maintaining infrastructure documentation;
- `reference/` and `inventories/` group documentation by topic (servers, VPN, proxies, and so on);
- `DECISION_LOG.md` and `WORK_LOG.md` are optional slots: decisions about norms, standards, or requirements for maintaining the folder, and about actual work on its structure.

Difference from a general store: here the emphasis is on systems in operation, with change logs and incidents, not on passive reference information.

### 4. Work products

Use the groundwork pattern when you need a single place in the workspace to find work products: what exists, where the domain canon lives, which indexes and cross-cutting overviews are already mature — without copying domain how-tos “just in case.”
This folder is the unified store and source of truth for navigating work products, so that entities are not multiplied, yet everything remains easy to find;
and when a work product is improved, the updated form becomes available to every folder that uses it.

Typical skeleton:

```text
NN_groundwork/
├── README.md
├── CATALOG.md
├── FACTS.md
├── DECISION_LOG.md
├── WORK_LOG.md
├── BACKLOG.md
├── INDEXES/
├── crosscutting/
└── _inbox/
```

How to read this pattern:

- `README.md` is the entry point: the folder's purpose, the “canon lives with the domain + catalog + cross-cutting overviews” model, and the rules for adding work products;
- `CATALOG.md` is the unified registry of work-product entries (indexes, cross-cutting overviews, links to domain canons outside this folder);
- `FACTS.md` holds stable facts about the groundwork system itself: the storage model, ID conventions, discoverability rules;
- `BACKLOG.md` holds ideas and improvements to the groundwork system itself that sit outside the current focus;
- `INDEXES/` holds topical indexes (links to materials, without duplicating canons);
- `crosscutting/` holds cross-cutting overviews that have no strong domain home;
- `_inbox/` holds drafts awaiting classification;
- `DECISION_LOG.md` and `WORK_LOG.md` are optional slots: decisions about norms, standards, or requirements for maintaining the work-product system, and about actual work on its structure.

Operating model:

| What | Where it lives |
|-----|-----------|
| Domain canon (skill, rules, scripts, project FACTS) | With the domain owner: a project folder, a process folder, assistant rules… |
| Topic indexes | `INDEXES/` |
| Cross-cutting overviews with no domain home | `crosscutting/` |
| Unified entry registry | `CATALOG.md` |
| Drafts awaiting classification | `_inbox/` |

How to add a work product:

1. If it has a strong domain home — leave the canon there; add a row to `CATALOG.md` and, when needed, to `INDEXES/`.
2. If it has no home (a cross-cutting overview) — place it in `crosscutting/`, register it in `CATALOG.md`.
3. In the affected folders of types project, process, storage, settings-n-servers, and meta-registry — update their `RELEVANT_GROUNDWORK.md`.

Symbolic links are not used as a catalog assembly system: Markdown links and the table in `CATALOG.md` only.

Difference from storage:

- **storage** / store / reference collection — keeps topical materials and canonical information “in place”;
- **groundwork** / work products — does not replace domain canons and does not collect second copies of how-tos: it catalogs, indexes, and holds cross-cutting overviews, while projects and processes find what they need through the local `RELEVANT_GROUNDWORK.md` present in each folder.

> For the “Training Center / Personal Structure Lab” workspace
>
> **Folder purpose:** a single place to find work products: what exists, where the canon lives, which cross-cutting overviews are already mature.
>
> **Discoverability:** projects and processes point to relevant files through a local `RELEVANT_GROUNDWORK.md`, without copying the texts.

### 5. Meta-folder / shared registry

Use this pattern when the folder describes not one subject area, but the state of the whole folder system: an overview of the workspace layer, canonical registries, shared routing rules, shared backlog lists, and maintenance workflows. A typical workspace-overview meta-folder belongs to this pattern.

Typical skeleton:

```text
NN_AboutWorkspace/
├── README.md
├── WORKSPACE_REVIEW.md
├── WORKSPACE_EXTERNAL_FOLDERS.md
├── DECISION_LOG.md
├── WORK_LOG.md
├── BACKLOG.md
├── RELEVANT_GROUNDWORK.md
├── registries/
│   ├── PROJECTS_REGISTRY.md
│   ├── PROCESSES_REGISTRY.md
│   ├── STORES_REGISTRY.md
│   ├── AREAS_REGISTRY.md
│   ├── OTHER_FOLDERS_REGISTRY.md
│   └── GITHUB_REPOS_REGISTRY.md
└── workflows/
```

How to read this pattern:

- the folder is responsible for an overview of the whole system, not for executing a single project;
- `README.md` works as navigation through the folder, not as the source of truth for every entity;
- `WORKSPACE_REVIEW.md` gives a summary overview, but does not replace the canonical registries;
- `WORKSPACE_EXTERNAL_FOLDERS.md` lists the root folders of a multi-root workspace that sit outside the main directory;
- `registries/` holds canonical registries by entity type;
- `BACKLOG.md` stores tasks for developing the project-management system itself;
- `RELEVANT_GROUNDWORK.md` points to groundwork materials useful when maintaining the overview layer and the registries;
- `workflows/` describes standardized actions, for example creating a subproject and updating the overview layer;
- `DECISION_LOG.md` and `WORK_LOG.md` are optional slots: decisions about norms, standards, or requirements for maintaining the meta-folder, and about actual work on its structure.

A meta-folder must not absorb the contents of individual projects. Its role is to connect, register, and route.

### 6. Store / reference collection

Use this type when the folder is needed as a place to store knowledge, resource lists, or topical materials — and those materials are not configurations, work products, or meta-overviews and registries.

Typical skeleton:

```text
NN_KnowledgeBase/
├── README.md
├── FACTS.md
├── DECISION_LOG.md
├── WORK_LOG.md
├── RELEVANT_GROUNDWORK.md
├── reference/
├── inventories/
└── templates/
```

How to read this type:

- the folder's main job is not “complete a project,” but “make the needed information quick to find and check”;
- `README.md` explains the makeup of the sections and is the entry point;
- `FACTS.md` stores canonical parameters, identifiers, and confirmed decisions;
- `RELEVANT_GROUNDWORK.md` links the store to relevant indexes and overviews in the groundwork folder;
- nested folders group materials by topic, not by the accidental origin of files;
- `DECISION_LOG.md` and `WORK_LOG.md` are optional slots: decisions about norms, standards, or requirements for maintaining the store, and about actual work on its structure.

Reference documents must not be mixed with current planning and the backlog stream. If a separate piece of work with a goal and stages starts inside the store, it is better to take it out into a project or subproject.

## Supporting principles

### Principle 1. Determine the folder's role first

Before creating a structure, answer one question: is this a project, a process, settings/servers, groundwork, a meta-registry, or a store. A mistake at this step usually leads to mixed documents and a loss of navigational clarity.

### Principle 2. Provide an explicit entry point

Every significant folder should have a `README.md` that answers at least three questions:

- what this folder is;
- why it exists;
- where to look next.

### Principle 3. Split content types across different files

Do not mix facts, plans, constraints, backlog, and instructions in one long “universal” document. One file should own one role.

### Principle 4. Make canonical storage locations

If a fact belongs with facts, it should have a predictable storage place, for example `FACTS.md`. If a task is deferred, it should go into `BACKLOG.md`. If a step-by-step procedure is needed, it should live in `workflows/` or a separate instructional document.

### Principle 5. Explicitly link neighboring entities

The structure should show connections through links: to related projects, registries, upstream/downstream folders, public repositories, groundwork materials, and key documents.

## Key files and how to work with them

The list below is not every possible document, but the main structural roles that repeat across the confirmed workspace patterns. Not every file is required in every type, but each has a clear area of responsibility.

The `template/<type>/` skeleton is a minimum set of roles. Files and folders that are not in the template (materials, drafts, archive, reviews, working scripts) are **normal** in a live folder. Do not delete them or “fit” the folder to the skeleton only because those extras are absent from the template.

### [README.md](en/template/project/README.md)

- Role: entry point and navigation through the folder.
- What to store: what this folder is, why it exists, what in it is primary, where to look next.
- When to update: when the set of files, the folder's status, related resources, or the link structure changes.
- What not to do: do not turn `README.md` into a dump of every fact, plan, and decision.
- Example: [`en/template/project/README.md`](en/template/project/README.md)

### [CONTEXT.md](en/template/project/CONTEXT.md)

- Role: explain the origin and the context in which the folder appeared.
- What to store: premises, stakeholders, decision history, assumptions, the related external and internal circuit.
- When to update: when the frame of the task, the launch context, or the accepted grounds change.
- What not to do: do not let it stand in for `FACTS.md` or `PLAN.md`.
- Example: [`en/template/project/CONTEXT.md`](en/template/project/CONTEXT.md)

### [GOALS.md](en/template/project/GOALS.md)

- Role: record the target state.
- What to store: the main goal, sub-goals, expected outcomes, criteria of successful achievement, and anti-goals when needed.
- When to update: when the meaning of the outcome changes, not merely the course of execution.
- What not to do: do not mix goals with current steps and backlog tasks.
- Example: [`en/template/project/GOALS.md`](en/template/project/GOALS.md)

### [CONDITIONS_n_CONSTRAINTS.md](en/template/project/CONDITIONS_n_CONSTRAINTS.md)

- Role: show the conditions under which the work is done.
- What to store: resources, constraints, dependencies, risks, external conditions, and time frames.
- When to update: when new constraints, risks, or dependencies appear, or when the frames change.
- What not to do: do not hide constraints across different documents if they systematically affect the work.
- Example: [`en/template/project/CONDITIONS_n_CONSTRAINTS.md`](en/template/project/CONDITIONS_n_CONSTRAINTS.md)

### [PLAN.md](en/template/project/PLAN.md)

- Role: show how the work is actually moving.
- What to store: stages, task status, current focus, next step.
- When to update: when the order, statuses, or nearest steps change.
- What not to do: do not keep long-lived canonical facts in `PLAN.md`; do not let it stand in for `WORK_LOG.md`.
- Example: [`en/template/project/PLAN.md`](en/template/project/PLAN.md)

### [FACTS.md](en/template/project/FACTS.md)

- Role: be the canonical source of facts.
- What to store: paths, URLs, identifiers, recorded decisions, technical parameters, stable definitions.
- When to update: when a new confirmed fact appears, or an already canonized value changes.
- What not to do: do not duplicate the same facts in several places without need; do not write a choice log here (“selected A, rejected B”) — that belongs in `DECISION_LOG.md`.
- Example: [`en/template/project/FACTS.md`](en/template/project/FACTS.md)

### [BACKLOG.md](en/template/project/BACKLOG.md)

- Role: hold deferred but not lost tasks and questions.
- What to store: ideas, later iterations, open issues, tasks outside the current plan.
- When to update: when something is deliberately deferred, or a new topic for later work appears.
- What not to do: do not turn the backlog into the current working plan.
- Example: [`en/template/project/BACKLOG.md`](en/template/project/BACKLOG.md)

### [RELEVANT_GROUNDWORK.md](en/template/project/RELEVANT_GROUNDWORK.md)

- Role: a local index of materials in a groundwork-type folder that matter specifically to this folder.
- What to store: links to relevant indexes (`INDEXES/`), cross-cutting overviews (`crosscutting/`), and, when needed, a row or section of `CATALOG.md`; a short note on why the link is needed by this folder.
- When to update: when a connection appears or changes to groundwork materials that are actually used in this folder's work.
- What not to do: do not copy full overview texts; do not duplicate this folder's own domain canons; do not collect links “just in case” with no connection to current work.
- Example: [`en/template/project/RELEVANT_GROUNDWORK.md`](en/template/project/RELEVANT_GROUNDWORK.md)
- Analogues: [`en/template/process/RELEVANT_GROUNDWORK.md`](en/template/process/RELEVANT_GROUNDWORK.md), [`en/template/storage/RELEVANT_GROUNDWORK.md`](en/template/storage/RELEVANT_GROUNDWORK.md), [`en/template/settings-n-servers/RELEVANT_GROUNDWORK.md`](en/template/settings-n-servers/RELEVANT_GROUNDWORK.md), [`en/template/meta-registry/RELEVANT_GROUNDWORK.md`](en/template/meta-registry/RELEVANT_GROUNDWORK.md)

A backbone file for the project, process, storage, settings-n-servers, and meta-registry types. The groundwork folder itself does not need this file: that is where the catalog, indexes, and overviews live.

### [DECISION_LOG.md](en/template/project/DECISION_LOG.md)

- Role: the folder's decision log. A log of decisions taken while the folder was being worked on; it makes it easy to reconstruct the picture and answer “why this way, and not otherwise.”
- What to store: things that could have gone otherwise by the owner's will and that remain in force as a standard: “selected A, rejected B; from now on FACTS holds such-and-such a value.” In a project — decisions about the course of the project; in a process — decisions about the process logic.
- When to update: when a variant is chosen that will from then on be treated as the standard.
- What not to do: do not put work here (“file was created,” “moved,” “check was completed”). Stop list: created, moved, extracted, completed, check completed, update completed.
- Before writing: two questions (is it a standard by the owner's will? is there a responsible person and an artifact?). If both answers are “yes” — two distinct wordings, not one paragraph in two files.
- Required in project and process; in the other types — an optional slot.
- Example: [`en/template/project/DECISION_LOG.md`](en/template/project/DECISION_LOG.md)
- Analogues: [`en/template/process/DECISION_LOG.md`](en/template/process/DECISION_LOG.md), [`en/template/settings-n-servers/DECISION_LOG.md`](en/template/settings-n-servers/DECISION_LOG.md), [`en/template/groundwork/DECISION_LOG.md`](en/template/groundwork/DECISION_LOG.md), [`en/template/meta-registry/DECISION_LOG.md`](en/template/meta-registry/DECISION_LOG.md), [`en/template/storage/DECISION_LOG.md`](en/template/storage/DECISION_LOG.md)

### [WORK_LOG.md](en/template/project/WORK_LOG.md)

- Role: the folder's work log. A log of work and of what was done: each event has a responsible person and an artifact.
- What to store: things that have a responsible person and an artifact: “file X was created,” “checked that the tag matches the CHANGELOG.” If a decision already exists: “the standard from the DECISION_LOG dated such-and-such was recorded in FACTS.” In a process — work on adjusting the process (cycle execution is `CYCLE_LOG.md`).
- When to update: when work on an artifact is finished.
- What not to do: do not put decisions here (“approved,” “decided,” “adopted”). Stop list: approved, decided, adopted.
- Before writing: the same two questions and the same split rule as for `DECISION_LOG.md`.
- Required in project and process; in the other types — an optional slot. In a process do not confuse it with `CYCLE_LOG.md`: `WORK_LOG` is process adjustment, `CYCLE_LOG` is cycle execution.
- Example: [`en/template/project/WORK_LOG.md`](en/template/project/WORK_LOG.md)
- Analogues: [`en/template/process/WORK_LOG.md`](en/template/process/WORK_LOG.md), [`en/template/settings-n-servers/WORK_LOG.md`](en/template/settings-n-servers/WORK_LOG.md), [`en/template/groundwork/WORK_LOG.md`](en/template/groundwork/WORK_LOG.md), [`en/template/meta-registry/WORK_LOG.md`](en/template/meta-registry/WORK_LOG.md), [`en/template/storage/WORK_LOG.md`](en/template/storage/WORK_LOG.md)

### [CYCLE_LOG.md](en/template/process/CYCLE_LOG.md)

- Role: optional log of executing a repeating process.
- What to store: the date or number of the cycle, what was done in this pass, differences from the previous cycle if any.
- When to update: after a cycle is completed, if the slot has been created.
- What not to do: do not put process adjustment here (`WORK_LOG.md`), internal versions (`VERSION_LOG.md`), or external releases (`RELEASE_LOG.md`).
- The file name can be chosen at install time; the template uses the canonical slot name.
- Example: [`en/template/process/CYCLE_LOG.md`](en/template/process/CYCLE_LOG.md)

### [VERSION_LOG.md](en/template/process/VERSION_LOG.md)

- Role: optional log of internal versions of the process and/or of the system that serves it.
- What to store: the internal version label and how it differs from the previous internal one.
- When to update: when the internal version changes, if the slot has been created.
- What not to do: do not confuse with an external release (`RELEASE_LOG.md`) or with cycle execution that does not change the version (`CYCLE_LOG.md`).
- The file name can be chosen at install time.
- Example: [`en/template/process/VERSION_LOG.md`](en/template/process/VERSION_LOG.md)

### [RELEASE_LOG.md](en/template/process/RELEASE_LOG.md)

- Role: optional log of external releases of the process, its results, or the serving system.
- What to store: the date and identifier of the external release, what became available outside.
- When to update: after an external release, if the slot has been created.
- What not to do: do not put internal versions that were not released outside (`VERSION_LOG.md`).
- The file name can be chosen at install time.
- Example: [`en/template/process/RELEASE_LOG.md`](en/template/process/RELEASE_LOG.md)

### [WORKSPACE_EXTERNAL_FOLDERS.md](en/template/meta-registry/WORKSPACE_EXTERNAL_FOLDERS.md)

- Role: a list of root folders of a multi-root workspace that sit outside the main directory.
- What to store: terms, a complete list of root folders, and separately — the external folders.
- When to update: when the set of folders in the workspace file changes.
- What not to do: do not let this file stand in for the registries in `registries/`, and do not duplicate the layer overview from `WORKSPACE_REVIEW.md`.
- Example: [`en/template/meta-registry/WORKSPACE_EXTERNAL_FOLDERS.md`](en/template/meta-registry/WORKSPACE_EXTERNAL_FOLDERS.md)

### [INCIDENTS.md](en/template/settings-n-servers/INCIDENTS.md)

- Role: record incidents and problem investigations for systems where this actually matters.
- What to store: incident date, symptoms, affected components, causes, consequences, investigation status, related decisions.
- When to update: on every significant incident, and when new information appears on a case already opened.
- What not to do: do not mix incidents with ordinary backlog tasks and general notes.
- Example: [`en/template/settings-n-servers/INCIDENTS.md`](en/template/settings-n-servers/INCIDENTS.md)

### [SERVICE_CHANGES_LOG.md](en/template/settings-n-servers/SERVICE_CHANGES_LOG.md)

- Role: keep a log of changes to services, settings, and infrastructure behavior.
- What to store: what exactly was changed, where, when, why, and with what effect.
- When to update: immediately after a systemically significant setting, service, or infrastructure configuration is changed.
- What not to do: do not leave such changes only in chat memory or in incidental technical notes; do not put work on the folder's documents here (`WORK_LOG.md`) or the choice of a standard (`DECISION_LOG.md`).
- Example: [`en/template/settings-n-servers/SERVICE_CHANGES_LOG.md`](en/template/settings-n-servers/SERVICE_CHANGES_LOG.md)

### [workflows/](en/template/project/workflows/README.md)

- Role: store step-by-step instructions for performing repeatable actions.
- What to store: the sequence of steps, start conditions, check points, and the expected result.
- When to update: when the way of performing the repeatable operation itself changes.
- What not to do: do not confuse a `workflow` with a `process`; a workflow is an instruction inside the structure, not a type of root folder.
- Example: [`en/template/project/workflows/README.md`](en/template/project/workflows/README.md)

## What makes the structure human-readable

- A reader quickly understands what the folder is, why it exists, and where to start; that requires an explicit entry through `README.md`.
- Folder and file names are self-documenting and do not require guessing the meaning from the author's private context.
- The structure is easy to scan at a glance: moderate depth, predictable sections, a single order of key files.
- Documents separate different types of content: context, goals, constraints, plan, facts, decisions, work, backlog, incidents, workflow, links to groundwork.
- Important connections are visible as links to related projects, registries, upstream/downstream folders, public repositories, and key documents.

## What makes the structure LLM-readable

- Each type of information has a predictable canonical storage place; one type of fact is not smeared across several files without need.
- Recurring documents use a stable template and the same internal section logic.
- Headings, lists, tables, and the folder tree are semantically explicit, so a model can extract the structure reliably.
- Documents are atomic enough: one file owns one role and does not mix facts, plan, decisions, work, backlog, and a reference dump at the same time.
- Names of entities and terms are used consistently; the same type of object is not renamed without reason in different places.

## Shared quality criteria for the structure

- `Findability`: the needed file can be found by name and place without extra explanation.
- `Predictability`: folders and files with the same role are built the same way.
- `Traceability`: it is clear where the canonical source of a fact is, and where a link or a derived description is.
- `Separation of concerns`: facts, processes, registries, backlog, and instructions are not mixed into one unreadable document.
- `Navigability`: from `README.md` one can reach the key documents without wandering.
- `Maintainability`: the structure can be extended without chaotic growth and without constant renaming.

## Methodological notes

### Logs in the skeleton

In the **project** and **process** skeletons, two logs are required: `DECISION_LOG.md` (standards that could have been otherwise) and `WORK_LOG.md` (work with a responsible person and an artifact). In the other four types the same files are an optional slot. A process additionally has three optional slots: `CYCLE_LOG.md`, `VERSION_LOG.md`, `RELEASE_LOG.md`.

### On “knowledge bases”

A classic knowledge base often sits on the boundary between storage and groundwork: ready answers and how-tos tend toward work products (groundwork / domain canon), while a “shelf” of files and collections without a how-to catalog role tends toward storage. That is why the storage example in the root README is not a single “knowledge base”; instead there are three more unambiguous cases.

## A note on PARA

PARA (Projects, Areas, Resources, Archives) can be used as an optional heuristic for an initial grouping of materials, if it helps bring order faster. But PARA is not a required foundation of this template: here the basic unit is the folder's structural pattern and its semantic role, not tying the whole system to one classification.

---

*Created: 14 April 2026, 13:55*
*Last updated: 4 September 2026, 01:55*
