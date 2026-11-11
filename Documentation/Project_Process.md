# Power BI Advanced Data Modeling Project

## 1. Project Overview

This project focuses on transforming a complex and poorly structured source dataset into an organised Power BI data model that is suitable for business reporting and analysis.

The project follows an end-to-end data modeling approach using Power BI Desktop and Power Query.

The main objective is to organise the source data into fact and dimension tables, create appropriate relationships, prepare analytical measures, and build a model that supports different business areas.

The project covers:

- Sales analysis
- Inventory analysis
- Marketing campaign performance
- Promotion coverage
- Order processing
- Sales target analysis

## 2. Tools and Technologies

- Power BI Desktop
- Power Query
- DAX
- Excel
- Data Modeling
- Dimensional Modeling

## 3. Project Workflow

The project was completed through the following major phases:

1. Data preparation and understanding
2. Query organisation and exploration
3. Dimension table development
4. Fact table development
5. Relationship creation
6. Data validation and model testing
7. Final data model organisation

---

# Phase 1: Data Preparation and Understanding

### Objective

Understand the source data before making any transformations.

### Process

The project started with an Excel workbook containing multiple sheets with different types of business information.

The source tables represented different business entities and activities, including:

- Customers
- Products
- Geography
- Campaigns
- Orders
- Sales
- Inventory
- Promotions
- Payments
- Shipments
- Sales targets

Each table was explored to understand its columns, purpose, and relationship with other tables.

### Identifying Facts and Dimensions

The source tables were examined to identify:

**Dimension candidates**

- Customer information
- Product information
- Campaign information
- Geographic information
- Order-related descriptive information
- Date information

**Fact candidates**

- Sales transactions
- Inventory records
- Campaign spending
- Promotion coverage
- Order processing
- Sales targets

This initial understanding helped determine how the final data model should be organised.

---

# Phase 2: Power Query Preparation

### Objective

Organise the imported queries and prepare the source data for transformation.

### Process

Power Query Editor was used as the main data preparation environment.

The queries were organised into groups to distinguish between original source queries and newly developed model tables.

This made the transformation process easier to manage as new dimension and fact tables were created.

The source queries were retained as the starting point for building the final model.

---

# Phase 3: Dimension Table Development

### Objective

Create clean dimension tables containing descriptive information about business entities.

Dimension tables provide the context required to filter and analyse fact data.

The following dimension tables were developed.

## 3.1 dim_customer

This table contains customer-related information.

The transformation process included:

- Merging customer contact information.
- Expanding the required contact columns.
- Merging additional user details.
- Expanding relevant customer details.
- Merging address information.
- Combining city-related information.
- Filtering and removing unnecessary columns.
- Renaming columns for better readability.

The resulting table brings customer-related information together in one dimension.

## 3.2 dim_product

This table contains product-related descriptive information.

The transformation process included:

- Removing unnecessary rows and columns.
- Merging product subcategory information.
- Expanding the required subcategory details.
- Creating an index column as a surrogate key.
- Reordering and renaming columns.

The resulting dimension provides product information for product-level analysis.

## 3.3 dim_campaign

This table contains campaign-related information.

The transformation process included:

- Removing duplicate records.
- Retaining the required campaign columns.
- Creating an index column as a surrogate key.
- Renaming and organising the columns.

The resulting table provides campaign details for marketing-related analysis.

## 3.4 dim_geo

This table contains geographic information.

The transformation process included:

- Removing duplicate records.
- Creating an index column.
- Renaming the generated key.
- Reordering and organising the columns.

The resulting dimension supports geographic analysis using city and region information.

## 3.5 dim_order_flags

This table combines descriptive order-related attributes.

It contains information such as:

- Channel
- Priority
- Flag key

The transformation process included:

- Keeping the required order-related columns.
- Removing duplicate combinations.
- Creating an index column as a surrogate key.
- Merging channel mapping information.
- Expanding the channel description.
- Renaming and organising the columns.

This dimension helps organise order attributes without creating a separate dimension for every individual flag.

## 3.6 dim_date

This dimension provides date-related information for time-based analysis.

The final model contains:

- Date
- Month
- Year

It supports date-based analysis across the fact tables.

---

# Phase 4: Fact Table Development

### Objective

Build fact tables containing business events, transactions, and measurable information.

The final model contains six fact tables.

## 4.1 fact_sales

This is the central sales transaction table.

It contains sales-related information such as:

- Order details
- Customer information
- Product information
- Quantity
- Sales amount
- Discount and cost-related information
- Dimension keys

The sales details were combined with the required order information.

Dimension lookups were used to bring the relevant keys into the fact table.

## 4.2 fact_inventory

This table contains product inventory information.

The source inventory data was prepared into a structure suitable for analysis.

The transformation process included converting month-based columns into rows using unpivoting, so inventory could be analysed by product and month.

## 4.3 fact_campaign_spend

This table contains marketing campaign performance information.

The fields visible in the final model include:

- Campaign key
- Date
- Impressions
- Clicks
- Spend

It supports analysis of campaign spending and performance.

## 4.4 fact_promotion_coverage

This table connects campaign and product information.

The final model contains:

- Campaign key
- Product key

It supports analysis of products included in marketing promotions.

## 4.5 fact_order_process

This table contains order processing and delivery-related date information.

The final model includes:

- Customer ID
- Order ID
- Order date
- Invoice date
- Delivery date
- Pay date

It supports analysis of different stages of the order process.

## 4.6 fact_sales_target

This table contains sales target information.

The final model includes:

- Period
- Target revenue

It can be used to compare target revenue with actual sales performance.

---

# Phase 5: Surrogate Keys and Data Integration

### Objective

Prepare fact and dimension tables so they can be connected correctly.

Surrogate keys were created for selected dimension tables using index columns in Power Query.

Examples include:

- customer key
- product key
- campaign key
- geo key
- flag key

These generated keys help identify dimension records within the data model.

The fact tables were then prepared with the relevant dimension keys through merge and lookup operations.

### Lookup Process

The dimension tables were used as lookup sources to retrieve the required keys.

The process involved:

1. Selecting the appropriate fact table.
2. Merging it with the required dimension table.
3. Matching records using the relevant columns.
4. Expanding only the required key column.
5. Checking the resulting records and totals.

This process helps replace repeated descriptive values with the corresponding dimension keys.

---

# Phase 6: Data Quality and Validation

### Objective

Ensure that transformations and relationships do not introduce incorrect records or change important business totals unexpectedly.

During fact table development, special attention was given to the effect of merges.

### Validation Approach

The project followed these checks:

- Checking for duplicate records.
- Identifying duplicate dimension values.
- Checking whether joins create additional rows.
- Reviewing records that do not match during lookups.
- Comparing important totals before and after transformations.
- Checking whether the resulting fact tables retain the expected data.

### Example: Duplicate Product Issue

During the product lookup process, duplicate product names in the product dimension caused records in the fact table to multiply after merging.

This changed the total sales value.

The issue was investigated by grouping records and identifying duplicate product names in the dimension.

The duplicate records were reviewed, and the unnecessary record was removed based on the available source information.

The lookup was then checked again.

This demonstrates why validating joins is important in Power BI data modeling.

---

# Phase 7: Relationship Development

### Objective

Connect fact tables and dimension tables to create the final analytical model.

After preparing the tables, relationships were created in Power BI Model View.

The final model contains the following dimensions:

- dim_customer
- dim_product
- dim_campaign
- dim_order_flags
- dim_geo
- dim_date

The fact tables are:

- fact_sales
- fact_inventory
- fact_order_process
- fact_promotion_coverage
- fact_campaign_spend
- fact_sales_target

The relationships allow the dimensions to provide descriptive context for the corresponding business data.

The model contains multiple fact tables supporting different business processes rather than a single fact table.

---

# Phase 8: Supporting Tables

Two additional supporting tables are visible in the final model.

## security

This table contains:

- Email
- Region

It provides the information needed to support region-based user security.

## _measure

This table is used to organise analytical measures separately from the main fact and dimension tables.

Some visible measures include:

- avg_order_pay
- base_total_customer
- total_active_customers
- total_orders

---

# 4. Final Data Model Structure

The completed model contains the following tables.

| Category | Tables |
|---|---|
| Dimensions | dim_customer, dim_product, dim_campaign, dim_order_flags, dim_geo, dim_date |
| Facts | fact_sales, fact_inventory, fact_order_process, fact_promotion_coverage, fact_campaign_spend, fact_sales_target |
| Supporting | security, _measure |

**Total: 14 tables**

- 6 Dimension tables
- 6 Fact tables
- 2 Supporting tables

The final model brings together different business processes in one Power BI data model.

---

# 5. Key Concepts Practised

Through this project, the following data modeling concepts were practised:

- Understanding source data
- Identifying fact and dimension tables
- Dimensional modeling
- Power Query transformations
- Merge Queries and lookup operations
- Removing duplicate records
- Creating surrogate keys
- Data cleaning and preparation
- Unpivoting data
- Relationship development
- Data validation
- Organising DAX measures
- Understanding supporting security tables

---

# 6. Project Outcome

The project transformed multiple sheets of source business data into an organised Power BI data model.

Instead of directly using the original source tables for reporting, the data was prepared into separate fact and dimension tables.

The final model supports different analytical areas, including sales, products, inventory, marketing campaigns, promotions, order processing, and sales targets.

The project provided practical experience in understanding complex source data, preparing tables, managing relationships, handling data-quality issues, and building a structured model for business intelligence.
