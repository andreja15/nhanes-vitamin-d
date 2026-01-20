# Vitamin D Deficiency and Depression (NHANES 2017–2018) — R

# Overview
This project evaluates whether vitamin D deficiency is associated with depression using NHANES 2017–2018 data, using survey-weighted logistic regression.

# Data
- Source: NHANES 2017–2018 (public-use)
- Outcome: Depression (PHQ-9 ≥ 10)
- Exposure: Vitamin D deficiency

# Methods
- Survey-weighted multivariable logistic regression in R
- Covariate selection guided by a conceptual model
- Compared a full model vs. a reduced model excluding potential intermediates (e.g., BMI, physical activity)

# Key Results 
- Vitamin D deficiency was not significantly associated with depression in the adjusted model (OR ≈ 1.03; p ≈ 0.89).
- Several demographic/socioeconomic covariates showed stronger associations with depression.
