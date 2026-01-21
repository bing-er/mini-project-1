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
├── notebooks/
│   ├── 01_exploration.ipynb
│   └── 02_modeling.ipynb
├── figs/
│   ├── residual_plot.png
│   └── pred_vs_actual.png
├── docs/
│   ├── 01_exploration.pdf
│   ├── 01_exploration.html
│   ├── 02_modeling.ipynb
│   ├── 02_modeling.ipynb
│   └── MP1_Yu_Cheng.pdf
├── data/
│   └── insurance.csv
├── requirements.txt
└── LICENSE
```

---

## ⚙️ Setup Instructions (Run Locally)
1)Clone the repo

```text
git clone https://github.com/bing-er/mini-project-1.git
cd mini-project-1
```

2)Create and activate a virtual environment

```text
 python3 -m venv .venv
source .venv/bin/activate
```

3)Install required dependencies

```text
python3 -m venv .venv
source .venv/bin/activate
```

4)Launch Jupyter Notebook

```text
jupyter notebook
```

---

## 🧪 Modeling Approach
### ✅ Preprocessing

- Train/test split: 80/20
- Numeric features: median imputation + standard scaling
- Categorical features: imputation + one-hot encoding

### ✅ Feature Engineering

- To explore whether the skewed distribution of charges impacts performance, we tested a log transformation of the target:
- log1p(charges) during training
- expm1(prediction) to convert predictions back to dollars

---

## 🤖 Models Trained

- At least three regression models were trained and evaluated:
- Linear Regression (baseline)
- Ridge Regression (L2 regularization)
- Lasso Regression (L1 regularization)
- Ridge Regression (log target) (feature-engineered target transformation)

---

## 📈 Results Summary
Evaluation metrics reported for each model:
- **MAE**
- **RMSE**
- **R²**

### Model comparison (test set)
| Model | MAE | RMSE | R² |
|------|------:|------:|------:|
| Linear Regression | 4181.19 | 5796.28 | 0.7836 |
| Lasso Regression | 4181.19 | 5796.28 | 0.7836 |
| Ridge Regression | 4186.91 | 5798.30 | 0.7834 |
| Ridge (log target) | 3881.88 | 7780.62 | 0.6101 |

✅ Based on **RMSE (lower is better)**, the best-performing model was **Linear Regression** (very close results with Ridge and Lasso).

**Visualizations included:**
- Model comparison table/chart
- Predicted vs Actual plot (best model)
- Residual plot (best model)

---

## 🔍 Key Observations

- Smoking status has the strongest relationship with higher insurance charges.
- Age and BMI also contribute meaningfully to prediction performance.
- The largest prediction errors tend to occur for extreme high-charge cases.
- The log-target Ridge model reduced MAE slightly, but increased RMSE overall, suggesting worse performance for large-error cases.

---

## 👥 Team Contributions

- **Nicky Cheng:** Completed 01_exploration.ipynb (EDA, distributions, correlation checks, and initial written analysis).
- **Binger Yu:** Completed 02_modeling.ipynb (preprocessing pipeline, feature engineering, training and evaluation of multiple regression models, results plots), finalized requirements.txt and README.md, corrected issues in 01_exploration.ipynb, and prepared the Overleaf LaTeX report framework (template, formatting, and section titles).

---

## 📌 Notes

- All notebooks are designed to run from top to bottom without errors.
- Dataset is stored under the data/ folder for reproducibility.




