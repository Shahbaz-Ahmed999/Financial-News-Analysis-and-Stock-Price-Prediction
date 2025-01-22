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

## TASK 2 Stock Ticker Extraction

**Goal:**  
*To extract company names or stock tickers from news articles, map the extracted company names to their respective stock tickers using an API or reliable dataset. A dataset from Kaggle (S&P 500 companies) is downloaded, providing a list of stock tickers with corresponding company names.*

---

### Data Collection
- **News Sources:**
  - News headlines and descriptions are loaded from `reuters_headlines.csv`.
  - A dataset of S&P 500 companies (`sp500_companies.csv`) is used as the mapping source.

### Named Entity Recognition (NER)
- **Model Used:**
  - SpaCy’s NER model is utilized to extract organization names from article descriptions.
- **Data Cleaning:**
  - Extracted names are cleaned to remove possessives, brackets, and quotes.

### Mapping to Tickers
- **Mapping Process:**
  - Extracted company names are mapped to S&P 500 tickers using a dictionary that includes both short and long company names.
- **Fuzzy Matching:**
  - Fuzzy matching (via `rapidfuzz`) ensures accurate mapping even with slight variations in company names.

### Final Output
- **Filtered Articles:**
  - Articles are filtered to retain only those with successfully matched tickers.
- **Resulting Dataset:**
  - The resulting dataset includes **headlines**, **descriptions**, **extracted company names**, **matched company names**, and **stock tickers**.

### Install Required Libraries
Ensure you have the necessary Python libraries installed:

pip install pandas spacy rapidfuzz
python -m spacy download en_core_web_sm

### Task 3: Financial Data Retrieval

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

**Objective:** The task is to forecast stock prices for a specified future time period (e.g., the next 7 days) using historical data. The goal is to build a predictive model using an LSTM (Long Short-Term Memory) neural network, evaluate its performance using metrics like RMSE and MAE, and visualize the forecast alongside historical data.

**Approach:**

**Data Collection:** Historical stock data is fetched using the yfinance library for a specific ticker symbol (MSFT) starting from 2018.
Key columns like Open, High, Low, Close, and Volume are used.

**Preprocessing:** Data is normalized using MinMaxScaler to bring all features to a common scale, essential for LSTM performance.
Multi-step time-series data is prepared by creating sequences of past prices (X) to predict multiple future closing prices (y).

**Model Design and Training:** 
A multi-layer LSTM model is built to capture time-dependent patterns in the data.
The model is trained on 80% of the data, while the remaining 20% is used for testing.

**Evaluation:** Predictions are compared with actual prices for each step in the forecast horizon.
Metrics such as RMSE (Root Mean Squared Error) and MAE (Mean Absolute Error) are calculated for each step.

**Visualization:** Historical data is visualized to understand trends.
Predicted vs. actual prices are plotted for individual steps and all steps together to assess model accuracy.

**Steps to Execute the Code:**
**Install Required Libraries:** Ensure that you have all required libraries installed. Use the following command if needed:
pip install numpy pandas yfinance matplotlib seaborn tensorflow scikit-learn

**Fetch Stock Data:** The get_stock_data function fetches historical stock data for the specified ticker (MSFT) and start date.

**Visualize Historical Data:** Use Seaborn and Matplotlib to plot the closing price and trading volume over time.

**Preprocess the Data:** Normalize the data using MinMaxScaler.
Split the data into training and testing sets (80% for training).
Prepare input (X) and output (y) sequences for multi-step forecasting.

**Build and Train the Model:** Define the LSTM model using the Sequential API in Keras.
Train the model using the prepared data.

**Make Predictions:** Predict future prices for the test set.
Inverse-transform the scaled predictions to get actual price values.

**Evaluate the Model:** Compute RMSE and MAE for each forecast step.

**Visualize the Results:** Plot the actual vs. predicted prices for individual steps.
Overlay all forecast steps for a comprehensive visualization.

**Interpret Results:** Analyze the model's performance and identify areas for improvement.

