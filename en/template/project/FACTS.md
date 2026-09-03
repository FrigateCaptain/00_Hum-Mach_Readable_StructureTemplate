# FACTS

## Why this file exists

This file is the canonical place for the project's stable facts.

## What belongs here

- confirmed paths, URLs, identifiers, and parameters;
- adopted decisions that need to be checked quickly;
- definitions that other documents point to.

## What does not belong here

- temporary notes and draft hypotheses;
- a step-by-step work plan;
- duplicates of the same facts in several wordings without need;
- the log of choosing a standard: “chose A, rejected B” belongs in `DECISION_LOG.md`; put the current value here after the decision.

---

## Example

> For the project “Publishing a training course on workspace structure”

**Repository:**
- GitHub: `https://github.com/your-username/workspace-structure-template`
- Status: private → moving to public on May 1, 2026.

**Technical decisions:**
- Template-file language: Russian (primary audience — Russian-speaking managers).
- Date format in documents: `ДД месяца ГГГГ, ЧЧ:ММ` (no ISO format, for readability).
- Default branch: `main`.

**Team agreements:**
- Final review: curator Анна С. (deadline — April 28, 2026).
- The publication announcement is agreed with the marketing team.

**Dependencies:**
- The template extends the [`llm-rules-base`](https://github.com/your-username/llm-rules-base) ruleset.
