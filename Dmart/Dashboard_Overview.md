# 📊 DMart Power BI Dashboard Overview

## 1️⃣ Data Model — Star Schema Design

![DMart Data Model](Screenshot%20(388).png)

### 🧩 Explanation
The above image represents the **Data Model** used for the DMart Sales Analysis Dashboard.  
It follows a **Star Schema** structure, which includes:
- **Fact Table:** `fact_Orders` — contains transactional data such as revenue, discount, and shipping info.  
- **Dimension Tables:**
  - `dim_Product` → product details (name, category, price)
  - `dim_Customers` → customer demographics (age, gender, city)
  - `dim_ShipMode` → shipping mode (Free, Priority, Express)
  - `dim_Payment` → payment method (COD, UPI, etc.)
  - `dim_Date` → date hierarchy for time-based analysis  
- This schema ensures faster DAX calculations and simplified reporting in Power BI.

---

## 2️⃣ Power BI Dashboard — DMart Sales Performance

![DMart Sales Dashboard](Screenshot%20(423).png)

### 💡 Dashboard Explanation
This dashboard provides a **360° view of DMart’s business performance** through interactive visuals.

#### 🔹 KPI Cards (Top Row)
- **Total Orders, Total Revenue, Cancellation Rate, Average Rating, Payment Mode COD**  
  → These key indicators give management a quick summary of the company’s performance.

#### 🔹 Sales Trends
- **Sales by Month & Year (Line Chart)** — Tracks seasonal trends and year-over-year growth.

#### 🔹 Revenue Breakdown
- **Total Revenue by Product Category (Donut Chart)** — Highlights the contribution of Branded, Local, and Imported products.

#### 🔹 Customer & Discount Insights
- **Rating vs Repeat Purchase Rate (Bar Chart)** — Shows that moderate discounts (11–30%) encourage repeat purchases without hurting ratings.

#### 🔹 Operational Insights
- **Orders by Ship Mode / Cancellation by Ship Mode** — Helps monitor logistics performance.
- **Cancellations Reason by Ship Mode** — Identifies issues in specific delivery types.

#### 🔹 Demographics & Payment
- **Total Order Value by Age Group and Gender** — Reveals that younger buyers (21–40) are most active.
- **Payment Method Distribution (Pie Chart)** — COD is the most preferred mode, followed by UPI.

---

### 🧠 Business Value
This Power BI dashboard enables DMart to:
- Monitor performance metrics in real-time.  
- Optimize product pricing, shipping, and discount strategy.  
- Understand customer demographics for targeted marketing.  
- Improve decision-making using interactive visuals and DAX-powered KPIs.
