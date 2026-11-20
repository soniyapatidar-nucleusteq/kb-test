---
type: Document
title: 'NG-20: Allow upload of requirement docs, runbooks, and Jira tickets linked
  to graph nodes'
description: 'Source: NG-20 Allow upload of requirement docs, runbooks, and Jira tickets
  linked to graph nodes Type: Story Status: Done As a solutions engineer, I want to
  upload requirement documents, runbooks, and'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-20: Allow upload of requirement docs, runbooks, and Jira tickets linked to graph nodes

Source: NG-20

Allow upload of requirement docs, runbooks, and Jira tickets linked to graph nodes

Type: Story
Status: Done

As a solutions engineer,
I want to upload requirement documents, runbooks, and Jira ticket exports and link them to specific graph nodes,
So that agents can retrieve intent and business context — not just code structure.
Description 
The backlog (F1.3) requires contextual supplement inputs to be linked to graph nodes so agents can retrieve intent. Currently no upload mechanism exists. This story adds a file upload panel to the node detail sidebar, stores uploaded docs in the org_datasources table with node_id tagging, and exposes them via GET /cmg/node/<id>/context.

Acceptance Criteria 
Node detail sidebar includes a drag-and-drop upload panel supporting .md, .txt, and .pdf files.

Uploaded files are stored with org_id, project_id, and node_id tags in the org_datasources table.

GET /cmg/node/<id>/context returns a list of linked documents: filename, type, excerpt (first 300 chars), upload timestamp.

Agent queries via GET /mcp/context include linked document content in the citations[] array.

File size limit: 5 MB per file. Files exceeding this show a clear error message.

Deleting a linked doc removes it from the node detail panel and the context API response.
