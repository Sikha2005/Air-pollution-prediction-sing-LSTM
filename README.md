# Air-pollution-prediction-sing-LSTM

This repository implements **PM2.5 time-series forecasting** using an **LSTM (Long Short-Term Memory)** model.  
The project supports **multiple forecasting horizons** and produces **research-ready plots**.

---

## ⏱️ Forecasting Horizons

- **1 Hour Ahead**
- **24 Hours Ahead**
- **1 Week Ahead**
- **2 Weeks Ahead**

Each horizon is evaluated using **Actual vs Predicted** plots.

---

## 📂 Dataset

- **File:** `air-quality-india.csv`
- **Target Column:** `PM2.5`
- **Preprocessing:**
  - Missing values handled using forward & backward fill
  - Min–Max scaling
  - Sliding window sequence generation

---

## 🧠 Model Architecture

- **Model:** LSTM
- **Window Size:** 37
- **LSTM Units:** 9
- **Dropout:** 0.2
- **Optimizer:** Adam (learning rate = 1e-5)
- **Loss Function:** Mean Squared Error (MSE)

This lightweight architecture is optimized for **CPU / Jupyter Notebook** usage.

---

## 📈 Visualization Strategy

- **Short-term forecasts (1h, 24h):**
  - Direct Actual vs Predicted plots
- **Long-term forecasts (1 week, 2 weeks):**
  - Actual data is **smoothed using moving average**
  - Ensures fair comparison with LSTM predictions (trend-based)

---

💾 Saved Figures

**The following figures are saved automatically:**

PM25_Actual_vs_Predicted_1Hour.png

PM25_Actual_vs_Predicted_24Hours.png

PM25_Actual_vs_Predicted_1Week.png

PM25_Actual_vs_Predicted_2Weeks_1500points.png
