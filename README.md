<div align="center">

# 🛒 Olist E-Commerce Power BI Dashboard

### End-to-End Business Intelligence for a Brazilian E-Commerce Giant

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)](https://learn.microsoft.com/en-us/dax/)
[![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

> A 6-page interactive Power BI report transforming 100K+ raw orders into actionable insights across Sales, Customers, Products, Sellers, Logistics, and RFM Segmentation.

</div>

---

## 📸 Dashboard Preview

### 1 · Sales Analysis
![Sales Analysis](Screenshots/01-sales-analysis.png)

### 2 · Customer Analysis
![Customer Analysis](Screenshots/02-customer-analysis.png)

### 3 · Product & Sales Analysis
![Product and Sales Analysis](Screenshots/03-product-sales-analysis.png)

### 4 · Seller Analysis
![Seller Analysis](Screenshots/04-seller-analysis.png)

### 5 · Delivery Delay Analysis
![Delivery Delay Analysis](Screenshots/05-delivery-delay-analysis.png)

### 6 · RFM Segmentation
![RFM Segmentation](Screenshots/06-rfm-segmentation.png)

---

## 📊 Key Business Metrics

| Metric | Value |
|---|---|
| 💰 Total Revenue | **$15M** |
| 📦 Total Orders | **96K** |
| 🛍️ Average Order Value | **~$159** |
| 👤 Total Customers | **99K** |
| ⭐ Average Review Score | **3.84 / 5** |
| 🚚 On-Time Delivery Rate | **91.89%** |
| ⏱️ Average Delivery Time | **12.50 days** |
| 📅 Time Period Covered | **Sep 2016 – Aug 2018** |

---

## 📋 Report Pages at a Glance

| # | Page | What You'll Find |
|---|---|---|
| 1 | **Sales Analysis** | Total Revenue, Orders & AOV KPIs · Top Product Categories · Revenue by State (Map) · Monthly Revenue Trend · Order Status Breakdown |
| 2 | **Customer Analysis** | Customer Growth Trend · Top Customer Cities (Treemap) · Review Scores by State · Customers by State Distribution |
| 3 | **Product & Sales Analysis** | Top Categories by Revenue · Top Sellers · Monthly Order Trends · Category-level drill-through |
| 4 | **Seller Analysis** | Seller KPIs · Revenue Trend · Geographic Distribution · Seller Performance Ranking |
| 5 | **Delivery Delay Analysis** | Avg Delivery Time · Avg Delay Days · On-Time Rate · Delivery Time Trend · Delay by State |
| 6 | **RFM Segmentation** | Total vs One-Time vs Repeat Customers · Top Customers Table · RFM Scatter Plot · Customer Segmentation |

---

## 🔍 Business Questions Answered

- 📈 **Which product categories and states drive the most revenue?**
- 🗺️ **How does revenue and customer base distribute across Brazil's 27 states?**
- 🚚 **Where are delivery delays concentrated, and how has on-time delivery improved over time?**
- 👥 **Who are the high-value customers (RFM Champions vs. One-Time buyers)?**
- 🏆 **Which sellers generate the most revenue and have the best performance?**
- ⭐ **How do customer review scores correlate with delivery performance?**

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| **Power BI Desktop** | Report authoring, data modeling, interactive visuals |
| **DAX** | Custom KPI measures, time intelligence, RFM scoring logic |
| **Power Query (M)** | Data cleaning, transformation, column type corrections |
| **Olist Dataset (Kaggle)** | 9 relational CSV files · ~100K orders · 2016–2018 |

---

## 🗂️ Data Model

The report is built on **9 relational tables** from the Olist Brazilian E-Commerce dataset:

```
olist_orders_dataset          ← core fact table
olist_order_items_dataset     ← line-item revenue & seller linkage
olist_order_payments_dataset  ← payment methods & installments
olist_order_reviews_dataset   ← review scores & comments
olist_customers_dataset       ← customer geography
olist_sellers_dataset         ← seller geography
olist_products_dataset        ← product metadata
product_category_name_translation ← Portuguese → English mapping
olist_geolocation_dataset     ← ZIP-code lat/long for maps
```

---

## ⚙️ DAX Highlights

```dax
-- RFM Customer Classification
Customer Type =
VAR freq = CALCULATE(COUNTROWS(olist_orders_dataset), ALLEXCEPT(RFM_Table, RFM_Table[customer_id]))
RETURN IF(freq > 1, "Repeat Customer", "One-Time Customer")

-- On-Time Delivery Rate
On Time Delivery Rate =
DIVIDE(
    CALCULATE(COUNTROWS(olist_orders_dataset), olist_orders_dataset[delivery_status] = "On Time"),
    COUNTROWS(olist_orders_dataset)
) * 100

-- Average Order Value
AOV = DIVIDE([Total Revenue], [Total Orders])
```

---

## 🚀 How to Use

1. **Clone or download** this repository
   ```bash
   git clone https://github.com/ritscode17/olist_powerbi_dashboard.git
   ```

2. **Open** `olist_powerbi_dashboard.pbix` in **Power BI Desktop** (free download from Microsoft)

3. **Refresh data** — if prompted, update the data source path to where you saved the Kaggle CSVs

4. **Explore interactively** using the slicers:
   - 📅 Date Range slider
   - 🗺️ Customer State filter
   - 📦 Order Status filter

> **💡 Tip:** The map visual uses Bing Maps. If you see a retirement warning, replace it with a **Filled Map** or **Azure Maps** visual to restore geographic functionality.

---

## 📁 Repository Structure

```
olist_powerbi_dashboard/
│
├── 📊 olist_powerbi_dashboard.pbix   ← Main Power BI report file
│
├── 🖼️ Screenshots/
│   ├── 01-sales-analysis.png
│   ├── 02-customer-analysis.png
│   ├── 03-product-sales-analysis.png
│   ├── 04-seller-analysis.png
│   ├── 05-delivery-delay-analysis.png
│   └── 06-rfm-segmentation.png
│
├── 📄 README.md
└── 📜 LICENSE
```

---

## 📚 Data Source

**Brazilian E-Commerce Public Dataset by Olist**
- 🔗 [Kaggle Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- ~100,000 orders placed between 2016 and 2018
- Published by Olist, Brazil's largest e-commerce marketplace integrator

---

## 👩‍💻 Author

**Ritinder Kaur**
*Data Analyst · Power BI · SQL · Python*

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

<div align="center">

⭐ **If this project helped or inspired you, please give it a star!** ⭐

</div>
