# 🎓 Student Performance Prediction — ML Research Project

> **Lumiere Research Scholar Program — Fall Cohort 2024**  
> *Researcher: Phan Thao Van*

## 📋 Overview

This repository contains the full machine learning pipeline for predicting high school student performance in mathematics. Using a rich demographic and behavioural dataset, this project investigates which factors most strongly influence academic outcomes and develops interpretable predictive models.

**Research Questions:**
1. What are the key factors that influence student performance in mathematics, and how do they differ across subjects?
2. Are there significant academic achievement gaps between students from different socioeconomic backgrounds?
3. Can a machine learning model accurately predict student performance from demographic factors?

---

## 🗂️ Repository Structure

```
student-performance-ml/
├── notebooks/
│   ├── 01_EDA_Student_Performance.ipynb        # Exploratory Data Analysis
│   ├── 02_Model_Development_Student_Performance.ipynb  # Model training & evaluation
│   └── 03_SHAP_Analysis_Student_Performance.ipynb      # Explainability with SHAP
├── data/
│   └── README.md                               # Data sourcing instructions
├── docs/
│   └── Research_Proposal.docx                 # Full research proposal
├── scripts/
│   └── requirements.txt                       # Python dependencies
├── .gitignore
└── README.md
```

---

## 🔬 Methodology

### 1. Exploratory Data Analysis (`01_EDA`)
- Dataset overview: student demographics, family background, social habits, and grades
- Descriptive statistics and data quality checks
- Distribution analysis of `final_grade` by school, alcohol consumption, and other factors
- Correlation heatmaps for numerical features

### 2. Model Development (`02_Model_Development`)
- **Preprocessing:** Binary encoding (sex, school), ordinal encoding (travel time, study time), one-hot encoding (parent education/job, school choice reason)
- **Feature selection:** `grade_1`, `grade_2`, `absences`, `family_relationship`, `age`
- **Models trained:**
  - Linear Regression (baseline)
  - k-Nearest Neighbours
  - Decision Tree
  - Random Forest + GridSearchCV hyperparameter tuning
  - **XGBoost** + GridSearchCV hyperparameter tuning *(best performer)*
- **Evaluation:** RMSE, MAE, R²

### 3. SHAP Explainability (`03_SHAP_Analysis`)
- SHAP (SHapley Additive exPlanations) applied to the best XGBoost model
- Summary plots: feature importance ranking
- Bar plots: mean absolute SHAP values
- Waterfall plots: individual prediction explanations

---

## 📊 Dataset

This project uses the **UCI Student Performance Dataset** (Cortez & Silva, 2008).

> ⚠️ **Data not included in this repository.** See [`data/README.md`](data/README.md) for instructions on downloading and placing the dataset.

**Key features include:**
- Demographics: age, sex, address type
- Family: parents' education & jobs, family size, relationship quality
- Social: free time, going out frequency, alcohol consumption (weekday/weekend)
- Academic: study time, past failures, absences, previous grades (G1, G2), final grade (G3)

---

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Jupyter Notebook or JupyterLab

### Installation

```bash
git clone https://github.com/<your-username>/student-performance-ml.git
cd student-performance-ml
pip install -r scripts/requirements.txt
```

### Running the Notebooks

Run in order:
```bash
jupyter notebook notebooks/01_EDA_Student_Performance.ipynb
jupyter notebook notebooks/02_Model_Development_Student_Performance.ipynb
jupyter notebook notebooks/03_SHAP_Analysis_Student_Performance.ipynb
```

> 📝 The notebooks were originally developed in Google Colab. The data loading cell uses a `.zip` file at `/content/archive.zip` — update the path to your local dataset location before running.

---

## 📦 Dependencies

See [`scripts/requirements.txt`](scripts/requirements.txt). Key packages:

| Package | Purpose |
|---|---|
| `pandas`, `numpy` | Data manipulation |
| `matplotlib`, `seaborn` | Visualisation |
| `scikit-learn` | ML models, preprocessing, evaluation |
| `xgboost` | Gradient boosting model |
| `shap` | Model explainability |

---

## 📝 Citation

If you use this work, please cite:

```
Phan, T.V. (2024). Student Performance Prediction using Machine Learning.
Lumiere Research Scholar Program. GitHub: https://github.com/<your-username>/student-performance-ml
```

**Original dataset:**
```
Cortez, P., & Silva, A. (2008). Using data mining to predict secondary school student performance.
In Proceedings of 5th Annual Future Business Technology Conference (pp. 5-12).
```

---

## 📄 License

This project is for academic research purposes. See the research proposal in `docs/` for full context.

---

*Built as part of the Lumiere Research Scholar Program, Fall 2024.*
