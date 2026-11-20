---
type: Document
title: 'NG-15: Persist per-project LSTM model across restarts via ProjectGraph.ml_snapshot'
description: 'Source: NG-15 Persist per-project LSTM model across restarts via ProjectGraph.ml_snapshot
  Type: Story Status: Done As the platform, I want per-project LSTM models to survive
  FastAPI restarts, So that '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-15: Persist per-project LSTM model across restarts via ProjectGraph.ml_snapshot

Source: NG-15

Persist per-project LSTM model across restarts via ProjectGraph.ml_snapshot

Type: Story
Status: Done

As the platform,
I want per-project LSTM models to survive FastAPI restarts,
So that engineers do not experience a burst of false-positive anomaly alerts every time the service restarts

Description 

Per-project LSTM models trained in PNOG-201 are held in memory and lost on FastAPI restart. On cold start, the predictor has no baseline and immediately flags every edge as anomalous until retraining completes.
This story ensures models are saved to ProjectGraph.ml_snapshot on train completion and restored on startup(). This mirrors the existing AstGraph.ml_snapshot pattern for the global model.

Acceptance Criteria 
After per-project LSTM training completes, model is serialized and saved to ProjectGraph.ml_snapshot in Postgres.

FastAPI startup() loads all ProjectGraph.ml_snapshot rows and restores MLAnomalyPredictor state per project.

Cold-start burst of false positives is eliminated — existing models are used immediately on startup.

If ml_snapshot is corrupt or incompatible (schema change), startup logs a warning and retrains from weight_history instead of crashing.

Verified: restart FastAPI, immediately query /cmg/ml/system-health for a project with a trained model — response uses restored model, not blank baseline.
