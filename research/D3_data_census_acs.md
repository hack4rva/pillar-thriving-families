> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# ACS building blocks for a Richmond maternal health equity dashboard

## Executive Summary
The American Community Survey (ACS) provides the foundational data required to build a comprehensive maternal health equity dashboard for Richmond. As of March 2026, the most recent 5-year dataset is the 2024 ACS (covering 2020–2024), which offers the statistical stability needed for neighborhood-level (census tract and block group) analysis [1]. 

Key insights for dashboard development include:
* **Comprehensive Coverage Data**: Tables like B27001 and B27010 provide detailed health insurance coverage status and types by age, allowing for precise tracking of uninsured rates among women of childbearing age (15–44) [2] [1].
* **Richmond Geography Support**: Richmond is fully supported as both a county-equivalent and a place, with detailed tract-level data available for equity mapping.
* **Accessible Infrastructure**: All required data can be accessed via the Census API (free key available in minutes) or downloaded directly without a key from data.census.gov [1].
* **Holistic Social Determinants**: Beyond clinical metrics, tables covering poverty, educational attainment, and employment (including parental employment constraints) provide the necessary context to identify systemic barriers to maternal care [3] [4].

## Why these ACS tables matter for Richmond maternal health
To effectively address maternal health equity in Richmond, a dashboard must track the social determinants of health that directly impact prenatal and postpartum outcomes. The 2020–2024 ACS 5-year estimates provide the optimal balance of recency and geographic granularity, enabling city-wide benchmarking and neighborhood-level targeting. 

Health insurance coverage is a primary predictor of maternal care access. By utilizing detailed ACS tables, public health strategists can isolate uninsured rates specifically for women aged 15–44 and analyze the mix of coverage types (employer-based, Medicaid, direct-purchase) for critical postpartum age groups (19–34) [2] [1]. Furthermore, integrating poverty rates, educational attainment, and employment status—particularly the employment status of parents with young children—reveals the compounding socioeconomic barriers that drive maternal health disparities [3] [4].

## Priority table inventory with Richmond applicability
These 18 ACS tables cover insurance, poverty, education, employment, and demographic disaggregation at Richmond city and tract scales. All are accessible via the Census API and data.census.gov.

| Domain | Table ID | Plain-English description | Best use for maternal health | Richmond geography supported | Most recent 5y | Access (API/data.census.gov) |
|---|---|---|---|---|---|---|
| Insurance | B27001 | Health Insurance Coverage Status by Sex by Age | Uninsured rate for women 15–44, age-specific | Place, County, Tract, Block Group | 2020–2024 | API: /2024/acs/acs5?group=B27001; data.census.gov |
| Insurance | B27010 | Types of Health Insurance Coverage by Age | Coverage mix (employer, Medicaid, direct-purchase) for 19–34 | Place, County, Tract, Block Group | 2020–2024 | API: /2024/acs/acs5?group=B27010; data.census.gov [1] |
| Insurance | C27001A–I | Coverage status by age (race/ethnicity iterations) | Race/ethnicity equity cuts for ages incl. 15–44 bins | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=C27001A; data.census.gov |
| Insurance | S2701 | Selected Characteristics of Health Insurance | Quick city/county uninsured rates, by race/age | Place, County | 2020–2024 | API: /2024/acs/acs5/subject?table=S2701; data.census.gov |
| Poverty | S1701 | Poverty Status in the Past 12 Months | Topline poverty % by age, sex, race | Place, County | 2020–2024 | API: /2024/acs/acs5/subject?table=S1701; data.census.gov |
| Poverty | B17001 | Poverty Status in the Past 12 Months by Sex by Age | Deep poverty counts by sex/age (corrected 2026-03-18: this is the correct table for poverty by age; C17001 does not exist in ACS 5-year data) | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=B17001; data.census.gov |
| Poverty | C17002 | Ratio of Income to Poverty Level | Depth-of-poverty bands (e.g., <50%) | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=C17002 |
| Education | S1501 | Educational Attainment | HS+/BA+ for adults 25+ by sex/race | Place, County | 2020–2024 | API: /2024/acs/acs5/subject?table=S1501 |
| Education | B15002 | Sex by Educational Attainment (25+) | Attainment distribution for women 25+ | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=B15002 |
| Education | B15001 | Sex by Age by Educational Attainment (18+) | Narrow to women 25–34, 35–44 | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=B15001 |
| Employment | S2301 | Employment Status | LFPR, employment-population, unemployment | Place, County | 2020–2024 | API: /2024/acs/acs5/subject?table=S2301 [4] |
| Employment | B23001 | Sex by Age by Employment Status (16+) | Detailed employment status for women 16–64 | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=B23001 [5] |
| Employment | B23008 | Age of Own Children by Parents’ Employment | Parents’ employment for under-6/6–17 | Place, County | 2020–2024 | API: /2024/acs/acs5?group=B23008 [3] |
| Demographics | B01001 | Sex by Age | Denominators for female 15–44 | Place, County, Tract, Block Group | 2020–2024 | API: /2024/acs/acs5?group=B01001 |
| Demographics | B03002 | Hispanic or Latino by Race | Race/ethnicity framework | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=B03002 |
| Demographics | B02001 | Race | Race-alone counts | Place, County, Tract, Block Group | 2020–2024 | API: /2024/acs/acs5?group=B02001 |
| Demographics | B05001 | Nativity and Citizenship Status | Foreign-born/non-citizen context | Place, County, Tract | 2020–2024 | API: /2024/acs/acs5?group=B05001 [6] |

*Richmond applicability notes:* Richmond city, VA is both a county-equivalent (state:51, county:760) and a place (state:51, place:67000). Tracts and block groups within Richmond are available for B/C tables to support neighborhood equity mapping.

## Access methods and key requirements
Acquiring the data is straightforward, with options for both automated pipelines and ad-hoc analysis.

* **API Access**: The Census API is the most efficient method for building a reproducible dashboard. 
 * **API Key**: A free API key is required for high-volume requests. You can request one at `api.census.gov/data/key_signup.html`. Typical turnaround is within minutes, though it can take up to 24 hours.
 * **Without a Key**: Small numbers of API calls generally work without a key, but they are subject to stricter rate limiting. The unauthenticated rate limit is 500 queries/day per IP address (corrected 2026-03-18). For dashboard builds making repeated pulls, request a free key to avoid hitting this ceiling.
 * **Endpoints**: Detailed tables use `/data/2024/acs/acs5`, while subject tables use `/data/2024/acs/acs5/subject`.
* **Direct Download**: Data is available without an API key via direct download from data.census.gov. Users can search for table IDs (e.g., B27010), select geographies, and export to CSV/XLSX [1]. This method includes Margin of Error (MOE) fields by default.

## Schema highlights and variable selection
To build accurate indicators, specific variables must be extracted from the broader tables.

* **Health Insurance (B27001 & B27010)**: For B27001, target labels like "Female: [age bin]: No health insurance coverage" for age bins 15–17, 18–24, 25–34, and 35–44. For B27010, variables enumerate coverage types such as "With employer-based health insurance only," "With Medicaid/means-tested public coverage only," and "With direct-purchase health insurance only" [2] [1].
* **Employment and Childcare (S2301 & B23008)**: S2301 provides Labor Force Participation Rate and Unemployment rate [4]. B23008 is critical for identifying childcare constraints, offering data on the employment status of parents with own children under 18 years, specifically isolating those with children under 6 years [3].
* **Demographics and Nativity (B05001)**: Use B05001 to contextualize coverage barriers for immigrant populations. Key variables include `B05001_006E` ("Estimate!!Total:! !Not a U.S. citizen") and naturalized citizen counts [6] [7].

## Indicator construction and calculations
Transforming raw ACS cells into dashboard KPIs requires precise numerator and denominator pairing.

* **Uninsured Rate (Women 15–44)**: Sum the "No coverage" variables for females across the 15–17, 18–24, 25–34, and 35–44 age bins from B27001. Divide by the total female population in those same age bins (using B27001 totals or B01001 for cross-validation).
* **Coverage Mix (Women 19–34)**: Calculate the share of employer-only, Medicaid-only, and direct-purchase-only coverage from B27010 for ages 19–25 and 26–34 [1]. *Note: B27010 is not sex-specific, so this serves as a population-level proxy for the maternal age cohort.*
* **Childcare Constraint Proxy**: Using B23008, calculate the percentage of parents with children under 6 who are not in the labor force, highlighting neighborhoods where childcare gaps may depress prenatal care access [3].

## Data quality, comparability, and guardrails
Working with small-area ACS data requires strict quality controls to prevent misleading conclusions.

* **Margin of Error (MOE) Handling**: ACS data are based on a sample and subject to sampling variability, represented by a 90 percent margin of error [2] [1]. Dashboard visualizations should suppress or gray out metrics where the MOE-to-estimate ratio exceeds 30%, or where the denominator is less than 200.
* **Time Comparability**: The 2024 5-year estimates reflect 2020 urban boundaries. Furthermore, health insurance coverage category names and age-categories have undergone updates in recent years [2]. Lock the dashboard baseline to 2020–2024 for small-area views to avoid cross-year boundary and definition conflicts.

## Inferences and assumptions (clearly labeled)
* **Inference**: "Most recent 5-year = 2024" corresponds to pooled years 2020–2024. This is supported by the presence of the `ACSDT5Y2024` dataset identifier [1].
* **Inference**: Maternal age is effectively proxied by ACS age bins 15–44. Postpartum risk focus often centers on the 19–34 and 35–44 cohorts, which align cleanly with B27010 and B27001 bins.
* **Inference**: Subject tables (S-series) are generally not available at the census tract or block group level. Detailed tables (B/C-series) must be used for neighborhood mapping.

## Unknowns and validation plan
* **Unknown**: The exact variable indices for B27001 female uninsured counts by specific age bins in the 2024 schema. 
 * *Validation Plan*: Resolve by programmatically reading the 2024 `/groups/B27001.html` metadata via the API and snapshotting the exact variable codes to the dashboard codebase.
* **Unknown**: Potential discrepancies between Richmond "Place" and Richmond "County-equivalent" totals due to geographic boundary nuances.
 * *Validation Plan*: Pull both Place (67000) and County (760) data for Richmond during the initial data pipeline build. Diff the totals and log any discrepancies greater than 1% to ensure consistency across dashboard views.

## Implementation roadmap
1. **Acquire Credentials**: Obtain a Census API key to enable automated, high-volume data pulls.
2. **Draft API Queries**: Construct group-based pulls for all listed tables, parameterizing geographies for Richmond Place, County, and Tracts.
3. **Build Normalization Layer**: Reshape the wide ACS tables into tidy data structures (Geography × Year × Demographic × Indicator), ensuring MOEs are attached to every estimate.
4. **Compute Indicators**: Calculate rates and confidence intervals, applying the >30% MOE suppression rule.
5. **Develop Visualizations**: Build city-level summary cards using S-tables and tract-level equity maps using B/C tables, ensuring tooltips clearly display MOEs and universe definitions.

## References

1. *B27010: Types of Health Insurance ... - Census Bureau Table*. https://data.census.gov/table/ACSDT5Y2024.B27010
2. *B27010: Types of Health Insurance ... - Census Bureau Table*. https://data.census.gov/table/ACSDT5Y2022.B27010?q=healthinsurance
3. *B23008: Age of Own Children Under ... - Census Bureau Table*. https://data.census.gov/table/ACSDT1Y2022.B23008?q=b23008
4. *S2301: Employment Status - Census Bureau Table*. https://data.census.gov/table/ACSST1Y2024.S2301
5. *B23001: Sex by Age by Employment ... - Census Bureau Table*. https://data.census.gov/table/ACSDT5Y2022.B23001?q=B23001&g=160XX00US3604243
6. *data/2021/acs/acs5/variables*. https://api.census.gov/data/2021/acs/acs5/variables.html
7. *Census Data API: /data/2020/acs/acs5/variables*. https://api.census.gov/data/2020/acs/acs5/variables.html