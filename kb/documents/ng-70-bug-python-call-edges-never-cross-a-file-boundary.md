---
type: Document
title: 'NG-70: BUG: Python call edges never cross a file boundary'
description: 'Source: NG-70 BUG: Python call edges never cross a file boundary Type:
  Subtask Status: In Review Callees were resolved against the caller''s own module
  with no import resolution, so every cross-file ca'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-70: BUG: Python call edges never cross a file boundary

Source: NG-70

BUG: Python call edges never cross a file boundary

Type: Subtask
Status: In Review

Callees were resolved against the caller's own module with no import
resolution, so every cross-file call pointed at a node that did not exist.
Those edges were discarded at debug level, meaning the build reported success
while producing a call graph that stopped at every file boundary.
Impact
PR impact analysis could not detect a change affecting code in another file,
which is the common case.
Resolution
Call sites are recorded during parse and resolved once every module is known,
using the import bindings actually present in each file. Ambiguous names are
left unresolved rather than guessed, so no edge is invented.
Acceptance criteria
Cross-file call edges are present and non-zero on a multi-module repo

Blast radius for a changed function reaches callers in other files

Existing test suites pass unchanged (423 backend, 54 pnog)
