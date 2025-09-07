# 📂 CORE_ML Projects

This repository contains my learning journey in **Machine Learning (ML)**, with projects and implementations organized into two categories: **Monthly** and **Weekly**.

---

## 📁 Folder Structure

### 🔹 Monthly
Focused on implementing ML algorithms using **scikit-learn** and working on small projects.

- **MiniProject1.ipynb**
  - Implemented **Linear Regression** (with and without Polynomial Features) using `scikit-learn`.
  - Used datasets from `sklearn.datasets`.
  - Evaluated model performance using:
    - **R² Score**
    - **Mean Squared Error (MSE)**
  - Applied **StandardScaler** and **MinMaxScaler** to compare scaling effects.

- **MiniProject2.ipynb**
  - Worked with the **Iris dataset**.
  - Implemented and compared 3 models:
    - Logistic Regression
    - K-Nearest Neighbors Classifier (KNN)
    - Multinomial Naive Bayes
  - Generated **Classification Reports** to evaluate precision, recall, F1-score.

---

### 🔹 Weekly
Focused on **learning algorithms from scratch** and practicing with datasets.

- **Linear_Regression_Scratch**
  - Linear Regression implemented **from scratch** (without libraries like sklearn).

- **scratch_logistic_regression**
  - Logistic Regression implemented **from scratch**.

- **titanic.ipynb**
  - Used Titanic dataset to apply:
    - Logistic Regression
    - K-Nearest Neighbors Classifier
    - Decision Tree Classifier
    - Naive Bayes Classifier
  - Evaluated models using **Classification Reports**.

- **Spam_Classifier.ipynb**
  - (Planned / Ongoing) – Spam classifier implementation using ML algorithms.

- **data/**
  - Contains datasets used for practice and model training.

- **mini-project.ipynb**
  - Explored ensemble learning using Random Forest Classifiers and Gradient Boosting applying it on credit card transaction fraud dataset
  - also got introduced to SMOTE (Synthetic Minority Oversampling Technique)
  - The dataset contains of 30 features and 1 target column depicting the fraud class of transactions (1 referring to fraud and 0 referring to no fraud)
    - No null values in any features
    - Was imbalanced with more non fraud cases a lot more than fraud cases
    - Handled it with SMOTE by equalizing the non-fraud class with the fraud class
  - Findings:
    - Used SMOTE to increase the class 1
    - Implemented with and without smote
    - After SMOTE both the classifiers gave bad results as compared to before SMOTE
    - Modified the Random Forest with `n_estimators` (reduced it) and `max_depth` (changed it to 75 from `None`) in result it gave almost same result
    - Modified the Gradient Boosting with `n_estimators` (reduced it), `max_depth` (changed it to 75 from `None`) and `max_fetures` (from `None` to `'sqrt'`), in result it gave better result


---

## ⚡ Skills Practiced
- Implementing ML algorithms from scratch.
- Using `scikit-learn` for standard models.
- Data preprocessing with scaling (StandardScaler, MinMaxScaler).
- Model evaluation: R² Score, MSE, Classification Reports.
- Hands-on with datasets: Iris, Titanic, and synthetic data from sklearn.

---

## 🚀 Next Steps
- Add more ML models (SVM, Random Forest, Gradient Boosting).
- Explore hyperparameter tuning.
- Work on real-world datasets for better generalization.
