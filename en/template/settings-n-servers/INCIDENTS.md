# INCIDENTS

## Why this file exists

A record of infrastructure incidents: symptoms, causes, consequences, and the status of the investigation.

## What belongs here

- the date and time of the incident;
- the components affected;
- symptoms and causes found;
- consequences and actions taken;
- the status of the investigation and related decisions.

## What does not belong here

- planned changes (use `SERVICE_CHANGES_LOG.md` for that);
- canonical parameters (use `FACTS.md` for that);
- ordinary backlog tasks.

---

## Example

---

### INC-2026-04-18: prod-web-01 unavailable

**Date and time:** April 18, 2026, 03:22–04:05 (MSK)
**Duration:** ~43 minutes
**Components affected:** prod-web-01 (nginx), all inbound HTTP/HTTPS requests.

**Symptoms:** the site returned `502 Bad Gateway`; Grafana monitoring sent an alert at 03:24.

**Cause:** nginx crashed due to insufficient memory (the OOM killer terminated the process). Peak load from a crawler overloaded the worker pool.

**Actions:**
1. 03:30 — nginx restart: `systemctl restart nginx`.
2. 04:00 — temporary crawler throttling via `nginx.conf` (rate limiting).
3. 04:05 — service restored, monitoring is green.

**Status:** closed. The decision is recorded in `SERVICE_CHANGES_LOG.md` (entry dated 18.04.2026).

**Related tasks:** add an alert on memory utilization > 85% — in `BACKLOG.md`.
