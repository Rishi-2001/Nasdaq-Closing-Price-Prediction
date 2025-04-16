# Nasdaq Closing Price Prediction - Optiver Challenge

This project is based on the **Optiver "Trading at the Close"** Kaggle competition, where the goal is to predict short-term price movements of Nasdaq-listed stocks during the final 10 minutes of the trading session.

---

## Problem Statement

The objective is to develop a machine learning model that forecasts **closing price movements** by utilizing:
- Order book data
- Closing auction signals

The model aims to identify potential trading opportunities and improve decision-making by minimizing the **Mean Absolute Error (MAE)** between the predicted return and the observed return.

---

## Dataset Overview

The dataset includes:
- Historical **order book data** (bid/ask prices, volumes)
- **Auction-level data** (imbalance indicators, matched volumes)
- **Target**: Future return of a synthetic Nasdaq index based on individual stock movements

All stock identifiers are anonymized.

---

## Approach

### Feature Engineering
- Extracted statistical features from the order book and auction data
- Created imbalance-based indicators to capture supply/demand pressure
- Normalized key variables to handle volatility differences across stocks

### Model Development
- Primary Model: **LightGBM Regressor**
- Training with **K-Fold Cross-Validation**
- Experiments with:
  - **XGBoost** using GPU acceleration (`gpu_hist`)
  - **Random Forest Regressor** (commented for reference)

### Hyperparameter Tuning
- Used **Optuna** for efficient hyperparameter search
- GridSearchCV and Hyperopt setup included (optional and commented)

### Evaluation
- Evaluation Metric: **Mean Absolute Error (MAE)**

<div align="center">
  <img src="https://github.com/user-attachments/assets/c8c9a803-a4f7-4102-8b4f-cee4f94a5c2a" alt="MAE Formula" width="400"/>
</div>

---

## Visualizations & Insights

- **Feature Importance Plots**:  
  Used LightGBM’s `plot_importance()` to visualize key features influencing the model’s predictions. These plots helped identify which order book and auction metrics were most predictive of price movement.

- **Auction Imbalance Analysis**:  
  Auction imbalance data provided a clear signal of demand-supply skew. Analyzing this helped improve the model’s sensitivity to directional pressure during the final minutes of trading.

- **Cross-Validation Curves**:  
  MAE scores were plotted across folds, confirming model stability and generalizability across different stock IDs and trading dates.

---

## Results

- The LightGBM model, after hyperparameter tuning with **Optuna**, achieved **low MAE scores**, outperforming basic baseline regressors.
- Most predictive features:
  - Order imbalance indicators
  - Depth of book metrics
  - Previous auction price volatility

- The model generalized well across unseen stocks, showing its robustness in a real-time trading scenario.

---

## Future Improvements

- **Advanced Temporal Models**:  
  Explore temporal models like LSTM or Transformers to better handle sequence information in order book updates.

- **Dynamic Feature Windows**:  
  Introduce rolling or exponentially weighted features to capture evolving patterns in microstructure signals.

- **Model Ensembling**:  
  Combine LightGBM, XGBoost, and Random Forest using stacking or blending to capture diverse model strengths.

- **Live Simulation**:  
  Simulate final auction trading windows with streaming data to benchmark live predictive power.

---

## Related Links

- [Kaggle Competition: Optiver - Trading at the Close](https://www.kaggle.com/competitions/optiver-trading-at-the-close)
  
