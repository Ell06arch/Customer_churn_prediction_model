# Customer_Churn_Prediction

This project involves building and evaluating a logistic regression model to predict customer churn based on various customer characteristics, product characteristics, user experiences, transaction history, and customer engagement.

## Table of Contents
- [Introduction](#introduction)
- [Analysis](#data-description)
- [Data Cleaning and Preprocessing](#data_cleaning_and_preprocessing)
- [Feature Engineering](#feature_engineering)
- [Model Development](#model_developmemt)
- [Interpretation of Model Performance](#interpretation_of_model_performance)
- [Summary for Non-Data practitiones](#summary_for_non-data_practioners)

## Introduction
Customer churn prediction is crucial for businesses to retain customers and improve satisfaction. This project uses a logistic regression model to identify customers likely to leave.

## Data Description
The dataset includes customer characteristics, product usage, user experience, transaction history, and customer engagement metrics. Important features used in the model include:
- CustomerID
- Country
- State
- City
- Zip Code
- Gender
- Senior Citizen
- Partner
- Dependents
- Phone Service
- Multiple Lines
- Internet Service
- Streaming TV
- Streaming Movies
- Contract
- Paperless Billing
- Payment Method
- Online Security
- Online Backup
- Device Protection
- Tech Support
- Tenure Months
- Monthly Charge
- Total Charges
- Churn Label
- Churn Value
- Churn Score
- CLTV
- Churn Reason

## Feature Engineering
We performed the following feature engineering steps:
- Created a new feature for the number of additional services.
- Normalized the total charge and monthly charge.
- Calculated the average charge per month.
- Normalized the churn score and CLTV.

## Model Training
We used a logistic regression model to predict customer churn. The model was trained on a subset of the data and evaluated using a test set.

## Model Evaluation
The model's performance was evaluated using the following metrics:
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
