---
type: SERVICE
title: order-service
description: service order-service. Connected to GET /api/checkout/{id}, GET /api/checkout/summary,
  GET /api/orders and 41 other(s).
resource: null
tags:
- service
timestamp: '2026-11-19T07:38:32.700863'
---

# order-service

service order-service. Connected to GET /api/checkout/{id}, GET /api/checkout/summary, GET /api/orders and 41 other(s).

## Connections

- [[endpoints/order-service_GET__api_checkout__id_|order-service_GET__api_checkout__id_]] — exposes, outgoing
- [[endpoints/order-service_GET__api_checkout_summary|order-service_GET__api_checkout_summary]] — exposes, outgoing
- [[endpoints/order-service_GET__api_orders|order-service_GET__api_orders]] — exposes, outgoing
- [[endpoints/order-service_GET__api_orders__id_|order-service_GET__api_orders__id_]] — exposes, outgoing
- [[endpoints/order-service_GET__api_checkout|order-service_GET__api_checkout]] — exposes, outgoing
- [[endpoints/order-service_DELETE__api_orders__id_|order-service_DELETE__api_orders__id_]] — exposes, outgoing
- [[endpoints/order-service_POST__api_checkout|order-service_POST__api_checkout]] — exposes, outgoing
- [[endpoints/order-service_POST__api_orders|order-service_POST__api_orders]] — exposes, outgoing
- [[modules/maven_com.github.docker-java_docker-java-transport-zerodep|maven_com.github.docker-java_docker-java-transport-zerodep]] — imports, outgoing
- [[modules/maven_org.springframework.boot_spring-boot-starter-actuator|maven_org.springframework.boot_spring-boot-starter-actuator]] — imports, outgoing
- [[modules/maven_com.github.docker-java_docker-java|maven_com.github.docker-java_docker-java]] — imports, outgoing
- [[modules/maven_com.h2database_h2|maven_com.h2database_h2]] — imports, outgoing
- [[modules/maven_org.springframework.boot_spring-boot-starter-web|maven_org.springframework.boot_spring-boot-starter-web]] — imports, outgoing
- [[modules/maven_org.springframework.boot_spring-boot-starter-data-jpa|maven_org.springframework.boot_spring-boot-starter-data-jpa]] — imports, outgoing
- [[modules/maven_javax.xml.bind_jaxb-api|maven_javax.xml.bind_jaxb-api]] — imports, outgoing
- [[classes/com.example.order.checkout.CheckoutWorkflow|com.example.order.checkout.CheckoutWorkflow]] — depends_on, outgoing
- [[classes/com.example.order.OrderApplication|com.example.order.OrderApplication]] — depends_on, outgoing
- [[classes/com.example.order.checkout.WorkflowTrace|com.example.order.checkout.WorkflowTrace]] — depends_on, outgoing
- [[classes/com.example.order.checkout.InventoryUnavailableException|com.example.order.checkout.InventoryUnavailableException]] — depends_on, outgoing
- [[classes/com.example.order.checkout.CustomerSummary|com.example.order.checkout.CustomerSummary]] — depends_on, outgoing
- [[classes/com.example.order.OrderRepository|com.example.order.OrderRepository]] — depends_on, outgoing
- [[classes/com.example.order.checkout.CheckoutRepository|com.example.order.checkout.CheckoutRepository]] — depends_on, outgoing
- [[classes/com.example.order.checkout.Quote|com.example.order.checkout.Quote]] — depends_on, outgoing
- [[classes/com.example.order.checkout.Status|com.example.order.checkout.Status]] — depends_on, outgoing
- [[classes/com.example.order.checkout.StockItem|com.example.order.checkout.StockItem]] — depends_on, outgoing
- [[classes/com.example.order.ProductOrder|com.example.order.ProductOrder]] — depends_on, outgoing
- [[classes/com.example.order.checkout.CheckoutAudit|com.example.order.checkout.CheckoutAudit]] — depends_on, outgoing
- [[classes/com.example.order.UnifiedMetricsEndpoint|com.example.order.UnifiedMetricsEndpoint]] — depends_on, outgoing
- [[classes/com.example.order.checkout.CheckoutController|com.example.order.checkout.CheckoutController]] — depends_on, outgoing
- [[classes/com.example.order.checkout.PricedLine|com.example.order.checkout.PricedLine]] — depends_on, outgoing
- [[classes/com.example.order.checkout.Checkout|com.example.order.checkout.Checkout]] — depends_on, outgoing
- [[classes/com.example.order.checkout.Summary|com.example.order.checkout.Summary]] — depends_on, outgoing
- [[classes/com.example.order.checkout.InvoiceCheck|com.example.order.checkout.InvoiceCheck]] — depends_on, outgoing
- [[nodes/database_order-service_h2_orderdb|database_order-service_h2_orderdb]] — depends_on, outgoing
- [[classes/com.example.order.checkout.Line|com.example.order.checkout.Line]] — depends_on, outgoing
- [[classes/com.example.order.checkout.PricingEngine|com.example.order.checkout.PricingEngine]] — depends_on, outgoing
- [[classes/com.example.order.checkout.InvalidCheckoutException|com.example.order.checkout.InvalidCheckoutException]] — depends_on, outgoing
- [[classes/com.example.order.checkout.InventoryClient|com.example.order.checkout.InventoryClient]] — depends_on, outgoing
- [[services/inventory-service|inventory-service]] — depends_on, outgoing
- [[classes/com.example.order.checkout.OutOfStockException|com.example.order.checkout.OutOfStockException]] — depends_on, outgoing
- [[classes/com.example.order.checkout.CheckoutRequest|com.example.order.checkout.CheckoutRequest]] — depends_on, outgoing
- [[containers/order-service|order-service]] — deployed_as, outgoing
- [[env_vars/order-service_SERVER_PORT|order-service_SERVER_PORT]] — configured_by, outgoing
- [[env_vars/order-service_INVENTORY_BASE_URL|order-service_INVENTORY_BASE_URL]] — configured_by, outgoing
