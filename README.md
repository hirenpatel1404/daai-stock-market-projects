# DAAI Stock Market Projects (1–3)

Coursework for the **Data Analytics & AI (DAAI)** diploma — a three-part project analysing and modelling the *Daily Historical Stock Prices (1970–2018)* dataset. Each project builds on the previous one:

| Project | Focus | What it does |
|---------|-------|--------------|
| **Project 1** | Exploratory Data Analysis (EDA) | Load, clean and explore the data; summary statistics; visualisations; investigate unusual values |
| **Project 2** | Data Preparation & Feature Engineering | Clean the data, create features (returns, moving averages, volatility, volume features), merge the datasets, one-hot encode, and save a model-ready dataset |
| **Project 3** | Machine Learning | Build MACD & RSI indicators, create Buy/Sell/Hold trading signals, and train models (Logistic Regression, Random Forest, SVM) to predict them |

---

## Repository contents

| File | Description |
|------|-------------|
| `Stock_Market_Data_Part_1.ipynb` | Project 1 notebook — EDA |
| `Stock_Market_Data_Part_2.ipynb` | Project 2 notebook — data preparation & feature engineering |
| `Project3_Hiren.ipynb` | Project 3 notebook — technical indicators & machine learning |
| `Project1_Hiren.docx` | Project 1 technical report |
| `Project2_Hiren.docx` | Project 2 technical report |
| `Project3_Hiren.docx` | Project 3 technical report |
| `README.md` | This file |

> **Note:** the raw data files and the prepared dataset are **not included** in this repository because they are too large for GitHub (up to ~2 GB). See **How to get the data** below.

---

## How to get the data

The project uses the **Daily Historical Stock Prices (1970–2018)** dataset from Kaggle:

- https://www.kaggle.com/datasets/ehallmar/daily-historical-stock-prices-1970-2018

Download and unzip it to get two files:
- `historical_stock_prices.csv` — daily prices (ticker, open, close, adj_close, low, high, volume, date)
- `historical_stocks.csv` — company info (ticker, exchange, name, sector, industry)

Place both CSVs in the same folder as the notebooks.

`stock_prepared.csv` (the output of Project 2) is re-created by running the Project 2 notebook, and is the input for Project 3.

---

## How to run the notebooks

1. Install Python 3 with the usual data libraries:
   ```
   pip install pandas numpy matplotlib scikit-learn plotly
   ```
2. Open the notebook in **Jupyter Notebook** (recommended for the large files) or **Google Colab**.
3. Make sure the CSV files are in the same folder as the notebook.
4. Run the cells top to bottom (**Kernel → Restart & Run All**).

**Order:** run Project 1 → Project 2 (this creates `stock_prepared.csv`) → Project 3 (this uses `stock_prepared.csv`).

> The full dataset is ~21 million rows, so some cells are memory-heavy. A machine with 16 GB+ RAM (or local Jupyter) is recommended over the free Colab tier.

---

## Key findings (short version)

- **Project 1:** the data is right-skewed — most stocks are low-priced with a few very expensive ones; extreme values were investigated and kept, not deleted.
- **Project 2:** built normalized features (returns, moving averages, volatility, relative volume) and a clean, model-ready dataset.
- **Project 3:** the trading signal is extremely imbalanced (~99.9% Hold). Models could be pushed to catch the rare Buy/Sell signals, but always with very low precision — showing that these rule-based signals are hard to predict from price features alone. Random Forest was the strongest model. These predictions are a classification exercise, **not** financial advice.

---

*Author: Hiren Patel — Willis College, DAAI diploma.*
