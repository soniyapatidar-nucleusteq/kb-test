---
type: Document
title: 'NG-89: Collect real application logs into the platform'
description: 'Source: NG-89 Collect real application logs into the platform Type:
  Story Status: In Review User story As a client team, I want my applications'' logs
  to reach the platform automatically, so that every'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-89: Collect real application logs into the platform

Source: NG-89

Collect real application logs into the platform

Type: Story
Status: In Review

User story As a client team, I want my applications' logs to reach the platform automatically, so that everything shown on screen comes from real activity, not test data.
Description Everything on screen used to be test data the platform generated itself. The platform now collects real logs from client applications and sends each stream to the right client project.
What was done:
Built the route that brings logs from an onboarded application into the platform. It was first proven with the local MovieLens application.

The platform reads log files as well as container output.

Each incoming log stream is matched to the correct client project automatically.

Old log lines that are replayed, for example when Airflow re-reads its history, are recognised by age and no longer create incidents.

Lines already stamped by the platform aren't processed a second time.

The ticketing tool's own logs are kept out of collection.

Individual log lines are no longer stored. Only summaries and the few lines attached to an incident are kept.

Acceptance criteria
Logs from an onboarded application, both container output and log files, appear in the platform within seconds.

Each stream is assigned to the right client project.

Replayed old lines don't create new incidents.

Individual log lines aren't stored.
