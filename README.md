#  E-Commerce Sales & Customer Behavior Analysis

##  Project Overview
Understanding customer purchasing behavior, identifying profitable product lines, and predicting temporal demand shifts are critical for e-commerce profitability. This project conducts a comprehensive **Exploratory Data Analysis (EDA)** on a real-world online retail dataset to extract actionable business intelligence. 

The analysis identifies top revenue-driving products, seasonal sales patterns, price elasticity, geographic revenue distribution, and distinct customer purchasing cohorts to support data-driven inventory and marketing strategies.

##  Project Objectives
The analysis was guided by 10 core investigative questions:
1. Which products generate the highest sales?
2. Which countries contribute the most revenue?
3. What are the monthly/weekly/hourly sales trends?
4. Which products have the highest quantity sold?
5. What is the average order value?
6. Who are the most valuable customers?
7. Are there unusual transactions or outliers?
8. What percentage of transactions are cancelled?
9. Which products show increasing or declining demand?
10. Is there a relationship between product price and quantity purchased?

##  Dataset Information
* **Source:** [UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail)
* **Context:** Transactional data for a UK-based non-store online retail company selling unique all-occasion gifts.
* **Size:** 541,909 transactional records.
* **Features:** `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.

##  Tech Stack & Methodology
* **Language:** Python 3
* **Libraries:** Pandas (Data Manipulation), NumPy (Numerical Operations), Matplotlib & Seaborn (Data Visualization).
* **Data Preprocessing Pipeline:**
  * Cleaned missing `CustomerID` values to ensure accurate customer cohort analytics.
  * Extracted time-series dimensions (`YearMonth`, `DayOfWeek`, `Hour`) from `InvoiceDate`.
  * Engineered a `TotalPrice` metric (`Quantity` * `UnitPrice`).
  * Filtered out and separately analyzed cancelled transactions (invoices prefixed with 'C').

##  Key Exploratory Findings

###  Product Performance & Elasticity
* **Top Performers:** *"PAPER CRAFT, LITTLE BIRDIE"* and *"REGENCY CAKESTAND 3 TIER"* dominate both total revenue generated and physical quantity sold.
* **Price vs. Quantity Elasticity:** A classic negative price elasticity curve is present. Bulk wholesale orders (100+ units per item) are exclusively restricted to lower-cost inventory priced under $5.00.

###  Geographic Distribution
* While the **United Kingdom** completely dominates overall sales, the top international markets are the **Netherlands, EIRE (Ireland), Germany, and France**. 
* The Netherlands is uniquely dense, yielding massive average order values indicative of wholesale B2B distribution.

###  Temporal Demand Trends
* **Seasonality:** Demand scales aggressively entering Q4, peaking dramatically in **November** (holiday/gifting season), followed by a sharp drop in December.
* **Micro-Trends:** Purchasing activity is heavily front-loaded in the week. **Thursday** is the highest volume day, with a perfect bell curve of hourly activity peaking exactly at **12:00 PM (Noon)**.

###  Customer Cohorts & Health
* **Customer Value:** Scatter plots reveal two distinct groups: standard retail shoppers (1-5 invoices, <$2k lifetime spend) and a highly lucrative **B2B/Wholesale cohort** (15-40+ invoices, $6k-$10k+ lifetime spend).
* **Fulfillment Health:** Only **2.2%** of all recorded transactions are cancellations, indicating a highly healthy 97.8% transaction completion rate.

##  Strategic Business Recommendations

1. **Aggressive Q3 Inventory Stockpiling:** Warehouse allocations for top-performing craft and gifting items must be maximized by mid-October to prevent out-of-stock events during the massive November holiday spike.
2. **Temporal Marketing Optimization:** Re-weight digital ad spend and promotional email blasts to hit inboxes on **Thursday mornings at 10:00 AM** to capture the proven midday purchasing surge.
3. **Formalize a B2B VIP Program:** Since high-volume B2B customers drive a disproportionate amount of revenue but are highly sensitive to unit price, implement a formal wholesale tier with tiered bulk discounts to retain these crucial accounts.
4. **European Hub Expansion:** The massive average order values originating from the Netherlands and EIRE justify investigating localized European fulfillment hubs to reduce transit times and capitalize on existing wholesale demand.
```eof
