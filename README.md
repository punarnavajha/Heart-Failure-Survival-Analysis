# Heart-Failure-Survival-Analysis
# Survival Analysis: Heart Failure Clinical Outcomes

###  Introduction

This project presents a retrospective survival analysis of patients with heart failure, a critical condition where cardiac output is insufficient to meet physiological demands.

The primary objective is to identify and quantify the impact of specific clinical biomarkers—such as age, ejection fraction, and serum creatinine—on patient longevity.

By utilizing non-parametric (Kaplan-Meier) and semi-parametric (Cox Proportional Hazards) methods, this study evaluates which clinical factors most significantly influence the hazard of mortality

### Data and Methods 

Provider: UCI Machine Learning Repository

Dataset: Heart Failure Clinical Records (ID: 519)

Indicator: Time to death event or censoring (Days)

Sample Size: 299 observations

### Methods

**Retrospective Observational Analysis:** Performed on a curated clinical cohort.

**Data Pipelines:** Programmatically fetched using the ucimlrepo API and processed via Python (pandas).

**Survival Estimation:** Non-parametric survival functions estimated using the Kaplan-Meier Fitter.

**Regression Modeling:** A Cox Proportional Hazards (CPH) model was employed to estimate multivariate Hazard Ratios (HR).

### Technical Implementation & Resilience

A significant technical hurdle was encountered during the data acquisition phase in a Python 3.14 (macOS) environment. The system triggered a SSLCertVerificationError due to missing root certificates in the standalone Python installation.

# Resolution:
The issue was resolved by programmatically configuring an unverified SSL context for the urllib library. This ensured a stable, reproducible data fetch pipeline without compromising the local system's global security settings.

###  Clinical Insights & Findings
My model achieved a **Concordance Index of 0.72**.

#### 1. Survival Probability (Kaplan-Meier)
Comparison between cohorts shows a distinct trend in survival probability over the 250+ day follow-up period.
![Kaplan-Meier Curve](The%20KM%20Curve.png)

Trend: While both groups show a decline in survival, divergence is noted during long-term follow-up.

Interpretation: Non-smokers generally exhibit a higher survival probability, though confidence intervals overlap, necessitating multivariate regression for clarity.

#### 2. Risk Quantification (Cox PH Model)
Using the `lifelines` library, I identified three primary predictors of mortality:
![Cox Summary](The%20Cox%20Summary.png)


* **Serum Creatinine (HR: 1.43):** The strongest risk factor identified; a unit increase corresponds to a **43% increase** in mortality risk.
* **Age (HR: 1.05):** Each year of age increases mortality risk by **5%**.
* **Ejection Fraction (HR: 0.95):** A protective factor; higher heart pump efficiency reduces mortality risk by **5%**.

### Discussion

Marked variation in survival hazard was observed based on biochemical markers. The Hazard Ratio of 1.43 for serum creatinine highlights the critical prognostic value of renal function in heart failure patients. Conversely, the protective effect of ejection fraction (HR 0.95) underscores the importance of cardiac pump efficiency in determining longevity.

These differences likely reflect structural physiological factors and the progression of multi-organ failure (specifically cardiorenal syndrome).

### Limitations

**Sample Size:**  The analysis is based on 299 patients, which may limit generalizability to broader populations.

**Case Mix:**  No adjustment for comorbid conditions outside the provided features or genetic predispositions.

**Descriptive Scope:** Findings identify associations rather than direct causal pathways.

###  Technical Resilience
* **Environment:** Developed in Python 3.14 on macOS.
* **Problem Solving:** Successfully addressed `SSLCertVerificationError` hurdles during data acquisition by programmatically configuring an unverified SSL context for `urllib`.
