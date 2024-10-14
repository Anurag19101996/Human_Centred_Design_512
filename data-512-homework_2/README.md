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
## Addressing Questions

### What biases did you expect to find in the data (before you started working with it), and why?

I expected that countries with very small populations or remote geographic locations (either politically or geographically) would have limited article coverage. The reason for this expectation is that media and contributors may focus on more prominent, easily accessible regions where news coverage and information are more readily available. This could lead to a bias where countries with significant global influence or media presence have more articles on Wikipedia, while smaller or isolated countries may be underrepresented due to the challenges in gathering or verifying information.

### What might your results suggest about (English) Wikipedia as a data source?

I expected that larger countries, whether in terms of geography or population, would have more coverage of politicians on Wikipedia. However, the fact that countries like China and India appear in the bottom 10 for coverage challenges this expectation. Additionally, European regions consistently rank the highest in both overall coverage and high-quality coverage, suggesting that Wikipedia contributors may have a bias towards European countries. This could indicate a Western-centric bias in Wikipedia's representation, potentially due to the demographics of its contributors or accessibility challenges in other regions.

### Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases?

If the analysis is focused specifically on European countries, this dataset could be quite suitable since the data coverage and quality appear to be robust for this region. The high volume and quality of information on European politicians in Wikipedia would allow for accurate insights and modeling for Europe-centric studies, making it a reliable data source for region-specific analyses.

### Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?

This dataset may not be suitable for research or modeling focused on Asian countries, as coverage and high-quality articles for this region are limited, with Asian region ranking among the lowest. Relying on this dataset for insights or decisions about Asian countries could lead to biased or misleading results, as the dataset does not adequately represent this region's political figures or events.

---
## Considerations

- **Article Exclusions**: Articles that did not pertain to politicians, such as "David Henríquez (footballer, born 1977)," were excluded from the analysis to ensure accuracy. This filtering led to an error rate of 0% for ORES score extraction.
- **Missing Revision IDs**: Eight articles for politicians did not have a valid `revision_id` from the Wikipedia API and were therefore excluded from the analysis.
- **Data Tables**: All required data tables are embedded within the Python notebook for easy reference and analysis.
