## CryptoArbitrage

![bit coin image](https://executium.com/m/alt/images/1140521458_cryptoarbitrage.jpg)

### Overview

The cryptoarbitage analysis contains data from 01/01/2018 - 03/31/2018 , preparation, analysis, and visualizations used to complete to arbitrage analysis between Bitstmap and Coinbase.  

---

### Problem Statement
Review the historical trade data for Bitcoin on two exchanges IE: Bitstamp and Coinbase and determine if there are any arbitrage opportunities.  

---

### Tools and/or Imports Used 
Jupyter, Pandas, Pathlib, matpltlib

---

### Outcome: 
There are minimal arbitrage opportunities between the two exchanges.  Of the months of data analyzed arbitrage opportunities were limited to 185 timestamped events. Specificaly 13 days in Jan, 5 days in Feb, and 3 days in Mar. There have been less arbitrage oppertunitres between these exchanges over time. Note: Referanced outome data in attached CSV file is a list of opportunities by Month/Day.  

---

### Appendix:  
List of terms definitions and code used to complete the analysis

| Term | Description | Calculation/ or Value |
| :--- | :--- | :---: |
|arbitrage_spread / difference |The spread is the difference between two stocks or exchanges that exists as the same time.  A profit is made when you simultaneously buy at the lower price and sell at the higher price, locking in the price |bitcoin_1['Column name '].loc['date'].plot(legend=True, figsize=(15, 10), title="TITLE", color="blue", label="BTC 1") bitcoin_2['Column name'].loc['date'].plot(legend=True, figsize=(15, 10), color="orange", label="BTC 2")
|arbitrage_spread| Review the summary statistics for the spread between the two assets by subtracting the closing price|arbitrage_spread = bitcoin_2['Column name'].loc['date'] - bitcoin_1['Column name'].loc['date'] arbitrage_spread.describe()
|spread_return|Identify the trades that will cover the transaction costs. To begin first convert the arbitrage_spread dollar values into percentage return values. Include only the trades that have an arbitrage_spread that’s greater than 0. Use the prices from the day as the denominator. |spread_return =arbitrage_spread[arbitrage_spread>0] / bitcoin_1['Column name'].loc['date'] 
|Profitable_trades|percentage return values. 1% minimum return threshold, thus anything over 1% = profitable|profitable_trades = spread_return[spread_return > .01]  profitable_trades.head(10)  profitable_trades.describe()
|profit|This is the potential profit by “day”/ timestamp.|profit = profitable_trades * bitcoin_1['Close'].loc['2015-10-19']

---
### Created by:
Niki van Dyck 
