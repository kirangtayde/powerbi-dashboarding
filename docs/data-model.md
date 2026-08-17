# Semantic Data Model

## Recommended star schema

```text
DimDate ─┐
DimCustomer ─┤
DimProduct ──┼── FactSales
DimRegion ───┤
DimChannel ──┘
```

### FactSales grain
One row per business transaction/order line, depending on the approved source grain.

### Core dimensions
- Date: day, week, month, quarter, year
- Customer: segment, geography, lifecycle
- Product: category, brand, product hierarchy
- Region: market and territory
- Channel: source/campaign/channel

### Governance
Use explicit relationships, a dedicated date table, controlled measure definitions and documented refresh dependencies.
