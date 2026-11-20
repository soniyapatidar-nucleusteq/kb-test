---
type: DATABASE
title: postgres
description: Postgres is the persistence layer for orgs, projects, CMG graphs and
  weight history. Incidents here cascade to every API endpoint, so it ranks high in
  most RCA traces. Connection exhaustion is the dom
resource: null
tags:
- database
timestamp: '2026-11-20T11:54:14.719910'
---

# postgres

Postgres is the persistence layer for orgs, projects, CMG graphs and
weight history. Incidents here cascade to every API endpoint, so it ranks
high in most RCA traces. Connection exhaustion is the dominant failure mode.

## Known bugs
- Pool exhaustion when weight-worker flushes coincide with heavy UI reads
  (reproduce with `infra/fault_injection/db_pool_exhaust.py`).
- Long-running `weight_history` JSONB updates can lock the `ast_graph` row
  during auto-flush.

## Remediation
1. `docker exec postgres pg_isready` and check active connections:
   `SELECT count(*) FROM pg_stat_activity;`
2. Look for lock waits: `SELECT * FROM pg_locks WHERE NOT granted;`
3. If exhausted, restart fastapi first (releases its pool), postgres last.

## Connections

- [[services/inventory-service|inventory-service]] — depends_on, incoming
- [[services/order-service|order-service]] — depends_on, incoming
