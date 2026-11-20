---
type: Document
title: 'NG-46: Minimum weight floor for critical-path nodes'
description: 'Source: NG-46 Minimum weight floor for critical-path nodes Type: Story
  Status: Done User Story: As a platform operator, I want certain critical edges to
  never fully decay to zero even during quiet per'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-46: Minimum weight floor for critical-path nodes

Source: NG-46

Minimum weight floor for critical-path nodes

Type: Story
Status: Done

User Story:
As a platform operator, I want certain critical edges to never fully decay to zero even during quiet periods, so that important paths don't disappear from the graph just because they haven't fired recently.
Description:
Currently all edges decay toward zero identically via the W(u,v,t) formula regardless of importance. This means a rarely-triggered but critical path (e.g. a disaster-recovery failover) can decay to near-invisibility. This story adds a floor map — keyed by node ID or pattern — that WeightEngine applies post-decay, ensuring tagged nodes/edges never fall below a configured minimum weight.
Acceptance Criteria:
WeightEngine supports a floor map: {node_id_or_pattern: minimum_weight}.

After decay calculation, any edge matching a floor entry is clamped to at least the floor value.

Floor map is configurable via API or config file — not hardcoded in weight_engine.py.

Floor does not prevent an edge from being marked anomalous if its actual co-occurrence spikes above the floor.

Edges without a matching floor entry behave exactly as before (no regression).

Unit test: an edge with a floor of 5.0 that would naturally decay to 0.5 is clamped to 5.0.

Dependencies: None — extends existing WeightEngine decay logic.
