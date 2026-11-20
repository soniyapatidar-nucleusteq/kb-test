---
type: Document
title: 'NG-78: Show each connection''s share of errors and warnings'
description: 'Source: NG-78 Show each connection''s share of errors and warnings Type:
  Story Status: In Review User story As an on-call engineer, I want to see each connection''s
  share of errors and warnings, so that'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-78: Show each connection's share of errors and warnings

Source: NG-78

Show each connection's share of errors and warnings

Type: Story
Status: In Review

User story As an on-call engineer, I want to see each connection's share of errors and warnings, so that a busy connection that starts failing stands out even when its traffic stays flat.
Description On busy connections the score stayed high and flat, so a wave of errors barely showed. Each connection now counts its events, errors and warnings per day, using the severity the log reader already assigns to each line. The error and warning share for today and for the last 7 days is shown in the connection details and the scores table.
The tracker suggested making errors add more to the score. Instead, errors are counted separately, so the normal activity level used by alerts stays clean.
Acceptance criteria
A connection whose traffic stays flat while its error share rises from 1% to 30% shows that rise.

Activity scores are identical with and without severity on the log lines.
