---
type: Document
title: 'NG-23: Node correction flow — flag misrepresented node or correct an inferred
  edge'
description: 'Source: NG-23 Node correction flow — flag misrepresented node or correct
  an inferred edge Type: Story Status: Done As an engineer, I want to flag a graph
  node as misrepresented or correct a wrongly in'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-23: Node correction flow — flag misrepresented node or correct an inferred edge

Source: NG-23

Node correction flow — flag misrepresented node or correct an inferred edge

Type: Story
Status: Done

As an engineer,
I want to flag a graph node as misrepresented or correct a wrongly inferred edge,
So that the platform learns from human feedback without requiring a full re-ingest.

Description 

The backlog (F4.4) requires a human feedback loop where engineers can correct the platform's graph understanding. Corrections must be applied incrementally — re-ingest is too expensive for a single edge fix.
This story adds a right-click context menu to graph nodes with three actions: Flag as misrepresented, Correct edge relationship, Add business context annotation. Corrections are stored and applied on the next weight cycle.
⚠ Scope correction: zero PATCH/PUT endpoints exist on nodes/edges today. Build actual PATCH /orgs/{org}/projects/{proj}/graph/nodes/{id} and .../edges/{id} endpoints — not just a corrections table.


Acceptance Criteria 
Right-clicking a node in the graph opens a context menu with: Flag as misrepresented, Correct edge relationship, Add business context.

Corrections are stored in a new node_corrections table (node_id, org_id, project_id, correction_type, payload, created_by, created_at).

On the next weight computation cycle, corrected edges are re-weighted according to the human override.

Flagged nodes show a small ⚑ indicator on the graph until the correction is reviewed.

A corrections log is accessible in project settings showing all pending and applied corrections.

Corrections do not require full CMG re-ingest — they are applied as delta patches.
