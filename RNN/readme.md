# Improved Character-Level RNN Text Generator

## Overview
This code implements a character-level text generation model using an **enhanced SimpleRNN architecture**. The model generates text based on a given input sequence, learning patterns from the training corpus and predicting the next character in the sequence.

---

## Original Code Summary
The original code:
- Used a **single SimpleRNN layer** for character prediction.
- Employed **one-hot encoding** for input and output.
- Generated text deterministically using `argmax`.
- Had limited sequence length and no regularization.
- Was trained on a very small text corpus, which restricted generation diversity.

---

## Modifications Made

### 1. Stacked RNN Layers
- Added a **second SimpleRNN layer** to improve sequential pattern learning.
- The first layer outputs sequences (`return_sequences=True`) to allow stacking.

### 2. Bidirectional Layer
- Introduced a **Bidirectional RNN layer** to capture dependencies from both past and future context.

### 3. Dropout Regularization
- Added **Dropout layers** after each RNN layer.
- Reduces overfitting and improves generalization to unseen sequences.

### 4. Gradient Clipping
- Used **RMSprop optimizer with gradient clipping** to prevent exploding gradients.

### 5. Temperature-Based Sampling
- Replaced deterministic `argmax` with **temperature-based sampling**.
- Produces more natural, varied, and creative text sequences.

### 6. Slightly Longer Input Sequence
- Increased `seq_length` to 6 to capture more context from previous characters.

---

## Advantages of the Modified Model
- **Better sequence learning:** Stacked and bidirectional layers capture more complex patterns.  
- **Reduced overfitting:** Dropout improves model robustness.  
- **More creative text generation:** Temperature-based sampling produces varied outputs.  
- **Stable training:** Gradient clipping prevents numerical issues during backpropagation.  
- **Flexible architecture:** Can be easily adapted to longer texts or larger datasets for richer generation.

---

## Conclusion
This model demonstrates a modernized approach to character-level RNN text generation while preserving the original conceptual framework.

