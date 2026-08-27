# Section 11: Classical Q Learning

**Course:** Practical AI with Python and Reinforcement Learning  
**Section:** 11 - Classical Q Learning  
**Status:** ✅ Completed  
**Completed on:** Summer 2026

---

## 📚 Section Overview
This section introduces **Classical Q-Learning**, a foundational reinforcement learning algorithm. You'll learn the theory behind Q-Learning, implement it from scratch, and explore both discrete and continuous state spaces.

### Lecture Breakdown
| # | Lecture | Status |
|---|---------|--------|
| 90 | Introduction to Classical Q-Learning Overview | ✅ |
| 91 | History of Q-Learning | ✅ |
| 92 | Q-Learning Theory - Part One - Stable Inflation | ✅ |
| 93 | Q-Learning Theory - Part Two - Q Lapped Equation | ✅ |
| 94 | Q-Learning Theory - Part Three - Q-Upside Evolution | ✅ |
| 95 | Q-Learning Theory - Part Four - Programmatic Q Updates | ✅ |
| 96 | Q-Learning Implementation - Part One - Environmental Setup | ✅ |
| 97 | Q-Learning Implementation - Part Two - Table and Hyperparameters | ✅ |
| 98 | Q-Learning Implementation - Part Three - Update Functions | ✅ |
| 99 | Q-Learning Implementation - Part Four - Agent Learning | ✅ |
| 100 | Q-Learning Implementation - Part Five - Visualization and Utilization | ✅ |
| 101 | Continuous Q-Learning Theory - Part One - Environment Setup | ✅ |
| 102 | Continuous Q-Learning Theory - Part Two - Q-Lattice Shape | ✅ |
| 103 | Continuous Q-Learning Theory - Part Three - Deactivation Theory | ✅ |
| 104 | Continuous Q-Learning Theory - Part Four - Deactivation Implementation | ✅ |
| 105 | Continuous Q-Learning Theory - Part Five - Function and Hyperparameters | ✅ |
| 106 | Continuous Q-Learning Theory - Part Six - Training and Usage | ✅ |
| 107 | Q-Learning Exercise Project | ✅ |
| 108 | Q-Learning Exercise Project - Solutions | ✅ |

**Total Lectures:** 19 (All Completed ✅)

---

## 🎯 Key Learning Points (All Mastered ✅)

### Q-Learning Theory
- ✅ History and evolution of Q-Learning
- ✅ The Q-Learning equation and Bellman equation
- ✅ Q-Value updates and temporal difference learning
- ✅ Programmatic Q updates
- ✅ Stable inflation and Q-Value convergence

### Q-Learning Implementation
- ✅ Environment setup for Q-Learning
- ✅ Creating and initializing Q-Tables
- ✅ Setting hyperparameters (learning rate, discount factor, epsilon)
- ✅ Update functions for Q-Values
- ✅ Agent learning loop
- ✅ Visualization and utilization of learned policies

### Continuous Q-Learning
- ✅ Environment setup for continuous state spaces
- ✅ Q-Lattice shape and discretization
- ✅ Deactivation theory and implementation
- ✅ Function approximation and hyperparameters
- ✅ Training and usage for continuous environments

### Project Work
- ✅ Q-Learning Exercise Project
- ✅ Project solutions completed

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
