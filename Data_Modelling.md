# Supply Chain Analysis – Data Model Documentation

## 1. Model Overview

The Power BI project uses a multi-fact data model consisting of five fact tables and five dimension tables.

The model follows a Fact Constellation (Galaxy Schema) approach, where multiple fact tables share common dimension tables.

## 2. Dimension Tables

| Table | Description |
|---|---|
| dim_product | Contains product attributes such as category, colour, product line, product name, specifications and unit cost. |
| dim_supplier | Contains supplier information, including name, location, specialty, tier and quality score. |
| dim_customer | Contains customer attributes such as name, country, channel type and annual volume. |
| dim_facility | Contains facility information, including name, location, type and annual capacity. |
| dim_date | Contains calendar attributes such as date, day, month, quarter, weekday and weekend indicator. |

## 3. Fact Tables

| Table | Description |
|---|---|
| fact_sales | Stores sales-related information, including revenue, profit, discounts, orders and customer/product identifiers. |
| fact_inventory | Stores inventory information such as stock levels, reorder points and safety stock levels. |
| fact_shipment | Stores shipment information including carrier, quantity, delivery date, shipment date and delay reason. |
| fact_procurement | Stores procurement information such as purchase orders, order quantities, supplier details, lead time and quality score. |
| fact_production | Stores production information such as batch numbers, quantities produced, defective units and defect rates. |

## 4. Data Modelling Approach

The model uses multiple fact tables to represent separate supply chain business processes.

Shared dimensions provide common analytical attributes across these processes.

Examples:
- Product dimension for product-level analysis.
- Date dimension for time-based analysis.
- Facility dimension for facility-level analysis.

The model supports analysis of sales, inventory, production, procurement and shipment operations.

## 5. Relationship Concepts

Power BI relationship indicators:

- 1: One side of a relationship.
- *: Many side of a relationship.
- Arrow: Filter propagation direction.

One-to-many relationships allow dimension records to filter corresponding fact records.

Exact relationship keys, cardinality and active/inactive status should be documented using Power BI's relationship properties.

## 6. Date Modelling

The model contains a dedicated dim_date table.

The fact tables include date-related keys, including:
- date_key
- order_date_key
- ship_date_key
- delivery_date_key

These represent different operational dates.

Further investigation is required to document the active and inactive relationships and the date roles used in calculations.

## 7. Disconnected Measure Table

A separate measure table is maintained outside the relationship model.

This table is used to organize DAX measures and does not require relationships with the fact or dimension tables.

## 8. Important Modelling Concepts Learned

- Fact and dimension tables.
- Fact constellation schema.
- One-to-many relationships.
- Relationship cardinality.
- Filter propagation.
- Shared dimensions.
- Date dimension and role-playing dates.
- Disconnected measure tables.
- Fact table granularity.

