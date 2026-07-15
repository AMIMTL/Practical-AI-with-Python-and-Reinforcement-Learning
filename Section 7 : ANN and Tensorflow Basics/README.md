# Section 7: Artificial Neural Network and TensorFlow Basics

**Course:** Practical AI with Python and Reinforcement Learning  
**Section:** 7 - Artificial Neural Network and TensorFlow Basics  
**Status:** 🔄 In Progress (0/27 lectures completed)

---

## 📚 Section Overview
This comprehensive section introduces the fundamentals of **Artificial Neural Networks (ANNs)** and **TensorFlow/Keras**. It covers both theory (perceptrons, activation functions, backpropagation) and practical implementation (regression, classification, TensorBoard).

### Lecture Breakdown
| # | Lecture | Duration |
|---|---------|----------|
| 35 | Introduction to Artificial Neural Networks | 2min |
| 36 | Perceptron Model | 11min |
| 37 | Neural Networks | 7min |
| 38 | Activation Functions | 11min |
| 39 | Multi-Class Classification Considerations | 11min |
| 40 | Cost Functions and Gradient Descent | 18min |
| 41 | Backpropagation | 15min |
| 42 | TensorFlow vs. Keras Explained | 2min |
| 43 | Keras Syntax - Preparing the Data | 11min |
| 44 | Keras Syntax - Creating and Training the Model | 14min |
| 45 | Keras Syntax - Model Evaluation | 13min |
| 46 | Keras Regression - Exploratory Data Analysis | 19min |
| 47 | Keras Regression - EDA Continued | 13min |
| 48 | Keras Regression - Data Preprocessing and Model Creation | 9min |
| 49 | Keras Regression - Model Evaluation and Predictions | 11min |
| 50 | Keras Classification - EDA and Preprocessing | 8min |
| 51 | Keras Classification - Overfitting and Evaluation | 17min |
| 52 | Keras Classification - Overview of Project Options | 2min |
| 53 | Keras Project Notebook Exercise Overview | 8min |
| 54 | Keras Project Solution - Exploratory Data Analysis | 21min |
| 55 | Keras Project Solutions - Missing Data - Part One | 15min |
| 56 | Keras Project Solutions - Dealing with Missing Data - Part Two | 12min |
| 57 | Keras Project Solutions - Categorical Data | 17min |
| 58 | Keras Project Solutions - Data Preprocessing | 4min |
| 59 | Keras Project Solutions - Creating and Training the Model | 4min |
| 60 | Keras Project Solutions - Model Evaluation | 10min |
| 61 | Tensorboard | 18min |

**Total Time:** 5hr 1min (All lectures)

---

## 🎯 Key Learning Points
- [ ] Perceptron model and its limitations
- [ ] Multi-layer neural networks
- [ ] Activation functions (ReLU, Sigmoid, Tanh, Softmax)
- [ ] Multi-class classification with softmax
- [ ] Cost functions (MSE, Cross-Entropy)
- [ ] Gradient Descent optimization
- [ ] Backpropagation algorithm
- [ ] TensorFlow vs. Keras relationship
- [ ] Keras Sequential API
- [ ] Data preprocessing for neural networks
- [ ] Model compilation, training, and evaluation
- [ ] Regression with Keras
- [ ] Classification with Keras
- [ ] Overfitting detection and prevention
- [ ] TensorBoard for visualization

---

## 📝 Personal Notes
*Add your own notes, code snippets, or tips here:*

### Basic Keras Workflow
```python
import tensorflow as tf
from tensorflow import keras

# 1. Prepare data
X_train, X_test, y_train, y_test = train_test_split(X, y)

# 2. Build model
model = keras.Sequential([
    keras.layers.Dense(64, activation='relu'),
    keras.layers.Dense(1, activation='sigmoid')
])

# 3. Compile
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# 4. Train
model.fit(X_train, y_train, epochs=10, validation_data=(X_test, y_test))

# 5. Evaluate
test_loss, test_acc = model.evaluate(X_test, y_test)
```

---

## 🚀 Progress Tracker

| Lecture | Completed? |
|---------|------------|
| 35. Introduction to ANN | [ ] |
| 36. Perceptron Model | [ ] |
| 37. Neural Networks | [ ] |
| 38. Activation Functions | [ ] |
| 39. Multi-Class Classification | [ ] |
| 40. Cost Functions and GD | [ ] |
| 41. Backpropagation | [ ] |
| 42. TF vs. Keras | [ ] |
| 43. Keras - Preparing Data | [ ] |
| 44. Keras - Creating/Training | [ ] |
| 45. Keras - Model Evaluation | [ ] |
| 46. Keras Regression - EDA | [ ] |
| 47. Keras Regression - EDA Cont. | [ ] |
| 48. Keras Regression - Preprocessing | [ ] |
| 49. Keras Regression - Evaluation | [ ] |
| 50. Keras Classification - EDA | [ ] |
| 51. Keras Classification - Overfitting | [ ] |
| 52. Project Overview | [ ] |
| 53. Project Exercise Overview | [ ] |
| 54. Project Solution - EDA | [ ] |
| 55. Project Solution - Missing Data I | [ ] |
| 56. Project Solution - Missing Data II | [ ] |
| 57. Project Solution - Categorical Data | [ ] |
| 58. Project Solution - Preprocessing | [ ] |
| 59. Project Solution - Create/Train | [ ] |
| 60. Project Solution - Evaluation | [ ] |
| 61. Tensorboard | [ ] |

---

## 🔗 Resources
- [TensorFlow Documentation](https://www.tensorflow.org/)
- [Keras API Reference](https://keras.io/api/)
- [TensorBoard Guide](https://www.tensorflow.org/tensorboard)

---

## 💡 Tips for This Section
- **Theory lectures (35-41):** Focus on understanding *why* neural networks work, not memorizing formulas.
- **Keras syntax (43-45):** These are your foundation - master the workflow!
- **Regression vs. Classification:** Notice the differences in:
  - Output layer activation
  - Loss function
  - Evaluation metrics
- **TensorBoard:** It's a powerful tool for monitoring training - set it up early.
- **The project (53-60):** This is where it all comes together - don't skip it!
