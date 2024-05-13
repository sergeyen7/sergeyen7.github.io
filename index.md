---
layout: default
title: Donchian Quest Research
description: Do trend following strategy works in crypto?
---
# Table of contents
* [Experiment](#experiment)

* [What is trend following?](#what-is-trend-following)
  
* [Idea and script](#idea-and-script)
  
* [How to use it](#how-to-use-it)
  
* [Script description](#script-description)
  
* [Crypto DEX Hyperliquid](#crypto-dex-hyperliquid)

* [Vault monthly results](#vault-monthly-results)
  
* [Contacts](#contacts)

# Experiment

I want to test **crypto trend following strategy**. 

This type of strategies shows good results in TradFI: commodities, stocks, forex. 

Tradingview shows that this strategy is profitable in crypto too.

I will test it in real trading.

# What is trend following?

Trend following is an trading strategy that aims to capitalize on the directional movement, or trends, in financial markets. Followers of this strategy believe that assets tend to move in persistent directions over time. 

* * *

> **Trend followers typically buy or sell assets based on the direction of the prevailing trend, attempting to ride the trend for as long as possible to maximize profits.**

* * *

Trend following is characterized by its systematic and disciplined approach, with practitioners aiming to minimize losses during periods of market volatility while capturing gains during trend movements.

This approach involves using technical analysis tools to identify and confirm trends: moving averages, different types of price channels, Bollinger bands, Supertrend and so on. 

Different researches say that all this tools give approximately the same results if you choose approximately the same settings. Therefore, any of these tools can be used.


# Idea and script

Richard Donchian was a financial pioneer and is often referred to as the "father of trend following." 

Donchian is most famous for his work in developing the concept of trend following systems and for establishing some of the first systematic trading strategies.

One of his significant contributions to the field of technical analysis is **the creation of the Donchian Channels**, which are a set of lines typically used to identify potential breakouts or breakdowns in a trading instrument's price movements.

The channel breakout concept he proposed was used by many traders.

Another Richard, commodities speculator Richard Dennis, used channels in his famous Turtles training and made hundreds of millions of dollars.

Similar idea was proposed in article **“Black Box Trend Following - Lifting the Veil”**. Authors: Nigol Koulajian and Paul Czkwianianc. The authors of this paper are principals of Quest Partners LLC, trading company manages $2.3 billion in assets.

I coded this as a script in Tradingview:

[Tradingview](https://www.tradingview.com/script/YPQwKNF8-Donchian-Quest-Research/).

![Script on Tradingview](/images/BTCUSD.png)

# How to use it

* You can use script for your trading as you wish - on any exchange with spot or perpetual futures. My referral link for Hyperliquid exchange:

     [app.hyperliquid.xyz/join/SERGEYEN](https://app.hyperliquid.xyz/join/SERGEYEN).

* You can invest your money in my Hyperliquid vault - if you clearly understand theory of trend following described in next chapters:

     [Vault Donchian Quest Research](https://app.hyperliquid.xyz/vaults/0x54094fd5077de413017b5e83da0b587043b55144).

# Script description

Strategy uses two channels. One channel - for opening trades. Second channel - for closing. Channel is similar to Donchian channel, but uses Close prices (not High/Low). 

* * *

Strategy waits for beginning of trend - when price breakout of channel. Default length of both channels = 50 candles.

Conditions of trading:

* Open Long: If last Close = max Close for 50 closes.
* Close Long: If last Close = min Close for 50 closes.
* Open Short: If last Close = min Close for 50 closes.
* Close Short: If last Close = max Close for 50 closes.

* * *

Color of lines:

- black - channel for opening trade.
- red - channel for closing trade.
- yellow - entry price.
- fuchsia - stoploss and breakeven.
- vertical green - go Long.
- vertical red - go Short.
- vertical gray - close in end, don't trade anymore.

* * *

Order size calculated with ATR and volatility.

You can't trade 1 contract in BTC and 1 contract in XRP - for example. They have different price and volatility, so 1 contract BTC not equal 1 contract XRP.

Script uses universal calculation for every market. It is based on:
* Risk - USD sum you ready to loss in one trade. It calculated as percent of Equity.
* ATR indicator - measurement of volatility.

With default setting your stoploss = 0.5 percent of equity:

- If initial capital is 1000 USD and used parameter "Permit stop" - loss will be 5 USD (0.5 % of equity).
- If your Equity rises to 2000 USD and used parameter "Permit stop"- loss will be 10 USD (0.5 % of Equity).

* * *

This Risk works only if you enable “Permit stop” parameter in Settings.

If this parameter disabled - strategy works as reversal strategy:
* If close Long - channel border works as stoploss and momentarily go Short.
* If close Short - channel border works as stoploss and momentarily go Long.

Channel borders changed dynamically. So sometime your loss will be greater than ‘Risk %’. Sometime - less than ‘Risk %’.

If this parameter enabled - maximum loss always equal to 'Risk %'. This parameter also include breakeven: if profit % = Risk %, then move stoploss to entry price.

* * *

> **Like all trend following strategies - it works only in trend conditions. If no trend - slowly bleeding.**

* * *

There is no special additional indicator to filter trend/notrend. You need to trade every signal of strategy.

Strategy gives many losses:
* 30 % of trades will close with profit.
* 70 % of trades will close with loss.
* But profit from 30% will be much greater than loss from 70 %.

Your task - patiently wait for it and don't use risky setting for position sizing.

* * *

Recommended timeframe - Daily.

* * *

Trend can vary in lengths. Selecting length of channels determine which trend you will be hunting:
* 20/10 - from several days to several weeks.
* 20/20 or 50/20 - from several weeks to several months.
* 50/50 or 100/50 or 100/100 - from several months to several years.

* * *

Inputs (Settings):

* Length: length of channel for trade opening/closing. You can choose 20/10, 20/20, 50/20, 50/50, 100/50, 100/100. Default value: 50/50.

* Permit stop: use stop or go reversal. Default value: without stop, reversal strategy.

* Orders number: use single order or divide it to several orders.

* Use additional orders?: if trade is profitable - use additional orders to increase position size.

* Cost %: If enabled "Use additional": Maximal position cost (size * entry) in percents of Equity.

* Permit Long / Permit short: Longs are most profitable for this strategy. You can disable Shorts and enable Longs only. Default value: permit all directions.

* Risk % of Equity: for position sizing used Equity percent. Don't use values greater than 5 % - it's risky. Default value: 0.5%.

* ATR multiplier: this multiplier moves stoploss up or down. Big multiplier = small size of order, small profit, stoploss far from entry, low chance of stoploss. Small multiplier = big size of order, big profit, stop near entry, high chance of stoploss. Default value: 2.

* ATR length: number of candles to calculate ATR indicator. It used for order size and stoploss. Default value: 20.

* Close in end: to close active trade in the end (and don't trade anymore) or leave it open. You can see difference in Strategy Tester. Default value: don’t close.

* Show info label: show informational label with calculations: ATR, order size, prices.


# Crypto DEX Hyperliquid

Hyperliquid is an order book perpetual futures DEX. The DEX runs on the Hyperliquid L1, a custom blockchain that is performant enough to operate the whole exchange – every operation happens transparently on-chain with block latency <1 second.

It uses Arbitrum USDC for deposits/withdrawals. Cost of deposit = cost of gas ($0.08 - $0.10). Cost of withdraw = 1 USDC (was 2 USDC). After deposit all operations executed on 'inside' L1 blockchain. No lock-up period, withdraw possible any time.

Mainnet alpha is live. For trade you need:
* email or any EVM wallet (e.g., Rabby, MetaMask, WalletConnect, Coinbase Wallet).
* ETH on Arbitrum for deposit's gas. 
* USDC on Arbitrum for deposit.

You can trade more than 100 assets on the exchange: btc, eth, regular altcoins, defi, memes. New coins are constantly being added. Prices based on oracles prices from different CEXs and DEXs. Leverages from 3x to 50x.

Interesting function - 'vaults'. It's like 'pools' on other DEXs, but 'vault leader' can trade funds of this vault. Normal perpetual trade - longs, shorts. Normal liquidations if something go wrong. If trade is profitable - leader receive a 10% profit share for managing the vault. 

* * *

> **As always: Trading is inherently risky, and vaults’ past performance is not a guarantee of future returns.**

* * *

Vaults have a lock-up period of 1 day.

Exchange has a trading API, which has the most necessary functions: receive data, open a trade, close a trade, place orders. This API does not have some rarely used functions, such as changing leverage. Python SDK shows examples of all API commands.

Disadvantages of Hyperliquid:
* sometime relatively high funding rates. They are higher than on the CEXs.
* sometime relatively low liquidity on some coins. Whales only begin discover this DEX.
* for high speed work all servers should be near each other. Maybe in a single zone of AWS (or similar provider).
* counterparty risk - anonymous developers can anytime go away with money.

Main advantage of Hyperliquid:
* it works on smartcontracts.

# Vault monthly results

|    Date    |  Equity (USD)  |  Pnl (30 days) |
|:-----------|:---------------|:---------------|
| 1 Jan 2024 |           5000 |              0 |
| 1 Feb 2024 |           4755 |           -245 |
| 1 Mar 2024 |           7295 |           2531 |
| 1 Apr 2024 |           8887 |            830 |
| 1 May 2024 |           5629 |          -3994 |

# Contacts

[Twitter](https://twitter.com/sergeyen777).

[Tradingview](https://www.tradingview.com/u/sergeyen/).

<script src="http://code.jquery.com/jquery-1.4.2.min.js"></script> <script> var x = document.getElementsByClassName("site-footer-credits"); setTimeout(() => { x[0].remove(); }, 10); </script>

