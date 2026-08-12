# EV Battery Power Prediction

## Project Objective

This project incorporates a large real-world electric vehicle dataset containing over 200,000 telemetry records, sourced from [Vehicle Energy Dataset (VED)](https://github.com/gsoh/VED), by GS Oh (licensed under the Apache License 2.0). The project uses this data to develop and compare machine-learning models designed to predict electric vehicle power consumption based on the vehicle's operating conditions. Reliable predictions of battery power demand is integral for understanding energy consumption and developing improved EV energy management strategies.

## Models Used

- Linear Regression
- Ridge Regression
- Random Forest
- Gradient Boosting
- Neural Network

## Dataset

The Vehicle Energy Dataset used provides real world driving data with over 200,000 entries with 20 columns of recorded metrics, from which the EV subset was extracted. This provided us with data such as vehicle speed, battery state of charge, vehicle characteristics, operating conditions, trip information and much more.

## Data Preparation

To prepare our required data, the EV subset was extracted from the wider VED, chosen for its consistency in measured variables and valid values. Relevant independent vehicle and battery measurements were selected as input features with "battery power demand" being our target variable. The data was then split 80/20 into training and testing sets, before being standardised where required to be input into our ML models.

## Model Selection

Five machine learning models  were implemented, with their suitability for predicting EV battery power demand then compared to one another. Linear Regression and Ridge Regression provided simple baselines as linear models, while Random Forest and Gradient Boosting were used to test the more complex relationships with the data. A neural network was also implemented as a more complex, non- linear model.

## Model Evaluation
Three key regression metrics were used to evaluate the models: Mean Absolute Error, Root Mean Square Error and the coefficient of determination (referred to as MAE, RMSE and R² respectively). The first two measure the amount of prediction error, hence lower values are desirable. While R² measures how closely the model aligns with the variations in battery power demand within a range of 0-1, with 1 being a perfect score.

##
