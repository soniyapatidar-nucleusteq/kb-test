---
type: Document
title: 'NG-87: Layered view of the static code graph'
description: 'Source: NG-87 Layered view of the static code graph Type: Subtask Status:
  To Do User story As a user exploring a project''s code map, I want to see it one
  level at a time, as labelled boxes, so that a '
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-87: Layered view of the static code graph

Source: NG-87

Layered view of the static code graph

Type: Subtask
Status: To Do

User story As a user exploring a project's code map, I want to see it one level at a time, as labelled boxes, so that a large graph stays readable and I can drill down from services to functions.
Description A large code map drawn all at once was unreadable. The new hierarchical view, now the default, shows one level at a time:
Services sit at the top. Opening a box shows what is inside it: folders, then files, classes and functions.

Breadcrumbs lead back up.

Boxes are linked by labelled lines that name the kind of link, such as "calls" or "imports". Callers sit above the parts of the code they call.

Links that leave the current view are drawn to faded "ghost" boxes, placed next to their partner. Clicking a ghost goes to it.

The toolbar shows how many services, folders, files, classes and functions are inside the current selection.

Live scores, root-cause results and impact results roll up onto the box that contains each part of the code.

The previous view is still available.

Acceptance criteria
The graph opens at service level and drills down level by level, with breadcrumbs back.

Links leaving the view appear as ghost boxes, and clicking one goes to it.

Live scores and root-cause status show on the box that contains each part of the code.

Counts in the toolbar match the selection.
