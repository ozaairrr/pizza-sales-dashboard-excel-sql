<p align="center">
  <img src="https://github.com/ozaairrr/pizza-sales-dashboard-excel-sql/blob/a46da886d2a2d965f2982166971cae1bc153b8e7/Dashboard/Pizza_Sales_Dashboard_Preview.png" alt="Pizza Sales Dashboard" width="500">
</p>
<p align="center"><i>📊 Dashboard showcasing key pizza sales KPIs and trends</i></p>

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
🗂️ Additional queries for trends, category-wise sales, and filtering by time (month, quarter) are available in the project files [**here**](https://github.com/ozaairrr/pizza-sales-dashboard-excel-sql/blob/b74646f706eb3d4046e84e8c2726ad7cfe623c44/SQL/sql_quries_pizza_sales.pdf).

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
├── Datasets/
│   ├── pizza_sales_raw.csv
│   └── pizza_sales_cleaned.xlsx
├──Dashboard/
|   ├── Pizza_Sales_Dashboard_Preview.png
|   ├── Pizza_Sales_Dashboard.xlsx
├── sql/
│   └── pizza_kpi_queries.sql
├── README.md
```

## 🧠 **Insights Gained**

- 📈 **Order Timing**: Most orders are placed between **12PM to 1PM & 4PM to 8PM**, with a noticeable peak on **Fridays and Saturdays**.  
- 🍕 **Top-Selling Pizzas**: **Classic Pepperoni** and **BBQ Chicken** contribute over **25% of revenue**.  
- 🧩 **Category Performance**: **Meat** and **Supreme** categories dominate in revenue, while **Veggie** pizzas lag behind.  
- 📦 **Size Preferences**: **Large** and **Extra Large** pizzas are most frequently ordered, showing a demand for value portions.  
- ❄️ **Underperformers**: Items like **Spinach Alfredo** consistently show low sales across all time periods.  

## 🖼️ **Dashboard Preview**

![Pizza Sales Dashboard](https://github.com/ozaairrr/pizza-sales-dashboard-excel-sql/blob/a46da886d2a2d965f2982166971cae1bc153b8e7/Dashboard/Pizza_Sales_Dashboard_Preview.png)
### 📊 Final Excel Dashboard with KPIs & Charts
 The final Excel dashboard with all KPIs and charts can be found [**here**](https://github.com/ozaairrr/pizza-sales-dashboard-excel-sql/blob/1b1f3bb677602f35f8a1eb7114e2a4e63e424b14/Dashboard/Pizza_Sales_Dashboard.xlsx).


## ✅ **Conclusion**
This project showcases how combining Excel's powerful data analysis features with SQL's precision querying can generate actionable business insights. From raw data cleaning to dashboard creation, each step was designed to mimic real-world BI workflows. The outcome is a scalable, beginner-friendly analytics solution that highlights key sales patterns, identifies performance gaps, and enables data-driven decision-making. Whether you're exploring your first data project or building a business case, this dashboard demonstrates the value of blending tools for end-to-end analytics.

## 🔗 **Dataset**

- **Size**: 48,621 rows  
- **Type**: Simulated pizza sales data 
- **Includes**: pizza_id	order_id	total_order	pizza_name_id	quantity	order_date	order_day	order_time	unit_price	total_price	pizza_size	pizza_category	pizza_ingredients	pizza_name
- **[Download Dataset](https://github.com/ozaairrr/pizza-sales-dashboard-excel-sql/raw/a5f3253af85bc2d898f0c4e17c9b98c8daec703f/Datasets/processed_pizza_sales_dataset.xlsx)**  

📬 **Contact**

For questions or suggestions, feel free to open an issue or reach out.
