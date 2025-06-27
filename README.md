# 🔍 Exploring Trust in AI Using Stack Overflow Developer Survey Data

## 📘 Overview
This project explores what influences developers' **trust in AI** using data from the **2024 Stack Overflow Developer Survey**. With the **2025 survey currently underway**, I wanted to understand how developer sentiment toward AI is evolving—and whether we can **predict trust in AI** based on behavioral and demographic features.

---

## 🧠 Goal
To build a machine learning model that predicts whether a developer **trusts AI**, and identify the **most important factors** driving that trust.

---

## ⚙️ Process Summary

### 1. Data Source
- **Stack Overflow Developer Survey 2024**  
- Cleaned to retain relevant columns and handle missing/unknown values.

### 2. Target Variable
- **AITrust**: Binary classification  
  - `1`: Trust AI (somewhat or highly)
  - `0`: Do not trust AI

### 3. Features Considered
- Ordinal: `AISent` (personal sentiment toward AI)
- One-Hot Encoded: `Age`, `DevType`, `RemoteWork`, `AIThreat`, `EdLevel`
- Numeric: `YearsCodePro`

---

## 🧼 Data Cleaning & Feature Engineering
- Removed redundant or highly correlated features (e.g. `AIAcc`)
- Encoded categorical variables using **OrdinalEncoder** and **OneHotEncoder**
- Used `ColumnTransformer` to cleanly manage different types of data

---

## 🧪 Models Tried
### 🔹 Logistic Regression
- Served as a baseline model  
- Simple, interpretable—but underperformed

### 🔹 Random Forest Classifier ✅
- Delivered better performance and more meaningful feature importance
- Final model performance:
  - **Accuracy**: `0.65`
  - **Precision**: `0.63`
  - **Recall**: `0.41`
  - **F1 Score**: `0.50`
  - **ROC AUC**: `0.62`

---

## 📊 Top 3 Features (Feature Importances)

| Rank | Feature          | Meaning                    |
|------|------------------|----------------------------|
| 1    | Years Coding Pro | Developer experience       |
| 2    | AI Sentiment     | Personal sentiment on AI   |
| 3    | Developer Type   | Role/type of developer     |

These findings suggest that **personal attitudes**, **career path**, and **experience** all play roles in shaping how much developers trust AI.

---

## 📈 Visualizations
A Power BI bar chart was created to show the **distribution of AITrust in 2024**, revealing that:

> 🔍 **43% of developers** say they either *"somewhat trust"* or *"highly trust"* AI.

This insight helped validate the balance of our binary target and supported deeper exploration.

---

## 💡 Lessons Learned
- Modeling human behavior and trust is **complex**
- Data imbalance, encoding schemes, and feature correlation have a huge impact on performance
- Feature importance from tree-based models can be powerful in interpreting results

---

## 📁 Repository Contents

```bash
├── data/
│   └── cleaned_survey_data_2024.csv
├── notebooks/
│   └── modeling_ai_trust.ipynb
├── visuals/
│   └── ai_trust_feature_importance.png
├── README.md
└── requirements.txt
