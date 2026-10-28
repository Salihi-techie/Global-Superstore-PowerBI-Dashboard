# 📊 Global Superstore Executive Performance Dashboard (Power BI)

![Dashboard Preview](Dashboard_Screenshot.png)

## 📌 Project Overview
This project delivers an interactive, executive-ready Power BI dashboard created as part of **AnalystLab Africa Mission 02**. The dashboard analyzes global retail transaction data from the **Global Superstore** dataset, encompassing over **25,000 distinct orders** across international markets between 2011 and 2014.

The objective of this analytics solution is to provide C-suite decision-makers with actionable insights into revenue distribution, regional profitability, product category performance, and multi-year growth trends.

---

## 🎯 Executive Summary & KPI Overview
* **Total Sales:** $12.64M
* **Total Profit:** $1.47M
* **Total Orders:** 25,000 (25.0K)
* **Average Order Value (AOV):** $246.49
* **Profit Margin:** 11.61%

---

## 🛠️ Data Architecture & DAX Modeling

### 1. Data Cleaning & Transformation (Power Query)
* Verified and standardized data types across all 24 dataset columns.
* Handled missing spatial records by populating null values in `Postal Code` with `"N/A"`.
* Validated uniqueness on `Row ID` and `Order ID` to ensure no duplicate transaction entries distorted financial totals.

### 2. Key DAX Measures
The business calculations were modeled using explicit DAX measures:

```dax
// Total Revenue Generated
Total Sales = SUM('Global Superstore'[Sales])

// Cumulative Net Profit
Total Profit = SUM('Global Superstore'[Profit])

// Count of Unique Customer Transactions
Total Orders = DISTINCTCOUNT('Global Superstore'[Order ID])

// Average Sales Per Order
Average Sales = AVERAGE('Global Superstore'[Sales])

// Overall Net Profit Margin Protection
Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
