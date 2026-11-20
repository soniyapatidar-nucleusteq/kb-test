---
type: Document
title: 'NG-62: BUG : Java/JS parsers never run when a repo has a docker-compose.yml
  — graph builds with zero code nodes'
description: 'Source: NG-62 BUG : Java/JS parsers never run when a repo has a docker-compose.yml
  — graph builds with zero code nodes Type: Subtask Status: Done As an engineer exploring
  a Java or JavaScript project,'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-62: BUG : Java/JS parsers never run when a repo has a docker-compose.yml — graph builds with zero code nodes

Source: NG-62

BUG : Java/JS parsers never run when a repo has a docker-compose.yml — graph builds with zero code nodes

Type: Subtask
Status: Done

As an engineer exploring a Java or JavaScript project, I want its classes and
methods to appear in the graph, So that RCA, blast radius and the code map have
real code to work with instead of only infrastructure.
Description
A Java or JavaScript repository that also contains a docker-compose.yml builds a
graph with no code in it at all. The build reports success and logs no warning,
so nothing indicates anything is missing.
The Java and JavaScript parsers only run when the earlier build step found
nothing at all. That step also reads config files, so a single docker-compose.yml
is enough to make the build think it already has the code and skip them.
Acceptance Criteria
A Java or JavaScript repository containing a docker-compose.yml builds with its
classes and methods present.

Nodes found from config files — compose services, dependencies, CI jobs — are
kept alongside the code rather than replaced by it.

The graph records the language it actually parsed.

A repository the build genuinely cannot parse still reports a warning, as it
does today.

Python projects are unaffected — existing behaviour unchanged.

Known limitation, needs its own ticket: a project with two languages still
gets only one of them. A Python repo with a JavaScript frontend parses the Python
and skips the JavaScript, for the same reason.
