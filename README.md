🛍️ Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores customer shopping behavior using transactional data from 3,900 purchases. The project covers the full analytics pipeline — from data cleaning in Python, to structured business analysis in SQL (PostgreSQL), to an interactive Power BI dashboard — culminating in actionable business recommendations for a retail company.

📌 Business Problem

A leading retail company wants to better understand its customers' shopping behavior to improve sales, customer satisfaction, and long-term loyalty. Management has observed shifting purchase patterns across demographics, product categories, and sales channels, and wants to know which factors — discounts, reviews, seasonality, or payment preferences — drive consumer decisions and repeat purchases.

Overarching business question:

"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"

🏗️ Project Workflow

Customer-Shopping-Behavior-Analysis/

├── Customer_Shopping_Behavior_Analysis.ipynb           # Python: data cleaning & feature engineering

├── customer_behavior_sql_queries.sql                   # SQL: business analysis queries (PostgreSQL)

├── Customer_Behavior_Dashboard.pbix                    # Power BI: interactive dashboard

├── Customer_Shopping_Behavior_Analysis.pdf             # Full project report

├── Customer-Shopping-Behavior-Analysis.pptx            # Stakeholder presentation

├── Business_Problem_Document.pdf                       # Original business problem statement

└── README.md

Data Preparation (Python) — Cleaned and transformed the raw dataset.

Data Analysis (SQL) — Loaded the cleaned data into PostgreSQL and ran structured business queries.

Visualization (Power BI) — Built an interactive dashboard summarizing key patterns.

Reporting — Documented findings and recommendations in a report and presentation.

📊 Dataset Summary

Detail	             Value

Rows	               3,900

Columns	             18

Missing Data	       37 values in Review Rating

Key features:

Demographics: Age, Gender, Location, Subscription Status

Purchase details: Item Purchased, Category, Purchase Amount, Season, Size, Color

Shopping behavior: Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

🐍 Data Preparation (Python)

Performed in Customer_Shopping_Behavior_Analysis.ipynb using pandas:

Data loading & exploration — df.info(), df.describe() for structure and summary statistics.

Missing value handling — Imputed missing Review Rating values using the median rating per product category.

Column standardization — Converted column names to snake_case for readability.

Feature engineering:

age_group — created via quartile binning (pd.qcut) into Young Adult / Adult / Middle-aged / Senior.

purchase_frequency_days — mapped from the frequency_of_purchases categorical field (e.g. Weekly → 7, Monthly → 30).

Redundancy check — Verified discount_applied and promo_code_used were identical, and dropped promo_code_used.

Database integration — Loaded the cleaned DataFrame into PostgreSQL using SQLAlchemy + psycopg2 for downstream SQL analysis.

🗄️ Data Analysis (SQL)

Structured business analysis was performed in PostgreSQL (customer_behavior_sql_queries.sql), answering 10 key business questions:

#	Business Question	                                          Key Insight

1	Revenue by gender	                              Male customers generated $157,890 vs. Female $75,191

2	High-spending discount users	                  839 customers used a discount yet spent above the average

3	Top 5 products by review rating	                Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78)

4	Standard vs. Express shipping spend	            Express ($60.48) slightly outspends Standard ($58.46)

5	Subscribers vs. non-subscribers	                Non-subscribers drive $170K revenue vs. subscribers' $62.6K, despite   

6	Products with highest discount dependency     	Hat, Sneakers, Coat, Sweater, Pants

7	Customer segmentation (New/Returning/Loyal)    	Loyal: 3,116 · Returning: 701 · New: 83

8	Top 3 products per category                   	e.g. Jewelry & Blouse lead Accessories/Clothing

9	Repeat buyers (>5 purchases) vs. subscription	  Most repeat buyers (2,518) are not subscribed

10	Revenue by age group	                        Young Adults lead with $62,143 in total revenue

📈 Power BI Dashboard

An interactive Customer Behavior Dashboard (Customer_Behavior_Dashboard.pbix) was built to visualize insights, featuring:

KPI cards: 3.9K customers, $59.76 avg. purchase amount, 3.75 avg. review rating

Subscription status breakdown (27% Yes / 73% No)

Revenue & sales by category

Revenue & sales by age group

Interactive filters/slicers: Subscription Status, Gender, Category, Shipping Type

💡 Business Recommendations

Boost Subscriptions — Promote exclusive benefits to convert non-subscribers, who currently drive the majority of revenue.

Customer Loyalty Programs — Reward repeat buyers to move more customers into the "Loyal" segment.

Review Discount Policy — Balance discount-driven sales boosts against margin control for heavily discounted products.

Product Positioning — Highlight top-rated and best-selling products (e.g. Gloves, Jewelry, Blouse) in campaigns.

Targeted Marketing — Focus efforts on high-revenue age groups (Young Adults) and Express-shipping users.

🛠️ Tech Stack

Layer                                               	Tools

Data Cleaning & Feature Engineering       	Python, pandas, Jupyter Notebook

Database	                                  PostgreSQL, SQLAlchemy, psycopg2

Analysis	                                  SQL (window functions, CTEs, aggregations)

Visualization	                              Power BI

Reporting	                                  PDF report, PowerPoint presentation

🚀 Getting Started

Prerequisites

Python 3.8+

PostgreSQL

Power BI Desktop (to view/edit the .pbix dashboard)

Setup

bash

# Clone the repository

git clone <https://github.com/bhaktibhanushali-01/Customer_Behavior_Analysis.git>

cd Customer-Shopping-Behavior-Analysis

# Install Python dependencies

pip install pandas sqlalchemy psycopg2-binary jupyter


Run the Analysis

Open Customer_Shopping_Behavior_Analysis.ipynb and run all cells to clean the data and load it into PostgreSQL.

Open customer_behavior_sql_queries.sql in your PostgreSQL client (e.g. pgAdmin) and run the queries against the loaded customer table.

Open Customer_Behavior_Dashboard.pbix in Power BI Desktop to explore the interactive dashboard.

📄 Deliverables

✅ Python notebook — data cleaning & preparation

✅ SQL queries — business analysis

✅ Power BI dashboard — visual insights

✅ Project report (PDF)

✅ Stakeholder presentation (PPTX)

📜 License

This project is distributed under the MIT License.
