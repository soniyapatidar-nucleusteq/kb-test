---
type: Document
title: pricing-requirements.md
description: 'Owner: Payments team · Status: Approved · Version 1.3'
resource: null
tags:
- document
- upload
- md
timestamp: '2026-11-19T10:11:45.835409'
---

# pricing-requirements.md

Owner: Payments team · Status: Approved · Version 1.3

## Purpose

Defines how the order service prices a checkout, so that every order total a
customer sees is the amount they are charged.

## Volume discounts

- Orders of 100 units or more get a volume discount, applied per line by
  `PricingEngine.volumeRate`.
- The discount must never exceed **30%** of the line total.
- `volumeRate` must reject a quantity of zero or less instead of indexing into
  the rate table — negative quantities caused the "Array index out of bounds"
  incident in production.

## Quotes

- `PricingEngine.quote` prices every line before the customer confirms.
- A quote is valid for 15 minutes; after that the `CheckoutController` must ask
  for a new one.

## Stock

- Before confirming, the checkout reserves stock through `InventoryClient`.
- If the inventory service is unavailable, retry twice, then fail the checkout
  with `InventoryUnavailableException` — never confirm an order without a
  reservation.

## Invoices

- `InvoiceCheck.invoiceTotal` must equal the sum of the priced lines, to the
  cent. Any difference blocks the invoice and raises an alert.

## Out of scope

Refunds and partial shipments are covered by the Fulfilment requirements
document.

## Connections

- [[classes/com.example.order.checkout.CheckoutController|com.example.order.checkout.CheckoutController]] — DESCRIBES, outgoing
- [[classes/com.example.order.checkout.InventoryClient|com.example.order.checkout.InventoryClient]] — DESCRIBES, outgoing
- [[classes/com.example.order.checkout.InventoryUnavailableException|com.example.order.checkout.InventoryUnavailableException]] — DESCRIBES, outgoing
- [[classes/com.example.order.checkout.InvoiceCheck|com.example.order.checkout.InvoiceCheck]] — DESCRIBES, outgoing
- [[classes/com.example.order.checkout.PricingEngine|com.example.order.checkout.PricingEngine]] — DESCRIBES, outgoing
- [[functions/com.example.order.checkout.InvoiceCheck_invoiceTotal|com.example.order.checkout.InvoiceCheck_invoiceTotal]] — DESCRIBES, outgoing
- [[functions/com.example.order.checkout.PricingEngine_volumeRate|com.example.order.checkout.PricingEngine_volumeRate]] — DESCRIBES, outgoing
