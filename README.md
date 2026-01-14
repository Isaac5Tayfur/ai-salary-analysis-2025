# Statistical Analysis & Salary Modeling in the AI Job Market (2025) 🤖

This project provides a statistically rigorous analysis of AI job salaries in 2025, combining exploratory analysis, robust non-parametric inference, effect sizes, and predictive modeling. The goal is not only to identify *who earns more*, but also *who varies more* and which factors meaningfully drive compensation.

> *Context:* Final project for an advanced **Statistics for Data Science** course.

---

## Objectives
- Understand salary distributions and market structure (central tendency **and** dispersion).
- Validate group differences using robust statistical inference (beyond p-values).
- Quantify practical significance using **effect sizes**.
- Build an interpretable predictive baseline model for salary estimation.

---

## Dataset
- Source: Kaggle dataset **“Global AI Job Market Trend 2025”** (downloaded programmatically via `kagglehub`).
- File used: `ai_job_dataset.csv`
- Sample size: ~15,000 job records (after cleaning/outlier handling, slightly reduced).

---

## Methods (high level)
### 1) Exploratory Data Analysis (EDA)
- Distributional inspection of salary and predictors
- Visual comparisons across experience level, company size, and other categorical drivers

### 2) Outlier handling
- Identification and treatment of extreme values to stabilize inference and modeling

### 3) Statistical inference (robust workflow)
- Normality checks and variance assessment
- **Kruskal–Wallis** for global group differences (non-parametric)
- Practical significance via **epsilon squared (ε²)** / **eta squared (η² approx.)**
- Post-hoc quantification using **bootstrapping** (confidence intervals for differences)

### 4) Association analysis
- Categorical association measured via **Cramér’s V**

### 5) Predictive modeling
- Multiple regression with dummy encoding
- Comparison between linear vs. log-transformed approaches
- Bootstrap-based evaluation (RMSE)

---

## Key findings (from the notebook conclusions)
- **Experience is the dominant salary driver**: `experience_level` explains ~**64.5%** of salary variability (η² ≈ 0.65).
- **Company size is secondary**: `company_size` explains ~**3%** of the variability (η² ≈ 0.03).
- **Salaries are not normally distributed** and show positive skewness, consistent with a market containing a long tail of high-paying roles.
- **Dispersion differs strongly by group**: some segments exhibit much wider salary “bands”, suggesting heterogeneous career paths and compensation structures.
- **Weak dependence between experience and company size** (Cramér’s V ≈ **0.03**), indicating these factors are largely independent.
- **Predictive baseline (log-linear OLS)** achieves **R² ≈ 67.9%** and an average error (RMSE) of ~**$30,147 USD** (bootstrap-based), implying relevant variance remains unexplained by these two variables alone.

---

## Repository contents
- `Statistical Analysis of AI Salaries (2025).ipynb` — full executed notebook (analysis + results)
- (optional) `Statistical Analysis of AI Salaries (2025).html` — rendered version for easy reading
- `README.md` — project overview (this file)

---

## How to run
### Option A — Run the notebook as-is
1. Create/activate your environment (Python 3.10 recommended).
2. Install dependencies (example):
   ```bash
   pip install -U kagglehub pandas numpy scipy statsmodels scikit-learn matplotlib seaborn plotly tqdm
   ```

3. Open and run:

   ```bash
   jupyter lab
   ```

### Option B — Use the existing dataset file

If you already have `ai_job_dataset.csv`, place it in the project folder and update the notebook path accordingly.

---

## Notes & limitations

* Results reflect the dataset’s sampling and labeling quality; real-world salaries also depend on geography, role specialization, and negotiation dynamics.
* The predictive model is best interpreted as an **explanatory baseline**, not a precise salary oracle.

---

## Author

Tayfur Akkaya Clavijo  
Blog: [https://tayfur-ac.hashnode.dev/](https://tayfur-ac.hashnode.dev/)  
GitHub: [https://github.com/Isaac5Tayfur](https://github.com/Isaac5Tayfur)

