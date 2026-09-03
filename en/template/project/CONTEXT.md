# CONTEXT

## Why this file exists

This file explains why the project came into being and in what context it exists.

## What belongs here

- the premises for starting it;
- stakeholders and related loops;
- the history of decisions and important assumptions.

## What does not belong here

- a canonical list of facts and parameters;
- the current work plan;
- a list of deferred ideas instead of `BACKLOG.md`.

---

## Example (AI / workspace)

> For the project “Publishing a training course on workspace structure”

The course is created in response to requests from participants in a closed cohort — they want a standard structure they can pick up and apply immediately, without a long setup.

Main stakeholders: course participants (up to 50 people), the program curator (responsible for the final review), the technical team (support for the public repository on GitHub).

Decision history:
- In March 2026 they dropped a Notion template in favor of a GitHub repository — it is easier to fork and does not require an account.
- In April 2026 they decided to split the “instruction for a human” (STRUCTURE_GUIDE.md) and the “instruction for an LLM” (workflow) — testing showed that mixing them in one file is awkward.

Assumptions: participants are already familiar with basic Git and Markdown.

## Example (another domain)

> For the project “Opening the café "У парка" — breakfast and lunch format”

The project was started after an observation: within a 700-meter radius of the chosen location there are 4 business centers and 1 coworking space, but not a single place offering a quick breakfast and a sit-down lunch. Existing coffee shops close by 16:00 and miss the lunch traffic.

Main stakeholders:
- the business owners (two partners, 60/40 shares);
- the premises landlord — the residential complex's management company;
- the future head chef (hired at phase 2, shapes the menu and purchasing).

Decision history:
- A full-service restaurant with 80 seats was considered first — it was rejected because of high capital outlay and a long payback (~3 years instead of 14 months).
- They then chose between window-service street food and a seated format — they chose the latter after a survey of 60 potential guests: 78% named “a place to sit and work on a laptop” as the key factor.
- In the end they rejected a franchise in favor of their own brand — the franchise supplied ready-made processes but did not allow the menu to be adapted flexibly to the location.

Assumptions: weekday pedestrian traffic will not fall below 1,200 people/day (counter data, March 2026); the average lunch check will stay in the 450–650 ₽ range.
