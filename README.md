# Time Series: Predicting the temperature in La Paz, Mexico




## Overview
- **Programming language**: Python
- **Packages**: pandas, numpy, scikit-learn, darts, prophet, XGBoost, plotly
- **Problem type**: Time-series forecasting with historical data
- **Dataset**: Historical daily wether data from https://www.visualcrossing.com/weather/weather-data-services
- **Models**: Baseline: NaiveSeasonal, FB Prophet, DARTS XGBModel, XGBRegressor
- **Conclusion**: XGBRegressor using walk-forward validation was the best performing model.


  
## Objective
1. Predict the average daily temperature in La Paz, Mexico


## Models
**Baseline**
NaiveSeasonal model using the value from the previous year’s equivalent date as a prediction

**FB Prophet**
- Additive regression model that works best with time series data that has strong seasonal effects
— Robust to outliers, missing data, and noisy data
— Easy to use but also tuneable

**DARTS XGBModel**
- DARTS’ built in XGBModel; has different hyperparameters than XGBoost

**XGBRegressor**
- Used functions to turn the time series problem into a supervised learning problem and fit an XGBRegressor model 
- Avoid data leakage
- Ever expanding training dataset (expanding window)

## Evaluation
- NaiveSeasonal was ~1°C less accurate than the best model
- Tuning the lags of DARTS XGBModel made a big difference
- XGBRegressor using walk-forward validation was the best performing model


# Visualisation
![fb_prophet_predictions](/Images/fb_prophet_predictions.png)
FB prophet predictions


![XGBRegressor_actuals_and_predictions](/Images/XGBRegressor_actuals_predictions.png)
The XGBRregressor model predictions and actual temperatures

# Next Steps
- Explore hyperparameter tuning for prophet, DARTS XGBModel, and XGBRegressor
- Explore other models
- Functionalise and develop code to create a pipeline that connects to API, cleans data and outputs to model.
- Explore ways to change the model given knowledge of El Niño






