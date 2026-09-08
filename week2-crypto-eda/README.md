# Week 2: BTCUSDT Exploratory Data Analysis

Exploratory analysis of Bitcoin price behavior using pandas, pulled directly 
from Binance's public API — no dataset download needed.

## What it covers
- 365 days of daily BTCUSDT OHLCV data, pulled live via `requests`
- Price trend over the full period
- Daily return distribution (spot the fat tails)
- 7-day rolling volatility — showing how risk clusters into calm and turbulent periods
- Identified the single worst day in the period and its exact return

## Key findings
- Mean daily return: -0.07%, std dev (volatility): 2.32%
- Max single-day gain: 12.19%, max single-day loss: -14.02%
- Volatility is not constant — it clusters, with clear calm stretches and 
  sharp spikes, consistent with what's often called "volatility clustering" 
  in financial time series

## Stack
- pandas, matplotlib
- Binance public REST API (`/api/v3/klines`)
- Kaggle Notebooks

## Why this matters (for me)
I trade BTCUSD and do USDT arbitrage — seeing the return distribution and 
volatility clustering directly, rather than just reacting to daily price 
moves, is useful context for position sizing and risk expectations.
