# Financial-News-Analysis-and-Stock-Price-Prediction

Project Overview

This project analyzes financial news articles and their impact on stock price prediction. The tasks include performing exploratory data analysis (EDA), extracting stock tickers using NLP, retrieving financial data, forecasting stock prices, and correlating news content with stock performance.

# Dataset
The dataset used in this project consists of financial news articles.

Download the reuters.headlines file from the following link:
https://www.kaggle.com/datasets/notlucasp/financial-news-headlines?select=reuters_headlines.csv

# Requirements
**pandas , numpy,  matplotlib,  nltk,  spacy, scikit-learn,  yfinance,  statsmodels,  tensorflow,  requests,  tqdm**

# Task 1: Exploratory Data Analysis (EDA)

**Objective**: Perform EDA on financial news headlines and descriptions to understand the dataset and identify key trends.

Steps

**Load Dataset:** Place the reuters_headlines.csv file in the appropriate directory and load it using Pandas.

file_path = r"C:\Users\SHAHBAZ\Desktop\reuters_headlines.csv"
reuters_df = pd.read_csv(file_path)

**Clean Dataset:** Remove duplicates and handle invalid values in the Time column.

**Visualize Trends:** Create a line plot of the number of articles over time.

Analyze word frequency and generate a word cloud.

**Output:** Summary statistics and cleaned dataset stored in a DataFrame.

Visualizations saved or displayed inline.

# Task 2: Stock Ticker Extraction

**Objective:** Extract company names mentioned in financial news descriptions, clean them, and map them to stock tickers.

Steps

**Load Dataset:** Use the cleaned data from Task 1.

**Company Name Extraction:** Use spaCy to extract organization entities (ORG) from the descriptions.

Clean and filter company names.

**Map to S&P 500 Tickers:** Load sp500_companies.csv containing company names and their stock tickers.

Use fuzzy matching to map extracted names to valid tickers.

**Save Output:** Save the matched tickers in unique_stock_companies.csv for the next task.

# Task 3: Financial Data Retrieval

**Objective:** Retrieve key financial metrics and historical stock prices for identified companies.

Steps

**Load Dataset:** Read unique_stock_companies.csv for stock tickers.

**Fetch Financial Metrics:** Use Yahoo Finance API to retrieve market capitalization and P/E ratio.

Store results in a DataFrame.

**Fetch Historical Prices:** Retrieve the past year’s daily closing prices for all tickers.

**Save Outputs:** Save financial metrics in stock_financial_data.csv.

Save historical prices in historical_prices.csv.

**Visualizations:** Create line plots for historical stock prices.

Display metrics distributions (e.g., market capitalization).

# Task 4: Stock Price Prediction

**Objective** Build an LSTM model to predict multi-step future stock prices based on historical data.

Steps

**Fetch Data:** Use Yahoo Finance API to retrieve historical stock data for the chosen ticker (e.g., MSFT).

**Visualize Data:** Plot closing prices and trading volumes over time.

**Data Preparation:** Normalize data using MinMaxScaler.

Prepare multi-step input-output pairs for LSTM.

**Train-Test Split:**

Use 80% of data for training and 20% for testing.

**Build LSTM Model**

Use TensorFlow/Keras to construct and train an LSTM model.

Include dropout layers for regularization.

**Evaluate Model:**

Calculate RMSE and MAE for predictions.

Visualize actual vs. predicted prices for different forecast steps.

