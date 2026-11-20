---
type: Document
title: 'NG-30: Mount /config/repos backend routes to connect frontend repo configuration
  page'
description: 'Source: NG-30 Mount /config/repos backend routes to connect frontend
  repo configuration page Type: Story Status: To Do Labels: BackEnd As a platform
  operator, I want to manage GitHub repo connections '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-30: Mount /config/repos backend routes to connect frontend repo configuration page

Source: NG-30

Mount /config/repos backend routes to connect frontend repo configuration page

Type: Story
Status: To Do
Labels: BackEnd

As a platform operator,
I want to manage GitHub repo connections from the UI,
So that I can add, edit, or remove repos without editing environment files
Description 
Similar to the Kafka config gap (PNOG-106), the frontend page service/frontend/pages/config/repos/index.js exists and renders a repo configuration UI. The backend routes it depends on are not mounted in service/backend/app/main.py.
This story registers the repo config routes, allowing operators to add/remove GitHub repo connections, set the default branch (CMG_DEFAULT_REF), and view the current git config — all from the UI.

Acceptance Criteria 
Repo config router registered in service/backend/app/main.py.

GET /config/repos returns list of configured repos with: url, default_branch, last_sync_at, status.

POST /config/repos adds a new repo connection (url, branch, GitHub token stored in OrgDatasource).

DELETE /config/repos/{id} removes a repo connection.

Frontend /config/repos page reads and writes via the API — no hardcoded values.

CMG_DEFAULT_REF env var is overridable per-repo from the UI.
