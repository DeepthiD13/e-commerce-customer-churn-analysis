# E-Commerce Customer Churn Analysis

## Project Overview

This project is a **Module End Assignment 2 – MySQL** focused on **E-Commerce Customer Churn Analysis**. The project uses an e-commerce customer churn dataset to perform data cleaning, data transformation, customer behavior analysis, churn analysis, and customer return analysis using SQL in **MySQL Workbench**.

## Objectives

- Clean missing and inconsistent values.
- Handle outliers.
- Standardize inconsistent data values.
- Transform the dataset into meaningful categories.
- Analyze churned and active customers.
- Identify customer behavior and purchasing patterns.
- Analyze customer returns.
- Generate useful insights from the e-commerce customer data.

## Tools and Technologies

| Category | Details |
|---|---|
| Assignment | Module End Assignment 2 – MySQL |
| Project | E-Commerce Customer Churn Analysis |
| Database | MySQL |
| Tool | MySQL Workbench |
| Language | SQL |
| Main Database | `ecomm` |
| Main Table | `customer_churn` |
| Returns Table | `customer_returns` |

## Repository Files

- **E-Commerce_Customer_Churn_Dataset.sql** – Original SQL dataset and database setup provided for the assignment.
- **E-Commerce_Customer_Churn_Analysis.sql** – Completed SQL work containing data cleaning, transformation, analysis, and customer returns analysis.

## Data Cleaning

### Mean Imputation

Missing values were replaced using mean values for:

- `WarehouseToHome`
- `HourSpendOnApp`
- `OrderAmountHikeFromlastYear`
- `DaySinceLastOrder`

The calculated mean values were rounded to the nearest integer where required.

### Mode Imputation

Missing values were replaced using mode values for:

- `Tenure`
- `CouponUsed`
- `OrderCount`

### Outlier Treatment

Rows where `WarehouseToHome > 100` were deleted.

### Data Standardization

The following inconsistent values were standardized:

- `Phone` → `Mobile Phone`
- `Mobile` → `Mobile Phone`
- `COD` → `Cash on Delivery`
- `CC` → `Credit Card`

## Data Transformation

The following transformations were performed:

- `PreferedOrderCat` was renamed to `PreferredOrderCat`.
- `HourSpendOnApp` was renamed to `HoursSpentOnApp`.
- A `ComplaintReceived` column was created.
  - `Yes` when `Complain = 1`
  - `No` otherwise
- A `ChurnStatus` column was created.
  - `Churned` when `Churn = 1`
  - `Active` otherwise
- The original `Churn` and `Complain` columns were dropped.

## Data Exploration and Analysis

The completed SQL script covers the following analysis requirements:

1. Count of churned and active customers.
2. Average tenure and total cashback amount of churned customers.
3. Percentage of churned customers who complained.
4. City tier with the highest number of churned Laptop & Accessory customers.
5. Most preferred payment mode among active customers.
6. Total order amount hike from last year for single customers preferring mobile phones.
7. Average number of devices registered among UPI users.
8. City tier with the highest number of customers.
9. Gender with the highest number of coupons utilized.
10. Number of customers and maximum app hours for each preferred order category.
11. Total order count for credit card users with the maximum satisfaction score.
12. Average satisfaction score of customers who complained.
13. Preferred order category among customers who used more than 5 coupons.
14. Top 3 preferred order categories by average cashback amount.
15. Preferred payment modes based on the assignment's average tenure and order-count conditions.
16. Distance categories and churn-status breakdown.
17. Customer order details for married customers in City Tier 1 whose order count is above the average order count.

## Distance Categorization

Customers were categorized based on warehouse-to-home distance:

- `<= 5 km` → Very Close Distance
- `<= 10 km` → Close Distance
- `<= 15 km` → Moderate Distance
- `> 15 km` → Far Distance

The number of customers in each distance category was analyzed according to churn status.

## Customer Returns Analysis

A `customer_returns` table was created in the `ecomm` database.

The table contains:

- `ReturnID`
- `CustomerID`
- `ReturnDate`
- `RefundAmount`

The return records specified in the assignment were inserted into the table.

The final query joins `customer_returns` with `customer_churn` and displays return details together with customer details for customers who:

- Are `Churned`
- Have `ComplaintReceived = Yes`

## SQL Concepts Used

This project demonstrates the following SQL concepts:

- Database creation
- Table creation
- Data insertion
- Data cleaning
- Missing-value handling
- Mean calculation
- Mode calculation
- Outlier removal
- Data standardization
- Data transformation
- Column renaming
- Adding columns
- Updating records
- Dropping columns
- `CASE` statements
- `WHERE`
- `GROUP BY`
- `ORDER BY`
- `HAVING`
- `COUNT()`
- `SUM()`
- `AVG()`
- `MAX()`
- Subqueries
- Table joins
- Conditional filtering

## How to Run the Project

1. Open **MySQL Workbench**.
2. Open `E-Commerce_Customer_Churn_Analysis.sql`.
3. Execute the SQL script.
4. The script creates and uses the `ecomm` database.
5. Review the result grids generated by the analysis queries.

## Project Outcome

This project demonstrates how SQL can be used to perform an end-to-end analysis of e-commerce customer churn data.

The project covers:

- Data cleaning
- Missing-value treatment
- Outlier handling
- Data standardization
- Data transformation
- Customer churn analysis
- Customer behavior analysis
- Customer segmentation
- Customer return analysis

The analysis helps identify patterns related to customer churn, purchasing behavior, payment preferences, satisfaction, coupon usage, distance categories, and customer returns.

## Conclusion

The **E-Commerce Customer Churn Analysis** project provides practical experience in using SQL and MySQL Workbench to clean, transform, analyze, and interpret customer data.

The completed SQL solution follows the requirements of **Module End Assignment 2 – MySQL** and demonstrates the use of SQL for real-world customer churn analysis.

## Author

**E-Commerce Customer Churn Analysis**

**Module End Assignment 2 – MySQL**
