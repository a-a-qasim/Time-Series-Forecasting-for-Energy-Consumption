# PJME Energy Consumption Forecasting with XGBoost

##  Project Overview
This project focuses on predicting hourly energy consumption (MW) for the PJM Interconnection (PJME) region. Using the **XGBoost** regressor, I developed a model that identifies daily, weekly, and seasonal patterns to provide highly accurate energy forecasts.

##  Key Upgrades & Workflow Improvements
This version implements several "Must-Concentrate" upgrades to improve upon the original baseline:
* **Chronological Data Integrity**: Implemented strict datetime conversion and index sorting to eliminate data leakage and ensure smooth time-series curves.
* **Advanced Feature Engineering**: Extracted 8 unique time-based features, including ISO-standardized week numbers and day of month, to capture complex seasonality.
* **Clean Analytical Workflow**: Fixed legacy Seaborn and Matplotlib warnings for a production-ready Jupyter Notebook environment.

##  Performance Results
My upgraded model achieved a lower error rate than the original project benchmark:

| Metric | Original Author | **My Upgraded Model** |
| :--- | :--- | :--- |
| **RMSE** | 3741.16 MW | **3713.70 MW** |
| **MAPE** | 9.23% | **8.56%** |

## Visual Insights

### 1. Data Train/Test Split
Separating the data at 2015-01-01 to validate model performance on unseen future data.
![Train Test Split](energy_train_test_split.png)

### 2. Feature Importance
Analysis showing that **Hour of Day** is the primary driver of energy consumption fluctuations.
![Feature Importance](feature_importance_ranking.png)

### 3. Forecast vs. Truth
A comparison of the model's predictions (8.56% MAPE) against actual recorded energy usage.
![Final Prediction](forecast_results_comparison.png)

## Conclusion
The model proves highly effective at capturing daily rhythms. Future iterations will incorporate weather data (Temperature/Humidity) to further reduce errors during extreme seasonal peaks.