# DAX Measures – Supply Chain Analytics

## 1. Overview

This document contains the DAX measures used to evaluate order fulfilment and delivery performance.

The calculations use the supplied order-level and order-line datasets.

## 2. Order-Level Measures

### Total Orders

```dax
Total Orders =
DISTINCTCOUNT(fact_orders_aggregate[order_id])
```

Counts the unique customer orders.

### On-Time Orders

```dax
On-Time Orders =
CALCULATE(
    [Total Orders],
    fact_orders_aggregate[on_time] = 1
)
```

Counts orders delivered on time.

### In-Full Orders

```dax
In-Full Orders =
CALCULATE(
    [Total Orders],
    fact_orders_aggregate[in_full] = 1
)
```

Counts orders fulfilled with complete quantities.

### OTIF Orders

```dax
OTIF Orders =
CALCULATE(
    [Total Orders],
    fact_orders_aggregate[otif] = 1
)
```

Counts orders satisfying both on-time and in-full conditions.

## 3. Delivery Performance KPIs

### On-Time Delivery %

```dax
OT % =
DIVIDE(
    [On-Time Orders],
    [Total Orders],
    0
)
```

### In-Full Delivery %

```dax
IF % =
DIVIDE(
    [In-Full Orders],
    [Total Orders],
    0
)
```

### OTIF %

```dax
OTIF % =
DIVIDE(
    [OTIF Orders],
    [Total Orders],
    0
)
```

## 4. Order-Line Measures

### Total Order Lines

```dax
Total Order Lines =
COUNTROWS(fact_order_lines)
```

### In-Full Order Lines

```dax
In-Full Order Lines =
CALCULATE(
    [Total Order Lines],
    fact_order_lines[In Full] = 1
)
```

### Line Fill Rate (LIFR)

```dax
LIFR % =
DIVIDE(
    [In-Full Order Lines],
    [Total Order Lines],
    0
)
```

### Total Ordered Quantity

```dax
Total Ordered Quantity =
SUM(fact_order_lines[order_qty])
```

### Total Delivered Quantity

```dax
Total Delivered Quantity =
SUM(fact_order_lines[delivery_qty])
```

### Volume Fill Rate (VOFR)

```dax
VOFR % =
DIVIDE(
    [Total Delivered Quantity],
    [Total Ordered Quantity],
    0
)
```

## 5. Customer Target Measures

### On-Time Target %

```dax
OT Target % =
DIVIDE(
    AVERAGE(dim_targets_orders[ontime_target%]),
    100,
    0
)
```

### In-Full Target %

```dax
IF Target % =
DIVIDE(
    AVERAGE(dim_targets_orders[infull_target%]),
    100,
    0
)
```

### OTIF Target %

```dax
OTIF Target % =
DIVIDE(
    AVERAGE(dim_targets_orders[otif_target%]),
    100,
    0
)
```

## 6. Target Variance

### OTIF Target Variance

```dax
OTIF Target Variance =
[OTIF %] - [OTIF Target %]
```

A negative value indicates performance below the target.

A positive value indicates performance above the target.

## 7. Formatting Guidelines

| Measure | Format |
|---|---|
| Total Orders | Whole Number |
| On-Time Orders | Whole Number |
| In-Full Orders | Whole Number |
| OTIF Orders | Whole Number |
| OT % | Percentage |
| IF % | Percentage |
| OTIF % | Percentage |
| LIFR % | Percentage |
| VOFR % | Percentage |
| Target measures | Percentage |
| OTIF Target Variance | Percentage |

## 8. Implementation Notes

- Order-level KPIs use the aggregated orders table.
- Line-level KPIs use the individual order-lines table.
- Volume Fill Rate is calculated using total delivered quantity divided by total ordered quantity.
- DIVIDE is used to handle potential division-by-zero cases.
- Flag columns are assumed to contain numeric 0/1 values.
- Customer target values are stored as whole-number percentages and converted to decimal percentages.
- All measures must be tested with the final Power BI relationships and data types.

