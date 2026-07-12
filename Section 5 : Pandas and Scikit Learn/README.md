# Section 6: Pandas and Scikit-Learn Crash Course

**Course:** Practical AI with Python and Reinforcement Learning  
**Section:** 6 - Pandas and Scikit-Learn Crash Course  
**Status:** ✅ Completed  
**Completed on:** [Add Date]

---

## 📚 Section Overview
This section covers two essential Python libraries for data science and machine learning:
- **Pandas** - For data manipulation, cleaning, and analysis
- **Scikit-Learn** - For machine learning model building and evaluation

### Lecture Breakdown
| # | Lecture | Duration | Status |
|---|---------|----------|--------|
| 26 | Pandas and Scikit-Learn Overview | 1min | ✅ |
| 27 | Pandas - Series Part One | 9min | ✅ |
| 28 | Pandas - Series Part Two | 11min | ✅ |
| 29 | Pandas - DataFrames - Part One | 19min | ✅ |
| 30 | Pandas - DataFrames - Part Two | 8min | ✅ |
| 31 | Pandas - DataFrames - Part Three | 14min | ✅ |
| 32 | Pandas - DataFrames - Part Four | 15min | ✅ |
| 33 | Scikit-Learn - Using Train-Test-Split | 11min | ✅ |
| 34 | Scikit-Learn - Using Metrics | 15min | ✅ |

**Total Time:** 1hr 43min (All Completed ✅)

---

## 🎯 Key Learning Points (All Mastered ✅)

### Pandas
- ✅ Understanding Series (one-dimensional arrays)
- ✅ Creating and manipulating DataFrames
- ✅ Reading and writing data (CSV, Excel, etc.)
- ✅ Data selection and filtering (`loc`, `iloc`, boolean indexing)
- ✅ Handling missing data (`dropna()`, `fillna()`)
- ✅ Grouping and aggregating data (`groupby()`)
- ✅ Merging and joining DataFrames
- ✅ Applying functions to DataFrames (`apply()`, `map()`)

### Scikit-Learn
- ✅ Train-Test-Split for model evaluation
- ✅ Understanding data leakage prevention
- ✅ Common evaluation metrics (accuracy, precision, recall, F1-score)
- ✅ Setting random states for reproducibility

---

## 📝 Personal Notes
*Add your own notes, code snippets, or tips here:*

### Pandas Series Example
```python
import pandas as pd

# Creating a Series
s = pd.Series([1, 2, 3, 4, 5], index=['a', 'b', 'c', 'd', 'e'])
print(s)
print(s['b'])  # Access by index label
```

### Pandas DataFrame Example
```python
# Creating a DataFrame
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'Salary': [50000, 60000, 70000]
}
df = pd.DataFrame(data)
print(df.head())
print(df.describe())  # Summary statistics
```

### Scikit-Learn Train-Test-Split
```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

---

## 🚀 All Lectures Completed ✅

| Lecture | Status |
|---------|--------|
| 26. Overview | ✅ |
| 27. Series Part One | ✅ |
| 28. Series Part Two | ✅ |
| 29. DataFrames Part One | ✅ |
| 30. DataFrames Part Two | ✅ |
| 31. DataFrames Part Three | ✅ |
| 32. DataFrames Part Four | ✅ |
| 33. Train-Test-Split | ✅ |
| 34. Using Metrics | ✅ |

---

## 🔗 Resources
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Pandas Cheat Sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)
- [Scikit-Learn Documentation](https://scikit-learn.org/stable/)
- [Train-Test-Split Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)
- [Evaluation Metrics Guide](https://scikit-learn.org/stable/modules/model_evaluation.html)

---

## 💡 Key Takeaways from This Section
- **Pandas** is the "Excel in Python" - it will save you hours of data cleaning time.
- **DataFrames** are the most commonly used Pandas structure.
- Always set a `random_state` in `train_test_split` for reproducible results.
- Different metrics are appropriate for different problems - choose wisely!
