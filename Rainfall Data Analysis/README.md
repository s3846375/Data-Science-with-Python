# Rainfall Data Analysis

## Overview

This project applies the data science process to real-world rainfall data. It involves loading, cleaning, and preparing raw climate data before conducting exploratory analysis. Through systematic data processing and visualization, the aim is to uncover patterns and trends in rainfall over time.

## Dataset

The analysis is based on a dataset (Data.csv) containing daily rainfall measurements.

- Year, Month, Day: Date components.

- Rainfall amount (millimetres): Daily precipitation records.

## Features

- Handling Missing Values: Rows with null values (NaN) were identified and removed.

- Standardizing Dates: Converted mixed month formats and text-based days into numerical formats.

- Data Validation: Identified and removed unreasonable dates, such as February 48th or December 200th.

- Filtered the dataset to focus strictly on the period between January 1, 2013, and December 31, 2023.

## Key Findings & Observations

Based on the exploratory visualizations:

- Highest Rainfall Year: Based on the analysis, 2020 has the highest cumulative rainfall, experienced significantly higher rainfall in the early months of the year.

- Lowest Rainfall Year: Conversely, 2019 was the driest year overall, showing consistently lower rainfall totals across most months compared to the rest of the decade.

- Wettest Months: April, October, and December typically experience the highest rainfall and the most significant year-to-year variability.

- Driest Months: June, July, and August remain consistently dry, with rainfall almost always staying below 60 mm.

- Recent Trends: There was a notable spike in rainfall in early 2020. However, by 2023, rainfall amounts dropped significantly across almost every month.
