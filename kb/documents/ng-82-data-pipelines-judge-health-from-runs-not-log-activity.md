---
type: Document
title: 'NG-82: Data pipelines: judge health from runs, not log activity'
description: 'Source: NG-82 Data pipelines: judge health from runs, not log activity
  Type: Story Status: In Review User story As the owner of a data-pipeline project,
  I want health judged from pipeline runs and tab'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-82: Data pipelines: judge health from runs, not log activity

Source: NG-82

Data pipelines: judge health from runs, not log activity

Type: Story
Status: In Review

User story As the owner of a data-pipeline project, I want health judged from pipeline runs and table updates, so that a job that runs once a day doesn't look idle between runs.
Description Activity scoring suits services that log all day. A daily pipeline logs only while it runs, so its activity says little about its health. The platform now reads pipeline runs and task runs from the scheduler (Airflow) every 5 minutes. It records when each table was last updated and when its next update is due. For each pipeline it shows: failed, running, late, not started because an earlier pipeline failed, slower than usual, or OK. Each table shows whether it is out of date. For a failed task, the impact view lists the tables and pipelines downstream of it, nearest first.
Acceptance criteria
A failed ingestion run shows as failed. The pipelines that depend on it show as not started, and the table it should have updated shows as out of date.

The impact view for the failed task lists the downstream tables in order.

Reading the same runs twice gives the same records.

Status: partly addressed. This was built and tested on example data. The MovieLens pilot needs the platform to be given access to MovieLens's Airflow scheduler and the MovieLens project to be onboarded.
