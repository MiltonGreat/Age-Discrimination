# Credit Scoring Model & Age Bias Analysis

![screenshot-localhost_8888-2025 04 04-13_55_35](https://github.com/user-attachments/assets/2cba1caa-b822-4a34-a2b8-3f33cc06429a)

### Overview

This project builds a credit risk scorecard using machine learning (logistic regression) and analyzes whether the model introduces age-based discrimination, particularly against older applicants (60+).

Key questions addressed:

- Does the credit scoring model unfairly penalize older applicants with lower scores?
- How does model performance vary across age groups?
- Is there statistical evidence of bias in approval rates?

### Dataset

Target: SeriousDlqin2yrs (1 = default within 2 years, 0 = no default)

**Key Features Used**

- Feature Risk Impact
- RevolvingUtilizationOfUnsecuredLines (Hig)h
- TotalPastDue (engineered) (Very High)
- NumberOfTimes90DaysLate (High)
- MonthlyIncome (Medium)
- age (Low)

### Key Steps

1. Data Preparation
- Cleaning: Handles missing values, outliers, and feature engineering (e.g., TotalPastDue).
- Demographic Simulation: Generates synthetic race/gender attributes (real data lacks these due to privacy).

2. Model Training
- Traditional Scorecard: Logistic regression with score mapping (e.g., 600 base points).
- ML Models: Random Forest and Gradient Boosting, optimized for AUC-ROC.

3. Fairness Evaluation
Metrics:
- Disparate impact ratio (threshold: <0.8 indicates bias).
- Statistical tests (t-tests for score differences by demographic group).
Visualization: Score distributions, fairness gaps, and performance comparisons.

### Key Findings

1. No Age Discrimination Against Older Applicants

Older applicants (60+) receive higher credit scores on average than younger groups. Approval rates:

- 60+: 79.4%
- <60: 44.5%

Disparate impact ratio = 1.78 (well above the 0.8 fairness threshold).

2. Statistical Significance

All age groups show significant differences in scores (p < 0.001):

- 70+ applicants score 27.6 points higher than the reference group (30-39).

### Recommendations

1. No evidence of bias against older applicants—the model is fair by regulatory standards.

2. Potential over-favoring of older groups: Scores may be too generous given their lower default rates.

### Next steps:

- Investigate feature interactions (e.g., DebtRatio for retirees).
- Test for other biases (income, geography).
- Recalibrate thresholds if stricter parity is needed.

### Source

[Give Me Some Credit Dataset from Kaggle](https://www.kaggle.com/c/GiveMeSomeCredit)
  

