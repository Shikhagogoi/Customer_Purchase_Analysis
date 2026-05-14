# 🛒 Customer Purchase Analysis

An end-to-end retail analytics project focused on uncovering customer purchasing behavior, revenue patterns, product performance, and subscription trends using advanced SQL analytics techniques.

This project simulates a real-world business intelligence workflow where raw transactional data is transformed into actionable insights for decision-making.

---

# 📌 Project Highlights

✅ Customer Segmentation Analysis  
✅ Revenue & Sales Analytics  
✅ Subscription Behavior Insights  
✅ Product Performance Tracking  
✅ Ranking & Window Function Analysis  
✅ Business KPI Reporting  
✅ Retention & Loyalty Analysis  
✅ PostgreSQL Query Optimization  
✅ Dashboard-Ready Analytics Workflow  

---

# 🎯 Project Objective

The primary goal of this project is to demonstrate how SQL can be used beyond basic querying to solve real business problems and generate data-driven insights.

The project focuses on answering analytical business questions such as:

- Which customer segments generate maximum revenue?
- Do subscribed customers spend more?
- Which products perform best across categories?
- How do discounts influence purchasing behavior?
- Which age groups contribute most to revenue?
- Are repeat customers more likely to subscribe?

---

# 🧠 Skills Demonstrated

### 🔹 SQL Concepts
- CTEs (Common Table Expressions)
- Window Functions
- Subqueries
- Aggregate Functions
- CASE Statements
- Ranking Functions
- GROUP BY Analytics
- Business KPI Calculations

### 🔹 Data Analytics Skills
- Customer Segmentation
- Revenue Analysis
- Behavioral Analytics
- Trend Identification
- Business Intelligence Reporting

### 🔹 Tools & Technologies
- PostgreSQL
- Python
- Power BI 

---

# 📂 Project Structure

```bash
Customer-Purchase-Analytics/
│
├── Python Analysis/
│   ├── data_cleaning.ipynb
│   ├── eda_analysis.ipynb
│   ├── data_modeling.ipynb
│
├── SQL Queries/
│   ├── business_analysis_queries.sql
│   ├── customer_segmentation.sql
│   ├── advanced_analytics.sql
│
├── Dataset/
│   └── customer_data.csv
│
├── Dashboard/
│   └── customer_analytics_dashboard.pbix
│
└── README.md
```

---

# 📊 Key Business Analyses Performed

## 1️⃣ Revenue Analysis
- Gender-wise revenue contribution
- Subscription-based spending comparison
- Revenue contribution by age group

## 2️⃣ Customer Analytics
- Loyal vs Returning vs New customer segmentation
- Repeat purchase behavior analysis
- Customer spending trends

## 3️⃣ Product Analytics
- Top-rated products
- Most discounted products
- Top-performing products by category

## 4️⃣ Operational Insights
- Shipping-type purchase comparison
- Discount effectiveness analysis
- Purchase behavior tracking

---

# 📈 Sample SQL Analysis

### 🔹 Top 3 Products Within Each Category

```sql
WITH item_counts AS (
    SELECT category,
           item_purchased,
           COUNT(customer_id) AS total_orders,
           ROW_NUMBER() OVER (
               PARTITION BY category
               ORDER BY COUNT(customer_id) DESC
           ) AS item_rank
    FROM customer
    GROUP BY category, item_purchased
)

SELECT item_rank,
       category,
       item_purchased,
       total_orders
FROM item_counts
WHERE item_rank <= 3;
```

---

# 📌 Key Insights

📍 Non-subscribed customers generated significantly higher average revenue compared to subscribers.

📍 A small group of loyal customers contributed disproportionately to overall sales.

📍 Certain products achieved high sales despite frequent discounting, indicating strong market demand.

📍 Express shipping customers showed higher average purchase values than standard shipping customers.

---

# 🚀 Future Improvements

- RFM Customer Segmentation
- Cohort Analysis
- Customer Lifetime Value (CLV)
- SQL Stored Procedures
- Query Optimization using Indexing
- Interactive Power BI Dashboard
- Predictive Analytics Integration

---

# 📜 License

This project is licensed under the MIT License.

---

# 👩🏻‍💻 Author

**Sikha Gogoi**  
M.Tech Data Science | Data Analytics & AI Enthusiast

Passionate about transforming raw data into meaningful business intelligence using SQL, analytics, and machine learning.

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.
