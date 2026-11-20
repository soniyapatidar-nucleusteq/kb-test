---
type: Document
title: 'NG-68: Fix CMG static graph build failing with socket hang up on large repositories'
description: 'Source: NG-68 Fix CMG static graph build failing with socket hang up
  on large repositories Type: Subtask Status: Done Found while working on the parent
  task — the static graph build for batch-2025-cap'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-68: Fix CMG static graph build failing with socket hang up on large repositories

Source: NG-68

Fix CMG static graph build failing with socket hang up on large repositories

Type: Subtask
Status: Done

Found while working on the parent task — the static graph build for batch-2025-capstone failed every time, blocking the demo setup.
Problem: UI showed socket hang up; the backend then stored a successful build with 0 nodes, overwriting the project's graph.
Cause: the repo's zipball is 69.5 MB and GitHub took 58–194 s to generate it. The Next.js proxy gave up at 30 s, the download timeout was 60 s, and the resulting httpx.RemoteProtocolError escaped the caught exception list — so a slow download was reported as a repo with no code in it. The archive was also being downloaded twice per build.
