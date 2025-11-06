# Stock Price Prediction Model

This project uses a simple Linear Regression model to predict future stock closing prices based on historical data. The Python script provides an interactive menu to analyze different stock datasets.

Project Files

model5.py: The main Python script that contains the logic for:

Loading and preparing the stock data.

Engineering new features (like moving averages).

Training a Linear Regression model.

Evaluating the model's performance (MSE, R², MAPE).

Plotting the actual vs. predicted stock prices.

Amazon.csv: Historical stock price data for Amazon (AMZN).

GOOGL.csv: Historical stock price data for Google (GOOGL).

TSLA.csv: Historical stock price data for Tesla (TSLA).

How to Use

Prerequisites:

Ensure you have Python installed.

Install the required libraries:

pip install pandas scikit-learn matplotlib


Run the Script:

Place model5.py, Amazon.csv, GOOGL.csv, and TSLA.csv in the same directory.

Open your terminal or command prompt and navigate to that directory.

Run the script:

python model5.py


Analyze:

The script will present a menu.

Enter the number corresponding to the stock you wish to analyze (1 for Tesla, 2 for Amazon, 3 for Google).

The script will output the model's performance metrics and display a plot of the results.

Enter 'q' to quit.

Disclaimer


This project is for educational purposes only. The linear regression model used is very simple and should not be used for real-world financial advice or trading.
