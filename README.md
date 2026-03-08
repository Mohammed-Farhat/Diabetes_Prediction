# Diabetes Prediction Using Ensemble Machine Learning

This project develops a **machine learning pipeline for diabetes prediction** using patient health data. The workflow includes **data preprocessing, exploratory data analysis (EDA), feature engineering, class balancing, baseline model training, and ensemble learning techniques** to improve prediction performance.

The objective is to **compare traditional baseline models with ensemble methods** and evaluate how ensemble learning improves classification performance for diabetes detection.

---

# Project Overview

Diabetes is a widespread chronic disease that benefits from **early detection using predictive analytics**. In this project, we train and evaluate machine learning models to predict whether a patient has diabetes based on several medical and lifestyle attributes.

The notebook implements a **complete ML pipeline**, including:

- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Feature encoding and scaling
- Class imbalance handling using **SMOTE**
- Training **baseline machine learning models**
- Training **ensemble learning models**
- Performance comparison using classification metrics

---

# Dataset

File: `diabetes_prediction_dataset.csv`

Dataset statistics:

- **Rows:** 100,000
- **Target variable:** `diabetes`
- **Class distribution:** 91,500 non-diabetic, 8,500 diabetic

Features included in the dataset:

| Feature | Description |
| --- | --- |
| `gender` | Patient gender |
| `age` | Age in years |
| `hypertension` | Whether the patient has hypertension |
| `heart_disease` | Presence of heart disease |
| `smoking_history` | Smoking behavior |
| `bmi` | Body Mass Index |
| `HbA1c_level` | Average blood sugar level over time |
| `blood_glucose_level` | Current blood glucose measurement |
| `diabetes` | Target variable (0 = No, 1 = Yes) |

---

# Machine Learning Pipeline

The analysis is implemented in **`notebook.ipynb`** and follows the workflow below.

## 1. Data Loading

The dataset is loaded using **pandas** and basic dataset statistics are inspected.

---

## 2. Exploratory Data Analysis (EDA)

EDA is performed to understand the dataset structure and relationships between features.

This includes:

- Class distribution visualization
- Feature correlation analysis
- Distribution plots for numeric variables
- Feature impact analysis on diabetes occurrence

---

## 3. Data Cleaning and Preprocessing

The dataset undergoes several preprocessing steps:

- Removing duplicate rows
- Removing invalid category values: `Other` from `gender` and `No Info` from `smoking_history`
- One-hot encoding categorical variables
- Standardizing numeric features using **StandardScaler**

---

## 4. Train-Test Split

The dataset is divided into **training and testing sets** to evaluate model generalization.

Typical split:

- **80% training**
- **20% testing**

---

## 5. Handling Class Imbalance

The dataset is highly imbalanced.

To address this issue:

- **SMOTE (Synthetic Minority Oversampling Technique)** is applied **only on the training data**.

This improves model learning for the minority class (diabetic patients).

---

# Models Implemented

## Baseline Model

- Logistic Regression

This model serves as a **baseline for comparison** with more complex ensemble models.

---

## Ensemble Learning Models

### Random Forest

A bagging-based ensemble method that builds multiple decision trees and aggregates their predictions.

### XGBoost

A gradient boosting algorithm known for strong performance on tabular datasets.

### Soft Voting Classifier

A voting ensemble that combines predictions from multiple models by averaging their predicted probabilities.

---

# Model Evaluation

Models are evaluated using several classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC Score

These metrics allow a comprehensive comparison between baseline and ensemble models.

---

# Repository Structure

```text
.
|-- diabetes_prediction_dataset.csv
|-- notebook.ipynb
|-- requirements.txt
`-- README.md
```

## How To Run

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/diabetes-ensemble-prediction.git
```

1. **Navigate to the project folder**

```bash
cd diabetes-ensemble-prediction
```

1. **Install the dependencies**

```bash
pip install -r requirements.txt
```

1. **Start Jupyter Notebook**

```bash
jupyter notebook
```

1. **Open and run `notebook.ipynb`**
