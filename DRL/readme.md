# Deep Reinforcement Learning: Q-Learning with Environmental Awareness

## Overview
This code implements **Q-Learning** to find the most efficient path in a graph from a start node to a goal node.  
The modified version improves the original implementation by introducing a **structured codebase**, an **epsilon-greedy policy** for better exploration/exploitation, and extended training iterations for more stable convergence.

---

## Original Code Summary
The original implementation:
- Defined a graph with nodes and edges, including environmental factors (police and drug trace nodes).
- Constructed a reward (R) matrix for transitions, with high reward for reaching the goal node.
- Implemented basic Q-Learning to find the most efficient path.
- Tracked visits to environmental nodes using `env_police` and `env_drugs`.
- Sampled actions randomly from available options without a formal exploration/exploitation strategy.
- Trained over 1000 iterations and plotted cumulative rewards.

---

## Modifications Made

### 1. Epsilon-Greedy Policy
- Replaced fully random action selection with an **epsilon-greedy policy**.
- Balances exploitation of known high-reward paths with exploration of less-visited paths.
- Improves convergence reliability and prevents the agent from getting stuck in suboptimal paths.

### 2. Code Refactoring and Modularization
- Encapsulated key logic into functions for action selection, Q-value updates, and environmental interactions.
- Ensures a **cleaner, more readable code structure**.
- Random starting states used during training for better exploration coverage.

### 3. Extended Training
- Increased training iterations from 1000 to 5000.
- Provides more stable learning and better reward convergence over the course of training.

### 4. Environmental Interaction Handling
- Maintains the original environmental matrices (`env_police` and `env_drugs`).
- Updates environmental interactions consistently within Q-value updates.
- Reinforces safe decision-making indirectly via epsilon-greedy exploration and action filtering.

---

## Advantages of the Modified Model
- **More stable learning** due to epsilon-greedy exploration.
- **Cleaner, modular code** that is easier to read, maintain, and extend.
- **Improved reward convergence** with extended iterations and random starting states.
- Retains **environmental interaction tracking** without redundant logic.

---

## Conclusion
The modified Q-Learning implementation improves upon the original by enhancing exploration/exploitation, training stability, and code clarity.  
The agent reliably learns the most efficient paths while preserving the environmental awareness logic from the original code.
