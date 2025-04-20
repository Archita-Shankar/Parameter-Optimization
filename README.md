

# 📈 Parameter Optimization for SVM on Letter Recognition Dataset

## 📝 Overview

This project explores **Support Vector Machine (SVM)** classification using `scikit-learn` on a dataset where the target variable is `letter`.  
The primary objective is to **tune the regularization parameter `C`** to maximize **test accuracy** across multiple train-test splits.

---

## 🔧 Methodology

### 1. Data Preprocessing
- The target variable `letter` is **encoded numerically** using `LabelEncoder`.
- Feature matrix `X` and label vector `y` are extracted from the dataset.

### 2. Model Training & Hyperparameter Tuning
- The experiment is repeated over **10 different train-test splits**, with:
  - `test_size = 0.3`
  - `random_state` ranging from `0` to `9`

- For each split:
  - 100 values of the regularization parameter `C` are tested, **linearly spaced between `0.1` and `10`**.
  - An SVM model with an **RBF kernel** is trained for each value of `C`.
  - The corresponding **test accuracy** is recorded.
  - The **best value of `C`** and its **associated accuracy** are saved.

---

## 📊 Results

### 🏆 Best Parameters and Accuracies

| Split | Accuracy | Best Parameters |
|-------|----------|-----------------|
| 0     | 0.9673   | `{'C': 10.0, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 1     | 0.9623   | `{'C': 9.9, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 2     | 0.9632   | `{'C': 10.0, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 3     | 0.9617   | `{'C': 10.0, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 4     | 0.9592   | `{'C': 10.0, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 5     | 0.9610   | `{'C': 9.7, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 6     | 0.9582   | `{'C': 10.0, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 7     | 0.9643   | `{'C': 8.5, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 8     | 0.9652   | `{'C': 9.7, 'kernel': 'rbf', 'gamma': 'scale'}` |
| 9     | 0.9635   | `{'C': 9.9, 'kernel': 'rbf', 'gamma': 'scale'}` |

---

## 📈 Convergence Graph

- A convergence graph was generated for the **best-performing split** (Split 0, Accuracy: **0.9673**).
- The plot shows **test accuracy vs. `C` value** across 100 iterations.

> ![435424403-3b77f833-97db-4417-a75b-e313868da1c6](https://github.com/user-attachments/assets/df0080fc-978a-4734-b169-2a2cdee0e251)
>  *This visual helps understand how accuracy evolves with varying regularization strength and guides optimal hyperparameter selection.*
