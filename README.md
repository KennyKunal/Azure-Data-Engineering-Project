# Grocery Data Engineering Pipeline

> 🚧 **Status:** Work in Progress

## Overview

This project is an end-to-end Azure Data Engineering pipeline that collects grocery product data from multiple e-commerce platforms, enriches the data using Google's Gemini API, and transforms it into analytics-ready datasets following the Medallion (Bronze, Silver, Gold) architecture.

The goal is to simulate a production-grade data engineering workflow by combining web scraping, AI-powered data enrichment, scalable data processing, and cloud-based analytics.

---

## Current Progress

### ✅ Completed

* Amazon Fresh web scraper
* BigBasket web scraper
* Multi-source product data extraction

The current scrapers extract information such as:

* Product Name
* Brand
* Price
* Discount
* Product URL
* Ratings (where available)
* Product Images
* Category
* Additional product metadata

---

## Planned Data Pipeline

```text
                  Amazon Fresh          BigBasket
                        │                  │
                        └────── Python Web Scrapers ──────┐
                                                          │
                                                          ▼
                                           Raw Product Information
                                                          │
                                                          ▼
                                         Gemini API Enrichment
                                                          │
                 ┌──────────────────────────────────────────────────────┐
                 │ Enriched Product Information                         │
                 │ • Macronutrients (Protein, Carbs, Fat)              │
                 │ • Calories                                          │
                 │ • Ingredients                                       │
                 │ • Product Category                                  │
                 │ • Dietary Labels (Veg, Vegan, Gluten-Free, etc.)    │
                 │ • Health Score (Future)                             │
                 │ • Product Summary                                   │
                 └──────────────────────────────────────────────────────┘
                                                          │
                                                          ▼
                                      Azure Data Lake (Bronze Layer)
                                                          │
                                                          ▼
                                         Azure Databricks (PySpark)
                                                          │
                                 Data Cleaning & Standardization
                                                          │
                                                          ▼
                                             Silver Delta Tables
                                                          │
                                     Business Transformations
                                                          │
                                                          ▼
                                              Gold Data Model
                                                          │
                                                          ▼
                                              Power BI Dashboard
```

---

## Tech Stack

* Python
* Selenium / Playwright
* Google Gemini API
* Azure Data Lake Storage Gen2
* Azure Databricks
* PySpark
* Delta Lake
* Azure Data Factory
* SQL
* Power BI
* Git & GitHub

---

## Gemini API Enrichment

After the scraping stage, each product is enriched using the Gemini API to generate structured nutritional and product metadata.

Examples of enriched attributes include:

* Protein
* Carbohydrates
* Fat
* Calories
* Fiber
* Sugar
* Serving Size
* Ingredients
* Product Category
* Dietary Information
* Product Description
* Health Tags
* Additional product insights

This enrichment step improves data quality and enables richer downstream analytics.

---

## Development Roadmap

### Phase 1 – Data Collection ✅

* [x] Amazon Fresh scraper
* [x] BigBasket scraper
* [ ] Add more grocery websites
* [ ] Configurable scraping framework

### Phase 2 – AI Data Enrichment

* [ ] Integrate Gemini API
* [ ] Enrich products with nutritional information
* [ ] Validate and standardize AI-generated fields
* [ ] Store enriched raw data

### Phase 3 – Data Lake

* [ ] Store raw scraped data in Azure Data Lake (Bronze)
* [ ] Store enriched product data
* [ ] Partition data by ingestion date
* [ ] Build Azure Data Factory ingestion pipelines

### Phase 4 – Data Transformation (Databricks)

* [ ] PySpark transformation pipeline
* [ ] Remove duplicates
* [ ] Handle missing values
* [ ] Normalize brands and categories
* [ ] Standardize units
* [ ] Data quality validation
* [ ] Create Delta tables

### Phase 5 – Data Modeling

* [ ] Build Silver layer
* [ ] Build Gold layer
* [ ] Create fact and dimension tables
* [ ] Track historical price changes
* [ ] Implement incremental data loading

### Phase 6 – Analytics

* [ ] Price comparison across retailers
* [ ] Brand analysis
* [ ] Nutritional comparison
* [ ] Best protein per ₹
* [ ] Product category insights
* [ ] Daily price trend analysis
* [ ] Interactive Power BI dashboard

### Phase 7 – Production Features

* [ ] Pipeline orchestration with Azure Data Factory
* [ ] Logging and monitoring
* [ ] Error handling
* [ ] Data quality reports
* [ ] Parameterized pipelines
* [ ] CI/CD with GitHub Actions

---

## Project Goals

* Build a production-style Azure Data Engineering project
* Demonstrate end-to-end ETL development
* Combine web scraping with AI-powered data enrichment
* Implement the Medallion (Bronze, Silver, Gold) architecture
* Process data efficiently using PySpark and Databricks
* Build analytics-ready datasets for reporting
* Showcase modern cloud data engineering practices

---

## Repository Status

This project is actively under development. Features will be implemented incrementally, with each milestone documented as the pipeline evolves.
