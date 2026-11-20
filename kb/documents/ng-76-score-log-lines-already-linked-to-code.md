---
type: Document
title: 'NG-76: Score log lines already linked to code'
description: 'Source: NG-76 Score log lines already linked to code Type: Story Status:
  In Review User story As the platform, I want activity scoring to use log lines that
  are already matched to the exact function t'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-76: Score log lines already linked to code

Source: NG-76

Score log lines already linked to code

Type: Story
Status: In Review

User story As the platform, I want activity scoring to use log lines that are already matched to the exact function that wrote them, so that scores land on real code instead of whole services.
Description Activity scoring used to read raw log lines and work out their source again, separately from the log reader. It now takes the lines the log reader has already understood and linked to code, which are the lines shown on the Log status screen. Each line then credits the function or class that wrote it. Each line's environment is carried through, so test and production weighting keeps working. A setting allows switching back to the old source if needed, and the two sources are never read together, so no line is counted twice.
Acceptance criteria
Raw log feeds are no longer read by activity scoring.

Credited connections land on functions or classes where the line was linked to code.

A line from a staging stream counts half; a line from production counts fully.

Switching back to the old source restores the previous behaviour.

Numbers before and after the change are reported for each run: lines received, lines linked, connections scored, and pairs that couldn't be linked to a real connection.
