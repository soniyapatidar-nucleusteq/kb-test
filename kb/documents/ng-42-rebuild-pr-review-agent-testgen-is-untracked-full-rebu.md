---
type: Document
title: 'NG-42: Rebuild PR Review Agent (testgen/ is untracked — full rebuild)'
description: 'Source: NG-42 Rebuild PR Review Agent (testgen/ is untracked — full
  rebuild) Type: Story Status: In Progress User Story: As a developer opening a pull
  request, I want PNOG to tell me what my change ac'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-42: Rebuild PR Review Agent (testgen/ is untracked — full rebuild)

Source: NG-42

Rebuild PR Review Agent (testgen/ is untracked — full rebuild)

Type: Story
Status: In Progress

User Story:
As a developer opening a pull request, I want PNOG to tell me what my change actually impacts in the graph, so that I can review and test the right things before merging.
Description:
service/backend/app/testgen/ is completely untracked in git on this branch — zero source files exist, only a stale compiled .pyc left over from another branch. This is not a wire-up task, it's a full rebuild. This story ports diff_aware.py, impact.py, and pr_suite.py from the pr-testcases-and-graph branch (or wherever they're currently tracked), reconnects them to a new /cmg/impact endpoint, and reconnects the existing frontend component PRTestCaseGenerator.jsx, which currently has no backend to call.
Acceptance Criteria:
testgen/ ported as tracked source onto dev — the whole package (all ~19 modules, not just the 3 named originally; pr_suite.py depends on several of the others), with its call-graph/node-heat logic reconciled against dev's current, still-live weight-engine and anomaly system rather than the source branch's stripped-down version.

POST /cmg/impact ported and adapted onto dev's current cmg.py (2,435 lines today vs. 779 on the source branch — this is not a drop-in copy).

POST /cmg/pr-suite also ported, explicitly wired as an extension of /slm-tests/generate (reusing its TestCase model, per the source branch's own design), not a duplicate generator.

PRTestCaseGenerator.jsx's existing working flow (/graph/prs, /slm-tests/generate, /cmg/run-tests) is not regressed; the new "graph mode" (impact ranking + graph-aware suggestions) is added alongside it.

Affected nodes ranked by relevance (direct change vs. downstream impact) — unchanged from original.

Generated test suggestions reference real graph node names, not generic templates — unchanged from original.

Integration test: a sample PR diff against a seeded graph returns the expected set of impacted nodes.


Dependencies: Source code confirmed accessible on pr-testcases-and-graph (local + origin). No blocking dependency, but do not merge or cherry-pick directly from that branch — it will delete live features.
