---
type: Document
title: 'NG-92: Data model for logs and the knowledge graph'
description: 'Source: NG-92 Data model for logs and the knowledge graph Type: Story
  Status: In Review User story As the platform team, I want an agreed data model for
  log data and the knowledge graph, so that log l'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-92: Data model for logs and the knowledge graph

Source: NG-92

Data model for logs and the knowledge graph

Type: Story
Status: In Review

User story As the platform team, I want an agreed data model for log data and the knowledge graph, so that log lines can be grouped, categorised, linked to code and turned into incidents, without storing every line or rewriting history when the model or code map changes.
Description Before the log pipeline was built, there was no design for where log data and the knowledge graph should live or how they connect. This ticket produced that design, revised it through review, and applied it to the database.
What was done:
Log data model, three versions (8, 9 and 11 October). The tables were designed around the order the pipeline runs: collect, match patterns, group, read with the AI model, link to code. They cover:
where each log comes from: organisation, project, log source and instance;

the kinds of line (templates);

patterns, tagged with domain, industry, technology and application type;

the AI model's results;

code map versions, so a line stays linked to the version of the code it was matched against.

The tables were designed to work for any application, and each one is illustrated with real MovieLens log lines.

Grouping check: the design addresses whether grouping similar lines hides function, class and file names. A rule was adopted so those names are kept.

Knowledge graph storage and linking:
what the knowledge graph holds and which relationships it uses;

where it is stored, with the main database as the source of truth and Neo4j as a copy;

how a log line links to the graph, and how changes are recorded and sent on.


Database scaling plan: what holds up at pilot, growth and large scale, and the first steps to take, such as giving logs their own partitioned database and setting a retention period.

Decision not to store every log line: individual lines aren't kept. Only summaries and the few lines attached to an incident are stored, and the table for raw lines was removed.

Review: the design document was checked against the tables actually built, and comments were written in the document.

Acceptance criteria
A reviewed data model covers log sources, kinds of line, patterns, AI model results, links to code, and code map versions.

The knowledge graph design states what is stored, where it is stored, and how log lines link to it.

Individual log lines aren't stored.

The built tables match the reviewed design, and the differences are written down.
