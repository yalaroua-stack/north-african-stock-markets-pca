# North African Stock Markets — Factor Structure Analysis

**Academic project** — Master 1 Actuarial Science & Finance | May 2026

## Overview

This repository contains the full data analysis pipeline for the paper:

> *"Factor Structure of North African Stock Markets: A PCA-Based Analysis of MASI, EGX30, and Tunindex"*  
> Younes El Aaroua & Adham El Hayani

The project investigates whether Morocco (MASI), Egypt (EGX30), and Tunisia (Tunindex) share common latent risk factors over the period 2015–2024, using a combination of factorial and correspondence analysis methods.

## Key Findings

- **PC1 explains 46.0%** of joint return variance — a regional North African market factor
- **COVID-19 caused transient amplification**: PC1 surged from 36.8% to 66.4% before returning to 35.4% post-crisis
- **MASI acts as a regional hub**: AFC confirms crash co-movement through Morocco but no direct Egypt–Tunisia qualitative link (p = 0.652)
- **Tunindex structurally decoupled post-2022**: PC1 loading reversed from +0.353 to −0.517, driven by Tunisia's domestic crisis
- **Tunindex offers the best risk-adjusted returns**: Sharpe = 0.21 (full sample), 0.99 (post-COVID)

## Methods

| Method | Purpose |
|--------|---------|
| PCA | Latent factor extraction from return covariance matrix |
| Rolling PCA (120-day) | Time-varying factor intensity tracking |
| AFC | Pairwise qualitative co-movement tests |
| ACM | Joint qualitative market state mapping |
| Mean-Variance Optimisation | Sharpe ratio analysis + efficient frontier |

## Repository Structure

```
├── north_african_markets_analysis.ipynb   # Full annotated analysis notebook
├── MASI.csv                               # Morocco MASI daily prices (Investing.com)
├── EGX30.csv                              # Egypt EGX30 daily prices (Investing.com)
├── Tunindex.csv                           # Tunisia Tunindex daily prices (Investing.com)
├── figures/                               # All generated PNG figures
│   ├── pca_scree.png
│   ├── rolling_pca.png
│   ├── afc_residuals.png
│   ├── acm_fullsample.png
│   └── ...
└── README.md
```

## How to Run

**Requirements:**
```bash
pip install pandas numpy scipy statsmodels scikit-learn prince matplotlib
```

**Steps:**
1. Download `MASI.csv`, `EGX30.csv`, `Tunindex.csv` from [Investing.com](https://www.investing.com) (daily, 2015–2024)
2. Place all CSV files in the same folder as the notebook
3. Open `north_african_markets_analysis.ipynb` in Jupyter
4. Run all cells from top to bottom (`Kernel → Restart & Run All`)

All output figures and CSV tables are saved automatically in the working directory.

## Data Source

Daily closing prices retrieved manually from [Investing.com](https://www.investing.com)

## Tech Stack

- **Python** 3.13.1 (Anaconda)
- **pandas**, **numpy** — data manipulation
- **scikit-learn** — PCA
- **scipy**, **statsmodels** — statistical tests (ADF, Jarque-Bera, KMO, Bartlett, χ²)
- **prince** — Multiple Correspondence Analysis (ACM)
- **matplotlib** — visualisation

## License

Academic use only. Data from Investing.com is subject to their terms of service.
