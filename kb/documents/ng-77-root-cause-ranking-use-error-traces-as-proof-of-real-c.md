---
type: Document
title: 'NG-77: Root-cause ranking: use error traces as proof of real call paths'
description: 'Source: NG-77 Root-cause ranking: use error traces as proof of real
  call paths Type: Story Status: In Review User story As someone investigating an
  incident, I want error traces to count as proof that'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-77: Root-cause ranking: use error traces as proof of real call paths

Source: NG-77

Root-cause ranking: use error traces as proof of real call paths

Type: Story
Status: In Review

User story As someone investigating an incident, I want error traces to count as proof that one function called another, so that root-cause ranking follows the path the failure actually took.
Description When a log line carries an error trace, each step in the trace shows a real call between two functions. These calls now build a separate error-path score on the matching connections in the code map. Steps with no matching connection are counted but not scored. Root-cause ranking and impact ordering use the higher of the activity score and the error-path score. Anomaly alerts and the prediction model never read the error-path score, so it can't distort them. Both scores appear in the connection details and the scores table.
Acceptance criteria
A Java error trace credits exactly the calls along the trace and no others.

A root-cause search started from the failing function ranks the traced caller chain first.

The same activity with and without error traces gives identical activity scores and alerts.
