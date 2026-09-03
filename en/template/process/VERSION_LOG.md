# VERSION_LOG

**Optional slot.** Create it when the process or the system that supports it has internal versions. You may choose the filename at install time; the template shows the slot's canonical name.

## Why this file exists

A log of **internal** versions of the process and/or the system that supports the process.

## What belongs here

- the number or label of the internal version;
- what changed in the logic or in the supporting system relative to the previous internal version;
- a link to the decision in `DECISION_LOG.md` if the version follows from a chosen standard.

## What does not belong here

- external releases for users (`RELEASE_LOG.md`);
- running the next cycle with no version change (`CYCLE_LOG.md`);
- work that edits files with no version change (`WORK_LOG.md`).

---

## Example

> For the process “Managing AI-assistant rules”

**Internal classification version 0.3.** Rule categories: `always` / `auto-attached` / `agent-requestable`. This is a version of the schema inside the process, not a public release of the ruleset.
