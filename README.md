# 🌸 Iris Flower Species Classification

A machine learning project that automates the identification of iris flower species (setosa, versicolor, and virginica) using physical measurements of their sepals and petals.

---

## 📋 Problem Definition
Biologists need a simple and automated way to correctly identify iris flower species without relying on manual guesswork. While some iris flowers look very different, others look almost identical. This project leverages machine learning to look at four basic measurements—the length and width of the petals and sepals—to instantly predict the correct species.

---

##  Dataset
The project uses the classic Iris Dataset built into scikit-learn.
* Features (4):
  1. Sepal length (cm)
  2. Sepal width (cm)
  3. Petal length (cm)
  4. Petal width (cm)
* Target Classes (3):
  * 0: setosa
  * 1: versicolor
  * 2: virginica

---

## Project Workflow

1. Exploratory Data Analysis (EDA): Visualizing pairwise relationships and feature distributions using seaborn pairplots.
2. Data Preprocessing: Splitting the data into training and testing sets ($80\%$ train, $20\%$ test).
3. Pipeline Construction: Building a robust scikit-learn Pipeline that combines:
   * StandardScaler for feature scaling.
   * DecisionTreeClassifier (max_depth=3, random_state=42) for classification.
4. Model Evaluation: Assessing performance using Accuracy, Classification Report, and Confusion Matrix.
5. Model Persistence: Saving the trained pipeline using joblib for future deployment.

---


## 📈 Results & Detailed Performance Analysis

The model was evaluated on a held-out test set of 30 samples (representing $20\%$ of the total dataset).

---

### 🎯 Overall Accuracy Score

> Model Accuracy: 96.67% 
> * Correct Predictions: 29 out of 30 samples
> * Errors: 1 misclassification

---

### 📋 Classification Report Breakdown

| Class Index | Species Name | Precision | Recall | F1-Score | Support |
| :---: | :--- | :---: | :---: | :---: | :---: |
| 0 | `setosa` | 1.00 | 1.00 | 1.00 | 11 |
| 1 | `versicolor` | 1.00 | 0.92 | 0.96 | 13 |
| 2 | `virginica` | 0.86 | 1.00 | 0.92 | 6 |
| Macro Avg | — | 0.95 | 0.97 | 0.96 | 30 |
| Weighted Avg | — | 0.97 | 0.97 | 0.97 | 30 |

---

### 🔍 Key Metrics Insights
* `setosa`: Achieved a flawless 1.00 across precision, recall, and F1-score, confirming it is mathematically distinct and easily separated from the other species.
* `versicolor`: Maintained a perfect precision of `1.00`, but dipped slightly in recall (`0.92`) due to one sample being misidentified.
* `virginica`: Achieved full recall (`1.00`), successfully catching all true `virginica` flowers, though its precision was `0.86` because an extra sample was mistakenly predicted as belonging to this class.
