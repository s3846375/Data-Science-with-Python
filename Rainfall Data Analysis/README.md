# Rainfall Data Analysis

## Overview

This project applies the data science process to real-world rainfall data. It involves loading, cleaning, and preparing raw climate data before conducting exploratory analysis. Through systematic data processing and visualization, the aim is to uncover patterns and trends in rainfall over time.

## Dataset

The raw dataset (`Data.csv`) contains daily rainfall records with the following columns:

| Column                          | Description                                                             |
| ------------------------------- | ----------------------------------------------------------------------- |
| `Year`                          | Year of the observation                                                 |
| `Month`                         | Month of the observation (may contain names, abbreviations, or numbers) |
| `Day`                           | Day of the observation (may contain numbers or spelled-out words)       |
| `Rainfall amount (millimetres)` | Recorded daily rainfall in mm                                           |

The data spans from 2013 to 2023 and contains several data quality issues that are addressed during cleaning (see below).

## Requirements

- Python 3
- [pandas](https://pandas.pydata.org/)
- [matplotlib](https://matplotlib.org/)

## Analysis Tasks

### Task 1: Data Preparation

Cleans and prepares the raw rainfall data:

- Loads `Data.csv` and inspects data types and shape
- Removes rows containing missing values
- Converts `Year`, `Month`, and `Day` into a single `date` column, handling:
  - Month names/abbreviations (e.g. `"April"`, `"Jan"`) converted to numeric months
  - Day values spelled out as words (e.g. `"nine"`) converted to numbers
  - Invalid or unparseable dates (e.g. day `48`, month `200`) removed
- Filters out dates outside the valid range (2013-01-01 to 2023-12-31)
- Removes rainfall outliers (values `< 0` mm or `> 10,000` mm)
- Exports the cleaned dataset to `Data_clean.csv`

### Task 2: Data Exploration

Using the cleaned dataset, the notebook explores rainfall patterns through several sub-tasks:

- **2.1 — Daily rainfall by month (2014):** Reshapes 2014 data into a day-by-month table and identifies the highest daily rainfall recorded in each month, visualized as a bar chart.
- **2.2 — Yearly and monthly trends (2015–2017):** Compares total yearly rainfall and monthly rainfall patterns across three years using bar and line charts.
- **2.3 — Highest vs. lowest rainfall years:** Identifies the top 3 and bottom 3 years by total rainfall across the full dataset (2013–2023) and compares the wettest year (2020) against the driest year (2019) on a monthly basis.
- **2.4 — Long-term trend (last 10 years):** Examines total and average yearly rainfall from 2014 to 2023 to reveal how rainfall has changed over the last decade.

## Key Findings

- The years **2020, 2021, and 2022** recorded the highest total rainfall, while **2013, 2014, and 2019** recorded the lowest.
- **2020** was the wettest year overall (786.8 mm), while **2019** was the driest (374.4 mm) — a difference of over 400 mm.
- Rainfall generally trended upward from 2014 to 2017, dipped sharply in 2019, then peaked in 2020 before gradually declining, though remaining relatively high through 2021–2022.
