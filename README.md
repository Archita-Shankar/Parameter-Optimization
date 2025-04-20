# 📈 SVM Parameter Tuning on Letter Recognition Dataset

## 📝 Summary

This project focuses on using a **Support Vector Machine (SVM)** with an **RBF kernel** to classify letters.  
The goal: **optimize the regularization parameter `C`** to maximize test accuracy across multiple data splits.

---

## 🔧 Approach

### 1. Data Preparation
- Encoded the `letter` column numerically using `LabelEncoder`.
- Extracted features (`X`) and target labels (`y`) from the dataset.

### 2. Training & Tuning
- Performed 10 separate train-test splits with:
  - 70% training and 30% testing data
  - `random_state` values from 0 to 9
- For each split:
  - Tested 100 `C` values linearly spaced between 0.1 and 10
  - Trained an SVM with RBF kernel for each value
  - Recorded test accuracy and identified the best `C` value per split

---

## 📊 Results

### 🔍 Top Accuracy & Corresponding Parameters

| Split | Accuracy | Best `C` Value |
|-------|----------|----------------|
| 0     | 0.9673   | `C=10.0`       |
| 1     | 0.9623   | `C=9.9`        |
| 2     | 0.9632   | `C=10.0`       |
| 3     | 0.9617   | `C=10.0`       |
| 4     | 0.9592   | `C=10.0`       |
| 5     | 0.9610   | `C=9.7`        |
| 6     | 0.9582   | `C=10.0`       |
| 7     | 0.9643   | `C=8.5`        |
| 8     | 0.9652   | `C=9.7`        |
| 9     | 0.9635   | `C=9.9`        |

> All models used: `kernel='rbf', gamma='scale'`

---

## 📈 Accuracy vs. `C` (Split 0)

The following plot shows how test accuracy changes with different `C` values for the **best-performing split (Split 0)**:

![Convergence Graph](https://github.com/user-attachments/assets/df0080fc-978a-4734-b169-2a2cdee0e251)

> *This visualization highlights how accuracy improves with increasing regularization and helps identify the most effective `C` value.*
