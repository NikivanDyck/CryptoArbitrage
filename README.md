## CryptoArbitrage

![bit coin image](https://executium.com/m/alt/images/1140521458_cryptoarbitrage.jpg)

### Overview

The cryptoarbitage analysis was completed within Jupyter notebooks. The analysis code contains data collection, preparation, analysis, and visualizations used to complete to arbitrage analysis.  

---

### Problem Statement
Review the historical trade data for Bitcoin on two exchanges IE: Bitstamp and Coinbase and determine if there are any arbitrage opportunities.  

---

### Tools and/or Imports Used 
Jupyter, Pandas, Pathlib, matpltlib

---

### Outcome: 
There are minimal arbitrage opportunities between the two exchanges.  Of the months of data analyzed arbitrage opportunities were limited to 185 events as reflected in CSV file.  

---

### Appendix:  
List of terms definitions and code used to complete the analysis

| Term | Description | Calculation/ or Value |
| :--- | :--- | :---: |
|arbitrage_spread / difference |The spread is the difference between two stocks or exchanges that exists as the same time.  A profit is made when you simultaneously buy at the lower price and sell at the higher price, locking in the price |bitcoin_1['Column name '].loc['date'].plot(legend=True, figsize=(15, 10), title="October 19, 2015", color="blue", label="BTC 1") bitcoin_2['Column name'].loc['date'].plot(legend=True, figsize=(15, 10), color="orange", label="BTC 2")|

|arbitrage_spread| Review the summary statistics for the spread between the two assets by subtracting the closing price|arbitrage_spread = bitcoin_2['Column name'].loc['date'] - bitcoin_1['Column name'].loc['date']  
arbitrage_spread.describe()|

|spread_return|Identify the trades that will cover the transaction costs. To begin first need to convert the arbitrage_spread dollar values into percentage return values|Use the arbitrage_spread to determine the return percentage of the trades with a positive spread. Include only the trades that have an arbitrage_spread that’s greater than 0. Use the prices from the day as the denominator. 

spread_return |arbitrage_spread[arbitrage_spread>0] / bitcoin_1['Column name'].loc['date'] |

|Profitable_trades|percentage return values. 1% minimum return threshold, thus anything over 1% = profitable |profitable_trades = spread_return[spread_return > .01]
profitable_trades.head(10)
profitable_trades.describe()|

|Profit|This is the potential profit by “day”/ timestamp.|profit = profitable_trades * bitcoin_1['Close'].loc['2015-10-19']
profit
