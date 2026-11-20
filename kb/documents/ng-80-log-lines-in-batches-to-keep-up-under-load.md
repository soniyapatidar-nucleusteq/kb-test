---
type: Document
title: 'NG-80: Log lines in batches to keep up under load'
description: 'Source: NG-80 Log lines in batches to keep up under load Type: Story
  Status: In Review User story As the platform, I want to process log lines in batches
  and update only the connections they touch, so'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-80: Log lines in batches to keep up under load

Source: NG-80

Log lines in batches to keep up under load

Type: Story
Status: In Review

User story As the platform, I want to process log lines in batches and update only the connections they touch, so that scoring doesn't slow down when a client is busiest.
Description Lines were processed one at a time, and each one caused work across the whole project. Lines are now scored in batches: each connection is updated once per batch, and only connections the batch touches are read and written. A large-batch failure found during the work was fixed. A repeatable speed test was added.
Acceptance criteria
Batch scoring gives the same final scores and counts as one-at-a-time scoring.

The speed test reports throughput before and after.

Note: recent readings are now stored once per batch, which changes the normal level that alerts compare against.
