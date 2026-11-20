---
type: Document
title: 'NG-67: QA — Validate Health, RCA & Blast Radius on client data pipelines'
description: 'Source: NG-67 QA — Validate Health, RCA & Blast Radius on client data
  pipelines Type: Story Status: Done A client is migrating their data estate from
  Hadoop Hive → BigQuery → Lumi, and has built Data '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-67: QA — Validate Health, RCA & Blast Radius on client data pipelines

Source: NG-67

QA — Validate Health, RCA & Blast Radius on client data pipelines

Type: Story
Status: Done

A client is migrating their data estate from Hadoop Hive → BigQuery → Lumi, and has built Data Ingestion and Data Engineering pipelines they want to monitor on our platform. We will get access to those pipelines ahead of a demo covering Health Dashboard, RCA, and Blast Radius.
All current validation is against generic sample web services. A data pipeline's graph is made of jobs, tables and datasets rather than routes and function calls, so these three features are unproven on that shape of topology.
Objective
Onboard the client pipelines as a project and verify Health, RCA and Blast Radius return correct, explainable results on that topology — with screenshot/API evidence for each.
Scope
Onboard — create the project, configure the datasource, build the graph for both pipelines, and confirm the nodes/edges represent actual pipeline dependency flow (job → job, source → target table) and not just file structure. Document coverage gaps.

Health — verify score, trend, forecast and history are correct and project-scoped; verify cold-start/no-data behaves gracefully; verify a pipeline failure moves the signal in the expected direction.

RCA — verify returned candidates are genuine upstream causes, ranked sensibly, across at least 3 seeded faults with known ground truth; unknown node IDs return a clean empty result.

Blast Radius — verify impacted nodes are downstream and match the real dependency chain (regression check on NG-65 — direction was previously inverted); verify behaviour on wide fan-out.

Demo script — document and dry-run a repeatable flow: seed fault → health degrades → RCA finds root cause → blast radius shows impact.

Acceptance Criteria
Pipelines onboarded; built graph confirmed to represent dependency flow, coverage documented

Health correct and project-scoped, including cold-start and no-data cases

RCA returns correct upstream root cause for 3+ seeded faults

Blast Radius returns correct downstream impact, direction verified

UI and API results agree

Defects logged as linked bugs with repro steps and demo impact

QA report published with evidence per feature

Dependencies
Client access to pipeline source and/or runtime metadata — blocks start. Confirm the form of access (repo, orchestrator DAG metadata, runtime logs).

A non-prod environment and an agreed way to seed or simulate failures.

Risks
Topology mismatch (highest): our static builder targets application code; pipeline lineage may not be produced, in which case RCA and Blast Radius traverse the wrong structure. Assess first.

No event mapping for pipeline run events (job start/fail/duration), leaving dynamic weights flat and weakening Health and RCA ranking.

Lineage may need stitching across three systems; partial lineage truncates blast radius.

Gaps in the first two are feature work, not QA fixes — raise as separate dev tickets.
