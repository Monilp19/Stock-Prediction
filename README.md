Stock Movement Prediction System
It does not contain any insights or any other source, it is an ML based Project which is trained on a large dataset from past years. It does not take or predict stocks which are new to stock market. Model is trained and tested with the dataset and only predicts the movement of stock, it can not be always true, Model can predict wrong decisions because it not real time model and trained on Past History of that particular stock.

A machine learning-based stock market analysis and prediction system that forecasts next-day price movement directions (`UP`, `DOWN`, `SIDEWAYS`). This project leverages supervised machine learning classification algorithms trained on historical price indicators and volume patterns to provide quantitative trading insights. It features both a powerful command-line interface (CLI) and an interactive web dashboard built with Flask.

---

## 🚀 Key Features

* **Multi-Algorithm Support:** Uses `Random Forest`, `Logistic Regression`, `Decision Tree`, and `Gradient Boosting` models.
* **Feature Engineering:** Computes technical indicators including rolling moving averages, daily returns, historical volatility, MACD, RSI, and Bollinger Bands.
* **Backtesting Engine:** Simulates historical predictions to evaluate model performance over test data.
* **Interactive Dashboard:** Futuristic web UI with model accuracy comparison, live TradingView charts, prediction probability distribution, confusion matrix, and feature importances.
* **Flexible Input:** Supports global tickers (e.g. `AAPL`) and Indian NSE/BSE stocks (e.g. `TCS.NS`, `RELIANCE.NS`) via the Yahoo Finance API.

---

## 📁 Repository Structure

```text
stock-movement-prediction/
│
├── static/                 # Web app assets (custom CSS & UI styles)
├── templates/              # HTML layout for the Flask dashboard
├── app.py                  # Flask web server & prediction backend API
├── stockmarket.py          # Interactive CLI for yfinance-based prediction
├── stocks.py               # Model training script for local CSV datasets
├── test_accuracy.py        # Model benchmarking & parameter tuning utility
├── requirements.txt        # Production dependencies
├── README.md               # Project documentation
└── .gitignore              # Standard git exclusion configurations
```

---

## 🛠️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/stock-movement-prediction.git
   cd stock-movement-prediction
   ```

2. **Set up a virtual environment (recommended):**
   ```bash
   # Create a virtual environment
   python -m venv venv
   
   # Activate on Windows (cmd/PowerShell)
   venv\Scripts\activate
   
   # Activate on macOS/Linux
   source venv/bin/activate
   ```

3. **Install the dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

---

## 💻 Usage

### 1. Interactive CLI Prediction (`stockmarket.py`)
Run the terminal-based predictor to download recent historical data for any ticker, train a model, and print immediate next-day predictions:
```bash
python stockmarket.py
```
* **Example tickers:** `AAPL` (Apple), `TCS.NS` (Tata Consultancy Services), `INFY.NS` (Infosys), `RELIANCE.NS` (Reliance Industries).

### 2. CSV-based Local Model Training (`stocks.py`)
Train and evaluate baseline model configurations using a local historical CSV data file (e.g. `RELIANCE1.csv`):
```bash
python stocks.py
```

### 3. Model Tuning & Benchmarking (`test_accuracy.py`)
Benchmark different parameters (features, decision thresholds, algorithm hyperparameters) to find the configuration with the highest accuracy:
```bash
python test_accuracy.py
```

### 4. Running the Web Application (`app.py`)
Launch the interactive web dashboard:
```bash
python app.py
```
Open your browser and navigate to `http://127.0.0.1:5000` to interact with the dashboard.

---

## 🤖 Machine Learning Details

### Feature Engineering
* **Daily Returns:** Captures short-term momentum.
* **Moving Averages (MA):** Computes rolling averages to smooth out price noise.
* **Volume Ratio:** Normalizes trading volume against its 5-day rolling average.
* **Advanced Features (used in `test_accuracy.py`):** Includes RSI, MACD, Bollinger Bands, and Rolling Volatility.

### Target Classification
The target label is next-day price movement based on a return threshold:
* **`UP`**: Next-day return exceeds $+0.5\%$ (threshold configurable)
* **`DOWN`**: Next-day return falls below $-0.5\%$
* **`SIDEWAYS`**: Next-day return remains within $[-0.5\%, +0.5\%]$

---

## ⚠️ Disclaimer
This system is created for **educational and research purposes only** and does not constitute financial advice. Algorithmic stock predictions contain high uncertainty. Do not use this tool for live trading or financial decision-making without consulting a licensed advisor.
