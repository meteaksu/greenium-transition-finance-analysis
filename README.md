# Econometric & Behavioral Modeling of the Greenium and Transition Finance

## 📌 Executive Summary
This research project explores the behavioral finance mechanisms and economic incentives behind the **Greenium** (Green Bond Premium) and applies these dynamics to **Transition Finance** instruments (Sustainability-Linked Bonds - SLBs). 

Utilizing a matched-pair bond dataset constructed in **DuckDB** based on **Luxembourg Green Exchange (LGX)** standards, the study quantifies the signaling impact of issuer ESG scores on yield discounts and analyzes the secondary market $YTM$ penalties triggered by coupon step-up mechanisms.

---

## 🛠️ Tech Stack & Methodology
* **Database & Data Architecture:** `DuckDB` (In-Memory SQL analytics, relational schema design, matched-pair join logic)
* **Econometric Modeling:** `Statsmodels` (Ordinary Least Squares - OLS Regression)
* **Data Processing & Visualization:** `Pandas`, `NumPy`, `Matplotlib` (Publication-ready financial visualization)
* **Market Standards:** Luxembourg Green Exchange (LGX) DataHub, Climate Bonds Initiative (CBI), ICMA SLB Principles

---

## 📊 Key Findings & Empirical Results

### 1. The Greenium Behavioral Model (OLS Regression)
$$\text{Greenium (bps)} = \beta_0 + \beta_1 (\text{ESG Score}) + \beta_2 (\text{Carbon Intensity}) + \epsilon$$

* **ESG Signaling Power ($p < 0.001$):** A statistically significant positive relationship was confirmed between an issuer's ESG score and the magnitude of the Greenium. Each 1-point increase in ESG score yields an average **~0.15 bps yield reduction** (Warm-Glow effect / SFDR institutional mandate push).
* **Greenwashing Premium:** Carbon intensity alone showed statistical insignificance in depressing Greenium, indicating that secondary markets heavily price ESG signaling over raw current carbon metrics.

### 2. Transition Finance & Step-Up Penalty Analysis
* Analyzed Sustainability-Linked Bonds (SLBs) featuring a **25 bps ($0.25\%$) coupon step-up penalty** triggered by missed sustainability KPI targets.
* Missed KPI targets resulted in an immediate adjustment in secondary market Yield-to-Maturity ($YTM$), demonstrating how behavioral penalty structures effectively discipline high-emitting ("brown") corporate issuers transitioning to net-zero.

---

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone [https://github.com/meteaksu/greenium-transition-finance-analysis.git](https://github.com/meteaksu/greenium-transition-finance-analysis.git)

   pip install pandas numpy matplotlib statsmodels duckdb
