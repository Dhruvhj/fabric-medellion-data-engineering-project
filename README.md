Microsoft Fabric Medallion Architecture Project

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/8065af18-f580-49d0-b0df-fc6edae7e173" />


This repository contains an end-to-end data engineering project using Microsoft Fabric, demonstrating the implementation of the Medallion Architecture (Bronze, Silver, Gold) to process and analyze structured and unstructured data for a mid-sized retail business, Shopping Mart.

The project integrates Fabric Lakehouse, PySpark, and Power BI to build a modern data platform with scalable ingestion, transformation, and visualization pipelines.

Project Overview

The goal of this project is to simulate a data platform for Shopping Mart to analyze sales, inventory, and social media/product review data to gain actionable insights and optimize inventory management.

Architecture

The project follows the Medallion Architecture:

Bronze Layer – Raw data ingestion (CSV/JSON).

Silver Layer – Cleaned and validated data (structured/unstructured).

Gold Layer – Business-ready aggregated data for analytics.

Key Components:

Microsoft Fabric Workspace

Fabric Lakehouses (Bronze, Silver, Gold)

PySpark Notebooks for transformations

Power BI semantic model and dashboards

Master Orchestrator pipeline for end-to-end automation

Data Ingestion
Bronze Layer

Initial Manual Copy – Simple CSV ingestion from GitHub repository.

Metadata-Driven Pipeline – Uses JSON metadata, Lookup, and ForEach activities to automate ingestion of multiple files (structured & unstructured).

Silver Layer

PySpark Transformations: Cleaning, validation, and integration.

Null handling, type casting, and joining structured data.

Converting unstructured JSON to Parquet for distributed storage.

Silver shortcuts reference Bronze data without duplication.

Gold Layer

Aggregation of Silver-layer data for business KPIs:

Web engagement metrics

Social sentiment analysis

Product review aggregation

Delta Lake tables created for Power BI direct connectivity.

Modeling & Visualization

Semantic Model: Relationships between fact and dimension tables.

Date Dimension Table for time-series analysis.

Power BI Dashboard:

KPI Cards: Total Sales, Products Sold

Slicers: Year, Month, Day, Product Category

Visualizations: Sales Trend, Top Products, Review Ratings, Social Sentiment

Pipeline Orchestration

Master Orchestrator runs the full end-to-end pipeline:

Structured Data Ingestion

Unstructured Data Ingestion

Silver Transformations Notebook

Gold Transformations Notebook

Scheduling and failure notifications implemented for automation.

Technologies Used

Microsoft Fabric Lakehouse

PySpark (Data Transformations)

Delta Lake (Gold Layer)

Power BI (Semantic Model & Dashboard)

JSON (Metadata-driven ingestion)
