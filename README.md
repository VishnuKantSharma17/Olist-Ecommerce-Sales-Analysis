# 🛒 Olist E-Commerce Sales & Customer Analysis

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-SQL-blue)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Project-green)

## 📌 Project Overview

This project analyzes e-commerce data using **PostgreSQL, SQL and Microsoft Power BI**.

The project focuses on analyzing:

- Sales performance
- Order trends
- Customer behavior
- Product categories
- Customer geography
- Delivery performance
- Customer reviews and ratings
- Payment methods
- Seller performance

The project follows an end-to-end data analytics workflow from raw data preparation in PostgreSQL to interactive business dashboards in Power BI.

---

## 🎯 Business Objectives

The analysis aims to answer questions such as:

- What is the total revenue and order volume?
- What is the average order value?
- Which product categories generate the most revenue?
- Which customer states and cities contribute the most revenue?
- What percentage of orders are delivered on time?
- How do customer ratings vary across categories?
- Which payment methods are most commonly used?
- Which sellers generate the highest revenue?
- How do sales and orders change over time?

---

## 🛠️ Tools & Technologies

- **PostgreSQL**
- **SQL**
- **Microsoft Power BI**
- **DAX**
- **Data Modeling**
- **Data Visualization**
- **Power BI Drillthrough**

---

## 🗂️ Dataset

The project uses the **Olist Brazilian E-Commerce dataset**.

The dataset contains information about:

- Customers
- Orders
- Order Items
- Products
- Sellers
- Payments
- Reviews
- Geolocation
- Product Categories

### Main Tables

| Table | Description |
|---|---|
| `olist_customers_dataset` | Customer information |
| `olist_geolocation_dataset` | Geographic information |
| `olist_products_dataset` | Product information |
| `olist_sellers_dataset` | Seller information |
| `olist_orders_dataset` | Order information |
| `olist_order_items_dataset` | Products and sellers in orders |
| `olist_order_payments_dataset` | Payment information |
| `olist_order_reviews_dataset` | Customer reviews and ratings |
| `product_category_name_translation` | Product category translation |

---

# 🏗️ SQL & PostgreSQL

The raw datasets were loaded into PostgreSQL and organized into relational tables.

Relationships were created between:

```text
Customers
    ↓
Orders
    ↓
Order Items
    ↓
Products
    ↓
Sellers
```

Additional relationships were created for:

```text
Orders → Payments
Orders → Reviews
Products → Category Translation
```

Indexes were also created for frequently used fields such as:

- `order_id`
- `customer_id`
- `product_id`
- `seller_id`
- `purchase_date`
- `customer_state`

---

## 🔄 SQL Data Transformation

Several BI-oriented SQL views were created for Power BI analysis.

### `bi_dim_product`

Provides product-level analytical information including:

- Product ID
- Product category
- Product weight
- Product dimensions
- Product volume

### `bi_fact_order`

Provides order-level analytical information including:

- Order ID
- Customer ID
- Order status
- Purchase date
- Purchase month
- Delivery date
- Estimated delivery date
- Delivery days
- Late-delivery indicator
- Customer location

### `bi_fact_sales`

Combines information from:

- Order Items
- Orders
- Customers
- Products
- Reviews
- Payments
- Sellers

### `bi_payments_order`

Provides order-level payment summaries including:

- Payment value
- Payment installments
- Payment type

---

# 📊 Power BI Dashboard

The Power BI report contains **9 analytical pages**.

## 1. Executive Dashboard

Provides an overall business-performance overview.

### Key KPIs

| KPI | Value |
|---|---:|
| Total Revenue | **14.21M** |
| Total Orders | **98.67K** |
| Total Customers | **95.42K** |
| AOV | **144.01** |
| On-Time % | **93.23%** |
| Average Rating | **4.03** |
| YoY % | **253.07%** |

### Visuals

- Orders by Month
- Order Status Share
- Revenue Trend
- Top Categories by Revenue
- Revenue by State
- Executive KPI cards

---

## 2. Sales Trend

Analyzes sales performance over time.

### Includes

- Revenue vs Last Year
- Rolling 30-Day Revenue
- Revenue YTD
- Category × Year analysis
- Revenue
- Orders
- AOV

---

## 3. Category & Product

Analyzes category-level performance.

### Includes

- AOV vs Orders by Category
- Top 10 Categories by Rating
- Top 20 Categories
- Category Revenue Share
- Revenue
- Orders
- AOV
- Average Rating
- On-Time %

---

## 4. Customer Geography

Analyzes customer revenue geographically.

### Includes

- Revenue by Customer State
- Top 10 Customer States by Revenue
- Top 10 Customer Cities by Revenue
- Customer State × Category analysis

---

## 5. Delivery & Logistics

Analyzes delivery performance.

### Key KPI

**On-Time Delivery: 93.23%**

### Includes

- Average Delivery Days by Category
- On-Time %
- Total Late Orders
- Late Orders by Month
- Late % by Customer State

---

## 6. Reviews

Analyzes customer ratings and review performance.

### Key Metrics

| Metric | Value |
|---|---:|
| Average Rating | **4.03** |
| Positive Review % | **0.75** |
| Negative Review % | **0.17** |

### Includes

- Rating Distribution
- Average Rating by Category
- Average Rating by Late/On-Time Status

---

## 7. Payments

Analyzes payment behavior.

### Payment Types

- Credit Card
- Boleto
- Debit Card
- Voucher

### Includes

- Payment Value Trend
- Payment Type Share
- Late Orders by Month
- Payment Value
- Orders
- AOV
- Average Installments

---

## 8. Sellers

Analyzes seller performance.

### Includes

- Total Sellers
- Revenue per Seller
- Top 10 Sellers by Revenue
- Seller State by Revenue
- Seller State × Category

---

## 9. Drillthrough

Provides detailed analysis after selecting a category or state.

### Includes

- Revenue
- Orders
- AOV
- Average Rating
- On-Time %
- Revenue by Year-Month
- Category-level details

---

# 📈 Key Business Insights

Based on the completed Power BI dashboard:

1. Total revenue is approximately **14.21M**.
2. The dashboard contains approximately **98.67K orders**.
3. Approximately **95.42K customers** are represented.
4. Overall AOV is approximately **144.01**.
5. Overall on-time delivery is **93.23%**.
6. Average customer rating is **4.03/5**.
7. `health_beauty` is among the highest-revenue categories shown in the dashboard.
8. **SP** is a major customer-revenue-contributing state.
9. Credit card represents the largest payment-value share.
10. Delivery performance can be analyzed by category, state and month using the logistics dashboard.

---

# 🔄 Project Workflow

```text
Raw CSV Data
      ↓
PostgreSQL
      ↓
Data Validation
      ↓
SQL Transformations
      ↓
BI Views
      ↓
Power BI Data Model
      ↓
DAX Measures
      ↓
Interactive Dashboard
      ↓
Business Insights
```

---

# 📁 Project Structure

```text
Olist-Ecommerce-Sales-Analysis/
│
├── README.md
│
├── SQL/
│   └── olist_analysis.sql
│
├── PowerBI/
│   └── Olist_Ecommerce_Dashboard.pbix
│
├── Screenshots/
│   ├── Executive_Dashboard.png
│   ├── Sales_Trend.png
│   ├── Category_Product.png
│   ├── Customer_Geo.png
│   ├── Delivery_Logistics.png
│   ├── Reviews.png
│   ├── Payments.png
│   ├── Sellers.png
│   └── Drillthrough.png
│
└── Documentation/
    └── Project_Insights.md
```

---

# 💡 Skills Demonstrated

- SQL
- PostgreSQL
- SQL Joins
- SQL Aggregations
- SQL Views
- SQL Indexing
- Data Transformation
- Data Modeling
- Power BI
- DAX
- KPI Development
- Data Visualization
- Time-Series Analysis
- Geographic Analysis
- Customer Analysis
- Product Analysis
- Delivery Analysis
- Review Analysis
- Payment Analysis
- Seller Analysis
- Power BI Drillthrough

---

# 🚀 Future Improvements

Potential future improvements include:

- Customer segmentation
- RFM analysis
- Customer retention analysis
- Repeat-purchase analysis
- Customer Lifetime Value
- Seller performance analysis
- Profitability analysis
- Delivery-time prediction
- Python-based exploratory data analysis

---

# 👨‍💻 Author

## Vishnu Kant Sharma

**Aspiring Data Analyst**

### Skills

`SQL` `PostgreSQL` `Power BI` `DAX` `Excel` `Python` `Data Analysis`

---

## ⭐ Project Status

**Completed**

This project demonstrates an end-to-end data analytics workflow using SQL, PostgreSQL and Power BI.
