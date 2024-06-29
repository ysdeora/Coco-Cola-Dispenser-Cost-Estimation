# Coca-Cola Dispenser Service Cost Prediction

## Project Overview
This project aims to predict service costs for Coca-Cola dispensers using various data models and analysis techniques. The goal is to understand the factors influencing service costs and develop accurate prediction models.

## Model Progression

### Model 1: Non-Sensor Data
- **Objective**: Estimate 'per service' cost using non-sensor data
- **Factors**: City, Outlet, Dispenser Model, Avg. Volume Dispensed, Age of Dispenser, Time from Last Service, Month of Servicing
- **Results**: 
  - Low accuracy ($350 error with $370 standard deviation)
  - Service costs more correlated with static factors than usage or maintenance patterns
  - Little correlation between top states/cities/outlets
  - ~30% accuracy in predicting the 25th percentile cost bucket
  - ~32% accuracy in predicting annual service cost for a dispenser

### Model 2: Incorporating Sensor Data
- **Objective**: Improve prediction accuracy using sensor data
- **Key Findings**:
  - Improved accuracy to ~40% in predicting annual cost bucket
  - Trouble Add count & Part Removal impact service costs more than factors like City, Outlet, or State
  - 55% accuracy in predicting top and bottom quartiles (up from 35%)

### Further Analysis
- **Service Cost Prediction**:
  - S9100 model: Error reduced to $250 (from $350)
  - S9000 model: No significant improvement ($360 error)
  - ~48% accuracy in predicting the cost bucket of a service
- **Hours Spent Correlation**:
  - Hours spent in service is highly correlated with total service cost
  - 60% accuracy when including 'hours spent' in the model
- **Service Reason Prediction**:
  - 36% accuracy in predicting service reason based on sensor data
  - Flow Control and CPM issues have the highest service cost

## Daily Cost Prediction Model
- **Objective**: Predict daily service cost per active dispenser
- **Results**:
  - Mean Absolute Percentage Error: ~15%
  - Significant improvement from per-service cost models
  - High dependence on the day of the week
  - Weekends have ~3% lesser average cost compared to weekdays

## Key Insights
1. Sensor data improves prediction accuracy, but challenges remain in predicting exact service costs.
2. Hours spent during service is a crucial factor in determining cost.
3. Certain sensor data points (e.g., Reboot Count, Beverage Unavailable Count) are more significant in predicting service needs.
4. Daily cost prediction models show promise, with better accuracy than per-service models.
5. Day of the week influences service costs, with weekends showing slightly lower costs.

## Future Work
- Further investigation into the relationship between sensor data and service outcomes
- Exploration of more granular time-based models
- Integration of additional data sources to improve prediction accuracy
