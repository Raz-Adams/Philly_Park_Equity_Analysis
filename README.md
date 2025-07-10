# Green Spaces and Income Gaps: Mapping Philadelphia's Park and Recreation Equity

![Bivariate Map of Park Access and Income](Parks%20&%20Rec%20Equity%20Map%201.png)

## Project Overview

This project uses spatial analysis techniques in Esri ArcGIS Pro to investigate the urban question: **Is access to public parks in Philadelphia equitable across communities of different income levels?**

By joining neighbourhood-level income data with park and recreation centre locations, this analysis creates a comprehensive picture of "park equity." While the maps visually suggest a pattern where wealthier areas have better park access, a deeper statistical analysis reveals a more nuanced reality: the relationship is not a simple linear correlation. Instead, Philadelphia's park access is highly polarised, with a majority of neighbourhoods having excellent access while a significant number are left underserved, creating a distinct "have vs. have-not" dynamic.

## Data Sources

*   **Neighborhood Boundaries:** [Philadelphia Neighborhoods](https://www.opendataphilly.org/dataset/philadelphia-neighborhoods) via OpenDataPhilly.
*   **Park Locations:** [PPR Properties](https://www.opendataphilly.org/dataset/ppr-properties) via OpenDataPhilly.
*   **Median Household Income:** [U.S. Census Bureau](https://www.census.gov/programs-surveys/acs) American Community Survey (ACS) 5-Year Estimates.

## Methodology

The analysis was conducted using **Esri ArcGIS Pro** and involved the following key steps:

1.  **Data Preparation:** Median household income data (tabular) was joined to the neighbourhood polygons (spatial) using a common name field.
2.  **Defining Access:** A **Buffer** of a half-mile (a proxy for a 10-minute walk) was created around all park polygons. These buffers were dissolved into a single "park access zone."
3.  **Quantifying Access:** The **Intersect** tool was used to find the parts of each neighbourhood that fell within the park access zone.
4.  **Calculating the Metric:** The area of this intersected portion was calculated and expressed as a percentage of the neighbourhood's total area, resulting in a final **`Percent Access`** field.

## Results and Discussion

The findings are presented through a combination of maps for spatial visualisation and charts for statistical validation.

### Spatial Patterns of Disparity

The thematic and bivariate maps clearly illustrate the geographic distribution of both income and park access. There are strong visual correlations in areas like Northwest Philadelphia and Center City (High Income/High Access) and in parts of North and Southwest Philadelphia (Low Income/Low Access).

![Side-by-side Thematic Maps](Parks%20&%20Rec%20Equity%20Thematic%20Map%201.png)

### The Statistical Story: A Weak Correlation

While the maps suggest a link, a scatter plot was created to test the statistical relationship between income and park access.

![Scatter Plot of Income vs. Park Access](Park%20Equity%20Relationship%20Chart.jpg)

The resulting **R-squared value is 0.03**. This is a surprisingly low value, indicating that a simple linear model of income can only explain 3% of the variation in park access. This weak correlation suggests that while a visual relationship exists, income alone is not the sole or primary predictor of park access in Philadelphia when measured this way.

### The Real Story: A Polarised City

The histogram of park access reveals why the correlation is so weak.

![Histogram of Park Access](Park%20Equity%20Histogram.jpg)

The chart shows a heavily skewed distribution. A vast majority of neighbourhoods have nearly 100% access, confirmed by the **median access value of 99.9%**. This creates the large cluster of points at the top of the scatter plot, which flattens the trendline. The key takeaway is not a gradual decline in access with income, but rather a city where most are well-served, while a significant "long tail" of neighbourhoods are left with very limited access.

## Conclusion

This project successfully quantifies park access across Philadelphia and reveals a complex story of equity. While there are clear visual overlaps between wealthy neighbourhoods and high park access, the relationship is not a simple linear one. The city's extensive park system provides excellent access to a majority of neighbourhoods across various income levels. The primary equity issue identified by this analysis is the significant number of underserved neighbourhoods that form a "long tail" in the distribution, existing as park deserts regardless of the city-wide average. Upon closer inspection, we realise that some of these low-income areas are low-population areas and have very little to no income recorded.

## Limitations and Future Work

*   This analysis uses a straight-line buffer. A future project using **Network Analysis** would provide a more realistic measure of walkability based on actual street networks.
*   The study does not account for park **quality, size, amenities, or safety**, which are critical components of true recreational equity.

---
*Analysis and Cartography by Adams Abdul-Razaak, July 2025*
