# Section 12: Deep Q-Learning

**Course:** Practical AI with Python and Reinforcement Learning  
**Section:** 12 - Deep Q-Learning  
**Status:** ✅ Completed
---

## 📚 Section Overview
This section introduces **Deep Q-Learning (DQN)**, a major advancement in reinforcement learning that combines Q-Learning with deep neural networks. You'll learn the theory behind DQN, implement it manually, and also use Keras-RL2 for rapid development.

### Lecture Breakdown
| # | Lecture | Duration | Status |
|---|---------|----------|--------|
| 109 | DQN Section Overview | 2min | ✅ |
| 110 | History of DQN | 5min | ✅ |
| 111 | DQN Theory and Intuition - Part One - Review of Core RL Ideas | 5min | ✅ |
| 112 | DQN Theory and Intuition - Part Two - Neural Networks for RL | 11min | ✅ |
| 113 | DQN Theory and Intuition - Part Three - Feedback and Function Approximation | 21min | ✅ |
| 114 | DQN Theory and Intuition - Part Four - Experience Replay | 19min | ✅ |
| 115 | DQN Theory and Intuition - Part Five - Mapping Key Ideas to Code | 16min | ✅ |
| 116 | DQN Manual Implementation - Part One - Imports and Environment | 5min | ✅ |
| 117 | DQN Manual Implementation - Part Two - Artificial Neural Network | 7min | ✅ |
| 118 | DQN Manual Implementation - Part Three - Hyperparameters and Functions | 19min | ✅ |
| 119 | DQN Manual Implementation - Part Four - Model Training | 16min | ✅ |
| 120 | DQN - Keras-RL2 - Part One - Overview | 7min | ✅ |
| 121 | DQN - Keras-RL2 - Part Two - Imports and Environment | 3min | ✅ |
| 122 | DQN - Keras-RL2 - Part Three - Creating the ANN | 6min | ✅ |
| 123 | DQN - Keras-RL2 - Part Four - DQN Agent | 14min | ✅ |

**Total Time:** 2hr 49min (All Completed ✅)

---

## 🎯 Key Learning Points (All Mastered ✅)

### DQN Theory and Intuition
- ✅ Review of core Reinforcement Learning ideas
- ✅ Why neural networks are needed for RL
- ✅ Feedback and function approximation
- ✅ Experience Replay (breaking correlation in sequential data)
- ✅ Mapping key theoretical ideas to code

### Manual DQN Implementation
- ✅ Setting up imports and environment
- ✅ Building the Artificial Neural Network (ANN)
- ✅ Setting hyperparameters and functions
- ✅ Model training loop
- ✅ Target networks and stability techniques

### Keras-RL2 Implementation
- ✅ Overview of Keras-RL2 library
- ✅ Setting up imports and environment
- ✅ Creating the ANN for DQN
- ✅ Building and configuring the DQN Agent

---

## 📝 Personal Notes
*Add your own notes, code snippets, or tips here:*

### DQN Key Concepts

| Concept | Description |
|---------|-------------|
| **Function Approximation** | Use neural networks to approximate Q-values instead of a Q-table |
| **Experience Replay** | Store transitions in a buffer and sample randomly to break correlation |
| **Target Network** | A separate network for calculating target Q-values, updated periodically |
| **Epsilon-Greedy** | Balance exploration and exploitation during training |

### Manual DQN Implementation (Core Loop)
```python
import numpy as np
import tensorflow as tf
from tensorflow.keras import layers, models

# 1. Build the Q-Network
def build_model(state_size, action_size):
    model = models.Sequential([
        layers.Dense(24, activation='relu', input_shape=(state_size,)),
        layers.Dense(24, activation='relu'),
        layers.Dense(action_size, activation='linear')
    ])
    model.compile(optimizer='adam', loss='mse')
    return model

# 2. Experience Replay Buffer
class ReplayBuffer:
    def __init__(self, max_size=10000):
        self.buffer = []
        self.max_size = max_size
    
    def add(self, experience):
        if len(self.buffer) >= self.max_size:
            self.buffer.pop(0)
        self.buffer.append(experience)
    
    def sample(self, batch_size):
        indices = np.random.choice(len(self.buffer), batch_size, replace=False)
        return [self.buffer[i] for i in indices]

# 3. DQN Training Step
def train_step(model, target_model, batch, gamma=0.95):
    states = np.array([e[0] for e in batch])
    actions = np.array([e[1] for e in batch])
    rewards = np.array([e[2] for e in batch])
    next_states = np.array([e[3] for e in batch])
    dones = np.array([e[4] for e in batch])
    
    # Predict Q-values for current states
    q_values = model.predict(states, verbose=0)
    
    # Predict Q-values for next states using target network
    next_q_values = target_model.predict(next_states, verbose=0)
    
    # Update Q-values using Bellman equation
    for i in range(len(batch)):
        if dones[i]:
            q_values[i][actions[i]] = rewards[i]
        else:
            q_values[i][actions[i]] = rewards[i] + gamma * np.max(next_q_values[i])
    
    # Train the model
    model.fit(states, q_values, epochs=1, verbose=0)
```

### Keras-RL2 Implementation
```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Flatten
from rl.agents import DQNAgent
from rl.policy import BoltzmannQPolicy
from rl.memory import SequentialMemory

# Build model
def build_model(states, actions):
    model = Sequential([
        Flatten(input_shape=(1, states)),
        Dense(24, activation='relu'),
        Dense(24, activation='relu'),
        Dense(actions, activation='linear')
    ])
    return model

# Create DQN Agent
model = build_model(env.observation_space.shape[0], env.action_space.n)
memory = SequentialMemory(limit=50000, window_length=1)
policy = BoltzmannQPolicy()
dqn = DQNAgent(model=model, memory=memory, policy=policy, 
               nb_actions=env.action_space.n, nb_steps_warmup=10, 
               target_model_update=1e-2)
dqn.compile(optimizer='adam', metrics=['mae'])

# Train
dqn.fit(env, nb_steps=50000, visualize=False, verbose=1)

# Test
dqn.test(env, nb_episodes=5, visualize=True)
```

### Key Hyperparameters
| Parameter | Typical Value | Effect |
|-----------|---------------|--------|
| **Learning Rate** | 0.001 | Step size for updates |
| **Gamma (γ)** | 0.95-0.99 | Discount factor for future rewards |
| **Epsilon (ε)** | 1.0 → 0.01 | Exploration rate (decays over time) |
| **Batch Size** | 32-64 | Number of samples per training step |
| **Memory Size** | 10,000-100,000 | Size of replay buffer |
| **Target Update** | 0.01 | How often target network updates |

---

## 🚀 All Lectures Completed ✅

| Topic Area | Lectures Completed |
|------------|-------------------|
| DQN Overview & History | 109-110 |
| DQN Theory & Intuition | 111-115 |
| Manual DQN Implementation | 116-119 |
| Keras-RL2 Implementation | 120-123 |

---

## 🔗 Resources
- [DQN Paper (Nature 2015)](https://www.nature.com/articles/nature14236)
- [Keras-RL2 Documentation](https://github.com/taylormcnally/keras-rl2)
- [Experience Replay Explained](https://paperswithcode.com/method/experience-replay)
- [TensorFlow Documentation](https://www.tensorflow.org/)

---

## 💡 Key Takeaways from This Section
- **DQN** combines Q-Learning with deep neural networks to handle large state spaces.
- **Experience Replay** breaks correlation in sequential data by storing and randomly sampling transitions.
- **Target Networks** stabilize training by providing consistent Q-value targets.
- **Manual Implementation** builds deep understanding of the internals.
- **Keras-RL2** provides a high-level API for rapid DQN development.
- **Hyperparameters** like learning rate, gamma, and epsilon are critical for success.
- This section bridges **classical Q-Learning** and **modern deep RL**.
- The **Snake game project** (upcoming) will apply all these concepts.
