# Heart-Failure-Survival-Analysis
# Predictive Modeling of Survival Outcomes in Heart Failure Patients
# Introduction
This project presents a retrospective survival analysis of patients with heart failure, a critical condition where cardiac output is insufficient to meet physiological demands.

The primary objective is to identify and quantify the impact of specific clinical biomarkers—such as age, ejection fraction, and serum creatinine—on patient longevity. By utilizing non-parametric (Kaplan-Meier) and semi-parametric (Cox Proportional Hazards) methods, this study evaluates which clinical factors most significantly influence the hazard of mortality.

# Data and Methods
Data Source

Provider: UCI Machine Learning Repository

Dataset: Heart Failure Clinical Records (ID: 519)

Indicator: Time to death event or censoring (Days)

Sample Size: 299 observations

# Methods

Retrospective Observational Analysis: Performed on a curated clinical cohort.

Data Pipelines: Programmatically fetched using the ucimlrepo API and processed via Python (pandas).

Survival Estimation: Non-parametric survival functions estimated using the Kaplan-Meier Fitter.

Regression Modeling: A Cox Proportional Hazards (CPH) model was employed to estimate multivariate Hazard Ratios (HR).

Technical Resilience: Addressed macOS-specific SSL certificate hurdles in Python 3.14 to ensure a reproducible data acquisition pipeline.

# Results
Survival Probability Comparison

The Kaplan-Meier analysis (Figure 1) illustrates the survival probability over time, comparing smoking and non-smoking cohorts.

Trend: While both groups show a decline in survival, divergence is noted during long-term follow-up.

Interpretation: Non-smokers generally exhibit a higher survival probability, though confidence intervals overlap, necessitating multivariate regression for clarity.

Multivariate Risk Quantification

The Cox Proportional Hazards model achieved a Concordance Index of 0.72, indicating strong predictive discrimination.

Clinical Factor	Hazard Ratio (HR)	P-Value	Interpretation
Age	1.05	<0.005	5% increased mortality risk per year of age.
Ejection Fraction	0.95	<0.005	Protective: 5% reduction in risk per % increase in heart function.
Serum Creatinine	1.43	<0.005	Major Risk: 43% increased risk per unit increase.
Discussion
Marked variation in survival hazard was observed based on biochemical markers. The Hazard Ratio of 1.43 for serum creatinine highlights the critical prognostic value of renal function in heart failure patients. Conversely, the protective effect of ejection fraction (HR 0.95) underscores the importance of cardiac pump efficiency in determining longevity.

These differences likely reflect structural physiological factors and the progression of multi-organ failure (specifically cardiorenal syndrome).

# Limitations
Sample Size: The analysis is based on 299 patients, which may limit generalizability to broader populations.

Case Mix: No adjustment for comorbid conditions outside the provided features or genetic predispositions.

Descriptive Scope: Findings identify associations rather than direct causal pathways.

# Conclusion
This analysis demonstrates the value of survival modeling in identifying high-risk clinical profiles in heart failure patients. By quantifying the protective effect of cardiac function against the high-risk impact of renal impairment, this project provides a data-driven framework for clinical risk stratification.

# Tools Used
Python

pandas

lifelines (Survival Analysis)

matplotlib
