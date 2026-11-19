---
type: MODULE
title: com.example.order.checkout
description: module com.example.order.checkout. Connected to com.example.order, com.example.order,
  Checkout and 68 other(s).
resource: null
tags:
- module
timestamp: '2026-11-19T10:12:52.093964'
---

# com.example.order.checkout

module com.example.order.checkout. Connected to com.example.order, com.example.order, Checkout and 68 other(s).

## Connections

- [[modules/com.example.order|com.example.order]] — imports, incoming
- [[modules/com.example.order|com.example.order]] — imports, outgoing
- [[classes/com.example.order.checkout.Checkout|com.example.order.checkout.Checkout]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_confirm|com.example.order.checkout.Checkout_confirm]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_fail|com.example.order.checkout.Checkout_fail]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getId|com.example.order.checkout.Checkout_getId]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getCustomer|com.example.order.checkout.Checkout_getCustomer]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getCouponCode|com.example.order.checkout.Checkout_getCouponCode]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getStatus|com.example.order.checkout.Checkout_getStatus]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getUnits|com.example.order.checkout.Checkout_getUnits]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getSubtotal|com.example.order.checkout.Checkout_getSubtotal]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getVolumeDiscount|com.example.order.checkout.Checkout_getVolumeDiscount]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getCouponDiscount|com.example.order.checkout.Checkout_getCouponDiscount]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getTax|com.example.order.checkout.Checkout_getTax]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getTotal|com.example.order.checkout.Checkout_getTotal]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getFailureReason|com.example.order.checkout.Checkout_getFailureReason]] — defined_in, incoming
- [[functions/com.example.order.checkout.Checkout_getCreatedAt|com.example.order.checkout.Checkout_getCreatedAt]] — defined_in, incoming
- [[classes/com.example.order.checkout.Status|com.example.order.checkout.Status]] — defined_in, incoming
- [[classes/com.example.order.checkout.CheckoutAudit|com.example.order.checkout.CheckoutAudit]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutAudit_confirmed|com.example.order.checkout.CheckoutAudit_confirmed]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutAudit_cancelled|com.example.order.checkout.CheckoutAudit_cancelled]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutAudit_invoiceMismatch|com.example.order.checkout.CheckoutAudit_invoiceMismatch]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutAudit_money|com.example.order.checkout.CheckoutAudit_money]] — defined_in, incoming
- [[classes/com.example.order.checkout.CheckoutController|com.example.order.checkout.CheckoutController]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_checkout|com.example.order.checkout.CheckoutController_checkout]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_recent|com.example.order.checkout.CheckoutController_recent]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_summary|com.example.order.checkout.CheckoutController_summary]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_one|com.example.order.checkout.CheckoutController_one]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_invalid|com.example.order.checkout.CheckoutController_invalid]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_outOfStock|com.example.order.checkout.CheckoutController_outOfStock]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_unavailable|com.example.order.checkout.CheckoutController_unavailable]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_failed|com.example.order.checkout.CheckoutController_failed]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutController_error|com.example.order.checkout.CheckoutController_error]] — defined_in, incoming
- [[classes/com.example.order.checkout.CheckoutRepository|com.example.order.checkout.CheckoutRepository]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutRepository_findTop20ByOrderByIdDesc|com.example.order.checkout.CheckoutRepository_findTop20ByOrderByIdDesc]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutRepository_findByCustomerIgnoreCase|com.example.order.checkout.CheckoutRepository_findByCustomerIgnoreCase]] — defined_in, incoming
- [[classes/com.example.order.checkout.CheckoutRequest|com.example.order.checkout.CheckoutRequest]] — defined_in, incoming
- [[classes/com.example.order.checkout.Line|com.example.order.checkout.Line]] — defined_in, incoming
- [[classes/com.example.order.checkout.CheckoutWorkflow|com.example.order.checkout.CheckoutWorkflow]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_run|com.example.order.checkout.CheckoutWorkflow_run]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_recent|com.example.order.checkout.CheckoutWorkflow_recent]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_validate|com.example.order.checkout.CheckoutWorkflow_validate]] — defined_in, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_fail|com.example.order.checkout.CheckoutWorkflow_fail]] — defined_in, incoming
- [[classes/com.example.order.checkout.CustomerSummary|com.example.order.checkout.CustomerSummary]] — defined_in, incoming
- [[functions/com.example.order.checkout.CustomerSummary_of|com.example.order.checkout.CustomerSummary_of]] — defined_in, incoming
- [[classes/com.example.order.checkout.Summary|com.example.order.checkout.Summary]] — defined_in, incoming
- [[classes/com.example.order.checkout.InvalidCheckoutException|com.example.order.checkout.InvalidCheckoutException]] — defined_in, incoming
- [[classes/com.example.order.checkout.InventoryClient|com.example.order.checkout.InventoryClient]] — defined_in, incoming
- [[functions/com.example.order.checkout.InventoryClient_reserve|com.example.order.checkout.InventoryClient_reserve]] — defined_in, incoming
- [[functions/com.example.order.checkout.InventoryClient_release|com.example.order.checkout.InventoryClient_release]] — defined_in, incoming

_21 further connection(s) not listed._
