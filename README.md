# EV Battery Power Prediction

## Project Objective

This project incorporates a large real-world electric vehicle dataset containing over 200,000 telemetry records, sourced from [Vehicle Energy Dataset (VED)](https://github.com/gsoh/VED), by GS Oh (licensed under the Apache License 2.0). The project uses this data to develop and compare machine-learning models designed to predict electric vehicle power battery power demand based on the vehicle's operating conditions. Reliable predictions of battery power demand are integral to understanding energy consumption and developing improved EV energy management strategies.

## Models Used

- Linear Regression
- Ridge Regression
- Random Forest
- Gradient Boosting
- Neural Network

## Dataset

The Vehicle Energy Dataset used provides real world driving data with over 200,000 entries with over 20 columns of recorded metrics, from which the EV subset was extracted. This provided us with variables including vehicle speed, battery state of charge, vehicle characteristics, operating conditions and trip information

## Data Preparation

To prepare our required data, the EV subset was extracted from the wider VED, chosen for its consistency in measured variables and valid values. Relevant independent vehicle and battery measurements were selected as input features with "battery power demand" being our target variable. The data was then split 80/20 into training and testing sets, before being standardised where required to be input into our ML models.

## Model Selection

Five machine learning models  were implemented, with their suitability for predicting EV battery power demand then compared to one another. Linear Regression and Ridge Regression provided simple baselines as linear models, while Random Forest and Gradient Boosting were used to capture the more complex relationships within the data. A neural network was also implemented as a more complex, non- linear model.

## Model Evaluation

Three key regression metrics were used to evaluate the models: Mean Absolute Error, Root Mean Square Error and the coefficient of determination (referred to as MAE, RMSE and R² respectively). MAE measured the average magnitude of errors, while RMSE gives added weight to the larger errors. The R² measures how closely the model aligns with the variations in battery power demand with values closest to one indicating more accurate prediction performance.

## Results

The Gradient Boosting model showed the strongest performance by all three metrics, achieving an MAE of 6.05kW, an RMSE of 8.90kW and an R² of 0.441. The Neural Network and Random Forest models followed close behind, both achieving an R² over 0.43. As expected the linear models performed noticeably worse, indicating that non linear methods were better suited to model the complex relationships within the vehicle data.
![R² Model Comparison](figures/fig1%20r2_model_comparison.png)

![Model Error Metrics](figures/fig%202%20model_error_metrics.png)

## Error Analysis

Further analysis was conducted to investigate how the Gradient Boosting model performed beyond the three evaluation metrics. Examining residual distributions in order to identify systematic prediction errors, the residual approximately centred around zero, with no clear evidence of systematic bias.
![Residual Distribution](figures/fig%205%20residual_distribution.png)

In order to determine the weaknesses of the model, error was compared across different operating regimes to display conditions where prediction performance deteriorated. As seen in the below figure, the MAE was highest when the vehicles were at the higher end of their operating regimes.
![Where Model Struggles](figures/fig%203%20where%20model%20strugles.png)

The Gradient Boosting model provided a balanced fit between predictive performance and model complexity, even outperforming the neural network without requiring the same complexity.
![Actual vs Predicted](figures/fig%204%20actual_vs_predicted_scatter.png)

## Key Findings

![Battery Power Demand](figures/fig%207%20battery_power_over_time.png)
- Gradient boost achieved the best predictive performance.
- Non-linear ensemble models far outperformed the linear regression approaches.
- Model performance was not always consistent as vehicle operating regimes varied.
![Operating Conditions](figures/fig%206%20vehicle_operating_conditions.png)
- Residual analysis showed a low frequency of large error and no clear evidence indicating a systematic bias.
- The results demonstrate the potential for machine learning to support EV battery power demand prediction using real world vehicle data.

## Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Plotly
- Jupyter Notebook

## How to Run

Open `EV_Battery_Power_Prediction.ipynb` in Jupyter Notebook or JupyterLab and run the cells from top to bottom. The required Python packages are listed in `requirements.txt`.





