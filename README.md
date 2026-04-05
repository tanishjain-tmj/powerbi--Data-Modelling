# 📊 Power BI Project README

## Data Modeler – Building a Normalized Star Schema Data Model

---

## 📌 Project Overview

This project focuses on building a **well-structured relational data model** in Power BI using a **Star Schema approach**.
The model includes fact and dimension tables with properly defined relationships, cardinality, and hierarchies.

---

## 🎯 Objectives

* Understand **table relationships**
* Apply **cardinality (1:M, M:1)**
* Implement **Star Schema**
* Handle **inactive relationships & ambiguity**
* Build **hierarchies and matrix visuals**

---

# 🚀 STEP-BY-STEP IMPLEMENTATION

---

## 🔹 Step 1: Import Data

### 📌 Action:

* Open Power BI Desktop
* Go to **Home → Get Data → Excel**
* Import:

  * Sales_Fact.xlsx
  * Customer_Dim.xlsx
  * Product_Dim.xlsx
  * Region_Dim.xlsx
  * Date_Dim.xlsx
  * Returns_Fact.xlsx


---

## 🔹 Step 2: Data Cleaning (Power Query)

### 📌 Action:

* Click **Transform Data**
* Perform:

  * Remove blank rows
  * Set correct data types:

    * IDs → Whole Number
    * Revenue → Decimal
    * Date → Date
* Ensure no nulls in key columns

---

## 🔹 Step 3: Load Data

### 📌 Action:

* Click **Close & Apply**
* Load cleaned data into model

---

## 🔹 Step 4: Create Relationships (Model View)

### 📌 Action:

Go to **Model View** and create:

* Sales_Fact → Customer_Dim
* Sales_Fact → Product_Dim
* Sales_Fact → Region_Dim
* Sales_Fact → Date_Dim
* Returns_Fact → Sales_Fact
* Returns_Fact → Date_Dim (**Inactive**)

### ⚙ Settings:

* Cardinality: **One-to-Many (1:*)**
* Cross filter: **Single direction**

### ⚠ Important:
* Keep Returns → Date relationship **inactive** to avoid ambiguity

### 📸 Screenshot:
<img width="1907" height="948" alt="Screenshot 2026-04-05 215222" src="https://github.com/user-attachments/assets/3858250f-e1c7-49e1-bd78-4d54ff8f1939" />

---

## 🔹 Step 5: Schema Design

### 📌 Action:

* Ensure **Star Schema**:

  * Sales_Fact = central table
  * All dimension tables connected to it

* Returns_Fact:

  * Kept as **secondary fact table**

---

## 🔹 Step 6: Handle Ambiguity

### 📌 Action:

* Do NOT activate Returns → Date relationship
* Avoid circular filtering paths

### 📌 Explanation:

There are multiple paths:

* Returns → Sales → Date
* Returns → Date

So one must remain inactive.

---

## 🔹 Step 7: Create Hierarchies

### 📌 Action:

### 📅 Date Hierarchy:

* Year → Quarter → Month → Date

### 🌍 Region Hierarchy:

* Country → State → City

### 🛍 Product Hierarchy:

* Category → Subcategory → ProductName

### 📸 Screenshot:
<img width="297" height="568" alt="Screenshot 2026-04-05 220231" src="https://github.com/user-attachments/assets/a079f37d-9251-4fc1-b4f7-5c7ef0ee249e" />

---

## 🔹 Step 8: Create Matrix Visuals (Report View)

### 🟦 Visual 1: Sales by Category & Region

* Rows → Category
* Columns → Country/Region
* Values → Revenue (Sum)

### 🟩 Visual 2: Return Reasons by Fiscal Year

* Rows → Reason
* Columns → Fiscal Year
* Values → ReturnID (Count)

### 🟨 Visual 3: Revenue by Customer Segment

* Rows → Segment
* Values → Revenue (Sum)

### 📸 Screenshot:
<img width="1914" height="978" alt="Screenshot 2026-04-05 221112" src="https://github.com/user-attachments/assets/5a090935-e0d7-4f45-a8a4-4fb11499e6a7" />

---

## 🔹 Step 9: Final Validation

### ✅ Checklist:

* All relationships correct
* No ambiguity errors
* Star schema visible
* Hierarchies created
* Visuals working correctly

# 📝 Summary

### ✔ Schema Type:

Star Schema with Sales_Fact as central table

### ✔ Relationships:

1:M relationships between dimensions and fact tables

### ✔ Special Handling:

Inactive relationship used to avoid ambiguity

### ✔ Filter Direction:

Single direction for optimized performance

### ✔ Challenges:

* Ambiguous path between Returns and Date
* Resolved using inactive relationship

---

# 🎯 Conclusion

This project demonstrates building a **normalized and efficient data model** using Power BI with proper relationship handling, schema design, and reporting.

---
