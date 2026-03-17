# Who Uses Richmond's Maternal Data—and What a Trusted Tool Must Do

## Executive Summary

Richmond’s maternal health data ecosystem is rich but highly fragmented, creating significant friction for the professionals working to improve outcomes. Currently, users must navigate a maze of state dashboards, restricted hospital databases, and national report cards that often present conflicting figures due to differing methodologies and reporting lags. For example, the Virginia Department of Health (VDH) reports a 2023 preterm birth rate of 9.8% [1], while the 2025 March of Dimes Report Card cites 10.1% for 2024 [2]. 

This fragmentation erodes confidence and drains resources. Analysts and program coordinators spend hours manually reconciling definitions—such as distinguishing maternal deaths (within 42 days of pregnancy) [3] from pregnancy-associated deaths (up to 365 days postpartum) [1]. Furthermore, critical local insights require stitching together state-level dashboards, local oversamples like the Pregnancy Risk Assessment Monitoring System (PRAMS) for the Richmond City Health District (RCHD) [4], and program-specific data. To be adopted, a shared data coordination tool must normalize these definitions, clearly display data provenance, and offer a dual-mode user experience that caters to both seasoned epidemiologists and occasional grant writers.

## Who Will Use the Tool and Why

The primary users of a Richmond maternal health data tool span a spectrum of technical expertise and organizational missions. They range from power analysts who need raw microdata to program coordinators who need fast, credible figures for grant applications. 

| Persona | Goals & Core Tasks | Current Workflow & Data Sources | Pain Points | Success Criteria for a Shared Tool |
| :--- | :--- | :--- | :--- | :--- |
| **City/Health District Epidemiologist** (e.g., RCHD/VDH) | Monitor population health, evaluate interventions, and produce official reports like the Community Health Assessment (CHA). | Pulls from VDH MCH dashboards, PRAMS microdata, and vital statistics. Aggregates data by locality and demographics. | Frustrated by provisional data flags [3] and the inability to easily link outpatient prenatal/postpartum outcomes due to a lack of a comprehensive outpatient database [5]. | Ability to run custom queries, access reproducible notebooks, and export data with clear methodological documentation. |
| **Health System Quality Analyst** (e.g., VCU Health, Bon Secours) | Track clinical quality measures, benchmark against state averages, and monitor Severe Maternal Morbidity (SMM). | Uses internal EHR data and VHHAAnalytics.com for inpatient metrics (C-sections, SMM, AHRQ measures) [5]. | VHHA data is member-restricted [5], making it hard to share findings with community partners. True mortality is hard to measure post-discharge [5]. | Secure, HIPAA-compliant environment to benchmark internal quality metrics against regional public health data without violating data sharing restrictions. |
| **Advocacy Nonprofit Researcher** (e.g., Birth in Color RVA) | Highlight racial disparities, advocate for policy changes, and publish equity-focused reports. | Relies on March of Dimes Report Cards [2], VDH dashboards [6], and the Virginia Community Health Improvement Data Portal [7]. | State-level data often lacks neighborhood-level granularity. Discrepancies between sources (e.g., MoD vs. VDH) complicate narrative building. | Pre-built equity modules that calculate rate ratios, map social determinants of health (SDOH) by zip code, and generate narrative-ready visuals. |
| **Program Coordinator / Grants Lead** (e.g., Urban Baby Beginnings) | Secure funding, plan community interventions, and report on program impact. | Manually copies/pastes fast facts from VDH [1] and local program data (e.g., WIC serving 8,500/month) [8]. | Overwhelmed by complex dashboards. Struggles to know which "latest year" is stable vs. provisional. Lacks time for deep analysis. | A "Quick Facts" builder that exports grant-ready, cited statistics in under 5 clicks, with opinionated defaults for the most reliable metrics. |

*Takeaway: A successful tool cannot be one-size-fits-all; it must offer a "Quick Facts" interface for coordinators and an "Analyst Mode" for epidemiologists, ensuring both speed and depth.*

## The Data Ecosystem Richmond Teams Actually Use

Richmond teams currently rely on a patchwork of public and restricted data sources. While public dashboards cover most statewide needs, locality-specific insights or microdata require navigating restricted channels or utilizing proxy indicators.

| Data Source | Owner | What it Contains | Access Level | Typical Uses |
| :--- | :--- | :--- | :--- | :--- |
| **VDH MCH Dashboards** | VDH | Birth/death certificates, inpatient hospitalizations, PRAMS, pregnancy-associated mortality [6] [1]. | Public | General population health tracking, fast facts (e.g., 92,639 live births in 2023) [1]. |
| **VA PRAMS** | VDH / CDC | Maternal experiences before, during, and after pregnancy. Oversamples RCHD and Blue Ridge [4]. | Public dashboards; Microdata restricted | Identifying high-risk populations and evaluating local RCHD interventions [4]. |
| **VHHA Analytics** | VHHA | Inpatient data, C-section rates, SMM, AHRQ maternal health measures [5]. | Restricted to member hospitals [5] | Clinical benchmarking, tracking SMM trends and obstetric trauma [5]. |
| **Hospital Discharge Data** | VHI | Detailed records of hospital discharges in Virginia [9]. | By Request / Purchase [9] | Deep-dive research into healthcare utilization and outcomes [9]. |
| **March of Dimes Report Card** | March of Dimes | Preterm birth grades, infant mortality, low-risk Cesarean rates, SMM [2]. | Public | Advocacy, grant writing, and state-to-state comparisons [2]. |
| **Community Health Improvement Data Portal** | VDH / CARES | SDOH, demographics, and health indicators by zip code, county, or census tract [10]. | Public | Mapping neighborhood-level disparities and social environments [10]. |

*Takeaway: The ecosystem is bifurcated between highly accessible but broad public data and highly granular but restricted hospital data. The shared tool must bridge this gap by integrating public APIs while providing clear request pathways for restricted data.*

## Indicator Priorities for Richmond

To effectively support grant applications and program planning, the tool must prioritize indicators that align with national benchmarks like Healthy People 2030 (HP2030) and highlight critical local vulnerabilities, particularly in the postpartum period.

* **Preterm Birth and Infant Mortality**: The 2025 March of Dimes Report Card grades Virginia a "C-" with a preterm birth rate of 10.1% [2]. VDH reports an infant mortality rate of 5.8 per 1,000 live births for 2023 [1], while MoD reports 5.9 for 2023 [2].
* **Quality of Care Metrics**: Virginia's low-risk Cesarean rate is 26.1%, which remains above the HP2030 target of 23.6% [2]. The overall C-section rate in Virginia was 33.05% in 2023 [5]. Severe Maternal Morbidity (SMM) is reported at 84.0 per 10,000 hospital deliveries by MoD [2], though VHHA notes SMM rates have fluctuated, peaking at 3.26% in 2021 before settling to 2.64% in 2024 [5].
* **Postpartum Risk and Overdose**: A critical area for Richmond is the late postpartum period. VDH data shows that 37.4% of pregnancy-associated deaths occur between 43 and 365 days after the end of pregnancy, with 40% of these deaths due to accidental overdose [1]. 
* **Maternal Mortality**: The maternal mortality rate is 33.4 per 100,000 births [2]. However, VDH strictly defines maternal deaths as occurring while pregnant or within 42 days of termination, excluding accidental or incidental causes [3].

## Current Workflows and Manual Steps

The current workflow for compiling maternal health data is highly manual and prone to error. Users typically follow these steps:
1. Navigate to multiple disparate portals (VDH, MoD, VHHA).
2. Search for the latest available year, often discovering that different portals have different "latest" years (e.g., VDH fast facts use 2023 [1], MoD uses 2024 for preterm births [2]).
3. Download CSVs and manually re-aggregate data to match Richmond City or Henrico County boundaries.
4. Attempt to back-solve denominators to calculate local rates.
5. Write methodological caveats to explain why numbers from different sources do not perfectly align.

This process breaks down frequently. Users often accidentally mix maternal mortality (≤42 days) [3] with pregnancy-associated deaths (≤365 days) [1], leading to inflated statistics in official reports. Furthermore, users frequently fail to notice that recent VDH maternal mortality data is marked with an asterisk indicating it is "not final" and subject to change following quality checks [3].

## Trust Requirements

For a shared data tool to be adopted, it must establish absolute credibility. Different personas require different trust signals:

| Persona | Trust Drivers | Red Flags to Avoid |
| :--- | :--- | :--- |
| **Epidemiologist** | Transparent data lineage, exact parity with VDH definitions, and clear small-N suppression rules. | Black-box calculations; missing denominators; lack of "provisional" data warnings. |
| **Quality Analyst** | Alignment with AHRQ measures and ICD-10 "Z-codes" [5]; secure handling of patient-level data. | Mixing inpatient administrative data with survey data without clear delineation. |
| **Advocacy Researcher** | Consistent demographic stratifications (race/ethnicity, payer); ability to trace data back to original public reports. | Masking disparities through over-aggregation; outdated demographic categories. |
| **Program Coordinator** | Official logos (VDH, MoD), auto-generated citations, and plain-language "About the Data" sections. | Conflicting numbers on the same dashboard; overly academic jargon. |

*Takeaway: Trust is built through transparency. The tool must feature automated citations, explicit "final vs. provisional" badges, and downloadable methodology pages that mirror VDH standards.*

## Design Principles for a "Good-Enough" Shared Tool

A "good-enough" tool does not need to replace restricted databases like VHI or VHHA; rather, it needs to streamline the public data experience while providing guardrails against common analytical errors.

* **Dual-Mode UX**: Offer a "Quick Facts" mode that generates 1-page fact sheets and grant language blocks in under five clicks, alongside an "Analyst Mode" with custom cohort filters and reproducible notebooks.
* **Opinionated Defaults**: Automatically default to the "latest stable year" rather than the most recent provisional year to prevent reporting errors.
* **Definitional Guardrails**: Implement definition choosers with explicit warnings (e.g., a pop-up explaining the difference between maternal and pregnancy-associated deaths when a user selects mortality metrics).
* **Export-Ready Assets**: Ensure all charts and maps export with auto-generated citations, date of access, and methodological caveats attached directly to the image file.

## Feature Set by Persona

To deliver immediate value, the tool should roll out features targeted at the specific pain points of each persona:

| Feature | Primary Persona Beneficiary | Description & Value |
| :--- | :--- | :--- |
| **Quick Facts Builder** | Program Coordinator | Generates standardized, cited statistics (e.g., preterm birth rates, WIC participation) for grant applications instantly. |
| **Equity & Disparity Module** | Advocacy Researcher | Calculates rate ratios and excess burden by race/ethnicity and payer type, mirroring MoD disparity reporting [2]. |
| **SDOH Hotspot Maps** | Epidemiologist / Advocate | Overlays maternal health indicators with zip/tract-level SDOH data from the Community Health Improvement Data Portal [10]. |
| **Quality Measures Pack** | Health System Analyst | Pre-built dashboards tracking SMM, VBAC, and obstetric trauma, with notes on episodic spikes [5]. |
| **Data Request Wizard** | Epidemiologist | Streamlines the process of requesting restricted patient-level data from VHI [9] or PRAMS microdata. |

## Data Integration and Governance

Maintaining the tool requires a robust governance framework to ensure compliance and accuracy. 
* **Pipelines**: Implement scheduled API ingests from the Virginia Open Data Portal [11] and VDH dashboards. Allow secure, manual upload pathways for local program data (e.g., RHHD WIC data [8] or local doula program metrics).
* **Compliance**: Strictly adhere to VDH suppression rules for small cell counts to mitigate HIPAA risks and protect patient privacy, especially when mapping data at the census tract level.
* **Versioning**: Maintain a visible changelog that alerts users when VDH updates provisional data to final status [3].

## Equity Analytics and SDOH Mapping

Funders increasingly demand place-based, equity-focused narratives. The tool must integrate SDOH layers from the Virginia Community Health Improvement Data Portal [7] to contextualize clinical outcomes. Prebuilt equity pages should automatically stratify metrics like inadequate prenatal care and preterm births by race, ethnicity, and insurance type (Medicaid vs. Private), allowing users to export "Disparity Snapshots" and "Hotspot Maps" with standardized, non-stigmatizing captions.

## Success Metrics for the Tool

The success of the shared tool will be measured by its ability to reduce friction and improve the quality of local reporting:
* **Time-to-Insight**: Reduction in the average time required to compile a standard maternal health fact sheet (target: under 10 minutes).
* **Citation Accuracy**: Decrease in the rate of definitional errors (e.g., mixing mortality definitions) in partner grant submissions.
* **Adoption**: Monthly active users tracked across all three target organization types (City, Health Systems, Nonprofits).
* **System Reliability**: 99% uptime and adherence to SLAs for updating data within 72 hours of VDH/MoD public releases.

## Risks, Unknowns, and Validation Plan

Before scaling the tool, several risks and unknowns must be addressed through a targeted pilot program with the Richmond and Henrico Health Districts (RHHD) and select nonprofits.

### Inferences (Clearly Labeled)
* *Inference*: Because VHHA data is member-restricted [5] and VHI data requires purchase/requests [9], we infer that community nonprofits currently have almost zero visibility into hospital-level quality metrics (like uncomplicated C-section rates) unless explicitly published in a public CHA or MoD report.
* *Inference*: Given that 40% of pregnancy-associated deaths are due to accidental overdose [1], we infer that users will increasingly need to cross-reference maternal health data with behavioral health and harm reduction datasets.

### Unknowns
* **Internal Health System Data**: The exact structure and export capabilities of internal EHR data at local health systems (VCU Health, Bon Secours) remain unknown, which may complicate the ingestion of local quality metrics.
* **PRAMS Update Cadence**: The exact frequency and lag time of updates for the RCHD-specific PRAMS oversample [4] is unclear, which could impact the timeliness of local behavioral insights.
* **User Upload Appetite**: It is unknown whether local community organizations have the data maturity or willingness to regularly format and upload their own program data (e.g., doula visits) into a shared system.

## Roadmap

**MVP (First 90 Days)**
Focus on aggregating public data and establishing trust. Integrate VDH MCH dashboards, MoD Report Card metrics, and DMAS HEDIS data. Launch the "Quick Facts" builder, basic SDOH maps, and implement automated citations and recency/provisional flags.

**V1.0 (6 Months)**
Introduce restricted-data workflows. Launch the Data Request Wizard for VHI/VHHA data, enable secure program-data uploads for nonprofits, and release the Quality Measures pack for hospital analysts. 

**V1.1+ (Beyond 6 Months)**
Deepen local integration. Establish interoperability with the RHHD CHA website [12], build advanced reproducible notebooks for epidemiologists, and explore optional API connectors to VHHA Analytics for credentialed partner organizations.

## References

1. *Maternal & Child Health - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/
2. *2025 March Of Dimes Report Card For Virginia | PeriStats | March of Dimes*. https://www.marchofdimes.org/peristats/reports/virginia/report-card
3. *Maternal Mortality - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/maternal-mortality/
4. *Data Dashboards - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/
5. *VHHA Maternal Health Data Overview*. https://www.vdh.virginia.gov/content/uploads/sites/233/VHHA-Maternal-Health-Overview-03182025.pdf
6. *Maternal Health Data Sources - Maternal Health*. https://www.vdh.virginia.gov/maternal-health/maternal-health-data-sources/
7. *Virginia Department of Health - Data Portal*. https://www.vdh.virginia.gov/data/
8. *Black Maternal Health Week by the numbers - Richmond ...*. https://www.vdh.virginia.gov/richmond-city/2025/04/11/black-maternal-health-week-by-the-numbers/
9. *Analyze Virginia Healthcare Data Products ⎸ VHI*. https://www.vhi.org/data/
10. *Community Health Data | Loudoun County, VA - Official Website*. https://www.loudoun.gov/2335/Community-Health-Data
11. *Welcome - Virginia Open Data Portal*. https://data.virginia.gov/
12. *2024 Community Health Assessment*. https://www.vdh.virginia.gov/content/uploads/sites/119/2025/04/2024-Richmond-and-Henrico-CHA.pdf