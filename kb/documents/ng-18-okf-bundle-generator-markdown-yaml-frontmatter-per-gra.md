---
type: Document
title: 'NG-18: OKF bundle generator — markdown + YAML frontmatter per graph node'
description: 'Source: NG-18 OKF bundle generator — markdown + YAML frontmatter per
  graph node Type: Story Status: Done As a developer or AI agent, I want to download
  the application knowledge graph as a directory o'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-18: OKF bundle generator — markdown + YAML frontmatter per graph node

Source: NG-18

OKF bundle generator — markdown + YAML frontmatter per graph node

Type: Story
Status: Done

As a developer or AI agent,
I want to download the application knowledge graph as a directory of markdown files,
So that I can query it with any agent, RAG pipeline, or semantic search tool without an SDK.

Description 

The product backlog North Star (F1.4) requires every graph node to be serializable to an OKF-compliant markdown file with YAML frontmatter (OKF v0.1: type, title, description, resource, tags, timestamp). This is a cross-cutting requirement — RCA citations (PNOG-101), the MCP endpoint (PNOG-103), and the knowledge base UI (PNOG-303) all depend on OKF files existing.
This story implements POST /orgs/{org_id}/projects/{project_id}/graph/okf/build, which generates the bundle and makes it downloadable as a .zip. The output must be git-hostable and vendor-neutra

Acceptance Criteria 
POST /orgs/{org_id}/projects/{project_id}/graph/okf/build generates one .md file per graph node.

Each file has YAML frontmatter with: type, title, description, resource (source file path), tags[], timestamp.

The bundle is downloadable as a .zip via GET /orgs/{org_id}/projects/{project_id}/graph/okf/download.

Files are valid markdown and render correctly in GitHub, Obsidian, and any standard markdown viewer.

Bundle is vendor-neutral — no PNOG-specific SDK required to read or query it.

Build time for a 200-node graph is under 30 seconds.

A node with no linked source file still generates a valid OKF file with resource: null.
