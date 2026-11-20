---
type: Document
title: 'NG-85: Automatic incidents and tickets from errors'
description: 'Source: NG-85 Automatic incidents and tickets from errors Type: Story
  Status: In Review User story As an on-call engineer, I want each new kind of failure
  to open one incident and one ticket that expl'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-85: Automatic incidents and tickets from errors

Source: NG-85

Automatic incidents and tickets from errors

Type: Story
Status: In Review

User story As an on-call engineer, I want each new kind of failure to open one incident and one ticket that explain why it happened, so that I'm not flooded with duplicates and know where to start.
Description The log-to-ticket service is now part of the platform and starts with the rest of it. A Java example application can deliberately trigger errors for testing, and the ticketing tool (Plane) was set up to receive tickets.
What was done:
One incident is created for each type of error. A new failure opens an incident and a ticket; a repeat adds a comment to the existing ticket.

The same error worded differently, or one task's failure merged into another task's incident, no longer happens.

Each incident explains why it happened: what caused it, the code path, what triggered it, and a plain cause sentence. The cause sentence comes from the patterns, with AI used only as a fallback.

Incidents have short, readable names taken from what the log says.

The incident panel shows the triggering log lines, the ticket and its status.

The knowledge graph is now stored in the main database, so rebuilding the code map no longer breaks incident links. Incidents link to the code they affect.

Bugs found in live testing were fixed: a false error raised by cut-off lines, cause sentences dropping words, deleted tickets blocking new ones, and broken ticket links.

Acceptance criteria
A new failure creates one incident and one ticket; a repeat only adds a comment.

Each incident shows its cause, code path, trigger and cause sentence.

The incident panel shows the log lines, the ticket and its status.

Rebuilding the code map keeps incident links.
