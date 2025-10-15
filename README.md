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

### Primary Data Warehouse
- **PostgreSQL** - Open-source relational database (Primary warehouse)
  - Table partitioning (by date ranges, list, hash)
  - Indexing and clustering capabilities
  - Materialized views for query optimization
  - Full control with no cost limitations
  - Can be self-hosted locally or on free cloud platforms (Supabase, Railway, Render)
  - Excellent for learning optimization techniques

### Cloud Data Warehouse (Comparison & Validation)
- **Google BigQuery** - Cloud data warehouse (Secondary/Comparison)
  - Limited usage due to free tier constraints (1 TB queries/month, 10 GB storage)
  - Used for performance comparison with small sample datasets
  - Demonstrates understanding of cloud-based solutions
  - Native partitioning and clustering features
  
**Strategic Approach:**
- Build and optimize in PostgreSQL (no limitations)
- Export sample data to BigQuery for cloud comparison
- Document performance differences between self-hosted and cloud solutions

### Workflow Automation & ETL
- **n8n** - Open-source workflow automation tool
  - Self-hosted (free)
  - Visual workflow builder
  - Data integration and ETL processes
  - Connect PostgreSQL and BigQuery workflows

### Development & Collaboration
- **GitHub** - Version control and collaboration
  - Repository management
  - Issue tracking
  - Documentation

- **Visual Studio Code** - Code editor
  - Free and open-source
  - Git integration
  - SQL extensions
  - PostgreSQL extensions

### Database Management & Data Generation
- **DBeaver** - Free universal database tool
  - PostgreSQL and BigQuery connections
  - Query development and testing
  - Data export/import
  
- **pgAdmin** - PostgreSQL administration tool
  
- **Mockaroo** / **Faker.js** - Free test data generation

### Data Visualization (Options)
- **Metabase** - Open-source analytics and BI (self-hosted, works well with PostgreSQL)
- **Apache Superset** - Open-source data visualization platform
- **Google Data Studio (Looker Studio)** - Free BI tool (for BigQuery comparison)

### Additional Tools
- **Python** - Data processing and scripting
  - pandas, numpy for data manipulation
  - psycopg2 for PostgreSQL connections
  - google-cloud-bigquery library (for comparison phase)

---

## Technical Approach & Rationale

### Why PostgreSQL as Primary Warehouse?

**Advantages:**
1. **No Cost Limitations** - Unlimited queries, storage, and experimentation
2. **Full Control** - Complete access to optimization techniques and configurations
3. **Learning Depth** - Hands-on experience with partitioning, indexing, and tuning
4. **Production-Ready** - Used by major companies for data warehousing
5. **Supports All Required Features:**
   - Table partitioning (declarative partitioning)
   - Indexes for clustering-like performance
   - Materialized views with refresh strategies
   - Query optimization and EXPLAIN ANALYZE

**BigQuery Limitations for Students:**
- Free tier: 1 TB query processing/month (can be exhausted quickly)
- 10 GB storage limit in sandbox mode
- Potential unexpected costs if limits exceeded
- Less control over optimization internals

**Our Strategy:**
1. **Phase 1:** Build complete data warehouse in PostgreSQL
   - Implement partitioning strategies
   - Create and optimize indexes
   - Build materialized views
   - Full-scale testing without cost concerns

2. **Phase 2:** Validate with BigQuery
   - Use small sample dataset (< 1 GB)
   - Compare query performance
   - Demonstrate cloud warehouse understanding
   - Stay within free tier limits

3. **Deliverable:** Comprehensive comparison showing:
   - Self-hosted vs. cloud trade-offs
   - Cost-benefit analysis
   - Performance benchmarks
   - Optimization techniques in both platforms

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

#### Primary Target: PostgreSQL Data Warehouse

**Loading Strategy:**
- Incremental loads for daily transactions using INSERT...ON CONFLICT
- Full refresh for dimension tables (products, stores, customers)
- Automated ETL workflows using n8n or Python scripts
- Transaction logs for data lineage tracking

**PostgreSQL Optimization Implementation:**

1. **Table Partitioning:**
   - Partition sales fact table by transaction_date (monthly or quarterly ranges)
   - List partitioning for stores by region
   - Hash partitioning for large dimension tables if needed

2. **Indexing (Clustering equivalent):**
   - B-tree indexes on frequently queried columns (store_id, product_id)
   - Composite indexes for common query patterns
   - Partial indexes for specific conditions

3. **Materialized Views:**
   - Pre-aggregated sales by product/store/time period
   - Scheduled refresh strategies (hourly, daily, weekly)
   - CONCURRENTLY refresh to avoid locking

**Data Warehouse Schema:**
- **Fact Table:** `fact_sales` (partitioned by transaction_date)
  - transaction_id, transaction_date, store_id, product_id, customer_id, quantity, amount, profit
- **Dimension Tables:**
  - `dim_products` (product_id, name, category, brand, price)
  - `dim_stores` (store_id, name, location, region, city)
  - `dim_customers` (customer_id, name, segment, join_date)
  - `dim_time` (date, day, month, quarter, year, day_of_week)

#### Secondary Target: Google BigQuery (Sample Data for Comparison)

**Purpose:** Validate optimization techniques with cloud warehouse
**Approach:**
- Export small sample dataset from PostgreSQL (< 1 GB)
- Implement same schema with BigQuery-native partitioning and clustering
- Compare query performance and optimization strategies
- Stay within free tier limits (1 TB queries/month)

**BigQuery Optimization:**
- Table partitioning by transaction_date (built-in)
- Clustering on store_id, product_id
- Materialized views for comparison

**Note:** The ETL process design is flexible and will be refined based on:
- Actual dataset characteristics and size
- Data quality and completeness
- Performance testing results
- PostgreSQL and BigQuery best practices discovered during implementation

---

## Project Timeline

### Midterm Deliverables (October 22, 2025)
- [x] Repository setup
- [x] Team member identification
- [x] Tool selection and feasibility assessment
- [x] Technical approach and rationale documentation
- [ ] Project plan presentation

### Final Deliverables

**Phase 1: PostgreSQL Data Warehouse Development**
- Dataset creation and preparation
- PostgreSQL database setup and schema design
- ETL pipeline implementation using n8n/Python
- Table partitioning implementation
- Index optimization and clustering strategies
- Materialized views creation and refresh scheduling
- Query performance testing and optimization

**Phase 2: BigQuery Comparison (Sample Data)**
- Export sample dataset to BigQuery
- Implement equivalent schema with BigQuery optimizations
- Performance comparison analysis
- Document trade-offs between self-hosted and cloud solutions

**Phase 3: Documentation & Analysis**
- Performance benchmarking results
- Optimization techniques comparison
- Cost-benefit analysis
- Final presentation and repository documentation

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

### PostgreSQL Documentation
- [PostgreSQL Table Partitioning](https://www.postgresql.org/docs/current/ddl-partitioning.html)
- [PostgreSQL Indexes](https://www.postgresql.org/docs/current/indexes.html)
- [Materialized Views](https://www.postgresql.org/docs/current/rules-materializedviews.html)
- [Query Performance Optimization](https://www.postgresql.org/docs/current/performance-tips.html)

### Cloud Platforms (Free Tiers)
- [Supabase](https://supabase.com/) - Free PostgreSQL hosting
- [Railway](https://railway.app/) - Free tier for PostgreSQL
- [Render](https://render.com/) - Free PostgreSQL instances

### BigQuery Resources
- [Google BigQuery Sandbox (Free)](https://cloud.google.com/bigquery/docs/sandbox)
- [BigQuery Partitioning & Clustering](https://cloud.google.com/bigquery/docs/partitioned-tables)

### Tools & Automation
- [n8n Documentation](https://docs.n8n.io/)
- [DBeaver](https://dbeaver.io/) - Universal database tool
- [pgAdmin](https://www.pgadmin.org/) - PostgreSQL administration

### Learning Resources
- [GitHub Student Developer Pack](https://education.github.com/pack)
- [PostgreSQL Tutorial](https://www.postgresqltutorial.com/)

