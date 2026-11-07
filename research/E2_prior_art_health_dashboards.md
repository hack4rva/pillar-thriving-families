> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Building Trustworthy Maternal & Community Health Dashboards for Richmond Stakeholders

## Executive Summary

To build a trusted maternal and community health data dashboard for Richmond stakeholders, developers must prioritize transparent data lineage over simplified, "black-box" metrics. The most trusted tools in the public health landscape—such as CDC WONDER, County Health Rankings & Roadmaps (CHR&R), and the City Health Dashboard—expose exactly "how the number was made" directly at the point of use. Trust is established when users can see the source dataset, the years covered, the numerator/denominator, and the specific suppression rules applied. 

Conflicting numbers across different platforms are common but usually explainable. Divergences stem from differing datasets, time windows, geographic boundaries, statistical modeling, and privacy suppression rules. Aggregators win when they maintain strict fidelity to their sources and meticulously document their transformations. For Richmond, a successful shared tool must route vital records to CDC WONDER/NCHS standards, maternal/infant indicators to PeriStats/NVSS definitions, and social determinants to the American Community Survey (ACS) and Virginia's Health Opportunity Index (HOI). 

Granularity is a major differentiator, but privacy and precision rules can break trust if mishandled. While city and regional tools excel by offering neighborhood-level specificity, strict privacy rules (like CDC WONDER's suppression of counts of 9 or fewer) must be respected and clearly communicated. Modeled estimates are highly valuable for small-area analysis but must be explicitly labeled with confidence intervals. Ultimately, Richmond's current data ecosystem is robust but fragmented across various Virginia Department of Health (VDH) portals and PDF reports. Richmond lacks a unified, citation-first portal that stitches together maternal, infant, behavioral, and social determinant data at the neighborhood scale with clear governance and reproducible exports.

## Landscape Snapshot — What trusted dashboards do differently

The most trusted tools make indicator lineage transparent, handle small numbers responsibly, and enable reproducible analysis through downloads and APIs.

### CDC WONDER anchors source data access and rules
CDC WONDER remains the baseline standard for vital records and mortality queries because of its rigorous methodology and transparent data use restrictions. It provides an ad-hoc query system for public health data, including the Natality and Linked Birth/Infant Death datasets [1] [2] [3]. WONDER builds trust by enforcing strict data suppression rules, explicitly prohibiting the publication of statistics representing nine or fewer births or deaths to protect privacy [4]. Furthermore, it ensures reproducibility by providing API options, tab-separated exports, and dynamically generated suggested citations on every results screen [5] [6].

### Aggregators for interpretation: PeriStats, CHR&R, City Health Dashboard
Top-tier aggregators add value beyond raw data through explicit methodologies, statistical weighting, and small-area smoothing. 
* **March of Dimes PeriStats** aggregates data from multiple agencies (NCHS, CDC, CMS, HRSA, Census) to provide over 60,000 graphs, maps, and tables on maternal and infant health [7] [8]. It builds credibility by stating that its calculations generally follow NCHS guidelines and are processed using SPSS/SAS software [8].
* **County Health Rankings & Roadmaps (CHR&R)** aggregates over 80 measures into composite scores for Population Health and Community Conditions [9]. It standardizes measures using Z-scores, applies scientifically informed weights, and groups counties into 10 data-informed "Health Groups" rather than using ordinal ranks, which reduces false precision [9] [10].
* **City Health Dashboard** provides over 40 measures of health and drivers of health at the city and census tract levels [11]. It maintains trust by publishing comprehensive technical documentation, including specific formulas (e.g., calculating life expectancy using Chiang’s abridged life table method) and providing a full data dictionary [12] [13] [14].

### State/local exemplars: VDH/HOI, city portals
State and local dashboards deliver vital neighborhood context by combining administrative data with clear methodologies. The Virginia Health Opportunity Index (HOI) aggregates over 30 variables into 13 indicators, grouped into four profiles, to create a single hierarchical index of social determinants of health [15]. City portals like the Chicago Health Atlas allow users to explore hundreds of indicators across 77 community areas with easy Excel/CSV downloads [16] [17] [18].

## Dashboard Inventory — What each tool shows, who it serves, and how it sources

A comparative view clarifies which tool to use for maternal versus community indicators, how they source their data, and the design choices that lend them credibility.

| Dashboard / Tool | What it Shows | Primary Users | Primary Data Sources | Indicator Definitions & Sourcing | Geography Levels | Access & Download | Design Notes & Credibility |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **March of Dimes PeriStats** | Maternal/infant indicators (preterm, LBW, infant mortality, C-section) [7] | Researchers, advocates, policymakers | NCHS/CDC, CMS, HRSA, Census [8] | NCHS-guided computations processed via SPSS/SAS [8] | State, county, city [8] | Visualizations, tables | 60,000+ charts; dedicated calculations methodology page [7] [8]. |
| **County Health Rankings (CHR&R)** | 80+ measures grouped into Health Outcomes and Health Factors [9] [10] | Community leaders, policymakers | BRFSS, NCHS, ACS, PLACES, modeled data [9] [10] | Z-scores, weighted composites, reverse coding for specific metrics [9] [10] | County [9] | CSV, SAS files [9] | Uses 10 "Health Groups" instead of ranks; highlights "Areas to Explore" [9]. |
| **CDC WONDER** | Ad hoc vital/mortality queries (Natality, Linked Birth/Infant Death) [1] [2] [3] | Epidemiologists, public health professionals | NVSS Natality, Mortality [2] [3] | Dataset-level methods; strict suppression rules [3] [4] | National, state, county | API, TSV export [5] | <=9 suppression rule; per-query dynamically generated citations [6] [4]. |
| **VDH BRFSS Indicators Dashboard** | Annual data on adult health-related behaviors [19] | Local planners, public health officials | Virginia BRFSS [19] | Small Area Estimate (SAE) methodology [19] | State, health district, county, geography [19] | Data request link [19] | Includes "About the Data" section and linked SAE methodology PDF [19]. |
| **VDH Health Opportunity Index (HOI)** | SDOH index based on 30+ variables [15] | Equity planners, researchers | ACS, administrative data [15] | 30 variables → 13 indicators → 4 profiles → 1 index [15] | Census tract, state [15] | Open data portal [15] | Hierarchical index allowing examination at multiple levels of detail [15]. |
| **VDH HealthStats (Vital Stats)** | Resident early infant and neonatal deaths, births [20] | Analysts, researchers | VDH vital records [20] | Standard vital statistics methods [20] | Locality, health district, city/county [20] | Static tables [20] | Race/ethnicity disaggregation provided. Data ceiling is 2020; use for historical reference only — not current data (corrected 2026-03-18). Primary current source is the VDH MCH Indicators Dashboard [20]. |
| **RHHD 2024 CHA** | Regional health priorities, demographics, mental health, chronic disease [21] | Cross-sector leaders, community members | Multiple public sources, local surveys [21] | Report-based methodology and community surveys [21] | Richmond City, Henrico County [21] | PDF report [21] | Extensive governance transparency; lists all CHA team members and partners [21]. |
| **City Health Dashboard** | 40+ measures of health and drivers of health [11] | City officials, researchers, advocates [11] | NVSS, ACS, modeled series [11] [12] | Per-metric technical docs (e.g., Chiang's life table method) [12] [13] | City, census tract [11] | CSV, API, Data Dictionary [11] [14] | Explicit guidance on appropriate vs. inappropriate uses of data [11]. |
| **Chicago Health Atlas** | Hundreds of indicators over time and across communities [16] [22] | Community orgs, researchers | CDPH, ACS, Healthy Chicago Survey [16] [18] | Per-indicator notes and methodology reports [18] | 77 community areas, citywide [18] | Excel, CSV [17] | "How to" guidance; allows downloading multiple indicators at once [22] [17]. |
| **NYC Environment & Health Portal** | Birth outcomes and environmental health [23] | Policymakers, advocates | NYC DOHMH vital records [23] | Per-topic methods [23] | City, borough, neighborhood | Downloads | Surfaces multiple outcomes for ~125,000 annual births rather than a single composite [23]. |
| **DC Health Matters** | 200+ health and quality of life indicators [24] | Hospitals, FQHCs, CBOs [24] | Multi-source [24] | Tracks CHNA and CHIP progress [24] | Ward, city | Web portal | Offers guidance on over 1,800 community-level interventions [24]. |

*Table 1: Inventory of maternal and community health data dashboards, detailing their scope, users, sources, and design credibility.*

## Data Provenance & Methods — Reducing "which number?" confusion

Make disagreements predictable and explainable by standardizing definitions, surfacing suppression and modeling flags, and aligning data vintages.

### Five causes of divergence and how to preempt them
When stakeholders pull "infant mortality" from three different sites and get three different numbers, trust erodes. These divergences typically stem from five factors: dataset lineage (e.g., NVSS vs. modeled surveys), time windows (single-year vs. multi-year rolling averages), geographic boundaries (census tract vs. county), small-number suppression rules, and age-adjustment applications. To preempt this, dashboards must utilize an in-line "Method Card" pattern paired with a compare toggle. This allows users to see the exact year window, geography, modeling flag, and suppression thresholds side-by-side.

### Suppression and small-area estimation done right
Handling small numbers is a critical credibility test. CDC WONDER strictly prohibits publishing statistics representing nine or fewer births or deaths to protect confidentiality [4]. CHR&R excludes counties from Health Groups if they have missing or unreliable values for premature death (e.g., standard error >20% of the estimate) [10]. For Richmond, adopting VDH's Small Area Estimate (SAE) methodology for behavioral data [19] while enforcing WONDER's <=9 suppression rule for vital records will ensure both granularity and privacy.

## Credibility Patterns — Design choices that signal trust to researchers

Eleven repeatable patterns from leading dashboards increase credibility, ensure appropriate use, and prevent data misinterpretation.

| Credibility Pattern | Description & Exemplars | Richmond Application |
| :--- | :--- | :--- |
| **Indicator Method Cards** | In-line documentation showing source, years, and formula (e.g., City Health Dashboard's life expectancy page) [12]. | Pin a one-click "Definition" popup at the widget level with numerator/denominator thresholds. |
| **Per-Result Citations** | Dynamically generated citations with timestamps on every results screen (e.g., CDC WONDER) [6]. | Include a suggested citation footer on every exported chart or dataset. |
| **Download & API with Dictionary** | Providing CSV/SAS files and comprehensive data dictionaries (e.g., CHR&R, City Health Dashboard) [10] [14]. | Ship an open API and CSV exports with query provenance and schema docs. |
| **Modeled Estimate Labels + CI** | Explicitly flagging statistical modeling and providing confidence intervals (e.g., CHR&R, VDH SAE) [10] [19]. | Apply a "Modeled estimate" tag with method summaries and CI displays. |
| **Suppression Badges** | Clear visual indicators when data is hidden for privacy or reliability (e.g., WONDER's <=9 rule) [4]. | Use badges to explain why a specific tract's data is unavailable. |
| **Definition-Locked Labels** | Using precise terminology in UI labels (e.g., "LBW <2500g" instead of just "Low Birthweight") [25]. | Enforce strict term-locking in all dashboard headers and legends. |
| **Update Logs & Timestamps** | Displaying when data was last reviewed or updated (e.g., WONDER, CHR&R) [9] [1]. | Display the next scheduled update date and the steward of record. |
| **Governance Transparency** | Publicly listing the steering committee and partners (e.g., RHHD 2024 CHA Appendix A) [21]. | Publish a Richmond Data Stewardship Council charter on the site. |
| **Dual-View Granularity** | Offering public-friendly smoothed data alongside raw data for analysts (e.g., City Health Dashboard) [11]. | Offer public tract views (multi-year rates) and authenticated researcher views. |
| **Appropriate-Use Guidance** | Explicitly stating what the data should *not* be used for (e.g., City Health Dashboard FAQ) [11]. | Provide decision pathways (e.g., "Planning snapshot" vs. "Program evaluation"). |
| **Composite Alternatives** | Grouping data rather than forcing ordinal ranks to avoid false precision (e.g., CHR&R's 10 Health Groups) [9]. | Avoid "one number to rule them all"; use domain scores or tiers. |

*Table 2: Design patterns that build trust among researchers and policymakers, with specific applications for a Richmond dashboard.*

## Richmond Needs Assessment — What exists, what's missing, what to build

Richmond has strong foundational data components, but lacks a single, indicator-level, citation-first portal unifying maternal/infant health, social determinants, and behaviors at the neighborhood scale.

### What Richmond has today
Richmond stakeholders currently rely on a fragmented ecosystem. The VDH Maternal & Child Health (MCH) Indicators Dashboard (updated October 2025, 2023 indicators) is the primary current source for maternal/child health indicators at the Richmond City level (corrected 2026-03-18). VDH HealthStats tables (data ceiling: 2020) serve as a historical supplement only [20]. The VDH Health Opportunity Index (HOI) offers a robust, tract-level view of social determinants [15]. The VDH BRFSS Indicators Dashboard provides adult health behaviors using Small Area Estimates [19]. Finally, the Richmond and Henrico Health Districts (RHHD) recently published the comprehensive 2024 Community Health Assessment (CHA), which synthesizes priorities like mental health and chronic disease [21].

### Gaps that block trust and adoption
Despite these resources, Richmond lacks a unified, interactive dashboard. The RHHD 2024 CHA is a static PDF report, limiting dynamic exploration [21]. There is limited neighborhood-level maternal indicator data available in a single view, and users must navigate multiple VDH portals to cross-reference vital stats with SDOH. Furthermore, there are unclear update cadences across these disparate sources and no public, centralized governance charter for a shared digital tool.

### What Richmond stakeholders would need to trust a shared tool
To trust a shared tool, Richmond stakeholders need a formalized Data Stewardship Council (comprising VDH, RHHD, VCU, hospital systems, and community organizations). The tool must feature an indicator catalog with locked definitions, versioned datasets with API/CSV exports, and absolute transparency regarding suppression and modeling. Finally, it needs a "most-used numbers" page specifically for maternal health that locks methods to source definitions (e.g., NVSS/PeriStats).

## Implementation Blueprint — From concept to credible shared tool

Start with high-value indicators, lock definitions to source methods, and ship governance, exports, and method cards on day one.

### Phase 1 (0–4 months): Foundation and governance
Convene the Data Stewardship Council. Select 15–20 core indicators, such as preterm birth, low birthweight, infant mortality, prenatal care, maternal mortality, HOI domain scores, and adult smoking/obesity. Define strict suppression rules (aligning with WONDER's <=9 rule) and establish modeling tags for SAE data.

### Phase 2 (4–8 months): Data pipeline and UX
Build the ETL pipelines from WONDER/NVSS, cross-check with PeriStats, and integrate ACS/HOI and BRFSS SAE data. Compute rolling 3-year rates to stabilize small-area data. Build the UI with in-line method cards, implement CSV/API downloads, and add a per-widget citation footer. Develop the "Why numbers differ" hover panel to explain divergences.

### Phase 3 (8–12 months): Neighborhood and reproducibility
Roll out census tract and community area rollups. Display Confidence Intervals (CIs) for all modeled data. Add "Reproduce this chart" code snippets (in R and Python) for researchers. Automate the update schedule and publicly post the governance charter and data change log.

## City/Regional Exemplars — What to emulate and what to avoid

Emulate tools that prioritize metric documentation and comparability guidance; avoid single-number rankings and opaque composites.

### Success patterns with examples
* **Metric Pages:** Emulate the City Health Dashboard, which dedicates full pages to explaining the calculation of metrics like life expectancy (using Chiang's abridged life table method) and lists exact data sources and years [12].
* **Health Groups over Ranks:** Emulate CHR&R's shift to 10 Health Groups, which uses k-means clustering to group counties based on similarity rather than forcing a 1-to-N ranking that implies false precision [9].
* **Neighborhood Focus with Downloads:** Emulate the Chicago Health Atlas, which provides data across 77 community areas and allows users to download multiple indicators at once via Excel or CSV [16] [17].
* **Topical Clarity:** Emulate the NYC Environment & Health Data Portal, which surfaces multiple specific birth outcomes for its ~125,000 annual births rather than hiding them behind a single maternal health score [23].

### Cautionary/failure patterns
Avoid presenting a single value without confidence intervals or context. Do not mix years or geographic boundaries without explicit labeling. Avoid over-aggregation that masks deep neighborhood disparities, and never publish modeled or imputed data without a clear "Modeled Estimate" flag.

## Inferences and Unknowns — What we assume and what we must learn

A few validated assumptions can move the project forward, but stakeholder interviews must lock down geographies, update cadences, and acceptable use policies.

### Inferences (explicitly labeled)
* **Inference:** Stakeholders prefer NVSS/CDC WONDER as the primary, authoritative source for maternal/infant counts, while PeriStats is utilized primarily for convenience, visualizations, and cross-state comparability.
* **Inference:** Neighborhood granularity is a strict requirement for local equity work; census tracts or RHHD-defined community areas will be the necessary geographic units.
* **Inference:** Researchers and policymakers will accept modeled data (like VDH BRFSS SAE) provided it is clearly labeled, accompanied by confidence intervals, and includes appropriate-use guidance.

### Unknowns to resolve
* Which neighborhood boundaries (standard census tracts vs. custom RHHD-defined communities) will serve as the canonical geography for the dashboard?
* Which 15–20 specific indicators are the absolute "day-one" must-haves for the maternal health stakeholder group?
* What are the exact update cadence expectations (quarterly vs. annual) for each dataset?
* Is there an appetite and budget for an authenticated "researcher view" that allows access to less-suppressed data under strict Data Use Agreements?
* What is the local tolerance for the inherent time lags in NVSS data versus the desire for provisional, less-verified local estimates?
* What specific data-sharing agreements are required with local hospital systems (e.g., VCU Health, Bon Secours) to access timelier maternal morbidity data?

## Appendix — Indicator-by-indicator sourcing and definitions

Lock definitions to authoritative sources to prevent metric drift and misuse across the Richmond ecosystem.

### Maternal/infant core indicators
* **Preterm Birth:** Defined as births occurring at <37 weeks gestation. Source from NVSS/CDC WONDER, ensuring alignment with PeriStats definitions [7].
* **Low Birthweight:** Defined as live births weighing <2500 grams. Source from NVSS/CDC WONDER, referencing City Health Dashboard definitions [25].
* **Infant Mortality:** Defined as deaths of children under 1 year of age per 1,000 live births. Source from the Linked Birth/Infant Death Records on CDC WONDER, strictly applying the <=9 suppression rule [3] [4].
* **Maternal Mortality:** Differentiate clearly between pregnancy-associated and pregnancy-related deaths, sourcing definitions and data from the VDH Maternal Mortality and Pregnancy-Associated Mortality Surveillance System [26] [27].

### Community/SDOH and behavior
* **Social Determinants:** Utilize the VDH Health Opportunity Index (HOI), maintaining its hierarchical structure (30+ variables into 13 indicators into 4 profiles) sourced from the ACS [15].
* **Behavioral Risks:** Source adult behaviors (smoking, obesity) from the VDH BRFSS Indicators Dashboard, explicitly noting the use of Small Area Estimate (SAE) methodology and displaying confidence intervals [19].

## References

1. *CDC WONDER*. https://wonder.cdc.gov/
2. *Natality Information*. https://wonder.cdc.gov/natality.html
3. *Infant Deaths - Linked Birth / Infant Death Records on CDC WONDER*. https://wonder.cdc.gov/lbd.html
4. *Data Use Restrictions *. https://wonder.cdc.gov/datause.html
5. *General Help for CDC WONDER*. https://wonder.cdc.gov/wonder/help/main.html
6. *FAQs -- Frequently Asked Questions*. https://wonder.cdc.gov/wonder/help/faq.html
7. *Home | PeriStats | March of Dimes*. https://www.marchofdimes.org/peristats/
8. *Calculations | PeriStats | March of Dimes*. https://www.marchofdimes.org/peristats/about-us/calculations
9. *CHRR Technical Documentation 2025_2.pdf*. https://www.countyhealthrankings.org/sites/default/files/media/document/CHRR%20Technical%20Documentation%202025_2.pdf
10. *County Health Rankings & Roadmaps Technical ...*. https://www.countyhealthrankings.org/sites/default/files/media/document/2024%20CHRR%20Technical%20Document_1.pdf
11. *FAQ | City Health Dashboard*. https://www.cityhealthdashboard.com/faq
12. *Life Expectancy - City-Level | City Health Dashboard*. https://www.cityhealthdashboard.com/metric/life-expectancy-city-level
13. *Technical Document | City Health Dashboard*. https://www.cityhealthdashboard.com/technical-documentation
14. *City Health Dashboard Data Dictionary*. https://assets.ctfassets.net/2b49co28d55u/3PObt33s5l6PjICO2myubP/1fa3db91625d93144a36dee32822d770/READ_ME_City_Health_Dashboard_Data_Dictionary_12-09-2025.pdf
15. *Health Opportunity Index - Virginia - Dataset - Virginia Open Data Portal*. https://data.virginia.gov/dataset/health-opportunity-index
16. *Chicago Health Atlas*. https://chicagohealthatlas.org/
17. *Download Data | Chicago Health Atlas*. https://chicagohealthatlas.org/download
18. *
    City of Chicago :: HCS Data & Documentation
*. https://www.chicago.gov/city/en/depts/cdph/supp_info/healthy-communities/hcs-data-and-documentation.html
19. *Indicators Dashboard - Data*. https://www.vdh.virginia.gov/data/health-behavior/indicators/
20. *Statistical Reports and Tables*. https://apps.vdh.virginia.gov/HealthStats/stats.htm
21. *2024 Community Health Assessment*. https://www.vdh.virginia.gov/content/uploads/sites/119/2025/04/2024-Richmond-and-Henrico-CHA.pdf
22. *How to Use the Chicago Health Atlas*. https://chicagohealthatlas.org/how-to
23. *Birth outcomes data for NYC*. https://a816-dohbesp.nyc.gov/IndicatorPublic/data-explorer/birth-outcomes/
24. *DC health matters: An innovative, community-driven health dashboard in response to affordable care act requirements*. https://www.researchgate.net/publication/266813158_DC_health_matters_An_innovative_community-driven_health_dashboard_in_response_to_affordable_care_act_requirements
25. *Metrics Background | City Health Dashboard*. https://www.cityhealthdashboard.com/metrics
26. *Virginia Department of Health - Data Portal*. https://www.vdh.virginia.gov/data/
27. *Maternal Health Data Sources - Maternal Health*. https://www.vdh.virginia.gov/maternal-health/maternal-health-data-sources