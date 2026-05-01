# Bike Sharing Demand Forecasting
 Overview
This project focuses on predicting hourly bike demand using historical ride data.  
The goal is to improve demand estimation so that bike availability can be better managed across different times of the day.

 Problem Statement
Accurately forecast bike demand at an hourly level to support operational decisions such as bike allocation and rebalancing.

 Approach
 1. Data Processing
- Cleaned and prepared historical ride data  
- Converted datetime into structured time features  
- Handled missing values and ensured consistency  


2. Feature Engineering
Created features to capture temporal patterns:
- Hour, day, month, weekday  
- Lag features (previous hour, previous day)  
- Rolling averages to capture short-term trends  
- Cyclical encoding for hour-based patterns  


3. Modeling
- Established a **naive lag-based baseline** for reference  
- Trained and compared:
  - Random Forest  
  - XGBoost  
- Selected XGBoost based on lowest error and consistent performance  


4. Validation
- Used **time-based train-test split** to avoid data leakage  
- Ensured model only learns from past data to predict future demand  

-Results

- Baseline MAE: ~61  
- XGBoost MAE: ~32  
- Improvement: **~47% reduction in error**

- Observed higher prediction errors during peak demand hours compared to non-peak periods
- 
5. Simulation (Rebalancing)

- Used predicted demand to simulate bike allocation across zones  
- Demonstrates how forecasts can support operational planning  
- Note: Simulation does not include real geographic constraints  

6. Key Learnings

- Time-based features and lag variables significantly improve forecasting accuracy  
- Proper validation (time split) is critical to avoid misleading results  
- Prediction alone is not sufficient; linking outputs to decisions adds practical value  


7. Limitations

- No real geographic or distance-based constraints in rebalancing simulation  
- Model performance varies during peak hours  
- External factors (events, holidays) not explicitly modeled  
