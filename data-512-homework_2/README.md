# Exploring Bias in Wikipedia Data

## Project Overview
This project explores the potential biases present in Wikipedia data by analyzing the coverage and quality of articles on political figures from various countries. Using article data collected from Wikipedia and population data, we apply machine learning predictions from ORES to assess article quality. This analysis helps highlight disparities in coverage and article quality by country and region.

## Goals
Analyze Wikipedia's coverage of politicians by country and compare it to population data.
Determine the quality distribution of these articles and observe any disparities across countries and regions.
Reflect on the impact of data bias and its implications for Wikipedia and broader data science applications.

## Data Sources
- **Wikipedia Politicians by Country Data** - Crawled from Wikipedia's "Politicians by nationality" category.
- **World Population Data** - Obtained from the Population Reference Bureau, representing populations as of August 2024.
  
Both files are included in this repository:
- politicians_by_country.AUG.2024.csv
- population_by_country_AUG.2024.csv

---

## Intermediate Files

### 1. `wp_countries-no_match.txt`
- **Description**: This file lists countries present in either the Wikipedia dataset or the population dataset but missing in the other, which could not be matched during the merge.
- **Format**: Plain text file, one country per line.

### 2. `wp_politicians_by_country.csv`
- **Description**: A consolidated CSV file containing Wikipedia article information and population data, merged by country.
- **Columns**:
- `country`: Country name associated with the politician’s article (string).
- `region`: The geographic region to which the country belongs (string).
- `population`: The population of the country, in millions (float).
- `article_title`: The title of the Wikipedia article about the politician (string).
- `revision_id`: The current revision ID of the article, as retrieved from the Wikipedia API (integer).
- `article_quality`: Quality assessment of the article by ORES, with classes ranging from "FA" (Featured Article) to "Stub" (string).

---

## Considerations

- **Article Exclusions**: Articles that did not pertain to politicians, such as "David Henríquez (footballer, born 1977)," were excluded from the analysis to ensure accuracy. This filtering led to an error rate of 0% for ORES score extraction.
- **Missing Revision IDs**: Eight articles for politicians did not have a valid `revision_id` from the Wikipedia API and were therefore excluded from the analysis.
- **Data Tables**: All required data tables are embedded within the Python notebook for easy reference and analysis.
