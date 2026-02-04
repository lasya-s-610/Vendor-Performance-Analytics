# 📦 Vendor Performance & Inventory Analytics

## 📌 Project Overview
This project focuses on analyzing vendor performance and inventory efficiency using transactional sales data.  
The objective is to identify profitability drivers, high-risk vendors, and low-rotation inventory to support data-driven business decisions.

The workflow combines **MySQL** for data processing, **Python** for analysis, and **Power BI** for visualization., starting from raw data ingestion into a relational database and ending with dashboard-ready insights.

---

## 🎯 Business Problems
- Which vendors generate **high profit but low sales** (growth opportunities)?
- Which vendors drive **high sales but low margins** (pricing or cost risk)?
- How much **capital is locked in unsold inventory**, and who contributes most?
- Which vendors need **strategic intervention vs monitoring**?

---

## 📂 Data Description
The dataset consists of large transactional retail records including:
- Vendor, brand, and item-level identifiers  
- Purchase and sales quantities  
- Purchase price, actual selling price, freight cost, excise tax  
- Inventory movement indicators  

Raw data was ingested from CSV files and transformed into analytical tables suitable for aggregation and analysis.

---

## 🧱 Data Pipeline
### 1. Data Ingestion
- Ingested large transactional CSV datasets into MySQL using Python.
- Handled large file sizes during ingestion to ensure reliable database loading
  
📓 Notebook: `VendorPerformance_ingestion.ipynb`

---

### 2. SQL Querying & Feature Engineering
- Executed SQL queries involving joins, filters, and aggregations to create a final analysis-ready dataset.
- Loaded SQL query results into Python DataFrames.
- Derived additional business metrics such as:
  - Profit Margin
  - Freight Ratio
  - Inventory Turnover
  - Vendor Dependency indicators

📓 Notebook: `VendorPerformance_SQLAnalysis.ipynb`

---
### 3. Exploratory Data Analysis & Business Insights
- Performed exploratory data analysis on vendor and inventory performance.
- Identified:
  - Low-margin and high-risk vendors
  - Low-rotation and unsold inventory
  - Profitability vs sales volume trade-offs
- Visualized trends and patterns to support analytical conclusions.

📓 Notebook: `VendorPerformance_PythonAnalysis.ipynb`

---

## 📈 Analytical Approach
- Built aggregated vendor and brand performance tables using SQL (CTEs, joins)
- Segmented vendors using **percentile-based thresholds** on sales and profit margin
- Classified vendors into:
  - High Sales – Low Margin  
  - Low Sales – High Margin  
  - Low Sales – Low Margin  
- Visualized trade-offs using **scatter plots with threshold reference lines**

Negative profit-margin entries were retained for overall correlation analysis and excluded only during targeted vendor segmentation to avoid distortion.

---

## 📱 Dashboard 
 
(VendorPerformance_dashboard.png)

---

## 🧰 Tech Stack
- **Database:** MySQL  
- **Analysis & Processing:** Python (Pandas, Matplotlib, Seaborn)   
- **Visualization:** Power BI
- **Tools:** Jupyter Notebook 

---

## 💡 Key Insights
- A limited number of vendors contributed heavily to revenue, increasing dependency risk.
- Several items showed high inventory value but low sales movement.
- High sales volume did not always correlate with high profitability.

---


## 🎯 Business Impact
This analysis supports:
- Targeted vendor renegotiation strategies  
- Inventory liquidation and optimization planning  
- Improved vendor prioritization  
- Reduction in capital lock-in due to slow-moving stock  

---


## Future Enhancements
-  Interactive Power BI dashboard for stakeholder reporting  
- Time-based vendor trend analysis 
- Automate ingestion and SQL execution using scheduled pipelines
