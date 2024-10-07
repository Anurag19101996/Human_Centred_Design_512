# Monthly Wikipedia Article Traffic Analysis for Rare Diseases

## Project Goal
The goal of this project is to analyze monthly views for selected rare disease articles on Wikipedia across desktop, mobile web, and mobile app access platforms, from July 1, 2015, to September 30, 2024. This analysis aims to provide insights into patterns in Wikipedia page requests for articles related to rare diseases.

## Source Data and Licensing

- **Source Data License**: Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0) and GNU Free Documentation License (GFDL).
- **Wikimedia Foundation Terms of Use (ToU)**: [Link to Wikimedia TOU](https://foundation.wikimedia.org/wiki/Terms_of_Use)

### Summary of How TOU Applies
The dataset created through this project is based on public traffic data provided by Wikimedia. Per the ToU:
- **Attribution**: Wikimedia must be credited as the source.
- **Share-Alike Requirement**: Any modified or derived versions of this dataset must be shared under similar open licenses.

### API Documentation
The data was obtained via the Wikimedia Pageviews API. The API documentation is available [here](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews).

## Generated Files

### Intermediate and Final Output Files
1. **rare-disease_monthly_mobile_2015070100-2024100100.json**  
   - **Description**: Monthly page views for selected rare disease articles accessed on mobile (app and web).
   - **Schema**:
     ```json
     {
       "article_title": [
         {
           "project": "en.wikipedia",
           "article": "article_title",
           "granularity": "monthly",
           "timestamp": "YYYYMMDDHH",
           "access": "mobile-app/mobile-web",
           "agent": "user",
           "views": integer
         }
       ]
     }
     ```

2. **rare-disease_monthly_desktop_2015070100-2024100100.json**  
   - **Description**: Monthly page views for selected rare disease articles accessed on desktop.
   - **Schema**:
     ```json
     {
       "article_title": [
         {
           "project": "en.wikipedia",
           "article": "article_title",
           "granularity": "monthly",
           "timestamp": "YYYYMMDDHH",
           "access": "desktop",
           "agent": "user",
           "views": integer
         }
       ]
     }
     ```

3. **rare-disease_monthly_cumulative_2015070100-2024100100.json**  
   - **Description**: Combined monthly views for desktop and mobile access.
   - **Schema**:
     ```json
     {
       "article_title": [
         {
           "project": "en.wikipedia",
           "article": "article_title",
           "granularity": "monthly",
           "timestamp": "YYYYMMDDHH",
           "agent": "user",
           "views": integer
         }
       ]
     }
     ```

4. **avg_views_time_series.png**  
   - **Description**: Time series plot showing articles with the highest and lowest average page requests for desktop and mobile access.
   - **Details**: Contains four lines (max desktop, min desktop, max mobile, min mobile).

5. **top_10_peak_time_Series.png**  
   - **Description**: Time series plot showing the top 10 articles by peak monthly page views for desktop and mobile access.
   - **Details**: Shows the 10 articles with the highest peak values for desktop and mobile access (20 lines total).

6. **least_10_months_time_series.png**  
   - **Description**: Time series plot for the 10 articles with the fewest months of available data, separated by desktop and mobile access.
   - **Details**: Highlights articles with the fewest months of data.
  
7. **DATA512-HW1-Anuraga.ipynb**
   - Python notebook to process the code for data extraction from API as well as the required analysis and time series charts.

## Known Issues and Special Considerations

1. **Data Gaps**: Some articles may have missing data for certain months, which could impact time series completeness.
2. **Large File Size**: JSON files exceed GitHub's recommended maximum file size (50 MB). Use Git Large File Storage (LFS) for storing and managing these files efficiently.
3. **Access Type Considerations**: The `access` field was removed from the cumulative file due to potential misinterpretation.
4. **Date Range Limitations**: Data was collected from July 1, 2015, through September 30, 2024, which restricts trend analysis to this time frame.
5. **API not working for articles with '/'**: Some articles had a '/' in their name and the API did not extract data (views) for them. They were skipped for this analysis. Example - Cystine/glutamate transporter.
