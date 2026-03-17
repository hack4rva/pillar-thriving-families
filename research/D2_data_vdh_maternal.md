# Virginia Maternal Health Data Playbook: Pinpointing Richmond-Ready Indicators

## Executive Summary
For researchers building a maternal health indicator dashboard focused on Richmond, Virginia Department of Health (VDH) data offers robust coverage with notable structural caveats. **Coverage is uneven but highly usable**: birth outcomes, infant mortality, and prenatal care are readily available at the Richmond City level via the Maternal & Child Health (MCH) Indicators dashboard and historical HealthStats tables [1] [2]. However, maternal mortality and severe maternal morbidity data often suppress locality-level detail because annual counts frequently fall below VDH's strict suppression threshold of 20 [3] [4]. 

To build a continuous pipeline, researchers must bridge a "format divide." Newer interactive dashboards (updated in late 2025 with 2023 data) provide clean CSV exports, while legacy HealthStats tables (currently lagging at 2020) require extracting data from Excel and PDF files [1] [2]. A major strategic advantage for Richmond is the Pregnancy Risk Assessment Monitoring System (PRAMS); Richmond City Health District is one of only two districts in the state that PRAMS oversamples, providing exclusive, high-resolution behavioral and risk-factor data unavailable for most other Virginia localities [5].

## 1. Data Asset Map — What VDH Publishes and Where
Every required maternal indicator exists within the VDH ecosystem, but the data is distributed across multiple distinct products, portals, and file types. 

### Core VDH Data Portals and Dashboards
| Data Source / Portal | Key Indicators Provided | Format | Geographic Level |
| :--- | :--- | :--- | :--- |
| **MCH Indicators Dashboard** | Infant mortality, late/no prenatal care, low birthweight, preterm birth, Medicaid births, WIC use, teen pregnancy [1]. | Web, CSV | County/City (Maternal residence) [1] |
| **Maternal Mortality Dashboard** | Maternal deaths (during pregnancy or within 42 days postpartum) [3]. | Web, CSV | State, Health District (Locality often suppressed) [3] |
| **Pregnancy-Associated Deaths** | Deaths within 365 days of pregnancy end, manner/cause of death [4]. | Web, CSV | State, Health District [4] |
| **VA PRAMS Dashboards** | Maternal experiences, behaviors, and risk factors before, during, and after pregnancy [5]. | Web, CSV | State, Richmond City Health District, Blue Ridge Health District [5] |
| **HealthStats (Vital Stats)** | Live births, infant deaths, low/very low birthweight, teenage pregnancies [2]. | PDF, Excel | City/County, Planning District, Health District [2] [6] |
| **MMRT Annual Reports** | Detailed cause-of-death analysis, racial disparities, preventability [7]. | PDF | Statewide [7] |

**Takeaway:** The dashboard architecture should rely on the MCH Indicators Dashboard for the primary automated CSV data feed, utilizing HealthStats PDFs and Excel files strictly for historical backfilling.

## 2. Geographic Resolution — From State to Planning District
Richmond City data is robust for high-frequency events (births) but fragile for rare events (maternal deaths). A multi-tiered geographic strategy is required to prevent empty dashboard tiles.

### County/City Availability & Suppression Thresholds
Live births, preterm births, and prenatal care metrics are reliably reported at the Richmond City level [1] [2]. VDH assigns this data based on the mother's normal city or county of residence at the time of birth, regardless of where the delivery occurred [1]. Infant deaths are similarly reported based on the infant's residence at the time of death [1]. 

### Health-District View (Richmond City HD)
For survey data, the Richmond City Health District (RCHD) is a premium asset. Because PRAMS is a state-based survey that specifically oversamples RCHD, researchers can extract statistically significant behavioral data specifically for Richmond—a level of granularity not available for most of Virginia [5].

### Planning-District Tables and Crosswalks
When Richmond City counts are suppressed, Planning District data serves as the best fallback. HealthStats publishes detailed PDF tables, such as "Resident Low Weight Live Births and Very Low Weight Births by Race by Planning District and City or County" [6]. Richmond City is located within Planning District 15, which can be used as a regional proxy when city-level data is unavailable [6].

## 3. Temporal Coverage & Refresh Cadence
There is a significant divergence in data vintage between the modern dashboards and the legacy statistical reports. 

| Data Source | Most Recent Data Vintage | Last Updated | Update Frequency / Lag |
| :--- | :--- | :--- | :--- |
| **MCH Indicators** | 2023 | September 16, 2025 [1] | ~1.5 to 2-year lag [1] |
| **Maternal Mortality** | 2019–2023 (Aggregated) | October 28, 2025 [3] | Rolling multi-year aggregates [8] |
| **Pregnancy-Associated Deaths** | 2018–2022 (Aggregated) | October 10, 2025 [4] | Rolling multi-year aggregates [8] |
| **MMRT Annual Report** | 2022 | February 20, 2025 [7] | ~2.5-year lag [7] |
| **HealthStats Tables** | 2020 | Varies (Legacy) [2] | Currently stalled at 2020 [2] |

**Takeaway:** Expect a 1.5 to 2-year lag for dashboard data. *Inference:* The HealthStats portal appears to have suffered a severe processing backlog (likely due to the pandemic), as its tables abruptly stop at 2020 [2].

## 4. Schema Consistency & Join Keys
VDH maintains a relatively consistent demographic schema across its modern dashboards, which enables researchers to join datasets using standard keys.

### Core Fields Across Sources
* **Geography:** City/County of residence [1].
* **Temporal:** Year of birth/death [1].
* **Indicator Definitions:** Standardized (e.g., Preterm birth = <37 weeks gestation; Low birthweight = <2,500 grams; Late/no prenatal care = none or started in 3rd trimester) [1].

### Race/Ethnicity Handling Limitations
VDH utilizes a strict, standardized race and ethnicity schema based on U.S. Census single-race categories [1]. 
* **Ethnicity:** Only two classes are recognized: Hispanic and Non-Hispanic [1]. 
* **Race:** Reported as the race of the mother at the time of birth, or the decedent at the time of death [1]. 
* **Limitation:** Because Hispanic is treated as an ethnicity where a person "may be of any race," intersectional analyses (e.g., isolating "Non-Hispanic Black" vs "Hispanic Black") may require careful handling depending on the specific cross-tabulations VDH exposes in the CSV downloads [1].

## 5. Data Quality & Suppression Caveats
Data quality is generally high, but strict privacy rules create artificial gaps in time-series data.

### Suppression Logic (<20 counts)
VDH enforces a strict suppression rule: **Counts lower than 20 and their associated rates should be interpreted with caution** and are frequently removed or masked from public tables to protect privacy [1] [3] [4]. Unknown or unreported variables are also removed from display tables, though they are included in overall state counts [1] [3].

### Validation Checks & Error Patterns
Previous year data in the mortality dashboards are explicitly marked as "not final" and may change as maternal deaths undergo additional quality checks, which can alter the underlying cause of death and shift the total counts [3]. 

### Mitigation Tactics
*Inference:* Because Richmond City's infant and maternal death counts may oscillate around the 20-count threshold, the dashboard will show false "zeroes" or gaps in certain years. Researchers must implement 3-year or 5-year rolling averages for mortality metrics to smooth out suppression gaps and provide accurate trend lines.

## 6. Integration Plan for the Maternal Health Dashboard
To build a resilient dashboard, researchers should implement a two-tier data ingestion pipeline.

### Source-Specific ETL Steps
1. **Primary Feed (Automated):** Connect to the VDH MCH Indicators, Maternal Mortality, and Pregnancy-Associated Deaths dashboards. Extract the underlying CSVs for 2021-2023 data [1] [3] [4].
2. **Secondary Feed (Manual/Scripted):** Download the 2010-2020 historical data from the HealthStats portal. This will require writing Python/R scripts to parse multi-tab Excel files (e.g., `2018Pop.xls`) and OCR tools to extract tabular data from legacy PDFs (e.g., `birth_1-10_2019.pdf`) [2] [6].
3. **Qualitative Overlay:** Extract narrative insights from the MMRT PDFs (e.g., the fact that Black women in Virginia die from cardiac causes at a rate of 26.6 per 100,000 vs 5.8 for White women) to provide context in dashboard tooltips, rather than attempting to scrape the PDF for quantitative time-series data [7].

### Front-End Display Rules
The dashboard must include clear tooltips explaining VDH's suppression rules. When a metric for Richmond City drops below 20, the UI should automatically offer the user a toggle to view the "Planning District 15" or "Richmond City Health District" aggregate to maintain analytical continuity [5] [6].

## 7. Unknowns & Follow-ups
While the public data inventory is extensive, a few critical unknowns require direct follow-up with the VDH Vital Event Statistics Program:

* **The 2021-2022 HealthStats Gap:** It is unknown if the granular city/county Excel tables for 2021 and 2022 will be published retroactively, or if the interactive dashboards have permanently replaced the annual PDF/Excel report volumes [2]. 
* **Custom Data Requests:** VDH explicitly offers a "Request Data" form for metrics not found in the dashboards [1]. Researchers should submit a request to see if VDH will provide unsuppressed Richmond City data under a strict Data Use Agreement (DUA) for research purposes, bypassing the public <20 suppression rule.

## References

1. *Maternal & Child Health Indicators - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/mch-indicators/
2. *Fetched web page*. https://apps.vdh.virginia.gov/HealthStats/stats.htm
3. *Maternal Mortality - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/maternal-mortality/
4. *Pregnancy-Associated Deaths - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/pregnancy-associated-deaths/
5. *Data Dashboards - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/
6. *TABLE 10 RESIDENT LOW WEIGHT LIVE BIRTHS AND ...*. https://apps.vdh.virginia.gov/HealthStats/documents/pdf/birth_1-10_2019.pdf
7. *2024 Virginia Maternal Mortality Review Team Annual Report*. https://www.vdh.virginia.gov/content/uploads/sites/233/2024-Virginia-Maternal-Mortality-Review-Team-Annual-Report.pdf
8. *Maternal & Child Health - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/