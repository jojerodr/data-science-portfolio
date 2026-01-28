# Childcare Cost Analysis in the United States

## Overview
This project analyzes childcare costs across the United States using a national childcare pricing dataset. The goal is to understand how childcare expenses vary by age group, care type, and state, and to highlight affordability challenges faced by families.

## Objective
The primary objective was to explore patterns in childcare pricing and identify:
- Average childcare costs by age group and care setting
- States with the highest infant childcare costs
- Relative affordability of childcare when compared to household income

## Data
The analysis uses the *National Database of Childcare Prices*, which includes state-level information on:
- Weekly childcare costs by age group (infant, toddler, preschool)
- Care type (center-based vs. family-based)
- Median household income by state

Weekly costs were converted to annual estimates to support clearer comparisons.

## Methods
- Data cleaning and preprocessing (removal of currency symbols, type conversion)
- Exploratory data analysis (EDA)
- Aggregation and summary statistics
- Data visualization using bar charts to compare costs across categories and states

## Tools
- Python  
- pandas, NumPy  
- matplotlib, seaborn  
- Jupyter Notebook  

## Key Insights
- Infant care is consistently the most expensive category across care types.
- Center-based childcare is generally more costly than family-based care.
- Certain states show significantly higher median infant care costs than others.
- When compared to median household income, childcare costs represent a substantial financial burden in many states.

## Files
- `analysis.ipynb`: Main notebook containing data cleaning, analysis, and visualizations

