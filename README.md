# Finance & Economics Time-Series Analysis

TCH Bootcamps: Data Science group project at NYU, Fall 2026.

We study how financial markets and the US economy affect each other, and we try to forecast where they go next. The data covers stock indices (Dow Jones, S&P 500, NASDAQ) and macroeconomic indicators like GDP growth, inflation, interest rates, unemployment and consumer spending.

## Goals

- Explore the data and find missing values, anomalies and outliers
- Clean it and line up indicators that come out daily, monthly and quarterly
- Build features like returns, moving averages, volatility and lags
- Find relationships between indicators with correlation and cross-correlation analysis
- Forecast key indicators with baseline ML models, VAR and LSTM/GRU
- Compare models using MAE, RMSE and MAPE
- (Optional) Build an interactive dashboard to explore the data and forecasts

## Dataset

**Provided dataset:** `finance_economics_dataset.csv` (Kaggle), 3,000 daily rows from 2000-01-01 to 2008-03-18, 24 columns.

**Note:** our first look shows the provided dataset is synthetic. The values are uniformly random, the columns are basically uncorrelated (max correlation about 0.05), and index prices don't match real history. So we also build a real version of the same dataset:

**Real dataset:** `scripts/build_finance_dataset.py` pulls actual data from 2000 to today, using the same column names.

| Source | Columns |
|---|---|
| Yahoo Finance (`yfinance`) | Index OHLC and volume, gold price |
| FRED (St. Louis Fed) | GDP growth, inflation (CPI YoY), unemployment, fed funds rate, consumer sentiment, federal debt, corporate profits, USD/EUR, USD/JPY, WTI oil, Case-Shiller home price index, retail sales, consumer spending (PCE) |

Bankruptcy rate, M&A deals and VC funding have no free public source, so those columns are left empty in the real dataset.

## Project Structure

```
.
├── data/
│   ├── raw/              # original Kaggle CSV (not committed)
│   └── processed/        # cleaned and merged data (not committed)
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_cleaning_preprocessing.ipynb
│   ├── 03_eda.ipynb
│   ├── 04_feature_engineering.ipynb
│   ├── 05_baseline_models.ipynb
│   ├── 06_var_model.ipynb
│   ├── 07_lstm_gru_models.ipynb
│   └── 08_evaluation.ipynb
├── scripts/
│   └── build_finance_dataset.py
├── src/                  # reusable functions (features, models, plots)
├── dashboard/
│   └── app.py            # Streamlit app (optional)
├── reports/
│   └── figures/
├── requirements.txt
└── README.md
```

## Getting Started

```bash
git clone https://github.com/Danny-0803/TCH_Bootcamps_Data_Science_Group_Project.git
cd TCH_Bootcamps_Data_Science_Group_Project

python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Get the data:

1. Download the Kaggle CSV and put it in `data/raw/`
2. Build the real dataset:

```bash
python scripts/build_finance_dataset.py
```

Data files aren't committed to the repo, so everyone needs to run these steps once.

## Tech Stack

- Python, pandas, NumPy
- Matplotlib, Seaborn, Plotly
- statsmodels (decomposition, VAR, ARIMA)
- scikit-learn (baseline models)
- TensorFlow/Keras or PyTorch (LSTM/GRU)
- Streamlit (dashboard)

## Timeline

| Week | Focus |
|---|---|
| 1 | Data understanding and cleaning |
| 2 | Exploratory data analysis |
| 3 | Feature engineering and first models |
| 4 | Mid-program presentation |
| 5 | Model evaluation |
| 6 | Visualization and insights |
| 7-8 | Dashboard (optional) and documentation |
| 9 | Final presentation |

## How We Work

- Don't push straight to `main`. Make a branch, e.g. `eda-correlations` or `var-model`
- Open a pull request and get one teammate to look at it before merging
- Clear notebook outputs before committing if they're huge
- Put reusable code in `src/` instead of copying it between notebooks

## Team

| Name | GitHub | Role |
|---|---|---|
| Devansh (Danny) Sharma | [@Danny-0803](https://github.com/Danny-0803) | |
| | | |
| | | |
| | | |

## Results

Coming soon.
