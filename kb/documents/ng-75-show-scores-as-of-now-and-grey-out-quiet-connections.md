---
type: Document
title: 'NG-75: Show scores as of now and grey out quiet connections'
description: 'Source: NG-75 Show scores as of now and grey out quiet connections Type:
  Story Status: In Review show scores as of now and grey out quiet connections User
  story As a user looking at the graph, I want '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-75: Show scores as of now and grey out quiet connections

Source: NG-75

Show scores as of now and grey out quiet connections

Type: Story
Status: In Review

show scores as of now and grey out quiet connections
User story As a user looking at the graph, I want every score to reflect the current time, so that a connection that went quiet an hour ago doesn't look active.
Description When activity stopped, screens kept showing the last score as if it were live. The manual refresh button also reset the fading clock. Scores are now faded to the current time wherever they are shown or used: the graph, the scores table, root-cause ranking and impact ordering. Each connection shows when it was last active, and connections with no recent activity are greyed out. Refresh no longer moves any clock.
Quiet connections are left out of anomaly alerts. Without this, every quiet night would raise false alarms.
Acceptance criteria
A connection last active an hour ago, with a 10-minute setting, shows about 1.6% of its last score.

Pressing refresh twice doesn't change any later score.

Quiet connections appear greyed out, with the time of their last activity.
