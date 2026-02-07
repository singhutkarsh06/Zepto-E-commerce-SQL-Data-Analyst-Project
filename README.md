# 📦 Zepto E-commerce SQL Data Analyst Project

This project is a complete, real-world **SQL Data Analytics Portfolio Project** built using an e-commerce inventory dataset scraped from **Zepto**, one of India’s fastest-growing quick-commerce companies. It simulates end-to-end workflows performed by data analysts in e-commerce and retail domains — including data exploration, cleaning, and generating business insights using SQL.

---

## 📌 Project Overview

This project demonstrates how SQL is used to:

* Create and manage an e-commerce inventory database
* Perform Exploratory Data Analysis (EDA)
* Clean inconsistent, duplicate, and messy real-world data
* Derive business insights around pricing, discounts, stock levels, and product categories

It is ideal for anyone preparing for **Data Analyst**, **Business Analyst**, or **Product Analyst** roles.

---

## 📁 Dataset Summary

The dataset (sourced from Kaggle) contains product listings scraped from Zepto. Each row represents a unique SKU with variations in weight, package size, discounts, and categories — similar to real e-commerce catalog data.

**Columns include:**

* `sku_id` – Unique product identifier
* `name` – Product name
* `category` – Product category
* `mrp` – Maximum Retail Price (in ₹)
* `discountPercent` – Discount percentage
* `discountedSellingPrice` – Final price after discount (₹)
* `availableQuantity` – Inventory quantity
* `weightInGms` – Weight in grams
* `outOfStock` – Boolean stock availability
* `quantity` – Units per package

---

## 🔧 Project Workflow

### **1. Database & Table Creation**

A PostgreSQL table is created with proper data types:

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```

---

### **2. Data Import**

Load the CSV using pgAdmin or use:

```sql
\copy zepto(category,name,mrp,discountPercent,availableQuantity,
discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');
```

---

### **3. Data Exploration**

Performed analysis including:

* Record counts
* Distinct category identification
* Null analysis
* Stock availability comparison
* Duplicate product detection
* Viewing sample records

---

### **4. Data Cleaning**

Steps include:

* Removing records with invalid (zero) MRP or selling price
* Converting paise → rupees
* Ensuring consistent data types and values

---

### **5. Business Insights Using SQL**

Generated meaningful insights such as:

* Top discounted products
* High-MRP out-of-stock items
* Potential revenue per category
* High-price, low-discount products
* Average discount per category
* Price-per-gram comparisons
* Weight-based product segmentation
* Total inventory weight per category

---

## 📜 License

This project is released under the **MIT License** — feel free to use, modify, and include it in your portfolio.

---
