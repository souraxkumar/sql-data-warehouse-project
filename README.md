# Data Warehouse and Analytics Project

A modern SQL Server data warehouse built using the **Medallion Architecture (Bronze, Silver, and Gold)** to integrate ERP and CRM data, perform ETL operations, and generate actionable business insights through SQL-based analytics.

## Table of Contents

- [Overview](#overview)
- [Data Architecture](#data-architecture)
- [Project Objectives](#project-objectives)
- [Technology Stack](#technology-stack)
- [Project Requirements](#project-requirements)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Analytics and Reporting](#analytics-and-reporting)
- [Testing and Data Quality](#testing-and-data-quality)
- [Documentation](#documentation)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## Overview

This project demonstrates the development of a modern data warehouse using Microsoft SQL Server. It integrates data from Enterprise Resource Planning (ERP) and Customer Relationship Management (CRM) systems, transforms raw data into a clean and consistent format, and prepares business-ready datasets for analytical reporting.

The project follows industry-standard data engineering practices, including data ingestion, transformation, data modeling, data quality validation, and documentation.

### Key Highlights

- Designed a data warehouse using Medallion Architecture.
- Integrated ERP and CRM datasets from CSV files.
- Built SQL-based ETL pipelines for data extraction, transformation, and loading.
- Implemented data cleansing, standardization, and validation.
- Developed fact and dimension tables using a star schema.
- Created SQL reports to analyze customer behavior, product performance, and sales trends.
- Documented the architecture, data flow, and data models.

## Data Architecture

The project follows the **Medallion Architecture**, which organizes data into three layers: Bronze, Silver, and Gold.

![Data Architecture](docs/data_architecture.png)

### 1. Bronze Layer — Raw Data

- Stores source data in its original format.
- Loads ERP and CRM CSV files into SQL Server.
- Preserves raw records for traceability and troubleshooting.
- Performs initial ingestion with minimal transformations.

### 2. Silver Layer — Cleaned Data

- Cleans and standardizes source data.
- Handles missing values, duplicates, and inconsistent formats.
- Applies data quality rules and validation checks.
- Integrates related ERP and CRM datasets.

### 3. Gold Layer — Business-Ready Data

- Organizes transformed data into analytical fact and dimension tables.
- Implements a star schema for efficient reporting.
- Supports customer, product, and sales analysis.
- Provides a structured foundation for dashboards and business intelligence.

## Project Objectives

The primary objective is to build a reliable and user-friendly data warehouse that consolidates sales-related information and supports data-driven decision-making.

Specific objectives include:

1. Integrating data from multiple source systems.
2. Improving data consistency and quality.
3. Developing reusable SQL-based ETL pipelines.
4. Designing an analytical data model.
5. Creating reports that provide meaningful business insights.
6. Maintaining clear technical and business documentation.

## Technology Stack

| Technology | Purpose |
|---|---|
| Microsoft SQL Server | Database and data warehouse |
| SQL | Data extraction, transformation, modeling, and analysis |
| SQL Server Management Studio (SSMS) | Database development and management |
| CSV | Source data format |
| Draw.io | Architecture, ETL, and data model diagrams |
| Git and GitHub | Version control and project collaboration |
| Notion | Project planning and task documentation |

## Project Requirements

### Data Engineering: Building the Data Warehouse

**Data sources**
- ERP datasets provided as CSV files.
- CRM datasets provided as CSV files.

**Data integration**
- Import data into SQL Server.
- Combine related data from the source systems.
- Apply consistent naming conventions and transformation rules.

**Data quality**
- Identify and resolve data inconsistencies.
- Standardize data formats and values.
- Validate relationships and key fields.
- Test the accuracy and completeness of transformed data.

**Data modeling**
- Create fact and dimension tables.
- Implement a star schema in the Gold layer.
- Document table structures, column definitions, and relationships.

**Scope**
- Focus on the latest available dataset.
- Historical data tracking and historization are outside the current scope.

### Business Intelligence: Analytics and Reporting

The Gold layer supports SQL-based analysis in three key areas.

#### Customer Behavior
- Customer distribution and purchasing patterns.
- Customer contribution to overall sales.
- Identification of high-value customers.
- Customer segmentation opportunities.

#### Product Performance
- Product-wise sales performance.
- Best-performing and underperforming products.
- Product contribution to revenue.
- Opportunities to improve product performance.

#### Sales Trends
- Sales performance over time.
- Revenue distribution across products and customers.
- Identification of sales patterns.
- Support for business planning and decision-making.

## Repository Structure

```text
data-warehouse-project/
│
├── datasets/
│   ├── source_crm/
│   └── source_erp/
│
├── docs/
│   ├── data_architecture.png
│   ├── data_architecture.drawio
│   ├── etl.drawio
│   ├── data_flow.drawio
│   ├── data_models.drawio
│   ├── data_catalog.md
│   ├── naming-conventions.md
│   └── requirements.md
│
├── scripts/
│   ├── bronze/
│   ├── silver/
│   └── gold/
│
├── tests/
│
├── README.md
├── LICENSE
├── .gitignore
└── requirements.txt
```

*Note: The directory structure above is a suggested organization. Keep only files and folders that actually exist in your repository.*

## Getting Started

### Prerequisites

Install the following tools:

- [SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) — Database engine.
- [SQL Server Management Studio (SSMS)](https://learn.microsoft.com/en-us/ssms/install/install) — Database management interface.
- [Git](https://git-scm.com/) — Version control.
- [Draw.io](https://www.drawio.com/) — Architecture and data modeling diagrams.

### Installation and Setup

**Step 1: Clone the repository**

```bash
git clone https://github.com/souraxkumar/sql-data-warehouse-project
cd data-warehouse-project
```

**Step 2: Set up SQL Server**

Install SQL Server Express and configure a database connection using SSMS.

**Step 3: Prepare the source datasets**

Verify that the ERP and CRM CSV files are available in the `datasets/` directory.

**Step 4: Create the database**

Create the project database in SQL Server using SSMS or your database setup scripts.

**Step 5: Execute the SQL scripts**

Run the scripts in the following order, following the dependencies documented in the repository:

1. Bronze — Load raw source data.
2. Silver — Clean and transform the data.
3. Gold — Create analytical tables and views.

**Step 6: Validate the results**

Run the available tests and SQL queries to verify data quality, table relationships, and analytical results.

*Important: Update these instructions to match the actual database name, script filenames, and execution order in your repository.*

## Analytics and Reporting

The project uses SQL queries to transform warehouse data into actionable insights.

Potential reporting metrics include:

- Total sales revenue.
- Number of customers.
- Number of products sold.
- Sales by product and customer.
- Top-performing products.
- Customer purchasing patterns.
- Sales trends over time.

The final analytical outputs can also be connected to a business intelligence tool, such as Power BI, for interactive dashboards.

## Testing and Data Quality

Data quality is an essential part of the warehouse development process.

The project can include validation checks for:

- Duplicate records.
- Missing or invalid values.
- Data type consistency.
- Primary key uniqueness.
- Referential integrity between fact and dimension tables.
- Row counts between source and target tables.
- Accuracy of calculated sales metrics.

SQL validation scripts should be maintained in the `tests/` directory.

## Documentation

Project documentation is maintained in the `docs/` directory.

| Document | Description |
|---|---|
| `data_architecture.drawio` | Overall warehouse architecture |
| `etl.drawio` | ETL techniques and processes |
| `data_flow.drawio` | Movement of data across the layers |
| `data_models.drawio` | Fact tables, dimension tables, and star schema |
| `data_catalog.md` | Dataset fields, descriptions, and metadata |
| `naming-conventions.md` | Naming rules for tables, columns, and files |
| `requirements.md` | Business and technical requirements |

For project planning and implementation guidance, refer to the [SQL Data Warehouse Project Guide](https://thankful-pangolin-2ca.notion.site/SQL-Data-Warehouse-Project-16ed041640ef80489667cfe2f380b269?pvs=4).

## License

This project is distributed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

This project is inspired by the educational resources and data engineering tutorials of **Baraa Khatib Salkini**, also known as **Data With Baraa**.

- [YouTube](http://bit.ly/3GiCVUE)
- [LinkedIn](https://linkedin.com/in/baraa-khatib-salkini)
- [Official Website](https://www.datawithbaraa.com)
- [Newsletter](https://bit.ly/BaraaNewsletter)
- [YouTube Membership](https://www.youtube.com/@datawithbaraa)

---

If you find this project useful, consider giving the repository a star on GitHub.
