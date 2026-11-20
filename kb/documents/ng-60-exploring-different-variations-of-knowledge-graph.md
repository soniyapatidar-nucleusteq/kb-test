---
type: Document
title: 'NG-60: Exploring different variations of Knowledge Graph'
description: 'Source: NG-60 Exploring different variations of Knowledge Graph Type:
  Subtask Status: In Review The Knowledge Graph is currently drawn one way — a force-directed
  node-link canvas. Five of the seven no'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-60: Exploring different variations of Knowledge Graph

Source: NG-60

Exploring different variations of Knowledge Graph

Type: Subtask
Status: In Review

The Knowledge Graph is currently drawn one way — a force-directed node-link
canvas. Five of the seven node types all attach to the same hub type, so the
layout collapses into a hairball as soon as a project carries real data, and
node position ends up meaning nothing.
This ticket is an exploration, not an implementation. Survey the realistic
alternatives for drawing the same telemetry — services, incidents, anomalies,
runbooks, PRs, SLO breaches and traces — and work out which layout answers
which operational question: live triage, post-incident review, root-cause of a
spread, coverage auditing, and stakeholder reporting.
Deliverable is a reference document: each candidate layout with a worked
example, what it is good at, where it breaks, and a recommendation on which to
adopt and in what order.
