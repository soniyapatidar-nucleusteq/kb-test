---
type: Document
title: 'NG-73: Single scoring engine with per-project settings'
description: 'Source: NG-73 Single scoring engine with per-project settings Type:
  Story Status: In Review User story As a project owner, I want my project''s scoring
  settings (fade speed, alarm sensitivity, minimum '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-73: Single scoring engine with per-project settings

Source: NG-73

Single scoring engine with per-project settings

Type: Story
Status: In Review

User story As a project owner, I want my project's scoring settings (fade speed, alarm sensitivity, minimum scores, environment weighting) to apply to my own live data, so that scores reflect how my system really behaves.
Description There are two scoring engines. The old global one has adjustable fade speed (λ), audit history and environment tiers. The per-project one that scores client data uses a fixed λ = 0.1, which gives a half-life of about 7 seconds. It also skips minimum scores (floors) on the batch ingest path and has no environment weighting. This ticket makes the per-project engine the only engine and moves those settings onto it.
Scope
Per-project settings: half-life, z-score threshold and environment multipliers. Defaults come from the application type: 10 minutes for services, 24 hours for ETL (extract, transform, load) jobs. Allowed range is 10 seconds to 7 days.

Every settings change is recorded (who, when, old value, new value) in weight_config_changes, which gets a new project_id column.

/graph/ingest, /graph/ingest/events, anomalies, flush, RCA and /edges/detail read the project's own settings.

Floors are applied on /graph/ingest/events.

The log-worker passes the environment on each event. Production counts 1.0, other environments 0.5, untagged events 1.0.

An "Activity Scoring" settings panel in the project's Settings tab and on /config/weights. It shows the half-life in plain words ("a score halves every N minutes"). Only owners and admins can edit.

The old weight-worker is retired behind the legacy-weight-engine compose profile.

Acceptance criteria
With a 10-minute half-life, a weight decays to about 50% after 10 minutes with no events (unit test).

Floors hold on edges updated through /graph/ingest/events (test).

A batch tagged staging adds half the weight of the same batch tagged production.

Every settings change has an audit row with who, when, the old value and the new value.

No event from a client stack reaches PNOG's own nodes.
