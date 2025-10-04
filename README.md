# 🛒 E-commerce Data Analysis with BigQuery

## 📌 Overview
I conducted an end-to-end data analysis project using **Google BigQuery**, a fully managed serverless data warehouse.  
The project focused on an **e-commerce dataset** containing millions of user session records from an online merchandise store.  
Using SQL, I explored the data, identified duplicates, and built queries to extract meaningful business insights about products, users, and traffic sources.

---

## 🎯 Objectives
- Access and explore a large-scale e-commerce dataset in BigQuery  
- Review dataset schema and metadata  
- Identify and handle duplicate rows  
- Write SQL queries to analyze traffic, visitors, and product performance  
- Derive actionable insights and recommendations  

---

## ⚙️ Setup
- Tools: **Google Cloud Platform → BigQuery**
- Languages: **SQL**
- Dataset size: ~21M+ rows (~5.6 GB)  

---

## 🔎 Data Exploration
- Used the **Schema tab** to inspect fields and data types  
- Reviewed **table metadata** to confirm record counts and storage size  
- Previewed rows to understand data distribution  
- Confirmed and removed duplicates using `GROUP BY` and `HAVING` logic  

---

## 🧾 Queries & Insights

### 1️⃣ Unique Visitors and Views
SELECT
  COUNT(*) AS product_views,
  COUNT(DISTINCT fullVisitorId) AS unique_visitors
FROM `data-to-insights.ecommerce.all_sessions`;

### Insight: High repeat engagement — total views far exceed unique visitors.

### 1️⃣ Unique Visitors and Views
SELECT
  COUNT(DISTINCT fullVisitorId) AS unique_visitors,
  channelGrouping
FROM `data-to-insights.ecommerce.all_sessions`
GROUP BY channelGrouping
ORDER BY channelGrouping DESC;
