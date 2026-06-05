# Olist Power BI Dashboard

Interactive Power BI report that explores sales, customers, products, sellers, delivery performance, and RFM segmentation for the Olist Brazilian e-commerce dataset.

## Highlights
- KPI overview: Total Revenue, Total Orders, Average Order Value, Total Customers, Average Review Score
- Monthly revenue and order trends
- State-level performance and customer distribution
- Top products, categories, and sellers by revenue
- Delivery delay analysis and review score distribution
- RFM segmentation for customer behavior

## Project Files
- olist_powerbi_dashboard.pbix: Power BI report file
- Screenshots/: dashboard images for quick preview

## Report Pages
- Sales Analysis: high-level KPIs, category revenue, revenue by state, and order status
- Customer Analysis: growth trend, top cities, review score by state, and customer distribution
- Product and Sales Analysis: top categories, top sellers, revenue share, and monthly orders
- Seller Analysis: seller KPIs, revenue trend, and distribution by state/city
- Delivery Delay Analysis: delay KPIs, delivery time trends, and status distribution
- RFM Segmentation: customer segmentation and top customers view

## Screenshots
![Sales Analysis](Screenshots/01-sales-analysis.png)
![Customer Analysis](Screenshots/02-customer-analysis.png)
![Product and Sales Analysis](Screenshots/03-product-sales-analysis.png)
![Seller Analysis](Screenshots/04-seller-analysis.png)
![Delivery Delay Analysis](Screenshots/05-delivery-delay-analysis.png)
![RFM Segmentation](Screenshots/06-rfm-segmentation.png)

## Data Source
- Olist Brazilian E-Commerce public dataset (Kaggle): https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## How to Use
1. Open `olist_powerbi_dashboard.pbix` in Power BI Desktop.
2. If prompted, update data source paths and refresh the model.
3. Use slicers to filter by date, state, status, and category.

## Notes
- The map visual uses Bing maps and may show a retirement warning in some Power BI versions. If needed, replace it with a Filled Map or Azure Maps visual.

## Author
- Ritinder Kaur

## License
MIT
