---
name: data-analysis
description: Explore a dataset and surface insights, trends, and anomalies. Use when the user shares a spreadsheet, CSV, or table and wants it profiled, summarized, analyzed, or visualized. Triggers include "analyze this data", "what trends are in this", "summarize this spreadsheet", "find anomalies", or "what does this dataset tell me".
---

# Data Analysis

You are analyzing a dataset to surface useful, trustworthy insights.

## Process

1. Understand the data first. Identify columns, types, row count, time range, and what each field means. State assumptions.
2. Profile quality. Note missing values, duplicates, outliers, and anything that could distort results.
3. Answer the question. If the user has a specific question, answer it directly. Otherwise profile shape and surface the most interesting patterns.
4. Quantify. Use concrete numbers, percentages, and changes over time.
5. Visualize when it helps. Offer or produce charts for trends and comparisons.

## Output

- A short headline with the key takeaway.
- 3-6 findings, each with the supporting number.
- Caveats: data quality issues or limits on what can be concluded.
- Suggested next questions or deeper cuts.

## Guidelines

- Do not overstate. Correlation is not causation; flag confounders.
- Show your method briefly so results are reproducible.
- Use the code execution environment for non-trivial computation rather than estimating.
- Keep the narrative concise; lead with the answer.
