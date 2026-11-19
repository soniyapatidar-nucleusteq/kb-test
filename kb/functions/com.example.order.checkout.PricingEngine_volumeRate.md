---
type: FUNCTION
title: volumeRate
description: function volumeRate, defined in order-service/src/main/java/com/example/order/checkout/PricingEngine.java.
  Connected to invoiceTotal, quote, PricingEngine and 5 other(s).
resource: order-service/src/main/java/com/example/order/checkout/PricingEngine.java
tags:
- function
timestamp: '2026-11-19T07:38:32.700863'
---

# volumeRate

function volumeRate, defined in order-service/src/main/java/com/example/order/checkout/PricingEngine.java. Connected to invoiceTotal, quote, PricingEngine and 5 other(s).

## Business context

- Adds price

## Linked documents

- [[documents/release-1-4-0|release-1-4-0]] — release_note 1.4.0, found in the text
- [[documents/pricing-requirements-md|pricing-requirements-md]] — upload

## Known problems

- [[incidents/array-index-out-of-bounds-exception|array-index-out-of-bounds-exception]] — Array index out of bounds exception (error, open, 3 occurrences) — caused here

## Runbooks

- [[runbooks/string|string]] — string

## Connections

- [[functions/com.example.order.checkout.InvoiceCheck_invoiceTotal|com.example.order.checkout.InvoiceCheck_invoiceTotal]] — calls, incoming
- [[functions/com.example.order.checkout.PricingEngine_quote|com.example.order.checkout.PricingEngine_quote]] — calls, incoming
- [[classes/com.example.order.checkout.PricingEngine|com.example.order.checkout.PricingEngine]] — member_of, outgoing
- [[modules/com.example.order.checkout|com.example.order.checkout]] — defined_in, outgoing
- [[incidents/array-index-out-of-bounds-exception|array-index-out-of-bounds-exception]] — CAUSED_BY, incoming
- [[runbooks/string|string]] — COVERS, incoming
- [[documents/pricing-requirements-md|pricing-requirements-md]] — DESCRIBES, incoming
- [[documents/release-1-4-0|release-1-4-0]] — DESCRIBES, incoming
