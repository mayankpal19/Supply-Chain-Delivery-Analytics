# Supply Chain KPI Definitions

## 1. Overview

This document defines the key performance indicators used to evaluate order fulfilment and delivery efficiency at AtliQ Mart.

The KPIs help measure delivery reliability, order completeness and overall customer fulfilment performance.

## 2. Key Performance Indicators

### 1. On-Time Delivery (OT%)

Measures the percentage of orders delivered on or before the agreed delivery date.

**Formula:**

OT% = (Orders Delivered On Time / Total Orders) × 100

**Business Purpose:** Evaluates delivery punctuality and identifies delays in order fulfilment.

### 2. In-Full Delivery (IF%)

Measures the percentage of orders delivered with the complete requested quantity.

**Formula:**

IF% = (Orders Delivered In Full / Total Orders) × 100

**Business Purpose:** Evaluates whether customers receive the quantities they ordered.

### 3. On-Time In-Full (OTIF%)

Measures the percentage of orders that satisfy both on-time and in-full delivery conditions.

**Formula:**

OTIF% = (Orders Delivered On Time and In Full / Total Orders) × 100

**Business Purpose:** Provides an overall measure of successful order fulfilment.

### 4. Line Fill Rate (LIFR%)

Measures the percentage of order lines fulfilled completely.

**Formula:**

LIFR% = (Order Lines Delivered In Full / Total Order Lines) × 100

**Business Purpose:** Identifies issues with product-level order fulfilment.

### 5. Volume Fill Rate (VOFR%)

Measures the percentage of ordered quantity successfully delivered.

**Formula:**

VOFR% = (Total Quantity Delivered / Total Quantity Ordered) × 100

**Business Purpose:** Evaluates how effectively the business fulfils the total quantity requested by customers.

## 3. Performance Target Analysis

The project also evaluates actual KPI performance against customer-specific targets.

**Target Variance:**

Target Variance = Actual KPI - Target KPI

A negative variance indicates performance below the target, while a positive variance indicates performance above the target.

## 4. Analytical Applications

These KPIs will be used to:

- Monitor overall delivery performance.
- Identify customers with recurring fulfilment issues.
- Compare actual performance against targets.
- Analyze monthly performance trends.
- Identify opportunities to improve operational efficiency.

## 5. Calculation Notes

- Order-level KPIs must use distinct order counts where appropriate.
- Line-level KPIs must use order-line records.
- Volume-based KPIs must use quantity totals rather than simple averages of percentages.
- KPI definitions and calculation logic will be validated against the supplied business requirements before implementation in DAX.

