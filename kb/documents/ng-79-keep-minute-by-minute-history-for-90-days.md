---
type: Document
title: 'NG-79: Keep minute-by-minute history for 90 days'
description: 'Source: NG-79 Keep minute-by-minute history for 90 days Type: Story
  Status: In Review User story As the platform, I want a long history of each connection''s
  activity, so that it can later learn what i'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-79: Keep minute-by-minute history for 90 days

Source: NG-79

Keep minute-by-minute history for 90 days

Type: Story
Status: In Review

User story As the platform, I want a long history of each connection's activity, so that it can later learn what is normal for each hour of the day and each day of the week.
Description Only the last 100 readings per connection were kept, with no record of when each was taken. Every connection now records its events, errors, warnings and score each minute. After 7 days, minutes are summarised into hours, and everything is kept for 90 days. The stored counts are enough to recalculate a score exactly, so later formula changes won't make the history useless. History can be viewed for any connection and time range.
Learning daily and weekly patterns is not part of this ticket. It needs at least two weeks of collected data and belongs to the alerting work.
Acceptance criteria
A day of traffic produces at most 1,440 records per active connection, and the hourly summary reduces older data by about 60 times.

A score recalculated from stored history matches the live score.

Records older than 90 days are removed automatically.
