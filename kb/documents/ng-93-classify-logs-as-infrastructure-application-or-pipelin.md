---
type: Document
title: 'NG-93: Classify logs as infrastructure, application or pipeline, and point
  incidents at code only for application errors'
description: 'Source: NG-93 Classify logs as infrastructure, application or pipeline,
  and point incidents at code only for application errors Type: Story Status: In Progress
  User story As an engineer investigating '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-93: Classify logs as infrastructure, application or pipeline, and point incidents at code only for application errors

Source: NG-93

Classify logs as infrastructure, application or pipeline, and point incidents at code only for application errors

Type: Story
Status: In Progress

User story As an engineer investigating an incident, I want to know whether a failure came from the infrastructure or from the application code, so that I'm sent to the code only when the code is at fault, and otherwise to the service or dependency that actually failed.
Description
The problem Every incident points at a code snippet, even when the code is not at fault. An out-of-memory error, a host name that does not resolve, a full disk or a database that is down all surface in some line of application code. The incident then names that line as the cause, and the developer looks in the wrong place. A NullPointerException, by contrast, really is in the code, and there the code link is exactly what is needed.
What changes
Every log category gets a log type that says where to look:
Infrastructure: host, container, memory, disk, network, DNS, a database, cache or broker that is down, credentials.

Application: the project's own code is wrong (null pointer, missing column, SQL error, bad input handling).

Pipeline: a pipeline run reports it (task failed, executor lost, SLA missed, rows rejected, schema mismatch).


The types are kept in a new table, log_type, which maps a category to its type. log_category and log_rule are not changed: a rule gets its type through its category.

When the category doesn't decide (an unhandled error, a 5xx), the incident decides from its own lines, in this order:
A stack trace through the project's code → application.

The log comes from a service that runs a stock image the project doesn't build, such as postgres:16 → infrastructure.

A task or pipeline is named → pipeline.


Infrastructure incidents name the failing dependency or service as the cause, never code. The code line where the error appeared is still shown, but muted and labelled "Surfaced in (not the cause)". Application incidents keep pointing at the code and its GitHub line as today.

The incident panel shows the log type as a badge.

Supporting changes
Standard category names: <subject>_<state>, e.g. db_connection_failed, jar_missing. Duplicates are merged, and technology prefixes and severity are removed from the names. Existing rules, rule suggestions and incidents are renamed to match.

Wider generic rule word lists, so common infrastructure messages get a category instead of falling through: "no response … within N seconds", "the database system is starting up", "address already in use / already running", "was sent SIGTERM".

One failure, one incident: a failure whose error line and stack trace arrived in different processing batches no longer splits into two incidents ("Retries exhausted" and "Host name not found").

Out of scope (follow-up) LLM guidance for infrastructure incidents ("what might be wrong and what to do"). The log type stored on each incident is what that work will use to decide when to call the LLM.

Acceptance criteria
Every failure category in log_category maps to infrastructure, application or pipeline in the log_type table. Categories that only describe an effect or an event have no type.

A log type changed by hand in the database is kept after a restart.

An out-of-memory error, a DNS failure or an unreachable dependency creates an incident marked Infrastructure. Its "Caused by" is the service or dependency, not code.

A NullPointerException or a missing column creates an incident marked Application, linked to the code and its source line.

A pipeline task failure creates an incident marked Pipeline.

A log from an off-the-shelf service (e.g. the Postgres container) with no category is classified as infrastructure.

The incident panel shows the log type. For infrastructure, the code location reads "Surfaced in (not the cause)", muted, and no code path is shown.

Category names follow <subject>_<state>; the old names are migrated with no rule left pointing at a missing category.

Stopping inventory-service and placing an order creates one incident ("Host name not found", infrastructure), not several.

Backend, categoriser and log-worker test suites pass.
