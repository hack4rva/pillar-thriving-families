> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Designing Truth: Preventing Harm from Maternal Health Data Misuse in Richmond's Civic-Tech Tools

## Executive Summary

For civic-tech tools targeting maternal health in Richmond, the presentation of data is as critical as the data itself. Incorrect, misleading, or overclaimed health data can lead to severe real-world harms, including misdirected resource allocation, flawed grant applications, and the erosion of advocacy credibility. This report outlines the strategic guardrails necessary to prevent these outcomes. 

Key insights driving this strategy include:
* **Indicator choice materially changes the story:** AHRQ's 2024 refinements to Severe Maternal Morbidity (SMM) lowered rates from 89.9 to 63.9 per 10,000 deliveries while increasing severity signals (ICU admissions rose from 17.0% to 22.4%) by tightening coding and excluding noisy transfusion-only flags [1]. 
* **Maternal mortality "trend lines" break in 2018:** The National Center for Health Statistics (NCHS) restricted pregnancy-checkbox-only coding (e.g., no maternal codes for checkbox-only deaths age 45 and over) and formalized a new method [2]. The CDC explicitly warns against comparing pre- and post-checkbox periods [3].
* **Coding transitions shift SMM levels independent of clinical change:** The transition from ICD-9 to ICD-10 reduced SMM largely via fewer transfusion codes, creating artificial declines [4]. 
* **Modeled estimates are not measured prevalence:** CDC PLACES small-area estimates synthesize survey and census data via multilevel regression and poststratification (MRP) [5]. They are for ecological inference only and must not be treated as individual-level risk [6].
* **Clinical misinterpretation risk is material:** Dashboards risk being used as triage or guidance. Health IT norms require strict non-medical-use disclaimers [7].

To protect Richmond advocates and researchers, the tool must bake in definitions, uncertainty markers, and comparability guardrails by default.

## Purpose and Audience Fit

The primary goal of this civic-tech tool is to equip Richmond advocates, researchers, and policymakers with defensible maternal health data. However, public health data is highly nuanced. When users export a chart to justify a grant or lobby for a policy change, they inherit the methodological baggage of the underlying data. If a user unknowingly compares a 2017 maternal mortality rate to a 2019 rate to claim a "sudden spike in deaths," their grant application may be rejected by reviewers who know the spike is a 2018 coding artifact [3] [8]. 

The tool must prevent these common misreads. By designing an interface that makes the correct interpretation the path of least resistance, the platform will ensure that Richmond's maternal health advocacy is built on an audit-proof foundation.

## Risk Landscape

Most harms in health data presentation stem from mis-specified indicators, coding-era breaks, small-number volatility, and the misuse of modeled estimates. 

### Harm Scenarios and Mitigations Matrix

| Scenario | Mechanism | Likelihood | Severity | Mitigation |
| :--- | :--- | :--- | :--- | :--- |
| **Cross-era NVSS MMR trend (pre/post 2018)** | Coding change and checkbox artifacts create false spikes/drops [3] [2]. | High | High | Block trend lines crossing 2018; mark change point; require acknowledgment. |
| **SMM rates inflated/deflated by transfusion codes** | Indicator sensitivity; ICD-10 transition decreased transfusion codes [4]. | Medium | Medium | Specify definition; offer "refined" toggle; exclude transfusion by default with rationale [1]. |
| **Model-based PLACES used as "measured" prevalence** | Small area estimates (SAE) and CIs ignored; ecological fallacy [5] [6]. | High | Medium | CIs on by default; "Modeled" chip; best-for-use notes. |
| **Small-number rates in Richmond City departments** | Rare events and unstable denominators create wild rate swings [9] [10]. | High | Medium | Suppress/aggregate small counts; show numerators; use rolling averages. |
| **Mixing MMR (≤42d) and PRMR (≤365d)** | Non-comparable definitions used interchangeably to claim trends [3] [11]. | Medium | High | Lock metric family; display comparability warning banner. |
| **Misattributing ICD-9 to ICD-10 shifts to policy success** | Coding transition artifact alters SMM incidence [4]. | Medium | Medium | Time-slice filters; era annotations; sensitivity excluding transfusion. |
| **Clinical use of dashboard** | UI suggests guidance (e.g., "who needs aspirin prophylaxis?") [7]. | Medium | Very High | "Not medical advice" banner; no risk calculators; redirect to care. |
| **Cross-state comparisons without methods alignment** | Different collection/edits limit comparability across borders [9] [10]. | Medium | Medium | Cross-state comparability warning; disable by default. |

*Key Takeaway:* The most likely risks involve users drawing false conclusions from methodological artifacts (like the 2018 checkbox change or the ICD-10 transition). Mitigations must be hardcoded into the UI, not just buried in a methodology page.

## Standards and Methods

To make every number audit-proof, the tool must adhere to authoritative definitions, document methods inline, and align to federal standards for race/ethnicity, suppression, and uncertainty.

### Maternal Mortality Metrics Are Fundamentally Different

A common error in advocacy is mixing different maternal mortality metrics. NVSS Maternal Mortality Rate (MMR), CDC PMSS Pregnancy-Related Mortality Ratio (PRMR), and Maternal Mortality Review Committee (MMRC) findings answer different questions and must not be combined [11].

| System | Based on | Time Window | Includes Injuries? | Purpose | Comparability Notes |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **NVSS MMR** | Death records, ICD codes [11] | During pregnancy up to 42 days after [11] | No [11] | National trends, WHO-aligned [3] [11] | Breaks across checkbox rollout; 2018 recoding; do not compare pre/post [3] [2]. |
| **CDC PMSS PRMR** | Vital records linkages + review [11] | During pregnancy up to 1 year after [11] | No [11] | Pregnancy-related trends [11] | Not directly comparable to NVSS or MMRCs [11]. |
| **MMRC** | Vital + medical/social/autopsy [11] | During pregnancy up to 1 year after [11] | Yes [11] | Preventability, contributing factors [11] | State/local; definitions differ; not for rate trending vs NVSS [11]. |

### SMM: Pick and Disclose Your Measure

Severe Maternal Morbidity (SMM) is highly sensitive to the chosen definition. The CDC uses 21 indicators based on ICD codes [12] [13]. However, AHRQ's 2024 refinements (MHI 03) require dialysis for Acute Renal Failure (ARF) and remove specific codes from the Coagulopathy (DIC) indicator [1]. 

These refinements increased severity markers (ICU admissions rose from 17.0% to 22.4%) and decreased the overall SMM rate from 89.9 to 63.9 per 10,000 deliveries in HCUP SID 2019–2021 data [1]. Furthermore, the transition from ICD-9 to ICD-10 significantly decreased SMM incidence primarily due to decreased blood transfusion codes [4]. The tool must offer a definition selector (e.g., CDC 21, AHRQ MHI 03) with auto-updating footnotes and a locked default that excludes transfusions to reduce noise.

### Natality-Based Indicators: Comparability Flags Required

Changes in birth certificate data collection alter trends. In 2014, NCHS changed from the date of the last menstrual period (LMP) to the obstetric estimate (OE) to calculate gestational age [14]. This change resulted in higher percentages of prenatal care beginning in the 1st trimester (76.6% based on OE vs 73.3% based on LMP in 2014) [14]. 

Additionally, race and ethnicity data follow the 1997 OMB standards, allowing multiple races and separate Hispanic origin reporting [14]. In 2022, race of mother was imputed for 7.6% of births [14]. The tool must display "Method: OE since 2014" on prenatal care charts and provide data-quality badges showing imputation percentages.

### Modeled Small-Area Estimates: What They Are and Aren't

CDC PLACES provides model-based estimates for small geographic areas (counties, census tracts, ZCTAs) using a multilevel regression and poststratification (MRP) framework based on BRFSS and ACS data [5] [15]. 

These are ecological estimates, not individual-level indicators [6]. The modeling process uses individual-level responses and county/state-level contextual effects to estimate probabilities, which are then applied to target populations [6]. Beginning with the 2023 release, the approach for generating 95% confidence intervals was updated, which may result in wider CIs than previous releases [6]. The tool must require CI display, include a "Best use" note, and warn users against double-adjusting for demographic characteristics in their own regression analyses, as PLACES already incorporates age, race, sex, education, and poverty [6].

## Guardrails in the Interface

UI defaults should make the correct interpretation the path of least resistance. The following design patterns reduce misinterpretation risk:

* **Definition Chips:** Always-on labels like "SMM (CDC 21, no transfusion)"; click to see code sets and inclusions [12] [13].
* **Era Markers:** Vertical lines on time-series charts at 2014 (OE shift), 2015 (ICD-10 transition), and 2018 (NVSS recoding) with hover explanations [4] [2] [14].
* **Uncertainty-First:** Confidence bands on by default; numeric CIs shown on hover [5] [6].
* **Small-n Autosuppression:** Hide/show thresholds with rationale; offer 3–5 year aggregates for rare events [9] [10] [14].
* **Comparability Guardrails:** Disable cross-source trend overlays; warn on cross-state comparisons; lock the "metric family" on each page [9] [10] [11].
* **Source Badges:** Inline source and method links on every tile (e.g., "NVSS 2023 final, released 2025-03-18" [16] [17]).
* **Export Controls:** Force-append footnotes and citations into PNG/CSV/PDF exports.
* **"Modeled Estimate" Treatment:** Distinct icon/color; "ecological only" tooltip; CI toggle locked on for census tracts [5] [6].
* **Narrative Scaffolds:** Prewritten note snippets for grant copying that explain methods and caveats.

## Disclaimers and Copy

Standardized, visible disclaimers reduce legal and practical misuse. Use the following paste-ready language blocks:

* **Non-Medical Use:** "The information provided using this web site is only intended to be general summary information to the public" [7]. "It is not medical advice, diagnosis, or treatment guidance. Individuals should consult a qualified clinician for care needs."
* **Data Provenance and Comparability:** "Metrics adhere to the definitions of their source systems. Maternal mortality (NVSS MMR) and pregnancy-related mortality (CDC PMSS PRMR) are not directly comparable due to different time windows and methods [3] [11]. Trend comparisons are restricted across known method changes (e.g., NVSS coding updates in 2018; 2014 shift to obstetric estimate) [2] [14]."
* **Modeled Estimates:** "Small-area estimates (CDC PLACES) are model-based, include 95% confidence intervals, and are intended for ecological analysis only; they are not individual-level measures [5] [6]."
* **Small Numbers and Suppression:** "To protect privacy and avoid unstable rates, results based on small counts are suppressed or aggregated. Use multi-year averages for rare events [9] [10] [14]."
* **Endorsement/Links:** "Reference in this web site to any specific commercial products, process, service, manufacturer, or company does not constitute its endorsement or recommendation" [7].

## Source Citation Requirements by Indicator Type

Every chart must surface definition, method, uncertainty, comparability, and update cadence.

| Indicator | Primary Source | Definition / Denominator | Must-Display Metadata | Comparability Flags |
| :--- | :--- | :--- | :--- | :--- |
| **Maternal Mortality Rate (MMR)** | CDC NVSS [3] [2] | WHO maternal death; during pregnancy to 42 days; per 100K live births [3] [11] | Year, geography, ICD revision, checkbox status | Do not compare pre/post 2018; do not mix with PRMR [3] [11]. |
| **Pregnancy-Related Mortality Ratio (PRMR)** | CDC PMSS [11] | Deaths during pregnancy to 1 year, determined pregnancy-related [11] | Time window, pregnancy-related determination | Not comparable to MMR/MMRC [11]. |
| **Severe Maternal Morbidity (SMM)** | CDC 21 indicators [12] [13]; AHRQ MHI [1] | Delivery hospitalizations with specified ICD codes [12] | Code set version, inclusion/exclusion (transfusion, ARF/DIC) | ICD-9 vs ICD-10; definition changes alter levels [1] [4]. |
| **Preterm birth, LBW, Cesarean** | NCHS Natality [14] | Preterm via OE ≥2014; LBW <2500g [14] | OE vs LMP, plurality, parity | Pre- vs post-2014 not directly comparable for some measures [14]. |
| **Modeled chronic conditions** | CDC PLACES [5] [15] | MRP of BRFSS+ACS; adult prevalence [5] | "Modeled estimate" label; 95% CI; version | Not for individual inference; caution on regression double-adjustment [6]. |

## Clinical Misinterpretation Risk

There is a severe risk of a data tool being interpreted as clinical guidance (e.g., a user checking a dashboard to decide if they need aspirin prophylaxis based on their demographic profile). Combine prominent UX cues with governance to preclude clinical use.

* **UX:** Implement a persistent "Not medical advice" banner. Avoid clinical styling (no red/yellow risk labels per individual attributes). Route users to services (e.g., 211, OB provider directories).
* **Content Governance:** Do not include clinical algorithms, patient-level inputs, or ZIP-based clinical recommendations. Redact facility-level outlier lists unless methods and volume are adequate and provided with context.
* **Policy:** Implement a Terms of Use acceptance gate. Log and periodically review search/feedback for clinical-question patterns.

## Implementation and QA

A short set of automated checks eliminates most advocacy and grant risks.

* **Data QA:** Implement schema validation for required metadata fields. Use unit tests that block charts without source/definition. Create a comparability linter that disallows mixed metric families.
* **Methods QA:** Build sensitivity toggles (e.g., SMM without transfusion). Enforce auto-era annotations and CI display for modeled/small-area data.
* **Accessibility:** Provide tooltips with plain-English definitions, a downloadable data dictionary, and auto-embedded footnotes on export.
* **Governance:** Maintain a versioned methods page, a change log, and an annual audit against source method updates (e.g., AHRQ MHI revisions).

## Inferences (Clearly Labeled)

* **Inference:** For small-number suppression thresholds, adopt a conservative rule (e.g., suppress when numerator < 20 or CI width exceeds 50% of point estimate) when the source does not specify. This aligns with common public-health practice, though explicit NVSS thresholds were not retrieved in this specific context.
* **Inference:** Default SMM display should exclude transfusion to reduce misclassification risk, reflecting AHRQ and validation study concerns, even though CDC allows optional inclusion [1] [4].
* **Inference:** For Richmond-scale geographies, multi-year rolling averages (3–5 years) are recommended to stabilize rare events; the exact window should balance timeliness and stability.

## Unknowns

* Whether Virginia MMRC public reports offer Richmond-specific insights and how their definitions align with NVSS/PMSS in current cycles.
* The tool's intended indicator list and whether users can upload external datasets (which affects comparability controls).
* Final vs provisional status and release cadence of the specific data feeds planned for use (e.g., latest NVSS year available in the pipeline).
* Any state-specific suppression rules from the Virginia Department of Health that should override generic thresholds.

## References

1. *Refining the Severe Maternal Morbidity Measure*. https://qualityindicators.ahrq.gov/Downloads/Resources/v2024_MHI_Scientific_Rationale_and_Empirical_Testing.pdf
2. *National Vital Statistics Reports*. https://www.cdc.gov/nchs/data/nvsr/nvsr69/nvsr69-02-508.pdf
3. *NVSS - Maternal Mortality - FAQ*. https://www.cdc.gov/nchs/maternal-mortality/faq.htm
4. *National Health Statistics Reports*. https://www.cdc.gov/nchs/data/nhsr/nhsr166.pdf
5. *Methodology | PLACES | CDC*. https://www.cdc.gov/places/methodology/index.html
6. *PLACES Frequently Asked Questions | PLACES | CDC*. https://www.cdc.gov/places/faqs/index.html
7. *Website Disclaimers - ASTP - Assistant Secretary for Technology Policy*. https://healthit.gov/website-disclaimers/
8. *Maternal Mortality in the United States: Changes in Coding, Publication, and Data Release, 2018*. https://stacks.cdc.gov/view/cdc/84769
9. *2025 Limitations of Data Comparability Across States. ...*. https://www.countyhealthrankings.org/sites/default/files/media/document/2025%20Limitations%20of%20Data%20Comparability%20Across%20States.pdf
10. *2023 Limitations of Data Comparability Across States*. https://www.countyhealthrankings.org/sites/default/files/media/document/2023%20Comparability%20Across%20States.pdf
11. *PMSS: Frequently Asked Questions | Maternal Mortality Prevention | CDC*. https://www.cdc.gov/maternal-mortality/php/pregnancy-mortality-surveillance-data/faqs.html
12. *Identifying Severe Maternal Morbidity (SMM) | Maternal Infant Health | CDC*. https://www.cdc.gov/maternal-infant-health/php/severe-maternal-morbidity/icd.html
13. *Severe Maternal Morbidity | Maternal Infant Health | CDC*. https://www.cdc.gov/maternal-infant-health/php/severe-maternal-morbidity/index.html
14. *User Guide to the 2022 Natality Public Use File*. https://ftp.cdc.gov/pub/Health_Statistics/NCHS/Dataset_Documentation/DVS/natality/UserGuide2022.pdf
15. *
            PLACES: Local Data for Better Health - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC9258452/
16. *National Vital Statistics Reports*. https://www.cdc.gov/nchs/data/nvsr/nvsr74/nvsr74-1.pdf
17. *Births: Final Data for 2023 - National Vital Statistics Reports - NCBI Bookshelf*. https://www.ncbi.nlm.nih.gov/books/NBK618136/