---
type: SERVICE
title: inventory-service
description: service inventory-service. Connected to POST /api/stock/{id}/reserve,
  GET /api/items, POST /api/stock/{id}/release and 34 other(s).
resource: null
tags:
- service
timestamp: '2026-11-20T11:54:14.719910'
---

# inventory-service

service inventory-service. Connected to POST /api/stock/{id}/reserve, GET /api/items, POST /api/stock/{id}/release and 34 other(s).

## Connections

- [[endpoints/inventory-service_POST__api_stock__id__reserve|inventory-service_POST__api_stock__id__reserve]] — exposes, outgoing
- [[endpoints/inventory-service_GET__api_items|inventory-service_GET__api_items]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_stock__id__release|inventory-service_POST__api_stock__id__release]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_items|inventory-service_POST__api_items]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_reconciliation_cancel|inventory-service_POST__api_reconciliation_cancel]] — exposes, outgoing
- [[endpoints/inventory-service_PUT__api_items__id_|inventory-service_PUT__api_items__id_]] — exposes, outgoing
- [[endpoints/inventory-service_DELETE__api_items__id_|inventory-service_DELETE__api_items__id_]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_supplier-feed|inventory-service_POST__api_supplier-feed]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_reconciliation_start|inventory-service_POST__api_reconciliation_start]] — exposes, outgoing
- [[endpoints/inventory-service_GET__api_reconciliation|inventory-service_GET__api_reconciliation]] — exposes, outgoing
- [[endpoints/inventory-service_GET__api_items__id_|inventory-service_GET__api_items__id_]] — exposes, outgoing
- [[modules/maven_org.springframework.boot_spring-boot-starter-web|maven_org.springframework.boot_spring-boot-starter-web]] — imports, outgoing
- [[modules/maven_org.postgresql_postgresql|maven_org.postgresql_postgresql]] — imports, outgoing
- [[modules/maven_org.springframework.boot_spring-boot-starter-data-jpa|maven_org.springframework.boot_spring-boot-starter-data-jpa]] — imports, outgoing
- [[containers/inventory-service|inventory-service]] — deployed_as, outgoing
- [[env_vars/inventory-service_SERVER_PORT|inventory-service_SERVER_PORT]] — configured_by, outgoing
- [[classes/com.example.inventory.SupplierFeedController|com.example.inventory.SupplierFeedController]] — depends_on, outgoing
- [[classes/com.example.inventory.Run|com.example.inventory.Run]] — depends_on, outgoing
- [[classes/com.example.inventory.FeedResult|com.example.inventory.FeedResult]] — depends_on, outgoing
- [[classes/com.example.inventory.NotRunningException|com.example.inventory.NotRunningException]] — depends_on, outgoing
- [[classes/com.example.inventory.InsufficientStockException|com.example.inventory.InsufficientStockException]] — depends_on, outgoing
- [[nodes/database_postgresql___postgres_5432_shop|database_postgresql___postgres_5432_shop]] — depends_on, outgoing
- [[classes/com.example.inventory.StockMovementRepository|com.example.inventory.StockMovementRepository]] — depends_on, outgoing
- [[classes/com.example.inventory.AlreadyRunningException|com.example.inventory.AlreadyRunningException]] — depends_on, outgoing
- [[classes/com.example.inventory.ItemRepository|com.example.inventory.ItemRepository]] — depends_on, outgoing
- [[classes/com.example.inventory.StockMovement|com.example.inventory.StockMovement]] — depends_on, outgoing
- [[classes/com.example.inventory.StockController|com.example.inventory.StockController]] — depends_on, outgoing
- [[classes/com.example.inventory.InventoryApplication|com.example.inventory.InventoryApplication]] — depends_on, outgoing
- [[services/postgres|postgres]] — depends_on, outgoing
- [[classes/com.example.inventory.SupplierFeedImporter|com.example.inventory.SupplierFeedImporter]] — depends_on, outgoing
- [[classes/com.example.inventory.StockService|com.example.inventory.StockService]] — depends_on, outgoing
- [[classes/com.example.inventory.StockReconciliation|com.example.inventory.StockReconciliation]] — depends_on, outgoing
- [[classes/com.example.inventory.Status|com.example.inventory.Status]] — depends_on, outgoing
- [[classes/com.example.inventory.Item|com.example.inventory.Item]] — depends_on, outgoing
- [[classes/com.example.inventory.ReconciliationController|com.example.inventory.ReconciliationController]] — depends_on, outgoing
- [[classes/com.example.inventory.InventoryNotFoundException|com.example.inventory.InventoryNotFoundException]] — depends_on, outgoing
- [[services/order-service|order-service]] — depends_on, incoming
