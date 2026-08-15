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

1. `amount` shows a positive relationship with `carpet_area`, with property prices generally increasing as carpet area increases.

2. Among the top 22 cities by number of listings, `Gurgaon` and `New-Delhi` have the highest median property amounts, while `Bhiwadi` has the lowest.

3. `New-Delhi` has the largest IQR, indicating greater variation in the middle 50% of property prices. In contrast, `Ranchi` has the smallest IQR, indicating relatively more consistent property prices.

4. `New-Property` has the highest median amount among the transaction types.

5. `New-Property` has severe high-price outliers, with extreme values located far above the upper whisker of the boxplot.

6. Among the selected 24 societies, `DLF The Valley Garden` has the highest median amount, while `Krish Aura` has the lowest.

7. `Omaxe Heights` and `Pacific Golf Estate` have the largest IQRs, indicating greater variation in the middle 50% of property prices within these societies.

8. `Motia Blue Ridge` and `RPS Auria Residences` have the smallest IQRs, indicating relatively consistent property prices within these societies.

9. As the number of bedrooms, bathrooms, and balconies increases, the median amount generally increases**. Properties with more than 7 bathrooms have a particularly large IQR, indicating greater variation in their prices.

10. The `9-balcony` category is an exception, showing a very small IQR and apparently consistent property prices. However, this result is not reliable because only two properties have 9 balconies.

11. Properties with `Power of Attorney ownership` have the lowest median amount, while the median amounts of the other ownership categories are relatively similar.


## Multivariate Analysis

. The `amount` of the flats is related to the `location` ad `society` as data points with the same color are increasing with the same proportion against `carpet_area` and `super_area`.

2. `Ahmedabad` has the highest number of furnished flats `760` and `Bhiwadi` with lowest number of furnished flats `100`.

3. `Gurgaon` has highest number of semi-furnished flats `2200` and `Goa` has lowest number of semi-furnished flats `260`.

4. `Kolkata` has highest number of Unfurnished flats `1900` and `Zirakpur` has lowest number of Unfurnished flats `220`.

## Feature Engineering

1. The `total_floors` and `floors` is changes to categorical column floors less than `11` is `low`, between `11` and `30` is `mid`, from `31` to `60` is high and above `60` is `very high`.

2. It is observed that cost of the flat depends on building floors.

3. By examining ratio between `bedrooms` and `bathrooms` and `carpet_area` few outliers are removed.

4. Flats with `covered` parking has slightly higher amounts then `opened` once.

5. The values missing in `total_floors` are replaced by the value of at which floor the flat is.

6. Unnecessary and for time being created columns are removed 'Unnamed: 0', 'description', 'facing', 'locality', 'carpet/super', 'floor', 'total_floors'.

7. To handle missing values the pipeline is created and each column missing values are filled differently given below:

    - amount : Nothing missing

    - price : Nothing missing

    - location : Nothing missing

    - carpet_area : Nothing missing

    - transaction : Replaced with most frequent values

    - furnishing : Nothing missing

    - overlooking : Replaced with 'Not Available' string

    - society : Replaced with the most repeated society in the same city
    
    - bathroom : Equal to the number of bedrooms the flat has.
    
    - balcony : Replaced with 0
    
    - car_parking : Replaced with most frequent values
    
    - ownership : Replaced with most frequent values
    
    - super_area : Nothing missing
    
    - bedrooms : Equal to the number of bathrooms the flat has.
    
    - car_parking_status : Replaced with the status of the car parkings the society mostly have.
    
    - total_floors_cat : Replaced with most frequent values
    
    - floor_cat : Replaced with most frequent values

8. The pipeline is setup for the data flow and each stage of the pipeline does the useful work.

    - First layer fill the missing values on the basis of the given imputers.
    
    - Second, the data is moved to the next layer where encoding of categorical and scaling of numerical columns is done.

    - At last, the data is moved inside the model and the model gets trained. 
