# House Price Prediction Analysis

## Project Overview

This project predicts house prices using machine learning techniques. It includes data preprocessing, exploratory data analysis (EDA), feature engineering, model training, and performance evaluation. The objective is to identify the factors that influence house prices and build a predictive model that can estimate the price of a house based on its features.

## Dataset Summary

The dataset contains information about residential houses, including features such as the number of bedrooms, bathrooms, living area, lot size, location, and other property characteristics. The target variable is the house sale price. The dataset is used to train and evaluate machine learning models for predicting house prices.

## Data Cleaning

1. Extra index columns are removed.

2. Duplicate rows are removed.

3. The number of bedrooms is extracted from the `title` column.

4. Missing values in the `amount` column are filled using information extracted from the `description` column.

5. `carpet_area` and `super_area` values are converted to the standard unit of `sqft`.

6. The floor number and total number of floors are separated into individual columns.

7. Missing values in the `furnishing` column are filled using information extracted from the `description` column.

8. Values in the `overlooking` column are standardized for consistency.

9. The number of car parking spaces and parking status (`Open` or `Covered`) are separated and converted to appropriate data types.

10. The `facing` and `location` columns are converted to the `category` data type.


## Univariate Analysis

1. The `amount` column is highly right-skewed with a skewness value of `154.94`. Approximately `98%` of the properties have prices ranging from `13 Lac` to `6.5 Cr`.

2. `71%` of the data comes from `22` cities cumulatively, while the remaining `59` cities contribute relatively fewer observations.

3. In the `carpet_area` column, `98%` of the properties have a carpet area between `300` and `4,000 sqft`. The distribution is concentrated within this range but is highly positively skewed, with a skewness value of `195.028`.

4. `74.3%` of the properties are listed for resale, while `25.6%` are new properties. The remaining `0.8%` belong to other transaction types.

5. `Furnished` and `semi-furnished` properties have relatively similar proportions, while only around `15%` of the flats are fully furnished.

6. The `facing` column has `39%` missing values. Among the non-missing values, `45%` of the flats face East.

7. The `overlooking` column contains `44%` missing values. Among the available values, the main categories are `Main Road`, `Garden/Park`, and `Pool`.

8. `9%` of the flats have all three overlook views Garden/Park, Main Road and Pool

9. Among the flats with available overlooking information, `44.9%` overlook a Main Road, `41%` overlook a Garden/Park, and `14.1%` overlook a Pool.

10. Only `24` societies have more than `50` flats listed in the dataset, out of `10,353` societies.

11. Most flats have around `2` to `3` bathrooms, with `75%` of the properties having between `1` and `3` bathrooms.

12. On average, each flat has approximately `2` balconies, with most properties having between `1` and `3` balconies.

13. The `car_parking` column has `57.6%` missing values. Among the available values, `34.2%` of the flats have `1` parking space. The distribution is highly right-skewed, with a skewness value of `16.46`.

14. The `ownership` column has `36.5%` missing values. Among the available values, `86.3%` of the flats have `Freehold` ownership.

15. Approximately `98%` of the properties have a `super_area` between `500` and `4,500 sqft`. The distribution is highly right-skewed, with a skewness value of `163.6`.

16. Most flats have `2` to `3` bedrooms.

17. Approximately `98%` of the buildings have between `1` and `30` floors.

18. The `car_parking_status` column has `57.67%` missing values. Among the available values, `86%` of the parking spaces are `Covered`, while `14%` are `Open`.


## Bivariate Analysis

1. `amount` has positive linear relationship with `carpet_area`.

2. Among top 22 cities according to row amount in data, `Gurgaon` and `New-Dehli` has highest median amount while `Bhiwadi` with lowest. 

3. `New-Dehli` has the highest IQR range shows amount is more distributed then other cities. While `Rachi` has consistent flat prices due to smallest IQR range.

4. `New-Property` has the highest median amount.

5. `New-Property` outliers are very severe as they are at very large gap from the other maximum boxplot range.

6. From selected `24` societies, `DLF The Valley Garden` society has the highest median amount. While `Krish Aura` has the the lowest median amount.

7. `Omaxe Heights` and `Pacific Golf Estate` has highest IQR range means the amounts are highly distributed in both.

8. `Motia Blue Ridge` and `RPS Auria Residences` societies have most consistent property prices as IQR range is very small.

9. When the number of `bathrooms`, `bedrooms` and `balconies` increases the amount median also increases. Flats with more then `7` bathrooms have larger IQR range showing more flactuation in flat prices.

10. The exception in `balcony` where the houses with `9 balconies` has very very small IQR range shows the amounts are ideally consistent. This is because there are only 2 flats in data having `9 balconies`.

11. Flats with `Power of Attorney` ownership have the lowest amount median while other categories almost have the same.

12 