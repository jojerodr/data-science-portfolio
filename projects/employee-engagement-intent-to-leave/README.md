# Understanding the Drivers of Employee Engagement and Intent to Leave

## Overview
This project analyzes employee engagement and intent to leave using the 2024 Federal Employee Viewpoint Survey (FEVS). The goal is to identify which engagement and workload-related factors are most strongly associated with employees’ likelihood of leaving, using large-scale survey data from the U.S. federal workforce.

## Business Problem
Employee engagement is a critical indicator of retention, performance, and organizational health. While organizations collect extensive employee survey data, it is often unclear which factors matter most for retention outcomes. This analysis explores how engagement, workload perceptions, and selected demographic characteristics relate to employees’ intent to leave.

## Data
The analysis uses the **2024 Federal Employee Viewpoint Survey (FEVS) Public Use Data File**, published by the U.S. Office of Personnel Management.  
- ~674,000 employee responses  
- 96 survey and demographic variables  
- Metadata-level join performed to map survey codes to question descriptions  
- Approximately 97.9% of variables successfully labeled

## Methods
- Data cleaning and preprocessing of large-scale survey data  
- Construction of a composite engagement score using four Likert-scale items:
  - Personal accomplishment (Q3)
  - Use of talents (Q6)
  - Alignment with agency goals (Q7)
  - Access to information (Q9)
- Exploratory data analysis (EDA)
- Descriptive statistics and visualization
- Correlation analysis between engagement, workload perceptions, and intent to leave

## Tools
- Python  
- pandas, NumPy  
- matplotlib, seaborn  
- Jupyter Notebook  

## Key Insights
- Employee engagement shows a moderate negative relationship with intent to leave (r = -0.36), indicating that higher engagement is associated with lower likelihood of leaving.
- Perceived workload reasonableness is also negatively associated with intent to leave (r = -0.25), though less strongly than engagement.
- Engagement and workload perceptions are positively correlated (r = 0.51), suggesting that engaged employees tend to view their workload more favorably.
- Engagement levels vary by tenure and supervisory status, highlighting differences in employee experience by career stage and role.

## Assumptions and Limitations
- Likert-scale survey items were treated as approximately continuous for analysis.
- Results reflect associations, not causal relationships.
- Findings are based on self-reported perceptions and broad public-use demographic categories.

## Files
- `employee_engagement_intent_to_leave.ipynb`: Data preparation, analysis, and visualizations
- `employee_engagement_intent_to_leave_report.pdf`: Written white paper summarizing findings and implications
- `employee_engagement_intent_to_leave_presentation.pdf`: presentation summarizing findings and implications

