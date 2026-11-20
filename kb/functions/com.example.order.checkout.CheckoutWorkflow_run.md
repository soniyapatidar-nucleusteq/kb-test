---
type: FUNCTION
title: run
description: function run, defined in order-service/src/main/java/com/example/order/checkout/CheckoutWorkflow.java.
  Connected to checkout, cents, CheckoutRequest and 27 other(s).
resource: order-service/src/main/java/com/example/order/checkout/CheckoutWorkflow.java
tags:
- function
timestamp: '2026-11-20T11:54:14.719910'
---

# run

function run, defined in order-service/src/main/java/com/example/order/checkout/CheckoutWorkflow.java. Connected to checkout, cents, CheckoutRequest and 27 other(s).

## Connections

- [[functions/com.example.order.checkout.CheckoutController_checkout|com.example.order.checkout.CheckoutController_checkout]] — calls, incoming
- [[functions/com.example.order.checkout.PricingEngine_cents|com.example.order.checkout.PricingEngine_cents]] — calls, outgoing
- [[classes/com.example.order.checkout.CheckoutRequest|com.example.order.checkout.CheckoutRequest]] — calls, outgoing
- [[functions/com.example.order.checkout.Checkout_confirm|com.example.order.checkout.Checkout_confirm]] — calls, outgoing
- [[classes/com.example.order.checkout.CheckoutRepository|com.example.order.checkout.CheckoutRepository]] — calls, outgoing
- [[classes/com.example.order.checkout.StockItem|com.example.order.checkout.StockItem]] — calls, outgoing
- [[classes/com.example.order.checkout.OutOfStockException|com.example.order.checkout.OutOfStockException]] — calls, outgoing
- [[functions/com.example.order.checkout.WorkflowTrace_step|com.example.order.checkout.WorkflowTrace_step]] — calls, outgoing
- [[functions/com.example.order.checkout.InvoiceCheck_invoiceTotal|com.example.order.checkout.InvoiceCheck_invoiceTotal]] — calls, outgoing
- [[functions/com.example.order.checkout.Checkout_getId|com.example.order.checkout.Checkout_getId]] — calls, outgoing
- [[functions/com.example.order.checkout.Checkout_getCustomer|com.example.order.checkout.Checkout_getCustomer]] — calls, outgoing
- [[functions/com.example.order.checkout.PricingEngine_quote|com.example.order.checkout.PricingEngine_quote]] — calls, outgoing
- [[functions/com.example.order.checkout.Checkout_getTotal|com.example.order.checkout.Checkout_getTotal]] — calls, outgoing
- [[functions/com.example.order.checkout.CheckoutAudit_invoiceMismatch|com.example.order.checkout.CheckoutAudit_invoiceMismatch]] — calls, outgoing
- [[classes/com.example.order.checkout.Line|com.example.order.checkout.Line]] — calls, outgoing
- [[functions/com.example.order.checkout.CheckoutWorkflow_fail|com.example.order.checkout.CheckoutWorkflow_fail]] — calls, outgoing
- [[functions/com.example.order.checkout.PricedLine_amount|com.example.order.checkout.PricedLine_amount]] — calls, outgoing
- [[functions/com.example.order.checkout.InvoiceCheck_matches|com.example.order.checkout.InvoiceCheck_matches]] — calls, outgoing
- [[functions/com.example.order.checkout.CheckoutAudit_confirmed|com.example.order.checkout.CheckoutAudit_confirmed]] — calls, outgoing
- [[functions/com.example.order.checkout.InventoryClient_reserve|com.example.order.checkout.InventoryClient_reserve]] — calls, outgoing
- [[classes/com.example.order.OrderRepository|com.example.order.OrderRepository]] — calls, outgoing
- [[classes/com.example.order.checkout.Checkout|com.example.order.checkout.Checkout]] — calls, outgoing
- [[functions/com.example.order.checkout.CheckoutWorkflow_validate|com.example.order.checkout.CheckoutWorkflow_validate]] — calls, outgoing
- [[functions/com.example.order.checkout.PackingSlipPrinter_print|com.example.order.checkout.PackingSlipPrinter_print]] — calls, outgoing
- [[classes/com.example.order.checkout.InventoryUnavailableException|com.example.order.checkout.InventoryUnavailableException]] — calls, outgoing
- [[classes/com.example.order.ProductOrder|com.example.order.ProductOrder]] — calls, outgoing
- [[classes/com.example.order.checkout.Quote|com.example.order.checkout.Quote]] — calls, outgoing
- [[classes/com.example.order.checkout.PricedLine|com.example.order.checkout.PricedLine]] — calls, outgoing
- [[classes/com.example.order.checkout.CheckoutWorkflow|com.example.order.checkout.CheckoutWorkflow]] — member_of, outgoing
- [[modules/com.example.order.checkout|com.example.order.checkout]] — defined_in, outgoing
