# BoomBikes Demand Prediction

## Table of Contents
* [General Information](#general-information)
* [Dataset Description](#dataset-description)
* [Problem Statement](#problem-statement)
* [Technologies Used](#technologies-used)
* [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
* [Data Preprocessing](#data-preprocessing)
* [Model Building](#model-building)
* [Model Evaluation](#model-evaluation)
* [Key Findings](#key-findings)
* [Business Recommendations](#business-recommendations)
* [Acknowledgements](#acknowledgements)

---

## General Information
BoomBikes is a **bike-sharing** provider in the **United States**. The company has faced a **decline in revenue post-COVID-19** and wants to understand the factors affecting the demand for shared bikes.

### **Objective**
1. Identify the key **factors influencing bike demand**.
2. Build a **linear regression model** to predict bike demand based on various features.
3. Provide **business recommendations** to optimize revenue.

## Dataset Description
- The dataset contains daily bike rental counts along with weather, temporal, and seasonal data.
- Columns include information such as **season, temperature, humidity, wind speed, working days, holidays, and weather conditions**.
- The target variable (`cnt`) represents the total number of bike rentals per day.

## Problem Statement
BoomBikes aims to **predict bike-sharing demand** based on external factors such as weather conditions, seasonality, and working days. The insights will help the company make data-driven decisions to **increase revenue and optimize operations**.

## Technologies Used
- **Python**
- **Pandas, NumPy** (Data Manipulation)
- **Matplotlib, Seaborn** (Visualization)
- **Scikit-learn** (Machine Learning, Feature Selection)
- **Statsmodels** (Statistical Analysis)

## Exploratory Data Analysis (EDA)
### Key Insights from EDA:
1. **Weekends and holidays show lower demand**, indicating most users are commuters.
2. **Bike usage decreases in extreme weather conditions (Heavy Rain, Snow, High Humidity)**.
3. **Temperature (`temp` and `atemp`) is the most positively correlated variable with demand**.
4. **Multicollinearity was detected between `temp` and `atemp`**, requiring feature selection.

## Data Preprocessing
- **Missing Values**: No missing values detected.
- **Feature Engineering**:
  - Categorical variables (`season`, `month`, `weekday`, `weather`) converted into **dummy variables**.
  - Dropped **highly correlated or redundant variables** (e.g., `temp` due to collinearity with `atemp`).
- **Outlier Treatment**: Removed extreme outliers in `humidity` and `windspeed` using **IQR method**.
- **Data Splitting**: 70% **training set**, 30% **test set**.

## Model Building
A **Multiple Linear Regression** model was built using:
1. **Recursive Feature Elimination (RFE)** to select the top 13 features.
2. **Variance Inflation Factor (VIF)** to remove multicollinear variables.
3. **Train-Test Split** with Min-Max Scaling for numerical features.

## Model Evaluation
- **R² Score on Training Data**: **0.83**
- **R² Score on Test Data**: **0.83**
- **No significant overfitting** (Training and Test scores are close).

## Key Findings
1. **Top Features Influencing Demand**:
   - `atemp` (Feeling temperature) **positively impacts** bike demand.
   - `year` (2019 has higher demand than 2018) suggests increased adoption.
   - `humidity` **negatively impacts** bike demand.

## Business Recommendations
- BoomBikes should increases its availability during warm and clear days mostly during September and Spring Season as the demand is more during these conditions
- Reduce the availability during extreme weather conditions (Snow and Humid Conditions)
- Consider to provide Discount offers and Promotions during Winter season and Holidays

## Acknowledgements
This project is inspired by **BoomBikes business challenges** and is based on publicly available datasets.

## Contact
Created by **[@muralik31]** – feel free to reach out!

---

Let me know if you want to modify any section! 🚀
