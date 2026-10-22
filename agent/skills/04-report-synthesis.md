---
name: Report Synthesis
description: Use after specialist findings (market data and/or web research) are collected, to merge them into the final structured research report for the user. Also use when the user asks to reformat, summarise, or extend a previous research report.
---

## Overview
Combine the specialist outputs into one coherent, cited research report that answers the original query.

## Inputs
- The original query, the research plan, and all sub-agent findings with their sources.

## Steps
1. Re-read the original question and decide which findings answer it directly.
2. Remove duplicate findings and settle conflicts: prefer the newer, primary source, and mention the conflict if it matters.
3. Write the report in this structure:
   - **Summary**: 3-5 bullet answer to the question.
   - **Research plan**: one line per subtask.
   - **Market data**: table or key figures with as-of dates (if relevant).
   - **Key findings**: grouped by theme, each with an inline source.
   - **Analysis**: drivers, risks, and outlook, clearly labelled as analysis.
   - **Gaps & caveats**: missing data, single-source claims, delayed pricing.
   - **Sources**: numbered list of URLs with dates.
4. Keep it under about 600 words unless the user asks for depth.

## Rules
- Every number and claim must trace back to a finding. Add no new facts at this stage.
- Label analysis and opinion as such, and end market-related reports with a short 'Not financial advice' note.

## Example
For "NVIDIA last quarter": the Summary gives % change and the main drivers. The Market data table shows latest price, period change, and 52-week range with dates. Key findings cover earnings, data-center demand, and export rules. Analysis covers valuation risk. Sources lists about 6 dated URLs.

## Gotchas
- Do not drop failed subtasks silently. List them under Gaps.
- Do not mix dates from different time zones or periods in one comparison.
- If findings are thin, give a shorter report rather than padding.
