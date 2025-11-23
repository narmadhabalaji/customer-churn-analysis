# 🛒 E-Commerce Customer Churn Analysis 

## Table of Contents
- Project Overview
- Problem Statement
- Dataset
- Tools & Technologies Used
- Data Cleaning
- Data Transformation
- Key Metrics
- Insights
- How to Run

## 📌 Project Overview
Customer churn is a critical problem in the e-commerce industry, where retaining customers is far more cost-effective than acquiring new ones.  

This project analyzes real customer behavioral data using SQL to:

- Understand what drives churn  
- Identify patterns across payment modes, complaints, tenure, and order habits  
- Provide insights that can help shape better retention strategies

---

## 🎯 Problem Statement
Businesses often face difficulty predicting which customers are likely to stop using their services.  

This project explores customer transaction history and demographic attributes to:

- Classify churned and active customers  
- Examine the impact of complaints, payment mode, and usage behavior  
- Reveal insights that support strategic decision-making

---

## 📁 Dataset
The dataset includes customer details such as:

- Customer ID  
- Tenure  
- Order counts  
- Cashback  
- Complaints  
- Preferred payment mode  
- Warehouse distance  
- Device usage  
- Monthly activity  
- Churn status

Dataset was provided as part of the capstone project.

---

## 🧰 Tools & Technologies Used
- **SQL**
- **MySQL Workbench**

---

## 🧹 Data Cleaning

### Missing Value Handling
- **Mean imputation**
  - WarehouseToHome  
  - HourSpentOnApp  
  - OrderAmountHikeFromLastYear  
  - DaySinceLastOrder

- **Mode imputation**
  - Tenure  
  - CouponUsed  
  - OrderCount

### Outlier Handling
- Removed rows where `WarehouseToHome > 100`

### Inconsistent Value Fixes
- Standardized categories:
  - “Phone” → “Mobile Phone”
  - “Mobile” (in category) → “Mobile Phone”
  - “COD” → “Cash on Delivery”
  - “CC” → “Credit Card”

---

## 🔁 Data Transformation

### Column Renaming
- `PreferedOrderCat` → `PreferredOrderCat`  
- `HourSpendOnApp` → `HoursSpentOnApp`

### New Columns Created
- `ComplaintReceived`  
  - `"Yes"` if `Complain = 1` else `"No"`

- `ChurnStatus`  
  - `"Churned"` if `Churn = 1` else `"Active"`

### Dropped Columns
- `Churn`  
- `Complain`

---

## 📊 Key Metrics (Actual Results from SQL Execution)

### 📌 Overall Customer Count

| Metric | Value |
|---|---|
| Total Customers | **5,628** |
| Active Customers | **4,680** |
| Churned Customers | **948** |
| Churn Rate | **16.83%** |

---

### 📌 Churn Behavior Insights

| Metric | Value |
|---|---|
| Avg Tenure of Churned Customers | **3.18 months** |
| Total Cashback Paid to Churned Customers | **152,030** |
| % of Churned Customers Who Complained | **53.59%** |

---

### 📌 Complaint Distribution by Gender

| Gender | Count |
|---|---|
| Female | 690 |
| Male | 914 |

---

### 📌 City Tier with Highest Churn
- **City Tier-3 – 150 customers**

---

### 📌 Most Used Payment Method (Active Customers)
- **Debit Card – 1,956 customers**

---

## 🧠 Business Insights

- **Complaints strongly correlate with churn**, with over half of churned users having previously complained.
- **Early lifecycle churn is high**, with average churn tenure only **3.18 months**, indicating customer drop-off within early months.
- **Tier-3 cities show the highest churn**, suggesting product, logistics, or service satisfaction issues in those locations.
- **Debit card users contribute the most to the active customer base**, indicating strong card-based usage.
- High cashback usage among churned customers suggests that **cashback alone may not be enough to retain users**.

---

## 🧪 Example Analysis Queries Performed

- Total churn and active customer count  
- Average tenure and cashback of churned customers  
- Complaint percentages  
- Satisfaction distribution  
- City-wise churn segmentation  
- Payment mode preferences  
- Device usage analysis  
- Order patterns and joined tables

---

## ▶️ How to Run the Project

1. Install MySQL Workbench 8.0 (or compatible SQL environment)
2. Create a database:

   ```sql
   CREATE DATABASE ecomm;
3. Import the provided SQL file ([E-Commerce Customer Churn Analysis](https://github.com/narmadhabalaji/customer-churn-analysis/blob/main/E-Commerce%20Customer%20Churn%20Analysis.sql))
4. Run the query blocks step-by-step

---

This project is implemented entirely in **one SQL file**, including:

- Database setup  
- Data loading  
- Data cleaning  
- Data transformation  
- Exploratory data analysis (EDA) queries
  
---
