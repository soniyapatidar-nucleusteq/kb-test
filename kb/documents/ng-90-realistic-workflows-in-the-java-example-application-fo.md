---
type: Document
title: 'NG-90: Realistic workflows in the Java example application, for the demo'
description: 'Source: NG-90 Realistic workflows in the Java example application, for
  the demo Type: Subtask Status: To Do User story As someone demonstrating the platform,
  I want the Java example application to pro'
resource: null
tags:
- document
- jira
timestamp: '2026-11-20T11:54:14.719910'
---

# NG-90: Realistic workflows in the Java example application, for the demo

Source: NG-90

Realistic workflows in the Java example application, for the demo

Type: Subtask
Status: To Do

User story As someone demonstrating the platform, I want the Java example application to produce every kind of log line through normal use, so that the Log Status screen and incident creation can be shown on realistic traffic instead of artificial error buttons.
Description The demo used buttons that each wrote a fixed set of log lines or triggered one error. That showed each case, but it didn't look like a real application. The buttons were replaced with two real features. Their normal use produces every case the Log Status screen reports, and their built-in defects create incidents.
Checkout (order service, which calls the inventory service):
reserves stock and prices the basket with volume discounts, coupons and tax;

records an order for each line, and releases the stock if any step fails;

writes a step-by-step trace and a finance audit trail.


Supplier restock feed (inventory service): imports a supplier's price file and prints a plain-text report of the rows it rejected.

Order lookup: a new way to fetch a single order.

Defects left in on purpose, for the platform to catch:
an invoice total that doesn't match what was charged;

supplier prices written with a decimal comma.


Every Log Status case is covered:
standard lines linked to code by a pattern;

standard lines linked to code by the AI model;

well-formed lines that name no code;

unstructured lines with no time or level.


Lines shaped for the demo: the trace lines were adjusted so the cases separate cleanly. Lines meant for the AI model form their own kind of line, so the model reads them, rather than being grouped with general application output.

Scenario guide: a document in the Java application lists each scenario, how to produce it (for example, which basket or supplier file to use), the expected log lines, and what the platform should show.

Acceptance criteria
Each scenario is produced by using the application normally, with no special buttons or error endpoints.

After running the scenarios, the Log Status screen shows lines identified by a pattern, by the model, and by neither, for both standard and unstructured lines.

The defects left in on purpose create incidents in the platform.

The scenario guide lets someone else reproduce each case.
