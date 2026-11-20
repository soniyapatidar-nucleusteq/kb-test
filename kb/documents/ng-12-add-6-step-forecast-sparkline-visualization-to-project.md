---
type: Document
title: 'NG-12: Add 6-step forecast sparkline visualization to project health dashboard'
description: 'Source: NG-12 Add 6-step forecast sparkline visualization to project
  health dashboard Type: Story Status: Done Labels: Frontend As an SRE reviewing a
  project, I want to see a forecast sparkline for th'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-12: Add 6-step forecast sparkline visualization to project health dashboard

Source: NG-12

Add 6-step forecast sparkline visualization to project health dashboard

Type: Story
Status: Done
Labels: Frontend

As an SRE reviewing a project,
I want to see a forecast sparkline for the top anomalous edges in the health dashboard,
So that I can anticipate which edges are trending toward failure before they breach the alert threshold
Description 

The LSTM predictor already computes a 6-step exponential decay forecast per edge (returned in _project_zscore_preds()). This data is available in the GET /cmg/ml/predict?org_id=X&project_id=Y response but is not visualized anywhere in the UI.
This story adds a sparkline component to the Health tab of the per-project dashboard. The top 5 anomalous edges are shown, each with a small inline chart: x-axis = 6 time steps, y-axis = predicted weight, current weight marked as a dot, forecast line colored amber or red based on deviation severity
Acceptance Criteria 
Health tab shows sparklines for the top 5 anomalous edges (ranked by anomaly_score descending).

Each sparkline shows: historical weights (last 6 known), current weight (marked point), 6-step LSTM forecast.

Forecast line is amber if predicted deviation is 1.5–2.5σ; red if > 2.5σ.

Clicking a sparkline opens the full edge detail panel with source Kafka topics and weight override option.

If fewer than 3 weight history samples exist for an edge, sparkline shows 'Insufficient data' placeholder.

Sparklines update automatically when the health endpoint is polled (every 30s).
