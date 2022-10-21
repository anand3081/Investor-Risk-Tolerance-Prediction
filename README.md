# GA Capstone Project: Investor Risk Tolerance Prediction and Robo Advisory Dashboard

Done by - **Anand Ramchandani**

## Background

**Problem Observed**
- When trying to create a risk assessment for each client, financial advisors deploy long and tedious questionnaires or surveys that require a lot of manual input and time from the investor.
- Studies have shown that these questionnaires are often prone to error because investors suffer from behavioural biases and are poor judges of their own risk perceptions, especially during times of financial turmoil. 
- Some studies have even show that the risk profiling questionnaire process helps in enabling behavioural biases

**Background regarding Risk Profiling**
- Risk tolerance measures subjective aspects of risk tolerance, including a investors personality, how they react to real or potential losses, and what their goals and priorities are
- Capacity or Ability to take risk measures objective factors like time horizon, need for income and family situation

**Questions on using Machine Learning to address this issue**
- Can machine learning provide a better assessment of an investors risk profile than a risk tolerance questionnaire?
- Can the machine learning algorithm better reflect how a client would deal in different financial market scenarios?
- Can we automate the investment and portfolio management process with minimal need for human intervention?

**Solution and Aim of this Project**
- To create a supervised regression-based machine learning model that is able to predict an individual investors risk tolerance. 
- Coupled with the individuals stated willingness to take risk, a robo advisory dashboard will be created using the model to recommend a portfolio based on that predicted risk tolerance.

**Target and Predictor Variables**
- The target predicted variable is the true Risk Tolerance of the investor. 
- The predictor variables are the other household demographic and financial attributes of the investor.

**Source of Dataset**
- The dataset used comes from the Survey of Consumer Finances, which is a statistical survey taken by the Federal Reserve every 3 years. 
- It contains the balance sheet, income and other household demographics of families in the United States. 
- The latest dataset was taken in 2019, which covers data on households from 2017 to 2019.
https://www.federalreserve.gov/econres/scfindex.htm
- We have datasets that go back to 2007

**How do we find the true risk tolerance of the individual?**

- We know that the ratio of risky assets to the total assets of an investor is a measure of the risk tolerance of that investor
- Risky Assets include investments in mutual funds, stocks, bonds, commodities, real estate, etc.
- Risk-Free Assets include checking and savings balances, certificates of deposit, and other cash balances and equivalents
- Using the data obtained in the Survey of Consumer Finances we can calculate the True Risk Tolerance and use that as the target predicted variable

![Risk%20Tolerance%20Formula.png](attachment:Risk%20Tolerance%20Formula.png)

## Problem Statement  
A Robo-Advisory firm hires a data scientist to create a machine learning model that is able to predict an investors risk tolerance from key feature attributes. Along with the investors stated willingness to take risk, a Robo Advisory prototype dashboard will also be created.

## Contents

- [Background](#Background)
- [Problem Statement](#Problem-Statement)
- [Functions Used](#Functions-Used)
- [Import Libraries](#Import-Libraries)
- [Import/Loading Data](#Import/Loading-Data)
- [Displaying the Data](#Displaying-the-Data)
- [Data Dictionary](#Data-Dictionary)
- [Exploratory Data Analysis (EDA)](#Exploratory-Data-Analysis-(EDA))
- [Feature Selection and Engineering](#Feature-Selection-and-Engineering)
- [Train Test Split](#Train-Test-Split)
- [Addressing Multicollinearity](#Addressing-Multicollinearity)
- [Model Selection](#Model-Selection)
- [Hyperparameter Tuning](#Hyperparameter-Tuning)
- [Random Forest Model](#Random-Forest-Model)
- [Model Performance Evaluation](#Model-Performance-Evaluation)
- [Feature Importance](#Feature-Importance)
- [Shapley Values for Model Interpretation](#Shapley-Values-for-Model-Interpretation)
- [Limitations with the Model](#Limitations-with-the-Model)
- [Robo Advisory Dashboard](#Robo-Advisory-Dashboard)
- [Conclusions](#Conclusions)
- [Recommendations](#Recommendations)
- [Robo Advisor Dashboard Link](#Robo-Advisory-Dashboard-Link)

## Summary of Analysis
1. General data cleaning and exploration, data from Federal Reserve website has quite reliable data
2. Create columns in each year for Risky Assets, Risk-Free Assets and Risk Tolerance
3. Remove Households with Null Values in resultant Risk Tolerance
4. Analyse Risk Tolerance Distribution Plots and merge datasets for all years into 1 big dataset
5. Feature Selection and Engineering based on criteria of using features easiy available to the investor, highly correlated with Risk Tolerance and reduced multicollinearity
6. Model Evaluation and Selection based on Mean Squared Error
7. Shapely Model Interpretation and Feature Importance
8. Select final features and run model in Explainer Dashboard

## Limitations of the Model
1. Model is purely based on US Households
2. Based on Households and not individual investors
3. Figures not adjusted for inflation throughout the years
4. Model at risk of Data Drift
5. Willingness to take risk in dataset is Yes or No rather than a range 
6. There are a lot of households with no savings
7. Regular ML Ops required to keep model relevant
8. Easy use by investor hinders predictive ability of model
9. Susceptible to new financial instruments, innovation and technology, like cryptocurrency, NFTs or even new laws

## Conclusions
1. Net Worth and Savings have by far the largest impact on Risk Tolerance
2. The higher ones Savings , the lower the Risk Tolerance
3. This model could be used to not only decipher one's Risk Tolerance but also to determine how each feature inform this prediction
4. This could possibly used to target customers directly to portfolios in line with their Risk Tolerance

##  Recommendations
1. Longer time period, more features and more households/investor data
2. Run more GridSearch to Hyperparameter Tune for each model
3. Gather data from other countries besides the US
4. Gather data from investors rather than just households
5. Adjust figures for inflation
6. Use range for willingness to take risk
7. Possible design improvements to make model more versatile and susceptible to market conditions and new financial instruments
