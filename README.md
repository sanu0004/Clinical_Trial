# 🏥 Clinical Trial Survival Analysis

Survival analysis of the Veteran Lung Cancer clinical trial dataset using
Kaplan-Meier estimation, log-rank testing, and Cox regression models.

## 📌 Overview
This project studies patient survival in a randomized clinical trial comparing
a standard treatment against a test treatment. It estimates survival
probabilities, tests for differences between groups, and identifies which
patient factors influence risk of death.

## 📂 Project Structure
├── Clinical-Trial.ipynb   # Main analysis notebook
├── veteran.csv            # Dataset (274 records)
└── README.md

## 📊 Dataset
Columns: ID, TIME (survival time in days), Y (event: 1 = death, 0 = start/censored),
trt (standard / test), celltype, karno (Karnofsky performance score),
diagtime (months from diagnosis), age, priortherapy.

## 🔍 Analysis Performed
- Data inspection (head, info, value counts of treatment groups)
- Kaplan-Meier survival curves (overall and by treatment group)
- Median survival time per treatment group
- Log-rank test to compare standard vs test treatment (p ≈ 0.93, no significant difference)
- Cox Proportional Hazards model with categorical encoding (get_dummies)
- Reshaping data into start/stop format for a Cox Time-Varying model
- Data quality checks (NaN and infinite values)
- Coefficient plots and hazard ratio interpretation

## 🛠️ Tech Stack
Python · Pandas · NumPy · Matplotlib · Lifelines · Jupyter / Google Colab

## ▶️ How to Run
1. Clone the repo
2. Install dependencies:
   pip install pandas numpy matplotlib lifelines jupyter
3. Place veteran.csv in the project folder
4. Run the notebook:
   jupyter notebook Clinical-Trial.ipynb

## 📈 Key Findings
- No statistically significant survival difference between standard and test treatments.
- Cox model reveals which covariates (e.g., Karnofsky score, cell type) affect hazard.

## 🚀 Future Scope
- Check the proportional hazards assumption
- Add true time-varying covariates
- Try Random Survival Forests or other ML survival models
- Build an interactive dashboard
