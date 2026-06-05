# Olist E-Commerce Power BI Dashboard

End-to-end Power BI report built on the [Olist Brazilian E-Commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (~100K orders, 2016–2018). Covers sales performance, customer behavior, logistics, and RFM segmentation across 6 interactive pages.

---

## Dashboard Preview

| Sales Analysis | Customer Analysis |
|---|---|
| ![Sales Analysis](Screenshots/01-sales-analysis.png) | ![Customer Analysis](Screenshots/02-customer-analysis.png) |

| Product & Sales | Seller Analysis |
|---|---|
| ![Product and Sales Analysis](Screenshots/03-product-sales-analysis.png) | ![Seller Analysis](Screenshots/04-seller-analysis.png) |

| Delivery Delay Analysis | RFM Segmentation |
|---|---|
| ![Delivery Delay Analysis](Screenshots/05-delivery-delay-analysis.png) | ![RFM Segmentation](Screenshots/06-rfm-segmentation.png) |

---

## Headline Numbers

- Total Revenue: **$15M**
- Total Orders: **96K**
- Total Customers: **99K**
- Average Order Value: **~$159**
- Average Review Score: **3.84 / 5**
- On-Time Delivery Rate: **91.89%**
- Average Delivery Time: **12.5 days**

---

## Report Pages

| Page | What it covers |
|---|---|
| **Sales Analysis** | Revenue, orders, and AOV KPIs — top product categories, revenue by state (map), monthly trend, order status breakdown |
| **Customer Analysis** | Growth trend, top cities (treemap), review scores by state, customer distribution by state |
| **Product & Sales Analysis** | Top categories and sellers by revenue, monthly order volume |
| **Seller Analysis** | Seller KPIs, revenue trend, geographic spread |
| **Delivery Delay Analysis** | Avg delivery time, avg delay days, on-time rate, delivery trend, delay breakdown by state |
| **RFM Segmentation** | One-time vs repeat customers, top customers table, RFM scatter |

---

## Business Questions

- Which product categories and states generate the most revenue?
- How has the customer base grown over time, and where are customers concentrated?
- Where are delivery delays happening, and how has logistics performance improved year over year?
- Who are the high-value customers — and how many are one-time vs repeat buyers?
- Which sellers punch above their weight in revenue?

---

## Tools & Stack

- **Power BI Desktop** — data modeling, DAX measures, report authoring
- **DAX** — custom KPIs, time intelligence, RFM scoring
- **Power Query (M)** — data cleaning, type corrections, joins
- **Dataset** — Olist Brazilian E-Commerce (9 CSVs, Kaggle)

---

## Data Model

9 relational tables joined in a star schema:

```
olist_orders_dataset              ← core fact table
olist_order_items_dataset         ← line-item revenue and seller linkage
olist_order_payments_dataset      ← payment value and installments
olist_order_reviews_dataset       ← review scores
olist_customers_dataset           ← customer geography
olist_sellers_dataset             ← seller geography
olist_products_dataset            ← product metadata
product_category_name_translation ← Portuguese to English mapping
olist_geolocation_dataset         ← ZIP-code coordinates for maps
```

---

## How to Use

1. Clone the repo or download `olist_powerbi_dashboard.pbix`
2. Open in **Power BI Desktop**
3. If prompted, update the data source path and hit **Refresh**
4. Use the slicers (date range, state, order status) to explore

> The map visual uses Bing Maps — if you see a retirement warning, swap it for a Filled Map or Azure Maps visual.

---

## Author

**Ritinder Kaur**

---

## License

MIT
