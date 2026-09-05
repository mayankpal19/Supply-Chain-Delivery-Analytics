# Supply Chain & Logistics Analytics Dashboard

## 📌 Executive Overview
An end-to-end supply chain intelligence dashboard engineered using **Power BI**, **Power Query**, and **Advanced DAX**. This platform evaluates order fulfillment efficiency, carrier SLA compliance, warehouse inventory turnover, and stockout risks across multi-regional distribution networks.

## 🔑 Key Metrics & Business KPIs
- **OTIF (On-Time In-Full) Rate:** Analyzed order delivery performance against strict customer SLAs.
- **Carrier Lead Time Variance:** Evaluated 3PL logistics provider performance to identify fulfillment bottlenecks.
- **Stockout & Safety Stock Buffer:** Formulated dynamic DAX measures calculating required safety stock to prevent inventory depletion.
- **Inventory Turnover Ratio:** Tracked high-velocity SKU demand against static warehouse holding costs.

## 🛠️ Data Architecture & Modeling
- **Data Modeling:** Modeled a clean **Star Schema** linking Fact Sales tables to Dimension tables (Customers, Products, Warehouses, Carriers).
- **Power Query ETL:** Applied automated transformations, null value handling, custom date tables, and conditional column logic.
- **DAX Calculations:** Built measure tables featuring time-intelligence functions (`SAMEPERIODLASTYEAR`, rolling averages) and KPI status indicators.

## 🚀 How to View
1. Download the `.pbix` dashboard file from the root folder.
2. Open in **Power BI Desktop** to interact with dynamic filters and cross-highlighting visuals.
