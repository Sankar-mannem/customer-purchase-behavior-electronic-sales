# Customer Purchase Behaviour Analysis Using Electronic Sales Data

## Project Overview

This project presents an end-to-end Exploratory Data Analysis (EDA) of customer purchase behaviour using an Electronic Sales dataset containing 20,000 transactions recorded between September 2023 and September 2024.

The objective of the analysis is to understand customer demographics, purchasing patterns, product performance, sales trends, customer satisfaction, and loyalty program participation. The insights generated from this analysis can support data-driven business decisions in areas such as marketing, customer retention, inventory management, and sales optimization.

This project demonstrates practical Data Analytics skills including data cleaning, feature engineering, data visualization, correlation analysis, outlier detection, and business insight generation.

---

# Business Problem

Retail organizations collect large volumes of transactional data every day. However, raw data alone cannot help businesses understand customer behaviour or improve decision-making.

This analysis aims to answer the following business questions:

* Which products generate the highest customer demand?
* Which customer age groups contribute the most revenue?
* How do customer demographics influence purchasing behaviour?
* What role does loyalty membership play in sales performance?
* Which products receive the highest customer satisfaction ratings?
* What factors influence customer spending?

The results of this analysis can help businesses improve customer engagement, marketing strategies, and operational planning.

---

# Dataset Information

The dataset contains electronic product sales transactions recorded over a one-year period.

### Dataset Features

| Feature           | Description                       |
| ----------------- | --------------------------------- |
| Customer ID       | Unique customer identifier        |
| Age               | Customer age                      |
| Gender            | Customer gender                   |
| Loyalty Member    | Loyalty program membership status |
| Product Type      | Product category purchased        |
| Rating            | Customer satisfaction rating      |
| Order Status      | Completed or cancelled order      |
| Payment Method    | Payment option selected           |
| Quantity          | Number of products purchased      |
| Unit Price        | Price per product                 |
| Total Price       | Total transaction amount          |
| Purchase Date     | Date of purchase                  |
| Shipping Type     | Delivery method                   |
| Add-ons Purchased | Additional products purchased     |
| Add-on Total      | Additional purchase amount        |

### Tools and Technologies

* Python
* Google Colab
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn

---

# Project Workflow

The project was completed using the following analytical workflow:

1. Data Loading and Inspection
2. Data Cleaning
3. Feature Engineering
4. Exploratory Data Analysis
5. Data Visualization
6. Correlation Analysis
7. Outlier Detection
8. Business Insight Generation
9. Business Recommendations

---

# Data Cleaning

Data cleaning was performed to improve data quality and ensure reliable analysis.

### Handling Missing Values

#### Gender Column

Missing values in the Gender column were replaced using the mode (most frequently occurring value).

```python
df['Gender'].fillna(df['Gender'].mode()[0], inplace=True)
```

Reason:

* Gender is a categorical variable.
* Mode imputation preserves the overall distribution of the data.

#### Add-ons Purchased Column

Missing values in the Add-ons Purchased column were replaced with "None".

```python
df['Add-ons Purchased'].fillna('None', inplace=True)
```

Reason:

* Missing values represented customers who did not purchase any additional products.

### Data Validation

The following checks were performed:

* Dataset structure inspection
* Missing value analysis
* Data type verification
* Statistical summary generation

Result:

✔ Dataset successfully cleaned with no remaining missing values.

---

# Feature Engineering

To improve analysis quality, several new features were created.

### Age Group Creation

Customers were grouped into meaningful age categories:

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

* Compare spending patterns across age groups.
* Identify high-value customer segments.

### Purchase Date Transformation

The Purchase Date column was converted into datetime format.

```python
df['Purchase Date'] = pd.to_datetime(df['Purchase Date'])
```

### Time-Based Features

Two additional variables were created:

* Year-Month
* Weekday

Purpose:

* Analyze monthly sales trends.
* Study customer purchasing behaviour over time.

---

# Exploratory Data Analysis and Visualizations

## 1. Gender Distribution

![Gender Distribution](visualizations/02_gender_distribution.png)

### Insight

The customer base is nearly equally distributed between male and female customers, indicating that electronic products appeal broadly across genders.

### Business Value

Supports the development of inclusive marketing strategies that target both customer groups effectively.

---

## 2. Monthly Sales Trend

![Monthly Sales Trend](visualizations/06_monthly_sales_trend.png)

### Insight

Sales showed significant variation throughout the year, with noticeable peaks during high-demand periods.

### Business Value

Helps businesses forecast demand, optimize inventory levels, and prepare for seasonal sales fluctuations.

---

## 3. Product Purchases by Gender

![Product Purchases by Gender](visualizations/09_product_purchases_by_gender.png)

### Insight

Smartphones emerged as the most purchased product category for both male and female customers.

### Business Value

Provides valuable information for product promotion and targeted marketing campaigns.

---

## 4. Spending Behaviour by Age Group

![Spending Behaviour by Age Group](visualizations/08_total_spending_by_age_group.png)

### Insight

Customers between 31 and 70 years old contributed the highest overall revenue.

### Business Value

Identifies high-value customer segments that should be prioritized in customer acquisition and retention strategies.

---

## 5. Sales by Gender and Loyalty Membership

![Sales by Gender and Loyalty Membership](visualizations/12_sales_by_gender_loyalty_membership.png)

### Insight

Non-loyalty members generated higher total sales than loyalty members.

### Business Value

Highlights an opportunity to redesign loyalty programs and improve customer engagement.

---

## 6. Average Product Rating Analysis

![Average Rating by Product](visualizations/11_average_rating_by_product.png)

### Insight

Smartphones received the highest average customer rating, indicating strong customer satisfaction.

### Business Value

High-rated products can be leveraged in marketing campaigns to build customer trust and increase sales.

---

## 7. Correlation Heatmap

![Correlation Heatmap](visualizations/13_correlation_heatmap.png)

### Insight

Strong positive relationships were observed between:

* Unit Price and Total Price
* Quantity and Total Price

### Business Value

Demonstrates that pricing and purchase quantity are key drivers of sales revenue.

---

## 8. Outlier Analysis

![Outlier Detection](visualizations/15_outlier_detection_boxplot.png)

### Insight

Outliers were identified in transaction values and add-on purchases.

### Business Value

Helps identify unusual purchasing behaviour, premium customers, and potential anomalies within the dataset.

---

# Key Business Insights

The analysis produced several important findings:

* Smartphones are the most purchased product category.
* Smartphones also received the highest average customer ratings.
* Customer purchasing behaviour is balanced across genders.
* Customers aged 31–70 contribute the largest share of revenue.
* Loyalty program participation remains relatively low.
* Unit price and quantity purchased strongly influence total spending.
* Customer satisfaction remains generally positive across product categories.

---

# Business Recommendations

Based on the analysis, the following recommendations are proposed:

### 1. Strengthen Loyalty Programs

Increase loyalty program adoption through personalized rewards and targeted promotions.

### 2. Focus on High-Value Age Segments

Develop marketing campaigns aimed at customers aged 31–70, who generate the highest revenue.

### 3. Expand Smartphone Promotions

Leverage smartphone popularity and customer satisfaction to drive additional sales.

### 4. Improve Demand Forecasting

Use historical sales trends to improve inventory planning and reduce stock shortages.

### 5. Develop Customer Segmentation Strategies

Segment customers based on purchasing behaviour to deliver more personalized experiences.

---

# Skills Demonstrated

This project demonstrates the following technical and analytical skills:

### Data Analytics

* Data Cleaning
* Feature Engineering
* Exploratory Data Analysis (EDA)
* Statistical Analysis
* Business Intelligence

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
* Customer Segmentation Insights
* Business Recommendation Development

---

# Repository Structure

customer-purchase-behaviour-electronic-sales/

├── notebooks/

├── reports/

├── visualizations/

├── README.md

├── requirements.txt

└── LICENSE

---
