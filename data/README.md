# Data Directory
This folder contains the raw and processed data used for the ML-Driven-Sector-ETF-Prediction project using LightGBM.
It includes historical ETF Price Data, Model Evaluation Summaries, and Risk Analysis Outputs.

## Contents

| File | Description |
|------|-------------|
| `sp500_sector_prices.csv` | Raw closing price data for major sector ETFs and SPY from 2008–2025, sourced via `yfinance`. |
| `sector_model_summary.csv` | Model evaluation metrics (R², RMSE, MAE) for each sector-specific LightGBM model. |
| `lgbm_risk_summary.csv` | Annual return, volatility, and Sharpe ratio for each sector ETF, computed from historical returns. |
| `.gitkeep` | Keeps this directory under version control even if empty. |

## Additional Data Sources

The following macroeconomic indicators are downloaded during data processing:

-> **VIX** (Volatility Index): Represents the market volatility expectations over the next 30 days.
  - *Source*: `^VIX` from Yahoo Finance during the execution of the sector_data_collection notebook.
  - *Period*: 2008-2025
  - *Purpose*: Used for volatility based features, such as the VIX z-score.

-> **TNX** (10-Year Treasury Yield): Represents the yield on the United State's 10-year government bonds.
  - *Source*: `^TNX` from Yahoo Finance during the execution of the sector_data_collection notebook.
  - *Period*: 2008-2025
  - *Purpose*: Used for risk-free ratio and yield-based features.

## Notes

- All `.csv` files are generated from the pipeline defined in the `notebooks/LGBM_Sector_Prediction/` notebook.
- Files are updated everytime the pipleine is rerun.

## Related Information

- Plots generated from this data are stored in the `plots/` directory.
- Code used to generate this data is available in the `notebooks/` directory.
