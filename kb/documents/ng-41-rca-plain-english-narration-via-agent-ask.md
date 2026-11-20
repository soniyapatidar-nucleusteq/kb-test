---
type: Document
title: 'NG-41: RCA plain-English narration via /agent/ask'
description: 'Source: NG-41 RCA plain-English narration via /agent/ask Type: Story
  Status: Done As an SRE during an incident, I want a plain-English explanation of
  the root cause, not just a raw graph path, so that'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-41: RCA plain-English narration via /agent/ask

Source: NG-41

RCA plain-English narration via /agent/ask

Type: Story
Status: Done

As an SRE during an incident, I want a plain-English explanation of the root cause, not just a raw graph path, so that I can understand and act on it quickly without manually reading the graph.
Description: Real RCA exists in two places — GET /cmg/rca/{node_id} (global, BFS-based) and the per-project GET /orgs/.../graph/rca/{node_id} (the actual Dijkstra-weighted one). Note: GET /orgs/.../graph/propagation is plain BFS, not Dijkstra, despite this ticket originally implying otherwise — narration should source its graph-path context from /graph/rca/{node_id}, not /propagation.
/agent/ask is moving this sprint from a local Ollama model onto the Claude API (Ollama kept only as an offline dev fallback behind the same provider interface, not removed). This story feeds real RCA output into /agent/ask as context, adds a "Narrate this root cause" action to the UI, and additionally enriches the explanation with incident/runbook/team-ownership context from the knowledge graph layer when it exists for the affected node(s).
Acceptance Criteria:
RCA output (graph path, weights, affected nodes) from GET /orgs/.../graph/rca/{node_id} is passed as context to /agent/ask.

The Claude API generates a plain-English summary of the root cause: what happened, what's affected, and likely cause — grounded in the actual graph path, not a generic response.

If the affected node(s) have linked incidents, a runbook, or a known owning team in the knowledge graph, the narration includes that context (e.g., "this has occurred before — 2 prior incidents; see Runbook X; owned by Team Y").

"Narrate this root cause" button/action added to the RCA panel.

Narration includes the underlying graph path so the explanation can be verified, not just trusted blindly.

If the Claude API is unreachable, the key is missing/invalid, or the account is over quota, the UI falls back to showing the raw graph path with a clear "narration unavailable" message — never a blank or broken state.

Response streams token-by-token (existing SSE contract); target under ~2 seconds to first token and under ~8 seconds for the full narration — a network-latency target against a hosted API, not the old local-CPU one.

Dependencies: Requires the Claude API provider swap (ANTHROPIC_API_KEY + the provider abstraction) to already be in place. This ticket wires narration on top of that client — it does not build the client itself. If that foundational work isn't done yet, it should be pulled in as a blocking dependency before this ticket starts, which would extend the estimate given separately.
