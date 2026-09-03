# RELEASE_LOG

**Optional slot.** Create it when the process, its results, or the system it maintains are released **externally**. You may choose the filename at install time; the template shows the slot's canonical name.

## Why this file exists

A log of **external** releases of the process, the process's results, or the system this process maintains.

## What belongs here

- the date and identifier of the external release;
- what became available outside (repository, channel, package);
- how this release differs from the previous external one.

## What does not belong here

- internal versions that were not released externally (`VERSION_LOG.md`);
- a cycle run with no external release (`CYCLE_LOG.md`);
- decisions about the process's logic (`DECISION_LOG.md`).

---

## Example

> For the process “Managing AI-assistant rules”

**2026-05-01.** External release of the ruleset: the public repository was switched to public, announcement in the team channel. There was no previous external release.
