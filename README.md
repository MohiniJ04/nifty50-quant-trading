# NIFTY 50 Quantitative Trading System (5-Minute Intraday)

## Project Overview

This project demonstrates the development of a **quantitative trading system** using **5-minute NIFTY 50 spot data**.  
The system covers the following components:

- **Data acquisition and cleaning**  
- **Feature engineering** (EMAs, returns, volatility, lag features, time features)  
- **Regime detection** (trend classification using EMA-based rule)  
- **Baseline trading strategy** (EMA crossover with regime filter)  
- **Machine Learning enhancement** (XGBoost & LSTM for trade profitability prediction)  
- **Outlier trade analysis** (statistical and time-of-day analysis of high-impact trades)  

The project demonstrates technical skills in **Python, Pandas, NumPy, ML modeling, and financial data analysis**, and is suitable for interview discussions.

---

## Installation Instructions

1. Clone the repository:
```bash
git clone https://github.com/<your-username>/nifty50-quant-trading.git
cd nifty50-quant-trading

2. Install required Python packages:
pip install -r requirements.txt

->> Project Structure

nifty50-quant-trading/
├── data/
│   ├── NIFTY 50_minute.csv           # Raw minute-level spot data
│   ├── nifty_spot_5min.csv           # Resampled 5-minute OHLCV
│   ├── nifty_cleaned_5min.csv        # Cleaned dataset
│   └── nifty_features_5min.csv       # Features for strategy & ML
├── notebooks/
│   ├── 01_data_acquisition.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_regime_detection.ipynb
│   ├── 05_baseline_strategy.ipynb
│   ├── 06_ml_models.ipynb
│   └── 07_outlier_trade_analysis.ipynb
├── results/
│   ├── baseline_backtest.csv
│   ├── ml_predictions.csv
│   └── outlier_trades.csv
├── requirements.txt
└── README.md

->>Workflow Summary
1. Data Acquisition & Resampling
~Loaded NIFTY 50 minute data
~Resampled into 5-minute OHLCV candles
2. Data Cleaning
~Forward-filled missing candles
~Removed extreme outliers (IQR method)
3. Feature Engineering
~EMA(5), EMA(15)
~Returns, EMA gap, volatility, candle body/range
~Time-based and lag features
4. Regime Detection
~Rule-based regime classification (+1: Uptrend, -1: Downtrend, 0: Sideways)
~Threshold applied to reduce noisy switches
5. Baseline Strategy & Backtest
~EMA crossover strategy filtered by regime
~Metrics computed: Total return, Sharpe ratio, max drawdown, win rate
6. Machine Learning Enhancement
~XGBoost: Non-linear feature interactions for profitable trade prediction
~LSTM: Sequence modeling using last 10 candles
~Only trades with predicted probability > 0.5 executed
7. Outlier Trade Analysis
~Identified trades with Z-score > 3
~Analyzed regime, volatility, time-of-day
~Highlighted trades contributing disproportionately to PnL

How to Run
1.Open Jupyter Notebook:
Run notebooks sequentially:

01_data_acquisition.ipynb

02_data_cleaning.ipynb

03_feature_engineering.ipynb

04_regime_detection.ipynb

05_baseline_strategy.ipynb

06_ml_models.ipynb

07_outlier_trade_analysis.ipynb

Check results/ folder for backtest, ML predictions, and outlier analysis outputs.

Author
~ Mohini Jakhar
Email: jakharmohini04@gmail.com


