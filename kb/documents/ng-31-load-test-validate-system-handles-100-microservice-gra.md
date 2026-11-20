---
type: Document
title: 'NG-31: Load test — validate system handles 100+ microservice graph under same
  model'
description: 'Source: NG-31 Load test — validate system handles 100+ microservice
  graph under same model Type: Story Status: To Do As a solutions engineer,I want
  evidence that PNOG handles a 100+ microservice repos'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-31: Load test — validate system handles 100+ microservice graph under same model

Source: NG-31

Load test — validate system handles 100+ microservice graph under same model

Type: Story
Status: To Do

As a solutions engineer,I want evidence that PNOG handles a 100+ microservice repository under the same graph model,So that I can confidently present the platform to enterprise clients with large codebases.

Description 

The cross-cutting acceptance criteria (Scale AC) require the platform to handle single-file scripts and 100+ microservice systems under the same architecture with no changes. The nuo-data/ sample dataset in the repo can serve as the base for a synthetic 100-service fixture.
This task documents the results of a structured load test against the four performance targets from the backlog

Acceptance Criteria 
CMG build for a 100-service synthetic repo completes in under 5 minutes.

Graph renders in the frontend in under 3 seconds after build.

Weight engine sustains 500 events/second (via POST /cmg/ingest load test) without consumer lag.

Per-edge LSTM training completes within the 300-second asyncio timeout for the largest edges.

Results documented in a test report: test fixture details, measured times, pass/fail per target.

Any failing targets have a GitHub issue filed with root cause and remediation estimate
