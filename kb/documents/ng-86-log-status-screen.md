---
type: Document
title: 'NG-86: Log Status screen'
description: 'Source: NG-86 Log Status screen Type: Story Status: In Review As a project
  owner, I want to see what happens to my project''s logs, so that I know how many
  lines were understood, linked to code, or mis'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-86: Log Status screen

Source: NG-86

Log Status screen

Type: Story
Status: In Review

As a project owner, I want to see what happens to my project's logs, so that I know how many lines were understood, linked to code, or missed.
Description A new Log Status tab for each project shows:
Overview for today, the last 7 days or the last 30 days: lines identified by a pattern, lines identified by the model, unstructured lines the model understood, and lines nothing identified. It also breaks lines down by format: standard, partial or unstructured.

Code linking: how many lines were linked to code, what found the link, the code line number, and which version of the project's code map each line was matched against.

Recent lines: the latest 10, 20 or 30 lines, with what they were linked to. They can be filtered by how they were identified and by format.

Detailed view: day-by-day and stage-by-stage counts, kept below the overview.

Acceptance criteria
The tab shows lines received, identified and linked for the chosen period.

Each identification type shows example lines.

Recent lines can be filtered by how they were identified and by format.
