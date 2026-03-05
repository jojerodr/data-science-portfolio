# Analyzing Patterns and Ethical Implications of Workforce Layoffs in 2022

## Overview
This project analyzes publicly reported workforce layoff events from 2022 — a year marked by rapid shifts from aggressive hiring to large-scale workforce reductions, particularly in tech and consumer-driven industries. Rather than treating layoffs as headline numbers, the analysis examines timing, industry concentration, organizational stage, and visibility bias to surface a more nuanced picture of workforce disruption.

The dataset is derived from the Layoffs.fyi tracker, hosted on Kaggle, and covers publicly disclosed layoff events including company name, industry, layoff counts, percentage of workforce affected, company stage, and date.

---

## Objectives
This project aimed to answer five key questions:

What temporal patterns can be observed in publicly reported layoffs throughout 2022?

Which industries experienced the highest frequency and magnitude of layoffs?

Are layoffs more commonly characterized by large, infrequent events or smaller, repeated reductions?

How does the visibility of layoffs differ across industries, and what does this imply about data completeness?

What risks arise when publicly reported layoff data is used to inform organizational or policy decisions?

---

## Dataset
**Source:** Layoffs.fyi tracker via Kaggle — Layoffs 2022  
**Scope:** Publicly disclosed workforce reduction events during 2022

| Variable | Description |
|----------|-------------|
| Company name | Organization reporting the layoff |
| Industry | Sector classification |
| Layoff date | Date of reported event |
| Employees laid off | Total headcount reduced |
| % of workforce affected | Proportional impact (where available) |
| Company stage | Seed, Series A–J, Post-IPO, etc. |

**Preprocessing:** Layoff dates were standardized into monthly periods. Numeric fields were cleaned and coerced into appropriate formats. ~36.8% of records lacked a reported workforce percentage and ~34.5% were missing total layoff counts — gaps that reflect reporting practices rather than data quality alone.

---

## Key Findings

### Temporal Patterns
Layoffs in 2022 did not occur gradually — they clustered in sharp waves. At the peak, a single month exceeded **90,000 employees laid off**, while many earlier months stayed under 10,000. This compression suggests layoffs were driven by sudden macroeconomic shifts rather than long-term workforce planning.

### Industry Concentration

| Industry | Total Laid Off | Layoff Events | Median Event Size |
|----------|---------------|---------------|-------------------|
| Hardware | 93,207 | 75 | 300 |
| Retail | 88,411 | 341 | 100 |
| Consumer | 83,160 | 275 | 112.5 |
| Transportation | 65,480 | 264 | 129 |
| Finance | 53,824 | 505 | 71.5 |
| Food | 50,811 | 244 | 124 |

Finance had the most layoff *events*, but Hardware had far larger individual events — an important distinction between frequency and magnitude.

### Layoff Severity Index
A severity index was constructed combining normalized layoff size (70%) and percentage of workforce laid off (30%) to capture proportional impact, not just raw counts.

| Company | Employees Laid Off | % of Workforce | Notes |
|---------|-------------------|----------------|-------|
| Intel | 22,000 | 20% | Highest severity score (~0.76) |
| Intel (2nd event) | 15,000 | 15% | — |
| Tesla | 14,000 | 10% | — |
| Amazon | 14,000 | 1% | Large in volume, low proportional impact |
| Katerra | 2,434 | 100% | Effectively ended operations |

### Company Stage and Organizational Risk
Post-IPO companies dominated layoff volume (992 events, 483,456 employees), but early-stage firms faced far higher proportional risk:

| Stage | Avg. % of Workforce Laid Off |
|-------|------------------------------|
| Post-IPO | 16.8% |
| Series A | 47.6% |
| Seed | 81.7% |

Employees at early-stage companies face significantly higher employment risk when layoffs occur, even though these events rarely make headlines.

### Visibility Bias
A visibility index (avg. layoff size × reported events) revealed that Hardware, Retail, and Consumer industries dominate public narratives — not necessarily because they were hit hardest, but because their layoffs were larger and more widely covered. This creates a systematic bias where smaller firms and less-covered sectors are underrepresented in public data.

### Distribution of Layoff Sizes
Layoff size distribution is highly right-skewed — most events were small, while a handful of extreme events account for a disproportionate share of total layoffs. Mean layoff sizes are inflated by outliers and do not reflect the typical experience for most organizations or employees.

---

## Ethical Considerations
- Public layoff data reflects **visibility, not completeness** — large, public companies are overrepresented
- Focusing on total counts without proportional context misrepresents true severity
- Normalizing layoffs as performance benchmarks minimizes their human impact
- Responsible use requires pairing absolute counts with proportional metrics and acknowledging reporting bias

---

## Key Takeaways
While Post-IPO companies dominated layoff headlines in 2022, employees at early-stage firms faced far greater existential risk. Public layoff data is a useful directional signal, but must be interpreted with an understanding of what it does — and does not — capture. Layoffs are not just data points; each one represents real workforce disruption with lasting personal and economic consequences.

---

## Files
- [layoffs2022Code.pdf](layoffs2022Code.pdf): Analysis code and visualizations
- [layoffs2022Deck.pdf](layoffs2022Deck.pdf): Slide deck summarizing findings
- [layoffs2022Paper.pdf](layoffs2022Paper.pdf): Full written analysis covering methodology, findings, and ethical implications

---

## Tools
Python  
pandas  
matplotlib  
Kaggle — Layoffs 2022 Dataset (Layoffs.fyi)
