# Used Phone Devices Assigment_Adam Shinkle
Assignment for class two analyzing used phone dataset
# Used Phone Data Analysis

#**Author:** Adam Shinkle
#**Course:** GSBA-594
#**Assignment:** Assignment 2: Data Analysis with pandas, numpy, and matplotlib

## Overview

#This project analyzes a dataset of used phones and tablets to understand what drives their resale price. It covers data cleaning, outlier detection, summary statistics with NumPy, sampling, and a multiple linear regression model built with statsmodels.

## Files

#| File | Description |
#|------|-------------|
#| `Data_Analysis_Assignment_Used_Phones.ipynb` | Jupyter Notebook with all code, outputs, and written comments |
#| `used_device_data.csv` | Dataset (3,454 devices, 15 columns) |
#| `README.ipynb` | This file |

## Dataset

#Each row is a used device. Columns include brand, operating system, screen size, 4G/5G support, camera megapixels, internal memory, RAM, battery, weight, release year, days used, and normalized used and new prices.

## What the Notebook Covers

#1. **Data limitations:** missing values (202 NaNs, mostly in `rear_camera_mp`), how they were handled, and other limitations of the data
#2. **Outliers:** box plots of the numeric columns, with commentary
#3. **Feature engineering:** a new `device_age` column (in years)
#4. **NumPy statistics:** mean, min, max, standard deviation, variance, and percentiles; count of devices under a price threshold
#5. **Sampling:** a random sample of 500 devices compared to the full dataset
#6. **Z-score outliers:** outliers in `normalized_used_price` (beyond 3 standard deviations), compared with the full data on `days_used`, `internal_memory`, and `weight`
#7. **Regression:** an OLS model predicting `normalized_used_price` from `internal_memory`, `battery`, `weight`, `days_used`, and `5g_yes`
#8. **Visualization:** scatterplots with regression lines for each predictor

## Data Cleaning

#- Missing `rear_camera_mp` values were filled with the median because the distribution is right-skewed.
#- Rows with missing values in the remaining columns were dropped (22 rows), leaving 3,432 rows.

## Key Findings

#- Mean device age is about 1.85 years.
#- Battery size, internal memory, 5G support, and days used are statistically significant predictors of used price; weight is not (p = 0.089).
#- 5G devices have a predicted normalized used price about 0.44 higher than non-5G devices, holding the other variables constant.
#- The model explains about 42% of the variation in used price (R² = 0.424).

## How to Run

#1. Install Python 3 and the required libraries:
#```
#   pip install pandas numpy matplotlib statsmodels jupyter
#```
#2. Make sure `used_device_data.csv` is in the same folder as the notebook.
#3. Open the notebook:
#```
#   jupyter notebook Data_Analysis_Assignment_Used_Phones.ipynb
#```
#4. Run all cells from top to bottom.
