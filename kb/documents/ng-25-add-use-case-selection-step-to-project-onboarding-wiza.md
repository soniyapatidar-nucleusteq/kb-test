---
type: Document
title: 'NG-25: Add use-case selection step to project onboarding wizard'
description: 'Source: NG-25 Add use-case selection step to project onboarding wizard
  Type: Story Status: To Do Labels: Frontend As a user onboarding a new project, I
  want to select my target use cases during setup,'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-25: Add use-case selection step to project onboarding wizard

Source: NG-25

Add use-case selection step to project onboarding wizard

Type: Story
Status: To Do
Labels: Frontend

As a user onboarding a new project,
I want to select my target use cases during setup,
So that the platform pre-configures knowledge weighting and features relevant to my team from day one.
Description 

The backlog (F1.5) requires use-case scoping at onboarding time. The OrgOnboarding wizard already exists (referenced in org admin dashboard) but does not include a use-case selection step. This story adds step 3 to the wizard with checkboxes for: Log Enrichment, PR Review Assist, Blast Radius, Predictive Alerting, RCA. The selection is stored and used to pre-tune λ decay and enable/disable feature tabs.

Acceptance Criteria 

Onboarding wizard step 3 presents checkboxes for: Log Enrichment, PR Review Assist, Blast Radius, Predictive Alerting, RCA.

At least one use case must be selected to proceed (validation on Next button).

Selection is stored in OrgOnboarding.selected_use_cases as a JSON array.

Platform pre-enables relevant feature tabs based on selection (e.g., selecting RCA enables the RCA panel; selecting Predictive Alerting enables the LSTM tab).

λ decay default pre-set per use case: Predictive Alerting uses λ=0.05 (slower decay); Log Enrichment uses λ=0.1 (default).

Selection can be changed later in project Settings → Use Cases without re-running the full wizard.
