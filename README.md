# 📊 Vrinda Store Annual Report 2022 – Data Analysis

## 📌 Project Overview
This project analyzes **Vrinda Store’s** 2022 sales performance using **Excel pivot tables** and dashboards.  
Key focus areas:
- Monthly sales and order trends
- Gender-based sales split
- Order status distribution
- State-wise sales
- Age group & gender sales patterns
- Sales channel performance

---

## 📂 Dataset
The raw dataset contains:
- **Order Details** → Order ID, Date, Status
- **Customer Info** → Gender, Age, Age Group
- **Product Info** → Category, Size, Quantity
- **Sales Info** → Amount, Currency
- **Shipping Info** → City, State, Postal Code, Country
- **Channel** → Platform used for purchase

File: `data/project_vrinda_stores_da.xlsx`

---

## 📊 Steps in Analysis

### 1️⃣ Data Cleaning
- Removed blank rows & irrelevant columns
- Formatted **Date** column
- Created **Month** column:  
  ```excel
  =TEXT(Date, "mmm")
  ```
  - Created **Age Group** column:
  ```excel
  =IF(Age>=50,"Senior",IF(Age>=30,"Adult","Teenager"))
  ```

  ## 2️⃣ Pivot Tables Created
- **Sales vs Orders** → Monthly **Sum of Amount** & **Count of Order ID**
- **Men vs Women** → Gender-wise **Sum of Amount**
- **Order Status** → Counts for **Delivered / Cancelled / Refunded**
- **State** → **Top sales by state** (Sum of Amount)
- **Age n Gender** → **Age Group × Gender** (Count of Order ID)
- **Channel** → **Orders share by platform** (Count of Order ID, % of Total)

---

## 3️⃣ Dashboard Creation
- **Combine** all pivot tables into one **Dashboard** sheet
- **Add Slicers** for:
  - **Month**
  - **Gender**
  - **State**
  - **Channel**
- **Use Conditional Formatting** to highlight top/bottom values and data bars

---

## 📈 Key Insights
- **Women** customers purchased **more** than men
- **Maharashtra**, **Karnataka**, and **Uttar Pradesh** show the **highest sales**
- **Amazon** and **Flipkart** are the **most used sales channels**
- **Adults (30–50)** form the **largest customer group**

---

## 📌 Formulas Used

| Purpose                 | Formula                                                      |
|-------------------------|--------------------------------------------------------------|
| Month extraction        | `=TEXT([@Date], "mmm")`                                      |
| Age grouping            | `=IF([@Age]<18,"Teenager",IF([@Age]<=50,"Adult","Senior"))`  |
| Total Sales (Pivot)     | **Sum of Amount**                                            |
| Order Count (Pivot)     | **Count of Order ID**                                        |
| Gender Split            | Pivot: **Rows = Gender**, **Values = Sum of Amount**         |
| % Orders by Channel     | `(Orders from Channel) / (Total Orders)`                     |

---
## Dashboard Preview

![Dashboard Screenshot](dashboard_img(2).png)

