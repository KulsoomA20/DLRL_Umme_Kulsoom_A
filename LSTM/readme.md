# Improved LSTM Architecture for Time Series Forecasting

## Overview
This project presents an enhanced Long Short-Term Memory (LSTM) model for time-series forecasting. The original implementation has been extended by improving the neural network architecture and replacing the dataset to demonstrate model adaptability, robustness, and better learning capacity on real-world data.

---

## Original Code Summary
The original code:
- Used the International Airline Passengers dataset
- Implemented a single-layer LSTM model
- Used a small time window
- Did not apply regularization techniques
- Trained for a fixed number of epochs without adaptive stopping

---

## Modifications Made

### 1. Dataset Replacement and Cleaning
- The airline passenger dataset was replaced with the **Daily Minimum Temperatures** dataset.
- This dataset represents real-world climate data suitable for univariate time-series forecasting.
- The dataset contained non-numeric and corrupted entries (e.g., `?0.2`).
- These values were handled by converting invalid entries to `NaN` and removing affected rows to ensure clean numerical input for the model.
- The core learning problem remains unchanged, ensuring conceptual continuity.

### 2. Increased Time Window
- The time step (window size) was increased from **10 to 20**.
- This allows the model to capture longer temporal dependencies and seasonal patterns.

### 3. Stacked LSTM Architecture
- The model now consists of **two LSTM layers**.
- The first LSTM layer uses `return_sequences=True` to enable stacking.
- This improves the model’s ability to learn deeper temporal representations.

### 4. Dropout Regularization
- Dropout layers were added after each LSTM layer.
- This helps prevent overfitting and improves generalization on unseen data.

### 5. Early Stopping Mechanism
- Early stopping was introduced during training.
- Training halts automatically when the loss stops improving, preventing unnecessary epochs and overfitting.

### 6. Improved Training Strategy
- Batch size was increased to ensure more stable gradient updates.
- The number of training epochs was set to **50**, with early stopping ensuring efficient and controlled training.

---

## Evaluation Metric
- **Root Mean Squared Error (RMSE)** is used to evaluate model performance on both training and testing datasets.

---

## Conclusion
The improved LSTM architecture demonstrates enhanced learning capacity, better generalization, and robustness when applied to real-world time-series data. By incorporating data cleaning, architectural depth, regularization, and adaptive training strategies, the model aligns well with modern deep learning practices while preserving the original forecasting objective.

