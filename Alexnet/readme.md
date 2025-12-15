# Modern AlexNet Architecture

## Overview
This code is a modified and modernized implementation of the original AlexNet architecture using TensorFlow and Keras. The goal of this modification is to adapt the classical AlexNet model to current deep learning best practices while preserving its core design philosophy.

---

## Original Code Summary
The original implementation:
- Followed the classical AlexNet architecture
- Used large fully connected layers (4096 neurons)
- Did not include batch normalization
- Used a Flatten layer, resulting in a very large number of parameters
- Was designed specifically for ImageNet (1000 classes)
- Did not include model compilation settings

---

## Modifications Made

### 1. Batch Normalization Added
- `BatchNormalization` layers were added after each convolutional layer.
- This improves training stability and convergence speed.
- It also reduces internal covariate shift during training.

### 2. Global Average Pooling Introduced
- The `Flatten()` layer was replaced with `GlobalAveragePooling2D()`.
- This significantly reduces the number of trainable parameters.
- Helps in preventing overfitting and improves generalization.

### 3. Reduced Fully Connected Layer Size
- Fully connected layers were reduced from **4096 neurons to 1024 neurons**.
- Makes the model lighter and more suitable for smaller datasets.
- Maintains strong representational power while reducing computation.

### 4. Dataset-Agnostic Design
- The number of output classes is now configurable.
- The model can be used with datasets such as CIFAR-10, CIFAR-100, or custom image datasets.

### 5. Model Compilation Added
- The model is compiled using:
  - **Adam optimizer**
  - **Categorical Crossentropy loss**
  - **Accuracy metric**
- This makes the model immediately ready for training.

---

## Advantages of the Modified Model
- Improved training stability
- Reduced overfitting
- Lower computational complexity
- Flexible and reusable architecture
- Aligns with modern deep learning standards

---

## Conclusion
This modernized AlexNet retains the original architectural concept while integrating contemporary techniques to enhance performance, scalability, and usability for real-world image classification tasks.

