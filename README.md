# Power BI Case Study: Crunchy Corner's financial Performance Analysis
## Table of Contents
- [Project Overview](#project-overview)
- [Objective](#objective)
- [Data Collection](#data-collection)
- [Data Cleaning](#data-cleaning)
- [Data Modelling](#data-modelling)

## Project Overview
Crunchy Corner, one of India’s largest fast-food restaurant chains, serves millions daily through its 1,000+ outlets across the country. Renowned for offering the largest SKU variety in the industry, Crunchy Corner strives to maintain profitability, enhance efficiency, and deliver exceptional value to its customers. 

This project analyzes Crunchy Corner's business data from 2020–2024 to uncover financial challenges, optimize operations, and ensure sustainable growth using data-driven insights.

## Objective 
The primary objective of this project is to design an interactive Power BI dashboard that enables Crunchy Corner to monitor and evaluate its financial performance across the years 2020–2024. The dashboard will serve as a comprehensive decision-support tool to:

**1. Track Key Financial Metrics –** Provide a clear overview of revenue, expenses, profit margins, and other critical financial indicators.

**2. Optimize Business Operations –** Identify cost-saving opportunities, underperforming areas, and operational inefficiencies.

**3. Enhance Financial Planning and Budgeting –** Support data-driven budgeting strategies, resource allocation, and long-term planning for sustainable growth.

## Data Collection 
**The Crunchy Corner Business data contains 47,7872 observations and 30 attributes.**

The Data Dictionary is provided below —
- **Year:** Financial years in which the business operations are recorded (2020 to 2024).
- **Quarter:** Financial quarters (Q1, Q2, Q3, Q4) used for quarterly analysis.
- **Month:** Financial months associated with sales and expenses.
- **Cluster Head:** Key management personnel overseeing operations in specific clusters.
- **SKU Code:** Unique identifier assigned to each product (SKU: Stock Keeping Unit).
- **SKU Description**: A detailed description of the product for identification.
- **Category:** The broad classification of products (e.g., beverages, snacks).
- **Sub Category:** Subdivision within a category (e.g., soft drinks under beverages).
- **Product:** Name of the primary product being sold.
- **Sub Product:** Specific product variations (e.g., flavors, sizes).
- **Channel:** The distribution medium to sell products (e.g., online, retail stores).
- **State:** Geographic states where the business operates.
- **Volume Mt:** Total quantity of SKU sold, measured in metric tons (Mt).
- **Gross Sales:** Total sales revenue generated before deductions like discounts and trade expenses.
- **Discount:** Total discount amount offered on products.
- **Trade Spend:** Funds allocated to trade promotions, such as price reductions or co-op advertising.
- **Total T & Disc:** The combined value of trade spend and discounts.
- **Net Revenue:** Revenue remaining after deducting trade spend and discounts from gross sales.
- **Raw Material:** Cost incurred for procuring raw materials required for production.
- **Packaging Material**: Expenses for packaging the products.
- **Industrial Fixed Cost:** Fixed business operational costs (e.g., rent, salaries).
- **Industrial Variable Cost:** Costs vary with production volume (e.g., utilities, direct labor).
- **COGS:** Cost of Goods Sold, which includes raw material and production costs.
- **Gross Profit:** The profit after deducting COGS from net revenue.
- **GP%:** Gross Profit as a percentage of net revenue, used to assess profitability.
- **Marketing:** Expenditure on marketing and promotional campaigns.
- **S&D:** Sales and distribution costs, including logistics and delivery expenses.
- **Depreciation:** Allocation of the cost of tangible assets over their useful life.
- **One-Off Item:** Exceptional or non-recurring expenses or income items.
- **Tax:** Taxes the business pays, such as income or sales tax.
- **Interest Income:** Income earned from investments or bank accounts.
- **Interest Expense:** Cost of interest paid on loans or borrowed capital.
- **Net Profit:** The final profit after deducting all expenses, taxes, and one-off items from gross profit.

## Data Cleaning 
The data is already clean. We don't need to perform data cleaning. 

## Data Modelling
##  (Star Schema ⭐)
For Crunchy Corner’s extensive dataset, consisting of 2 fact tables and 9 dimension tables, we have implemented the Star Schema approach, which is an effective model for organizing and analyzing large volumes of data.

![image](https://github.com/user-attachments/assets/d0c0cae0-2330-4084-a280-60a867b54924)

## Business Metrics 

## DAX 

**1. Net Revenue (Actual Data)**
```
a NR = SUM(Actual[Net Revenue])
```
**2. Gross Profit (Actual Data)**
```
a GP = SUM(Actual[Gross Profit])
```
**3. Ebitda (Actual Data)**
```
a Ebitda = SUM(Actual[Ebitda])
```
**4. PAT (Profit After TAX / Net Profit for Actual Data)**
```
a PAT = SUM(Actual[Net Profit])
```
**5. Volume (Actual Data)**
```
a vol = SUM(Actual[Volume Mt])
```
**6. Net Revenue (Budget Data)**
```
b NR = SUM(Budget[Net Revenue])
```
**7. Gross Profit (Budget Data)**
```
b Gross Profit = SUM(Budget[Gross Profit])
```
**8. EBITDA (Budget Data)**
```
b Ebitda = SUM(Budget[Ebitda])
```
**9. PAT (Profit After TAX /  Net Profit)**
```
b PAT = SUM(Budget[Net Profit])
```
**10. Volume (Budget Data)**
```
b vol = SUM(Budget[Volume Mt])
```
