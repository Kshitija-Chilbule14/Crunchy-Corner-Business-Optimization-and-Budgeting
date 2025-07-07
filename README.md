# Power BI Case Study: Crunchy Corner's Financial Performance Analysis 🍜
## Table of Contents
- [Project Overview](#project-overview)
- [Objective](#objective)
- [Data Collection](#data-collection)
- [Data Cleaning](#data-cleaning)
- [Data Modelling](#data-modelling)
- [Key Financial Metrics](#key-financial-metrics)
- [DAX](#dax)
- [Dashboard Preview](#dashboard-preview)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)
- [Conclusion](#conclusion)

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

## Key Financial Metrics 
**1. Total Number of SKUs (Stock Keeping Unit):** A unique code given to each product by businesses to help track inventory and manage orders. Crunchy Corner holds the distinction of having the largest SKU variety in the industry.

**2. COGS(Cost of Goods Sold):** COGS represents the direct costs a company pays to make the products it sells, such as raw materials, labor, and production costs. It is subtracted from total sales to find out how much profit the company makes from selling its goods.

**3. Gross Profit (GP):** Gross Profit is the money a company makes from selling its products after subtracting the cost of making those products (COGS). It shows how efficiently the company is producing and selling its goods. Gross Profit is calculated by subtracting the Cost of Goods Sold (COGS) from Net Revenue.

✨Formula:
**GP=Net Revenue−COGS**

**4. Net Revenue:** Net Revenue is the money a company keeps after subtracting costs like marketing, distribution, discounts, and other expenses from its total sales. It gives a clearer picture of the company’s real earnings, which can be used for operations, taxes, and profit.

**Note:** Total revenue is not the same as Net revenue.

Total Revenue refers to the total amount of money a company earns from its sales before any deductions.

Net Revenue is the amount remaining after subtracting different costs. It represents the actual revenue a company retains after these deductions.

**5. EBITDA (Earnings Before Interest, Taxes, Depreciation, and Amortization):** EBITDA is derived by subtracting operating expenses (like selling, marketing, and administrative costs) from Gross Profit. It reflects the company’s profitability from its core operations, excluding non-operational and non-cash items.

✨Formula:
**EBITDA=Gross Profit−Operating Expenses**

**6. PAT (Profit After Tax):** PAT is the final profit figure, showing the earnings available to the shareholders. It is derived by subtracting all non-operating expenses (such as taxes, interest, and depreciation) from EBITDA.

✨Formula:
**PAT=EBITDA−Interest−Taxes−Depreciation and Amortization**

**7. Volume:** Volume refers to the total quantity of products sold or the amount of business activity carried out in a given period. In terms of sales, it indicates how many units of a product were sold, helping to assess market demand and business performance.

**8. Raw Material Cost:** Raw Material Costs for Crunchy Corner include the expenses incurred in procuring the basic ingredients required for food preparation. This includes the cost of fresh produce, meats, packaging materials, spices, and other necessary raw materials to ensure high-quality meals are consistently served to customers.

**9. Trade and Discount Cost:** Trade and Discount Cost refers to the financial outlay Crunchy Corner spends on promotional offers, discounts, and deals to attract customers or partners. This can include seasonal discounts, bundle offers, or loyalty incentives designed to boost sales and customer retention.

**10.Marketing Cost:** Marketing Cost encompasses the expenses Crunchy Corner invests in advertising, brand promotions, digital campaigns, and other marketing activities aimed at raising brand awareness, reaching new customers, and retaining loyal ones. This could include social media ads, TV commercials, billboards, and promotional events.

**11.Fixed and Variable Costs:**

**Fixed Costs:** These are the expenses that do not change regardless of the restaurant’s sales volume. For Crunchy Corner, fixed costs include rent for restaurant locations, salaries for management and permanent staff, and utility bills that are constant over time.

**Variable Costs:** These are expenses that fluctuate depending on the volume of sales. For Crunchy Corner, variable costs include raw materials, and transportation costs that vary based on the number of meals sold and orders processed.

**12. General and Administrative Costs:**
General and Administrative (G&A) Costs for Crunchy Corner involve overhead expenses necessary for running the business. These costs include office expenses, salaries for corporate staff, legal fees, insurance, and other administrative functions that support the overall operations of the company but are not directly tied to food production or sales.

**13. Sales and Distribution Costs:**
Sales and Distribution Costs include the expenses incurred in delivering products to customers and managing sales. This includes the costs of transportation, delivery services, and the expenses related to running the sales process at each restaurant. These costs ensure that products are efficiently distributed to meet customer demand.

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
![1](https://github.com/user-attachments/assets/ea4b6abb-3c08-40c5-b814-45e1d30553a1)

![2](https://github.com/user-attachments/assets/328d4e5a-7e5b-4b26-8292-db03bf469931)

![3](https://github.com/user-attachments/assets/b59d3281-10a8-4fd8-938c-2c64fa0decc1)

![4](https://github.com/user-attachments/assets/cce9b81c-0933-4970-978b-88cd247d9570)


## Key Insights

#### **Year-wise analysis (2020 to 2024):**
- The highest Net Revenue was recorded in the financial year 2023.
- On analyzing the quarterly Net Revenue for 2023, it is clear that the company reached its peak revenue of 30.8M in Quarter 3.
- Within Quarter 3, the month of August stood out, achieving the highest Net Revenue of 12.4M.

**Note:** Below is the visualization chart for the Income Statement Flow from Net Revenue (NR) to Profit After Tax (PAT). This flow outlines how a company’s revenue is transformed into its final profit through the subtraction of various costs and expenses at different levels.

![image](https://github.com/user-attachments/assets/c8d566ce-eb24-48e8-a83b-bcd205792c45)

#### **State-wise Performance:**
Crunchy Corner operates across seven states in India, including Uttar Pradesh (UP), Maharashtra (MH), Gujarat (GUJ), Karnataka, West Bengal (Calcutta), and Tamil Nadu. 

Observations reveal that Uttar Pradesh (UP) contributes the highest Net Revenue of 193.33M, while Tamil Nadu records the lowest Net Revenue contribution of 3.72M among all the states where Crunchy Corner operates.

#### **Distribution Channel Analysis**
Crunchy Corner utilizes nine distinct distribution channels to sell its products: Direct Sales, Bulk Sales, Culinary Service, Distributor, External Sales, Domestic Sales, Online Sales, Others, and MFG Sales. Let’s identify which distribution channel contributes the highest Net Revenue.

As observed, Direct Sales contribute the most to the Net Revenue, followed closely by Bulk Sales.

#### **Cluster Head Analysis**
Crunchy Corner, being a large fast-food distribution chain, assigns Cluster Heads to manage and oversee operations across different regions, ensuring efficient business functioning and optimized performance. Let’s now analyze the Net Revenue by Cluster Heads to gain valuable insights into Crunchy Corner’s overall performance under each cluster head.

It appears that under Cluster Head Umar, the highest Net Revenue is being generated, indicating strong performance and efficient management strategies being implemented by Umar.

#### **Category-wise Analysis**
As Crunchy Corner is a renowned fast-food restaurant chain with the largest SKU base in the industry, it offers products across nine different categories. Let’s now analyze the Net Revenue by SKU category to understand which categories contribute the most to the company’s overall revenue.

As observed, the Protein Pack category generates the highest Net Revenue, followed by Fresh Fare and Country Fries, contributing significantly to Crunchy Corner’s overall revenue.

#### **Cost Analysis**
Now that we’ve completed the analysis of Crunchy Corner’s overall performance, let’s dive deeper into the cost analysis. By examining various costs such as raw material costs, marketing expenses, sales and distribution costs, and fixed and variable costs, we can gain a clearer understanding of the factors impacting profitability. This will allow us to identify areas for cost optimization, improve operational efficiency, and develop strategies to enhance overall financial performance in the long term.

Below is the Cost Analysis Funnel Chart, which visualizes the various costs incurred by Crunchy Corner. The chart breaks down key cost categories, providing a clear view of how expenses.

![image](https://github.com/user-attachments/assets/68d3500e-ec35-4558-b931-1a9f7d4f2ab8)

#### **Marketing Cost Analysis**
As we can observe, the top-performing category, Protein Pack, is also responsible for generating the highest marketing cost, which is in line with the increased efforts to promote and drive sales in this high-revenue category.

#### **Actual VS Budget Insights** 
In this problem statement, we are provided with both actual data and the target/budget of the company. This dual dataset allows us to compare and evaluate the company’s performance against the set goals, identifying any variances. Let’s deep dive into it —

Firstly, let’s analyze YOY Net Revenue for both actual and budget data
```
NR — Net Revenue (Actual)

B NR — Net Revenue (Budget)

YOY NR B% — YOY NR % (Budget)
```
- In 2021 and 2022, the actual NR is closer to the budget, reflecting better alignment with financial projections.
- In 2023, actual NR not only fails to meet the budget but also reflects a dip in performance, as shown by the steep YoY decline.
- 2024 continues to show a gap, but the negative YoY change indicates a gradual performance improvement.

Now, let’s analyze and compare the Year-over-Year (YoY) Net Revenue for actual and budgeted data across categories.
- Protein Pack is the highest revenue-generating category with Actual NR at 221M and Budgeted NR at 259M. However, there is a significant -14.42% YoY decline in Budgeted NR, indicating potential challenges in sustaining growth.
- Fresh Fare and Country Fries categories exhibit modest revenue levels (82M and 76M, respectively), and their YoY Budget NR% % indicates steady growth (+8.57% and +11.81%, respectively).
- Cake and Sweet Crust categories exhibit the lowest net revenue levels with declining YoY Budget percentages of -14.28% and -9.87%, respectively.

## Recommendations
#### 1. The company needs to improve the performance in underperforming regions like Tamil Nadu and certain other states, which showed significantly lower Net Revenue

**Actionable Insights**
- Conduct market surveys to understand customer behavior in these regions.
- Re-evaluate pricing, promotions, and menu localization.
- Pilot targeted campaigns with regional influencers or discounts.

#### 2. Expand high-yield channels such as Bulk Sales and Online Sales, which are contributing significantly to overall revenue.

**Actionable Insights**
- Strengthen logistics and supply chain operations to support bulk orders.
- Enhance the online ordering platform with a personalized user experience and targeted promotions.
- Promote subscription-based meal plans for loyal online customers.

#### 3. Optimize the SKU portfolio by focusing on high-performing categories like Protein Pack and Fresh Fare while eliminating or repackaging low-performing SKUs.

**Actionable Insights**
- Apply Pareto analysis to prioritize top-revenue-generating SKUs.
- Repackage underperforming SKUs into bundled offers to boost appeal.
- Conduct A/B testing to refine product offerings, pricing, and packaging strategies.

#### 4. Control rising costs, especially in Raw Materials and Marketing, which significantly impact profit margins.

**Actionable Insights**
- Negotiate long-term contracts with suppliers for better pricing and supply stability.
- Monitor marketing ROI across channels and redirect budget to high-conversion campaigns.
- Use historical data to improve demand forecasting and reduce excess inventory.

#### 5. Bridge the gap between actual performance and budget forecasts to improve financial planning and agility.

**Actionable Insights**
- Incorporate time-series forecasting models for more accurate projections.
- Implement rolling budgets with quarterly updates based on performance trends.
- Involve cross-functional teams in setting realistic budget targets.

#### 6. Enhance performance tracking and support for regional Cluster Heads to drive consistent growth across regions.

**Actionable Insights**
- Share strategies and practices from high-performing Cluster Heads like Umar.
- Establish a KPI-driven performance incentive plan for all regional managers.
- Conduct regular training sessions on dashboard usage and data interpretation.

## Conclusion
This project delivers actionable insights to help **Crunchy Corner** refine its **business strategies** and maintain its leadership in the fast-food industry.

