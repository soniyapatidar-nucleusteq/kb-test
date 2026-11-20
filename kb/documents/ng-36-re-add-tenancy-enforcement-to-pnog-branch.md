---
type: Document
title: 'NG-36: Re-add tenancy enforcement to pnog branch'
description: 'Source: NG-36 Re-add tenancy enforcement to pnog branch Type: Story
  Status: To Do tenancy.py exists only as a stray compiled .pyc file — not tracked
  source. There is zero RBAC/tenancy enforcement on t'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-36: Re-add tenancy enforcement to pnog branch

Source: NG-36

Re-add tenancy enforcement to pnog branch

Type: Story
Status: To Do

tenancy.py exists only as a stray compiled .pyc file — not tracked
source. There is zero RBAC/tenancy enforcement on this branch. Any
caller with a valid org/project ID pair gets access today.
Port service/backend/app/security/tenancy.py from the
pr-testcases-and-graph branch. Wire require_project_access into all
project_graphs.py routes. Default ENFORCE_TENANT_ISOLATION=1.
Cross-tenant bleed is a P0 defect per the original backlog.
BLOCKS: NG-33 (isolation test has nothing to test without this).


Acceptance Criteria:
tenancy.py restored as tracked source (not .pyc)

require_project_access dependency added to all routes in project_graphs.py

ENFORCE_TENANT_ISOLATION=1 set as default

Request with mismatched org/project ID returns 403, not data
