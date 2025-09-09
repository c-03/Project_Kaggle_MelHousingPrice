# Melbourne Housing Price Prediction

This project analyses and predicts Melbourne housing prices using a real-world dataset from Kaggle. The workflow covers data cleaning, feature engineering, exploratory analysis, and machine learning modeling to deliver actionable insights for buyers, sellers, and developers.

## Overview
This repository demonstrates a full data science pipeline:
- Data cleaning and imputation for missing values and outliers
- Exploratory data analysis and visualization
- Feature engineering and encoding
- Predictive modeling (regression, tree-based, boosting, clustering)
- Model evaluation and comparison

## Dataset
- **Source:** [Kaggle - Melbourne Housing Snapshot](https://www.kaggle.com/datasets/dansbecker/melbourne-housing-snapshot)
- **Author:** dansbecker
- **Rows:** ~13,500 (raw), ~11,000 (cleaned)
- **Columns:** 21 features (location, property details, price, etc.)
- **Files:**
  - `melb_data.csv`: Raw dataset
  - `melb_data_cleaned.csv`: Cleaned dataset after preprocessing

## Data Analysis Steps
1. **Data Exploration:**
	- Inspected data types, missing values, and summary statistics
	- Visualised distributions and relationships
2. **Data Cleaning:**
	- Imputed missing values (e.g., `Car` with 0, `BuildingArea` with IterativeImputer, `YearBuilt` with mode)
	- Fixed inconsistent or missing `CouncilArea` using suburb mapping
	- Removed impossible values (e.g., `BuildingArea` or `Landsize` = 0)
	- Detected and removed outliers using the IQR method
	- Converted date columns to datetime format
	- Removed duplicates
3. **Feature Engineering:**
	- Extracted month and day of week from `Date`
	- Encoded categorical variables (one-hot for low-cardinality, frequency encoding for high-cardinality)
4. **Modeling:**
	- Baseline and advanced regression models: Linear Regression, ElasticNet, SVR, Decision Tree, XGBoost, Random Forest
	- Dimensionality reduction (PCA, SelectKBest, RFE)
	- Model selection based on cross-validated RMSE and R²
5. **Clustering:**
	- KMeans clustering to segment properties

## Key Findings
- **Data Quality:** Significant missing values in `BuildingArea` and `YearBuilt` required careful imputation.
- **Model Performance:**
  - Best regression model (PCA + SVR) achieved R² ≈ 0.838 and RMSE ≈ 0.192(log-price scale)
  - PCA outperformed SelectKBest and RFE for dimensionality reduction

## Visualisations
- **Geospatial Map:** Median price by suburb, property count, and location
- **Line Chart:** Median price trends over time
- **Scatter/Regression:** Price vs. Year Built with OLS fit
- **Box Plot:** Price distribution by house type
- **Bar Charts:** Regional distribution, top sellers
- **Correlation Heatmap:** Numeric feature relationships
- **Clustering:** KMeans cluster visualization (PCA-reduced)

## Files
- `PricePrediction.ipynb`: Main notebook with all analysis, cleaning, modeling, and visualizations
- `melb_data.csv`: Raw dataset
- `melb_data_cleaned.csv`: Cleaned dataset after preprocessing
- `requirement.txt`: Python dependencies
- `README.md`: Project documentation
