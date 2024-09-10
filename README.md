# Smart Energy Supply Scheduling for Green Telecom Challenge


## Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Machine Learning Prediction](#machine-learning-prediction)
  - [Data Exploration and Preprocessing](#data-exploration-and-preprocessing)
- [Results](#results)

## Project Overview
The Smart Energy Supply Scheduling for Green Telecom Challenge, organized by the International Telecommunication Union (ITU), aims to develop machine learning models to optimize the utilization of various energy sources for powering mobile networks. The goal is to minimize energy costs while ensuring the battery's remaining capacity meets a set threshold. The energy sources considered are grid power, solar power, and diesel generators, with a focus on integrating these sources efficiently to reduce overall costs and carbon emissions.

## Problem Statement
Participants are tasked with designing an energy supply strategy that specifies when and which energy sources (grid, solar, diesel) to use. The strategy must minimize the total energy supply costs while maintaining the battery’s state of charge (SOC) above a defined discharge threshold. The challenge involves predicting daily solar energy generation and determining optimal usage strategies for the available energy sources based on historical data.

## Dataset
The dataset provided for this challenge is divided into the following key files:
- _Energy Consumption Data:_ Hourly data detailing the energy consumption of base stations.
- _Site Information and Grid Outage Data:_ Information on site configuration, battery capacity, grid outage plans, and diesel power output.
- _Solar Power and Weather Conditions Data:_ Hourly solar power statistics and weather conditions affecting solar energy generation.
- _Sample Submission File:_ Template for the expected format of submissions.

## Machine Learning Prediction
### Data Exploration and Preprocessing
- Merge and clean datasets to handle missing values and ensure consistency.
- Generat new features such as time from the provided hour and day data.
- Encode categorical variables and create a unified dataset for analysis.

### 2. Correlation Analysis:
- Investigate correlations between various features and the target variable (energy output).
- Test hypotheses regarding the relationships between energy output and factors such as solar zenith angle, Clearsky DNI, relative humidity, and other metrics.

### 3. Feature Engineering:
- Select relevant numeric features for modeling based on correlation analysis.
- Create a time feature to represent the hour of the day adjusted for day and hour.

### 4. Model Training and Optimization:
- Employ XGBoost Regressor to model energy output prediction.
- Use GridSearchCV to tune hyperparameters and select the best model.

### 5. Prediction and Strategy Formulation:
- Generate predictions for energy output using the optimized model.
- Develop a strategy to decide on energy source usage based on predicted energy output and predefined thresholds.

### Submission Preparation:
- Create a submission file with columns indicating the usage of grid, solar, and diesel power.
- Ensure the output format aligns with the challenge requirements, including continuous time series and alphabetical ordering of sites.

## Results
The final model was evaluated using metrics such as RMSE, MAE, and R-squared to assess its performance on the test set. The results are used to generate predictions for energy output, which are then translated into a strategy for energy source utilization.

The submission file is designed to ensure:
- Correct ordering of sites and time periods.
- Proper encoding of energy usage decisions.
- Compliance with the challenge format requirements.
