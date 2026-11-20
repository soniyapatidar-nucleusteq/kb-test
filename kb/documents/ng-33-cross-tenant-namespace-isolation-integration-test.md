---
type: Document
title: 'NG-33: Cross-tenant namespace isolation integration test'
description: 'Source: NG-33 Cross-tenant namespace isolation integration test Type:
  Story Status: To Do Labels: BackEnd As a platform operator, I want an automated
  test proving that events and graph data from one o'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-33: Cross-tenant namespace isolation integration test

Source: NG-33

Cross-tenant namespace isolation integration test

Type: Story
Status: To Do
Labels: BackEnd

As a platform operator,
I want an automated test proving that events and graph data from one org cannot bleed into another org's graph,
So that the platform is safe for multi-tenant enterprise deployment.
Description 
The cross-cutting Namespace Isolation AC states: 'Cross-tenant bleed is a P0 defect.' No automated test currently validates this. This task adds an integration test covering the full data path: event injection → weight update → health query across two isolated orgs.
This is a pre-production release gate — the platform must not ship without this test passing.
Acceptance Criteria 
Test creates two orgs (Org A, Org B) each with one project.

20 anomaly events are injected into Org A's project via POST /orgs/A/projects/A1/ingest.

GET /orgs/B/projects/B1/graph returns no nodes or edges from Org A.

GET /cmg/ml/system-health?org_id=B&project_id=B1 returns a health score unaffected by Org A events.

Test is added to the CI pipeline and must pass on every merge to main.

Any cross-tenant data leak detected causes the test to fail with a P0 label and blocks the release.
