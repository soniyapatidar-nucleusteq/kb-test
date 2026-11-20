---
type: Document
title: 'NG-69: Graph only shows one programming language per project'
description: 'Source: NG-69 Graph only shows one programming language per project
  Type: Subtask Status: Done When a project is written in more than one language,
  the graph only picked up one of them and silently ig'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-69: Graph only shows one programming language per project

Source: NG-69

Graph only shows one programming language per project

Type: Subtask
Status: Done

When a project is written in more than one language, the graph only picked up one of them and silently ignored the rest. On our test project this meant the entire data ingestion component — the part that actually moves the data — was missing from the graph, so anyone looking at it saw an incomplete picture of the system.
