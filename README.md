# Superstore-Dashboard

# 📊 Power BI Sales Dashboard — Sample Superstore

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-217346?style=for-the-badge&logo=microsoft&logoColor=white)

---

## 📌 Project Overview

An interactive, multi-page **Sales Analytics Dashboard** built using **Power BI Desktop** on the popular **Sample Superstore** dataset. This project demonstrates end-to-end data analysis skills — from data modeling and DAX to interactive visualizations and Row Level Security (RLS).

---

## 🖥️ Dashboard Pages

### 📄 Page 1 — Sales Overview
> *"How is our overall sales performance?"*

- **KPI Cards** — Total Sales, Total Profit, Profit Margin %, Total Orders
- **Line Chart** — Monthly Sales & Profit Trend
- **Bar Chart** — Total Sales by Region
- **Donut Chart** — Sales by Customer Segment
- **Slicers** — Year, Region, Segment filters
- <img width="1336" height="783" alt="image" src="https://github.com/user-attachments/assets/aa78dbdd-9848-48c7-ac1e-6afa22d12d09" />


---

### 📄 Page 2 — Product Analysis
> *"Which products and categories are driving revenue?"*

- **Bar Chart** — Total Sales by Category
- **Bar Chart** — Total Profit by Category
- **Bar Chart** — Top 10 Products by Sales (Top N Filter)
- **Treemap** — Sales by Sub-Category
  <img width="1327" height="747" alt="image" src="https://github.com/user-attachments/assets/0134e54a-6239-43ff-97e0-889bb3e3bb75" />

---

### 📄 Page 3 — Customer Analysis
> *"Who are our most valuable customers?"*

- **Donut Chart** — Sales by Customer Segment
- **Bar Chart** — High Value Customers (Top 10)
- **Map Visual** — Sales Distribution by State
- **Bar Chart** — Segment Profitability
<img width="1317" height="792" alt="image" src="https://github.com/user-attachments/assets/d582e479-b53e-48df-acf3-6b86399228a7" />

---

## 🗂️ Data Model

This project follows a **Star Schema** design:

```
         dim_customer
              |
 dim_date — fact_sales — dim_product
              |
         dim_location
```

| Table               | Type          | Key Columns                        |
|---------------------|---------------|------------------------------------|
| Sample - Superstore | Fact Table ⭐|  Order ID, Customer ID, Product ID |
| dim_customer        | Dimension     | Customer ID, Segment               |
| dim_product         | Dimension     | Product ID, Category, Sub-Category |
| dim_location        | Dimension     | City, State, Region                |
| dim_date            | Dimension     | Date, Month, Quarter, Year         |

---

## 📐 DAX Measures

```dax
-- Total Sales
Total Sales = SUM('Sample - Superstore'[Sales])

-- Total Profit
Total Profit = SUM('Sample - Superstore'[Profit])

-- Total Orders
Total Orders = DISTINCTCOUNT('Sample - Superstore'[Order ID])

-- Profit Margin %
Profit Margin % = DIVIDE(SUM('Sample - Superstore'[Profit]),
                         SUM('Sample - Superstore'[Sales]), 0) * 100
```

---

## 🔐 Row Level Security (RLS)

Implemented **Region-based RLS** to restrict data access per user:

| Role           | Filter                 |
|----------------|------------------------|
| East Region    | `[Region] = "East"`    |
| West Region    | `[Region] = "West"`    |
| South Region   | `[Region] = "South"`   |
| Central Region | `[Region] = "Central"` |

---

## 🛠️ Tools & Technologies

- **Power BI Desktop**
- **DAX** (Data Analysis Expressions)
- **Power Query** (ETL & Data Transformation)
- **Star Schema** Data Modeling
- **Row Level Security (RLS)**

---

## 📊 Key Insights

- 🏆 **Technology** is the highest selling and most profitable category
- 📍 **West Region** leads in Total Sales
- 👤 **Consumer Segment** contributes 50%+ of total revenue
- 📦 **Phones** is the top Sub-Category by sales
- 🥇 **Sean Miller** is the highest value customer
- ⚠️ **Furniture** has high sales but lowest profit margin

---

## 📁 Dataset

- **Source:** Sample - Superstore (Kaggle)
- **Records:** ~10,000 orders
- **Period:** 2014 - 2017
- **Columns:** 21 (Order ID, Sales, Profit, Quantity, Discount, etc.)

---

## 🚀 How to Use

1. Clone this repository
```bash
git clone https://github.com/yourusername/powerbi-sales-dashboard.git
```
2. Open **Power star.pbix** in Power BI Desktop
3. Refresh data if needed
4. Explore all 3 pages of the dashboard!

---

## 👨‍💻 Author

**Aditya Shinde**

---

⭐ **If you found this project useful, please give it a star!** ⭐
