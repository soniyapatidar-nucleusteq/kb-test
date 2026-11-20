---
type: Document
title: 'NG-39: Terraform state/plan parser'
description: 'Source: NG-39 Terraform state/plan parser Type: Story Status: To Do
  User Story: As a platform engineer, I want Terraform-managed infrastructure to appear
  in the graph, so that I can see cloud resource'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-39: Terraform state/plan parser

Source: NG-39

Terraform state/plan parser

Type: Story
Status: To Do

User Story:
As a platform engineer, I want Terraform-managed infrastructure to appear in the graph, so that I can see cloud resources alongside my application code and Docker/K8s topology.
Description:
The system currently parses Docker Compose, nginx, and Kubernetes manifests into infra nodes, but has no Terraform support. This story adds a new parser under pnog/cmg/parsers/ (or service/backend/app/parsers/) that reads Terraform state or plan files and feeds SERVICE/COMPUTE_RESOURCE nodes into the same schema used by the existing infra parsers.
Acceptance Criteria:
New Terraform parser reads .tf files or terraform show -json plan/state output.

Terraform resources (e.g. aws_instance, aws_rds_cluster) map to SERVICE or COMPUTE_RESOURCE node types consistent with the existing type schema.

Terraform-derived nodes merge into the same graph as Docker Compose/K8s nodes — no separate graph or duplicate namespace.

Resource dependencies declared in Terraform (e.g. depends_on) become edges in the graph.

Parser runs as part of the same CMG build flow — no separate manual trigger required.

A repo with no Terraform files builds successfully with zero Terraform nodes (no errors).

Dependencies: None — follows the same pattern as existing config/infra parsers.
