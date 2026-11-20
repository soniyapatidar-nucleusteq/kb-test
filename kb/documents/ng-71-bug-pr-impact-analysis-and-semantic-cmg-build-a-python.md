---
type: Document
title: 'NG-71: BUG: PR impact analysis and semantic CMG build a Python-only graph,
  so Java and JS repos return no impact'
description: 'Source: NG-71 BUG: PR impact analysis and semantic CMG build a Python-only
  graph, so Java and JS repos return no impact Type: Subtask Status: In Progress User
  Story As a developer reviewing a PR on a '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-71: BUG: PR impact analysis and semantic CMG build a Python-only graph, so Java and JS repos return no impact

Source: NG-71

BUG: PR impact analysis and semantic CMG build a Python-only graph, so Java and JS repos return no impact

Type: Subtask
Status: In Progress

User Story
As a developer reviewing a PR on a Java or JavaScript repository, I want the PR
review agent to build a graph of my code, so that impact analysis returns the
functions my change actually affects instead of nothing.
Description
_build_cmg_graph_from_repo runs pnog's StaticLayerBuilder alone, which covers
Python plus docker-compose and nginx. The Java, JS/TS and config parsers are
never called, code nodes are hardcoded to language="Python", and file counts
come from *.py only.
The polyglot logic already exists but sits inside the project-build endpoint in
project_graphs.py, so only that one caller benefits. Affected: POST /cmg/impact,
POST /cmg/pr-suite, GET /cmg/graph, and the semantic CMG baseline.
Fix is to extract the parser orchestration into a shared builder that runs every
parser whose files are present, merges the results, and labels nodes by their
producing parser — then point all call sites at it.
Acceptance Criteria
POST /cmg/impact on a Java PR returns non-empty impacted functions

POST /cmg/impact on a JS/TS PR returns non-empty impacted functions

A polyglot repo returns nodes from every language present, not just one

Node language reflects the producing parser, not a hardcoded "Python"

scanned_files / parsed_files count all parsed languages

Scope filtering (dev/sre/sec) applies after the merge, so non-Python nodes
are filtered too

Existing project-build output and its per-parser warnings are unchanged

Existing test suites pass (423 backend, 54 pnog)
