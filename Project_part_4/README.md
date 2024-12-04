# Warning Charleston Council and Citizens About the Impact of Forest Fires on Healthcare

## Introduction
This repository hosts the Wildfire Smoke Impact Analysis, focusing on evaluating the annual impacts of wildfire smoke on Charleston, South Carolina over the last 60 years. This project aims to estimate the effects of wildfire smoke on air quality and explore its broader implications on public health, particularly life expectancy and mortality rates in the region.

## Project Overview
The project is structured into multiple parts, with Part 1 being the foundational analysis common across different cities. Each participant applies this analysis to their assigned city using unique data subsets. For Charleston, the goal is to create annual smoke impact estimates from 1961-2021 and correlate these with AQI and health metrics.

This repository includes:

- **Data Acquisition:** Collection and processing of wildfire data within a 650-mile radius of Charleston.
- **Smoke Estimate Calculation:** Annual smoke impact estimates based on fire size and proximity.
- **Comparison with AQI and Health Data:** Validation of smoke estimates against EPA AQI data and health outcomes.
- **Visualizations:** Time series and histograms depicting trends and correlations.
- **Reflection on Collaboration:** Insights and contributions from team efforts.

## Dataset

### Primary Data
- **Wildfire Data:** From the US Geological Survey’s Combined Wildland Fire Polygons Dataset (1800s-Present).
- **AQI Data:** Particulate matter data from the EPA Air Quality System (AQS).

### Health Metrics
- **Life Expectancy and Mortality Data:** Sourced from the Institute for Health Metrics and Evaluation (IHME), detailing the effects of environmental factors on public health in Charleston from 2000 to 2019. [Access the data here](https://ghdx.healthdata.org/record/ihme-data/united-states-causes-death-life-expectancy-by-county-race-ethnicity-2000-2019).

### Data Filtering
Analysis includes fires within a 650-mile radius and during the typical fire season months (May to October).

## Prerequisites
- **EPA API Key:** Necessary for accessing detailed AQI information from the EPA AQS.

## Usage
- **HCDE_PROJECT_PART1.ipynb:** Executes data processing and initial analysis.
- **HCDE_PROJECT_PART2.ipynb:** Extended analysis incorporating health metrics and additional correlations, with normalized graphical representations.

## Extended Analysis in HCDE_PROJECT_PART2.ipynb: Focus on Health Metrics

The extended analysis in `HCDE_PROJECT_PART2.ipynb` delves deeper into the public health implications of wildfire smoke by examining life expectancy and mortality rates in Charleston. These health metrics were chosen due to their broad implications for community health and their sensitivity to environmental factors like air quality.

### Initial Hypothesis and Findings
The initial hypothesis proposed that as smoke estimates increase, life expectancy would decrease, while mortality rates would rise. This hypothesis is based on the known adverse health effects of prolonged exposure to particulate matter, such as respiratory and cardiovascular diseases, which can reduce lifespan and increase mortality.

The actual data analysis covering the years 1961 to 2021 supported this hypothesis:
- **Correlation between smoke estimate and mortality:** Positive correlation of 0.4947584341961076, indicating that higher smoke estimates are associated with increased mortality rates.
- **Correlation between smoke estimate and life expectancy:** Negative correlation of -0.3536624667580646, suggesting that increased smoke exposure correlates with decreased life expectancy.

These correlations validate the hypothesis that worsening air quality due to wildfire smoke has detrimental effects on public health, justifying the selection of these health metrics for detailed analysis.

### Predictive Model and Unexpected Results
The predictive model used in the analysis projected future values for life expectancy and mortality based on past smoke impact estimates. However, the predictions showed an unexpected trend:
- **Predicted Correlation between smoke estimate and mortality:** Calculated correlation was unexpectedly lower or even negative compared to the historical positive correlation, suggesting an anomaly or a potential shift in trend that the model did not capture.
- **Predicted Correlation between smoke estimate and life expectancy:** Similarly, the correlation was opposite of expected, indicating an increase in life expectancy with higher smoke estimates, which contradicts known health impacts.

### ARIMA Model Explanation
The ARIMA (AutoRegressive Integrated Moving Average) model was selected for its suitability in univariate time series forecasting, which is ideal for predicting future trends based on historical data. The model's use was inspired by the methodology detailed in the scientific literature on time series analysis of environmental data, specifically for forecasting air quality and its health impacts. [Reference to the methodology](https://www.sciencedirect.com/science/article/abs/pii/S2352938522000696).

These unexpected results from the predictive model may highlight limitations in the model's ability to accurately forecast complex health outcomes over time, especially when influenced by various confounding factors like improvements in healthcare, changes in population demographics, or environmental policy adjustments.

### Reflection on Methodology and Predictive Challenges
The discrepancies between actual and predicted correlations underscore the need for refined modeling techniques and consideration of external variables. These might include socioeconomic changes, healthcare advancements, and policy measures that could mitigate the adverse effects of wildfire smoke on public health.

The extended analysis not only reaffirms the immediate impacts of wildfire smoke on health as evidenced by the actual data but also emphasizes the challenges in predicting long-term trends in health outcomes. This complexity highlights the importance of continuous monitoring and updating of models to reflect real-world changes and ensure the accuracy and relevance of predictions used for public health planning and policy-making.

By examining these dynamics, the extended analysis provides valuable insights into the short-term and potential long-term health impacts of wildfire smoke, reinforcing the necessity for proactive public health measures and informed policy interventions to protect the vulnerable populations of Charleston.

## Additional References
- Charleston's susceptibility to forest fires: [First Street Foundation](https://firststreet.org/city/charleston-sc/4513330_fsid/fire)
- Historical wildfire impacts in South Carolina: [SC Forestry Commission](https://www.scfc.gov/protection/fire-burning/fire-resources/wildfire-history/)
