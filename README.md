# Air-pollution-prediction-using-LSTM

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

PM25 Actualvs Predicted 1Hour-saved as actual_vs_predicted.png

PM25 Actual vsP redicted 24Hours saved as 24hr actual_vs_predicted.png

PM25 Actual vs Predicted 1Week.png saved as PM25_Actual_vs_Predicted_700points.png

PM25 Actual vs Predicted 2Weeks saved as PM25_Actual_vs_Predicted_2Weeks_1500points.png

# PROCEDURE
# 1. Data Loading
-The air-quality dataset is loaded from a CSV file.

-Only the PM2.5 column is selected as the target variable for prediction.

# 2. Data Preprocessing
 -Missing PM2.5 values are handled using forward fill and backward fill to maintain continuity in the time-series data.

# 3. Data Scaling
 -Min-Max normalization is applied to scale PM2.5 values into the range [0, 1].
 -This improves training stability and convergence of the LSTM model.

# 4. Sequence Generation (Sliding Window)
 -A sliding window of 37 time steps is used.
 -Each input sequence contains 37 past PM2.5 values,and the model learns to predict the next PM2.5 value.

# 5. Train–Test Split
 -The dataset is split into 80% training data and 20% testing data.
 -Temporal order is preserved (no random shuffling).

# 6. Model Architecture
 A lightweight LSTM network is used:
 - LSTM layer with 9 units to capture temporal dependencies
 - Dropout layer (0.2) to reduce overfitting
 - Dense output layer for PM2.5 prediction

# 7. Model Training
 The model is trained using:
 - Adam optimizer with a low learning rate (1e-5)
 - Mean Squared Error (MSE) loss function
 Training epochs are kept low for CPU-friendly execution.

# 8. Prediction
-The trained model generates predictions on the test dataset.
-Predicted values are inverse-transformed back to original PM2.5 scale.

# 9. Visualization
 Actual vs Predicted PM2.5 values are plotted for:
 - 1 hour forecast
 - 24 hour forecast
 - 1 week forecast
 - 2 week forecast
# For long-term forecasts, moving average smoothing is applied
# to the actual data to enable fair comparison with LSTM predictions.



