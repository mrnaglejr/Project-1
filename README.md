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
Calculated the individual daily returns of each investment and plot them.
[Comparison_of_Daily_Returns](images/daily_returns_full.png)

Calculated the cumulative daily returns of all the investments
[Comparison_of_Cumulative_Returns](images/cumulative_returns_full.png)

Assessed the volatility of BTC compared to the stocks and ETFs.
[Assessed_Volatility](images/box_plot_full.png)

Run the standard deviations of each investment and plot them with hvplot drop downs
[hvplot_stddev](images/vol_comp_widget_full.png)
Plot the standard deviation of all of the investments and plot them in one graph.
[hvplot_stddev_all](images/vol_comp_full.png)
Compared the first 3000 days of each investment and compare the volatility.
[daily_returns_first3000](images/daily_returns_first3000.png)
[cumulative_returns_first3000](images/cumulative_returns_first3000.png)

Assess volatility across first 3000 trading days
[box_plot_first3000](images/box_plot_first3000.png)
Create the standard deviation visualization for each of investments for the first 3000 trading days
[std_dev_first3000](images/vol_comp_widget_first3000.png)
Create the standard deviation visualiztion for all of the investments for the first 3000 trading days
[std_dev_first3000_all](images/vol_comp_first3000.png)

##### BTC_Equity_MC_Forecast (need to run in python environment)
Using the Alpaca API to import the prices of the all the investments to run Monte Carlo simulations
Plotted the Cumulative Return for each portfolio.
Summarized the Monte Carlo forecast results to determine what each investment maybe worth.
[Monte_Carlo_sim_results](images/fcst_summ_stats.png)
[Monte_Carlo_results](images/fcst_ci_median_summ.png)