---
type: SERVICE
title: inventory-service
description: service inventory-service. Connected to POST /api/stock/{id}/release,
  GET /api/items/{id}, GET /api/items and 23 other(s).
resource: null
tags:
- service
timestamp: '2026-11-19T10:12:52.093964'
---

# inventory-service

service inventory-service. Connected to POST /api/stock/{id}/release, GET /api/items/{id}, GET /api/items and 23 other(s).

## Known problems

- [[incidents/host-name-not-found|host-name-not-found]] — Host name not found (error, open, 3 occurrences) — caused here

## Connections

- [[endpoints/inventory-service_POST__api_stock__id__release|inventory-service_POST__api_stock__id__release]] — exposes, outgoing
- [[endpoints/inventory-service_GET__api_items__id_|inventory-service_GET__api_items__id_]] — exposes, outgoing
- [[endpoints/inventory-service_GET__api_items|inventory-service_GET__api_items]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_stock__id__reserve|inventory-service_POST__api_stock__id__reserve]] — exposes, outgoing
- [[endpoints/inventory-service_DELETE__api_items__id_|inventory-service_DELETE__api_items__id_]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_supplier-feed|inventory-service_POST__api_supplier-feed]] — exposes, outgoing
- [[endpoints/inventory-service_PUT__api_items__id_|inventory-service_PUT__api_items__id_]] — exposes, outgoing
- [[endpoints/inventory-service_POST__api_items|inventory-service_POST__api_items]] — exposes, outgoing
- [[modules/maven_org.springframework.boot_spring-boot-starter-data-jpa|maven_org.springframework.boot_spring-boot-starter-data-jpa]] — imports, outgoing
- [[modules/maven_org.springframework.boot_spring-boot-starter-web|maven_org.springframework.boot_spring-boot-starter-web]] — imports, outgoing
- [[modules/maven_com.h2database_h2|maven_com.h2database_h2]] — imports, outgoing
- [[nodes/database_inventory-service_h2_inventorydb|database_inventory-service_h2_inventorydb]] — depends_on, outgoing
- [[classes/com.example.inventory.ItemRepository|com.example.inventory.ItemRepository]] — depends_on, outgoing
- [[classes/com.example.inventory.FeedResult|com.example.inventory.FeedResult]] — depends_on, outgoing
- [[classes/com.example.inventory.InventoryApplication|com.example.inventory.InventoryApplication]] — depends_on, outgoing
- [[classes/com.example.inventory.Item|com.example.inventory.Item]] — depends_on, outgoing
- [[classes/com.example.inventory.InventoryNotFoundException|com.example.inventory.InventoryNotFoundException]] — depends_on, outgoing
- [[classes/com.example.inventory.StockService|com.example.inventory.StockService]] — depends_on, outgoing
- [[classes/com.example.inventory.InsufficientStockException|com.example.inventory.InsufficientStockException]] — depends_on, outgoing
- [[classes/com.example.inventory.SupplierFeedImporter|com.example.inventory.SupplierFeedImporter]] — depends_on, outgoing
- [[classes/com.example.inventory.SupplierFeedController|com.example.inventory.SupplierFeedController]] — depends_on, outgoing
- [[classes/com.example.inventory.StockController|com.example.inventory.StockController]] — depends_on, outgoing
- [[containers/inventory-service|inventory-service]] — deployed_as, outgoing
- [[env_vars/inventory-service_SERVER_PORT|inventory-service_SERVER_PORT]] — configured_by, outgoing
- [[services/order-service|order-service]] — depends_on, incoming
- [[incidents/host-name-not-found|host-name-not-found]] — CAUSED_BY, incoming
