# CYCLE_LOG

**Optional slot.** Create it when the process is repeating and cycle runs need to be recorded. You may choose the filename at install time; the template shows the slot's canonical name.

## Why this file exists

A log of running the repeating process: what happened in a given cycle.

## What belongs here

- the date or number of the cycle;
- what was carried out in this pass of the process;
- how this cycle differed from the previous one, if it did.

## What does not belong here

- decisions about the process's logic (`DECISION_LOG.md`);
- work that adjusts the process (`WORK_LOG.md`);
- internal versions of the system (`VERSION_LOG.md`);
- external releases (`RELEASE_LOG.md`).

Difference from `WORK_LOG.md`: `WORK_LOG` is process adjustment; `CYCLE_LOG` is process execution.

---

## Example

> For the process “Managing AI-assistant rules”

**Cycle 2026-04 (first Monday of the month).** The scheduled review of the ruleset was carried out. The procedure did not differ from the previous cycle.
