# AI Import Export Trade Analysis

## Overview

This project analyzes global import–export trade patterns and predicts future trade values and USD–INR exchange rates using machine learning and time-series forecasting models.

The system combines **clustering**, **regression**, and **deep learning** techniques to understand international trade relationships and forecast economic trends.

The goal is to explore how trade data and exchange rates interact and to build predictive models that estimate future trade values in INR.

---

## Key Objectives

* Analyze historical global trade data
* Identify clusters of trading partner countries
* Predict total trade value using machine learning models
* Forecast USD–INR exchange rates using deep learning and time-series models
* Visualize trends and evaluate model performance

---

## Dataset

### Trade Data

The global import–export trade datasets used in this project were obtained from **Kaggle**.

These datasets contain historical trade values between countries categorized by HS2 product codes for the period **2010–2021**.

Attributes include:

* Country
* Year
* Export value (USD)
* Import value (USD)

Kaggle Dataset Source:
https://www.kaggle.com/

Files used in this project:

* `2010_2021_HS2_export.csv`
* `2010_2021_HS2_import.csv`

### Exchange Rate Data

USD–INR exchange rate data was obtained using the **Yahoo Finance API** via the `yfinance` Python library.

The dataset contains historical daily exchange rate values which were later aggregated for forecasting models.

File used:

* `USD_INR_Exchange.csv`

---

## Project Structure

```
AI-Import-Export-Trade-Analysis
│
├── README.md
├── requirements.txt
│
├── notebooks
│   └── trade_analysis.ipynb
│
├── data
│   ├── 2010_2021_HS2_export.csv
│   ├── 2010_2021_HS2_import.csv
│   └── USD_INR_Exchange.csv
│
└── results
    └── plots
```

### Folder Description

**notebooks/**
Contains the main Jupyter notebook where the entire analysis and modeling workflow is implemented.

**data/**
Contains all datasets used in the project.

**results/**
Stores visualizations, predictions, and generated outputs.

---

## Machine Learning Models Used

### 1. Gaussian Mixture Model (GMM)

Used for clustering countries based on trade characteristics.

Purpose:

* Identify groups of countries with similar trade behavior
* Classify trade partners into strategic tiers

Cluster evaluation metrics:

* Silhouette Score
* Davies-Bouldin Index
* Calinski-Harabasz Score

---

### 2. Random Forest Regressor

Used for predicting total trade value.

Advantages:

* Handles nonlinear relationships
* Robust to noise
* Good baseline regression model

---

### 3. XGBoost Regressor

Gradient boosting algorithm used to improve prediction accuracy.

Advantages:

* Handles complex relationships
* Regularization reduces overfitting
* High performance on tabular datasets

---

### 4. Ensemble Model (Voting Regressor)

Combines predictions from:

* Random Forest
* XGBoost

Purpose:
Improve predictive performance by combining multiple models.

---

### 5. LSTM (Long Short-Term Memory)

Deep learning model used for short-term exchange rate forecasting.

Why LSTM:

* Captures temporal dependencies
* Effective for sequential data
* Learns long-term patterns in financial time series

---

### 6. Prophet

Used for long-term USD-INR forecasting.

Advantages:

* Handles seasonality and trends
* Works well for economic time-series data
* Provides uncertainty intervals

---

## Workflow

```
Trade Data
   │
   ▼
Data Preprocessing
   │
   ▼
Trade Clustering (Gaussian Mixture Model)
   │
   ▼
Feature Engineering
   │
   ▼
Trade Value Prediction
(Random Forest + XGBoost Ensemble)
   │
   ▼
Exchange Rate Forecast
   ├── LSTM (Short-term)
   └── Prophet (Long-term)
```

---

## Evaluation Metrics

### Clustering

* Silhouette Score
* Davies-Bouldin Index
* Calinski-Harabasz Score

### Regression

* R² Score
* MAE (Mean Absolute Error)
* RMSE (Root Mean Squared Error)
* MAPE (Mean Absolute Percentage Error)

### Forecasting

* MAE
* RMSE
* MAPE

---

## Running the Project

Open the Jupyter notebook:

```
notebooks/trade_analysis.ipynb
```

Run all cells to reproduce the analysis and results.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* TensorFlow / Keras
* Prophet
* Matplotlib
* Seaborn
* Yahoo Finance API

---

## Future Improvements

* Add real-time trade data APIs
* Deploy models using FastAPI
* Build an interactive dashboard with Streamlit
* Improve forecasting using transformer-based models
* Automate data pipeline updates

---

## Author

**Anagha Hegde**

GitHub:
https://github.com/AnaghaHegde05

---

## License

This project is for educational and research purposes.
