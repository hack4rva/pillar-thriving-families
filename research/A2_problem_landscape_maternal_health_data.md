# Richmond's Maternal Data Maze: Who Holds What, Why It Conflicts, and How to Fix It

## Executive Summary
Richmond faces a critical maternal and infant health challenge, underscored by an "F"-grade preterm birth rate and pronounced postpartum overdose risks. However, efforts to address these crises are severely hampered by a fragmented data landscape. Multiple state and private entities—including the Virginia Department of Health (VDH), the Virginia Hospital & Healthcare Association (VHHA), and the Department of Medical Assistance Services (DMAS)—independently compile maternal health data using different denominators, definitions, and update cycles [1] [2]. 

For a nonprofit researcher or agency analyst in Richmond, this fragmentation creates a maze of conflicting "birth counts" and masked racial disparities. For instance, in 2022, Virginia recorded 95,630 resident births, 89,366 inpatient hospital deliveries, and 37,046 Medicaid-paid births—each representing a different universe of patients [1]. Without a local data governance playbook, these inconsistencies lead to policy misfires, misallocated resources, and obscured equity gaps. This report maps the real-world shape of Richmond's maternal health data coordination problem and provides a strategic framework to align datasets for actionable interventions.

## The Stakes: Disparities and Benchmarks that Matter Now
Richmond's maternal and infant health outcomes lag significantly behind national benchmarks, with severe risks concentrated in the postpartum period and among Black birthing people.

### Richmond's 12.5% preterm rate vs HP2030 9.4% target
Richmond City's preterm birth rate stands at 12.5%, earning an "F" grade on the 2025 March of Dimes Report Card [3]. This rate worsened from the previous year and sits well above the Healthy People 2030 target of 9.4% [3] [1]. Virginia as a whole received a "D+" grade with a 10.6% preterm birth rate [3]. Preterm birth is a primary driver of infant mortality and lifelong health disparities, making this a critical intervention point for the city.

### Virginia mortality context: 40% of pregnancy-associated deaths driven by overdose
The postpartum year is a mortality hot spot in Virginia. Between 2019 and 2023, the state recorded 34.5 maternal deaths per 100,000 live births [4]. When expanding the lens to pregnancy-associated deaths (deaths within one year of pregnancy, regardless of cause), the rate jumps to 62.3 per 100,000 live births (2018-2022) [4]. Crucially, 37.4% of these deaths occurred between 43 and 365 days postpartum, and 40% were due to accidental overdose [4]. This indicates that the largest share of maternal risk happens after routine obstetric care ends.

### Racial inequities: Black pregnancy-associated mortality at 89.5 vs 53.5 for White
Pronounced maternal mortality disparities exist across racial lines. According to the Virginia Department of Health (VDH) Office of the Chief Medical Examiner, Black women experienced pregnancy-associated deaths at significantly higher rates than White women from 2018 to 2020, averaging rates of 89.5 and 53.5 per 100,000, respectively [2]. 

## Who Compiles Maternal Health Data in Virginia/Richmond—and What They Use
At least eight distinct organizations publish or steward maternal metrics in Virginia, each drawing from different underlying systems with unique strengths and blind spots.

### VDH Maternal and Child Health (MCH) Epidemiology
VDH maintains dashboards using data from birth and death certificates (Vital Records), inpatient hospitalizations, the Pregnancy-Associated Mortality Surveillance System (PAMSS), and the Pregnancy Risk Assessment Monitoring System (PRAMS) [4] [5]. 

### VHHA and the Virginia Neonatal Perinatal Collaborative (VNPC)
VHHA and VNPC collaborate on the Maternal Health Dashboard, which uses inpatient hospital discharge data mandated by the Patient Level Data System Act [1]. This dashboard tracks in-hospital birth events, severe maternal morbidity (SMM), and payer mix across all Virginia birthing facilities [1] [6].

### Department of Medical Assistance Services (DMAS)
Virginia Medicaid (DMAS) tracks births paid by Medicaid by matching birth records to a database of enrolled individuals [1]. DMAS publishes focus studies on prenatal care, birth outcomes, and HEDIS measures [7] [8].

### Virginia Health Information (VHI)
VHI manages the All-Payer Claims Database (APCD) and the Emergency Department Care Coordination (EDCC) program, providing real-time data-sharing functionality to care providers [9] [2].

### March of Dimes and CDC WONDER
The March of Dimes PeriStats platform uses National Center for Health Statistics (NCHS) final natality data to calculate locality-level preterm birth rates [3]. CDC WONDER provides publicly accessible vital statistics data compiled from 57 jurisdictions [1].

## Table: Choosing the Right Source for the Question
A source-to-question matrix is essential to prevent apples-to-oranges analytical errors in Richmond.

| Source / Owner | Underlying Data | Best Richmond Use Case | Known Limitations |
| :--- | :--- | :--- | :--- |
| **VDH Vital Records** | Birth/death certificates | Locality-level time series and detailed race/ethnicity reporting. | Lags in final data publication; ongoing updates change historical counts [1]. |
| **VHHA / VNPC Dashboard** | Inpatient hospital discharges | Facility-level quality improvement (QI) and Severe Maternal Morbidity (SMM) tracking [6]. | Represents in-hospital events, not resident births; collapses race to White/Black/Other [1]. |
| **DMAS Focus Studies** | Medicaid claims & enrollment | Tracking payer-specific performance and postpartum care access [1]. | Only covers Medicaid population; counts differ from Vital Records due to matching methodology [1]. |
| **CDC WONDER** | NCHS Natality/Mortality | National and state-level benchmarking [1]. | Fixed cut-off dates cause slight variations from state-updated Vital Records [1]. |
| **VDH PRAMS** | Postpartum surveys | Understanding maternal behaviors, social factors, and prenatal experiences [1]. | Sample-based; small sample sizes at the locality level (e.g., Richmond n=309 in 2020) [10]. |

*Takeaway:* Analysts must pre-commit to a "resident denominator default" (Vital Records/WONDER) for Richmond locality rates, reserving hospital discharge data strictly for facility-level clinical improvement.

## Why Numbers Don't Match: Definitions, Denominators, and Data Hygiene
Most data inconsistencies in Richmond's maternal health landscape are expected artifacts of differing methodologies, but they cause severe friction if not explicitly managed.

### Resident vs. Event Data: The Denominator Problem
In 2022, CDC WONDER reported 95,630 total births for Virginia residents [1]. In contrast, the VHHA Maternal Health Dashboard reported 89,366 inpatient hospital deliveries [1]. Meanwhile, DMAS reported 37,046 Medicaid-paid births [1]. These numbers conflict because they measure different things: WONDER measures births to Virginia residents (including out-of-state births), VHHA measures delivery events inside Virginia hospitals (including out-of-state residents delivering in VA), and DMAS measures births matched to Medicaid enrollment [1] [6].

### Measure Definitions: Maternal vs. Pregnancy-Associated
Conflating mortality definitions inflates or deflates trendlines. Virginia strictly defines:
* **Maternal Mortality:** Death while pregnant or within 42 days of termination of pregnancy [11].
* **Pregnancy-Related Death:** Death during or within one year of pregnancy, caused by a pregnancy complication [2].
* **Pregnancy-Associated Death:** Death while pregnant or within one year of pregnancy, irrespective of cause [2].

### Coding Variability and Equity Blind Spots
The VHHA Maternal Health Dashboard suffers from inconsistent reporting of race codes by hospitals, forcing the data to be stratified only into White, Black, and "Other Race" [1]. In 2023, 30.83% of hospital deliveries were categorized as "Other Race" [1]. This architectural limitation obscures critical disparities among Hispanic, Asian, and Indigenous populations in Richmond.

### Sample vs. Census Constraints
While Vital Records capture the entire population, PRAMS relies on a randomized sample. In 2020, only 309 women residing in the Richmond City Health District completed the PRAMS survey [10]. Single-year city cuts of PRAMS data can be noisy, requiring multi-year pooling for stable estimates.

## Concrete Harms from Fragmentation and Duplicated Analysis
The lack of a unified data architecture in Richmond creates tangible harms for public health planning and equity initiatives.

### Policy Misfires from Geographic Blurring
Hospitals in Virginia's Central region accounted for 17.73% of the state's deliveries in 2023 [1]. Because VHHA data represents facility catchment areas rather than patient residence, using hospital data to claim "Richmond rates" blurs geography [1] [6]. This can steer funding away from true high-burden neighborhoods.

### Missed Postpartum Risk Interventions
Despite 40% of pregnancy-associated deaths being driven by accidental overdoses [4], obstetric data and behavioral health data remain siloed. Without linking DMAS postpartum data with VHI's Emergency Department Care Coordination (EDCC) alerts, Richmond misses critical windows to intervene when postpartum individuals present at the ED for substance use issues.

### Grant Friction and Credibility Loss
When local nonprofits apply for grants using conflicting birth counts (e.g., citing WONDER in one section and DMAS in another without explaining the denominator), it undercuts the credibility of the needs assessment. 

## Richmond Analyst's Workflow—Where It Breaks and How to Fix It
For a data analyst at a Richmond nonprofit or agency, the workflow breaks down at several predictable friction points:

1. **Source Discovery & Access:** High-value clinical data (like VHHA Analytics) is restricted to member hospitals or requires complex Data Use Agreements (DUAs) [12] [6]. Public-facing dashboards often suppress small-N data at the ZIP code level.
2. **Denominator Alignment:** Analysts waste hours reconciling why VDH Vital Records and CDC WONDER have slight variations for the exact same year (due to WONDER's fixed cut-off dates vs. VDH's ongoing updates) [1].
3. **Race/ZIP Stratification:** Attempting to map racial disparities at the neighborhood level fails when hospital data dumps 30% of patients into an "Other Race" bucket [1].

**The Fix:** Analysts must adopt a standard operating playbook that includes a one-page "Source-of-Truth Matrix," a strict definition glossary, and an update calendar tied to state release cycles.

## Action Plan: A Richmond Maternal Data Governance Kit (90 days)
To bypass fragmentation without waiting for new state-level technology, Richmond stakeholders should implement a lightweight governance kit.

### Adopt a Richmond Maternal Data Specification
Align local reporting with the Virginia Task Force on Maternal Health Data and Quality Measures (RD136), which issued 22 recommendations on data standardization and linkage [13]. Mandate that all local reports explicitly label denominators (e.g., "Resident Births" vs. "Hospital Deliveries").

### Build a 5-KPI Dashboard with Explicit Sources
Create a unified Richmond dashboard tracking:
1. **Preterm Birth Rate:** Sourced from Vital Records/NCHS [3].
2. **Infant Mortality:** Sourced from Vital Records [1].
3. **NTSV C-Section Rate:** Sourced from VHHA for hospital QI [1].
4. **Postpartum Visit Completion:** Sourced from DMAS HEDIS [5].
5. **SUD Engagement:** Sourced from DMAS/VHI linkages [2].

### Establish a Postpartum Overdose Sentinel
Leverage VHI's EDCC program to flag Medicaid-enrolled birthing people who present at emergency departments with overdose or OUD diagnoses within one year postpartum [9]. Trigger immediate outreach from local health district navigators.

## Facts, Inferences, Unknowns

### Facts (with source titles)
* **Preterm Birth:** Richmond City's preterm birth rate is 12.5% (Grade F), based on 2024 NCHS final natality data (*2025 March Of Dimes Report Card For Virginia*) [3].
* **Maternal Mortality Rates:** Virginia's maternal mortality rate was 34.5 per 100,000 live births (2019-2023). The pregnancy-associated death rate was 62.3 per 100,000 (2018-2022) (*Maternal & Child Health - Data*) [4].
* **Overdose Impact:** 40% of pregnancy-associated deaths in Virginia (2018-2022) were due to accidental overdose, and 37.4% occurred 43-365 days postpartum (*Maternal & Child Health - Data*) [4].
* **Racial Disparities:** Black women in Virginia experienced pregnancy-associated deaths at a rate of 89.5 per 100,000, compared to 53.5 for White women from 2018-2020 (*VHHA Partners with Health Care Organizations on Five-Part Maternal Health Data Webinar Series*) [2].
* **Data Discrepancies:** In 2022, CDC WONDER reported 95,630 births, VHHA reported 89,366 hospital deliveries, and DMAS reported 37,046 Medicaid births (*Virginia Maternal Health Task Force Environmental Scan*) [1].
* **PRAMS Sample Size:** In 2020, 309 women residing in the Richmond City Health District completed the PRAMS survey (*Richmond, VA PRAMS FACTS- 2020*) [10].
* **Hospital Data Limitations:** The VHHA Maternal Health Dashboard stratifies race only into White, Black, and Other Race due to inconsistent reporting (*Virginia Maternal Health Task Force Environmental Scan*) [1].

### Inferences (clearly labeled)
* *Inference:* Using hospital discharge data as a proxy for Richmond resident rates likely overstates or understates the true city burden due to regional patient flows across county lines.
* *Inference:* The aggregation of race into an "Other" category in hospital data (accounting for ~30% of deliveries) risks hiding specific prematurity and morbidity patterns among Richmond's Hispanic and Asian populations.
* *Inference:* Aligning DMAS postpartum HEDIS data and VHI EDCC alerts with local Richmond outreach efforts could directly reduce postpartum overdose mortality.

### Unknowns (what cannot be verified publicly)
* Current-year, Richmond-specific maternal mortality or Severe Maternal Morbidity (SMM) rates (these are often suppressed at the city level due to small sample sizes).
* Public access to facility-specific or ZIP-code-stratified SMM data in Richmond from VHHA (this data is restricted to participating hospitals and specific task forces).
* The exact overlap of out-of-state residents delivering in Richmond hospitals versus Richmond residents delivering outside the city.

### Assessment of primary friction points in the maternal health data workflow
The primary friction points for analysts are **denominator misalignment** (comparing resident births to hospital events), **definitional confusion** (mixing maternal vs. pregnancy-associated mortality), **data suppression/access barriers** (inability to access ZIP-level or facility-level SMM data without DUAs), and **coding degradation** (loss of granular race/ethnicity data in hospital feeds). These frictions force analysts to spend more time reconciling datasets than generating actionable insights for Richmond's vulnerable neighborhoods.

## References

1. *Virginia Maternal Health Task Force Environmental Scan*. https://govnpc.org/wp-content/uploads/2025/06/MHTF-Environmental-Scan.pdf
2. *VHHA Partners with Health Care Organizations on Five-Part Maternal Health Data Webinar Series - VHHA*. https://vhha.com/pressroom/vhha-partners-with-health-care-organizations-on-five-part-maternal-health-data-webinar-series/
3. *2025 March Of Dimes Report Card For Virginia | PeriStats | March of Dimes*. https://www.marchofdimes.org/peristats/reports/virginia/report-card
4. *Maternal & Child Health - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/
5. *Maternal Health Data Sources - Maternal Health*. https://www.vdh.virginia.gov/maternal-health/maternal-health-data-sources/
6. *VNPC Maternal and Infant Health Data Webinar Part 1 ...*. https://www.youtube.com/watch?v=hl1asRG-sok
7. *2023–24 Medicaid and CHIP Maternal and Child Health ...*. https://www.dmas.virginia.gov/media/xx2hrx3d/2023-2024-medicaid-and-chip-maternal-and-child-health-focus-study.pdf
8. *2019–20 Prenatal Care and Birth Outcomes Focus Study*. https://www.dmas.virginia.gov/media/5182/2019-2020-prenatal-care-and-birth-outcomes-focus-study.pdf
9. *Strengthening Maternal and Infant Care in Virginia ⎸ VHI*. https://www.vhi.org/2026/01/13/strengthening-virginias-maternal-and-infant-care-through-data
10. *Richmond, VA PRAMS FACTS- 2020*. https://www.vdh.virginia.gov/content/uploads/sites/67/2021/10/Richmond-Health-District.pdf
11. *Maternal Mortality - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/maternal-mortality/
12. *Data Analytics - VHHA Analytics - VHHA*. https://vhha.com/vhha-analytics/
13. *RD136 (Published 2024) - 2023 Task Force on Maternal Health Data and Quality Measures Report*. https://rga.lis.virginia.gov/Published/2024/RD136