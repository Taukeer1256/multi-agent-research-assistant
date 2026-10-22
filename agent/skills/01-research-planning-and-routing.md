---
name: Research Planning & Routing
description: Use at the start of any multi-part or non-trivial research query (company analysis, market/industry research, competitor comparisons, investment-thesis research, trend reports) to break it into subtasks and route them to market-data and web-research sub-agents in parallel. Not for one-line factual questions answerable with a single lookup.
---

## Overview
Turn a research query into a short plan of independent subtasks, send each one to the right specialist using delegate_subagent, collect the results, and hand them to report synthesis.

## Inputs
- The user's research query, plus any scope hints (tickers, companies, time range, region, depth).
- Tools: delegate_subagent (inline), web search.

## Steps
1. Restate the research goal in one sentence and pick the entities (companies, tickers, sectors) and the time window. If the user gives none, default to the last 30 days for prices and the last 6 months for news.
2. Break the goal into 2-6 subtasks. Label each one MARKET (prices, tickers, exchange, historical performance) or WEB (news, products, leadership, competitors, regulation, industry trends, analyst views).
3. Mark dependencies. Example: resolve the ticker first if only a company name is given. Independent subtasks run in parallel.
4. For each independent subtask, call delegate_subagent with subAgentId "inline" and a self-contained brief that includes: the objective, the exact entities and dates, which tools to use (MARKET: web search plus the Market Data Research skill; WEB: web search plus the Web Research skill), and the required output (bullet findings, each with its source and date).
5. Run dependent subtasks after the ones they rely on have returned.
6. Check the results: fill gaps with one follow-up delegation at most, and note any subtask that failed.
7. Load the Report Synthesis skill and write the final report.

## Rules
- Each brief must stand on its own, because sub-agents do not see the conversation.
- Keep to 6 subtasks or fewer. Merge any that overlap.
- Do not delegate trivial lookups. Run them yourself.
- Briefly show the user the plan (one line per subtask) at the top of the final report under 'Research plan'.

## Example
Query: "How has NVIDIA performed over the last quarter and what's driving it?"
Plan: (1) MARKET: NVDA price performance over the last 90 days, including % change and the 52-week range. (2) WEB: NVIDIA news and earnings for the last 90 days. (3) WEB: analyst sentiment and the competitive landscape (AMD, custom AI chips). Run 1-3 in parallel, then synthesise.

## Gotchas
- If only a company name is given, resolve the ticker first. If it is ambiguous (several listings), choose the primary US listing and say so.
- Prices found via web search may be delayed. Always give an as-of timestamp and never describe them as 'live'.
- If a sub-agent returns nothing useful, report the gap. Do not fill it with guesses.
