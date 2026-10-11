# Sustainable Finance Simulation: Greenium Valuation & Transition Dynamics

## Executive Summary
This project builds a relational database simulation and econometric framework to quantify the "Greenium" (yield discount on green bonds) and evaluate transition finance mechanics in corporate debt markets. Styled after the Luxembourg Green Exchange (LGX) and Climate Bonds Initiative (CBI) standards, the study models matched-pair bond structures and Sustainability-Linked Bonds (SLBs) with step-up penalty triggers. Utilizing an Ordinary Least Squares (OLS) regression framework, the model isolates the marginal impact of issuer ESG scores on secondary market yield spreads.

---

## Key Features & Technical Highlights

* **Relational Database Schema Design (DuckDB):** Structured an in-memory database linking corporate issuers with multi-class bond issuances (Vanilla, Green, and SLB), establishing relational constraints and domain-specific attributes.
* **Matched-Pair Greenium Extraction:** Implemented SQL queries to pair Green and Vanilla bonds issued by the same entity, calculating the net yield differential (Greenium) in basis points (bps).
* **Transition Finance Mechanics:** Modeled SLB coupon step-up penalties (25 bps) triggered by failure to meet key performance indicators (KPIs), capturing risk-pricing dynamics for high-emitting sectors.
* **Econometric Model Specification:** Applied OLS regression via `statsmodels` to benchmark the empirical relationship between ESG scores and Greenium spreads ($0.15 \text{ bps}$ reduction per ESG point).

---

## Analytical Pipeline Workflow

[ LGX / CBI Data Standards Schema ]
│
▼
[ Synthetic Market Generation ] ──► (50 Issuers across 6 Sectors & Matched Bonds)
│
▼
[ DuckDB Relational Engine ] ──► (Matched-Pair JOINs & SLB Penalty Tracking)
│
▼
[ Econometric OLS Regression ] ─► (Greenium ~ ESG Score + Carbon Intensity)
│
▼
[ Matplotlib Publication Plots ] ─► (Greenium Trend & KPI Step-Up Bar Chart)

---

## Key Results & Econometric Metrics

| Metric / Parameter | Value | Financial & Economic Interpretation |
| :--- | :--- | :--- |
| **Average Greenium Spread** | 5 to 19.2 bps | Borrowing cost discount achieved by green-labeled issuances |
| **ESG Score Coefficient ($\beta_1$)** | 0.1499 ($p < 0.001$) | Each 1-point ESG increase widens Greenium by ~0.15 bps |
| **SLB Penalty Margin** | +25.0 bps | Step-up coupon penalty applied upon KPI target default |
| **Average SLB Yield (Target Met)** | 4.49% | Base yield for compliant transition issuers |
| **Average SLB Yield (Target Missed)**| 4.59% | Penalized yield reflecting step-up margin execution |

---

## Tech Stack & Dependencies

* **Language:** Python 3.x
* **Database & SQL:** `duckdb`, `pandas`, `numpy`
* **Econometrics & Modeling:** `statsmodels`
* **Visualization:** `matplotlib`

---

## How to Run

 Clone the repository:
   ```bash
   git clone [https://github.com/meteaksu/greenium-transition-finance-simulation.git](https://github.com/meteaksu/greenium-transition-finance-simulation.git)
   cd greenium-transition-finance-simulation

   Install required packages:
   pip install pandas numpy duckdb statsmodels matplotlib

   Execute the primary analysis notebook:
   jupyter notebook green_bonds.ipynb
