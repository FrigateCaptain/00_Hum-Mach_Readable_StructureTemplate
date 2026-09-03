# DECISION_LOG

In a process-type folder this log is required. Put decisions about the process's own logic and structure here. Cycle runs, internal versions, and external releases belong in the separate optional slots `CYCLE_LOG.md`, `VERSION_LOG.md`, and `RELEASE_LOG.md`.

## Why this file exists

The folder's decision log. Record choices that the owner could have made differently and that establish a standard going forward.

## What belongs here

- a choice between alternatives: “chose A, rejected B; FACTS now records the following value”;
- a standard that remains in effect until a later decision changes it;
- a link to where the current outcome is recorded (usually `FACTS.md`).

Phrase each entry in the past tense of choosing (“chose,” “rejected,” “the standard is ...”), not as a report of completed work.

## What does not belong here

Work items such as “created a file,” “moved to archive,” or “completed the check.” Those belong in the work log (`WORK_LOG.md`).

Stop-list of verbs and phrases for this file: created (создан, создано), moved (перенесено), moved out (вынесен), completed (выполнено), check completed (проверка выполнена), update completed (актуализация выполнена).

## Before you write an entry

Two questions:

1. Could the owner have chosen differently, with the choice becoming the standard going forward?
2. Does the event have a performer and an artifact (a file, a check, or a transfer)?

If only the first answer is “yes,” record the entry only in `DECISION_LOG.md`.
If only the second answer is “yes,” record the entry only in `WORK_LOG.md`.
If both answers are “yes,” write two distinct entries, not the same paragraph in both files.

---

## Example

> For the process “Managing AI-assistant rules”

**April 10, 2026.** Chose a monthly review of the full set on the first Monday and rejected review “as drafts accumulate.” Going forward, FACTS records: scheduled review — once a month, on the first Monday.
