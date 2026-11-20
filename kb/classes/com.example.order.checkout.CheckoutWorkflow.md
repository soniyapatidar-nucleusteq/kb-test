---
type: CLASS
title: CheckoutWorkflow
description: class CheckoutWorkflow, defined in order-service/src/main/java/com/example/order/checkout/CheckoutWorkflow.java.
  Connected to fail, order-service, CheckoutController and 13 other(s).
resource: order-service/src/main/java/com/example/order/checkout/CheckoutWorkflow.java
tags:
- class
timestamp: '2026-11-20T11:54:14.719910'
---

# CheckoutWorkflow

class CheckoutWorkflow, defined in order-service/src/main/java/com/example/order/checkout/CheckoutWorkflow.java. Connected to fail, order-service, CheckoutController and 13 other(s).

## Connections

- [[functions/com.example.order.checkout.CheckoutWorkflow_fail|com.example.order.checkout.CheckoutWorkflow_fail]] — member_of, incoming
- [[services/order-service|order-service]] — depends_on, incoming
- [[classes/com.example.order.checkout.CheckoutController|com.example.order.checkout.CheckoutController]] — uses, incoming
- [[classes/com.example.order.checkout.WorkflowTrace|com.example.order.checkout.WorkflowTrace]] — uses, outgoing
- [[classes/com.example.order.checkout.PackingSlipPrinter|com.example.order.checkout.PackingSlipPrinter]] — uses, outgoing
- [[classes/com.example.order.checkout.CheckoutRepository|com.example.order.checkout.CheckoutRepository]] — uses, outgoing
- [[classes/com.example.order.checkout.PricingEngine|com.example.order.checkout.PricingEngine]] — uses, outgoing
- [[classes/com.example.order.OrderRepository|com.example.order.OrderRepository]] — uses, outgoing
- [[classes/com.example.order.checkout.InvoiceCheck|com.example.order.checkout.InvoiceCheck]] — uses, outgoing
- [[classes/com.example.order.checkout.InventoryClient|com.example.order.checkout.InventoryClient]] — uses, outgoing
- [[classes/com.example.order.checkout.CheckoutAudit|com.example.order.checkout.CheckoutAudit]] — uses, outgoing
- [[modules/com.example.order.checkout|com.example.order.checkout]] — defined_in, outgoing
- [[functions/com.example.order.checkout.CheckoutWorkflow_run|com.example.order.checkout.CheckoutWorkflow_run]] — member_of, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_reprintSlip|com.example.order.checkout.CheckoutWorkflow_reprintSlip]] — member_of, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_recent|com.example.order.checkout.CheckoutWorkflow_recent]] — member_of, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_validate|com.example.order.checkout.CheckoutWorkflow_validate]] — member_of, incoming
