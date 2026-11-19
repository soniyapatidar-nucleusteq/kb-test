---
type: CLASS
title: PricedLine
description: class PricedLine, defined in order-service/src/main/java/com/example/order/checkout/PricingEngine.java.
  Connected to order-service, run, fail and 4 other(s).
resource: order-service/src/main/java/com/example/order/checkout/PricingEngine.java
tags:
- class
timestamp: '2026-11-19T07:38:32.700863'
---

# PricedLine

class PricedLine, defined in order-service/src/main/java/com/example/order/checkout/PricingEngine.java. Connected to order-service, run, fail and 4 other(s).

## Connections

- [[services/order-service|order-service]] — depends_on, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_run|com.example.order.checkout.CheckoutWorkflow_run]] — calls, incoming
- [[functions/com.example.order.checkout.CheckoutWorkflow_fail|com.example.order.checkout.CheckoutWorkflow_fail]] — calls, incoming
- [[functions/com.example.order.checkout.InvoiceCheck_invoiceTotal|com.example.order.checkout.InvoiceCheck_invoiceTotal]] — calls, incoming
- [[functions/com.example.order.checkout.PricingEngine_quote|com.example.order.checkout.PricingEngine_quote]] — calls, incoming
- [[modules/com.example.order.checkout|com.example.order.checkout]] — defined_in, outgoing
- [[functions/com.example.order.checkout.PricedLine_amount|com.example.order.checkout.PricedLine_amount]] — member_of, incoming
