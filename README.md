# Heart-Failure-Survival-Analysis
##  Survival Analysis: Heart Failure Clinical Outcomes

###  Project Overview
This study investigates mortality risk factors in heart failure patients using a cohort of 299 observations from the UCI Machine Learning Repository. I implemented Kaplan-Meier survival curves and a multivariate Cox Proportional Hazards model to identify significant clinical predictors.

### Clinical Insights & Findings
My model achieved a **Concordance Index of 0.72**.

#### 1. Survival Probability (Kaplan-Meier)
Comparison between cohorts shows a distinct trend in survival probability over the 250+ day follow-up period.
![Kaplan-Meier Curve](The%20KM%20Curve.png)

#### 2. Risk Quantification (Cox PH Model)
Using the `lifelines` library, I identified three primary predictors of mortality:
![Cox Summary](The%20Cox%20Summary.png)

* **Serum Creatinine (HR: 1.43):** The strongest risk factor identified; a unit increase corresponds to a **43% increase** in mortality risk.
* **Age (HR: 1.05):** Each year of age increases mortality risk by **5%**.
* **Ejection Fraction (HR: 0.95):** A protective factor; higher heart pump efficiency reduces mortality risk by **5%**.

###  Technical Resilience
* **Environment:** Developed in Python 3.14 on macOS.
* **Problem Solving:** Successfully addressed `SSLCertVerificationError` hurdles during data acquisition by programmatically configuring an unverified SSL context for `urllib`.
