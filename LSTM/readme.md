# Time Series Forecasting Using an Improved LSTM Model

## Overview
This code implements an improved Long Short-Term Memory (LSTM) neural network for univariate time-series forecasting. The original model has been enhanced by modifying the dataset and upgrading the network architecture to better capture temporal dependencies and improve learning stability.

---

## Original Code Summary
The original implementation:
- Used the International Airline Passengers dataset
- Implemented a single-layer LSTM network
- Used a small fixed time window
- Did not include regularization techniques
- Trained the model for a fixed number of epochs without adaptive control

---

## Modifications Made

### 1. Dataset Replacement
- The original airline passenger dataset was replaced with the **Daily Minimum Temperatures** dataset.
- This dataset represents real-world climate data collected over several years.
- The learning objective remains the same: predicting future values from past observations.

### 2. Data Cleaning and Preprocessing
- Non-numeric values present in the dataset were handled appropriately.
- The temperature values were converted to floating-point format for model compatibility.
- Min-Max normalization was applied to improve training stability.

### 3. Increased Time Window
- The time-step (look-back window) was increased from 10 to 20.
- This allows the model to learn longer-term temporal patterns.

### 4. Stacked LSTM Architecture
- The model was upgraded to a **two-layer stacked LSTM architecture**.
- The first LSTM layer returns sequences to support deeper temporal learning.
- This enhances the model’s capacity to capture complex trends in time-series data.

### 5. Dropout Regularization
- Dropout layers were added after each LSTM layer.
- This reduces overfitting and improves generalization on unseen data.

### 6. Improved Training Strategy
- The number of training epochs was adjusted to 50 for efficient learning.
- Batch size was increased to stabilize gradient updates.
- Early stopping was introduced to prevent unnecessary training once convergence is achieved.

---

## Advantages of the Modified Model
- Better ability to learn long-term temporal dependencies
- Reduced overfitting due to dropout and early stopping
- Improved adaptability to different real-world time-series datasets
- More stable and efficient training process
- Cleaner and more modular model architecture

---

## Conclusion
The improved LSTM model demonstrates a more robust and flexible approach to time-series forecasting. By enhancing the dataset, architecture, and training strategy, the modified implementation aligns with modern deep learning practices while preserving the core forecasting objective of the original code.
