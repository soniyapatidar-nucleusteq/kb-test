---
type: Document
title: 'NG-63: Ship a Docker-socket log collector and make log ingestion project-aware'
description: 'Source: NG-63 Ship a Docker-socket log collector and make log ingestion
  project-aware Type: Story Status: Done User Story: As a platform operator, I want
  any locally running service''s logs to be autom'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-63: Ship a Docker-socket log collector and make log ingestion project-aware

Source: NG-63

Ship a Docker-socket log collector and make log ingestion project-aware

Type: Story
Status: Done

User Story: As a platform operator, I want any locally running service's logs to be automatically collected and turned into live graph weights on the correct project's graph, so that observability works out of the box without touching the monitored service or manually wiring up which project it belongs to.
Description:
Two real gaps exist today, confirmed directly against the running code:
Nothing collects logs today. No log-collector component exists anywhere on this branch's history — it fails silently, so logs are simply lost with no error surfaced. (Couldn't independently confirm "the collector was deleted from the repo" specifically — there's an unrelated Fluentd-based setup, {{infra/fluentd/}}, on a much older, unmerged branch that predates {{dev}} entirely and was never part of this branch's lineage. Worth confirming with Soniya whether that's the thing she means, or whether she's referring to something else that existed elsewhere — it changes whether this is a from-scratch build or a partial port.)

Ingestion is global-only and hardcoded. The consumer ({{service/weight-worker/worker.py}}) matches incoming events against a fixed {{_CONTAINER_MAP}} of only this platform's own container names (frontend, nginx, fastapi, postgres, kafka, redis, etc.), and every matched event lands on the single global demo graph — never a specific tenant's project graph. This is a known, previously-documented limitation, not a new finding.

Proposed pipeline: One collector container per machine, reading the Docker socket, normalizing each log line into a fixed set of fields, and publishing to the existing 8 Kafka topics ({{app.events}}, {{net.requests}}, {{cache.events}}, {{db.queries}}, {{frontend.errors}}, {{git.releases}}, {{metrics.resources}}, {{pod.logs}} — confirmed this is the platform's complete topic set). The consumer then resolves each event to a specific project + graph node before weighting lands.
No changes to any monitored service — Compose already labels every container with its stack and service name ({{com.docker.compose.project}}/{{com.docker.compose.service}}), which a socket-attached collector gets for free without touching the service itself.
Acceptance Criteria:
A collector container reads the Docker socket and captures logs for every running container on the host, requiring zero changes (code, config, or env var) to any monitored service.

Each log line is normalized into a fixed field set before publishing — timestamp, stack label, container/service name, log level, and the raw line at minimum.

Normalized events are published to the correct one of the existing 8 Kafka topics, not a single catch-all topic.

The consumer resolves each event to a specific project automatically, using all three signals scored against data already stored, not a hardcoded list:
Stack name vs. the project's repo name (available today via ProjectGraph.repo)

The container name set vs. service:-prefixed nodes in that project's graph

The Java/Python package in the logger name vs. class:-prefixed nodes in that graph — confirmed Java class node ids already embed the full dotted package path (class:com.example.pkg.ClassName), which is a direct, clean match against a logger name; Python class ids embed the module path similarly.


When a confident match is found, the event's weight lands on that specific project's graph, not the global demo graph.

No UI step or manual project association is required — matching is fully automatic end-to-end.
