> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.


# Richmond Maternal Data: Fast, Open, and Actionable in 48 Hours

## Executive Summary
Richmond’s core maternal and infant health outcomes, alongside tract-level Social Determinants of Health (SDOH) context, are already publicly accessible across disparate portals. However, researchers and community health workers repeatedly duplicate effort by manually pulling, cleaning, and joining these datasets while navigating complex suppression rules. 

The most promising software-shaped opportunities for a 48-hour hackathon involve building a "data backbone" rather than just another visualization. By leveraging the Virginia Department of Health (VDH) dashboards (which offer 2023 recency) [1], the Health Opportunity Index (HOI) CSVs [2], and KIDS COUNT raw data [3], teams can deliver automated aggregation scripts, indicator dictionaries, and offline-capable mapping tools. These solutions directly address the organizational pain of fragmented data, align with the 2024 Richmond & Henrico Community Health Assessment (CHA) priorities [4], and provide immediate value even if live API access fails during the event.

## Data Access Plumbing: Exactly Where to Pull What, and How
To build a sustainable data pipeline, developers must target specific, reliable endpoints across state and federal portals. 

### VDH Maternal/Infant Dashboards: 2023 Recency and Locality Filters
VDH provides comprehensive, recently updated (2023) dashboards that allow for CSV downloads and locality-level filtering. 
* **MCH Indicators**: Tracks infant mortality, late or no prenatal care, low birthweight, maternal smoking, Medicaid births, preterm birth, teen pregnancy, and WIC use during pregnancy [1]. 
* **Maternal Mortality**: Defines maternal deaths (during pregnancy or within 42 days of termination) and provides cause-of-death groupings using ICD-10 codes [5].
* **Severe Maternal Morbidity (SMM)**: Tracks 21 unexpected outcomes of labor and delivery, categorized into heart, bleeding, breathing, and kidney complications, as well as sepsis [6].
* **PRAMS (Pregnancy Risk Assessment Monitoring System)**: Provides behavioral data (e.g., pregnancy intention, breastfeeding initiation). While mostly state-level, it specifically oversamples and stratifies data for the Richmond City Health District [7].

### ACS API 2024 5-Year: Ready Variables and Geography Helpers
The U.S. Census Bureau's American Community Survey (ACS) 5-year estimates provide the demographic and economic backbone for maternal health analysis [8]. The API supports detailed tables down to the block group level and Data Profiles down to the census tract level [8]. Key tables include DP05 for sex and age demographics [9].

### KIDS COUNT VA: Raw CSVs and Suppression Notes
The Annie E. Casey Foundation's KIDS COUNT Data Center serves as a highly reliable, VDH-sourced fallback for maternal data [3]. It provides raw CSV downloads for low birthweight [3], infant mortality [10], and teen birth rates [11]. Crucially, it provides explicit metadata on data sources and suppression rules, making it an ideal source for offline hackathon builds.

### VDOE School Quality Profiles: School-Level Proxies for Early Risk
The Virginia Department of Education (VDOE) offers downloadable spreadsheets detailing chronic absenteeism, enrollment, and economically disadvantaged student populations [12]. These metrics serve as highly localized proxies for community distress and early childhood risk environments.

### HOI Tract CSV: 1,875 Tracts and 20 Fields in One File
The Virginia Health Opportunity Index (HOI) is available on the Virginia Open Data Portal as a single, comprehensive CSV [2]. It maps 1,875 census tracts across 20 indicators, including Access to Care, Affordability, Food Accessibility, Segregation, and Material Deprivation [2]. This is the ultimate "quick win" dataset for a hackathon, requiring zero API authentication.

## Risks, Gaps, and Guardrails: Preventing Small-N Leakage
Data suppression and geography mismatches are the top failure modes when combining public health data. Hackathon teams must build guardrails directly into their code.

### Small-Number Suppression and Confidentiality
To prevent the re-identification of individuals, VDH restricts data releases to de-identified aggregate data and applies strict suppression guidelines [13]. For example, in disease reporting, suppression is warranted when population sizes or case numbers are too small [14]. KIDS COUNT explicitly notes that for low birthweight data, counts less than 10 are suppressed before 2021, and counts of 20 or less are suppressed from 2021 onward, though percentages may still be reported [3]. **Action**: Scripts must automatically flag or redact small counts and handle percentages cautiously to avoid reverse-engineering suppressed numerators.

### Geography Harmonization
Maternal outcomes are typically reported by the mother's locality of residence [1], whereas SDOH data like the HOI are reported by 10-digit Census Tract FIPS codes [2]. Teams must utilize geographic crosswalks (like the HUD USPS ZIP Code Crosswalk) [15] to accurately join tract-level environmental data with locality-level health outcomes.

## Software-Shaped Opportunity Set
The following opportunities are scoped specifically for a 48-hour hackathon. They prioritize reducing duplicated effort for researchers and rely on publicly available data.

| Opportunity Name | Target User & Pain Point | Required Data Sources | Simplest Implementation | 48-Hour Demo Success Criteria |
| :--- | :--- | :--- | :--- | :--- |
| **1. Richmond MCH Offline Aggregator** *(No-API Fallback)* | **User**: Public health researchers.<br>**Pain**: Manually downloading and joining VDH and KIDS COUNT CSVs every quarter. | VDH MCH Indicators CSV [1]; KIDS COUNT Low Birthweight CSV [3]; HOI CSV [2]. | Python/Pandas script that ingests local CSVs, standardizes column names, and outputs a single tidy dataset. | A working script that takes 3 raw CSVs and outputs 1 clean, merged CSV with a basic Streamlit data table viewer. |
| **2. HOI-to-MCH Tract Risk Mapper** | **User**: Community Health Workers (CHWs).<br>**Pain**: Cannot easily see which neighborhoods have both high maternal risk and low access to care. | HOI CSV (Access to Care, Affordability) [2]; VDH MCH Indicators (Locality level) [1]. | Leaflet or Observable choropleth map coloring Richmond tracts by HOI score, overlaid with maternal outcome markers. | An interactive web map highlighting the top 10% highest-risk census tracts in Richmond for targeted CHW deployment. |
| **3. Indicator Dictionary & Query Builder** | **User**: Data scientists and grant writers.<br>**Pain**: Constantly looking up ACS table IDs and VDH definitions. | ACS 5-Year API Docs [8]; VDH Data Definitions [1] [5]. | A static MkDocs or GitHub Pages site listing exact API calls, table IDs (e.g., DP05), and VDH definitions. | A published static site where a user can copy-paste a working Python snippet to pull Richmond poverty and demographic data. |
| **4. School-to-Maternal Early Risk Connector** | **User**: Cross-sector policymakers.<br>**Pain**: Siloed data prevents seeing the link between distressed schools and maternal health. | VDOE Chronic Absenteeism CSV [12]; HOI CSV [2]; VDH Teen Pregnancy data [1]. | A dashboard plotting school absenteeism rates against tract-level material deprivation and locality teen birth rates. | A visual scatterplot or map proving the correlation between high-absenteeism school zones and low HOI scores in Richmond. |
| **5. Suppression Guardrail Library** | **User**: Hackathon developers and VDH analysts.<br>**Pain**: Accidentally publishing dashboards that violate VDH/KIDS COUNT <20 count suppression rules [3]. | Any VDH or KIDS COUNT dataset with small counts. | A Python utility function (`def apply_suppression(df, threshold=20):`) that masks low counts and adds standard footnotes. | A unit-tested Python module that successfully redacts sensitive rows from a dummy dataset before visualization. |

*Key Takeaway*: Prioritize Opportunity 1 and 2 if live API access is blocked, as they rely entirely on static CSV downloads available right now.

## Implementation Blueprint: From Zero to Demo by Sunday
To guarantee a working demo, teams should adopt a "CSV-first" ingestion strategy. 
1. **Stack**: Use Python (Pandas/Geopandas) for data manipulation. Use Streamlit or Observable for rapid, interactive front-end deployment without complex backend routing.
2. **Data Handling**: Standardize on 10-digit Census Tract FIPS codes [2] as the primary join key. Cache all API pulls locally as CSVs during development so rate limits or connectivity drops do not break the demo.
3. **Packaging**: Success on Sunday looks like a one-click run script, a published mini-site (via GitHub Pages or Streamlit Community Cloud), and a downloadable merged dataset.

## Governance and Reuse: Making it a Backbone
Hackathon projects often die on Monday. To ensure this data backbone survives, teams must document their indicator definitions, source URLs, and last-updated dates directly in the UI. The code repository must include a clear change log and instructions on how to run the monthly/quarterly update scripts when VDH or KIDS COUNT releases new data.

## Alignment with Richmond Priorities
To gain traction beyond maternal health teams, these tools must speak to broader community concerns. The 2024 Richmond & Henrico Community Health Assessment (CHA) identified violence (34.8%), chronic health conditions (32.4%), and mental health (31.9%) as the top resident concerns [4]. By overlaying maternal outcomes with HOI indicators for material deprivation [2] or mapping them alongside mental health resource deserts, the resulting software becomes a cross-functional tool for the entire health district.

## Validation and Next Steps
Post-demo, the immediate next step is to validate the aggregation logic with RHHD/VDH epidemiologists to ensure suppression rules were applied correctly. Future iterations should automate the data pulls via GitHub Actions (running weekly/monthly) and integrate additional VDH datasets, such as Neonatal Abstinence Syndrome (NAS) or overdose emergency department visits, as optional layers.

---

## Inferences and Unknowns

### Inferences (Clearly Labeled)
* **Inference**: Tract-level Social Determinants of Health (via HOI) strongly correlate with individual maternal health outcomes. *Reasoning*: While maternal data is often locality-wide, applying tract-level HOI data assumes that neighborhood-level deprivation accurately proxies the risk environment for expectant mothers living in those tracts.
* **Inference**: VDOE chronic absenteeism is a valid proxy for early childhood and family distress. *Reasoning*: High absenteeism in elementary/middle schools likely indicates broader family instability, which overlaps with the target demographic for maternal and infant health interventions.
* **Inference**: KIDS COUNT data perfectly mirrors VDH internal data. *Reasoning*: KIDS COUNT cites VDH as its source [3], so we infer the CSV downloads are a mathematically identical fallback for VDH's own dashboards.

### Unknowns
* **API Stability**: Whether the Census ACS API will experience rate limiting or downtime during the specific 48-hour hackathon window is currently unverified, necessitating the CSV-fallback approach.
* **Granular Maternal Data Availability**: VDH approval for tract-level maternal outcome data (rather than locality-level) for public dashboarding remains uncertain, given their strict confidentiality and suppression policies [13].
* **PRAMS Micro-Targeting**: While PRAMS oversamples Richmond [7], the sufficiency of the sample size to allow for cross-tabulation by both race *and* specific Richmond zip codes without triggering suppression rules is undetermined.

## References

1. *Maternal & Child Health Indicators - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/mch-indicators/
2. *Health Opportunity Index - Virginia - Health Opportunity Index (CSV) - Virginia Open Data Portal*. https://data.virginia.gov/dataset/health-opportunity-index/resource/89114d14-fccc-4833-8f3b-ca08ff8c81de
3. *Low birthweight babies | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/3252-low-birthweight-babies
4. *Community Health Assessment (CHA) - Richmond City Health Department*. https://www.vdh.virginia.gov/richmond-city/cha/
5. *Maternal Mortality - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/maternal-mortality
6. *Severe Maternal Morbidity - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/smm/
7. *Data Dashboards - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/
8. *American Community Survey 5-Year Data (2009 to 2024)*. https://www.census.gov/data/developers/data-sets/acs-5year.html
9. *DP05 ACS Demographic and Housing Estimates - Census Data*. https://data.census.gov/table/ACSDP5Y2024.DP05?g=060XX00US5115991571
10. *Infant mortality | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/6051-infant-mortality
11. *Teen birth rate per 1,000 by age group | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/3235-teen-birth-rate-per-1000-by-age-group
12. *Download Data - Virginia School Quality Profiles*. https://schoolquality.virginia.gov/download-data
13. *COMMONWEALTH of VIRGINIA*. https://www.vdh.virginia.gov/content/uploads/sites/19/2023/04/Syndromic-Surveillance-MOA-2022.pdf
14. *Data and Reports - Disease Prevention*. https://www.vdh.virginia.gov/disease-prevention/disease-prevention/hiv-aids-sexually-transmitted-disease-std-hepatitis-reports/
15. *HUD USPS ZIP Code Crosswalk Files | HUD USER*. https://www.huduser.gov/portal/datasets/usps_crosswalk.html