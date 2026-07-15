# Pharmacy-Sales-Analysis-Excel
European Pharmacy Sales Dataset 2026
# Pharmacy Sales Performance Analysis (Excel & Power Pivot)

## 🎯 Project Overview
This project delivers an interactive, enterprise-grade data analytics solution for a pharmacy chain using **Excel's advanced BI capabilities (Power Query & Power Pivot)**. Based on the **European Pharmacy Sales Dataset** from Kaggle, this analysis helps stakeholders monitor key retail metrics, optimize inventory, identify high-margin pharmaceutical categories, and evaluate regional branch performance.

---

## 🛠️ Tech Stack & BI Tools
* **Power Query (ETL):** Imported and cleaned the data tables, standardized date formats, verified data types, and eliminated duplicates/null values.
* **Power Pivot (Data Modeling):** Constructed a robust **Star Schema** with designated relationships.
* **DAX (Data Analysis Expressions):** Programmed key performance indicators (KPIs) to drive business decisions.
* **Excel Dashboards:** Created dynamic, interactive visual reports with automated filters.

---

## 📐 Data Model Structure (Star Schema)
To optimize performance, I established relationships between the central transaction table (**FactSales**) and the following dimension tables:
* **FactSales** ↔ **DimProduct** (linked via `ProductID` / `Product_ID`)
* **FactSales** ↔ **DimPharmacy** (linked via `StoreID` / `Store_ID`)
* **FactSales** ↔ **DimDate** (linked via `Date` / `DateKey`)

---

## 📊 Key KPIs & Business Metrics (DAX Measures)
These custom metrics were written in **Power Pivot** to calculate pharmacy performance without bloating the file size:
Total Cost := SUM(FactSales[Cost])
Total Profit := [Total Revenue] - [Total Cost]
Profit Margin % := DIVIDE([Total Profit], [Total Revenue], 0)
Average Basket Value := DIVIDE([Total Revenue], DISTINCTCOUNT(FactSales[InvoiceNumber]), 0)

📈 Dashboard Architecture
The dynamic Excel Dashboard consists of:

KPI Cards: Displaying Total Revenue, Total Profit, and Profit Margin % prominently.

Product Analysis:

A Bar Chart filtering the Top 5 selling drugs/products based on revenue.

A Column Chart highlighting the highest profit-generating medical categories.

Geographical & Branch Analysis: A Column Chart displaying sales performance mapped by region/city and categorized by store type (Urban vs. Rural).

Time-Series Analysis: A Line Chart tracking the monthly sales trend to identify seasonal spikes in drug consumption.

Interactive Slicers: Connected to all Pivot Tables to filter the entire dashboard by Year, Drug Category, and Region instantly.

📷 Dashboard & Data Model Preview
(Add your project screenshots here to showcase your work directly on GitHub)

1. Interactive Dashboard
2. Power Pivot Data Model (Star Schema)
💡 Key Business Takeaways
Operational Efficiency: Slicing the data by branch type reveals whether Urban or Rural pharmacies require different stock optimization plans.

Product Performance: Identifying the Top 5 drugs prevents critical stockouts of essential medicine while maximizing overall profit margins.

* **Total Revenue:** 
  ```dax
  Total Revenue := SUM(FactSales[Revenue])
