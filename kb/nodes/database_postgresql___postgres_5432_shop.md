---
type: DATABASE
title: shop
description: database shop. Connected to inventory-service, order-service.
resource: null
tags:
- database
timestamp: '2026-11-20T11:54:14.719910'
---

# shop

database shop. Connected to inventory-service, order-service.

## Connections

- [[services/inventory-service|inventory-service]] — depends_on, incoming
- [[services/order-service|order-service]] — depends_on, incoming
