---
type: MODULE
title: com.example.inventory
description: module com.example.inventory. Connected to InsufficientStockException,
  getItemId, getRequested and 68 other(s).
resource: null
tags:
- module
timestamp: '2026-11-20T11:54:14.719910'
---

# com.example.inventory

module com.example.inventory. Connected to InsufficientStockException, getItemId, getRequested and 68 other(s).

## Connections

- [[classes/com.example.inventory.InsufficientStockException|com.example.inventory.InsufficientStockException]] — defined_in, incoming
- [[functions/com.example.inventory.InsufficientStockException_getItemId|com.example.inventory.InsufficientStockException_getItemId]] — defined_in, incoming
- [[functions/com.example.inventory.InsufficientStockException_getRequested|com.example.inventory.InsufficientStockException_getRequested]] — defined_in, incoming
- [[functions/com.example.inventory.InsufficientStockException_getAvailable|com.example.inventory.InsufficientStockException_getAvailable]] — defined_in, incoming
- [[classes/com.example.inventory.InventoryApplication|com.example.inventory.InventoryApplication]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_main|com.example.inventory.InventoryApplication_main]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_initDatabase|com.example.inventory.InventoryApplication_initDatabase]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_getAll|com.example.inventory.InventoryApplication_getAll]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_getOne|com.example.inventory.InventoryApplication_getOne]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_create|com.example.inventory.InventoryApplication_create]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_update|com.example.inventory.InventoryApplication_update]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_delete|com.example.inventory.InventoryApplication_delete]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_handleInventoryNotFound|com.example.inventory.InventoryApplication_handleInventoryNotFound]] — defined_in, incoming
- [[functions/com.example.inventory.InventoryApplication_errorResponse|com.example.inventory.InventoryApplication_errorResponse]] — defined_in, incoming
- [[classes/com.example.inventory.InventoryNotFoundException|com.example.inventory.InventoryNotFoundException]] — defined_in, incoming
- [[classes/com.example.inventory.Item|com.example.inventory.Item]] — defined_in, incoming
- [[functions/com.example.inventory.Item_getId|com.example.inventory.Item_getId]] — defined_in, incoming
- [[functions/com.example.inventory.Item_setId|com.example.inventory.Item_setId]] — defined_in, incoming
- [[functions/com.example.inventory.Item_getName|com.example.inventory.Item_getName]] — defined_in, incoming
- [[functions/com.example.inventory.Item_setName|com.example.inventory.Item_setName]] — defined_in, incoming
- [[functions/com.example.inventory.Item_getQuantity|com.example.inventory.Item_getQuantity]] — defined_in, incoming
- [[functions/com.example.inventory.Item_setQuantity|com.example.inventory.Item_setQuantity]] — defined_in, incoming
- [[functions/com.example.inventory.Item_getUnitPrice|com.example.inventory.Item_getUnitPrice]] — defined_in, incoming
- [[functions/com.example.inventory.Item_setUnitPrice|com.example.inventory.Item_setUnitPrice]] — defined_in, incoming
- [[functions/com.example.inventory.Item_getBin|com.example.inventory.Item_getBin]] — defined_in, incoming
- [[functions/com.example.inventory.Item_setBin|com.example.inventory.Item_setBin]] — defined_in, incoming
- [[classes/com.example.inventory.ItemRepository|com.example.inventory.ItemRepository]] — defined_in, incoming
- [[functions/com.example.inventory.ItemRepository_findFirstByNameIgnoreCase|com.example.inventory.ItemRepository_findFirstByNameIgnoreCase]] — defined_in, incoming
- [[classes/com.example.inventory.ReconciliationController|com.example.inventory.ReconciliationController]] — defined_in, incoming
- [[functions/com.example.inventory.ReconciliationController_status|com.example.inventory.ReconciliationController_status]] — defined_in, incoming
- [[functions/com.example.inventory.ReconciliationController_start|com.example.inventory.ReconciliationController_start]] — defined_in, incoming
- [[functions/com.example.inventory.ReconciliationController_cancel|com.example.inventory.ReconciliationController_cancel]] — defined_in, incoming
- [[functions/com.example.inventory.ReconciliationController_conflict|com.example.inventory.ReconciliationController_conflict]] — defined_in, incoming
- [[classes/com.example.inventory.StockController|com.example.inventory.StockController]] — defined_in, incoming
- [[functions/com.example.inventory.StockController_reserve|com.example.inventory.StockController_reserve]] — defined_in, incoming
- [[functions/com.example.inventory.StockController_release|com.example.inventory.StockController_release]] — defined_in, incoming
- [[functions/com.example.inventory.StockController_handleInsufficientStock|com.example.inventory.StockController_handleInsufficientStock]] — defined_in, incoming
- [[functions/com.example.inventory.StockController_handleNotFound|com.example.inventory.StockController_handleNotFound]] — defined_in, incoming
- [[functions/com.example.inventory.StockController_handleBadRequest|com.example.inventory.StockController_handleBadRequest]] — defined_in, incoming
- [[classes/com.example.inventory.StockMovement|com.example.inventory.StockMovement]] — defined_in, incoming
- [[functions/com.example.inventory.StockMovement_getId|com.example.inventory.StockMovement_getId]] — defined_in, incoming
- [[functions/com.example.inventory.StockMovement_getItemId|com.example.inventory.StockMovement_getItemId]] — defined_in, incoming
- [[functions/com.example.inventory.StockMovement_getDelta|com.example.inventory.StockMovement_getDelta]] — defined_in, incoming
- [[functions/com.example.inventory.StockMovement_getReason|com.example.inventory.StockMovement_getReason]] — defined_in, incoming
- [[functions/com.example.inventory.StockMovement_getAt|com.example.inventory.StockMovement_getAt]] — defined_in, incoming
- [[classes/com.example.inventory.StockMovementRepository|com.example.inventory.StockMovementRepository]] — defined_in, incoming
- [[functions/com.example.inventory.StockMovementRepository_ledgerStock|com.example.inventory.StockMovementRepository_ledgerStock]] — defined_in, incoming
- [[classes/com.example.inventory.StockReconciliation|com.example.inventory.StockReconciliation]] — defined_in, incoming
- [[functions/com.example.inventory.StockReconciliation_start|com.example.inventory.StockReconciliation_start]] — defined_in, incoming
- [[functions/com.example.inventory.StockReconciliation_cancel|com.example.inventory.StockReconciliation_cancel]] — defined_in, incoming

_21 further connection(s) not listed._
