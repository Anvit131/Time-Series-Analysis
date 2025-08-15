# Time-Series-Analysis
# Time Series Forecasting of Air Quality (CO Concentration)

## Overview

This project focuses on forecasting the concentration of carbon monoxide (CO) using time series models and machine learning approaches. Using a dataset indexed by datetime containing multiple air quality sensor measurements and meteorological data, the project explores various modeling techniques to predict future CO levels.

---

## Dataset

The dataset includes these columns:

- **Target variable:** `CO(GT)` — concentration of carbon monoxide
- **Exogenous features:** Sensor readings and meteorological factors including:
  - `PT08.S1(CO)`, `NMHC(GT)`, `C6H6(GT)`, `PT08.S2(NMHC)`, `NOx(GT)`,
    `PT08.S3(NOx)`, `NO2(GT)`, `PT08.S4(NO2)`, `PT08.S5(O3)`, `T` (temperature),
    `RH` (relative humidity), `AH` (absolute humidity)
- **Index:** Datetime index marking each observation time

---

## Key Components

### 1. Data Preprocessing

- Handling missing values and interpolation if necessary
- Resampling to daily frequency for visualization and seasonality analysis
- Winsorization to clip outliers between the 1st and 99th percentile
- Stationarity tests with Augmented Dickey-Fuller (ADF) test

### 2. Exploratory Data Analysis

- Visualization of daily and hourly/monthly seasonal patterns using line plots and heatmaps

### 3. Modeling Approaches

- **SARIMA model:** Classic time series model with seasonal components
- **RandomForest regression:** Machine learning model using lagged features and exogenous variables
- **XGBoost regression:** Gradient boosting model using the same features
- **LSTM:** Deep learning model for sequential prediction with lagged and exogenous features

### 4. Model Evaluation

- Train/test split with 80/20 ratio
- Error metrics: Mean Absolute Error (MAE) and Mean Absolute Percentage Error (MAPE)
- Residual diagnostics for SARIMA
- Visualization of actual vs predicted values for all models

---

## How to Run

1. **Install dependencies:**

pip install numpy pandas matplotlib seaborn statsmodels scikit-learn xgboost tensorflow


2. **Load your dataset** into a pandas DataFrame `df` with a datetime index.

3. **Set the target column:**


4. **Run preprocessing, EDA, modeling, and evaluation steps** sequentially.

5. **Train models:** SARIMA, RandomForest, XGBoost, LSTM (code structured in separate blocks).

6. **Generate predictions** and visualize results.

7. **Perform multi-step forecasting** using the provided recursive LSTM code.

---

## Project Structure

- `data_preprocessing.py`: Data cleaning and feature engineering
- `eda.py`: Exploratory data analysis and visualization
- `sarima_model.py`: SARIMA training and forecasting
- `ml_models.py`: RandomForest, XGBoost, LSTM model implementations
- `forecasting.py`: Multi-step forecasting methods
- `visualizations.py`: Plotting actual vs predicted, residuals, and diagnostics

---

## Results

- Quantitative error metrics for each model are printed during execution.
- Visual comparisons show strengths and weaknesses of respective approaches.
- SARIMA offers interpretable seasonal components and residual diagnostics.

---

## Future Work

- Include hyperparameter tuning and model selection automation.
- Extend to additional pollutants and multivariate forecasting.
- Deploy models as APIs or interactive dashboards.
- Improve forecast uncertainty quantification and explanation.
- LSTM provides flexible multi-step forecasting capabilities.

---

## License

MIT License
