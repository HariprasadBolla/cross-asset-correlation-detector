# Cross-Asset Correlation Anomaly Detector

A quantitative finance project that tracks rolling correlations 
across major asset classes and automatically flags when 
relationships break down from historical norms.

## Overview

Financial markets are interconnected — stocks, bonds, gold, and 
currencies typically maintain stable relationships over time. 
When these relationships break down, it often signals a market 
dislocation driven by macro events such as financial crises, 
central bank policy shifts, or geopolitical shocks.

This tool automatically detects those breakdowns across 6 
cross-asset pairs using statistical anomaly detection.

## Assets Tracked

- **SPY** — S&P 500 (Equities)
- **GLD** — Gold (Commodities)
- **TLT** — US 20Y Treasury Bonds (Rates)
- **UUP** — US Dollar Index (FX)

## Methodology

- Downloads 10 years of daily price data via Yahoo Finance
- Converts prices to daily percentage returns
- Computes 60-day rolling correlations for all 6 asset pairs
- Flags anomalies when correlation exceeds ±2 standard deviations 
  from the historical mean
- Visualizes results with anomaly bands and generates a summary report

## Key Findings

- **GLD vs UUP** had the most anomaly days (145), reflecting 
  repeated breakdowns in the traditional gold-dollar inverse 
  relationship driven by geopolitical risk
- **SPY vs TLT** was the most stable pair with only 18 anomaly 
  days, maintaining its traditional inverse relationship for most 
  of the decade
- Major anomaly clusters align with: the 2016 Brexit shock, 
  the 2020 COVID crash, and the 2022-2023 Fed rate hike cycle

## Libraries Used

- `yfinance` — market data
- `pandas` — data manipulation
- `matplotlib` & `seaborn` — visualization

## How to Run

1. Clone the repository
2. Install dependencies: `pip install yfinance pandas matplotlib seaborn`
3. Open `cross_asset_correlation.ipynb` in Jupyter Notebook
4. Run all cells
