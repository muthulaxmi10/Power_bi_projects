# 🛒 DMart Sales Performance Analysis Dashboard (Power BI)

## 🎯 Objective
Leverage Power BI to analyze DMart’s historical transaction data and derive actionable insights on:
- Sales trends across time, product categories, and regions.
- Customer behavior and purchase patterns.
- Pricing and discount impacts on performance.
- Operational efficiency (shipping and payment modes).

## 🧩 Problem Statement
D-Mart, a leading retail chain, aims to modernize its decision-making through data-driven analytics.  
The goal is to:
- Identify top-performing and underperforming products.
- Understand customer demographics and preferences.
- Track cancellations, shipping modes, and payment methods.
- Enable management to take strategic actions via an interactive Power BI dashboard.

## 🧹 Data Cleaning & Preparation
Performed using Power BI Power Query Editor:
- Changed data types for consistency (e.g., Date, Numeric, Text).
- Standardized date format for all date columns.
- Replaced null or missing values: 0 for cancelled or returned transactions.
- Created new calculated columns:
  - **TimeSpent_Group** → Categorized customers by time spent on the website.
  - **Age_Group** → Grouped customers by age range.
  - **Discount %** and **Discount Bucket** → To analyze discount performance.
  - **Is Discounted** → Identified products sold at a discount.

## 🧮 Data Modeling
Implemented **Star Schema model**:
- **Fact Table:** fact_Orders (contains sales transactions)
- **Dimension Tables:** dim_Customer, dim_Product, dim_ShipMode, dim_Date, dim_Payment
- Relationships built via primary & foreign keys (CustomerID, ProductID, ShipModeID, etc.)

## 📊 Key Measures Created (DAX)
```
Total Orders = COUNTROWS (fact_Orders)
Total Revenue = SUM (fact_Orders[Total Order Value])
Average Rating = AVERAGE (fact_Orders[Avg Rating])
Cancellation Rate % = DIVIDE([Cancelled Orders], [Total Orders])
Repeat Purchase Rate % = DIVIDE([Repeat Customers], DISTINCTCOUNT(fact_Orders[Customer ID]))
COD % vs Online % = Share of orders by payment type
Average Shipping Days = DATEDIFF between Order Date and Ship Date
On-Time Delivery % = % of orders delivered within SLA
```

## 📈 Dashboard Highlights
The Power BI dashboard provides a **360° view of business performance**:
- **Sales Overview Cards:** Total Orders, Revenue, Cancellation Rate, Avg. Rating, Payment Mode %
- **Trend Analysis:** Year-wise sales line chart
- **Revenue Breakdown:** Donut chart by product category (Branded, Local, Imported)
- **Customer Insights:** Age & Gender distribution chart  

**File:** `Dmart+Dataset_Tableau.csv`  
The dataset includes:
- Order details (date, value, discount, shipping mode, payment type)
- Customer demographics (age, gender, location)
- Engagement metrics (time on website, number of clicks)
- Product details (name, category, ratings)
- Order status

### Operational Analysis
- Orders by Ship Mode
- Cancellation by Ship Mode
- Average Shipping Days

### Discount & Loyalty Analysis
- Repeat Purchase Rate vs. Discount Buckets
- Impact of Discounts on Ratings

### Payment Insights
- COD vs Online distribution pie chart

## 💡 Insights
- Branded products contribute the highest share of total revenue.
- Younger customers (21–40 years) are the most active buyers.
- Repeat purchases are higher in moderate discount ranges (11–30%).
- Free and priority shipping modes dominate order volume.
- COD remains the most preferred payment method.
- Cancellation rate is relatively low, showing efficient operations.

## 🧠 Business Impact
- Helped DMart identify top-performing product types.
- Improved understanding of customer demographics and engagement.
- Enabled data-driven pricing and shipping optimization.
- Streamlined decision-making with a centralized interactive dashboard.

## ⚙️ Tech Stack
- **Tool:** Microsoft Power BI
- **Language:** DAX (Data Analysis Expressions)
- **Data Cleaning:** Power Query Editor
