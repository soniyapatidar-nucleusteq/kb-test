---
type: Document
title: 'NG-29: OpenTelemetry span-to-Kafka bridge — auto-feed OTel traces into weight
  engine'
description: 'Source: NG-29 OpenTelemetry span-to-Kafka bridge — auto-feed OTel traces
  into weight engine Type: Story Status: To Do Labels: BackEnd As an engineer using
  an OpenTelemetry-instrumented service, I want'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-29: OpenTelemetry span-to-Kafka bridge — auto-feed OTel traces into weight engine

Source: NG-29

OpenTelemetry span-to-Kafka bridge — auto-feed OTel traces into weight engine

Type: Story
Status: To Do
Labels: BackEnd

As an engineer using an OpenTelemetry-instrumented service,
I want OTEL spans to be automatically ingested into the PNOG weight engine,
So that my CMG graph reflects real traffic patterns without any custom logging code.

Description 
Teams using standard OTel SDK instrumentation should get PNOG weight updates for free. This story adds an OTel collector config that exports spans to the Kafka net.requests topic, and extends the weight worker EventResolver L2 to parse the OTel span schema (traceId, spanId, service.name, http.method, http.status_code) into CMG node co-occurrences

Acceptance Criteria 
OTel collector configuration exports spans to Kafka topic net.requests.

EventResolver._resolve_l2() parses OTel span attributes: service.name → ServiceCall node, http.url → NetworkRequest node.

Co-occurrence edge created between caller service and callee service for each span pair.

Load test: 1000 spans/second ingested without consumer lag (measured via Kafka consumer group offset).

Teams using standard OTel SDK (Python, Java, Node.js) get automatic CMG weight updates with zero code changes.

OTel bridge is disabled when DISABLE_KAFKA=1 (same toggle as other Kafka consumers).
