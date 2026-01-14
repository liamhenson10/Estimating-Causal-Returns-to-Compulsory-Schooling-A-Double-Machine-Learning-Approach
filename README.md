# Estimating-Causal-Returns-to-Compulsory-Schooling-A-Double-Machine-Learning-Approach
This project estimates the causal effect of compulsory schooling laws on earning in the U.K. using double machine learning

# Estimating Causal Returns to Compulsory Schooling using Double Machine Learning

This repository contains the code and paper for an applied econometric analysis estimating the **causal effect of compulsory schooling laws on earnings in the United Kingdom**. The project exploits exogenous variation from historical changes in the minimum school-leaving age and applies **interactive IV double machine learning (DML)** to estimate local average treatment effects for policy-affected individuals.

The analysis focuses on two major reforms:  
- the increase in the minimum school-leaving age from **14 to 15** (1947 in Great Britain, 1957 in Northern Ireland), and  
- the increase from **15 to 16** in **1972**.

---

## Motivation

Estimating returns to education is complicated by endogeneity arising from unobserved ability, family background, and selection into schooling. Compulsory schooling laws provide a natural source of exogenous variation, but traditional linear IV models impose restrictive functional form assumptions.

This project applies **double machine learning** to relax these assumptions, allowing for flexible, nonlinear relationships while preserving valid causal inference. The goal is to estimate the **causal return to additional compulsory education for marginal students** whose schooling decisions were altered by policy.

---

## Data

The analysis uses repeated cross-sectional microdata combining:

- **UK General Household Survey (1983–1998)**  
- **Northern Ireland Continuous Household Survey (1985–1998)**  

The final dataset includes demographic characteristics, schooling histories, and real annual earnings. Individuals are assigned exposure to compulsory schooling reforms based on birth cohort and region.

---

## Methodology

The causal parameter of interest is the **Local Average Treatment Effect (LATE)** of additional compulsory education on log real earnings.

Key features of the empirical approach:
- Interactive IV framework targeting LATE
- Double machine learning estimation to debias regularized nuisance functions
- Flexible learners including **Random Forests, XGBoost, and Elastic Net**
- Cross-fitting and cross-validation for robustness
- Separate estimation by reform and region to study heterogeneity

---

## Main Findings

- Additional compulsory education induced by the **1947/1957 reforms** led to **large positive earnings effects** for marginal students (approximately **20–35%**).
- Returns to compulsory education were **smaller for the 1972 reform**, consistent with a narrower set of affected students.
- Estimates are robust across learners and cross-fitting schemes in samples with strong first-stage compliance.
- Results suggest that linear IV models may understate returns when treatment effects are nonlinear.


---

## Reproducibility

The analysis is fully reproducible using the provided R Markdown file.  
Due to data size and licensing restrictions, raw survey data are not included in the repository. Instructions for data access and preprocessing are documented in the code.

---

## Software

- R (≥ 4.0)
- Key packages: `DoubleML`, `mlr3`, `mlr3learners`, `xgboost`, `tidyverse`, `ivreg`

---

## Author

**Liam Henson**

---

## Notes

This repository is intended to demonstrate applied econometric modeling, causal inference, and reproducible research practices in a policy-relevant setting.
