# Customer Purchase Behaviour Analysis Using Electronic Sales Data

## Executive Summary

Customer behaviour analysis plays a critical role in helping organizations understand purchasing patterns, optimize business strategies, and improve customer satisfaction. This project presents a comprehensive analysis of electronic sales transactions recorded between September 2023 and September 2024.

The primary objective of this project is to explore customer purchasing behaviour, identify key sales trends, evaluate product performance, understand customer demographics, and generate actionable business insights that can support strategic decision-making.

Using Python and various data analytics techniques, the project covers data cleaning, feature engineering, exploratory data analysis (EDA), visualization, correlation analysis, and outlier detection. The analysis transforms raw transactional data into meaningful business intelligence that can assist stakeholders in improving marketing effectiveness, customer engagement, inventory management, and overall sales performance.

---

## Project Impact

This analysis transformed 20,000 raw transaction records into actionable business insights that can support customer retention, marketing optimization, inventory planning, and revenue growth.

The project identified:

- High-value customer segments responsible for the largest share of revenue.
- Product categories driving customer demand and satisfaction.
- Opportunities to improve loyalty program effectiveness.
- Key factors influencing customer spending behaviour.
- Strategic actions that can support long-term business growth.

By leveraging data analytics techniques, the project demonstrates how transactional data can be converted into meaningful business intelligence for decision-making.

---

# Business Problem

Modern retail businesses generate large volumes of transactional data every day. However, without proper analysis, organizations struggle to extract meaningful insights that can support business growth.

This project seeks to answer several important business questions:

* Which products are most popular among customers?
* Which customer segments generate the highest revenue?
* How does customer age influence purchasing behaviour?
* Are there noticeable differences in purchasing behaviour across genders?
* How effective is the loyalty membership program?
* Which products achieve the highest customer satisfaction ratings?
* What factors influence overall customer spending?

By answering these questions, businesses can better understand customer needs and make informed decisions to improve performance.

---

# Project Objectives

The key objectives of this project are:

* Analyze customer demographics and purchasing behaviour.
* Identify top-performing product categories.
* Evaluate customer satisfaction using product ratings.
* Examine spending behaviour across different age groups.
* Investigate sales performance trends over time.
* Analyze loyalty membership participation and its impact on sales.
* Explore relationships between key numerical variables.
* Detect unusual purchasing behaviour through outlier analysis.
* Generate business recommendations based on analytical findings.

---

# Dataset Overview

The dataset contains 20,000 electronic sales transactions recorded between September 2023 and September 2024.

Each transaction contains information related to customers, products, purchases, ratings, payment methods, shipping preferences, and loyalty membership.

### Dataset Features

| Feature           | Description                   |
| ----------------- | ----------------------------- |
| Customer ID       | Unique customer identifier    |
| Age               | Customer age                  |
| Gender            | Customer gender               |
| Loyalty Member    | Membership status             |
| Product Type      | Product category purchased    |
| SKU               | Product identifier            |
| Rating            | Customer rating               |
| Order Status      | Completed or Cancelled        |
| Payment Method    | Payment option selected       |
| Quantity          | Number of products purchased  |
| Unit Price        | Price per item                |
| Total Price       | Total transaction value       |
| Purchase Date     | Date of purchase              |
| Shipping Type     | Delivery method               |
| Add-ons Purchased | Additional products purchased |
| Add-on Total      | Cost of add-ons               |

### Dataset Source

Electronic Sales Dataset (Kaggle) https://www.kaggle.com/datasets/cameronseamons/electronic-sales-sep2023-sep2024

---

## Key Results at a Glance

| Area | Key Finding |
|--------|------------|
| Product Performance | Smartphones were the most purchased and highest-rated products |
| Customer Demographics | Customer distribution was balanced across genders |
| Revenue Contribution | Customers aged 31–70 generated the highest sales |
| Loyalty Program | Non-loyalty members generated higher total sales |
| Revenue Drivers | Unit Price and Quantity strongly influenced Total Price |
| Customer Satisfaction | Product ratings remained consistently positive |
| Outlier Analysis | High-value transactions indicate premium customer segments |

---

# Tools and Technologies

### Programming Language

* Python

### Development Environment

* Google Colab

### Libraries Used

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn

---

# Project Workflow

The project was completed using the following analytical framework:

1. Data Collection and Understanding
2. Data Cleaning
3. Feature Engineering
4. Exploratory Data Analysis (EDA)
5. Data Visualization
6. Correlation Analysis
7. Outlier Detection
8. Business Insight Generation
9. Recommendation Development

---

# Data Cleaning

Data cleaning was performed to improve data quality and ensure reliable analytical outcomes.

## Missing Value Analysis

The dataset was inspected for missing values using:

```python
df.isnull().sum()
```

Missing values were identified in the following columns:

### Gender

Missing values were replaced using the most frequently occurring category (mode).

```python
df['Gender'].fillna(df['Gender'].mode()[0], inplace=True)
```

**Reason**

Gender is a categorical variable, and replacing missing values with the mode helps preserve the original distribution of customer demographics.

---

### Add-ons Purchased

Missing values were replaced with "None".

```python
df['Add-ons Purchased'].fillna('None', inplace=True)
```

**Reason**

Missing values represented customers who did not purchase additional products.

---

## Data Validation

Following the cleaning process:

* Missing values were eliminated.
* Data types were verified.
* Dataset consistency was confirmed.

Result:

✔ Clean dataset with no remaining missing values.

---

# Feature Engineering

Additional variables were created to improve analytical depth.

## Age Group Creation

Customers were categorized into the following age groups:

* 0–10
* 11–20
* 21–30
* 31–40
* 41–50
* 51–60
* 61–70
* 71–80
* 81–90
* 91–100

Purpose:

* Customer segmentation
* Spending behaviour analysis
* High-value customer identification

---

## Date Transformation

Purchase Date was converted into datetime format.

```python
df['Purchase Date'] = pd.to_datetime(df['Purchase Date'])
```

---

## Time-Based Features

Two additional variables were created:

### Year-Month

Used to analyze monthly sales trends.

### Weekday

Used to analyze purchasing behaviour across different days of the week.

---

# Exploratory Data Analysis and Visual Insights

## 1. Gender Distribution

![Gender Distribution](visualizations/gender_distribution.png)

### Objective

To understand the demographic composition of the customer base.

### Analysis

The visualization indicates that the customer base is almost equally distributed between male and female customers.

### Business Insight

The balanced distribution suggests that electronic products appeal broadly across genders.

### Recommendation

Marketing campaigns should maintain inclusive targeting strategies rather than focusing heavily on a single gender segment.

---

## 2. Monthly Sales Trend

![Monthly Sales Trend](visualizations/monthly_sales_trend.png)

### Objective

To analyze sales performance over time.

### Analysis

Sales fluctuated throughout the year, with several months exhibiting significantly higher revenue than others.

### Business Insight

These fluctuations suggest seasonal demand patterns and periods of increased purchasing activity.

### Recommendation

Businesses should leverage historical sales patterns to improve inventory management and demand forecasting.

---

## 3. Product Purchases by Gender

![Product Purchases by Gender](visualizations/product_purchases_by_gender.png)

### Objective

To compare product preferences across genders.

### Analysis

Smartphones emerged as the most purchased product category among both male and female customers.

### Business Insight

Customer demand for smartphones remains consistently high across demographic groups.

### Recommendation

Organizations should prioritize smartphone-related promotions and maintain sufficient inventory levels.

---

## 4. Spending Behaviour by Age Group

![Spending Behaviour by Age Group](visualizations/total_spending_by_age_group.png)

### Objective

To identify high-value customer segments.

### Analysis

Customers aged between 31 and 70 generated the highest overall revenue.

### Business Insight

Middle-aged customers represent the most valuable customer segment in terms of purchasing power.

### Recommendation

Targeted marketing campaigns and loyalty programs should focus on these age groups.

---

## 5. Sales by Gender and Loyalty Membership

![Sales by Gender and Loyalty Membership](visualizations/sales_by_gender_loyalty_membership.png)

### Objective

To evaluate the impact of loyalty membership on sales.

### Analysis

Non-loyalty members generated significantly higher total sales than loyalty members.

### Business Insight

Current loyalty program participation may not be sufficiently attractive to customers.

### Recommendation

Review membership benefits and introduce personalized incentives to increase engagement.

---

## 6. Average Product Rating Analysis

![Average Rating by Product](visualizations/average_rating_by_product.png)

### Objective

To evaluate customer satisfaction across product categories.

### Analysis

Smartphones achieved the highest average customer rating.

### Business Insight

Customers appear highly satisfied with smartphone purchases.

### Recommendation

Promote highly rated products using customer testimonials and review-based marketing strategies.

---

## 7. Correlation Heatmap

![Correlation Heatmap](visualizations/correlation_heatmap.png)

### Objective

To identify relationships between numerical variables.

### Analysis

Strong positive relationships were observed between:

* Unit Price and Total Price
* Quantity and Total Price

A moderate negative relationship was observed between Rating and Unit Price.

### Business Insight

Revenue is primarily influenced by pricing and purchase volume.

### Recommendation

Pricing strategies and product bundling initiatives can be optimized to maximize revenue generation.

---

## 8. Outlier Detection Analysis

![Outlier Detection](visualizations/outlier_detection_boxplot.png)

### Objective

To identify unusual purchasing behaviour and extreme transaction values.

### Analysis

Outliers were detected in Total Price and Add-on Total variables.

### Business Insight

These observations may represent premium purchases, high-value customers, or exceptional transactions.

### Recommendation

Further investigation of high-value transactions may help identify profitable customer segments.

---

# Key Findings

The analysis produced several important findings:

* Smartphones are the most purchased product category.
* Smartphones received the highest average customer ratings.
* Customer purchasing behaviour is balanced across genders.
* Customers aged 31–70 contribute the largest share of revenue.
* Loyalty membership participation appears relatively low.
* Pricing and quantity purchased strongly influence total spending.
* Customer satisfaction remains positive across most product categories.
* Significant sales fluctuations occur throughout the year.

---

# Strategic Business Recommendations

Based on the analysis of customer purchasing behaviour, sales trends, customer demographics, product performance, customer satisfaction, and loyalty membership participation, the following strategic recommendations are proposed.

---

## 1. Redesign and Strengthen the Loyalty Program

### Observation

The analysis revealed that non-loyalty members generated significantly higher sales compared to loyalty members.

### Business Impact

This suggests that the current loyalty program may not be delivering sufficient value to encourage customer participation and repeat purchases.

### Recommendation

The organization should redesign the loyalty program by introducing:

* Personalized rewards and offers
* Tier-based membership levels
* Exclusive member discounts
* Reward points for repeat purchases
* Early access to product launches and promotions

### Expected Benefits

* Increased customer retention
* Higher repeat purchase rates
* Improved customer lifetime value
* Greater customer engagement

---

## 2. Prioritize High-Value Customer Segments

### Observation

Customers aged between 31 and 70 generated the highest overall revenue.

### Business Impact

These customers represent the most profitable segment and contribute significantly to business performance.

### Recommendation

Develop targeted marketing campaigns specifically for high-value age groups through:

* Personalized email campaigns
* Product recommendations
* Exclusive promotions
* Premium product bundles

### Expected Benefits

* Increased conversion rates
* Higher average order values
* Improved return on marketing investment

---

## 3. Expand Smartphone-Focused Sales Strategies

### Observation

Smartphones were identified as both the most purchased and highest-rated product category.

### Business Impact

Smartphones represent a major revenue driver and customer preference.

### Recommendation

Increase smartphone-focused business initiatives including:

* Smartphone upgrade programs
* Trade-in offers
* Smartphone and accessory bundles
* Promotional campaigns around flagship devices

### Expected Benefits

* Increased sales revenue
* Improved customer satisfaction
* Higher cross-selling opportunities

---

## 4. Improve Demand Forecasting and Inventory Management

### Observation

Monthly sales trends revealed significant fluctuations throughout the year, indicating periods of increased demand.

### Business Impact

Inaccurate inventory planning during peak demand periods can lead to stock shortages, lost sales opportunities, and customer dissatisfaction.

### Recommendation

Utilize historical sales data to:

* Forecast future demand
* Identify seasonal purchasing patterns
* Optimize inventory replenishment schedules
* Improve supply chain planning

### Expected Benefits

* Reduced stock shortages
* Improved product availability
* Better inventory utilization
* Enhanced customer experience

---

## 5. Implement Data-Driven Customer Segmentation

### Observation

Customers exhibit different spending patterns based on age, purchasing behaviour, and product preferences.

### Business Impact

A single marketing strategy may not effectively address the needs of all customer groups.

### Recommendation

Segment customers based on:

* Age groups
* Purchase frequency
* Spending behaviour
* Product preferences
* Loyalty membership status

Develop personalized campaigns for each segment.

### Expected Benefits

* Increased customer engagement
* Higher marketing effectiveness
* Improved customer retention

---

## 6. Leverage Customer Ratings and Feedback

### Observation

Smartphones achieved the highest customer satisfaction ratings among all product categories.

### Business Impact

Positive customer reviews and ratings influence purchasing decisions and strengthen brand credibility.

### Recommendation

Use customer ratings and reviews within:

* Product pages
* Marketing campaigns
* Social media promotions
* Email marketing communications

### Expected Benefits

* Increased customer trust
* Higher conversion rates
* Stronger brand reputation

---

## 7. Develop Cross-Selling and Upselling Opportunities

### Observation

The dataset includes add-on purchases, indicating opportunities for customers to purchase complementary products.

### Business Impact

Customers purchasing primary products are often willing to purchase related accessories and services.

### Recommendation

Implement recommendation systems that promote:

* Product accessories
* Extended warranties
* Product bundles
* Complementary electronic devices

### Expected Benefits

* Increased average transaction value
* Higher revenue per customer
* Improved product attachment rates

---

## 8. Monitor High-Value Transactions and Premium Customers

### Observation

Outlier analysis identified unusually high transaction values within the dataset.

### Business Impact

These transactions may represent premium customers, bulk purchases, or highly profitable customer segments.

### Recommendation

Develop a dedicated strategy for high-value customers through:

* VIP customer programs
* Premium loyalty benefits
* Personalized customer support
* Exclusive promotional offers

### Expected Benefits

* Increased retention of premium customers
* Higher customer lifetime value
* Improved long-term profitability

---

## 9. Establish a Data-Driven Decision-Making Framework

### Observation

The analysis demonstrates the value of leveraging transaction data to understand customer behaviour and business performance.

### Business Impact

Organizations that utilize analytics effectively are better positioned to respond to market changes and customer needs.

### Recommendation

Develop business intelligence dashboards and reporting systems to continuously monitor:

* Sales performance
* Customer behaviour
* Product performance
* Customer satisfaction
* Loyalty program effectiveness

### Expected Benefits

* Faster decision-making
* Improved strategic planning
* Better operational efficiency
* Sustainable business growth

---

## Strategic Conclusion

The analysis demonstrates that customer purchasing behaviour is influenced by product preferences, demographic characteristics, pricing, and purchasing patterns. By strengthening loyalty initiatives, focusing on high-value customer segments, optimizing inventory planning, leveraging customer feedback, and adopting data-driven decision-making practices, organizations can improve customer satisfaction, increase revenue, and achieve long-term competitive advantage.

The insights generated from this project provide a foundation for developing targeted business strategies that support sustainable growth and enhanced customer engagement.

---

# Skills Demonstrated

This project demonstrates proficiency in:

### Data Analytics

* Data Cleaning
* Feature Engineering
* Exploratory Data Analysis
* Statistical Analysis
* Correlation Analysis
* Outlier Detection

### Data Visualization

* Bar Charts
* Line Charts
* Heatmaps
* Box Plots

### Python Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn

### Business Analytics

* Customer Behaviour Analysis
* Sales Trend Analysis
* Customer Segmentation
* Business Intelligence
* Strategic Recommendation Development

---

# Repository Structure

```text
customer-purchase-behaviour-electronic-sales/

├── data/
├── notebooks/
├── reports/
├── visualizations/
├── README.md
├── requirements.txt
└── LICENSE
```

---
