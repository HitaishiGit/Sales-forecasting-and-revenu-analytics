# Sales Forecasting and Revenue Analytics

## Project Overview
This project focuses on analyzing retail sales patterns and developing machine learning models to forecast store-level sales. Using the Rossmann Store Sales dataset, the project explores sales trends, promotional impact, store characteristics, and competition-related factors to identify key drivers of revenue.

## Objectives
- Analyze historical retail sales patterns.
- Understand the impact of promotions, holidays, and store characteristics on sales.
- Identify important factors influencing revenue.
- Develop machine learning models to forecast daily store sales.
- Compare model performance using regression evaluation metrics.

## Dataset
**Dataset:** Rossmann Store Sales

The dataset contains:
- Store information
- Daily sales and customer counts
- Promotional indicators
- Holiday information
- Store types and assortment categories
- Competition distance and opening information

The working dataset contains 252,321 training records and 41,088 test records after preprocessing.

## Tools and Technologies
- Python
- Google Colab
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Machine Learning and Regression

## Project Workflow

### 1. Data Cleaning and Preprocessing
- Handled missing values in training, testing, and store datasets.
- Imputed missing competition distance using the median.
- Handled missing competition and promotional information.
- Converted date columns into datetime format.
- Merged store information with sales data.

### 2. Exploratory Data Analysis
Analyzed sales patterns based on:
- Daily and monthly sales trends
- Store types and assortment categories
- Promotional activities
- School and state holidays
- Competition distance
- Customer counts
- Top-performing stores

### 3. Feature Engineering
Created additional features:
- Year, Month, Day and Week of Year
- Weekend indicator
- Competition open duration
- Promotional indicators

Applied one-hot encoding to categorical variables.

### 4. Model Development
Developed and compared two regression models:

- Random Forest Regressor
- HistGradientBoosting Regressor

Used chronological train-validation splitting to evaluate forecasting performance on later dates.

### 5. Model Evaluation

**Random Forest Regressor**

| Metric | Result |
|---|---:|
| MAE | 1,225.26 |
| RMSE | 1,787.20 |
| RMSPE | 34.69% |

**HistGradientBoosting Regressor**

| Metric | Result |
|---|---:|
| MAE | 1,757.34 |
| RMSE | 2,267.97 |
| RMSPE | 53.45% |

Random Forest achieved better performance across all three evaluation metrics and was selected as the final model.

*RMSPE was calculated on validation observations with non-zero actual sales.*

### 6. Feature Importance
The Random Forest feature importance analysis identified the following influential features:

1. Store Open status
2. Promotional activity
3. Competition distance
4. Store identifier
5. Day of the week
6. Competition opening duration

### 7. Sales Forecasting
The selected Random Forest model was used to generate predictions for 41,088 test records.

The prediction output includes:
- Store identifier
- Date
- Predicted sales

## Key Findings
- Promotional days showed higher average sales than non-promotional days.
- Customer count had a strong positive correlation with sales.
- Sales varied across store types and assortment categories.
- Store operating status was the most influential model feature.
- Random Forest outperformed the Gradient Boosting model on the validation dataset.

## Conclusion
This project demonstrates an end-to-end retail analytics and sales forecasting workflow, combining data preprocessing, exploratory analysis, feature engineering, machine learning, model evaluation, and prediction generation.

The findings highlight how operational, promotional, and store-related factors contribute to retail sales patterns.

## Future Improvements
- Experiment with advanced forecasting algorithms such as XGBoost and LightGBM.
- Perform hyperparameter optimization.
- Incorporate additional historical data.
- Explore time-series forecasting approaches.
- Improve prediction accuracy for high-revenue stores.
