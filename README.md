# ARDL–STR–KAN: A Regime-Gated Hybrid Forecasting Framework

Supplementary material for the paper **"A Regime-Gated Hybrid Forecasting Framework: Coupling
Autoregressive Distributed Lags, Smooth-Transition Dynamics, and Kolmogorov–Arnold Residual
Learning"**.

**Author:** Mazin Mohammed (corresponding author), Department of Statistics, CHRIST (Deemed to
be University), Bengaluru, India — mazin.mohammed@stat.christuniversity.in

**Co-authors:** Dibu A.S. and Sathya P., same department.

ARDL–STR–KAN is a three-stage hybrid forecaster: an ARDL linear conditional mean, a logistic
smooth-transition (STR) gate whose transition variable is chosen by a Teräsvirta-type F-test,
and a Kolmogorov–Arnold Network (KAN) that learns the nonlinear ARDL residual, combined as
ŷ_t = L̂_t + G_t · KAN(X_t).

## Contents

### Figures (`Figures/`)

| File | Paper reference | Shows |
|---|---|---|
| `S1_log_transform.jpg` | Section 5.2 | NASDAQ Composite level and its log, showing variance stabilisation |
| `S2_exogenous_series.jpg` | Section 5.2 | Log 10-year Treasury yield and log VIX (VIX spikes in 2008 and 2020) |
| `S3_returns_volatility_clustering.jpg` | Section 5.2 | Daily log returns, showing volatility clustering |
| `S4_return_distribution.jpg` | Section 5.2 | Return density against the normal, and normal Q–Q plot (heavy, asymmetric tails) |
| `S5_residual_diagnostics.jpg` | Section 6.1 | ACF of ARDL residuals and of squared residuals (ARCH effects) |
| `S6_gate.jpg` | Section 3.3 | Fitted logistic gate (γ = 4.655, c = 0) and distribution of G_t |
| `S7_rmse_comparison.jpg` | Section 7.1 | Hold-out RMSE of ARDL vs hybrid, with the Diebold–Mariano result |

Note: in `S2`, the panel titles use x₂,t and x₃,t for the series called m_t (10-year yield)
and n_t (VIX) in the paper.

### Tables (`Tables/`)

| File | Paper reference | Shows |
|---|---|---|
| `TableS1_walkforward_folds.jpg` | Section 6.2 | Per-fold walk-forward results (four expanding-window folds) |
| `TableS2_methodological_comparison.jpg` | Section 7.2 | Methodological comparison with ARIMA/ARDL, STR, ARIMA–ANN hybrids and standalone KAN |

## Data

Raw data are not redistributed here; please download them from the original sources.

- **NASDAQ study (2000-01-03 to 2024-12-31, N = 6,243):** NASDAQ Composite (`NASDAQCOM`),
  10-year Treasury constant-maturity yield (`DGS10`) and CBOE Volatility Index (`VIXCLS`),
  all from FRED: https://fred.stlouisfed.org
- **Wind-farm application:** Kelmarsh wind farm SCADA data (six Senvion MM92 turbines,
  10-minute records, 2022–2023), CC-BY-4.0: https://zenodo.org/records/16807551

## Headline results (as reported in the paper)

- NASDAQ hold-out (chronological 80/20): RMSE 0.01138 for ARDL against 0.01063 for the
  hybrid, a 6.59% reduction; HLN-corrected Diebold–Mariano statistic 2.798 (p = 0.0052).
- Monte Carlo (120 replications per setting): no gain on the linear control, mean gains of
  10.85%–43.13% as nonlinearity strengthens.
- Kelmarsh wind farm: 34.8%–37.0% RMSE reduction with contemporaneous drivers, but only
  0.29%–0.52% with lagged drivers. The gains depend on contemporaneous information.

## Citation

If you use this material, please cite the paper:

```
Mazin Mohammed, Dibu A.S. and Sathya P.: A Regime-Gated Hybrid Forecasting Framework:
Coupling Autoregressive Distributed Lags, Smooth-Transition Dynamics, and
Kolmogorov–Arnold Residual Learning. <conference name, proceedings, year, pages/DOI>
```

## License

The figures and tables in this repository are released under the
[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
license. You may share and adapt them, including commercially, provided you give appropriate
credit to the authors. No source code is included in this repository.
