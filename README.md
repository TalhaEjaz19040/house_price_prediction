# House Price Prediction Analysis

## Project Overview

This project predicts house prices using machine learning techniques. It includes data preprocessing, exploratory data analysis (EDA), feature engineering, model training, and performance evaluation. The objective is to identify the factors that influence house prices and build a predictive model that can estimate the price of a house based on its features.

## Dataset Summary

The dataset contains information about residential houses, including features such as the number of bedrooms, bathrooms, living area, lot size, location, and other property characteristics. The target variable is the house sale price. The dataset is used to train and evaluate machine learning models for predicting house prices.

## Data Cleaning

1. Extra index columns is removed.

2. Duplicate rows are removed.

3. From title number of bedrooms are extracted.

4. From description the missing values in amount column are filled.

5. Convert the carpet_area and super_area values in standard unit sqft.

6. Floor number and total number of floors are separated.

7. The furnishing column missing values filled from description column.

8. Make values consistent in overlooking column.

9. Car parking and its status `Open` or `Covered` are separated and convered to appropriate data type.

10. facing and location column is changed to category data type.