# Predicting Restaurant Inspection Risk Using Historical Inspection Data

## Overview

Restaurant inspection grades in Los Angeles County are public and highly visible. A downgrade from an A to a B is not just regulatory — it affects revenue, reputation, and long term viability.

This project evaluates whether historical inspection data contains measurable predictive signal about future downgrade risk. Instead of analyzing inspection scores descriptively, the goal is to test whether prior inspection behavior can predict the likelihood of receiving a non-A grade on a subsequent inspection.

The final dataset contains 106,694 inspection records from the Los Angeles County Environmental Health public portal.

---

## Business Problem

Inspection outcomes influence customer behavior and operational stability. If downgrade risk is partially persistent rather than random, historical data could be used to identify elevated risk facilities before the next inspection.

This project reframes inspection outcomes as a predictive risk problem rather than a compliance report.

---

## Data Preparation and Feature Engineering

After cleaning and filtering to valid A, B, and C grades:

Total inspections: 106,694  
Non-A inspections: 4,861 (~4.6%)

The target variable was defined as:

1 = Non-A grade  
0 = A grade  

Records were sorted by facility and inspection date to preserve temporal order.

Facility-level historical features were engineered using only prior inspections to prevent time leakage:

Prior inspection count  
Prior average score  
Prior non-A rate  
Days since last inspection  

First-time inspections were excluded due to lack of historical data. After filtering, 63,782 inspections remained in the modeling dataset.

Categorical features (program status, service description, program element, city, ZIP code) were one-hot encoded, resulting in 827 total predictors.

---

## Temporal Validation Strategy

To simulate real-world deployment, a time-based split was used instead of random sampling.

Training set: 51,120 inspections  
Test set: 12,662 inspections  
Cutoff date: June 17, 2025  

Non-A rate shifted from:

4.28% in training  
8.04% in test  

This revealed temporal drift and reinforced the importance of time-aware validation.

---

## Modeling and Performance

Three classification models were trained:

Logistic Regression  
Random Forest  
Gradient Boosting  

Performance was evaluated using:

ROC-AUC  
Precision  
Recall  
F1 Score  
Confusion Matrices  

### ROC-AUC Results

Gradient Boosting: 0.7846  
Random Forest: 0.7550  
Logistic Regression: 0.7479  

Gradient Boosting achieved the strongest ranking ability overall.

However, threshold-level behavior revealed tradeoffs:

Gradient Boosting had strong precision but very low recall (2.7%) at default threshold.
Logistic Regression captured 55.8% of non-A cases but with lower precision (18.9%).

This illustrates the operational tradeoff between sensitivity and false positives.

---

## Key Risk Patterns

Descriptive analysis revealed structured risk patterns:

High-risk restaurant categories showed elevated non-A rates:

Restaurant (61–150 seats) high risk: 8.65%  
Restaurant (31–60 seats) high risk: 8.26%  
Restaurant (0–30 seats) high risk: 7.11%  

Moderate risk categories generally fell between 2–3.5%.

Inspection outcomes are not independent events. Past performance meaningfully shifts downgrade probability.

---

## Ethical Considerations

Geographic features may encode neighborhood-level disparities.
Risk scores reflect probability, not certainty.
Models must not be used as punitive labeling tools.
Ongoing fairness monitoring and drift detection would be required in deployment.

---

## Recommendations and Implementation

If deployed by a health department, the model would support inspection prioritization rather than automated enforcement.

A practical deployment plan would include:

1. Selecting a recall-oriented threshold  
2. Monitoring precision to manage operational burden  
3. Quarterly retraining to address temporal drift  
4. Auditing performance across geographic segments  

---

## Key Takeaways

Inspection history contains measurable predictive signal.
Rare event prediction requires careful metric selection beyond accuracy.
Time-based validation is essential in operational risk modeling.
Model choice depends on objective: early warning vs precision control.
Used responsibly, this framework could support proactive compliance efforts.

---

## Files
| File | Description |
|------|------------|
| [JRodriguez_DSC680_P3M3_Paper.pdf](JRodriguez_DSC680_P3M3_Paper.pdf) | Full white paper |
| [JRodriguez_DSC680_P3M3.pdf](JRodriguez_DSC680_P3M3.pdf) | Modeling notebook |
| [JRodriguez_DSC680_P3M3Code.pdf](JRodriguez_DSC680_P3M3Code.pdf) | Slide deck |

---

## Tools

Python  
pandas  
scikit-learn  
matplotlib  
numpy
