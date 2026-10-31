# Data Model & Database Structure

## 1. Overview

The project uses six structured CSV datasets to analyze order fulfilment and supply chain delivery performance.

The data model consists of customer, product, date and target information alongside transactional order records.

The objective is to organize these datasets into a relational model suitable for analytical reporting in Power BI.

## 2. Dataset Structure

| Table | Type | Records | Description |
|---|---|---:|---|
| dim_customers | Dimension | 35 | Customer details and city |
| dim_products | Dimension | 18 | Product details and category |
| dim_date | Dimension | 183 | Calendar and week information |
| dim_targets_orders | Target | 35 | Customer-specific delivery targets |
| fact_order_lines | Fact | 57,096 | Individual order-line transactions |
| fact_orders_aggregate | Fact | 31,729 | Aggregated order-level performance |

## 3. Important Columns

### dim_customers
- customer_id
- customer_name
- city

### dim_products
- product_id
- product_name
- category

### dim_date
- date
- mmm_yy
- week_no

### dim_targets_orders
- customer_id
- ontime_target%
- infull_target%
- otif_target%

### fact_order_lines
- order_id
- order_placement_date
- customer_id
- product_id
- order_qty
- agreed_delivery_date
- actual_delivery_date
- delivery_qty
- In Full
- On Time
- On Time In Full

### fact_orders_aggregate
- order_id
- customer_id
- order_placement_date
- on_time
- in_full
- otif

## 4. Proposed Table Relationships

| Primary Table | Related Table | Join Column |
|---|---|---|
| dim_customers | fact_order_lines | customer_id |
| dim_customers | fact_orders_aggregate | customer_id |
| dim_products | fact_order_lines | product_id |
| dim_date | fact_order_lines | order_placement_date |
| dim_date | fact_orders_aggregate | order_placement_date |
| dim_customers | dim_targets_orders | customer_id |

These relationships should be validated in Power BI before finalizing the model.

## 5. Data Modelling Considerations

- Dimension tables provide descriptive attributes for filtering and grouping.
- Fact tables contain measurable order and fulfilment information.
- Customer and product IDs act as lookup keys.
- The date table supports time-based analysis.
- Delivery dates and order placement dates require careful date relationship management.
- The two fact tables represent different levels of detail and should not be joined directly without a clearly defined analytical requirement.

## 6. Model Design Objective

The proposed model aims to support:

- Customer-level performance analysis.
- Product-level fulfilment analysis.
- Monthly and weekly delivery trends.
- Actual versus target KPI comparisons.
- Order fulfilment performance monitoring.

## 7. Validation

The relationships and cardinalities will be checked in Power BI during implementation. The final model documentation will be updated to reflect the actual implemented relationships.

