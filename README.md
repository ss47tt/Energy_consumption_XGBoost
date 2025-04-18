# Energy_consumption_XGBoost

How to train, validate, and predict energy comsumption data?

1. Download the dataset from Kaggle, https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption

2. I used the energy consumption by COMED CSV file for this project which can be found in the dataset. The aim is to use time-based features to predict future energy consumption.

3. I sorted the datetime column of the COMED csv file in ascending order (oldest to newest).

4. I added time-based features, those are, hour, day of week, month, weekend, day of month, quarter, lag one hour, lag one day, lag one week.

5. I used correlation matrix to check the correlation values for all the time-based features and removed weekend, day of month, and quarter.

6. I used XGBoost to do feature importances for hour, day of week, month, lag one hour, lag one day, lag one week. I found that lag one hour feature is the most important.

7. I used XGBoost to do training and validation with time series split and used grid search to find the best hyperparameters for the XGBoost model.

8. XGBoost is then used to predict the future 24 hours data for every hour interval using recursive or direct methods. Recursive method is not recommended as it can accumulate previous data points' errors.
