---
type: Document
title: 'NG-40: Per-node confidence score'
description: 'Source: NG-40 Per-node confidence score Type: Story Status: Done User
  Story: As an engineer exploring the graph, I want to see how confident PNOG is about
  its understanding of a given node, so that I '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-40: Per-node confidence score

Source: NG-40

Per-node confidence score

Type: Story
Status: Done

User Story:
As an engineer exploring the graph, I want to see how confident PNOG is about its understanding of a given node, so that I know which parts of the graph to trust and which need more context.
Description:
No confidence field exists anywhere in the codebase today (F4.3 is not started). This story adds a computed confidence score per node, based on three factors: AST coverage of the source file, whether a runbook/doc is linked, and recent signal count (how much live traffic touches this node). The score is surfaced via the context API and shown as a badge in the node detail panel.
Acceptance Criteria:
Confidence score (0–100) computed as a weighted combination of: AST coverage of the file, has-runbook-or-doc-link (boolean), recent-signal-count (last 7 days).

Score is exposed via GET /context/{node_id} as a confidence_score field.

InteractiveGraph.jsx node detail panel shows the score as a badge (e.g. color-coded: green ≥70, amber 40–69, red <40).

Nodes with zero signals and no linked docs score low by default — not silently defaulted to a mid-range score.

Score recalculates when new signals arrive or a doc is linked/unlinked — not a one-time computation at build time.

Score calculation weights are configurable (not hardcoded), so they can be tuned without a code change.
