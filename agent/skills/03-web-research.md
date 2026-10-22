---
name: Web Research
description: Use when a subtask needs current or qualitative information from the web: company news, earnings coverage, product launches, leadership changes, competitors, regulation, industry trends, market sizing, or analyst sentiment. Not for numeric stock price history (use Market Data Research).
---

## Overview
Use web search to find recent, credible information and return sourced bullet findings for the planner to combine.

## Inputs
- The subtask objective, entities, and time window from the brief.
- Tool: web search.

## Steps
1. Write 2-4 targeted queries (entity + topic + timeframe, e.g. "NVIDIA Q3 2026 earnings data center revenue").
2. Prefer primary or credible sources: company IR/press releases, regulators, major financial and news outlets, and industry research firms.
3. Pull out the key facts: what happened, when, figures, and who said it.
4. Cross-check important claims against a second source when you can. Flag claims that come from one source only.
5. Return 4-10 bullets, each formatted as: finding, date, source URL.

## Rules
- Every bullet needs a URL and a date.
- Prefer the newest sources within the requested window. Label anything older than the window as background.
- Keep reported facts separate from opinion or speculation.

## Example
Brief: "Recent drivers of Tesla stock, last 60 days".
Output: "- Q3 deliveries beat consensus at 497k units (2026-10-02, https://ir.tesla.com/...)" plus further bullets on margins, regulation, and analyst moves.

## Gotchas
- Search snippets can be out of date or wrong. Open or confirm the source before quoting numbers.
- Avoid content farms and unattributed rumour sites.
- If nothing relevant turns up, say "no reliable recent coverage found" instead of padding.
