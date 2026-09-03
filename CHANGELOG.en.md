# Changelog

*[Russian version: CHANGELOG.md](CHANGELOG.md)*

All notable changes to this public workspace structure template.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

A version ships with the publication: every update to the repository contents gets a number and a date at once. There is no accumulating `Unreleased` section.

What the version digits mean in this repository:

- **MAJOR** — the layout of `template/` or of the root explainer paths changes; a type or a file is removed or renamed. Updating from an earlier copy of the template takes manual work.
- **MINOR** — folder types, required skeleton files, or substantial additions to `STRUCTURE_GUIDE.md` / the workflow are introduced. An install updates over the previous copy.
- **PATCH** — wording edits that leave the structure inventory and the meaning of the types unchanged.

The scheme matches versioning of the public rules corpus [ElucidatingYourLLM](https://github.com/FrigateCaptain/ElucidatingYourLLM) (SemVer with a stated contract, a release on every push, no `Unreleased` section).

---

## [1.5.0] — 2026-09-04

### Added

- In skill `structure-revise` and in `workflows/STRUCTURE_WORKFLOW.md`: determine a folder's type from three axes (file set, folder-registry record, journals). If the axes disagree — ask. If there is no doubt — name the type at once and, in parentheses, the arguments on each axis. A target type the user named explicitly remains the target even when the file set still belongs to another type (that is a type change)
- In the GUIDE, the workflow, and the skills: files and folders that are not in `template/<type>/` are normal in a live folder; the skeleton is a minimum set of roles, not an exhaustive list of what is allowed

---

## [1.4.0] — 2026-09-04

### Added

- English companion files next to the Russian originals: `STRUCTURE_GUIDE.en.md`, `workflows/STRUCTURE_WORKFLOW.en.md`, `CHANGELOG.en.md`, and `SKILL.en.md` in each of the three `.agents/skills/` packages
- Full English placeholder tree at `en/template/` (Russian `template/` stays in place)
- Language switcher at the top of `STRUCTURE_GUIDE.md` ↔ `STRUCTURE_GUIDE.en.md` and `CHANGELOG.md` ↔ `CHANGELOG.en.md`

### Changed

- Root `README.md` is bilingual (English block first, then Russian), following the ElucidatingYourLLM layout; it links to the English Structure Guide

---

## [1.3.1] — 2026-09-04

### Added

- Root `LICENSE` file: MIT, copyright FrigateCaptain 2026

---

## [1.3.0] — 2026-09-04

### Added

- Three Agent Skills in `.agents/skills/`: `structure-workspace` (the whole workspace — open and run the workflow), `structure-template` (one folder: the skeleton, or only the missing blanks), `structure-revise` (one folder: revision, type change, splitting text already on disk)
- In `workflows/STRUCTURE_WORKFLOW.md`: composition canon read from disk (`CHANGELOG`, GUIDE, `find template/`); three-column check of an existing folder; existing files must not be overwritten by the template; procedure for changing a folder's type (five actions per file); decisions and work are separate journal entries; do not create a meta-registry as a side task

### Changed

- Root `README.md`: instruction-selection table keyed to task scope; the skill listed in the “What's in the kit” table
- `STRUCTURE_GUIDE.md`: pointer to the whole-workspace workflow and the one-folder skill

---

## [1.2.0] — 2026-08-17

### Added

- Required journals `DECISION_LOG.md` and `WORK_LOG.md` in the project and process types
- Optional slots for the same journals in settings-n-servers, groundwork, meta-registry, and storage
- Optional process slots: `CYCLE_LOG.md`, `VERSION_LOG.md`, `RELEASE_LOG.md`
- Placeholder `template/meta-registry/WORKSPACE_EXTERNAL_FOLDERS.md`
- `*.bak` mask in `.gitignore`

### Changed

- Root `README.md`: H1 and a framed hook on environment markup (“where things live”) and context handoff; sections “Who this is for and why”, “What this is, in outline”, “Where it came from”
- `STRUCTURE_GUIDE.md`: opening paragraph on markup and context handoff; six-type trees aligned with `template/`; journal roles; key-files reference expanded with tree wording; method notes (which journals are required, the storage/groundwork boundary)
- `workflows/STRUCTURE_WORKFLOW.md`: required and optional journals at install time

---

## [1.1.1] — 2026-08-03

### Removed

- `STYLE_NOTES.md` — authors' internal style rules; not part of the template for users
- `publish.yaml.example` — sample internal publication flag; not part of the template for users

---

## [1.1.0] — 2026-08-02

### Added

- `groundwork` folder type in `template/groundwork/` (catalog, indexes, cross-cutting overviews)
- Required skeleton file `RELEVANT_GROUNDWORK.md` in the project, process, storage, settings-n-servers, and meta-registry types

### Changed

- Root `README.md`, `STRUCTURE_GUIDE.md`, `workflows/STRUCTURE_WORKFLOW.md` — six types; groundwork and `RELEVANT_GROUNDWORK.md` in the standard skeleton
- Order and wording of types in the README table (storage last)

---

## [1.0.0] — 2026-08-02

### Added

- Public template skeleton: `README.md`, `STRUCTURE_GUIDE.md`, `STYLE_NOTES.md`
- Five types in `template/`: project, process, storage, settings-n-servers, meta-registry
- Workflow for an LLM assistant: `workflows/STRUCTURE_WORKFLOW.md`

---

[1.5.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.4.0...v1.5.0
[1.4.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.3.1...v1.4.0
[1.3.1]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.3.0...v1.3.1
[1.3.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.1.1...v1.2.0
[1.1.1]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/releases/tag/v1.0.0
