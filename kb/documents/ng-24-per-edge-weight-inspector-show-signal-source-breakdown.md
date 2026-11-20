---
type: Document
title: 'NG-24: Per-edge weight inspector — show signal source breakdown and manual
  override input'
description: 'Source: NG-24 Per-edge weight inspector — show signal source breakdown
  and manual override input Type: Story Status: Done Labels: Frontend As an SRE, I
  want to click any graph edge and see exactly whi'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-24: Per-edge weight inspector — show signal source breakdown and manual override input

Source: NG-24

Per-edge weight inspector — show signal source breakdown and manual override input

Type: Story
Status: Done
Labels: Frontend

As an SRE,
I want to click any graph edge and see exactly which signal sources are driving its weight,
So that I can understand why a particular relationship is marked as high-risk and override it if needed.

Description 

The backlog (F4.5) requires full weight visibility and manual override. Currently clicking an edge shows only the W(u,v,t) value. This story adds a detailed breakdown panel: percentage contribution per Kafka topic, the full decay formula with current λ, and a manual override input that persists to Postgres.
⚠ Confirm: this must be a new, distinct PATCH .../edges/{id}/weight endpoint — separate from the existing automated weight_delta (EMA) ingest path.

Acceptance Criteria 
Clicking an edge in the graph opens a detail panel showing: current W(u,v,t) value, % contribution per Kafka topic (e.g., app.events: 60%, git.releases: 40%).

Full weight formula displayed with current values substituted: W = Σ co(u,v,τ) × e^(−0.1 × Δt).

Manual override input field allows entering a custom weight value with a Save button.

Override is persisted in a weight_overrides table and applied on the next weight computation cycle.

Override badge shown on the edge in the graph (e.g., ✎ icon) until the override is cleared.

Clear override button restores formula-driven weight on the next cycle.
