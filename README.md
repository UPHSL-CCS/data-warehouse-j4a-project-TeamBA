[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=21090705&assignment_repo_type=AssignmentRepo)

# Data Warehouse Optimization Project - TeamBA

## Project Overview

**Project Title:** Retail Sales Performance Analytics  
**Course:** Data Warehousing (J4A)  
**Institution:** UPHSL-CCS  
**Presentation Date:** October 22, 2025

### Objective
Implement and analyze data warehouse optimization techniques using cloud-based tools to improve query performance through:
- Partitioning
- Clustering
- Materialized views
- Version-controlled collaboration

### Business Problem
A local retail company wants to analyze sales performance across products, stores, and time to make better inventory and pricing decisions.

---

## Team Members - TeamBA

1. **Mark Anthony Hernandez**
2. **Al Jorome Gonzaga**
3. **Agatha Wendie Floreta**
4. **Larie Amimirog**

---

## Preferred Tools & Technologies

### Data Warehousing & Analytics
- **Google BigQuery** - Cloud data warehouse (Free tier/Student credits available)
  - Partitioning and clustering capabilities
  - SQL-based querying
  - Scalable storage and compute

### Workflow Automation & ETL
- **n8n** - Open-source workflow automation tool
  - Self-hosted (free)
  - Visual workflow builder
  - Data integration and ETL processes

### Development & Collaboration
- **GitHub** - Version control and collaboration
  - Repository management
  - Issue tracking
  - Documentation

- **Visual Studio Code** - Code editor
  - Free and open-source
  - Git integration
  - SQL extensions

### Database & Data Generation
- **PostgreSQL** - Open-source relational database (if needed for source data)
- **Mockaroo** / **Faker.js** - Free test data generation

### Data Visualization (Options)
- **Google Data Studio (Looker Studio)** - Free BI tool integrated with BigQuery
- **Metabase** - Open-source analytics and BI (self-hosted)
- **Apache Superset** - Open-source data visualization platform

### Additional Tools
- **DBeaver** - Free universal database tool
- **Python** - Data processing and scripting
  - pandas, numpy for data manipulation
  - google-cloud-bigquery library

---

## ETL Process

> **Note:** This ETL process is subject to change based on actual dataset structure and project requirements.

### Extract
**Data Sources:**
- **Custom Dataset** - Team will create/collect our own retail sales dataset
  - Point of Sale (POS) transaction records
  - Product inventory information
  - Store and location details
  - Customer purchase data (if applicable)

**Dataset Creation Methods:**
- Manual data collection from real/simulated retail scenarios
- Synthetic data generation using Mockaroo/Faker.js
- Public retail datasets (Kaggle, etc.) as reference/baseline
- CSV/Excel files prepared by the team

**Extraction Methods:**
- CSV/JSON file uploads to cloud storage
- Direct file import to BigQuery
- Database connections (PostgreSQL/MySQL) if needed
- API integrations using n8n workflows for automation

### Transform
**Data Cleaning & Transformation:**
- Remove duplicates and handle missing values
- Standardize date/time formats
- Normalize product categories and store names
- Calculate derived metrics:
  - Total sales amount (quantity × price)
  - Profit margins
  - Sales trends (daily, weekly, monthly)
- Data type conversions
- Currency standardization

**Data Enrichment:**
- Add time dimensions (day, week, month, quarter, year)
- Categorize products by type, brand, price range
- Geographic data for stores (region, city)
- Customer segmentation

**Tools Used:**
- n8n for workflow orchestration
- Python (pandas) for complex transformations
- SQL for data manipulation

### Load
**Target: Google BigQuery Data Warehouse**

**Loading Strategy:**
- Incremental loads for daily transactions
- Full refresh for dimension tables (products, stores, customers)
- Partitioning by date for transaction tables
- Clustering by store_id and product_id for query optimization

**Data Warehouse Schema:**
- **Fact Table:** Sales transactions
- **Dimension Tables:**
  - Products (product_id, name, category, price)
  - Stores (store_id, name, location, region)
  - Customers (customer_id, name, segment)
  - Time (date, day, month, quarter, year)

**Optimization Techniques:**
- Table partitioning by transaction_date
- Clustering on frequently queried columns
- Materialized views for common aggregations
- Scheduled refresh strategies

**Note:** The ETL process design is flexible and will be refined based on:
- Actual dataset characteristics and size
- Data quality and completeness
- Performance testing results
- BigQuery best practices discovered during implementation

---

## Project Timeline

### Midterm Deliverables (October 22, 2025)
- [x] Repository setup
- [x] Team member identification
- [x] Tool selection and feasibility assessment
- [ ] Project plan presentation

### Final Deliverables
- Implementation of data warehouse optimization techniques
- Performance analysis and comparison
- Documentation of results

---

## Notes

All tools selected are either:
- Free and open-source
- Offer free tiers suitable for educational projects
- Provide student credits or academic licenses
- Can be self-hosted at no cost

This ensures the project is feasible within a student budget while meeting all technical requirements.

**Note:** This plan and tool selection is open to changes based on:
- Project requirements evolution
- Technical feasibility testing
- Team feedback and collaboration
- Instructor recommendations

---

## Resources

- [Google BigQuery Sandbox (Free)](https://cloud.google.com/bigquery/docs/sandbox)
- [n8n Documentation](https://docs.n8n.io/)
- [GitHub Student Developer Pack](https://education.github.com/pack)

