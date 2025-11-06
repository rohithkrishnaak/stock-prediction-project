# Stock Prediction Project
A simple stock price prediction demo using a linear regression model in Python. This repository contains example CSVs (TSLA, Amazon, GOOGL), a single analysis script (model5.py), and a requirements.txt to reproduce the environment.

## Project overview
This project demonstrates a straightforward workflow to:
- Load historical stock price CSVs,
- Engineer simple time-series features (moving averages, volatility, range),
- Train a Linear Regression model to predict the next day's closing price,
- Evaluate model performance (RMSE, MAPE, R²),
- Visualize actual vs predicted prices.

Intended as an educational example rather than a production-ready forecasting pipeline.

## Requirements
- Python 3.8+ recommended
- The repository includes a requirements.txt — install dependencies with:
  pip install -r requirements.txt

If you prefer to install only the libraries used by model5.py:
- pandas
- numpy
- scikit-learn
- matplotlib

## Installation
1. Clone the repository:
   git clone https://github.com/rohithkrishnaak/stock-prediction-project.git
2. Change directory:
   cd stock-prediction-project
3. Create a virtual environment (optional but recommended):
   python -m venv venv
   source venv/bin/activate  # macOS / Linux
   venv\Scripts\activate     # Windows
4. Install dependencies:
   pip install -r requirements.txt

## Usage
From the repository root run:
python model5.py

The script launches a simple text menu:
- 1: Analyze Tesla (TSLA.csv)
- 2: Analyze Amazon (Amazon.csv)
- 3: Analyze Google (GOOGL.csv)
- q: Quit

Selecting a company will:
- Load the respective CSV,
- Compute features,
- Train a linear regression on the first 80% of the chronological data,
- Evaluate on the remaining 20%,
- Print model intercept and coefficients,
- Print RMSE, MAPE, and R²,
- Display a plot comparing actual vs predicted prices.

Note: model5.py expects CSV files to be present in the same directory (they are included in the repo).

## How the model works (brief)
- Target: next-day close price (Close shifted by -1).
- Features: Open, High, Low, Close, Volume, 7-day MA, 30-day MA, 7-day Std, Range (High - Low).
- Split: chronological 80% train / 20% test (no shuffling).
- Model: sklearn.linear_model.LinearRegression (ordinary least squares).
- Metrics: RMSE, MAPE, R².
- Visualization: matplotlib plot of actual vs predicted prices for the test partition.

## Dataset
Included example CSV files:
- TSLA.csv
- Amazon.csv
- GOOGL.csv

Each CSV is expected to contain at least the columns: Date, Open, High, Low, Close, Volume.

## Training & Evaluation notes
- The script trains a new model each time you run an analysis for a company.
- Because features include the unscaled price columns, linear regression coefficients are in price units — consider standardizing if comparing coefficient magnitudes or using regularization.
- Model evaluation is reported on the chronologically last 20% — appropriate for time-series holdout, but consider cross-validation strategies designed for time-series (e.g., expanding window) for more robust assessment.

## Results (expected)
- The baseline linear regression typically produces a simple baseline forecast. Expect relatively high errors for volatile stocks; metrics printed by the script (RMSE, MAPE, R²) quantify performance.
- The model prints the intercept and coefficients so you can inspect feature impacts.

## File structure
- .gitignore
- README.md
- requirements.txt
- model5.py        — main script; menu-driven CLI and analysis function
- TSLA.csv
- Amazon.csv
- GOOGL.csv

## Contributing
Contributions and suggestions are welcome. Suggested workflow:
- Fork the repo
- Create a feature branch
- Open a pull request describing changes

