# Project-1
## Overview
Perform portfolio analysis on Stocks, ETFs and S&P 500 and Dow Jones indexes to compare to Bitcoin historical prices to determine whether Bitcoin is a better investment or not. 
Used Yahoo Finance and CoinGecko APIs to compare 5 Mutual funds and ETFs and compare it to S&P 500 and Dow Jones indexs. Run Monte Carlo simulations on portfolio analysis.
Perform portolio analysis on Virtual Currency compared to Stocks performance and use monte carlo simulations.
Compare volatility for virtual currency against stock market indexs and individual stocks. Use Monte Carlo simulations to show how volatile virtual currency is compated to the US Stock Market is and show that Virtual Currency is actually a good investment or not a good investment.

## Project objective

Our objective is to assess viability of Bitcoin/(digital currency) as an investment and compare its historical performance and volatility to the broader stock market. 

Pull historical performance of Bitcoin.

Pull historical performance of major stock market indices (SP500, DJIA, & Nasdaq) and high performing stocks

Examine and compare historical returns and volatility of indices and Bitcoin.

Forecast and compare future performance of indices & Bitcoin using Monte Carlo Simulations.

### Libraries Used
OS library
Requests Library
Pandas Library
Numpy Library
Yahoo Finance API through PyPi (No Key Needed)
[pypi_yahoo_finance](https://pypi.org/project/yahoo-finance/)
Json Library
CoinGeckoAPI (No Key Needed)
[CoinGeckoAPI](https://www.coingecko.com/en/api)
DateTime Library
Alpaca Trade API(Key Needed)
Monte Carlo Simulations (MCForecastTools, MCSimulation)
Path Library
HV Plot Library
Matplotlib PyPlot Library
DotENV Variable

### Jupyter Notebooks used
##### data_prep.ipynb (pyvizenv) 
Import historical stock prices for Apple (AAPL), Amazon(AMZN), Microsoft (MSFT), S&P 500 (SPY), Dow Jones Index (DIA), QQQ Trust Series Fund (QQQ) using the Yahoo Finance API and exported the historical prices into individual csv files.
Downloaded BitCoin(BTC) historical prices using the CoinGeckoAPI and dowloaded to csv file.

##### BTC_Equity_Comparison.ipynb
Imported CSV files into a combined dataframe.
Calculated the daily returns and plot them.
Assessed the volatility of BTC compared to the stocks and ETFs.
Run the standard deviations of each investment and plot them.
Plot the standard deviation of all of the investments and plot them in one graph.

Compared the first 3000 days of each investment and compare the volatility.

##### BTC_Equity_MC_Forecast
Using the Alpaca API to import the prices of the all the investments to run Monte Carlo simulations
Plotted the Cumulative Return for each portfolio.
Summarized the Monte Carlo forecast results to determine what each investment maybe worth.
