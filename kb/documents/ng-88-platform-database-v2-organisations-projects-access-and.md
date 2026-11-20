---
type: Document
title: 'NG-88: Platform database v2: organisations, projects, access and operations
  data'
description: 'Source: NG-88 Platform database v2: organisations, projects, access
  and operations data Type: Story Status: In Review User story As the platform team,
  I want the database to match the agreed design, s'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-88: Platform database v2: organisations, projects, access and operations data

Source: NG-88

Platform database v2: organisations, projects, access and operations data

Type: Story
Status: In Review

User story As the platform team, I want the database to match the agreed design, so that onboarding, access control and pipeline and alert features have a proper place to store their data.
Description After the review of the schema and ERD (entity-relationship diagram) on 23 October, the database was brought in line with the agreed design. Each new table got its own create, read, update and delete API.
What was done:
Reference lists:
Industries and domains are now picked from a list instead of typed as free text, and each domain is linked to its industries.

Data source types come from a catalogue.

A project starts with its organisation's industry.


Project setup: each project now has its own environments (for example production and staging), code repositories with their application type, data sources, members and ticket destinations.

Roles and permissions: standard project roles are created automatically. Roles can be given permissions, and members are given roles on each project.

Build history: each code map build is kept as a version.

Proposed additions: tables for anomalies, root-cause runs, KPI definitions and values, pipeline runs and task runs, table freshness, schema changes, connection scores and their history, and stored credentials.

Credentials: secrets are stored encrypted. The key is never kept in the database, and without a key the platform refuses to store a secret rather than saving it in plain text.

Migration: existing data moves into the new tables automatically on startup. The migration can run again safely and works on a new database.

Documentation: a "differences from the design" document lists every place where the implementation departs from the ERD, and why.

Acceptance criteria
Every table in the agreed design exists, with its links to other tables.

Each new table can be created, read, updated and deleted through the API.

Existing organisations, projects and data sources carry over with no data lost.

Starting the platform again doesn't change or duplicate data.

Credentials are stored encrypted and can't be saved without a key.

A document lists the differences between the implementation and the design.
