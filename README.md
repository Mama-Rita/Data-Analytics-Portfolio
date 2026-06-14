# Customer Retention and Revenue Analysis

### Table of contents
- [Project Overview](project-overview)
- [Data Source](data-source)
- [Tools](tools)
- [Data Cleaning/Preparation](data-cleaning/preparation)
- [Exploratory Data Analysis](exploratory-data-analysis)
- [Data Analysis](data-analysis)
- [Results/Findings](results/findings)
- [Recommendation](recommendation)
- [Limitations](limitations)

## Project Overview

This project focuses on analyzing customer churn behavior and its impact on revenue performance in a telecom company. The goal is to identify key drivers of customer churn, measure the financial impact of lost customers, and provide actionable insights to improve customer retention and revenue optimization.

## Data Source

Telecom customer churn Data: The primary Dataset for this analysis is the "telecom_customer_churn.csv" file containing customer demographics, subscription details, service usage patterns, billing information, and churn indicators.

## Tools

- Microsoft Excel - Data Cleaning and Initial Exploration
- PowerBI - Data modelling and Data Visualisation
- DAX(Data Analysis Expressions) - Custom measures for churn and revenue analysis

## Data Cleaning/Preparation

In the initial Data Preparation Phase, I performed the Following Tasks;
1. Data Loading and Inspection
2. Handling Missing Values
3. Checking for Duplicates
4. Data Cleaning and Formatting

## Exploratory Data Analysis

EDA Involved Exploring the Telecom customer churn Data to answer key questions such as;
- What is the overall churn rate?
- How much revenue is lost due to churn?
- Which customer segment is most likely to churn?

## Data Analysis

To Calculate Revenue lost, I used this DAX measure,

```DAX
Revenue Lost (Churned) = 
CALCULATE(
    [Total Revenue],
    'telecom customer'[Customer Status] = "churned"
)
```

To calculate Churned Customers, I used this DAX measure,

```DAX
Churned Customers = 
CALCULATE(
    COUNTROWS('telecom customer'),
    'telecom customer'[Customer Status] = "churned"
)
```

### Results/Findings

The analysis results are summarised as follows;
1. Month-to-month customers show significantly higher churn rates
2. Higher monthly charges are associated with increased churn likelihood
3. A large portion of churn is driven by competitor-related factors
4. High-value customers contribute disproportionately to revenue loss when they churn

### Recommendations
Based on the analysis, I recommend the following actions;
- If 30% of churned month-to-month customers are retained through long-term contract incentives, approximately 759 customers could be saved, resulting in an estimated ₦ 2.3 million in retained revenue
- Improve service quality in areas linked to top churn reasons
- Optimize pricing strategies for high-churn customer segments

### Limitations
- I handled missing values using standard imputation approaches (such as replacing them with 0 or Null where appropriate), which may have introduced slight bias into some calculations and analyses.
- I was limited to the customer service, demographic, and billing information available in the dataset. The absence of deeper interaction data, such as customer support history, complaint records, or application usage patterns, restricted the depth of my analysis of customer behavior and churn drivers.






























