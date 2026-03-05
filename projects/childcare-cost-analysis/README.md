# Childcare Affordability: The Hidden Workforce Risk
## Overview
This project investigates childcare affordability as an underestimated constraint on workforce participation across the United States. Using the U.S. Department of Labor's National Database of Childcare Prices (2023), the analysis quantifies childcare costs by state, measures affordability relative to household income, and evaluates how cost burdens shape labor-force participation — particularly for women and single-parent households.

The project is structured across four mediums, ending with an interactive Power BI dashboard.

---

## Objectives
This project aimed to answer three key questions:

How do childcare costs vary across states and age groups, and where are the most extreme geographic inequities?

How does childcare affordability burden relate to female labor-force participation rates at the county level?

Which household types are most exposed to childcare cost pressure, and what are the workforce implications?

---

## Dataset
**Source:** U.S. Department of Labor — National Database of Childcare Prices (2023)  
**Observations:** 23,000+ across all U.S. states and counties  
**Key variables:**
| Variable | Description |
|----------|-------------|
| Weekly childcare prices | Center-based and family-based, by age group |
| Median Household Income (MHI) | State and county level |
| Female Labor-Force Participation Rate (FLFPR) | County level |
| Single-mother households | Number with children under age 6 |

**Preprocessing:** Weekly prices were annualized (×52) and divided by MHI to compute affordability ratios. Currency symbols and commas were stripped; missing numeric values were handled through standard pandas conversions with no rows selectively removed.

---

## Key Findings

### National Patterns
- The median annual infant-care cost across the U.S. is approximately **$8,589**, rising above **$15,700** in high-cost regions like Washington D.C.
- Most counties devote **15–30% of household income** to infant care — well above the federal 7% affordability benchmark.
- Female labor-force participation averages **56–57%** nationally, but declines in counties where childcare burdens exceed 20–25% of income.
- A positive correlation (**+0.144**) exists between affordability burden and the concentration of single-mother households with children under six.

### Insights From Visualizations

**1. Infant Care Is the Most Expensive Age Group**  
Center-based infant care reaches $150–$180 per week nationally ($7,800–$9,300/year). Family-based infant care is cheaper but still runs $80–$110 per week.

**2. Large Geographic Inequities**  
The top states by annual infant-care cost and their affordability burden:

| State | Affordability Burden (% of Income) |
|-------|-------------------------------------|
| Washington | 26.5% |
| California | 24.7% |
| D.C. | 24.6% |
| Massachusetts | 22.4% |
| New York | 20.4% |

These states exceed the federal affordability guideline by **3–4×**, despite having higher median incomes. West Coast, Northeast, and Southeastern states cluster as the highest-burden regions.

**3. Workforce Participation Declines as Affordability Worsens**  
A scatterplot of affordability vs. FLFPR shows a **negative correlation of –0.139**. Counties with burdens above 25% cluster heavily in the 50–65% FLFPR range. This relationship slightly strengthens when high-income outliers are removed, suggesting affordability constraints matter most for middle- and low-income families.

**4. Single-Mother Households Are Disproportionately Exposed**  
Counties with the highest affordability burdens frequently show 80–120+ single-mother households with children under six (+0.144 correlation). Families with the least financial flexibility face the steepest cost pressures, creating compounding workforce risks.

**5. Burden by Age Group**
| Age Group | % of Income |
|-----------|-------------|
| Infants | 15.9% |
| Toddlers | 14.3% |
| Preschool | 13.5% |

---

## Key Takeaways
Childcare affordability is not just a family problem — it is a **structural workforce issue**. When infant care consumes 20–25% of a household's income, labor-force participation drops, talent pipelines shrink, and retention challenges grow — especially for single-parent households.

Even modest employer supports or policy interventions targeting childcare costs have the potential to stabilize participation and improve equity outcomes across income levels.

---

## Future Work
- Incorporate subsidy data and employer childcare benefit programs
- Analyze year-over-year affordability trends
- Explore causal modeling to move beyond correlation

---

## Files
* [childcare_cost_analysis.ipynb](childcare_cost_analysis.ipynb): Data cleaning, analysis, and visualizations
* [childcare_cost_analysis_report.pdf](childcare_cost_analysis_report.pdf): Written report summarizing methods and findings
* [childcare_cost_analysis_presentation.pdf](childcare_cost_analysis_presentation.pdf): Slide deck used to present results
---

## Tools
Python  
pandas  
matplotlib  
Plotly  
Power BI  
U.S. DOL National Database of Childcare Prices (2023)
