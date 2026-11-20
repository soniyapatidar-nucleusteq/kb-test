---
type: Document
title: 'NG-32: Ensure all agent outputs include graph path + OKF citations (cross-cutting
  AC)'
description: 'Source: NG-32 Ensure all agent outputs include graph path + OKF citations
  (cross-cutting AC) Type: Story Status: To Do Labels: BackEnd As a platform architect,
  I want every agent endpoint to cite the '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-32: Ensure all agent outputs include graph path + OKF citations (cross-cutting AC)

Source: NG-32

Ensure all agent outputs include graph path + OKF citations (cross-cutting AC)

Type: Story
Status: To Do
Labels: BackEnd

As a platform architect,
I want every agent endpoint to cite the graph path and OKF source documents that produced its output,
So that no agent response is a black-box probability score.

Description 

The cross-cutting Explainability acceptance criteria require that every agent output cites its evidence. This task audits all agent endpoints (RCA, blast radius, predictive alert, PR review) and adds citations[] where missing. It is the final quality gate before the platform is considered production-ready.

Acceptance Criteria 
RCA endpoint (PNOG-101) citations[] verified present and accurate.

Blast radius endpoint includes graph path showing which downstream edges carry impact and their current weights.

Predictive alert push (PNOG-105) includes OKF node link and graph path in alert body.

PR review response includes list of affected nodes with their scope (DEV/SRE/SEC) and current weight.

No endpoint returns a bare numeric score without a supporting graph path.

Automated contract test: each agent endpoint response schema validated against citations[] requirement.
