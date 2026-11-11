# Power BI Advanced Data Modeling Project

## 📌 Project Overview

This project focuses on building an organised and structured data model using **Microsoft Power BI**.

The objective was to transform multiple sheets of source business data into a well-structured model containing fact tables, dimension tables, and supporting tables.

The project follows an end-to-end data modeling process using Power Query for data preparation, surrogate keys for identifying dimension records, and relationships to connect different business processes.

The final model supports analysis across sales, customers, products, inventory, marketing campaigns, promotions, order processing, and sales targets.

---

## 🎯 Project Objectives

- Understand and explore the source datasets.
- Organise and prepare queries using Power Query.
- Develop fact and dimension tables.
- Create surrogate keys using index columns.
- Integrate dimension keys into fact tables.
- Establish relationships between tables.
- Identify and resolve data-quality issues.
- Develop a structured Power BI data model.

---

## 🛠️ Tools and Technologies

| Tool / Technology | Purpose |
|---|---|
| Microsoft Power BI Desktop | Data modeling and business intelligence |
| Power Query | Data cleaning and transformation |
| DAX | Analytical calculations and measures |
| Microsoft Excel | Source data |

---

## 🔄 Project Workflow

The project was completed through the following stages:

1. Understanding the source data.
2. Organising queries and preparing the workspace.
3. Developing dimension tables.
4. Developing fact tables.
5. Creating surrogate keys.
6. Integrating tables using merge and lookup operations.
7. Establishing relationships.
8. Validating the data model.
9. Organising analytical measures.


## Data Modeling Process

![Power BI Data Modeling Process](Screenshots/02_Data_Modeling_Process.png)

---

## 🗂️ Final Data Model Structure

The final Power BI model contains **14 tables**.

### 1. Dimension Tables

Dimension tables contain descriptive information used to analyse business data.

| Table | Description |
|---|---|
| `dim_customer` | Customer information |
| `dim_product` | Product details |
| `dim_campaign` | Marketing campaign information |
| `dim_geo` | Geographic information |
| `dim_order_flags` | Order-related attributes |
| `dim_date` | Date, month, and year information |

### 2. Fact Tables

Fact tables contain business events and measurable information.

| Table | Description |
|---|---|
| `fact_sales` | Sales transaction information |
| `fact_inventory` | Product inventory information |
| `fact_order_process` | Order processing and delivery dates |
| `fact_promotion_coverage` | Campaign and product coverage |
| `fact_campaign_spend` | Campaign spending and performance |
| `fact_sales_target` | Sales target information |

### 3. Supporting Tables

| Table | Description |
|---|---|
| `security` | Email and region information for security-related functionality |
| `_measure` | Organises analytical measures |

### Model Summary

| Category | Number of Tables |
|---|---:|
| Dimension Tables | 6 |
| Fact Tables | 6 |
| Supporting Tables | 2 |
| **Total** | **14** |

---

## 🔧 Power Query Transformations

The following transformations were used during data preparation and table development:

- Merge Queries
- Expand Columns
- Remove Columns
- Rename Columns
- Change Data Types
- Remove Duplicates
- Add Index Columns
- Filter Rows
- Split Columns
- Trim Text
- Unpivot Columns
- Reorder Columns

These transformations helped prepare the source data for the final model.

---

## 🔑 Data Modeling Concepts

The project provided practical experience with:

- Fact and dimension table design
- Dimensional modeling
- Surrogate key creation
- Merge and lookup operations
- One-to-many relationships
- Relationship cardinality
- Data integration
- Data-quality validation
- Multiple fact tables
- Analytical measure organisation

---

## 📊 Final Data Model

The final model connects different business processes through fact and dimension tables.

It provides a structured foundation for analysing:

- Sales performance
- Customer information
- Product performance
- Inventory levels
- Campaign spending
- Promotion coverage
- Order processing
- Sales targets

![Complete Power BI Data Model](Screenshots/01_Complete_Data_Model.png)


---

## 📁 Repository Structure

```text
Power-BI-Advanced-Data-Modeling/
│
├── Dataset/
│   └── PowerBI_Source_Data.xlsx
│
├── Documentation/
│   └── Project_Process.md
│
├── Screenshots/
│   ├── README.md
│   ├── 01_Complete_Data_Model.png
│   └── 02_Data_Modeling_Process.png
│
├── PowerBI/
│   └── PowerBI_Data_Modeling.pbix
│
└── README.md
```

---

## 📚 Documentation

For a detailed explanation of the project stages, transformations, and modeling approach, refer to:

- [Complete Project Process](Documentation/Project_Process.md)
- [Dataset Information](Dataset/README.md)

---

## 🎓 Key Learnings

Through this project, I gained practical experience in:

- Understanding complex source datasets.
- Preparing data using Power Query.
- Designing fact and dimension tables.
- Creating surrogate keys.
- Integrating tables through merge and lookup operations.
- Handling duplicate records and data-quality issues.
- Building relationships in Power BI Model View.
- Organising a multi-fact data model.

---


The implementation and documentation reflect my project work.

---

**Project:** Power BI Advanced Data Modeling  
**Tool:** Microsoft Power BI Desktop  
**Focus:** Data Preparation | Dimensional Modeling | Fact & Dimension Tables | Data Relationships
