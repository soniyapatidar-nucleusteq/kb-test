---
type: Document
title: 'NG-65: BUG: Root Cause and Blast Radius results are the wrong way round'
description: 'Source: NG-65 BUG: Root Cause and Blast Radius results are the wrong
  way round Type: Subtask Status: Done As an engineer responding to an incident, I
  want Blast Radius to list the components that are '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-65: BUG: Root Cause and Blast Radius results are the wrong way round

Source: NG-65

BUG: Root Cause and Blast Radius results are the wrong way round

Type: Subtask
Status: Done

As an engineer responding to an incident, I want Blast Radius to list the components that are affected when something fails, so that I can judge how serious the issue is and who to inform.
Right now the two lists are swapped. Blast Radius shows what the failing component relies on, and Root Cause shows what relies on it — the opposite of what each label promises. The result is that the severity call can't be trusted: in one case an API gateway failure listed a test-only library as "affected", which would never be impacted by that outage.
The platform's other analysis view already gets this right, so the two screens currently disagree about the same component.
Acceptance criteria
Blast Radius lists the components affected when the selected one fails

Root Cause lists the components the selected one relies on

Both views agree for the same component

Existing tests continue to pass
