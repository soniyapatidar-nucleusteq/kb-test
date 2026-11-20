---
type: Document
title: 'NG-43: Reviewer/team routing for PR impact'
description: 'Source: NG-43 Reviewer/team routing for PR impact Type: Story Status:
  To Do User Story: As a developer opening a PR, I want PNOG to suggest which team
  should review it based on what it touches, so tha'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-43: Reviewer/team routing for PR impact

Source: NG-43

Reviewer/team routing for PR impact

Type: Story
Status: To Do

User Story:
As a developer opening a PR, I want PNOG to suggest which team should review it based on what it touches, so that the right people see it without manual routing.
Description:
Team ownership already exists in the knowledge graph as (Team)-[:OWNS]->(Node) relationships (seeded via POST /team or Obsidian vault sync) — not as a stored list on the Team node. This task extends the PR impact endpoint (NG-42) to cross-reference impacted nodes against that ownership graph and suggest reviewers. Note: /cmg/impact today is stateless and never queries Neo4j — it builds the graph fresh from the PR's GitHub archive. This story needs to bridge that: when org_id/project_id are supplied and resolve to a project with a persisted graph and seeded team ownership, look up owning teams for the impacted node IDs; otherwise degrade gracefully.

Acceptance Criteria:
POST /cmg/impact response includes a suggested_reviewers field — teams whose OWNS relationships overlap with impacted nodes, when org_id/project_id are supplied and resolve to a project with a persisted graph.

If no team owns an impacted node, or no project context is supplied/resolvable at all, the field returns an empty list — never an error. (Extended from the original AC — an ad-hoc "any GitHub repo" call with no linked project is a very likely real usage pattern and needs the same graceful-empty behavior.)

PRTestCaseGenerator.jsx displays suggested reviewers alongside impact results, next to the existing impacted-services display.

Multiple teams can be suggested if impact spans ownership boundaries.

Team ownership data is read from the existing (Team)-[:OWNS]->(Node) relationships — no new ownership schema.


Dependencies: NG-42 must be complete first — and note NG-42 is itself now scoped as a port/reconciliation from an existing branch, not a from-scratch build (see NG-42's updated description). This ticket's estimate assumes NG-42's ported endpoint is already in place.
