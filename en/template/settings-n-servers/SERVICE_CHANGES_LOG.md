# SERVICE_CHANGES_LOG

## Why this file exists

A log of changes to services, settings, and infrastructure behavior.

## What belongs here

- what exactly was changed;
- where (which server, service, configuration);
- when;
- why;
- with what effect.

## What does not belong here

- canonical facts (use `FACTS.md` for that);
- incident analysis (use `INCIDENTS.md` for that);
- general notes and reflections;
- work on this folder's documents (use `WORK_LOG.md` for that, if the slot is in use);
- a choice of standard (“selected A, rejected B”) — that is `DECISION_LOG.md`, if the slot is in use.

---

## Example

---

### 2026-04-18 — Rate limiting in nginx after an OOM incident

**What was changed:** `limit_req_zone` was added to `nginx.conf` to throttle crawlers.
**Where:** prod-web-01, file `/etc/nginx/nginx.conf`.
**When:** April 18, 2026, 04:00.
**Why:** to prevent a repeat of the nginx OOM crash under heavy bot load.
**Effect:** worker load dropped by ~40% according to Grafana (48 h observation after the change). Legitimate traffic was not affected.

---

### 2026-04-10 — PostgreSQL update 15.3 → 15.6

**What was changed:** PostgreSQL version on prod-db-01.
**Where:** prod-db-01.
**When:** April 10, 2026, 02:00–02:35 (planned window).
**Why:** security patch CVE-2026-XXXX, recommended by the vendor.
**Effect:** no incidents; pre-update backup — in the `company-backups` bucket (snapshot `pg-pre-update-20260410`).
