# KIDS COUNT for Richmond: Maternal Health and Family Wellbeing, Ready for Action

## Executive Summary
Virginia’s maternal-health indicators on the Annie E. Casey Foundation's KIDS COUNT Data Center are fresh and locality-ready, providing a strong foundation for a Richmond-specific baseline. Infant mortality, low birthweight, and first-trimester prenatal care all cite Virginia Department of Health (VDH) Vital Records, allow filtering to Richmond City, and offer downloadable CSVs updated as recently as late 2025. 

However, critical nuances require strategic handling:
* **Geographic Definition Mismatch**: KIDS COUNT assigns infant mortality to the mother’s residence, whereas VDH assigns it to the infant’s residence. 
* **Preterm Birth Gap**: The national KIDS COUNT preterm birth indicator only covers the 50 most populous U.S. cities, effectively excluding Richmond. 
* **Socioeconomic Data Lags**: Poverty and health insurance indicators rely on Census model-based estimates (SAIPE/SAHIE) that carry a longer lag (currently showing 2022 data).
* **Outdated School Readiness**: School readiness metrics on KIDS COUNT rely on outdated PALS-K data (last updated in 2020) and do not reflect Virginia's current assessment frameworks.

## Purpose and Decisions

### Near-Term Decisions Enabled
You can build a current, locality-filtered maternal-health and family wellbeing baseline from KIDS COUNT today. This data enables you to define a core maternal-health KPI set for Richmond (infant mortality, low birthweight, prenatal care) alongside socioeconomic context metrics (poverty, uninsured rates). By selecting canonical definitions and establishing 2022–2023 as the core vintage for comparability, you can immediately populate dashboards and strengthen grant applications with authoritative, localized data.

### Medium-Term Decisions Enabled
In the medium term, this inventory highlights exactly where you must source data outside of KIDS COUNT. You will need to integrate VDH preterm birth data and updated school readiness metrics (such as VKRP) directly from state or local agencies. Furthermore, understanding the update cadence of KIDS COUNT allows you to establish a sustainable data refresh schedule and governance documentation for your organization.

## Indicator Inventory

Most maternal indicators are current (2022–2023) and easily downloadable. Socioeconomic context indicators lag to 2022, while preterm birth and school readiness require alternate sourcing for Richmond.

### Maternal Health and Family Wellbeing: Richmond Availability and Vintage

| Indicator | Richmond Available? | Geography Rule | Latest Vintage / Update | Data Source & Provider | Access Method | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Infant mortality** | Yes | Mother's residence | Nov 2025 | VDH Division of Health Statistics / Voices for Virginia's Children | CSV Download | Rate per 1,000 live births [1]. |
| **Low birthweight** | Yes | Mother's residence | Dec 2025 | VDH Division of Health Statistics / Voices for Virginia's Children | CSV Download | Counts <10 suppressed pre-2021; <=20 suppressed from 2021+ [2]. |
| **Prenatal care (1st trimester)** | Yes | Mother's residence | 2022-2023 (Updated Nov 2025) | VDH Division of Health Statistics / Voices for Virginia's Children | CSV Download | Counts <=20 suppressed [3]. |
| **Preterm births** | No | Top 50 US Cities only | Jan 2025 | NCHS microdata / Annie E. Casey Foundation | CSV Download | Richmond excluded. Use VDH directly [4]. |
| **Children in poverty (annual)** | Yes | County/City | 2022 (Updated Jul 2024) | U.S. Census Bureau SAIPE / Voices for Virginia's Children | CSV Download | Do not compare to ACS-based child poverty series [5]. |
| **Children under 19 without health insurance** | Yes | County/City | 2022 (Updated Dec 2024) | U.S. Census Bureau SAHIE / Voices for Virginia's Children | CSV Download | Covers children <19 below 200% FPL [6] [7]. |
| **School readiness (PALS-K)** | Unclear | Locality | Academic Year 2019 (Updated May 2020) | VDOE via UVA Curry / Voices for Virginia's Children | CSV Download | Outdated. Use as historical context only [8] [9]. |

*Key Takeaway*: Richmond-specific maternal health data is robust and recently updated, but you must rely on external sources for preterm birth and current school readiness metrics.

### Download and Filtering Instructions
Accessing the data for repeatable pulls is straightforward via the web interface:
1. Navigate to the specific indicator page and set the "Locations" filter to Virginia [2].
2. Use the "Table" view and select "Detailed" or "Sort / Rank" to locate "Richmond city, Virginia" [8].
3. Click the **"Download Raw Data"** button to export a CSV file, which includes locality and year columns for easy filtering [2] [5].
4. To bundle multiple indicators for Richmond simultaneously, use the **"Create a Custom Report"** feature. Select Location: Virginia → City/County → Richmond city, add your selected indicators, and generate a permanent URL that can be bookmarked for future reference [10] [11].

## Methodology and Definition Alignment

Birth indicators mostly align on definitions between KIDS COUNT and VDH; the largest risk to data integrity is the geographic assignment of infant mortality.

### KIDS COUNT vs. VDH: Definitions and Implications

| Indicator | KIDS COUNT Definition & Residence Rule | VDH Definition & Residence Rule | Alignment | Implication & Action |
| :--- | :--- | :--- | :--- | :--- |
| **Infant Mortality** | Deaths <1 year per 1,000 live births. Locality = **Mother's residence** [1]. | Deaths <1 year per 1,000 live births. Locality = **Infant's residence** [12]. | Partial Mismatch | **Action**: Select a canonical rule. Recommend using mother's residence to align with other birth indicators. |
| **Low Birthweight** | <2,500 grams. Locality = Mother's residence [2]. | <2,500 grams. Locality = Mother's residence [12]. | Aligned | **Action**: Use KIDS COUNT data as-is. |
| **Preterm Birth** | <37 completed weeks. Top 50 cities only [4]. | <37 weeks gestation. Statewide/Locality [12]. | Aligned (Def) / Mismatch (Coverage) | **Action**: Source preterm birth data directly from VDH for Richmond. |
| **Prenatal Care** | First 13 weeks of pregnancy. Locality = Mother's residence [3]. | Comparable to VDH measures. | Aligned | **Action**: Use as a leading indicator for birth outcomes. |

*Key Takeaway*: Cross-indicator coherence favors using the mother's residence for all birth metrics. When integrating VDH preterm data, ensure you explicitly state the residence rules to preserve apples-to-apples comparisons.

### Suppression and Comparability Notes
Voices for Virginia's Children applies strict suppression rules to KIDS COUNT data to protect privacy. For low birthweight, counts less than 10 are suppressed before 2021, and counts of 20 or less are suppressed from 2021 onward [2]. While percentages are still reported, they should be interpreted with caution [2]. 
*Inference*: You should focus analyses on rates rather than raw counts. If analyzing small subgroups in Richmond, pool multi-year data to smooth out small-number fluctuations.

## Data Vintage, Lags, and Trend Integrity

Maternal indicators are highly recent, while socioeconomic context metrics carry an inherent lag. 

* **Maternal Indicators**: Infant mortality, low birthweight, and prenatal care were all updated in late 2025 (November/December) [2] [1] [3]. These likely include 2023 data, making them highly relevant for current baselining.
* **Socioeconomic Indicators**: Poverty (SAIPE) and uninsured (SAHIE) data were updated in mid-to-late 2024, reflecting 2022 estimates [6] [5]. 
* **School Readiness**: PALS-K data was last updated in May 2020 [8]. 

**Actionable Guidance**: Anchor your maternal trends on the 2022–2023 data. When combining this with 2022 SAIPE/SAHIE data, explicitly note the lag. Do not mix SAIPE child-poverty data with ACS-based poverty indicators, as the sources differ fundamentally [5].

## Access and Automation

While CSV exports are highly reliable, public API documentation for KIDS COUNT is not readily available. 

### Step-by-Step Pulls
1. Filter to Virginia → Richmond city → "Download Raw Data" [2].
2. Store CSVs by indicator and date, logging the "Last updated" month/year directly from the page text.
3. For multi-indicator bundles, utilize the "Create a Custom Report" tool and archive the permanent URL to standardize future pulls [11].

### Automation Plan
*Inference*: Because API endpoints are undocumented, you should plan for scheduled, semi-automated browser scripts or manual monthly checks of the CSVs. Monitor the AECF "Updates" page [13] and the Voices for Virginia's Children site for new data releases.

## Risks, Biases, and Failure Cases

Several pitfalls could mislead decisions if not properly contextualized:

* **Geography Mismatch (Infant Mortality)**: The difference between mother's residence (KIDS COUNT) [1] and infant's residence (VDH) [12] can shift rates, especially in regions with major referral hospitals like Richmond. Standardize on one rule and footnote all visuals.
* **Small Number Suppression**: Post-2021 suppression of counts <=20 [2] can hide true count changes. Rely on rates and add confidence intervals where possible.
* **Readiness Discontinuity**: KIDS COUNT relies on PALS-K [8]. Virginia has transitioned toward VKRP/KRA. Treat PALS-K strictly as historical data and source current readiness directly from VDOE or Richmond Public Schools.
* **Census Model-Based Estimates**: SAIPE and SAHIE are model-based estimates [6] [5]. Uncertainty margins are not always displayed on KIDS COUNT pages; retrieve margins of error directly from the Census Bureau when precision is critical.

## Recommended Next Steps

**0–30 Days: Establish the Baseline**
* Extract CSVs for infant mortality, low birthweight, prenatal care, poverty, and uninsured rates.
* Select canonical definitions (e.g., mother's residence for birth outcomes).
* Publish an initial Richmond maternal-health baseline.

**30–60 Days: Close the Gaps**
* Source preterm birth data directly from VDH at the locality level [12].
* Integrate VDH data with KIDS COUNT data, adding clear data-quality notes regarding source differences.
* Initiate contact with Voices for Virginia's Children to inquire about update cadences and potential API access.

**60–90 Days: Finalize and Automate**
* Replace outdated PALS-K readiness data with current VKRP data from state/local sources.
* Add Margin of Error (MOE) aware visuals for SAIPE/SAHIE poverty and insurance data.
* Finalize internal documentation on residence rules and suppression impacts.

## Unknowns and Resolution Plan

* **API Availability**: It is unknown if a stable, public API exists for KIDS COUNT [14]. *Resolution*: Contact AECF or Voices for Virginia's Children directly to request developer access.
* **Preterm Birth Locality Data on KC**: No Virginia-specific preterm birth page filtering to Richmond was found on KIDS COUNT. *Resolution*: Confirm this gap with Voices; default to VDH data [12].
* **Exact Latest Year in CSVs**: The "Last Updated" date (e.g., Nov 2025) does not explicitly state the data year on the summary page [1]. *Resolution*: Verify the exact year column inside each downloaded CSV and lock it to a "reference year" in your internal data model.

## Appendices

**Providers and Sources**
* **State Provider**: Voices for Virginia's Children (Richmond, VA) [2] [15].
* **Maternal Indicators Source**: Virginia Department of Health, Division of Health Statistics [2] [1].
* **Socioeconomic Source**: U.S. Census Bureau (SAIPE/SAHIE) [6] [5].

**Key Indicator Links**
* Infant mortality: [Table 3236](https://datacenter.aecf.org/data/tables/3236-infant-mortality)
* Low birthweight: [Table 3252](https://datacenter.aecf.org/data/tables/3252-low-birthweight-babies)
* Prenatal care: [Table 3234](https://datacenter.aecf.org/data/tables/3234-prenatal-care-beginning-in-the-first-trimester)
* Children in poverty: [Table 5879](https://datacenter.aecf.org/data/tables/5879-children-living-in-poverty-annual)
* Children without health insurance: [Table 5926](https://datacenter.aecf.org/data/tables/5926-children-under-age-19-without-health-insurance)

## References

1. *Infant mortality | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/3236-infant-mortality
2. *Low birthweight babies | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/3252-low-birthweight-babies
3. *Prenatal care beginning in the first trimester | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/3234-prenatal-care-beginning-in-the-first-trimester
4. *Preterm births | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/18-preterm-births?locations=VA
5. *Children living in poverty- annual | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/5879-children-living-in-poverty-annual
6. *Low-income children under age 19 without health insurance | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/6176-low-income-children-under-age-19-without-health-insurance
7. *Children under age 19 without health insurance | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/5926-children-under-age-19-without-health-insurance
8. *Kindergarteners whose fall PALS-K scores were below kindergarten readiness levels by race | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/10735-kindergarteners-whose-fall-pals-k-scores-were-below-kindergarten-readiness-levels-by-race
9. *Kindergarteners whose fall PALS-K scores were below kindergarten readiness levels by race | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/9167-kindergarteners-whose-fall-pals-k-scores-were-below-kindergarten-readiness-levels-by-race
10. *Child poverty statistics*. https://datacenter.aecf.org/data
11. *US Data by State and Population by Race | KIDS COUNT Data Center*. https://datacenter.aecf.org/locations
12. *Maternal & Child Health Indicators - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/mch-indicators/
13. *Updates | KIDS COUNT Data Center*. https://datacenter.aecf.org/updates
14. *KIDS COUNT Data Center from the Annie E. Casey Foundation*. https://datacenter.aecf.org/
15. *Voices for Virginia's Children - KIDS COUNT Data Center*. https://datacenter.aecf.org/about/state-providers/details/47-voices-for-virginias-children