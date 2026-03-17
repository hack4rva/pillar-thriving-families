# Grant-Ready Richmond Maternal Health: Credible Data, 5-Step Demo

## Executive Summary

Richmond’s maternal and infant health metrics reveal a localized crisis that state-level averages obscure. While Virginia's overall preterm birth rate sits at 10.1%, Richmond City's rate is a staggering 12.5%, earning an "F" grade from the March of Dimes [1]. Furthermore, the highest-risk window for maternal mortality is the postpartum period, with 37.4% of Virginia's pregnancy-associated deaths occurring 43 to 365 days after pregnancy, driven heavily (40%) by accidental overdoses [2]. 

Despite this urgent need, local health advocates and grant writers struggle to coordinate actionable data. They are forced to manually reconcile mismatched geographies, lagging vintages, and suppressed data cells across half a dozen siloed agency dashboards. This tool solves the "fifth time recreating this spreadsheet" problem. By auto-harmonizing authoritative sources—from the Virginia Department of Health (VDH) to the CDC and HRSA—into a single, citation-stamped "Grant Pack," this platform eliminates cross-vintage errors, saves hours of researcher time, and directs limited funding to the Richmond neighborhoods and postpartum windows that need it most.

## The User Hook—"The Fifth Time Recreating This Spreadsheet" (30–45 seconds)

**Speaker:** "Imagine you are a grant researcher for a Richmond maternal health non-profit. In the past month alone, you’ve responded to three different RFPs. Each asks for the same core metrics: preterm birth rates, maternal mortality, and social vulnerability. 

But to get those numbers, you have to pull from five different sources. You pull Richmond City's 12.5% preterm rate from the 2024 March of Dimes report [1]. Then you pull maternal mortality from VDH's 2018–2023 dashboard [2]. You try to map workforce shortages using HRSA data [3]. You spend hours reconciling mismatched years and geographies, terrified that a reviewer will flag your application for mixing 2024 city data with 2023 state data. 

Today, your director asks you to 'just update the spreadsheet' for a new city grant. But this time, you aren't starting from scratch. You are using our platform—a tool that auto-harmonizes the data, locks the geography, and generates a consistent, citation-stamped export that satisfies the strictest policy reviewers."

## Tool Walkthrough—5 Steps in 2–3 Minutes

### Step 1: Select Richmond City + Indicator Pack
**Action:** The user selects "Richmond City" from a dropdown and clicks the "Richmond Maternal Core" preconfigured pack.
**Script:** "We start by selecting our target geography. The tool instantly loads the core indicators: preterm births, infant mortality, and pregnancy-associated deaths. Notice the 'Vintage Badges' next to each metric. It clearly labels the March of Dimes data as 'NCHS 2024 final' [1] and the VDH Maternal and Child Health data as '2019–2023' [2]. This ensures your grant narrative stays internally consistent."

### Step 2: Map Need—Preterm Hotspots + Access
**Action:** The screen transitions to a heatmap of Richmond.
**Script:** "Next, we map the need. We overlay Richmond's preterm hotspots with HRSA Maternity Care Target Area (MCTA) scores, which range from 0 to 25 [3]. To contextualize the social determinants of health, we toggle on the Virginia Health Opportunity Index (HOI), which maps 13 indicators at the census tract level [4]. Now we can visually prove exactly which neighborhoods lack both care access and social infrastructure."

### Step 3: Postpartum + Overdose Lens
**Action:** The user adjusts a timeline slider to "43–365 days postpartum."
**Script:** "Because 37.4% of pregnancy-associated deaths in Virginia occur between 43 and 365 days postpartum, we filter for this specific window [2]. The dashboard immediately highlights that 40% of these deaths are due to accidental overdose [2]. This allows us to precisely target perinatal substance use disorder (SUD) supports in our grant proposal."

### Step 4: PRAMS Local Insights
**Action:** The user clicks into behavioral indicators.
**Script:** "For behavioral insights, we pull from the Pregnancy Risk Assessment Monitoring System (PRAMS). While PRAMS is a state-based survey, the tool includes an on-screen caveat noting that data can only be credibly stratified for the Richmond City Health District (RCHD) and Blue Ridge, where the program oversamples [5]. We select RCHD to show local prenatal care initiation rates without over-extrapolating."

### Step 5: Export "Grant Pack"
**Action:** The user clicks "Generate Grant Pack."
**Script:** "Finally, with one click, we export the 'Grant Pack.' This bundles a PDF and CSV containing our harmonized metrics, maps, methodology notes, and visible suppression flags. It’s ready to be attached directly to an RFP."

## Credibility and Limits Statement (30 seconds)

**Speaker:** "To win grants, data must be unimpeachable. We do not generate new data; we triangulate authoritative sources. Every metric displays its named owner, methodology, and vintage date—such as the VDH Maternal Mortality Review Team's 2021 case reviews [6] or the CDC's 2020 SVI documentation [7]. 

Let me be explicitly clear about our limits: **This tool does not provide clinical guidance.** It is not a diagnostic tool or a provider directory. Furthermore, to protect patient privacy, we strictly adhere to small-number suppression rules, aggregating data to approved census tracts and health districts."

## Why This Doesn't Exist Already—And How We Overcome It

If this is so valuable, why hasn't it been built? The answer lies in privacy laws and bureaucratic fragmentation. 

HIPAA's 45 CFR 164.514 Safe Harbor provision strictly restricts the release of geographic subdivisions smaller than a State, particularly for populations under 20,000 [8]. Additionally, VDH policy mandates the suppression of data where population sizes or case numbers are too small, to maintain confidentiality [9]. 

Naive tech solutions fail because they try to force microdata into the open, violating these rules. Our design embraces these constraints. We aggregate to approved geographies (tracts and districts), prominently display suppression flags rather than guessing missing values, and export citation-first summaries rather than raw Protected Health Information (PHI).

## Partner and Pilot: Urban Baby Beginnings + RHHD

To turn these maps into immediate community services, we are proposing a pilot with **Urban Baby Beginnings**, Virginia’s leading nonprofit building maternal health hub infrastructure with a strong presence in Richmond [10]. 

By partnering with Urban Baby Beginnings and the Richmond and Henrico Health Districts (RHHD), we will co-define postpartum and SUD support indicators in two high-need Richmond census tracts. RHHD will validate our indicator thresholds, and Urban Baby Beginnings will use the generated Grant Packs to apply for targeted intervention funding.

## Value Proposition & ROI: Researcher Time and Grant Consistency

The core value proposition is the elimination of manual data reconciliation, directly translating to researcher hours saved and higher grant success rates due to data consistency.

| Task | Status Quo | With Tool | Time Delta |
| :--- | :--- | :--- | :--- |
| Source identification (5–7 sources) | 2–3 hours | 5 minutes | Saves ~2.5 hours |
| Vintage/geography harmonization | 2 hours | Automated | Saves 2 hours |
| Map creation/overlays | 1–2 hours | 5 minutes | Saves ~1.5 hours |
| Methods/citation write-up | 1 hour | Auto-included | Saves 1 hour |
| **Total per grant pack** | **6–8 hours** | **<30 minutes** | **Saves 5.5 to 7.5 hours** |

*Takeaway:* By reducing the data assembly process from a full workday to under 30 minutes, non-profits can increase their grant application volume while ensuring zero cross-vintage data errors.

## Risk, Limits, and Ethics

We must do no harm while speeding action. Our ethical guardrails include:
* **Non-clinical scope:** The platform provides population-level coordination data and resource links only.
* **Privacy-first architecture:** Visible suppression flags are used; no microdata or PHI is ever exported or stored.
* **Transparency:** Prominent vintage stamps and an automated "Consistency Check" prevent users from accidentally misleading grant reviewers by mixing incompatible data years.

## Anticipated Judge Questions & Crisp Responses

| Judge Question | Data-Backed Response |
| :--- | :--- |
| **How accurate is this data?** | We surface only named, authoritative sources: VDH MCH (updated Oct 10, 2025) [2], MMRT [6], PRAMS [5], March of Dimes (NCHS 2024 final) [1], and HRSA MCTA [3]. Each stat carries a vintage badge and direct link. |
| **Why are some cells blank?** | This is intentional small-number suppression per VDH policy [9] and HIPAA Safe Harbor rules [8]. We aggregate to tract/district and flag suppression to prevent disclosure risk. |
| **Why do city and state numbers differ?** | They represent different geographies and vintages (e.g., Richmond city's 12.5% from MoD 2024 [1] vs. Virginia's 2019–2023 MCH stats [2]). Our "Consistency Check" prevents users from mixing these in the same denominator. |
| **Do you give clinical guidance?** | No. The tool coordinates public health data and links to resources. It offers no diagnoses, treatment advice, or provider directories. |
| **How current is this data?** | Vintages are shown on-screen: NCHS 2024 [1], VDH MCH 2019–2023 [2], MMRT 2021 in review [6]. We publish an update schedule aligned with agency releases. |
| **Why hasn't this been built already?** | HIPAA Safe Harbor [8], small cell suppression [9], and cross-agency vintage lags made integrations risky. We designed specifically around these constraints. |

## Data Source Comparison

| Source | Owner | Geography | Vintage Window | Methods / Notes |
| :--- | :--- | :--- | :--- | :--- |
| **VDH MCH Dashboards** | VDH | State / Local | 2018–2023 (Updated Oct 2025) | Uses vital records, hospitalizations, PAMSS, PRAMS [2]. |
| **VA PRAMS** | VDH / CDC | State + RCHD/BRHD | Most recent dashboard years | Survey data; Richmond oversample allows local stratification [5]. |
| **MMRT Annual Reports** | VDH OCME | State | 2021 review in progress | Requires 6-9 mo certification + 6-9 mo eligibility verification [6]. |
| **March of Dimes** | NCHS / MoD | State / City | 2024 final | NCHS natality data; provides specific city grades [1]. |
| **HRSA HPSA / MCTA** | HRSA | Tracts / Service Areas | Current | Composite score (0-25) including SVI, prenatal care, diabetes [11] [3]. |
| **CDC/ATSDR SVI** | CDC | Tracts | 2020, 2022 | 15-indicator social vulnerability index; full documentation online [7]. |
| **VA HOI** | VDH OHE / VCU | Tracts | Current release | 30+ variables combined into 13 indicators and 4 profiles [12] [4]. |

*Takeaway:* This matrix proves to evaluators that the tool relies exclusively on gold-standard, verifiable public health data, ensuring complete transparency for grant reviewers.

## Inferences and Unknowns

**Inferences (Assumptions to be validated):**
* **Time Saved:** We infer a savings of 5.5 to 7.5 hours per grant pack based on the manual steps automated by the tool.
* **User Frequency:** We assume non-profit researchers rebuild similar spreadsheets multiple times per quarter for different RFPs.

**Unknowns (To be tested in pilot):**
* Which specific PRAMS indicators (e.g., depression screening vs. prenatal care) Richmond judges and grant reviewers will prioritize most highly.
* The exact HRSA MCTA scores for Richmond service areas at the exact time of the live demo, as these update dynamically.
* The preferred level of geographic aggregation (tract vs. district) that RHHD will require for public-facing presentations to avoid suppression triggers.

## Continuation Pitch (30 seconds)

**Speaker:** "We aren't just building a hackathon prototype; we have a 90-day roadmap to a validated pilot. 
* **Weeks 1–2:** We finalize our data update cadence and co-design specific postpartum indicators with Urban Baby Beginnings and the Richmond Health District.
* **Weeks 3–6:** We run two mock grant cycles to measure exact hours saved and test our 'Consistency Check' pass rate.
* **Weeks 7–12:** Urban Baby Beginnings will submit 2 to 3 real grant applications using our Grant Pack. We will collect reviewer feedback and publish the pilot results. 

Fund this project today, and within three months, we will transform how Richmond secures the capital needed to save mothers and babies."

## References

1. *2025 March Of Dimes Report Card For Virginia | PeriStats | March of Dimes*. https://www.marchofdimes.org/peristats/reports/virginia/report-card
2. *Maternal & Child Health - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/
3. *Scoring Shortage Designations | Bureau of Health Workforce*. https://bhw.hrsa.gov/workforce-shortage-areas/shortage-designation/scoring
4. *Virginia Department of Health, Office of Health Equity*. https://puttinglocaldatatowork.urban.org/grantee/virginia-department-health-office-health-equity.html
5. *Data Dashboards - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/
6. *2024 Virginia Maternal Mortality Review Team Annual Report*. https://www.vdh.virginia.gov/content/uploads/sites/233/2024-Virginia-Maternal-Mortality-Review-Team-Annual-Report.pdf
7. *The Social Vulnerability Index (SVI): Data and Tools Download for Place and Health | CDC*. https://svi.cdc.gov/dataDownloads/data-download.html
8. *45 CFR § 164.514 - Other requirements relating to uses and disclosures of protected health information. | Electronic Code of Federal Regulations (e-CFR) | US Law | LII / Legal Information Institute*. https://www.law.cornell.edu/cfr/text/45/164.514
9. *Data and Reports - Disease Prevention*. https://www.vdh.virginia.gov/disease-prevention/disease-prevention/hiv-aids-sexually-transmitted-disease-std-hepatitis-reports/
10. *Welcome to Urban Baby Beginnings - Urban Baby Beginnings*. https://urbanbabybeginnings.org/
11. *
      Federal Register
       :: 
      Criteria for Determining Maternity Care Health Professional Target Areas
    *. https://www.federalregister.gov/documents/2022/05/19/2022-10783/criteria-for-determining-maternity-care-health-professional-target-areas
12. *Health Opportunity Index - Virginia Open Data Portal*. https://data.virginia.gov/dataset/health-opportunity-index