---
type: Document
title: 'NG-83: Understand each log line: patterns first, then an AI model'
description: 'Source: NG-83 Understand each log line: patterns first, then an AI model
  Type: Story Status: In Review User story As the platform, I want to work out what
  each log line means, so that errors are recog'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-83: Understand each log line: patterns first, then an AI model

Source: NG-83

Understand each log line: patterns first, then an AI model

Type: Story
Status: In Review

User story As the platform, I want to work out what each log line means, so that errors are recognised and grouped correctly, whatever the technology or wording.
Description The platform now reads each line in three stages, from cheapest to most expensive:
Known patterns. A library of general log shapes covers Java, Python, microservices and data pipelines. Each pattern is tagged with technology, application type, domain and industry. Most routine Airflow output is recognised at this stage.

Grouping. Lines that differ only in values such as IDs or times are grouped into one template, so each kind of line is worked out only once.

AI model. A model trained for log reading handles only lines the patterns couldn't understand, and only once per new kind of line. Where the patterns and the model disagree, the difference is recorded for review.

The data model was designed and revised after review to hold the model's results and graph versions.
Acceptance criteria
Lines the patterns recognise never go to the model.

The model reads each new kind of line once, not every time it appears.

Most routine Airflow lines are recognised by patterns.

The same error with different values is grouped as one kind of line.
