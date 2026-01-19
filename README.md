# Mini Project 1 — Regression Challenge (COMP 9130)

This project builds a complete regression workflow to predict **medical insurance charges** (`charges`) using demographic and health-related features.  
The work includes exploratory data analysis, preprocessing, feature engineering, model training, evaluation, and result interpretation.

---

## 📌 Problem Description & Motivation
Medical insurance costs vary significantly across individuals.  
The goal of this project is to build regression models that can predict **insurance charges** based on factors such as age, BMI, smoking status, and region.

**Target Variable:** `charges` (continuous)

---

## 📊 Dataset Description
**Dataset:** Insurance Costs dataset (`insurance.csv`)  
**Rows:** 1338  
**Features:** 6 input features + 1 target column

### Columns
- `age` (numeric)
- `sex` (categorical)
- `bmi` (numeric)
- `children` (numeric)
- `smoker` (categorical)
- `region` (categorical)
- `charges` (target)

---

## 🗂️ Repository Structure
```text
mini-project-1/
├── README.md
├── requirements.txt
├── data/
│   └── insurance.csv
├── notebooks/
│   ├── 01_exploration.ipynb
│   └── 02_modeling.ipynb
└── src/
    └── (optional scripts)
