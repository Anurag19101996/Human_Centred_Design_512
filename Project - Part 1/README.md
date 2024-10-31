# Wildfire Smoke Impact Analysis - Course Project Part 1

This repository contains the code, data, and analysis for **Part 1** of the wildfire smoke impact project. The focus is to evaluate the annual wildfire smoke impacts on an assigned city within the last 60 years. My assigned city is **Charleston, South Carolina**. The objective is to estimate wildfire smoke’s effect on air quality and produce visualizations that highlight the trends, distribution, and correlation with AQI data.

## Project Overview

The project is divided into five parts, with Part 1 being the **Common Analysis** where all students perform the same base analysis with a unique dataset subset for each city. The aim of this part is to establish a base understanding of wildfire smoke impact on the city by creating an annual smoke estimate for each year (1961-2021) and comparing it to AQI data to assess its validity.

This repository includes the following elements of Part 1:

- **Data Acquisition**: Retrieving, processing, and filtering wildfire data within 650 miles of Charleston.
- **Smoke Estimate Calculation**: Creating annual smoke estimates based on fire size and distance.
- **Comparison with AQI Data**: Using AQI data from EPA AQS to validate the smoke estimates.
- **Visualizations**: Producing time series and histogram visualizations to illustrate trends and distributions.
- **Reflection on Collaboration**: Documenting collaborative insights and attributions.

## Dataset

### Primary Dataset
The wildfire data is sourced from the **US Geological Survey’s Combined Wildland Fire Polygons Dataset (1800s-Present)**, available in both ArcGIS and GeoJSON formats. This dataset includes fire polygons, years, and acreage but lacks specific start and end dates for fires.

### AQI Data
AQI data is obtained via the **EPA Air Quality System (AQS) API**. It includes air quality data for Charleston, with a focus on particulate matter (PM2.5) as it is a primary contributor to air pollution from wildfires.

### Data Filtering
- Data is filtered for fires within 650 miles of Charleston.
- Only fires occurring from **May to October** are considered, as these months align with the typical fire season.
- Analysis focuses on the years **1961-2021**.

## Prerequisites

- **EPA API Key**: An API key is required to access the EPA AQS data for AQI information. You can request it from the [EPA AQS API website](https://www.epa.gov/aqs).

## Usage

1. **Run Analysis**: Open and execute `HCDE_PROJECT_PART1.ipynb` to process the data, calculate smoke estimates, and generate the required visualizations, including the histogram and time series graphs.

## Analysis Steps

### Fire Smoke Estimate Calculation:
- Fires within 650 miles of Charleston were identified.
- Smoke estimates are based on fire area and distance using a logarithmic function: `fire area / log(1 + distance from Charleston)` for closer and larger fires.
- Rationale for Logarithmic Scaling: The logarithmic function is applied to distance to account for the fact that smoke impact decreases as distance from the fire increases, but not in a strictly linear way. The use of log(1 + distance) moderates the influence of distant fires by reducing the impact gradually rather than abruptly. This approach provides a more realistic representation of smoke dispersion, where closer fires contribute more heavily to the estimate, and distant fires contribute less as they are further away.

### Visualization in Python Notebook:

1. **Impact Score Prediction (2025-2050)**: Shows the smoke estimates (impact scores) for available data (1961 to 2021) and predictions from 2025 to 2050 using a difference ARIMA model with confidence intervals.
2. **Number of Fires by Distance from Charleston**: A histogram displaying the number of fires in 50-mile bins from Charleston up to 1800 miles (nearest distance to the periphery of the fire is used).
3. **Total Acres Burned per Year (Within 650 Miles)**: A time series of total acres burned by fires each year within 650 miles of Charleston (1961-2021).
4. **Time Series of Fire Smoke Impact and AQI**: Compares AQI estimates and smoke estimates (impact scores) for available years.

AQI data, focusing on **PM2.5**, was used to validate smoke estimates. Observations indicate a correlation between high smoke estimates and elevated AQI values, suggesting wildfire impact on Charleston’s air quality.

### Refelections and Visualizations writeup
'Data 512 Part 1 Reflections.pdf' contains the writeup as required for Step 3: Write and Reflect.
