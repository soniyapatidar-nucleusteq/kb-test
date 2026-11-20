---
type: Document
title: 'NG-91: Knowledge graph screen: one consistent view, incident code links and
  zoom'
description: 'Source: NG-91 Knowledge graph screen: one consistent view, incident
  code links and zoom Type: Story Status: In Review User story As someone investigating
  an incident, I want the knowledge graph to loo'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-91: Knowledge graph screen: one consistent view, incident code links and zoom

Source: NG-91

Knowledge graph screen: one consistent view, incident code links and zoom

Type: Story
Status: In Review

User story As someone investigating an incident, I want the knowledge graph to look and behave the same everywhere and to take me straight to the failing line of code, so that I can move from an incident to its cause without hunting through files.
Description The knowledge graph had several problems:
The full observability suite drew it with a different graph and a thinner detail panel than the project dashboard.

An incident named the part of the code that failed, but not the exact line, and it had no link to the code.

Long log lines and cause text overflowed the panel.

Scrolling or pinching over any graph zoomed the whole page instead of the graph.

What was done:
Same view everywhere: the full suite's knowledge graph now uses the same graph and detail panel as the project dashboard. The page layout, filters and node cards are unchanged. Filtering by kind now hides other kinds instead of dimming them. Clicking a part of the code loads its knowledge context.

Complete incident detail: in one place, the detail shows the ticket, cause, caused by, failed in, code path, trigger, exception, occurrence times, log lines, live signal and knowledge context.

Link to the failing line:
When a log names a file and line, the incident now keeps it.

"Caused by" and "Failed in" show the file and line, with a link that opens that line on GitHub at the exact version of the code.

Incidents recorded before this change link to where the code is defined, marked "(def)".


Tidier panel: raw log lines are collapsed by default and scroll inside their own box, and long cause text wraps.

Zoom: scrolling or pinching over the static graph or the knowledge graph zooms only the graph. The knowledge graph can now also be zoomed towards the cursor, dragged to move around, and reset to the starting view.

Acceptance criteria
The knowledge graph and its detail panel look the same in the full suite and on the project dashboard.

An incident shows the file and line where it failed, and the link opens that line on GitHub.

Older incidents still show a link to where the code is defined.

Raw log lines start collapsed, and long text doesn't overflow.

Scrolling or pinching over a graph never zooms or scrolls the page.

All backend tests pass, and both knowledge graph tabs load in the browser without errors
