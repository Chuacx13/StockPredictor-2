# Stock Prediction Using PyTrends and Global Market Data

## Project Overview

- **Objective**:
  This project aims to predict the price change of the S&P 500 index by incorporating:

1. The relative interest of "bullish" and "bearish" search term from Google Trends data.
2. The price changes in other global markets that opens before the U.S. market.

The predictions generated by the model can be used to make informed decisions about whether to take a long or short position.

- **Data Sources**:

  - **Google Trends**: Extracts data on the relative interest levels of bullish and bearish search terms on Google, to gauge market sentiment.
  - **Yahoo Finance**: Price changes from key global markets that are opened before the U.S. market, providing an early indication of potential movements in the S&P 500.

- **Model**:

  - **PyTorch's LSTM**: LSTMs are effective in sequence prediction tasks and in capturing long-range dependencies, potentially providing more accurate predictions.

- **Backtesting**:
  - The model's performance is evaluated using backtesting metrics such as the **Sharpe Ratio** and **Maximum Drawdown** to assess risk-adjusted returns and potential losses over time.

## File Overview

- **SetUpParams.ipynb**: This notebook downloads the necessary market data from yfinance.

- **IncludePyTrendsData.ipynb**: This extracts and processes relative interest of the "bullish" and "bearish" terms over time from Google Trends.

- **DataProcessing.ipynb**: This notebook handles the preprocessing of raw data. It includes steps such as data cleaning, data exploration, train-test split and normalization.

- **Predictions.ipynb**: This notebook handles training of the LSTM model. From hyperparameter tuning (cross-validation) to evaluating the model on Mean-Squared Error and Mean Absolute Percentage Error. Finally, it makes predictions on unseen test data.

- **CalcProfits.ipynb**: This is the notebook that calculates the profits generated by the model's predictions. It decides on whether to long or short the stock based on predictions made by the model and the Bollinger Bands Strategy. Additionally, it also compares the profitability of the strategy with a Buy-and-Hold strategy. Lastly, the trading strategy is backtested on Sharpe Ratio and Max Drawdown.

- **model_state_dict.pth**: This file stores the trained model's state dictionary, which contains the weights and biases of the model after training.

- **requirements.txt**: This text file lists the Python libraries and dependencies required to run the notebooks in this project.

## Results

![Profit Over Time Graph](https://github.com/Chuacx13/StockPredictor-2/blob/main/image/Long-and-Short_Strat_vs_Buy-and-Hold_Strat_Graph.png)

- **Yearly Sharpe Ratio**: ~0.88
- **Maximum Drawdown**: ~0.14

## Limitations

- **Data Limitations**:

  - Google Trends data are subjected to noise and may not fully capture market sentiment.

- **Market Conditions**:

  - The model may perform differently under varying market conditions (e.g., during periods of high volatility or low liquidity).

- **Bid-Ask Spread**:

  - The model does not take into account the potential losses that the Bid-Ask spread can cause to the trading strategy's profits.

## Installation

Clone the repository using the following command:

```bash
git clone git@github.com:Chuacx13/StockPredictor-2.git
```

Ensure that you are in the right directory by using the following command:

```bash
cd StockPredictor-2
```

Install these dependences by using the following command:

```bash
pip install -r requirements.txt
```

Note: Running only CalcProfits.ipynb runs the entire project from collecting data to training the model to generating predictions to backtesting the model.
