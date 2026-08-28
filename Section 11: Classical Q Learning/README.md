# Section 11: Classical Q Learning

**Course:** Practical AI with Python and Reinforcement Learning  
**Section:** 11 - Classical Q Learning  
**Status:** ✅ Completed  
**Completed on:** [Add Date]

---

## 📚 Section Overview
This section introduces **Classical Q-Learning**, a foundational reinforcement learning algorithm. You'll learn the theory behind Q-Learning, implement it from scratch, and explore both discrete and continuous state spaces.

### Lecture Breakdown
| # | Lecture | Duration | Status |
|---|---------|----------|--------|
| 90 | Introduction to Classical Q-Learning Overview | 4min | ✅ |
| 91 | History of Q-Learning | 4min | ✅ |
| 92 | Q-Learning Theory - Part One - Stable Inflation | 5min | ✅ |
| 93 | Q-Learning Theory - Part Two - Q-Large Equation | 5min | ✅ |
| 94 | Q-Learning Theory - Part Three - Q-Upside Equation | 5min | ✅ |
| 95 | Q-Learning Theory - Part Four - Hypercontractile Q Updates | 5min | ✅ |
| 96 | Q-Learning Implementation - Part One - Environment Setup | 5min | ✅ |
| 97 | Q-Learning Implementation - Part Two - Stable and Hyperparameters | 5min | ✅ |
| 98 | Q-Learning Implementation - Part Three - Update Function | 5min | ✅ |
| 99 | Q-Learning Implementation - Part Four - Agent Learning | 5min | ✅ |
| 100 | Q-Learning Implementation - Part Five - Visualization and Utilization | 5min | ✅ |
| 101 | Continuous Q-Learning Theory - Part One - Environment Setup | 5min | ✅ |
| 102 | Continuous Q-Learning Theory - Part Two - Q-Update Shape | 5min | ✅ |
| 103 | Continuous Q-Learning Theory - Part Three - Decentralization Theory | 5min | ✅ |
| 104 | Continuous Q-Learning Theory - Part Four - Decentralization | 5min | ✅ |
| 105 | Continuous Q-Learning Theory - Part Five - Function and Hyperparameters | 5min | ✅ |
| 106 | Continuous Q-Learning Theory - Part Six - Training and Update | 5min | ✅ |
| 107 | Q-Learning Exercise Project | 5min | ✅ |
| 108 | Q-Learning Exercise Project - Solutions | 5min | ✅ |

**Total Time:** 2hr 50min (All Completed ✅)

---

## 🎯 Key Learning Points (All Mastered ✅)

### Q-Learning Theory
- ✅ Introduction and course overview
- ✅ History and evolution of Q-Learning
- ✅ Stable Inflation concept
- ✅ Q-Large Equation
- ✅ Q-Upside Equation
- ✅ Hypercontractile Q Updates

### Q-Learning Implementation
- ✅ Environment Setup
- ✅ Stable and Hyperparameters
- ✅ Update Function
- ✅ Agent Learning
- ✅ Visualization and Utilization

### Continuous Q-Learning
- ✅ Environment Setup
- ✅ Q-Update Shape
- ✅ Decentralization Theory
- ✅ Decentralization Implementation
- ✅ Function and Hyperparameters
- ✅ Training and Update

### Project Work
- ✅ Q-Learning Exercise Project
- ✅ Project Solutions

---

## 📝 Personal Notes
*Add your own notes, code snippets, or tips here:*

### Q-Learning Key Concepts
```python
import numpy as np

# Q-Learning Update Equation (Bellman Equation)
# Q(s,a) = Q(s,a) + α * (r + γ * max(Q(s',a')) - Q(s,a))

# Components:
# α (alpha) - learning rate (0 < α ≤ 1)
# γ (gamma) - discount factor (0 ≤ γ ≤ 1)
# r - reward
# s - current state
# a - action taken
# s' - next state
# max(Q(s',a')) - maximum Q-Value for next state

# Q-Table Update
def update_q_table(q_table, state, action, reward, next_state, alpha=0.1, gamma=0.9):
    best_next_action = np.argmax(q_table[next_state])
    td_target = reward + gamma * q_table[next_state, best_next_action]
    td_error = td_target - q_table[state, action]
    q_table[state, action] += alpha * td_error
    return q_table
```

### Epsilon-Greedy Exploration
```python
def epsilon_greedy(q_table, state, epsilon=0.1):
    """Choose action using epsilon-greedy policy."""
    if np.random.random() < epsilon:
        return np.random.randint(q_table.shape[1])  # Explore
    else:
        return np.argmax(q_table[state])  # Exploit
```

### Key Parameters
| Parameter | Range | Effect |
|-----------|-------|--------|
| **Learning Rate (α)** | 0 to 1 | How quickly Q-values update |
| **Discount Factor (γ)** | 0 to 1 | Importance of future rewards |
| **Epsilon (ε)** | 0 to 1 | Exploration vs. exploitation |

---

## 🚀 All Lectures Completed ✅

| Topic Area | Lectures Completed |
|------------|-------------------|
| Q-Learning Overview & History | 90-91 |
| Q-Learning Theory | 92-95 |
| Q-Learning Implementation | 96-100 |
| Continuous Q-Learning | 101-106 |
| Project & Solutions | 107-108 |

---

## 🔗 Resources
- [Q-Learning Wikipedia](https://en.wikipedia.org/wiki/Q-learning)
- [Bellman Equation](https://en.wikipedia.org/wiki/Bellman_equation)
- [Reinforcement Learning Course by Sutton & Barto](http://incompleteideas.net/book/the-book-2nd.html)

---

## 💡 Key Takeaways from This Section
- **Q-Learning** is a model-free reinforcement learning algorithm.
- The **Q-Table** stores values for each state-action pair.
- **Bellman Equation** defines the optimal Q-Value for a state-action pair.
- **Learning Rate (α)** controls how quickly Q-values converge.
- **Discount Factor (γ)** determines the importance of future rewards.
- **Epsilon-Greedy** balances exploration and exploitation.
- **Continuous state spaces** require discretization or function approximation.
- The **Q-Lattice** approach discretizes continuous spaces into manageable grids.
- This section provides the **foundation** for understanding DQN and other deep RL algorithms.
- The **exercise project** reinforces all key concepts through hands-on practice.
