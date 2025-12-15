# Fashion-MNIST Image Classification Using a Deep CNN

## Overview
This code implements a deep Convolutional Neural Network (CNN) for image classification on the Fashion-MNIST dataset. The original model has been enhanced by modifying the dataset and upgrading the network architecture to improve feature extraction, classification accuracy, and visualization of learned representations.

---

## Original Code Summary
The original implementation:
- Used the Cats vs Dogs dataset  
- Implemented a small CNN with 3 convolutional layers  
- Used 150x150 color images  
- Did not employ transfer learning or advanced architectures  
- Trained the model for a fixed number of epochs without detailed visualization of predictions  

---

## Modifications Made

### 1. Dataset Replacement
- The original Cats vs Dogs dataset was replaced with **Fashion-MNIST**, a widely-used benchmark dataset of grayscale images of clothing items.  
- This dataset contains 60,000 training images and 10,000 test images across 10 classes.  
- The learning objective remains the same: classifying images into the correct category.

### 2. Image Preprocessing
- Reshaped images to match the input shape `(28, 28, 1)` for CNN compatibility.  
- Normalized pixel values to a range of 0 to 1 for stable and efficient training.  

### 3. Deeper CNN Architecture
- Added multiple convolutional layers with increasing filters (32 → 64 → 64) for deeper feature extraction.  
- Used MaxPooling after each convolutional block to reduce spatial dimensions and computation.  
- Flattened feature maps before dense layers for classification.

### 4. Dense Layers and Output
- Added a fully connected Dense layer with 64 neurons for higher-level feature learning.  
- Output layer consists of 10 neurons (one per class) with logits for classification.  
- Used `SparseCategoricalCrossentropy` loss suitable for integer labels.  

### 5. Training Enhancements
- Optimizer switched to **Adam** for adaptive learning rates.  
- Increased number of epochs to 10 for better convergence on Fashion-MNIST.  
- Validation set used to monitor performance during training.  

### 6. Visualization
- Plotted training and validation accuracy over epochs.  
- Displayed model predictions on 8 random test images with color-coded labels (green = correct, red = incorrect).  
- Provided insight into model’s ability to distinguish visually similar classes.  

---

## Advantages of the Modified Model
- Handles grayscale images efficiently and generalizes to 10 classes.  
- Deeper convolutional layers improve feature extraction and classification accuracy.  
- Normalization and modern optimizer ensure stable training.  
- Visualizations aid understanding of model predictions and layer representations.  
- Modular and extensible architecture allows future upgrades, e.g., transfer learning or data augmentation.  

---

## Conclusion
The improved CNN model provides a robust framework for image classification on Fashion-MNIST. By enhancing the dataset, network depth, preprocessing, and visualization strategy, the modified implementation demonstrates higher accuracy, better generalization, and a clear understanding of how CNNs process image data.  
