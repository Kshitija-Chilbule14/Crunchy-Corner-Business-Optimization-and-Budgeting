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

**1. Net Revenue**
```
a NR = SUM(Actual[Net Revenue])

b NR = SUM(Budget[Net Revenue])

Last Year NR = CALCULATE([a NR],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % NR = DIVIDE(([a NR]-[Last Year NR]),[Last Year NR],0)

NR YTD = TOTALYTD([a NR],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year NR YTD = CALCULATE([NR YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```
**2. Gross Profit**
```
a GP = SUM(Actual[Gross Profit])

b GP = SUM(Budget[Gross Profit])

Last Year GP = CALCULATE([a GP],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % GP = DIVIDE(([a GP]-[Last Year GP]),[Last Year GP],0)

GP YTD = TOTALYTD([a GP],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year GP YTD = CALCULATE([GP YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```
**3. Ebitda**
```
a Ebitda = SUM(Actual[Ebitda])

b Ebitda = SUM(Budget[Ebitda])

Last Year EBITDA = CALCULATE([a Ebitda],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % EBITDA = DIVIDE(([a Ebitda]-[Last Year EBITDA]),[Last Year EBITDA],0)

EBITDA YTD = TOTALYTD([a Ebitda],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year EBITDA YTD = CALCULATE([EBITDA YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```
**4. PAT (Profit After TAX / Net Profit)**
```
a PAT = SUM(Actual[Net Profit])

b PAT = SUM(Budget[Net Profit])

Last Year PAT = CALCULATE([a PAT],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % PAT = DIVIDE(([a PAT]-[Last Year PAT]),[Last Year PAT],0)

PAT YTD = TOTALYTD([a PAT],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year PAT YTD = CALCULATE([PAT YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```
**5. Volume**
```
a vol = SUM(Actual[Volume Mt])
```
**6. Total Number of SKUs**
```
No. of SKU = CALCULATE(COUNT(Dim_Product[Product_Id]))
```

