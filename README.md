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

## Univariate Analysis

1. amount is highly righ skewed with value `154.94` and `98%` of the amount is from `13 Lac` to `6.5 Cr`.

2. `71%` of the data is from `22` cities cumulatively while rest of the `59` cities have small amount of data.

3. In carpet_area column, `98%` of the data lies between `300` to `4000` sqft with uniform graph but overall data is highly positive skewed with `195.028` value.

4. `74.3%` of the property is for resale and `25.6%` is the new property while `0.8%` of prperty is contributed by other transactions.

5. Both the `furnished` and `semi-furnished` are equal but only `15%` of the flats are furnished.
