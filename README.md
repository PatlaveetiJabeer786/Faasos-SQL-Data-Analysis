# Faasos-SQL-Data-Analysis
A comprehensive SQL portfolio project focusing on data cleaning, customer behavior metrics, and delivery efficiency analytics for a food delivery brand.

# Faaso's SQL Data Analysis Portfolio Project

A Data Analytics project using SQL to extract actionable insights from a food delivery dataset. This project covers data cleaning, customer segmentation, and operational efficiency.

## 🚀 Project Overview (STAR Method)

### Situation
Faaso’s handles massive amounts of raw data regarding customer orders, driver pickups, and ingredient recipes. However, the data is often "dirty"—containing missing values, inconsistent 'NaN' strings, and hidden patterns that require systematic SQL analysis.

### Task
My objective was to clean the dataset and extract business-critical insights. Specifically, I aimed to identify peak travel times, the most popular roles (veg vs. non-veg), and driver efficiency (pickup intervals).

### Action
* **Data Cleaning:** Handled missing values in `cancellation` and `exclusion` columns using CTEs and Temporary Tables to replace dirty data with standard flags.
* **Feature Engineering:** Extracted specific features like Hour, Day, and Month from timestamps to enable time-series analysis.
* **Metric Calculation:**
    * Calculated average pickup time per driver using `DATEDIFF` and `ROW_NUMBER()`.
    * Identified peak order hours using `DATEPART`.
    * Tracked ingredient changes (extras vs. exclusions) using complex `CASE WHEN` logic.

### Result
* Successfully transformed a messy dataset into a structured format ready for reporting.
* Discovered that **Fridays** are the busiest days, and determined the average driver pickup window to be **[mention your calculated average] minutes**, helping optimize delivery logistics.

## 🛠️ Tools Used
* **Database:** SQL Server (SSMS)
* **Techniques:** CTEs, Window Functions, Temporary Tables, Joins, Date Functions.
