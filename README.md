# Microsoft-Fabric-ZedaFleet-Analysis-Project

---

# Zeda Fleet Analytics – End-to-End Gold Layer Project
## Solution Overview

We’re going to use Microsoft Fabric to build an end-to-end fleet analytics pipeline using the medallion architecture. This involves:

**Bronze Layer**: Collect raw operational data from ERP, IoT telemetry, and customer interactions.

**Silver Layer**: Transform it into clean, structured fleet datasets.

**Gold Layer**: Enrich with KPIs, financial metrics, and utilization measures.

**Data Factory**: Automate the entire process, ensuring fresh reporting daily.

---

## Business Case

Zeda Limited manages one of Southern Africa’s largest rental and leasing fleets. With operations spanning retail, corporate, and government clients, the business must balance:

Utilization Efficiency → ensuring vehicles generate revenue and minimizing idle time.

Cost Management → reducing maintenance and downtime costs that impact profitability.

Strategic Reporting → delivering insights to EXCO, GMs, OEMs, and NAAMSA for operational planning and compliance.

The data-driven fleet analytics initiative addresses these challenges by providing a single source of truth for performance tracking, cost optimization, and strategic decision-making.

---

## Medallion Architecture in Action

Let’s break down each layer of the pipeline:

### Bronze Layer (Raw Data Ingestion)

**What It Does**: Stores raw ERP extracts, rental logs, leasing contracts, maintenance events, and IoT telemetry.

**How To Do It**: Land CSV/JSON extracts and IoT feeds into the Fabric Lakehouse.

**Why It’s Important**: Preserves original operational data for audit and traceability.

### Silver Layer (Data Transformation)

**What It Does**: Cleans and structures the raw data into domain tables: customers, vehicles, rentals, contracts, maintenance, telemetry, and interactions.

**How To Do It**: Use PySpark + Delta tables for standardized schemas and consistent data quality.

**Why It’s Important**: Provides a trusted, structured foundation for analytics.

### Gold Layer (Data Enrichment)

**What It Does**: Enriches Silver data with KPIs and business-friendly views (e.g., vehicle_lifecycle, branch_revenue_summary, maintenance_financials, customer_interaction_summary).

**How To Do It**: Join domain tables, add derived fields like utilization_rate, cost_per_km, revenue_per_vehicle, and save as Delta views.

**Why It’s Important**: Creates ready-to-consume insights for reporting and analysis.

---

## Orchestration with Data Factory

**What It Does**: Automates ingestion, transformation, and enrichment.

**How To Do It**: Schedule Data Factory pipelines to refresh data daily.

**Why It’s Important**: Ensures leadership always has up-to-date insights.

---

## Executive Summary

**Utilization**: Economy and commercial vehicles deliver the highest usage, while premium vehicles show underutilization.

**Revenue Distribution**: Gauteng dominates revenue share, creating geographic dependency.

**Cost vs Profitability**: Maintenance costs rising faster than profits in older fleets.

**Customer Engagement**: Corporate clients generate the majority of leasing revenue but show low engagement in loyalty programs.

Insights Deep Dive

---

## Advanced Analysis

📈 **Change-over-Time**: Utilization trending downward post-peak season.

📊 **Cumulative Analysis**: Coastal branches lead YTD revenue growth.

⚖️ **Performance Analysis**: Strong negative correlation between downtime and profit margin.

🧩 **Part-to-Whole**: 5 branches contribute >60% of total profit.

🎯 **Segmentation**: Economy segment achieves the best utilization-to-revenue balance.

---

## Exploratory Analysis

**Cardinality**: Wide customer diversity, but top corporates dominate revenue.

**Date Exploration**: Telemetry gaps indicate IoT device under-reporting.

**Magnitude**: Downtime clustering in high-mileage fleets.

**Ranking**: Top 10 customers = ~40% of leasing revenue.

---

## Recommendations

**Fleet Mix**: Reallocate underutilized premium cars toward high-demand economy/commercial categories.

**Branch Diversification**: Reduce Gauteng dependency by strengthening coastal operations.

**Predictive Maintenance**: Use telemetry and service history to forecast failures and cut costs.

**Customer Loyalty**: Design tailored corporate retention programs.

**Data Coverage**: Enhance IoT telemetry adoption for full fleet visibility.

---

## Final Thoughts

By following this framework, Zeda Fleet builds a scalable, automated, and business-aligned analytics pipeline. Using Microsoft Fabric + Medallion Architecture, the company gains a single source of truth for fleet insights—supporting strategic planning, operational efficiency, and external compliance reporting.
