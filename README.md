[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=21090705&assignment_repo_type=AssignmentRepo)

# Data Warehouse Optimization Project - TeamBA

> **TL;DR:** Building an intelligent retail analytics platform using **n8n** (workflow automation) + **BigQuery** (data warehouse) + **AI** (Ollama/Gemini). Features automated ETL pipelines, natural language queries ("Show me top products this month"), anomaly detection, and predictive insights - all with 100% FREE tools! 🚀

---

## Project Overview

**Project Title:** Retail Sales Performance Analytics  
**Team:** TeamBA  
**Course:** Data Warehousing (J4A)  
**Institution:** UPHSL-CCS  
**Presentation Date:** October 22, 2025

### Objective
Implement and analyze data warehouse optimization techniques using **n8n workflow automation** and **Google BigQuery** to improve query performance through:
- Automated ETL pipelines with n8n
- Partitioning and clustering strategies
- Materialized views for performance optimization
- Real-time data integration workflows
- Version-controlled collaboration

### Business Problem
A local retail company wants to analyze sales performance across products, stores, and time to make better inventory and pricing decisions. The company needs an automated, scalable ETL solution that can:
- Extract sales data from multiple sources automatically
- Transform and enrich data for analytics
- Load optimized data structures into BigQuery
- Enable fast, efficient querying for business insights

---

## 🌟 Key Features - What Makes This Project Special?

<table>
<tr>
<td width="50%">

### 🔄 **Automated ETL with n8n**
- Visual workflow builder
- Zero-code data pipelines
- Real-time & scheduled processing
- Error handling & monitoring

</td>
<td width="50%">

### 🤖 **AI-Powered Analytics**
- Natural language queries
- Automatic anomaly detection
- Daily insights generation
- Predictive sales forecasting

</td>
</tr>
<tr>
<td width="50%">

### ⚡ **Performance Optimization**
- Table partitioning (date-based)
- Multi-column clustering
- Materialized views
- 10x faster queries

</td>
<td width="50%">

### 💰 **100% FREE Tools**
- BigQuery (free tier: 1 TB/month)
- n8n (open-source)
- Ollama AI (runs locally)
- PostgreSQL (open-source)

</td>
</tr>
</table>

---

## Team Members - TeamBA

1. **Mark Anthony Hernandez**
2. **Al Jorome Gonzaga**
3. **Agatha Wendie Floreta**
4. **Larie Amimirog**

---

## Core Technology Stack

### 🔄 ETL & Workflow Automation (PRIMARY FOCUS)
- **n8n** - Open-source workflow automation platform (Central ETL Engine)
  - Visual ETL pipeline builder
  - 400+ pre-built integrations
  - Self-hosted (free) with full control
  - Scheduled workflow execution
  - Error handling and retry logic
  - Webhook triggers for real-time data ingestion
  - HTTP Request nodes for API connections
  - Database nodes (PostgreSQL, MySQL)
  - Google BigQuery integration
  - Data transformation with JavaScript/JSON
  - Version control for workflows (export as JSON)

### 📊 Data Warehouse (FREE OPTIONS)
- **Google BigQuery Sandbox** - Cloud data warehouse (COMPLETELY FREE)
  - **Free Tier:** 10 GB storage, 1 TB queries/month (MORE than enough for this project)
  - No credit card required for sandbox mode
  - Native partitioning and clustering
  - SQL-based analytics
  - Integrates seamlessly with n8n
  - Materialized views support
  - Query performance analysis tools
  
- **Alternative FREE Options (if BigQuery doesn't work):**
  - **DuckDB** - Fast in-process analytical database (100% free, runs locally)
  - **PostgreSQL with TimescaleDB** - Time-series optimization (free, self-hosted)
  - **ClickHouse** - Fast columnar database (free, open-source)

### 💾 Source Database & Data Generation
- **PostgreSQL** - Source transactional database
  - Simulates retail company's operational database
  - Stores raw sales transactions
- **Mockaroo** / **Faker.js** - Realistic test data generation
  - Generate retail sales datasets
  - Product catalogs, store information
  - Customer transaction data

### 📈 Data Visualization
- **Google Looker Studio** - BI and visualization
  - Direct BigQuery integration
  - Real-time dashboard updates
  - Free to use
  - Share insights with stakeholders

### 🛠️ Development & Collaboration
- **GitHub** - Version control
  - n8n workflow version control (JSON exports)
  - SQL scripts and documentation
  - Team collaboration
  - Project tracking

- **Visual Studio Code** - Development environment
  - SQL extensions for BigQuery
  - JSON editing for n8n workflows
  - Git integration

- **Python** (Optional for advanced transformations)
  - pandas for complex data manipulation
  - google-cloud-bigquery library
  - Can be triggered from n8n workflows

### 🔍 Database Management
- **DBeaver** - Universal database tool
  - Connect to PostgreSQL and BigQuery
  - Query testing and validation
  - Schema visualization

---

## 🤖 AI-Powered Analytics with n8n

### Intelligent Automation Features

Our project will integrate AI capabilities through n8n workflows to provide smart, automated insights:

#### 1️⃣ **Automatic Daily Insights** 📈
**n8n Workflow:** Daily Sales Summary with AI
- **Trigger:** Scheduled daily at 8:00 AM
- **Process:**
  1. Query BigQuery for yesterday's sales data
  2. Calculate key metrics (total sales, top products, store performance)
  3. Send to OpenAI/Claude API with prompt: *"Summarize today's sales trends in 3 bullet points"*
  4. Send formatted summary via email/Slack to management
  
**Example Output:**
```
📊 Daily Sales Insights - October 15, 2025
• Sales increased 15% compared to last week, driven by electronics category
• Store #5 (Manila Branch) achieved highest revenue at ₱125,000
• Weekend promotions boosted average transaction value by 22%
```

#### 2️⃣ **Anomaly Detection** 🚨
**n8n Workflow:** Real-time Transaction Monitoring
- **Trigger:** Runs every hour or on new data load
- **Process:**
  1. Query recent transactions and calculate statistical baselines
  2. Detect anomalies: unusual spikes, drops, or patterns
  3. AI analysis: *"Explain why these transactions are unusual"*
  4. Alert team with actionable recommendations
  
**Detection Rules:**
- Transaction volume > 3 standard deviations from mean
- Sudden price changes on products
- Unusual purchasing patterns (e.g., 100x normal quantity)
- Store performance drops > 40% vs. previous week

**Alert Example:**
```
⚠️ ANOMALY DETECTED
Store: Branch #3
Issue: Transaction volume dropped 65% today
Possible Causes: System outage, local holiday, or inventory shortage
Action: Investigate immediately
```

#### 3️⃣ **Natural Language Query Interface** 💬
**n8n Workflow:** AI-Powered Data Assistant
- **Trigger:** Webhook (integrated with Slack/Teams/Web app)
- **Process:**
  1. Receive natural language question from user
  2. Send to AI (OpenAI GPT-4/Claude): *"Convert this to a BigQuery SQL query"*
  3. Execute generated SQL on BigQuery
  4. Format results and send back to user
  
**Example Queries:**
- User: *"Show me this month's top-selling regions"*
- AI generates: 
  ```sql
  SELECT 
    store_region,
    SUM(total_amount) as revenue,
    COUNT(*) as transactions
  FROM fact_sales
  WHERE DATE(transaction_date) >= DATE_TRUNC(CURRENT_DATE(), MONTH)
  GROUP BY store_region
  ORDER BY revenue DESC
  LIMIT 10
  ```
- Returns formatted results to user

**More Examples:**
- *"Which products had declining sales last month?"*
- *"Compare weekend vs weekday sales for electronics"*
- *"What's our average transaction value by store?"*

#### 4️⃣ **Predictive Insights** 🔮
**n8n Workflow:** Sales Forecasting
- **Trigger:** Weekly on Monday mornings
- **Process:**
  1. Extract historical sales trends (past 3-6 months)
  2. AI analysis: *"Predict next week's sales and identify risks"*
  3. Generate actionable recommendations for inventory
  4. Send forecast report to management

**Output:**
```
📊 Weekly Forecast - October 15-22, 2025
Predicted Sales: ₱850,000 - ₱920,000
Confidence: 85%

Recommendations:
✅ Increase stock for "Product A" (predicted 40% demand increase)
⚠️ Slow movement expected for "Product B" (consider promotion)
📈 Electronics category trending up - prepare additional inventory
```

#### 5️⃣ **Automated Report Generation** 📄
**n8n Workflow:** Weekly Executive Summary
- **Trigger:** Every Friday at 5:00 PM
- **Process:**
  1. Query all relevant metrics from BigQuery
  2. Generate visualizations (charts, graphs)
  3. AI writes executive summary: *"Create a professional weekly report"*
  4. Export as PDF and email to stakeholders

### AI Integration Options (All FREE tiers available)

**Option 1: OpenAI API**
- GPT-4 for complex analysis and natural language
- n8n has native OpenAI node
- Free trial credits available

**Option 2: Claude API (Anthropic)**
- Excellent for data analysis and summaries
- n8n HTTP Request node
- Free tier available

**Option 3: Google Gemini API**
- Free quota: 60 requests/minute
- Integrates well with BigQuery ecosystem
- Great for insights and predictions

**Option 4: Ollama (100% FREE, Self-hosted)**
- Run LLMs locally (Llama 3, Mistral, etc.)
- No API costs, complete privacy
- n8n can connect via HTTP Request node
- Best for student projects with no budget

**Recommended:** Start with **Ollama** (free) or **Google Gemini** (free tier) to keep project cost at $0!

---

## ETL Process with n8n Integration

> **Primary Tool:** All ETL workflows will be built and orchestrated using n8n

### 🎯 Complete Architecture with AI Integration

```
                         ┌─────────────────────────────────────┐
                         │   AI Layer (Ollama/Gemini/GPT)     │
                         │  • Natural Language Queries         │
                         │  • Anomaly Detection               │
                         │  • Automated Insights              │
                         └──────────────┬──────────────────────┘
                                        │
                                        ↓
┌──────────────┐     ┌─────────────────────────────────┐     ┌──────────────────┐
│ PostgreSQL   │────→│   n8n Workflow Automation       │────→│  BigQuery DW     │
│ (Source DB)  │     │  • ETL Pipelines                │     │  • Partitioned   │
└──────────────┘     │  • Schedulers & Webhooks        │     │  • Clustered     │
                     │  • Transformations              │     │  • Materialized  │
┌──────────────┐     │  • AI Integration               │     └────────┬─────────┘
│ Mockaroo     │────→│  • Data Quality Checks          │              │
│ (Test Data)  │     │  • Error Handling               │              │
└──────────────┘     └─────────────────────────────────┘              ↓
                                                              ┌──────────────────┐
                                                              │  Looker Studio   │
                                                              │  (Dashboards)    │
                                                              └──────────────────┘
                                                 
                     ┌─────────────────────────────────┐
                     │  Automated Outputs              │
                     │  • Slack/Email Alerts           │
                     │  • Daily Insights Reports       │
                     │  • Anomaly Notifications        │
                     └─────────────────────────────────┘
```

---

### 📥 EXTRACT - Data Ingestion with n8n

#### Data Sources
**Primary Source:** PostgreSQL database (simulating retail company's operational system)
- Sales transactions table
- Product catalog
- Store information
- Customer data

#### n8n Extraction Workflows

**Workflow 1: Scheduled Batch Extraction**
- **Trigger:** Cron schedule (daily at 2:00 AM)
- **Nodes:**
  1. Schedule Trigger node
  2. PostgreSQL node (query new/updated records)
  3. Filter node (validate data completeness)
  4. Set node (prepare for transformation)
- **Query Pattern:** Extract incremental data based on `last_modified_date` or `transaction_date`

**Workflow 2: Real-time Transaction Capture**
- **Trigger:** Webhook (receives POST requests from POS systems)
- **Nodes:**
  1. Webhook node (listens for new transactions)
  2. Validate node (check required fields)
  3. PostgreSQL node (insert to staging table)
  4. Set node (prepare metadata)
- **Use Case:** Capture sales as they happen for near real-time analytics

**Workflow 3: File-based Data Import**
- **Trigger:** Manual or scheduled
- **Nodes:**
  1. Read Binary File node (CSV/JSON from local or cloud storage)
  2. Spreadsheet File node (parse CSV/Excel)
  3. Item Lists node (split into individual records)
  4. Set node (map columns to schema)
- **Use Case:** Import historical data or external datasets

#### Data Generation for Testing
- **Mockaroo Integration:** n8n HTTP Request node calls Mockaroo API
- **Generated Data Types:**
  - Realistic transaction records (1000-10000 records)
  - Product catalog with categories, prices, SKUs
  - Store locations across multiple regions
  - Customer demographics and purchase history

---

### 🔄 TRANSFORM - Data Processing with n8n

#### n8n Transformation Capabilities

**1. Data Cleaning Workflows**

**Node Chain:**
- **Remove Duplicates:** Aggregate node (group by unique keys)
- **Handle Nulls:** IF node (check for missing values) → Set default values
- **Data Type Conversion:** Code node (JavaScript) for complex conversions
- **Date Standardization:** Date & Time node for consistent formatting

**Example Transformation:**
```javascript
// Code node in n8n for calculating total sales
items.map(item => ({
  ...item,
  total_amount: item.quantity * item.unit_price,
  discount_applied: item.discount_percent / 100 * item.unit_price * item.quantity,
  net_amount: (item.quantity * item.unit_price) - (item.discount_percent / 100 * item.unit_price * item.quantity),
  transaction_timestamp: new Date(item.sale_date).toISOString()
}));
```

**2. Data Enrichment Workflows**

**Time Dimension Enrichment:**
```javascript
// Extract time components from transaction date
const date = new Date(item.transaction_date);
return {
  ...item,
  year: date.getFullYear(),
  quarter: Math.ceil((date.getMonth() + 1) / 3),
  month: date.getMonth() + 1,
  month_name: date.toLocaleString('en-US', { month: 'long' }),
  week: getWeek(date),
  day_of_week: date.getDay(),
  day_name: date.toLocaleString('en-US', { weekday: 'long' }),
  is_weekend: date.getDay() === 0 || date.getDay() === 6
};
```

**Product Categorization:**
- **Merge node:** Join product data with category mappings
- **Switch node:** Route products by price range (budget/mid/premium)
- **Function node:** Calculate profit margins

**Store Geographic Enrichment:**
- **HTTP Request node:** Call geocoding API for coordinates (if needed)
- **Set node:** Add region, city, country fields
- **IF node:** Classify stores by location type (urban/suburban/rural)

**3. Business Logic Transformations**

- **Calculate derived metrics:**
  - Gross sales, net sales, discounts
  - Profit margins (requires cost data)
  - Units sold per transaction
  - Average transaction value
  
- **Customer segmentation:**
  - RFM analysis (Recency, Frequency, Monetary)
  - Purchase patterns
  - Customer lifetime value

**4. Data Quality Workflows**
- **Validation nodes:** Check data ranges, required fields
- **Error handling:** Catch and log invalid records to error table
- **Data profiling:** Count records, check distributions
- **Alert triggers:** Send notifications for data quality issues

---

### 📤 LOAD - BigQuery Integration with n8n

#### Data Warehouse Schema (Star Schema)

**Fact Table: `fact_sales`**
```sql
- transaction_id (STRING)
- transaction_date (DATE) -- PARTITION KEY
- store_id (STRING) -- CLUSTER KEY
- product_id (STRING) -- CLUSTER KEY
- customer_id (STRING)
- quantity (INTEGER)
- unit_price (NUMERIC)
- discount_amount (NUMERIC)
- total_amount (NUMERIC)
- profit_margin (NUMERIC)
```

**Dimension Tables:**
- `dim_products` (product_id, name, category, brand, price_range)
- `dim_stores` (store_id, name, city, region, store_type)
- `dim_customers` (customer_id, name, segment, join_date)
- `dim_date` (date, year, quarter, month, week, day, is_weekend)

#### n8n Load Workflows

**Workflow 1: Fact Table Load (Incremental)**
- **Nodes:**
  1. Batch node (group records in batches of 1000)
  2. Google BigQuery node (INSERT operation)
  3. Set partitioning: `PARTITION BY DATE(transaction_date)`
  4. Set clustering: `CLUSTER BY store_id, product_id`
  5. IF node (check for load errors)
  6. Merge node (update load metadata table)

**Workflow 2: Dimension Table Load (SCD Type 1 - Full Refresh)**
- **Nodes:**
  1. Google BigQuery node (TRUNCATE target table)
  2. Google BigQuery node (INSERT all dimension records)
  3. Update node (log refresh timestamp)

**Workflow 3: Materialized View Creation**
- **Trigger:** Run after successful fact table load
- **n8n BigQuery Node:** Execute SQL to create/refresh materialized views

**Example Materialized Views:**
```sql
-- Daily sales summary
CREATE MATERIALIZED VIEW mv_daily_sales_summary
PARTITION BY sale_date
CLUSTER BY store_id
AS
SELECT 
  DATE(transaction_date) as sale_date,
  store_id,
  COUNT(*) as transaction_count,
  SUM(total_amount) as total_sales,
  AVG(total_amount) as avg_transaction_value,
  SUM(quantity) as total_units_sold
FROM fact_sales
GROUP BY sale_date, store_id;

-- Product performance
CREATE MATERIALIZED VIEW mv_product_performance
CLUSTER BY product_id
AS
SELECT 
  product_id,
  COUNT(DISTINCT DATE(transaction_date)) as days_sold,
  COUNT(*) as transactions,
  SUM(quantity) as units_sold,
  SUM(total_amount) as revenue,
  AVG(profit_margin) as avg_margin
FROM fact_sales
GROUP BY product_id;
```

#### Optimization Implementation

**1. Partitioning Strategy**
- n8n ensures all writes to `fact_sales` include partition column
- BigQuery DDL executed via n8n: `PARTITION BY DATE(transaction_date)`
- Benefits: Query only relevant date ranges, reduce costs

**2. Clustering Strategy**
- Cluster by most frequently filtered columns: `store_id`, `product_id`
- Implemented in table DDL via n8n workflow
- Benefits: Faster WHERE clause filtering, improved join performance

**3. Materialized Views**
- Pre-aggregate common queries
- Refresh strategy: 
  - Scheduled n8n workflow (every 6 hours)
  - Or triggered after ETL completion
- Benefits: Sub-second query response for dashboards

**4. Incremental Loading**
- n8n tracks last successful load timestamp
- Only extract and load new/changed records
- Reduces processing time and costs

#### Performance Monitoring Workflow
- **n8n workflow** to query BigQuery INFORMATION_SCHEMA
- Collect metrics:
  - Query execution times
  - Bytes processed
  - Slot usage
  - Table sizes
- Store metrics in monitoring table
- Generate performance reports

---

### 🔄 n8n ETL Orchestration Features

#### Workflow Scheduling
- **Daily full ETL:** 2:00 AM (low traffic period)
- **Hourly incremental loads:** Every hour during business hours
- **Dimension refresh:** Weekly on Sundays
- **Materialized view refresh:** Every 6 hours

#### Error Handling & Monitoring
- **Try/Catch blocks:** Error trigger nodes capture failures
- **Retry logic:** Automatic retry with exponential backoff
- **Alerts:** Send email/Slack notifications on failures
- **Logging:** Write execution logs to PostgreSQL audit table

#### Data Quality Checks
- **Pre-load validation:** Check record counts, null values, data ranges
- **Post-load validation:** Compare source vs. target counts
- **Reconciliation workflow:** Daily data integrity checks
- **Alert triggers:** Notify team if thresholds exceeded

#### Version Control & Collaboration
- Export n8n workflows as JSON files
- Store in GitHub repository under `/n8n-workflows/`
- Team members can import and test workflows
- Track changes and rollback if needed

---

### 📊 Expected Outcomes

**ETL Performance Metrics:**
- Extract time: < 5 minutes for daily batch
- Transform time: < 10 minutes for 10,000 records
- Load time: < 5 minutes to BigQuery
- Total ETL duration: < 20 minutes end-to-end

**Query Performance Improvements (with optimization):**
- Baseline (no optimization): 10-30 seconds
- With partitioning: 3-8 seconds
- With partitioning + clustering: 1-3 seconds
- With materialized views: < 1 second

**Data Warehouse Statistics:**
- Fact table: 10,000 - 50,000 transactions
- Dimension tables: 100-500 records each
- Date range: 1-2 years of data
- Storage: < 1 GB (within free tier)

---

## Project Timeline & Deliverables

### Phase 1: Setup & Planning (Week 1-2) ✅
- [x] Repository setup and GitHub collaboration
- [x] Team member identification
- [x] Tool selection (n8n + BigQuery focus)
- [x] ETL architecture design
- [ ] **Midterm Presentation (October 22, 2025)**
  - Project overview and objectives
  - n8n + BigQuery architecture
  - ETL workflow design
  - Expected optimization techniques

### Phase 2: Data Preparation (Week 3-4)
- [ ] Install and configure n8n (self-hosted)
- [ ] Set up PostgreSQL source database
- [ ] Generate test dataset using Mockaroo
- [ ] Create BigQuery project and datasets
- [ ] Design and document database schemas
  - Star schema (fact and dimension tables)
  - Identify partition and cluster keys

### Phase 3: ETL Development with n8n (Week 5-7)
- [ ] **Extract workflows:**
  - Build scheduled batch extraction from PostgreSQL
  - Create webhook-based real-time ingestion
  - Implement file-based import workflow
- [ ] **Transform workflows:**
  - Data cleaning pipeline (nulls, duplicates, validation)
  - Time dimension enrichment
  - Business metrics calculation
  - Data quality checks
- [ ] **Load workflows:**
  - Incremental load to fact tables
  - Full refresh for dimension tables
  - Implement error handling and logging
- [ ] **AI Integration Setup:**
  - Install Ollama (local AI) or configure Gemini API
  - Test AI connections from n8n
  - Build basic AI workflow prototype
- [ ] Export n8n workflows as JSON to GitHub

### Phase 4: Optimization Implementation (Week 8-9)
- [ ] **Partitioning:**
  - Implement date-based partitioning on fact_sales
  - Test query performance improvements
  - Document cost savings
- [ ] **Clustering:**
  - Apply clustering on store_id and product_id
  - Measure query speed improvements
  - Compare with non-clustered tables
- [ ] **Materialized Views:**
  - Create aggregated views for common queries
  - Set up refresh schedules via n8n
  - Benchmark query times (< 1 second target)
- [ ] Create n8n workflow for performance monitoring

### Phase 4.5: AI-Powered Features (Week 9-10)
- [ ] **Daily Insights Workflow:**
  - Build n8n workflow for automatic insights generation
  - Connect to AI API (Ollama/Gemini)
  - Schedule daily at 8:00 AM
  - Send formatted reports via email/Slack
- [ ] **Anomaly Detection:**
  - Create statistical baseline calculations
  - Build detection rules (3-sigma, trends)
  - Integrate AI explanations
  - Set up real-time alerts
- [ ] **Natural Language Query Interface:**
  - Create webhook endpoint for user queries
  - Build SQL generation workflow with AI
  - Test with sample business questions
  - Document example queries
- [ ] **Sales Forecasting:**
  - Build predictive analytics workflow
  - Generate weekly forecasts
  - Create actionable recommendations
- [ ] Export all AI workflows to GitHub

### Phase 5: Testing & Analysis (Week 11-12)
- [ ] Run performance benchmarks:
  - Baseline vs. optimized queries
  - ETL execution times
  - Data quality metrics
  - AI workflow response times
- [ ] Create test queries for business questions:
  - Top products by sales
  - Store performance comparisons
  - Sales trends over time
- [ ] Test AI features:
  - Natural language query accuracy
  - Anomaly detection effectiveness
  - Forecast prediction quality
- [ ] Build Looker Studio dashboard
- [ ] Document findings and improvements

### Phase 6: Final Deliverables (Week 13)
- [ ] **Documentation:**
  - Complete README with results
  - n8n workflow documentation (ETL + AI)
  - SQL scripts for schema and queries
  - Performance analysis report
  - AI integration guide
- [ ] **Presentation Materials:**
  - Architecture diagrams (with AI layer)
  - Live n8n workflow demonstration
  - AI features showcase (NLP queries, anomaly detection)
  - Performance comparison charts
  - Dashboard showcase with real-time insights
- [ ] **GitHub Repository:**
  - Clean up and organize all workflows
  - Add comprehensive documentation
  - Include sample data and setup instructions
  - Export all n8n workflows (ETL + AI)
- [ ] **Final Presentation & Demo**

---

## 🚀 Getting Started with n8n

### n8n Installation Options

**Option 1: Docker (Recommended for Team)**
```bash
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  docker.n8n.io/n8nio/n8n
```

**Option 2: npm**
```bash
npm install n8n -g
n8n start
```

**Option 3: n8n Cloud (Free Trial)**
- Sign up at [n8n.cloud](https://n8n.cloud)
- 5,000 workflow executions/month (Free tier)

### Initial Setup Steps

1. **Access n8n UI:** Open `http://localhost:5678`
2. **Configure Credentials:**
   - PostgreSQL connection (host, username, password, database)
   - Google BigQuery service account JSON
   - Mockaroo API key (if using)
3. **Import Workflows:** 
   - Download JSON files from `/n8n-workflows/` directory
   - Import via n8n UI: Settings → Workflows → Import
4. **Test Connections:** Run test workflows to verify all integrations work

### Team Collaboration Strategy

**Workflow Sharing:**
- Export workflows as JSON after each update
- Commit to GitHub: `/n8n-workflows/[workflow-name].json`
- Team members pull latest and import to their n8n instance

**Environment Variables:**
- Store sensitive credentials in `.env` file (NOT committed to GitHub)
- Document required variables in `.env.example`

**Testing:**
- Each member tests workflows locally before committing
- Use test data for development
- Production workflows run on designated team member's n8n instance

---

## 📊 Repository Structure

```
data-warehouse-j4a-project-TeamBA/
├── README.md
│
├── n8n-workflows/              # 🔄 Exported n8n workflows (JSON)
│   ├── ETL/
│   │   ├── 01-extract-postgresql.json
│   │   ├── 02-transform-sales-data.json
│   │   ├── 03-load-bigquery-fact.json
│   │   ├── 04-load-bigquery-dimensions.json
│   │   └── 05-create-materialized-views.json
│   │
│   ├── AI-Powered/
│   │   ├── 06-daily-insights-ai.json
│   │   ├── 07-anomaly-detection.json
│   │   ├── 08-nlp-query-interface.json
│   │   ├── 09-sales-forecasting.json
│   │   └── 10-weekly-report-generator.json
│   │
│   └── Monitoring/
│       ├── 11-performance-monitoring.json
│       ├── 12-data-quality-checks.json
│       └── 13-alert-system.json
│
├── sql/                        # 📊 BigQuery SQL scripts
│   ├── schema/
│   │   ├── create_fact_sales.sql
│   │   ├── create_dim_products.sql
│   │   ├── create_dim_stores.sql
│   │   ├── create_dim_customers.sql
│   │   └── create_materialized_views.sql
│   │
│   ├── queries/
│   │   ├── sales_by_store.sql
│   │   ├── product_performance.sql
│   │   ├── time_series_analysis.sql
│   │   └── anomaly_detection_queries.sql
│   │
│   └── optimization/
│       ├── partition_setup.sql
│       ├── clustering_setup.sql
│       └── performance_benchmarks.sql
│
├── data/                       # 📁 Sample datasets (CSV)
│   ├── sample_transactions.csv
│   ├── products.csv
│   ├── stores.csv
│   └── customers.csv
│
├── docs/                       # 📚 Documentation
│   ├── architecture.md
│   ├── n8n-setup-guide.md
│   ├── ai-integration-guide.md
│   ├── performance-results.md
│   └── images/
│       ├── architecture-diagram.png
│       └── n8n-workflow-screenshots/
│
├── scripts/                    # 🔧 Helper scripts
│   ├── generate_test_data.py
│   ├── setup_bigquery.sh
│   ├── setup_ollama.sh
│   └── benchmark_queries.py
│
├── .env.example               # 🔐 Environment variables template
└── .gitignore                 # Git ignore file
```

---

## Key Performance Indicators (KPIs)

### Project Success Metrics

**ETL Efficiency:**
- ✅ Automate 100% of data pipeline with n8n
- ✅ Achieve < 20 minute end-to-end ETL runtime
- ✅ Implement error handling with 0 silent failures
- ✅ 99%+ data quality (validated records vs. total)

**Query Performance:**
- ✅ Reduce query time by 90% (baseline vs. optimized)
- ✅ Sub-second response for dashboard queries
- ✅ Support 10+ concurrent analytical queries
- ✅ Stay within BigQuery free tier limits

**Optimization Techniques:**
- ✅ Implement partitioning (date-based)
- ✅ Implement clustering (multi-column)
- ✅ Create 5+ materialized views
- ✅ Document performance improvements

**Business Impact:**
- ✅ Answer retail business questions in < 3 seconds
- ✅ Enable daily sales performance tracking
- ✅ Provide product and store insights
- ✅ Support data-driven inventory decisions

**AI & Automation:**
- ✅ Deploy 5+ AI-powered workflows
- ✅ Automate daily insights generation
- ✅ Detect anomalies in real-time
- ✅ Natural language query interface
- ✅ Predictive analytics for inventory

---

## Business Questions to Answer

Our data warehouse will efficiently answer these key retail analytics questions:

1. **Sales Performance:**
   - What are the top 10 products by revenue this month?
   - Which stores have the highest sales volume?
   - What is the daily/weekly/monthly sales trend?

2. **Product Analytics:**
   - Which product categories have the best profit margins?
   - What products are frequently purchased together?
   - Which products have declining sales?

3. **Store Analysis:**
   - How do stores compare in terms of revenue and transactions?
   - Which store locations have the best performance?
   - What are the peak sales hours for each store?

4. **Time-Based Insights:**
   - How do sales vary by day of week?
   - What are the seasonal trends?
   - Which months have the highest revenue?

5. **Inventory Optimization:**
   - Which products are slow-moving and need clearance?
   - What products should be restocked based on sales velocity?
   - How much inventory is needed per store?

**All queries will be optimized using partitioning, clustering, and materialized views to achieve < 1 second response times.**

---

## Notes

**Why n8n?**
- **Visual & Intuitive:** Drag-and-drop workflow builder, perfect for learning ETL concepts
- **Free & Open Source:** No licensing costs, complete control
- **Extensive Integrations:** Native PostgreSQL and BigQuery support
- **Real-time Capabilities:** Webhooks for event-driven data pipelines
- **Educational Value:** Learn modern workflow automation used in industry
- **Team Collaboration:** Export/import workflows as JSON via GitHub
- **Error Handling:** Built-in retry logic and monitoring

**Project Philosophy:**
All tools selected are either:
- Free and open-source
- Offer free tiers suitable for educational projects
- Provide student credits or academic licenses
- Can be self-hosted at no cost

This ensures the project is feasible within a student budget while meeting all technical requirements and providing real-world, industry-relevant experience.

**Flexibility:**
This plan is adaptable and open to changes based on:
- Project requirements evolution
- Technical feasibility testing
- Team feedback and collaboration
- Instructor recommendations
- Best practices discovered during implementation

---

## Resources

### n8n Resources
- [n8n Documentation](https://docs.n8n.io/)
- [n8n Community Forum](https://community.n8n.io/)
- [n8n BigQuery Integration](https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.googlebigquery/)
- [n8n PostgreSQL Integration](https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.postgres/)
- [n8n Workflow Examples](https://n8n.io/workflows/)

### BigQuery Resources
- [Google BigQuery Sandbox (Free)](https://cloud.google.com/bigquery/docs/sandbox)
- [BigQuery Partitioning](https://cloud.google.com/bigquery/docs/partitioned-tables)
- [BigQuery Clustering](https://cloud.google.com/bigquery/docs/clustered-tables)
- [BigQuery Materialized Views](https://cloud.google.com/bigquery/docs/materialized-views-intro)
- [BigQuery Best Practices](https://cloud.google.com/bigquery/docs/best-practices)

### Additional Resources
- [GitHub Student Developer Pack](https://education.github.com/pack)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Mockaroo - Test Data Generator](https://www.mockaroo.com/)
- [Google Looker Studio](https://lookerstudio.google.com/)

### Learning Resources
- [Data Warehouse Concepts](https://cloud.google.com/architecture/data-warehouse)
- [Star Schema Design](https://en.wikipedia.org/wiki/Star_schema)
- [ETL Best Practices](https://www.stitchdata.com/resources/etl-best-practices/)

---

## Contact & Support

**Team:** TeamBA  
**Repository:** [data-warehouse-j4a-project-TeamBA](https://github.com/classroom/data-warehouse-j4a-project-TeamBA)

For questions, issues, or collaboration, please use GitHub Issues or contact team members directly.

