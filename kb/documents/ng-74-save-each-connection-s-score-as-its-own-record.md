---
type: Document
title: 'NG-74: Save each connection''s score as its own record'
description: 'Source: NG-74 Save each connection''s score as its own record Type:
  Story Status: In Review User story As the platform, I want to save only the connections
  that changed, so that storage stays efficient'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-74: Save each connection's score as its own record

Source: NG-74

Save each connection's score as its own record

Type: Story
Status: In Review

User story As the platform, I want to save only the connections that changed, so that storage stays efficient as projects grow.
Description Every small update rewrote a project's entire set of scores as one large item. Now each connection's score is its own record, with its own clock and recent readings, and an update writes only the connections it touched. Existing scores were moved across with a one-time migration.
Rebuilding the code map keeps the scores of connections that still exist. Connections that disappear are set aside for 30 days rather than deleted, so a later build can restore them. A failed or partial build never removes scores.
Acceptance criteria
An update touching 3 connections writes 3 records, not the whole project.

Every screen and feature shows the same values before and after the migration.

Rebuilding the code map keeps scores for connections that are unchanged.

Two updates arriving at the same time for one project never overwrite each other.

Note: minimum and pinned scores now fade correctly; before, they barely faded.
