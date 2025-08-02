# Introduction
Customer churn refers to the percentage of customers who stop using a company's product or service during a specific time period. Understanding churn is critical for telecom providers to improve customer satisfaction and reduce revenue loss. This project presents a complete data pipeline—from raw telecom data to actionable insights and a machine learning model that predicts which customers are most likely to churn.

# Project Objectives
ETL Pipeline: Design an end-to-end extract, transform, and load (ETL) flow in SQL Server to handle raw telecom customer data.
Data Cleaning: Handle nulls, convert data types, and prepare structured views for reporting.
Dashboarding: Create insightful, interactive dashboards in Power BI to track churn by demographics, geography, services, and contract details.
Prediction Model: Train a Random Forest machine learning model using Python to predict churners based on customer features.
Business Insight: Provide actionable suggestions by interpreting model predictions and dashboard findings.

# Tools & Technologies
SQL Server: For staging, cleaning, and structuring data
Power BI: For creating interactive visuals and dashboards
Python: For building, training, and evaluating the ML model
Jupyter Notebook: For experimenting with feature engineering and model validation
Libraries: pandas, numpy, scikit-learn, seaborn, matplotlib, joblib

#  Project Structure
SQL/ – Scripts for database schema, staging, and views
PowerBI/ – .pbix file with visuals and metrics
Python/ – Jupyter notebook with churn prediction model
README.md – Documentation and project overview
requirements.txt – Python dependencies

#  Data Cleaning and Preparation (SQL Server)
Staging Table: Load raw CSV data into a staging table.
Null Handling: Use SQL functions to handle missing values (ISNULL, NULLIF).
Type Conversion: Ensure correct formats for boolean, categorical, and numerical fields.
View Creation: Generate two main views:
vw_ChurnData: Includes labeled data for churn/stay customers
vw_JoinData: Filters new joiners to apply model predictions

#  Dashboard Design (Power BI)
The dashboard was created to provide quick visual insight into the factors influencing churn:

1. Summary Page
Total Customers
Total Churned
New Joiners
Overall Churn Rate
KPI Cards & Trendlines


2. Predicted Churner Profiles
Uses ML output to show predicted churners
Filterable by tenure, state, contract, and payment method
Helps identify high-risk customer groups


#  Machine Learning Model (Python – Random Forest)
Data Source: Used SQL view vw_ChurnData as input

Preprocessing:
Handled categorical variables with LabelEncoder
Removed irrelevant columns

Model: Random Forest Classifier,Trained on 80% of the dataset and Achieved 84% accuracy

# Evaluation:
Confusion Matrix
Precision, Recall, F1-score
Feature Importance to interpret results

# Prediction Output:
Applied model to vw_JoinData
Output stored as predictions.csv for Power BI use

## Snapshot of Dashboard (Power BI Service)
Summary Page-The summary page provides a high-level view of overall churn trends. It includes KPIs like total customers, churn rate, new joiners, and trend charts. Slicers allow filtering by gender, geography, and contract type for deeper insight.

![image alt](https://github.com/nishtha0911/Customer-Churn-Prediction-Analysis-Project/blob/main/summary%20page.png?raw=true)

Prediction Page-This page displays customers predicted to churn based on the machine learning model. Users can filter by age, tenure, services, or payment method to identify high-risk profiles and plan targeted retention strategies.

![image alt](https://github.com/nishtha0911/Customer-Churn-Prediction-Analysis-Project/blob/main/prediction%20page.png?raw=true)
