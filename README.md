# A Whale Off the Port(folio)

## Background

Harold's company has been investing in algorithmic trading strategies. Some of the investment managers love them, some hate them, but they all think their way is best.

You just learned these quantitative analysis techniques with Python and Pandas, so Harold has come to you with a challenge—to help him determine which portfolio is performing the best across multiple areas: volatility, returns, risk, and Sharpe ratios.

You need to create a tool  that analyzes and visualizes the major metrics of the portfolios across all of these areas, and determine which portfolio outperformed the others.

For this project, I have three main tasks:

1. [Read in and Wrangle Returns Data](#Prepare-the-Data)

2. [Determine Success of Each Portfolio](#Conduct-Quantitative-Analysis)

3. [Choose and Evaluate a Custom Portfolio](#Create-a-Custom-Portfolio)

---

## Instructions

### Prepare the Data

First, read and clean several CSV files for analysis. The CSV files include whale portfolio returns, algorithmic trading portfolio returns, and S&P 500 historical prices and complete the following steps:

1. Use Pandas to read the following CSV files as a DataFrame. Be sure to convert the dates to a `DateTimeIndex`.

    * `whale_returns.csv`: Contains returns of some famous "whale" investors' portfolios.

    * `algo_returns.csv`: Contains returns from the in-house trading algorithms from Harold's company.

    * `sp500_history.csv`: Contains historical closing prices of the S&P 500 Index.

2. Detect and remove null values.

3. If any columns have dollar signs or characters other than numeric values, remove those characters and convert the data types as needed.

4. The whale portfolios and algorithmic portfolio CSV files contain daily returns, but the S&P 500 CSV file contains closing prices. Convert the S&P 500 closing prices to daily returns.

5. Join `Whale Returns`, `Algorithmic Returns`, and the `S&P 500 Returns` into a single DataFrame with columns for each portfolio's returns.

### Conduct Quantitative Analysis

Analyze the data to see if any of the portfolios outperform the stock market (i.e., the S&P 500).

#### Performance Analysis

1. Calculate and plot daily returns of all portfolios.

![image](https://user-images.githubusercontent.com/98990090/172506920-5c362d2c-b46f-4f99-b2b3-4fec9922466d.png)

2. Calculate and plot cumulative returns for all portfolios. Does any portfolio outperform the S&P 500?

![image](https://user-images.githubusercontent.com/98990090/172506894-f8f7be81-4606-4102-b147-89939648c5a4.png)

> Berkshire Hathaway, Soros Fund Management, and Algo 2 all outperformed the SP Closing Price at one point in the data set

#### Risk Analysis

1. Create a box plot for each of the returns. 

2. Calculate the standard deviation for each portfolio.

![image](https://user-images.githubusercontent.com/98990090/172507023-084a367d-8ad4-46f1-9e94-e73e81affe38.png)

3. Determine which portfolios are riskier than the S&P 500.
> Berkshire Hathaway, INC

4. Calculate the Annualized Standard Deviation.

![image](https://user-images.githubusercontent.com/98990090/172507047-9bcebf2d-b5ff-4631-bf79-bc3f8e7054ef.png)

#### Rolling Statistics

1. Calculate and plot the rolling standard deviation for all portfolios using a 21-day window.

![image](https://user-images.githubusercontent.com/98990090/172507074-f1a03d3d-8ee1-49bb-9402-57c6b57b3ae4.png)

2. Calculate and plot the correlation between each stock to determine which portfolios may mimick the S&P 500.

![image](https://user-images.githubusercontent.com/98990090/172507106-b55537ac-b5bb-4428-86f9-324ec5d867c5.png)

3. Choose one portfolio, then calculate and plot the 60-day rolling beta between it and the S&P 500.

> Berkshire Hathaway <br>
![image](https://user-images.githubusercontent.com/98990090/172507140-f545141d-c0b0-4595-85b4-9655f1d85153.png)

### Sharpe Ratios

Investment managers and their institutional investors look at the return-to-risk ratio, not just the returns. After all, if you have two portfolios that each offer a 10% return, yet one is lower risk, you would invest in the lower-risk portfolio, right?

1. Using the daily returns, calculate and visualize the Sharpe ratios using a bar plot.

![image](https://user-images.githubusercontent.com/98990090/172507181-2f5fc8b6-fe90-4cc9-877b-d52ad9f000b4.png)

2. Determine whether the algorithmic strategies outperform both the market (S&P 500) and the whales portfolios.
> Algo 1 outperformed SP 500 and Whale Return, Algo 2 did not

### Create a Custom Portfolio

Harold is ecstatic that you were able to help him prove that the algorithmic trading portfolios are doing so well compared to the market and whales portfolios. However, now you are wondering whether you can choose your own portfolio that performs just as well as the algorithmic portfolios. Investigate by doing the following:

1. Visit [Google Sheets](https://docs.google.com/spreadsheets/) and use the built-in Google Finance function to choose 3-5 stocks for your portfolio.

2. Download the data as CSV files and calculate the portfolio returns.

3. Calculate the weighted returns for your portfolio, assuming equal number of shares per stock.

4. Add your portfolio returns to the DataFrame with the other portfolios.

5. Run the following analyses:

    * Calculate the Annualized Standard Deviation.
    * Calculate and plot rolling `std` with a 21-day window.
    * Calculate and plot the correlation.
    * Calculate and plot beta for your portfolio compared to the S&P 60 TSX.
    * Calculate the Sharpe ratios and generate a bar plot.

4. How does your portfolio do?
> My portfolio outperformed all portfolios except Algo 1.
