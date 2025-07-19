# Power BI Case Study: Crunchy Corner's Business Optimization and Budgeting 🍜

## For the Comprehensive Insights of the project, please read full [Medium Blog Here](https://medium.com/@kshitijachilbule01/optimizing-business-and-budgeting-strategies-for-crunchy-corner-5f96fae11eca)

## Project Overview
Crunchy Corner, one of India’s largest fast-food restaurant chains, serves millions daily through its 1,000+ outlets across the country. Renowned for offering the largest SKU variety in the industry, Crunchy Corner strives to maintain profitability, enhance efficiency, and deliver exceptional value to its customers. 

This project analyzes Crunchy Corner's business data from 2020 to 2024 to identify financial challenges, optimize operations, and ensure sustainable growth through data-driven insights.

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

b vol = SUM(Budget[Volume Mt])

Last Year VOL = CALCULATE([a vol],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % VOL = DIVIDE(([a vol]-[Last Year VOL]),[Last Year VOL],0)

VOL YTD = TOTALYTD([a vol],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year VOL YTD = CALCULATE([VOL YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```
**6. Total Number of SKUs**
```
No. of SKU = CALCULATE(COUNT(Dim_Product[Product_Id]))

Last Year SKU = CALCULATE([No. of SKU],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % SKU = DIVIDE(([No. of SKU]-[Last Year SKU]),[Last Year SKU],0)

SKU YTD = TOTALYTD([No. of SKU],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year SKU YTD = CALCULATE([SKU YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```

**7. Raw Material Cost**
```
RM = CALCULATE(SUM(Actual[Raw Material]))*-1

Last Year RM = CALCULATE([a RM],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % RM = DIVIDE(([a RM]-[Last Year RM]),[Last Year RM],0)

RM YTD = TOTALYTD([a RM],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year RM YTD = CALCULATE([RM YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```

**8. Trade and Discount**
```
Trade & Disc = CALCULATE(SUM(Actual[Total T & Disc])*-1)

Last Year T&D = CALCULATE([a Trade & Disc],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % T&D = DIVIDE(([a Trade & Disc]-[Last Year T&D]),[Last Year T&D],0)

T&D YTD = TOTALYTD([a Trade & Disc],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year T&D YTD = CALCULATE([T&D YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```

**9. Marketing Cost**

```
a Mkt = CALCULATE(SUM(Actual[Marketing])*-1)

Last Year MKT = CALCULATE([a Mkt],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % MKT = DIVIDE(([a Mkt]-[Last Year MKT]),[Last Year MKT],0)

MKT YTD = TOTALYTD([a Mkt],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year MKT YTD = CALCULATE([MKT YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```

**10. Fixed and Variable Cost**
```
a F&V = CALCULATE(SUM(Actual[Total Fixed & Variable Cost])*-1)

Last Year F&V = CALCULATE([a F&V],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % F&V = DIVIDE(([a F&V Cost]-[Last Year F&V]),[Last Year F&V],0)

F&V YTD = TOTALYTD([a F&V Cost],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year F&V YTD = CALCULATE([F&V YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```

**11. General and Administrative Cost**
```
a g&a = SUM(Actual[G&A])*-1

Last Year G&A = CALCULATE([a g&a],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % G&A = DIVIDE(([a g&a]-[Last Year G&A]),[Last Year G&A],0)

G&A YTD = TOTALYTD([a g&a],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year G&A YTD = CALCULATE([G&A YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```

**12. Sales and Distribution Cost**
```
a s&d Cost = SUM(Actual[S&D])*-1

Last Year S&D = CALCULATE([a s&d],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))

YoY % S&D = DIVIDE(([a s&d]-[Last Year S&D]),[Last Year S&D],0)

S&D YTD = TOTALYTD([a s&d],Dim_Date[Month End_Date],ALL(Dim_Date))

Last Year S&D YTD = CALCULATE([S&D YTD],SAMEPERIODLASTYEAR(Dim_Date[Month End_Date].[Date]))
```

## Dashboard Preview
![Crunchy Corner Business Optimization and Budgeting_page-0001](https://github.com/user-attachments/assets/dd289214-c400-41e4-a1c5-2ba8c95f74f7)

![Crunchy Corner Business Optimization and Budgeting_page-0002](https://github.com/user-attachments/assets/8ec4bc54-4d47-43e9-96fe-151483317b46)

![Crunchy Corner Business Optimization and Budgeting_page-0003](https://github.com/user-attachments/assets/e95f0c3b-cfe4-43a1-b673-8a1c02b0cd20)

![Crunchy Corner Business Optimization and Budgeting_page-0004](https://github.com/user-attachments/assets/fe775e17-30ff-459c-88c4-4f13fa69e20f)

![Crunchy Corner Business Optimization and Budgeting_page-0005](https://github.com/user-attachments/assets/ff8b04de-04c1-4c37-bd58-72966089caa2)

![Crunchy Corner Business Optimization and Budgeting_page-0006](https://github.com/user-attachments/assets/243dd908-dab3-4ad9-9005-74c3c4988e09)

![Crunchy Corner Business Optimization and Budgeting_page-0007](https://github.com/user-attachments/assets/92f9dd7d-38e1-4c4d-b411-17ea93c184d3)

![Crunchy Corner Business Optimization and Budgeting_page-0008](https://github.com/user-attachments/assets/9cc192c5-25ee-49b0-be58-3e60cac3bf20)
