---
type: Document
title: 'NG-13: Build reliability score dashboard with A–F grade and 7-day trend'
description: 'Source: NG-13 Build reliability score dashboard with A–F grade and 7-day
  trend Type: Story Status: Done Labels: Frontend As a VP of Engineering or SRE, I
  want a reliability dashboard showing the curre'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-13: Build reliability score dashboard with A–F grade and 7-day trend

Source: NG-13

Build reliability score dashboard with A–F grade and 7-day trend

Type: Story
Status: Done
Labels: Frontend

As a VP of Engineering or SRE,
I want a reliability dashboard showing the current health grade and its 7-day trend,
So that I can track whether the system is improving or degrading over time

Description 

The system health endpoint (GET /cmg/ml/system-health) returns a 0–100 score and per-edge predictions. There is currently no dedicated dashboard surface that shows this as a letter grade with historical context.
This story adds a Reliability tab to the per-project observability dashboard. It shows the current grade (A–F), a 7-day sparkline of the grade trend, and the top 3 degrading edges with their predicted severity. Grade bands: A=90+, B=75–89, C=60–74, D=45–59, F<45.
Acceptance Criteria 
New Reliability tab visible in the per-project observability dashboard.

Current health grade shown as a large letter (A–F) with the underlying numeric score.

7-day grade trend displayed as a sparkline (one data point per day, stored in Postgres or local state).

Top 3 degrading edges listed with: edge label (u→v), current anomaly_score, severity badge (LOW/MEDIUM/HIGH/CRITICAL).

Grade history is persisted — refreshing the page does not reset the 7-day sparkline.

Empty state shown when fewer than 2 days of history exist: 'Collecting baseline — check back tomorrow'
