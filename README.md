# Citi Bike NYC — Ridership & Operations Analysis

Exploratory analysis of 58.9M Citi Bike trips in New York City, using BigQuery, SQL, and Python to uncover usage patterns by rider type, station demand, and time-of-day trends — and translate them into concrete operational recommendations.

## Overview

Citi Bike's public trip dataset (`bigquery-public-data.new_york.citibike_trips`) was used to answer three questions relevant to system operations: how do subscribers and casual riders differ in behavior, which stations see the heaviest demand, and how does ridership shift across the day and week? The goal was to move from raw trip logs to specific, actionable recommendations a bike-share operator could act on.

## Approach

1. **Dataset exploration** — queried the BigQuery public dataset to understand volume, fields, and data quality limitations before forming hypotheses.
2. **AI-assisted hypothesis generation** — used Gemini to help scope and refine the business questions worth pursuing.
3. **SQL analysis in BigQuery** — extracted ride frequency, user segmentation, trip duration, top stations, and hourly/weekday distributions.
4. **Python visualization (Colab)** — validated and explored trends with pandas, matplotlib, seaborn, and Plotly, including KPI summaries and time-based breakdowns.

## Key Findings

- **58,937,715** total trips analyzed, average trip duration **16.04 minutes**, **17,682** unique bikes in service.
- Subscribers account for **79.6%** of all trips and take shorter rides, consistent with commute-driven usage; casual customers ride less often but for longer, consistent with leisure use.
- Weekday demand peaks sharply around **8 AM** and **5–6 PM**, matching commute hours; weekend demand is flatter and more evenly spread — supporting the leisure-usage hypothesis for casual riders.
- Stations like **Pershing Square North** and **E 17 St & Broadway** are consistently among the busiest for both starts and ends, pointing to established commuting corridors.
- Missing `user_type` and station-name values in a subset of trips limit segmentation accuracy and are flagged as a data quality issue.

## Recommendations

- Rebalance bikes proactively toward high-demand stations ahead of the morning peak, using observed weekday patterns.
- Prioritize service reliability during commute windows for subscribers; explore leisure/tourist passes for casual riders given their longer average trips.
- Evaluate dock capacity and maintenance response at high-traffic stations.
- Standardize data validation to reduce missing user-type and station metadata going forward.

## Tech Stack

Google BigQuery · SQL · Python (pandas, matplotlib, seaborn, Plotly) · Google Colab · Gemini

## Repository Contents

- `citibike_analysis.ipynb` — full notebook: SQL queries, Python visualizations, and analysis
- `README.md` — this file

## Team

This was a group project completed with Xinyi Zhang and Gabriel Wang.
