# 📊 Walmart Sales Analysis - Power BI Dashboard

A comprehensive Power BI data analysis project visualizing Walmart's sales performance, trends, and the impact of external factors across 45 stores from 2010 to 2012.

---

## 🚀 Project Overview
This dashboard provides deep insights into Walmart's weekly sales, distinguishing revenue streams between regular working days and holidays, while analyzing correlations with external economic and environmental factors such as temperature, fuel prices, and unemployment rates. It also features a dedicated investigation page to uncover the root causes behind yearly sales variances.

---

## 🖼️ Dashboard Screenshots

### 1. Main Dashboard - Performance & Trends Overview
![Main Dashboard](Screenshot%20for%20main%20dashboard%20of%20walmart%20sales.png)

### 2. Sales Investigation & Root Cause Analysis
![Sales Investigation](Screenshot%20for%20sales%20investigation%20dashboard.png)

### 3. Executive Summary & Key Insights
![Key Insights](Screenshot%20for%20key%20insight%20dashboard.png)

---

## 📈 Key Performance Indicators (KPIs) & Metrics
- **Total Sales:** $6.74bn
- **Average Weekly Sales:** $1.05M
- **Number of Stores:** 45
- **Working Day Sales:** $6.23bn
- **Holiday Sales:** $505.30M

---

## 🛠️ Data Transformation & Power Query
- **Conditional Column:** Added a custom conditional column in Power Query to map the `Holiday_Flag` values (`0` to **Workday** and `1` to **Holiday**) for better readability and filtering in the visuals.

---

## 📐 DAX Measures Used
Below are the core DAX measures created for this analysis:

```dax
-- Calculate total sales across all records
Total_Sales = SUM(Walmart_Sales[Weekly_Sales])

-- Calculate total sales specifically for regular working days
Working_Day_Sales = CALCULATE([Total_Sales], Walmart_Sales[Holiday_Flag] = 0)

-- Calculate total sales specifically for holiday periods
Holiday_Sales = CALCULATE([Total_Sales], Walmart_Sales[Holiday_Flag] = 1)

-- Count the total number of unique stores
Number_of_Stores = COUNT(Stores[Store])
```
---

## 💡 Key Insights & Findings

* **1. Working Days vs. Holidays:** 
  The vast majority of revenue ($6.23bn) is generated during regular working days, whereas holidays account for $505.30M.
  
* **2. Yearly Performance & Investigation:** 
  Peak sales were recorded in 2011 ($2.45bn), followed by 2010 ($2.29bn) and 2012 ($2.00bn). Although 2012 shows a lower total annual volume, monthly trend analysis and data completeness checks prove that 2012 sales closely matched (and at times outperformed) previous years—confirming that the annual drop was entirely driven by missing Q4 data records rather than an operational downturn.
  
* **3. Store-Level Performance:** 
  Revenue distribution is heavily polarized; specific top-performing branches (e.g., Stores 20, 4, 14) drive the bulk of sales, while bottom-performing branches require immediate operational focus and support[cite: 4].
  
* **4. External Factors:** 
  Scatter plots and correlation analysis indicate that external factors like temperature and fuel prices show minimal direct linear impact on total store sales within the observed range.
---

## 💻 Tech Stack & Tools
- **Microsoft Power BI** (Data Modeling, DAX, Power Query, Data Visualization)
- **Microsoft Excel** (Data Inspection & Preprocessing)
- **GitHub** (Version Control & Documentation)

---
## 📁 Repository Structure
```text
.
├── Walmart Sales Analysis Dashboard.pbix              # Main Power BI interactive dashboard file
├── Walmart_Sales.xlsx                                 # Original Dataset
├── walmart-main.png                                   # Overview of the main dashboard
├── walmart-investigation.png                          # Sales Investigation page view
├── walmart-insights.png                               # Executive summary & key insights view
└── README.md                                          # Project documentation and guide