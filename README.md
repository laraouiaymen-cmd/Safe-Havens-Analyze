# Did COVID-19 Change Safe-Haven Behaviour?

Evidence from volatility modelling, dynamic correlations, structural breaks, and regime switching — daily data across six assets, 1990–2026.

*MSc Finance — Asset & Risk Management, HEC Lausanne. Empirical Methods in Finance.*

---

## Research question

Traditional defensive assets (gold, US Treasuries, CHF, JPY) are assumed to provide reliable diversification during equity drawdowns. This project tests whether COVID-19 permanently altered those relationships relative to major equity benchmarks (the S&P 500 and Euro Stoxx 50) — changing the nature, persistence, and asset-specificity of safe-haven behaviour — and what that implies for portfolio construction.

## Methods

- **GJR-GARCH(1,1)-t** — asymmetric volatility modelling with Student-t innovations across six assets; Wald tests on persistence pre vs. post COVID
- **DCC(1,1)** — time-varying correlations between each safe-haven/equity pair; conditional beta decomposition separating correlation from relative volatility
- **Andrews sup-F + Bai-Perron** — two-stage structural break procedure on each of the eight DCC correlation series; break dates identified endogenously
- **Markov switching** — two-state regime model estimated separately pre and post COVID; Wald tests on transition probability equality across periods
- **ERC portfolio** — equal risk contribution weights before and after COVID; cost of inaction computed as the volatility increase from keeping pre-COVID allocations

## Key findings

COVID-19 did not eliminate safe-haven behaviour, but made it more unstable, asset-specific, and regime-dependent. Structural breaks are identified in all eight safe-haven/equity correlation pairs, with COVID-era break dates ranging from March 2020 to April 2021. The Markov-switching estimates show that the high-correlation breakdown regime became longer for most pairs post-COVID — most notably US Treasuries vs. S&P 500, where expected breakdown duration rose from 91.5 to 135.6 trading days. Gold and the yen proved more resilient; the Swiss franc improved against European equities but deteriorated against US equities. An investor keeping pre-COVID ERC weights in the post-COVID covariance structure incurs an additional 0.19 annualized percentage points of portfolio volatility.

## Repository structure

```
safe_haven_analysis.ipynb   — full pipeline with saved outputs (no re-run required)
safe_haven_report.pdf       — written report: methodology, results, discussion
data/                       — not included; course-provided dataset
```

## Dependencies

```
arch
ruptures
statsmodels
numpy
pandas
matplotlib
scipy
```

## Data note

The dataset (daily prices, 1990–2026, six assets) was provided as part of the HEC Lausanne Empirical Methods in Finance course and is not included in this repository. All outputs are saved directly in the notebook and fully visible without re-running.
