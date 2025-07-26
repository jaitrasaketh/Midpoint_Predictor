# Midpoint Price Prediction for High-Frequency Crypto Limit Order Books

## 📈 Overview

This project aims to predict the **midpoint prices** of cryptocurrencies using **high-frequency limit order book (LOB)** data. Traditional ML models struggle with fast-moving financial data and trend alignment. This work combines classical ML and deep learning — with a **custom hybrid CNN + SVR model and a trend-aware loss function** — to improve both accuracy and interpretability.

---

## 🔍 Problem Statement

In volatile crypto markets, accurately forecasting **midpoint prices** is crucial for trading strategies and market-making. This project targets robust predictions using:
- **Deep learning** (CNN, LSTM, MLP)
- **Classical ML** (SVR, KNN)
- A **custom loss function** designed to enforce **directional trend alignment**

---

## 🧠 Key Contributions

- Designed and trained a **hybrid CNN + SVR model** with a novel, dynamically scaled **epsilon-insensitive loss function**.
- Incorporated **Order Flow Imbalance (OFI)** to capture market sentiment (bullish vs bearish).
- Compared multiple models across 5-level and 10-level LOB depths.
- Delivered **state-of-the-art performance** with the proposed approach:
  - 📉 **MSE**: 28.05
  - 📈 **R²**: 0.998

---

## 📊 Dataset

- Source: Kaggle — *High Frequency Crypto Limit Order Book Data*  
- Asset: Ethereum (ETH)
- Time Range: April 7–19, 2021 (minute-level)
- Features:  
  - 150+ columns, including bid/ask volumes, distances from midpoint, market notional
  - Derived features: OFI, actual price from distance

---

## 🧪 Models Implemented

| Type             | Models                                  |
|------------------|------------------------------------------|
| Classical ML     | K-Nearest Neighbors (KNN), SVR           |
| Deep Learning    | LSTM, MLP, CNN + LSTM                    |
| Hybrid + Custom  | CNN + SVR with custom trend-aware loss   |

All models were trained on **rolling 100-record windows**, normalized, and evaluated using **MSE** and **R²**.

---

## ⚙️ Custom Loss Function

The custom loss function combines:

- **Epsilon-insensitive loss**: Ignores small prediction errors
- **Trend alignment penalty**: Penalizes angular difference between true and predicted trends
- **Dynamic epsilon**: Scales with standard deviation of target values

This encourages the model to focus on **both magnitude and direction** of price movements — vital for financial forecasting.

---

## 📈 Results Snapshot

| Model                | MSE (10 Levels) | R² (10 Levels) |
|----------------------|-----------------|----------------|
| SVR                 | 948.72          | 0.932          |
| LSTM                | 335.52          | 0.976          |
| CNN + LSTM          | 45.21           | 0.996          |
| CNN + SVR (custom)  | **28.05**       | **0.998**      |

---

## 📌 Future Work

- Integrate **attention mechanism** over OFI to dynamically weigh sentiment shifts
- Extend to **second-level prediction granularity**
- Explore **ensemble methods** for higher robustness
- Optimize for **real-time deployment**

---

## 📌 Future Work

- Integrate **attention mechanism** over OFI to dynamically weigh sentiment shifts
- Extend to **second-level prediction granularity**
- Explore **ensemble methods** for higher robustness

## 🧑‍💻 Author

**Sri Jaitra Saketh Goparaju**  
- Email: jaisaketh345@gmail.com  
- GitHub: [@jaitrasaketh](https://github.com/jaitrasaketh)

---


