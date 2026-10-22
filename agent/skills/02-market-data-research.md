---
name: Market Data Research
description: Use when a subtask needs stock market data: ticker lookup, exchange details, historical end-of-day prices, price change over a period, highs/lows, volume, or comparing several tickers' performance. Not for news, fundamentals commentary, or qualitative company info (use Web Research).
---

## Overview
Gather stock and market figures from reputable financial sources via web search, and return compact, accurate figures, each with its date and source.

## Inputs
- Ticker symbols or company names, plus a time window.
- Tool: web search.

## Steps
1. Confirm the ticker and primary exchange (search "<company> stock ticker"). If the company is listed in several places, choose the primary listing and say which.
2. Search for recent price data, e.g. "<TICKER> stock price", "<TICKER> stock performance past 3 months", "<TICKER> 52-week high low". Prefer exchange sites, company IR pages, and major financial outlets (Reuters, Bloomberg, CNBC, Yahoo Finance, Google Finance, MarketWatch, WSJ, FT).
3. Record: latest price and its date/time, the change over the requested period if it is reported, the 52-week range, market cap, and any notable price moves along with their reported cause.
4. When comparing tickers, use figures from the same date and source where possible, and present a small table.

## Rules
- Every figure needs an as-of date and a source URL.
- Only calculate % change when both endpoint prices come from reliable sources. Show the formula inputs.
- Never extrapolate or invent missing values. Mark them 'not found'.
- Do not give buy/sell recommendations.

## Example
Input: "AAPL vs MSFT, last 30 days".
Output table: Ticker | Latest price (date) | ~30-day change | 52-wk range | Market cap | Source. After the table, add one line noting which outperformed and any caveats about the data.

## Gotchas
- Search snippets often show stale or delayed quotes. Check the timestamp and say the figures may be delayed.
- Sources can disagree slightly on prices. Pick one source for each comparison and keep using it.
- Non-US tickers may need an exchange suffix (e.g. VOD.L).
