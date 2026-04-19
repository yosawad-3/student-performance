# 📌 Student Exam Performance Prediction

## 📖 Overview

This project focuses on analyzing and predicting student academic performance using a dataset that includes demographic, socioeconomic, and behavioral features.

The goal is to build a machine learning model that can:

* Predict a student’s **overall performance (Average Score)**
* Understand which factors most influence academic success

---

## 🎯 Objective

Develop a regression model to:

* Predict **Average Score** of students
* Analyze the impact of features like:

  * Study Time
  * Absences
  * Lunch Type
  * Parental Education Level
  * Gender

---

## 📊 Dataset Description

### 🔹 Features:

* **Gender** → Male / Female
* **Parental Education Level** → Education level of parents
* **Lunch Type** → Standard / Free or Reduced
* **Study Time** → Time spent studying
* **Absences** → Number of missed days
* **Math Score**
* **Reading Score**
* **Writing Score**

---

## 🎯 Target Variable

```text
Average Score = (Math Score + Reading Score + Writing Score) / 3
```

---

## 🧹 Data Preprocessing

### ✔ Handling Missing Values

* **Parental Education Level** → Filled using **group-based mode**
* **Lunch Type** → Filled using **group-based mode**
* **Study Time** → Filled using **group-based median**
* Used **binning (qcut)** on score columns to improve grouping:

  * Math_bin
  * Reading_bin
  * Writing_bin

---

### ✔ Feature Engineering

* Created new column:

```python
Average Score
```

---

### ✔ Removed Features (for modeling)

* `Test Preparation Course` → Constant column (no variance)
* `Math_bin`, `Reading_bin`, `Writing_bin` → Used only for preprocessing

---

### ✔ Encoding

Applied **One-Hot Encoding** on:

* Gender
* Parental Education Level
* Lunch Type

---

## ⚠️ Data Leakage Handling

* Dropped:

```text
Math Score, Reading Score, Writing Score
```

from model features to avoid leakage (since they directly form the target).

---

## 🤖 Model Used

### 🌳 Random Forest Regressor

* Handles non-linear relationships
* Robust to noise
* Works well on tabular data

---

## 📈 Model Evaluation

| Metric   | Value |
| -------- | ----- |
| Train R² | 0.97  |
| Test R²  | 0.86  |
| MAE      | 5.38  |

---

## 🧠 Insights

* Study Time positively impacts performance
* Absences negatively affect scores
* Socioeconomic factors (Lunch Type, Parental Education) influence outcomes
* Model captures most of the variance in student performance

---

## 🚀 Future Improvements

* Try **XGBoost / LightGBM** for better performance
* Perform **hyperparameter tuning**
* Use **feature importance analysis**
* Explore **multi-output regression** (predict each subject separately)

---

## 💻 Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Seaborn / Matplotlib

---

## 👤 Contributor

**Youssef Mohamed Awad**
GitHub: https://github.com/yosawad-3

---

## 📌 Conclusion

This project demonstrates how machine learning can be applied to educational data to:

* Predict student performance
* Identify key influencing factors
* Support data-driven decision-making in education
