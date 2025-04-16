# Project – Nasdaq Closing Price Prediction Challenge

## Description
Develop a model that predicts **closing price movements** for Nasdaq-listed stocks during the crucial **final ten minutes** of each trading day. Leverage data from the **order book** and **closing auction** to gain insights into supply and demand dynamics, and identify trading opportunities.

---

## Objective
Create a predictive model that forecasts **closing price movements** for a diverse range of Nasdaq-listed stocks by using information from:
- The **order book**
- The **closing auction**

---

## Dataset
The dataset consists of **historical data** from:
- Order book activity
- Closing auction data  
It includes features such as **order book dynamics**, **auction data**, and **closing price movements**.

---

## Evaluation Criteria
Models will be evaluated using the **Mean Absolute Error (MAE)** between the **predicted return** and the **observed target**.

### MAE Formula

<div align="center">
  <img src="https://github.com/user-attachments/assets/c8c9a803-a4f7-4102-8b4f-cee4f94a5c2a" alt="MAE Formula" width="400"/>
</div>

---

## Challenges and Considerations
- **Combining Order Book and Auction Data**:  
  Merge insights from both sources to improve prediction accuracy.

- **Supply and Demand Dynamics**:  
  Understand and model the real-time interactions between supply and demand.

- **Trading Opportunities**:  
  Identify opportunities in the last minutes of trading based on market dynamics.

---

> **Note**: This project is inspired by the [Optiver - Trading at the Close](https://www.kaggle.com/competitions/optiver-trading-at-the-close) Kaggle competition.
