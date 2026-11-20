---
type: Document
title: 'NG-84: Link each log line to the code that wrote it'
description: 'Source: NG-84 Link each log line to the code that wrote it Type: Story
  Status: In Review User story As an engineer investigating a problem, I want each
  log line linked to the function, class or file t'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-84: Link each log line to the code that wrote it

Source: NG-84

Link each log line to the code that wrote it

Type: Story
Status: In Review

User story As an engineer investigating a problem, I want each log line linked to the function, class or file that wrote it, so that I can go straight to the code instead of only seeing the service name.
Description Lines used to be linked only to the whole service. Now each line is linked to the most specific part of the code it can be matched to: function, class, file or module. The platform uses whatever the line provides:
the logger name, including the shortened names Spring uses;

stack trace frames, keeping their line numbers;

file paths;

names written in the message.

A name that is spelled differently or written only in part is still matched when exactly one part of the code fits. Where several parts fit, the match is marked as uncertain. Each link records what found it (a pattern, the model, the logger or a name), along with the code line number.
A set of demo scenarios was added to the Java example application. They show lines matched by a pattern, lines matched by the model, and junk lines that correctly stay unmatched. While building them, a crash caused by a junk line was found and fixed. Before the fix, that crash could stall the processing of all logs.
Acceptance criteria
A line from a Java or Python application links to the function or class that wrote it, where that can be worked out.

Stack trace frames link to their methods, with line numbers.

Partial or differently spelled names link only when exactly one part of the code fits.

Junk or unrelated lines stay unmatched and never stop processing.
