# FACTS

## Why this file exists

The canonical place to store addresses, ports, identifiers, and key parameters of servers and networks.

## What belongs here

- IP addresses, domain names, ports, protocols;
- server and service identifiers;
- VPN configurations and network parameters;
- recorded infrastructure decisions.

## What does not belong here

- a history of changes (use `SERVICE_CHANGES_LOG.md` for that);
- incident analysis (use `INCIDENTS.md` for that);
- project plans and a backlog;
- the log of choosing a standard: “selected A, rejected B” — that goes in `DECISION_LOG.md` if the slot is in use; this file holds the current value after the decision.

---

## Example

> For a “Server infrastructure” folder

**Servers:**
| Name | IP | Role | OS |
|-----|----|------|----|
| prod-web-01 | 192.168.1.10 | Web server (nginx) | Ubuntu 22.04 |
| prod-db-01 | 192.168.1.20 | PostgreSQL 15 | Ubuntu 22.04 |
| dev-01 | 192.168.1.30 | Development and tests | Debian 12 |

**VPN:**
- Provider: WireGuard.
- Config: `/etc/wireguard/wg0.conf` on prod-web-01.
- VPN address range: `10.0.0.0/24`.

**Services:**
- Monitoring: Grafana at `http://192.168.1.10:3000` (VPN only).
- Backups: S3-compatible storage, bucket `company-backups`, 30-day rotation.
