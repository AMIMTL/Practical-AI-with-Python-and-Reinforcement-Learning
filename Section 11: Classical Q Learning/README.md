# Section 11: Classical Q Learning

**Course:** Practical AI with Python and Reinforcement Learning  
**Section:** 11 - Classical Q Learning  
**Status:** 🔄 In Progress (4/19 lectures completed)

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
| 94 | Q-Learning Theory - Part Three - Q-Upside Equation | 5min | 🔄 |
| 95 | Q-Learning Theory - Part Four - Hypercontractile Q Updates | 5min | 🔄 |
| 96 | Q-Learning Implementation - Part One - Environment Setup | 5min | 🔄 |
| 97 | Q-Learning Implementation - Part Two - Stable and Hyperparameters | 5min | 🔄 |
| 98 | Q-Learning Implementation - Part Three - Update Function | 5min | 🔄 |
| 99 | Q-Learning Implementation - Part Four - Agent Learning | 5min | 🔄 |
| 100 | Q-Learning Implementation - Part Five - Visualization and Utilization | 5min | 🔄 |
| 101 | Continuous Q-Learning Theory - Part One - Environment Setup | 5min | 🔄 |
| 102 | Continuous Q-Learning Theory - Part Two - Q-Update Shape | 5min | 🔄 |
| 103 | Continuous Q-Learning Theory - Part Three - Decentralization Theory | 5min | 🔄 |
| 104 | Continuous Q-Learning Theory - Part Four - Decentralization | 5min | 🔄 |
| 105 | Continuous Q-Learning Theory - Part Five - Function and Hyperparameters | 5min | 🔄 |
| 106 | Continuous Q-Learning Theory - Part Six - Training and Update | 5min | 🔄 |
| 107 | Q-Learning Exercise Project | 5min | 🔄 |
| 108 | Q-Learning Exercise Project - Solutions | 5min | 🔄 |

**Total Time:** 2hr 50min (Completed: ~18min | Remaining: ~2hr 32min)

---

## 🎯 Key Learning Points

### Completed ✅
- ✅ Introduction and course overview
- ✅ History and evolution of Q-Learning
- ✅ Stable Inflation concept
- ✅ Q-Large Equation

### In Progress 🔄
- [ ] Q-Upside Equation
- [ ] Hypercontractile Q Updates
- [ ] Environment Setup
- [ ] Stable and Hyperparameters
- [ ] Update Function
- [ ] Agent Learning
- [ ] Visualization and Utilization
- [ ] Continuous Q-Learning Theory (Parts 1-6)
- [ ] Exercise Project & Solutions

---

## 📝 Personal Notes
*Add your own notes, code snippets, or tips here:*

### Q-Learning Key Concepts (So Far)
```python
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
```

### Epsilon-Greedy Exploration (Coming Up)
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

## 🚀 Progress Tracker

| Lecture | Completed? |
|---------|------------|
| 90. Overview | ✅ |
| 91. History | ✅ |
| 92. Stable Inflation | ✅ |
| 93. Q-Large Equation | ✅ |
| 94. Q-Upside Equation | [ ] |
| 95. Hypercontractile Q Updates | [ ] |
| 96. Environment Setup | [ ] |
| 97. Stable and Hyperparameters | [ ] |
| 98. Update Function | [ ] |
| 99. Agent Learning | [ ] |
| 100. Visualization and Utilization | [ ] |
| 101. Continuous - Environment Setup | [ ] |
| 102. Continuous - Q-Update Shape | [ ] |
| 103. Continuous - Decentralization Theory | [ ] |
| 104. Continuous - Decentralization | [ ] |
| 105. Continuous - Function and Hyperparameters | [ ] |
| 106. Continuous - Training and Update | [ ] |
| 107. Exercise Project | [ ] |
| 108. Exercise Project - Solutions | [ ] |

---

## 🔗 Resources
- [Q-Learning Wikipedia](https://en.wikipedia.org/wiki/Q-learning)
- [Bellman Equation](https://en.wikipedia.org/wiki/Bellman_equation)
- [Reinforcement Learning Course by Sutton & Barto](http://incompleteideas.net/book/the-book-2nd.html)

---

## 💡 Tips for This Section
- **Theory lectures (90-95):** Focus on understanding the Bellman equation - it's the foundation of Q-Learning.
- **Implementation (96-100):** Pay attention to the Q-Table structure and update function.
- **Continuous Q-Learning (101-106):** Understand how to discretize continuous state spaces.
- **Exercise Project (107-108):** Don't skip this - it solidifies all key concepts.
