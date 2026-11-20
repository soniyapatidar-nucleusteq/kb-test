---
type: Document
title: 'NG-81: Run several workers side by side safely'
description: 'Source: NG-81 Run several workers side by side safely Type: Story Status:
  In Review User story As the platform team, I want to run several scoring workers
  and servers at once, so that load can be shar'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-81: Run several workers side by side safely

Source: NG-81

Run several workers side by side safely

Type: Story
Status: In Review

User story As the platform team, I want to run several scoring workers and servers at once, so that load can be shared and a crash doesn't lose saved data.
Description Recent activity was held in one server's memory. A second server would see only part of a project's logs, and the two would disagree on scores. All live scores and recent activity are now kept in the shared database. Each project is handled by one worker at a time. Several workers and servers can be started together. A crash loses nothing that was already saved; at most the last unsaved batch is read again.
Acceptance criteria
Two workers produce exactly the same scores, counts and history as one worker for the same input.

Two workers split the incoming logs between them.

Stopping a worker mid-batch loses no saved data.

Note: a batch read again after a crash is counted twice. This is a small, accepted over-count.
