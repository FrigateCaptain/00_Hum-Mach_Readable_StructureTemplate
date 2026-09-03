# FACTS

## Why this file exists

The canonical place for stable facts about the groundwork folder itself: the storage model, ID conventions, and discoverability rules.

## What belongs here

- confirmed decisions about structure and naming;
- the catalog entry ID format;
- agreements on what counts as canon and what is only a pointer.

## What does not belong here

- the full list of work products (that is `CATALOG.md`);
- draft hypotheses from `_inbox/`;
- step-by-step how-to guides (those live in `crosscutting/` or with the domain);
- the log of choosing a standard: “selected A, rejected B” — that goes in `DECISION_LOG.md` if the slot is in use; this file holds the current value after the decision.

---

## Example

> For an `NN_groundwork` folder in a training workspace

**Model:** domain canon stays with its owner; groundwork holds the catalog, indexes, and cross-domain overviews.

**ID naming:** `gw-{layer}-{slug}`, where layer is `idx` | `cc` | `dom`.

**Discoverability:** projects and processes point to the relevant files through a local `RELEVANT_GROUNDWORK.md` and do not copy the texts.

**Symbolic links:** not used as a mirror of the work-product tree.
