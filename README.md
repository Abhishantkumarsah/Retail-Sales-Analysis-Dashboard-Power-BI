# 📊 Retail Sales Analysis Dashboard | Power BI

## 📌 Project Overview

This project focuses on analyzing retail transaction data using **Microsoft Power BI** to understand sales performance, product category trends, payment preferences, and transaction patterns.

The objective is to transform transaction data into an interactive dashboard that helps users monitor key performance indicators (KPIs), compare sales across categories and channels, and identify meaningful business insights.

The project builds on data cleaning and exploratory data analysis (EDA) performed using Python and demonstrates the application of Power BI, DAX, data modeling, and data visualization in a retail analytics scenario.

## 🎯 Business Objectives

* Analyze overall recorded sales performance.
* Monitor transaction volume and quantity sold.
* Identify top-performing product categories.
* Compare online and in-store sales.
* Understand customer payment preferences.
* Analyze monthly sales trends.
* Compare recorded sales by discount status.
* Investigate data quality issues and potential anomalies.
* Support data-driven business decisions through interactive visualizations.

## 🛠️ Tools & Technologies

* **Microsoft Power BI Desktop** — Dashboard development
* **Power Query** — Data transformation and preparation
* **DAX** — Measures and calculations
* **Python** — Data cleaning and exploratory analysis
* **Pandas & NumPy** — Data manipulation and statistical analysis
* **Matplotlib & Seaborn** — Exploratory data visualization
* **Jupyter Notebook** — Python analysis
* **GitHub** — Project documentation and version control

## 📂 Dataset Description

The dataset contains retail transaction records with information about customers, product categories, prices, quantities, transaction amounts, payment methods, sales channels, and transaction dates.

### Dataset Summary

| Metric                 | Details                     |
| ---------------------- | --------------------------- |
| Total Records          | 12,575                      |
| Total Columns          | 11                          |
| Unique Transaction IDs | 12,575                      |
| Unique Customer IDs    | 25                          |
| Product Categories     | 8                           |
| Payment Methods        | 3                           |
| Sales Channels         | 2                           |
| Date Range             | January 2022 – January 2025 |

### Dataset Columns

| Column           | Description                               |
| ---------------- | ----------------------------------------- |
| Transaction ID   | Unique transaction identifier             |
| Customer ID      | Customer identifier                       |
| Category         | Product category                          |
| Item             | Product or item description               |
| Price Per Unit   | Price of an individual item               |
| Quantity         | Number of units purchased                 |
| Total Spent      | Recorded transaction amount               |
| Payment Method   | Payment method used                       |
| Location         | Sales channel, such as Online or In-store |
| Transaction Date | Date of the transaction                   |
| Discount Applied | Indicates whether a discount was applied  |

*Note: The dataset contains missing values in several columns. Individual calculations may therefore use different numbers of valid observations.*

## 🔄 Project Workflow

### 1. Data Cleaning and Preparation

The initial stage focused on reviewing and preparing the transaction dataset.

Key activities included:

* Examining the dataset structure and column data types.
* Checking missing values and duplicate records.
* Reviewing numerical columns and transaction information.
* Investigating data quality issues.
* Preparing the dataset for exploratory analysis and dashboard development.

### 2. Exploratory Data Analysis (EDA)

Python was used to explore the dataset and identify initial patterns.

The analysis included:

* Descriptive statistics.
* Product category analysis.
* Payment method analysis.
* Online versus in-store sales comparisons.
* Monthly sales trend analysis.
* Correlation analysis.
* Potential outlier investigation.
* Missing-value assessment.
* Transaction amount consistency checks.

### 3. Power BI Dashboard Development

The prepared dataset is used to develop an interactive dashboard.

Planned dashboard components include:

* KPI cards for overall performance.
* A monthly sales trend line chart.
* A product category sales comparison.
* An online versus in-store sales comparison.
* A payment method analysis.
* A discount status comparison.
* Interactive slicers for filtering the results.

## 📈 Dashboard Preview

The dashboard screenshot will be added here after the Power BI report is completed.


![Retail Sales Analysis Dashboard]("D:\DataAnalyst\swynexIntern\Task1\retail_salesd_AnalysisDashboard.png")

## 📊 Key Performance Indicators (KPIs)

The dashboard is designed to display the following KPIs:

| KPI                       | Description                                             |
| ------------------------- | ------------------------------------------------------- |
| Total Sales               | Sum of available recorded transaction amounts           |
| Total Transactions        | Number of distinct transaction IDs                      |
| Total Quantity Sold       | Sum of available quantity values                        |
| Average Transaction Value | Average of available transaction amounts                |
| Unique Customers          | Number of distinct customer IDs                         |
| Missing Sales Amounts     | Number of records without a recorded transaction amount |
| Missing Discount Status   | Number of records without discount status information   |

These metrics provide an overview of transaction activity and help users investigate business performance.

## 🧮 DAX Measures

The following DAX measures can be used to calculate the dashboard KPIs.


### 1. Total Sales

```dax
Total Sales =
SUM('cleaning_review'[Total Spent])
```

Calculates the total of available recorded transaction amounts.

### 2. Total Transactions

```dax
Total Transactions =
DISTINCTCOUNT('cleaning_review'[Transaction ID])
```

Calculates the number of distinct transaction IDs.

### 3. Total Quantity

```dax
Total Quantity =
SUM('cleaning_review'[Quantity])
```

Calculates the total quantity across available observations.

### 4. Average Transaction Value

```dax
Average Transaction Value =
AVERAGE('cleaning_review'[Total Spent])
```

Calculates the average recorded transaction amount.

### 5. Unique Customers

```dax
Unique Customers =
DISTINCTCOUNT('cleaning_review'[Customer ID])
```

Calculates the number of distinct customer IDs.

### 6. Missing Sales Amounts

```dax
Missing Sales Amounts =
CALCULATE(
    COUNTROWS('cleaning_review'),
    ISBLANK('cleaning_review'[Total Spent])
)
```

Counts records with missing transaction amounts.

### 7. Missing Discount Status

```dax
Missing Discount Status =
CALCULATE(
    COUNTROWS('cleaning_review'),
    ISBLANK('cleaning_review'[Discount Applied])
)
```

Counts records where discount status is missing.

*The missing-value measures depend on how the columns are typed and imported into Power BI. Verify their results against the source dataset.*

## 📉 Dashboard Visualizations

The report is designed to include the following visualizations.

| Visualization                  | Business Question                                         |
| ------------------------------ | --------------------------------------------------------- |
| KPI Cards                      | What is the overall transaction performance?              |
| Monthly Sales Trend            | How do recorded sales change over time?                   |
| Sales by Category              | Which product categories have the highest recorded sales? |
| Sales by Channel               | How do online and in-store sales compare?                 |
| Transactions by Payment Method | Which payment methods are most frequently used?           |
| Sales by Discount Status       | How do recorded sales differ across discount statuses?    |

### Interactive Filters

The dashboard is designed to include slicers for:

* Transaction Date
* Product Category
* Sales Channel
* Payment Method

These filters allow users to explore different parts of the dataset without creating separate reports for each category.

## 💡 Preliminary Business Insights

The following findings were identified during the earlier Python analysis and can be used as reference points when validating the Power BI dashboard.

### 1. Product Category Performance

The Butchers category recorded approximately 208,118 in sales, while Milk Products recorded approximately 180,112.

**Business implication:** Investigating product demand, pricing, inventory availability, and profit margins may help explain differences in category performance.

### 2. Payment Method Preferences

Cash was the most frequently recorded payment method, with approximately 4,310 transactions.

**Business implication:** Supporting multiple payment methods can help accommodate different customer preferences.

### 3. Online vs. In-Store Sales

Online transactions generated approximately 791,401 in recorded sales, compared with approximately 760,670 for in-store transactions.

**Business implication:** The online channel may offer opportunities for further growth, subject to an evaluation of operating costs and profitability.

### 4. Monthly Sales Variation

January 2022 recorded approximately 52,911.50 in sales. January 2025 recorded approximately 25,548.50.

However, January 2025 contains data only through January 18.

**Business implication:** Comparisons should account for incomplete reporting periods, and unusually high or low values should be investigated before conclusions are drawn.

### 5. Transaction Value Distribution

The average recorded transaction value was approximately 129.65, while the median was approximately 108.50.

**Business implication:** Investigating the distribution can help explain typical purchasing behavior and determine whether relatively large transactions influence the average.

### 6. Data Quality

The dataset contains missing values, particularly in the `Discount Applied` column. The available records also allow transaction amount calculations to be checked for arithmetic consistency.

**Business implication:** Improving data completeness and investigating missing information can increase confidence in business reporting.


## ⚠️ Data Quality Considerations

Several limitations should be considered when interpreting the dashboard.

* Some transactions have missing prices, quantities, item descriptions, or total amounts.
* Discount status is missing for a substantial number of records.
* Missing transaction amounts are excluded from the sum of recorded sales.
* Missing quantities are excluded from the total quantity calculation.
* January 2025 is a partial reporting period.
* Statistical outliers should be investigated rather than automatically removed.
* The dataset contains only 25 unique customer IDs, which limits the generalizability of customer-level conclusions.
* Recorded sales do not establish profitability because product costs and margins are unavailable.
* Differences between discount groups do not establish that discounts cause changes in sales.


## 🚀 Future Improvements

Potential extensions to this project include:

* Developing a dedicated customer analysis page.
* Comparing sales across years and quarters.
* Analyzing average transaction values by category.
* Investigating discount effectiveness after addressing missing data.
* Performing customer purchase frequency and retention analysis.
* Adding additional data quality indicators.
* Developing automated reporting workflows.
* Integrating additional business data to investigate profitability.

## 👨‍💻 Skills Demonstrated

* Data Cleaning and Preparation
* Exploratory Data Analysis
* Power Query
* DAX Measures
* Data Modeling
* KPI Development
* Data Visualization
* Time-Series Analysis
* Correlation Analysis
* Business Insight Generation
* Analytical Thinking
* GitHub Documentation

## 👤 Author

**Abhishant Kumar**

Aspiring Data Analyst | Python | SQL | Excel | Power BI

This project demonstrates my ongoing learning in data analytics, from preparing transaction data to exploring business patterns and developing interactive reports.

---

