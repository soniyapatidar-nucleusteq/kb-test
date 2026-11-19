---
type: Document
title: inventory-requirements.docx
description: 'Inventory Reservation Requirements Owner: Fulfilment team Before a checkout
  is confirmed, the InventoryClient reserves stock through the StockService. If a
  reservation fails, the CheckoutController mu'
resource: null
tags:
- document
- upload
- docx
timestamp: '2026-11-19T15:28:53.512003'
---

# inventory-requirements.docx

Inventory Reservation Requirements
Owner: Fulfilment team
Before a checkout is confirmed, the InventoryClient reserves stock through the StockService.
If a reservation fails, the CheckoutController must release any stock already held.
Supplier feeds are loaded by the SupplierFeedImporter; rows with a negative quantity are rejected.
Stock must never go below zero.

## Connections

- [[classes/com.example.inventory.StockService|com.example.inventory.StockService]] — DESCRIBES, outgoing
- [[classes/com.example.inventory.SupplierFeedImporter|com.example.inventory.SupplierFeedImporter]] — DESCRIBES, outgoing
- [[classes/com.example.order.checkout.CheckoutController|com.example.order.checkout.CheckoutController]] — DESCRIBES, outgoing
- [[classes/com.example.order.checkout.InventoryClient|com.example.order.checkout.InventoryClient]] — DESCRIBES, outgoing
