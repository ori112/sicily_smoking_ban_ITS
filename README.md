# Interrupted Time Series (ITS) Analysis - Sicily Smoking Ban

## Project Overview
This project analyzes the impact of the 2005 public smoking ban in Sicily on hospital admissions for Acute Coronary Events (ACE). Using a **Frequentist approach** (Segmented Regression), we model the trend of admissions before and after the intervention to estimate the causal impact of the policy.

## Methodology
* **Design:** Interrupted Time Series (ITS)
* **Model:** Generalized Linear Model (GLM) with Poisson distribution (log-link).
* **Intervention Point:** January 2005 (Month 37).
* **Key Adjustments:**
    * **Seasonality:** Controlled using categorical month variables (`C(month)`).
    * **Population:** Controlled using log-population as an offset term.

## Data Structure
The analysis uses `sicily.csv` with the following key columns:
* `time`: Continuous time index (months 1-59).
* `aces`: Count of Acute Coronary Events (Outcome).
* `smokban`: Binary indicator (0 = Pre-ban, 1 = Post-ban).
* `stdpop`: Standardized population (used for rate calculation).

## Results Summary
* **Immediate Effect:** The model estimates a statistically significant drop in ACE admissions immediately following the ban.
* **Trend Change:** The long-term slope of admissions did not significantly change after the intervention; the primary impact was a "level shift" (immediate drop).
* **Counterfactual Analysis:** Comparing the actual data to a "No Ban" projection