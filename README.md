# Credit Card Financial Dashboard Project

## Overview

This project provides a comprehensive analysis of credit card customer and transaction data using interactive dashboards. The goal is to deliver actionable insights into key performance metrics and trends, enabling stakeholders to monitor and analyze credit card operations effectively.

## Data Sources

- **Customer Data**: Demographic, financial, and satisfaction information for each cardholder.
- **Credit Card Details**: Card type, annual fees, activation status, credit limits, and delinquency records.
- **Transaction Data**: Weekly transaction amounts, counts, interest earned, and expenditure types.
- **Supplementary Reports**: Aggregated dashboards and summary PDFs for financial and operational overview.

## Project Objectives

- Develop an interactive dashboard for real-time insights.
- Monitor key metrics such as revenue, transaction volume, customer acquisition, and delinquency.
- Analyze trends by customer segment, card type, region, and time period.
- Support data-driven decision-making for stakeholders.

## Data Structure

### 1. Customer Information

| Field                | Description                                   |
|----------------------|-----------------------------------------------|
| Client_Num           | Unique customer identifier                    |
| Customer_Age         | Age of the customer                           |
| Gender               | Gender (M/F)                                  |
| Dependent_Count      | Number of dependents                          |
| Education_Level      | Highest education attained                    |
| Marital_Status       | Marital status                                |
| State/Zipcode        | Location details                              |
| Car_Owner            | Car ownership status                          |
| House_Owner          | House ownership status                        |
| Personal_loan        | Personal loan status                          |
| Customer_Job         | Occupation                                    |
| Income               | Annual income                                 |
| Cust_Satisfaction_Score | Customer satisfaction (1-5)                |

### 2. Credit Card Details

| Field                | Description                                   |
|----------------------|-----------------------------------------------|
| Card_Category        | Card type (Blue, Silver, Gold, Platinum)      |
| Annual_Fees          | Yearly fee for the card                       |
| Activation_30_Days   | Whether activated within 30 days (1/0)        |
| Customer_Acq_Cost    | Cost to acquire the customer                  |
| Credit_Limit         | Maximum credit limit                          |
| Total_Revolving_Bal  | Revolving balance                             |
| Delinquent_Acc       | Delinquency flag (1/0)                        |

### 3. Transaction Data

| Field                | Description                                   |
|----------------------|-----------------------------------------------|
| Week_Start_Date      | Start date of the transaction week            |
| Week_Num             | Week number                                   |
| Qtr                  | Quarter                                       |
| Total_Trans_Amt      | Total transaction amount                      |
| Total_Trans_Ct       | Total transaction count                       |
| Avg_Utilization_Ratio| Average utilization of credit                 |
| Use Chip             | Transaction method (Swipe/Chip/Online)        |
| Exp Type             | Expenditure type (Fuel, Food, Bills, etc.)    |
| Interest_Earned      | Interest earned on transactions               |

## Key Metrics & Insights

- **Total Revenue (2023):** 57M
- **Total Interest Earned:** 8M
- **Total Transaction Amount:** 46M
- **Transaction Count:** 657K (Q4)
- **Overall Activation Rate:** 57.5%
- **Overall Delinquency Rate:** 6.06%
- **Top Performing Card Types:** Blue & Silver (93% of transactions)
- **Top States by Revenue:** TX, NY, CA (68% combined contribution)
- **Revenue by Gender:** Male (31M), Female (26M)
- **Revenue by Age Group:** Highest in 20-30 and 40-50 segments
- **Revenue by Occupation:** Businessman and Selfemployeed are top contributors

## Project Workflow

1. **Data Preparation**
    - Clean and preprocess CSV files.
    - Merge customer and transaction datasets using `Client_Num`.
2. **Database Integration**
    - Import data into SQL database.
    - Create tables for customer and transaction details.
3. **Dashboard Development**
    - Use Power BI to visualize key metrics and trends.
    - Implement DAX queries for custom calculations (e.g., revenue, week-over-week changes).
4. **Analysis & Reporting**
    - Generate weekly and quarterly reports.
    - Identify actionable insights for business stakeholders.

## Sample DAX Calculations

- **Age Grouping:**
  ```dax
  AgeGroup = SWITCH(
      TRUE(),
      [customer_age] = 30 && [customer_age] = 40 && [customer_age] = 50 && [customer_age] = 60, "60+",
      "unknown"
  )
  ```
- **Income Grouping:**
  ```dax
  IncomeGroup = SWITCH(
      TRUE(),
      [income] = 35000 && [income] = 70000, "High",
      "unknown"
  )
  ```
- **Revenue Calculation:**
  ```dax
  Revenue = [annual_fees] + [total_trans_amt] + [interest_earned]
  ```

## Example Insights 


  - Revenue increased by 28.8% week-over-week.
  - Transaction amount and count both showed significant growth.
  - Customer count also increased.

- **Year-to-Date:**
  - Blue and Silver cards dominate the market.
  - Activation and satisfaction rates are key drivers for revenue.
  - Delinquency remains low but should be monitored.

## How to Use

1. **Clone or Download the Data**
    - Data available on GitHub and Google Drive.
2. **Import to SQL**
    - Use provided SQL scripts to create and populate tables.
3. **Power BI Dashboard**
    - Import data and use DAX queries for custom metrics.
    - Explore interactive visuals for deep-dive analysis.
4. **Update & Share**
    - Refresh data weekly for real-time insights.
    - Export dashboards and reports for stakeholders.




