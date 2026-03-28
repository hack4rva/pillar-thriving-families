> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Two Paths to Thriving Families—Which Ships by Sunday, Which Scales by Policy

## Executive Summary
For the Hack for RVA 2026 event, the "Thriving Families" pillar presents two distinct problem statements: Expanding Youth Employment Pathways and Maternal Health Data Coordination. While both received a 23/32 ("Needs work") rubric score, they suffer from opposite challenges. Youth Employment is highly operational and software-shaped, offering a clear path to a Sunday demo using public data, but it risks duplicating existing city portals. Maternal Health is policy-shaped and constrained by strict Protected Health Information (PHI) regulations, making a functional 48-hour prototype nearly impossible without pivoting to a non-clinical scope. 

For a mixed-skills team (1 developer, 1 researcher, 1 product), **Expanding Youth Employment Pathways is the recommended choice**. It provides tractable data, clear user definitions, and a direct continuation path with local Richmond partners. If the team insists on Maternal Health, they must strictly avoid clinical data exchange and instead build a referral directory tailored to local maternity navigators.

## Problem Context in Richmond

Mayor Danny Avula's Mayoral Action Plan (MAP) outlines seven pillars for a thriving city, with Pillar 3 focused on "Thriving Families (where every child succeeds)" [1]. The nonprofit partners guiding this pillar for the hackathon are Girls For A Change and the Richmond Ed Fund [2]. 

### Youth Employment Metrics Show Traction but Require Scale
The Office of Community Wealth Building (OCWB) and its Youth Engagement Services (YES) division have made significant strides in youth employment. Between 2013 and 2023, the percentage of Richmond youth aged 16-19 who are neither in school nor employed dropped from 13% to 5.3% [3]. The flagship Youth Works RVA program places youth aged 14-24 in 7-week summer jobs paying $13 per hour for 15-25 hours weekly [3]. For Summer 2026, the city aims to serve 750 youth [4]. The MAP explicitly tracks the percentage of high school graduates entering the workforce with a living-wage job [1].

### Maternal Health Relies on Complex Interoperability Standards
Maternal health data coordination in Virginia is a highly regulated, multi-agency effort. The Virginia Department of Health (VDH) and Virginia Health Information (VHI) manage massive data infrastructures, including the All-Payer Claims Database (APCD) and the Emergency Department Care Coordination (EDCC) Program [5]. The EDCC provides real-time alerts to care managers when patients visit the ER, which has successfully reduced ER visits by 25% and hospitalizations by 35% in specific care models [5]. Additionally, federal efforts are underway to standardize maternal health data through the USCDI+ Maternal Health initiative [6]. Locally, the Richmond City Health District (RCHD) operates a Maternity Navigation line to manually connect uninsured pregnant individuals to prenatal care and financial assistance [7].

## Side-by-Side Feasibility Comparison

The two problem statements diverge significantly across every practical dimension required for a 48-hour hackathon build.

| Dimension | Expanding Youth Employment Pathways | Maternal Health Data Coordination | Key Takeaway |
| :--- | :--- | :--- | :--- |
| **Data Tractability (48 Hours)** | **High**: Public program details, employer calls, and MAP metrics are available. No PHI is required. Demo data can be easily seeded [1] [3] [8]. | **Low**: Relies on PHI, HIPAA-compliant systems, and state databases (EDCC, APCD) with 6-9 month lags [5]. Public dashboards are aggregate only [9]. | Youth data can be mocked safely; Maternal data requires synthetic generation to avoid legal violations. |
| **Problem Shape** | **Software-Shaped**: Focuses on intake, matching algorithms, employer coordination, and communication workflows [10]. | **Policy-Shaped**: Focuses on data standards (USCDI+), statewide mandates, and BAA agreements [6] [5]. | Youth needs a product; Maternal needs a policy agreement. |
| **User Clarity** | **Clear**: Richmond youth (14-24), YES program staff, and local employer hosts [10] [8]. | **Diffuse**: RCHD navigators, Medicaid care managers, OB/GYN practices, hospitals, and patients [5] [7]. | Youth allows for targeted user personas; Maternal risks scope creep. |
| **Demo Path by Sunday** | **Clear**: A live-feel web app showing youth intake, rules-based employer matching, and an admin dashboard tracking MAP goals [1]. | **Narrow**: A standards-mapping tool or a simulated referral directory. Cannot show live patient data [6] [7]. | Youth provides a visually impactful demo; Maternal risks looking like a "toy app." |
| **Harm Risk** | **Moderate**: Risks include algorithmic bias in matching, misrouting applications, or reputational damage to the city. | **High**: Misleading clinical alerts or incorrect referral data could delay time-sensitive prenatal or postpartum care [5]. | Maternal requires strict "not for clinical use" guardrails. |
| **Continuation Partner** | **Local**: OCWB, YES, ChamberRVA, and Richmond Public Schools [10] [8]. | **State/Regional**: VDH, VHI, or RCHD [5] [7]. | Youth aligns perfectly with city-level hackathon sponsors. |

## Inferences

* **Inference on the 23/32 "Needs Work" Score**: The Youth Employment statement likely lost points because the city already has an active application portal for Youth Works RVA [11]. A hackathon solution must avoid duplicating this and instead focus on the *employer matching* or *capacity management* side. The Maternal Health statement likely lost points because it asks volunteers to solve a systemic interoperability problem (USCDI+ and EDCC integration) without providing the necessary legal data access or APIs for a weekend build.
* **Inference on Tractable Scope**: Youth Employment can credibly ship a placement operations tool. Maternal Health must completely avoid clinical coordination and focus strictly on social determinants of health (SDOH) navigation and referral directories to be shippable and safe.
* **Inference on Partner Readiness**: OCWB and ChamberRVA are actively recruiting employer partners right now for the Summer 2026 cohort [8] [4]. They are highly primed for a pilot that streamlines this immediate operational need.

## Recommendation for a Mixed-Skills Team

**Choose: Expanding Youth Employment Pathways.**
This problem offers the highest 48-hour data tractability, the clearest user definition, the safest harm profile, and the most demonstrable Sunday impact. 

### 48-Hour Build Plan
* **Product (1)**: Lock in the user story focusing on the YES placement coordinator and the employer host. Define three core flows: employer role posting, rules-based youth matching, and an admin dashboard. Set success metrics tied to the MAP: time-to-match, placements filled by ward, and host capacity utilized [1].
* **Researcher (1)**: Compile a catalog of 20-30 realistic employer roles based on ChamberRVA and YES program tracks (e.g., Teens in Richmond & Parks, Founders Mark) [10] [8]. Define eligibility heuristics (age bands, residency, transportation needs) and draft fairness guardrails to prevent matching bias.
* **Developer (1)**: Build a lightweight, no-PII web application. Create a rules-based matching engine, integrate commodity APIs for SMS/email notifications to employers, and build a dashboard that visualizes placement status against the city's 750-youth target [4].

### Continuation Pitch
Propose a 60-day pilot with OCWB and ChamberRVA to manage the Summer 2026 employer host onboarding. Offer to export all matched data directly into the city's existing systems.

## Alternative Scope: If You Must Choose Maternal Health

If the team is passionate about Maternal Health, you must pivot away from clinical data exchange. 

* **The Build**: Create a "Navigator Console" designed specifically for the RCHD Maternity Navigation line [7]. 
* **Features**: Build a structured intake form (capturing language, coverage status, and gestational age), dynamic eligibility prompts for Medicaid/WIC, and a highly searchable, localized referral directory with verified hours and language access.
* **Standards Artifact**: Include a data dictionary that maps your intake fields directly to the ONC's USCDI+ Maternal Health data elements to prove systemic alignment [6].
* **Guardrails**: Prominently label the prototype "Not for clinical decision-making" and use exclusively synthetic patient data for the Sunday demo.

## Unknowns

* **City API Access**: Does the city's existing Youth Works RVA application portal [11] allow for data exports, or will the prototype need to operate as a standalone shadow system?
* **Employer Constraints**: What are the specific liability, background check, and minor labor law constraints required by ChamberRVA for host employers? [8]
* **Minor Consent**: What are the data governance and parental consent requirements for sending automated SMS notifications to 14-year-olds?
* **Maternal Directory Freshness**: If building the Maternal Navigation tool, how frequently does RCHD currently update its community resource directory, and who owns that maintenance? [7]

## References

1. *Mayoral Action Plan | 2025*. https://rva.gov/sites/default/files/2025-10/2025-MAP-Oct15_F.pdf
2. *Hack for RVA 2026 | Building a Thriving Economy*. https://rvahacks.org/partners
3. *2025 ANNUAL IMPACT REPORT*. https://rva.gov/sites/default/files/2025-11/OCWB%202025%20Annual%20Report.pdf
4. *Youth Works RVA: Summer 2026 Applications Now Open! | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/news/youth-works-rva-summer-2026/
5. *Virginia Data to Support Maternal Health*. https://www.vdh.virginia.gov/content/uploads/sites/233/Virginia-Data-to-Support-Maternal-Health-presentation.pdf
6. *Improving Maternal Health by Leveraging Existing Resources, Data Linkage and Standard Reporting for Patient-Centered Outcomes Research | ASPE*. https://aspe.hhs.gov/improving-maternal-health-leveraging-existing-resources-data-linkage-standard-reporting
7. *Healthy Childbirth and Infancy - Richmond City Health Department*. https://www.vdh.virginia.gov/richmond-city/healthy-childbirth-and-infancy/
8. *Mayor's Youth Academy - Summer Work-Based Learning - ChamberRVA*. https://www.chamberrva.com/mayors-youth-academy-summer-work-based-learning
9. *Maternal Health Data Sources - Maternal Health*. https://www.vdh.virginia.gov/maternal-health/maternal-health-data-sources
10. *Youth Engagement Services | Richmond*. https://www.rva.gov/community-wealth-building/youth-engagement-services
11. *Youth Works RVA Application 26' | Richmond*. https://www.rva.gov/form/youth-works-rva-application-26