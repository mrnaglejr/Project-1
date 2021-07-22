# *Project: Assess Viability of Bitcoin as an Investment*

## **Objective**

Our objective was to assess the viability of Bitcoin as an investment, particularly in relation to the broader equity market. To assess this, we wanted to answer the following questions:

- *How does Bitcoin price performance and volatility compare to equity markets?*

- *How does Bitcoin's price performance and volatility compare to early price performance and volatility of high-performing stocks and indices? Is Bitcoin an outlier?*

- *Is Bitcoin a good investment for the future?*

## **Analysis Overview** 

Our analysis consisted of a comparison of Bitcoin's historical price performance and volatility to 3 ETF's (SPY, DIA, QQQ) and 3 high-performing stocks (AAPL, AMZN, MSFT):

 - [SPY](https://www.investopedia.com/articles/investing/122215/spy-spdr-sp-500-trust-etf.asp): ETF that tracks the S&P 500 (500 large and mid-cap U.S. stocks)

 - [DIA](https://www.ssga.com/us/en/institutional/etfs/funds/spdr-dow-jones-industrial-average-etf-trust-dia): ETF that tracks the Dow Jones Industrial Average (30 'blue chip' U.S. stocks)

 - [QQQ](https://www.invesco.com/us-rest/contentdetail?contentId=3a48e01e98630410VgnVCM10000046f1bf0aRCRD&dnsName=us&audienceType=investors): ETF that tracks the Nasdaq 100 (top 100 non-financial stocks in Nasdaq)

Our rationale for using a mix of ETF's and individual stocks was to capture both the general trend of the broader equity market, as well as the peaks and valleys of top performers.

### **Approach:**

- Pull all available historical prices for Bitcoin, major stock market index ETFs (SPY, DIA, QQQ), and high performing stocks (AAPL, AMZN, MSFT).

- Examine and compare historical returns and volatility of index ETFs, stocks, and Bitcoin over full period for which we have Bitcoin prices. Assess BTC performance and volatility compared to other entities over this period.

- Examine and compare historical returns and volatility of index ETFs, stocks, and Bitcoin across each entity's first 3,000 trading days. Assess BTC's performance and volatility compared to early performance and volatility of other entities in comparison.

- Forecast and compare future performance of index ETFs, stocks, & Bitcoin using Monte Carlo Simulations.

## **Sources of Data:**

We gathered data from the following source to support our analysis:

- Yahoo Finance API (YFinance): pulled all available historical prices for 3 stocks & 3 ETFs

- Coingecko API: pulled all available historical BTC prices

- Alpaca API: pulled historical prices for 3 stocks & 3 ETFs for Monte Carlo Simulations

### **Scope of Data:**
- AAPL: historical daily closing prices dating back to December 1980
- AMZN: historical daily closing prices dating back to May 1997
- BTC: historical daily closing prices dating back to April 2013
- DIA: historical daily closing prices dating back to January 1998
- MSFT: historical daily closing prices dating back to March 1986
- QQQ: historical daily closing prices dating back to March 1999
- SPY: historical daily closing prices dating back to January 1993 

## **Libraries Used**
- OS library
- Requests Library
- Pandas Library
- Numpy Library
- Yahoo Finance API through PyPi (No Key Needed)
[YFinance](https://pypi.org/project/yahoo-finance/)
- Json Library
- [CoinGeckoAPI](https://www.coingecko.com/en/api) (No Key Needed)
- DateTime Library
- Alpaca Trade API (Key Needed)
- Monte Carlo Simulations (MCForecastTools, MCSimulation)
- Path Library
- HV Plot Library
- Matplotlib PyPlot Library
- DotENV Variable

## **Analysis Notebooks**
Our data collection, cleaning, and analysis are contained in the following notebooks:

### **Data_Prep.ipynb (pyvizenv)** 
- Imported historical stock prices for Apple (AAPL), Amazon (AMZN), Microsoft (MSFT), S&P 500 (SPY), Dow Jones (DIA), QQQ Trust Series Fund (QQQ) into Pandas dataframes using the Yahoo Finance API, and exported the historical prices into individual csv files.
- Imported Bitcoin (BTC) historical prices into Pandas dataframe using the CoinGeckoAPI and dowloaded to csv file.

### **BTC_Equity_Comparison.ipynb (pyvizenv)**
- Imported CSV files from above notebook into Pandas dataframe.
- Create a combined dataframe using an inner join. Resulting dataframe consisted of historical closing prices for all entities for the period spanning April 2013 to July 2021. This dataframe was used for the first part of the analysis: high-level overview of price performance and volatility.
- Calculated the individual daily returns of each entity and plotted.
- Calculated the cumulative daily returns of all entities.
- Created box plot of daily returns to visually represent volatility.
- Calculated daily and annualized standard deviations for each entity over the analysis period. Plotted the standard deviations for comparison
- To assess early price performance and volatility, created new dataframes consisting of each entity's earliest 3,000 trading days.
- Repeat above analysis for the earliest 3,000 trading days.

### **BTC_Equity_MC_Forecast (need to run in python environment)**
- Imported historical prices for ETFs and stocks from Alpaca API and loaded into Pandas dataframes for Monte Carlo simulations.
- Imported csv containing BTC historical closing prices and daily returns, loaded into a Pandas dataframe, and formatted to be compatible with MCForecastTools.py script.
- Set up 1,000 path, 10-year Monte Carlo simulations for all entities.
- Ran Monte Carlo simulations for all entities.
- Plotted simulation paths and distrbution of forecasted returns.
- Summarized the Monte Carlo forecast results.

## **Analysis Results**

### ***How does BTC price perfomance compare to equity markets?***

To start our analysis, we wanted to compare Bitcoin's price performance from 2013 to present day against the ETF's and stocks over the same period. We calculated the daily returns and plotted them:

![Daily Returns](https://github.com/mrnaglejr/Project-1/blob/main/images/daily_returns_full.png)

The plot of the daily returns highlighted the volatility of Bitcoin. While it showcased explosive growth unmatched by the other entities, Bitcoin also experienced some violent corrections over the period.

Next, we calculated and plotted the cumulative returns of all entities over the previously mentioned timeframe:

![Cumulative Returns](https://github.com/mrnaglejr/Project-1/blob/main/images/cumulative_returns_full.png)

On the whole, the plot of the cumulative returns showed that Bitcoin has significantly outperformed the equities in our comparison over the period. Additionally, the cumulative returns plot further highlight the wild swings of BTC. We see periods of explosive growth, followed by severe corrections.

### ***How does BTC volatility compare to equity markets?***

To gauge Bitcoin's volatility relative to the equity counterparts at a high-level, we created a box plot of daily returns:

![Daily Returns Box Plot](https://github.com/mrnaglejr/Project-1/blob/main/images/box_plot_full.png)

The box plot tells the same story that we saw with the daily returns plot, but in a cleaner way. Bitcoin clearly has a much wider spread of daily returns, featuring both outsized growth and declines. 

The next dimension of our volatility analysis consisted of a comparison of daily and annualized standard deviations. We plotted both the daily and annualized standard deviations of each entity:

![Volatility Comparison](https://github.com/mrnaglejr/Project-1/blob/main/images/vol_comp_full.png)

Unsurprisingly, Bitcoin appears to be in its own class with a significantly higher daily and annualized standard deviation for the period. Bitcoin has clearly been a far more volatile asset relative to the stock market over the last 8 years. That said, the cryptocurrency has also produced the greatest cumulative returns for its long-term investors over the same timeframe.

### ***Is Bitcoin an outlier? How do BTC's returns and volatility compare to early returns and volatility of equities?***

Our initial analysis showed that while BTC has produced greater returns than the ETFs and stocks in the comparison, it was also a highly volatile asset that has experienced multiple major crashes. The next phase of our analysis was aimed at determining whether BTC's explosive growth and extreme volatility are unique, or more typical of a new asset or asset class. In other words, is Bitcoin an outlier?

Our approach to answering this question was to compare BTC's returns and volatility to the early returns and volatility of the stocks and ETFs in our comparison. Specifically, we decided to limit our scope to each entity's first 3,000 trading days, and re-perform the above analysis.

### *How does BTC's price performance compare to the early price performance of equities?*

Similar to the initial analysis, we calculated the daily returns of each entity across the first 3,000 trading days and plotted them:

![Daily Returns - First 3,000 Trading Days](https://github.com/mrnaglejr/Project-1/blob/main/images/daily_returns_first3000.png)

This time around, the plot told a slightly different story. While Bitcoin's extreme highs and lows still stand out, we now see that other entities, such as Amazon and Apple, saw similar price swings in their early history.

However, looking at cumulative returns over the first 3,000 trading days, BTC still appears to be an outlier; the cryptocurrency still outperforms all other entities by a meaningful margin when limiting the analysis to the stocks and ETFs' early history:

![Cumulative Returns - First 3,000 Trading Days](https://github.com/mrnaglejr/Project-1/blob/main/images/cumulative_returns_first3000.png)

One item of note is that BTC seems to be following the QQQ somewhat closely over the last couple of years. If the BTC cumulative returns trendline converges with the QQQ early returns trendline again, perhaps we could argue that the historical performance of QQQ could serve as a benchmark for Bitcoin. 

Overall, the analysis of the early returns history shows that Bitcoin does appear to be outlier in terms of cumulative returns. At the same time, the analysis also shows that Bitcoin's return volatility is not necessarily unprecedented; both Apple and Amazon stock observed comparable price swings in their early history as well. 

### *How does BTC's volatility perforance compare to the early volatility of equities?*

A box plot of the daily returns across the first 3,000 trading days emphasizes the takeaway from above:

![Daily Returns Box Plot - First 3,000 Trading Days](https://github.com/mrnaglejr/Project-1/blob/main/images/box_plot_first3000.png)

Bitcoin is definitely a highly volatile asset. However, it does not appear to be as much of an outlier when comparing against the early volatility of the other entities. Amazon stock, for example, showcases a similarly wide spread of daily returns across its first 3,000 trading days.

The comparison of early standard deviations cements this point:

![Volatility Comparison - First 3,000 Trading Days](https://github.com/mrnaglejr/Project-1/blob/main/images/vol_comp_first3000.png)

Again, Bitcoin is near the top in terms of daily and annualized standard deviations. However, both Apple and Amazon's standard deviations across their first 3,000 trading days appear to be very comparable. In fact, both stocks' annualized standard deviations appear to exceed Bitcoin's annualized standard deviation. In short, the comparison of early price history suggests that Bitcoin's volatility is not necessarily a significant outlier. Instead, it might actually be a common hallmark of new, disruptive company or asset.

### ***Is Bitcoin a good investment for the future?***

The final phase of our analysis was to the assess Bitcoin's potential as an investment going forward. To attempt to answer this question, we decided to run 1,000 path, 10-year Monte Carlo simulations for all entities in our comparison. Then, we quantified the 95% confidence interval and median expectations of a 10-year investment of $10,000 in each entity.

Below are the results of the Monte Carlo simulations:

![Results of Monte Carlo Simulations](https://github.com/mrnaglejr/Project-1/blob/main/images/fcst_ci_median_summ.png)

The results of the Monte Carlo simulation suggest that an investment in Bitcoin is a relatively good bet for the future, especially for an investor with high risk tolerance. A $10,000 investment in Bitcoin is projected to have the highest upper range of the 95% confidence interval ($59M) and the highest median expected value ($957K) in 10 years. It also has the 4th highest lower bound of the 95% confidence interval, representing a total 10-year return of roughly 40% ($14K). In other words, the MC forecast suggests that based on the observed price history, you are unlikely to lose money on a 10-year investment in BTC. Furthermore, the forecast also suggests there is a chance for significant upside.

That said, the wide spread between the upper and lower ranges of the 95% confidence intervals emphasizes the extremes of investing in Bitcoin, and perhaps the crytpo market more broadly.

## **Conclusion: Is Bitcoin a Viable Investment?**

Per our historical price analysis, BTC appears to be a viable investment to date and going forward:

- BTC has been volatile, but extremely profitable for long-term investors
    - Outperformed all other assets in comparison from cumulative return perspective.
- Additionally, BTC’s return volatility is not too dissimilar from early volatility of tech stocks & ETF’s (AAPL, AMZN, QQQ). 
    - Will BTC volatility flatten over time with maturity similar to tech stocks?
- Results of MC simulations suggest that BTC has a good chance to continue to at least be reasonably profitable, with potential for considerable upside:
    - Highest median expected return, highest upper range of 95% confidence interval, 4th highest lower bound of 95% confidence interval

## **Other Considerations**

Below are other considerations aside from the historical price performance and future projections that could factor into a decision to invest in BTC:

- **Regulatory Environment**: Will governments be friendly to BTC and accomodative of the broader crypto market going forward?
- **Environmental Concerns**: Will recent concerns over BTC energy consumption cause investors to shy away, or open the door for more eco-conscious cryptos to take the stage?
- **Nascency of Crypto Market**: BTC is the first mover and current leader, but will it remain on top in an increasingly competitive and evolving space?
- **Risk Appetite & Time Horizon**: How comfortable are you with extreme volatility? Are you a long-term investor or a short-term investor?