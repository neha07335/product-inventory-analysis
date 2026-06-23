# 📦 Product Inventory & Environment Analysis — Power BI Dashboard

An interactive Power BI dashboard analyzing product inventory, sales performance, supply shortage, and profitability. This project also demonstrates a real-world workflow of **migrating the data source from Microsoft SQL Server to MySQL** without rebuilding the dashboard.

---

## 🔄 What Makes This Project Special

> Most dashboards just connect to one database. In this project, I first built the dashboard using **Microsoft SQL Server**, then successfully switched the data source to **MySQL** — keeping all visuals, measures, and transformations intact.

**Skills demonstrated:**
- Connecting Power BI to Microsoft SQL Server
- Migrating data source to MySQL without breaking the report
- Fixing connector and column mapping errors during migration
- Using Power Query Advanced Editor to update source references

---

## 📊 Dashboard Pages

### Page 1 — Overview & Performance
High-level summary of product performance, order trends, and profitability across the inventory dataset.

### Page 2 — Inventory & Risk Analysis
Detailed breakdown of supply shortages, total losses, and product-level inventory health.

---

## 📈 Key Metrics Tracked

| Metric | Description |
|---|---|
| **Total Profit** | Overall profit generated across all products |
| **Total Supply Shortage** | Quantity of products that fell short of demand |
| **Total Loss** | Revenue lost due to stockouts or returns |
| **Order Date Analysis** | Time-based trends using `Order_Date_DD_MM_YYYY` |
| **Product Name Breakdown** | Performance metrics split by individual products |

---

## 🗄️ Dataset

**Table:** `prod env inventory dataset` (MySQL database: `prod`)

**Key Columns:**

| Column | Description |
|---|---|
| `Product_Name` | Name of the product |
| `Product_ID` | Unique product identifier |
| `Order_Date_DD_MM_YYYY` | Date the order was placed |
| `Total Profit` | Profit from each record |
| `Total Supply Shortage` | Units short of fulfilling demand |
| `Total Loss` | Financial loss from shortages or returns |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard design and visualization |
| **Microsoft SQL Server** | Original data source |
| **MySQL (localhost:3306)** | Migrated data source |
| **Power Query (M)** | Data transformation and source switching |
| **DAX** | Custom measures and KPI calculations |
| **MySQL Workbench** | Database management and query testing |

---

## 🔄 How I Migrated from SQL Server to MySQL

1. Built the full dashboard connected to **Microsoft SQL Server**
2. Exported / recreated the dataset in **MySQL Workbench** under database `prod`
3. In Power BI → **Transform Data → Advanced Editor** → updated the `Source` line from SQL Server to MySQL connection string
4. Fixed column mapping errors (`Order_Date_DD_MM_YYYY`) that arose due to source switch
5. Disabled **Safe Update Mode** in MySQL using `SET SQL_SAFE_UPDATES = 0` for data edits
6. Refreshed the report — all visuals, measures, and relationships remained intact

---

## 🚀 How to Open This Project

1. Install **Power BI Desktop** → [Download here](https://powerbi.microsoft.com/desktop)
2. Install **MySQL Connector/NET** → [Download here](https://dev.mysql.com/downloads/connector/net/)
3. Set up a MySQL database named `prod` with the inventory table
4. Clone this repository and open `power_bi_report.pbix`
5. When prompted, update the data source to your local MySQL credentials:
   - Server: `your_mysql_server`
   - Database: `your_database_name`
   - Username: `your_username`

---

## 💡 Key Learnings

- How to connect Power BI to both **SQL Server and MySQL**
- How to switch data sources in Power BI using the **Advanced Editor**
- How to troubleshoot **column not found** errors after source migration
- How to handle **Safe Update Mode** errors in MySQL Workbench
- Importance of consistent **column naming** across database migrations
