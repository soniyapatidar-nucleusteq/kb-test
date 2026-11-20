---
type: Document
title: 'NG-14: Auto-retrain per-project LSTM when event delta exceeds threshold'
description: 'Source: NG-14 Auto-retrain per-project LSTM when event delta exceeds
  threshold Type: Story Status: Done As the platform, I want per-project LSTM models
  to retrain automatically when enough new events '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-14: Auto-retrain per-project LSTM when event delta exceeds threshold

Source: NG-14

Auto-retrain per-project LSTM when event delta exceeds threshold

Type: Story
Status: Done

As the platform,
I want per-project LSTM models to retrain automatically when enough new events have been ingested,
So that predictions improve continuously without manual intervention.

Description 

The existing _auto_train_loop() triggers global LSTM retraining but does not track per-project event counts. As a result, projects with high event volume may run stale models while the global model retrains.
This story extends _auto_train_loop() to check each project's event_count delta since its last train. If the delta exceeds 50 events, a project-scoped retrain is triggered asynchronously using asyncio.wait_for() with a 300s timeout

Acceptance Criteria 
_auto_train_loop() iterates over all ProjectGraph rows and checks event_count delta since last_trained_at.

If delta > 50 for a project, triggers project-scoped retrain via asyncio.wait_for(run_in_executor(...), timeout=300).

last_trained_at timestamp is updated on ProjectGraph after successful train.

Training timeout (300s) logs a warning and continues — it does not crash the loop.

Retrain status (last trained, event delta, model version) visible in the project health panel.

Concurrent retrains across projects are bounded to max 3 at a time to avoid CPU saturation.
