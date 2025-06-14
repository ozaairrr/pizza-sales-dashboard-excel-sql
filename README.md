# 🍕 Pizza Sales Dashboard (Excel + SQL)

A complete Excel-based data analysis and visualization project with SQL validation using a 48,621-row pizza sales dataset. The project focuses on building key business insights and dashboards to monitor pizza sales performance.

---

## 📌 Problem Statement

The goal of this project is to analyze key indicators from pizza sales data and uncover insights related to revenue, ordering patterns, and product performance. It also aims to visualize business trends and identify best/worst performing pizzas.

---

## 📈 KPIs Calculated

1. **Total Revenue** – Sum of all `total_price` values  
2. **Average Order Value** – Total revenue ÷ number of distinct orders  
3. **Total Pizzas Sold** – Sum of the `quantity` field  
4. **Total Orders** – Count of distinct `order_id`s  
5. **Average Pizzas per Order** – Total pizzas ÷ total orders  

---

## 📊 Charts & Visualizations

| Visualization                             | Type         | Description                                                  |
|------------------------------------------|--------------|--------------------------------------------------------------|
| Daily Trend for Total Orders             | Bar Chart    | Orders distribution across days of the week                 |
| Hourly Trend for Total Orders            | Line Chart   | Order frequency by hour of the day                          |
| % of Sales by Pizza Category             | Pie Chart    | Revenue distribution by pizza category                      |
| % of Sales by Pizza Size                 | Pie Chart    | Revenue distribution by pizza size                          |
| Total Pizzas Sold by Pizza Category      | Funnel Chart | Comparison of sales volume per pizza category               |
| Top 5 Best Sellers (By Quantity)         | Bar Chart    | Most sold pizzas                                             |
| Bottom 5 Worst Sellers (By Quantity)     | Bar Chart    | Least sold pizzas                                            |

---

## 🧮 SQL Queries Used (Validation Logic)

This project used Microsoft SQL Server to validate Excel calculations. Some key SQL queries include:

```sql
-- Total Revenue
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;

-- Avg Order Value
SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_order_Value FROM pizza_sales;

-- Total Pizzas Sold
SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales;

-- Total Orders
SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales;

-- Avg Pizzas Per Order
SELECT CAST(SUM(quantity) AS DECIMAL(10,2)) / CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS Avg_Pizzas_per_order
FROM pizza_sales;
```
🗂️ Additional queries for trends, category-wise sales, and filtering by time (month, quarter) are available in the project files.

## 🧰 **Tools Used**

- Excel for data cleaning, processing, pivot tables, and dashboards  
- SQL Server for querying and validating KPIs  
- Excel Charts for visualization (bar, line, pie, funnel)  
- Functions Used in Excel:  
  - `=TEXT()` for extracting weekday  
  - `=COUNTIF()` for deduplicating orders  
- PivotTables for aggregating KPIs  

## 🧹 **Data Cleaning & Processing**

- Replaced pizza size abbreviations (`S`, `M`, `L`, `XL`, `XXL`) with readable names (`Regular`, `Medium`, `Large`, etc.)  
- Created new column `order_day` using `=TEXT(order_date, "dddd")`  
- Generated a unique `count_order` logic using:  
  `=1 / COUNTIF(range, cell)` → to avoid duplicate order count  
- Final data was used in pivot tables for KPI calculations and visual charts  

## 📁 **Project Structure**
```
pizza-sales-dashboard-excel-sql/
├── data/
│   ├── pizza_sales_raw.csv
│   └── pizza_sales_cleaned.xlsx
├── dashboards/
│   └── pizza_sales_dashboard.png
├── sql/
│   └── pizza_kpi_queries.sql
├── README.md
```

## 🧠 **Insights Gained**

-📈 Order Timing: Majority of orders are placed between 6 PM to 9 PM, with Friday and Saturday being the busiest days.
-🍕 Top-Selling Items: Classic Pepperoni and BBQ Chicken pizzas contribute to over 25% of total revenue.
-📊 Category Impact: Meat and Supreme categories generate the most revenue, while Veggie pizzas have lower sales overall.
-📦 Size Distribution: Large and Extra Large pizzas account for the highest quantity sold, indicating customer preference for value sizes.
-🧊 Underperforming Items: Certain specialty pizzas like Spinach Alfredo consistently perform below average in both quantity and revenue.

## 🖼️ **Dashboard Preview**

## ✅ **Conclusion**

This project is a great example of combining Excel’s analytical capabilities with SQL logic to produce insightful business dashboards.  
It's scalable for beginner-to-intermediate analytics tasks and demonstrates core BI concepts clearly.

## 🔗 **Dataset**

- **Size**: 48,621 rows  
- **Type**: Simulated pizza sales data (sourced via YouTube tutorial)  
- **Includes**: order date, order time, quantity, price, pizza type, category, and size  

📬 **Contact**

For questions or suggestions, feel free to open an issue or reach out.
