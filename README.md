# 🚀 Microsoft Fabric Medallion Architecture Project
<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/02e4661d-8dc6-4565-ba69-cf3c43ce3ddb" />



This repository contains an end-to-end data engineering project using **Microsoft Fabric**, demonstrating the implementation of the **Medallion Architecture** (Bronze, Silver, Gold) to process and analyze structured and unstructured data for a mid-sized retail business, **Shopping Mart**.

The project integrates Fabric Lakehouse, PySpark, and Power BI to build a modern data platform with scalable ingestion, transformation, and visualization pipelines.

---

## 🎯 Project Overview

The goal of this project is to simulate a robust data platform for **Shopping Mart** to unify sales, inventory, and social media/product review data. The outcome is a curated Gold layer that enables the business to gain actionable insights and optimize inventory management decisions.

### Architectural Layers (Medallion Pattern)

* **Bronze Layer:** Raw data ingestion (CSV/JSON). Data is kept "as-is" for full auditability.
* **Silver Layer:** Cleaned, validated, and integrated data (structured/unstructured). Focus on data quality.
* **Gold Layer:** Business-ready, aggregated data for dimensional modeling and direct analytics consumption.

### Key Components

* Microsoft Fabric Workspace
* Fabric Lakehouses (Bronze, Silver, Gold)
* PySpark Notebooks for complex transformations
* Power BI Semantic Model and Dashboards
* Master Orchestrator pipeline for end-to-end automation

---

## 🛠️ Data Ingestion & Transformation Pipeline

### 📥 Bronze Layer: Scalable Ingestion
* **Initial Manual Copy:** Simple ingestion of structured data (e.g., CSV) from a GitHub repository.
* **Metadata-Driven Pipeline:** Utilizes a **JSON metadata file**, **Lookup**, and **ForEach** activities to dynamically automate the ingestion of multiple data sources (structured & unstructured).

### ✨ Silver Layer: Cleaning & Validation
* **PySpark Transformations:** Applied for data cleaning, validation, and integration:
    * Null handling and precise type casting (e.g., string to timestamp).
    * Joining of structured data (orders, customers, products).
    * Conversion of raw unstructured **JSON** data into query-optimized **Parquet** format.
* **Storage Efficiency:** Shortcuts are used to reference Bronze data, preventing data duplication across layers.

### 🌟 Gold Layer: Aggregation & Consumption
* **Aggregation:** Data is aggregated for business KPIs:
    * Web engagement metrics by user action.
    * Social sentiment analysis.
    * Product review score aggregation.
* **Delta Lake:** All final tables are written as **Delta Lake tables** to ensure ACID compliance and enable Power BI's Direct Lake connectivity.

---

## 📊 Modeling & Visualization

### Semantic Model
* Designed using a **Star Schema** with robust relationships between fact and dimension tables.
* Includes a dedicated **Date Dimension Table** for comprehensive time-series analysis.

### Power BI Dashboard
* **KPI Cards:** Total Sales, Products Sold.
* **Slicers:** Interactive filters for Year, Month, Day, and Product Category.
* **Visualizations:** Key charts for Sales Trend, Top Products, Review Ratings, and Social Sentiment analysis.

---

## ⚙️ Pipeline Orchestration

The **Master Orchestrator pipeline** ensures the entire process runs reliably and sequentially:
1.  Structured Data Ingestion
2.  Unstructured Data Ingestion
3.  Silver Transformations Notebook
4.  Gold Transformations Notebook

* **Automation:** Scheduling and failure notifications are implemented for production readiness.

---

## 💻 Technologies Used

| Component | Technology | Role in Project |
| :--- | :--- | :--- |
| **Data Lake** | Microsoft Fabric Lakehouse | Unified storage for all Bronze/Silver/Gold layers (Delta Lake). |
| **Compute Engine** | PySpark | High-performance ETL/ELT transformations. |
| **Data Format** | Delta Lake | ACID compliance and optimized querying in the Gold layer. |
| **Orchestration** | Fabric Data Pipeline | Metadata-driven ingestion and master workflow automation. |
| **BI Tool** | Power BI | Data Modeling, Semantic Model, and visualization. |
| **Metadata** | JSON | Configuration for dynamic ingestion. |

---
