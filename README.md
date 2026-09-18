# nhanes-vitamin-d
Survey-weighted logistic regression analysis of vitamin D deficiency and depression using NHANES 2017–2018 data (R)

# Vitamin D Deficiency and Depression (NHANES 2017–2018)  

# Overview

This project evaluates whether vitamin D deficiency is associated with depression using NHANES 2017–2018 data, a large, nationally representative federal health survey. The analysis uses survey-weighted logistic regression to account for NHANES's complex sampling design, adjusting for demographic, socioeconomic, and clinical covariates.

# Data

Source: NHANES 2017–2018 (public-use), merged from five component files (Vitamin D, Depression Screener, Demographics, Body Measures, Physical Activity) on respondent ID

Sample: Adults 18+ with complete data on vitamin D, depression screening, and covariates (n = 4,213)

Outcome: Depression, defined as a PHQ-9 score ≥ 10

Exposure: Vitamin D deficiency (< 30 nmol/L per CDC guidelines)

Covariates: Age group, sex, race/ethnicity, income-to-poverty ratio, season, BMI, and physical activity, selected from prior literature

# Methods

Survey-weighted multivariable logistic regression (survey::svyglm), incorporating NHANES sample weights, strata, and clusters

Chi-square confounder screening to test each covariate's association with both vitamin D and depression

Full model vs. reduced model comparison, dropping BMI and physical activity as potential intermediate variables

Forward stepwise selection by AIC to identify a parsimonious final model

# Key Results

Vitamin D deficiency was not significantly associated with depression in either model (adjusted OR ≈ 1.03, 95% CI: 0.59–1.81, p ≈ 0.89) - the null hypothesis was retained.

Income-to-poverty ratio was a strong protective factor (OR ≈ 0.73–0.77, p < 0.01).

Female sex (OR ≈ 1.39–1.43, p < 0.05) and Other/Multiracial identity (OR ≈ 3.2–3.4, p < 0.05) were independently associated with higher odds of depression.

Forward selection retained vitamin D, income, sex, and race/ethnicity in the final model - vitamin D remained non-significant throughout.

# Discussion

Despite prior literature linking vitamin D deficiency to depression, this analysis found no significant independent association after adjustment, suggesting socioeconomic and demographic factors play a more consistent role in this sample. Limitations include the cross-sectional design, self-reported PHQ-9 data, and possible residual confounding from excluded intermediate variables.

# Files

vitamin_d_depression.R - full analysis script (data merge, survey design, models, confounder screening, stepwise selection, visualizations)

Data: NHANES 2017–2018 component files (VID_J.XPT, DPQ_J.XPT, DEMO_J.XPT, BMX_J.XPT, PAQ_J.XPT) - from the CDC NHANES data portal

# Tools

R (haven, janitor, dplyr, tidyr, survey, broom, ggplot2, scales)
