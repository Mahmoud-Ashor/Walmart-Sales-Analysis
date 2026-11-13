# 📊 Walmart Sales Analysis - Power BI Dashboard

A comprehensive Power BI data analysis project visualizing Walmart's sales performance, trends, and the impact of external factors across 45 stores from 2010 to 2012.

---

## 🚀 Project Overview
This dashboard provides deep insights into Walmart's weekly sales, distinguishing revenue streams between regular working days and holidays, while analyzing correlations with external economic and environmental factors such as temperature, fuel prices, and unemployment rates.

---

## 🖼️ Dashboard Preview

### 1. Main Dashboard Overview
![Walmart Dashboard](Screenshot%20For%20Walmart%20Dashboard.png)

### 2. Key Insights & Analysis
![Key Insights](Screenshot%20For%20Key%20Insights%20After%20Analysis.png)


---

## 📈 Key Performance Indicators (KPIs) & Metrics
* **Total Sales:** $6.74bn.
* **Average Weekly Sales:** $1.05M.
* **Number of Stores:** 45.
* **Working Day Sales:** $6.23bn.
* **Holiday Sales:** $505.30M.

---

## 🛠️ Data Transformation & Power Query
* **Conditional Column:** Added a custom conditional column in Power Query to map the `Holiday_Flag` values (`0` to **Workday** and `1` to **Holiday** for better readability and filtering in the visuals.

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

💡 Key Insights

1.Working Days vs. Holidays: The vast majority of revenue ($6.23bn) is generated during regular working days, whereas holidays account for $505.30M.  
2.Yearly Performance: Peak sales were recorded in 2011 ($2.45bn), followed by 2010 ($2.29bn) and 2012 ($2.00bn).  
3.External Factors (Scatter Plots):
Positive upward trends indicate that higher temperatures and fuel prices align with higher overall monthly sales volumes.  
Unemployment rates show a relatively flat trend, suggesting minimal direct linear impact on total store sales within the observed range.


💻 Tech Stack & Tools
Microsoft Power BI (Data Modeling, DAX, Power Query, Data Visualization).
GitHub (Version Control & Documentation).

### 📂 Repository Structure

```text
.
├── Walmart Sales Analysis Dashboard.pbix         # Main Power BI interactive dashboard file
├── Walmart_Sales.xlsx                            # Original Dataset
├── Screenshot For Walmart Dashboard.png          # Overview of the main dashboard
├── Screenshot For Key Insights After Analysis.png # Detailed key insights view
└── README.md                                     # Project documentation and guide