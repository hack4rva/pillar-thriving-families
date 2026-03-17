# Thriving Families RVA MVP: The 10 Unknowns That Will Make or Break It

## Executive Summary

The success of the Thriving Families MVP hinges on three cross-cutting dependencies: transit reliability, verified work-based learning (WBL) capacity, and maternal data-sharing interoperability. While Richmond Public Schools (RPS) students are rapidly gaining skills—earning 1,960 industry certifications in the 2024-2025 school year [1] —the bottleneck to economic mobility is the opaque supply of credit-bearing WBL placements. Simultaneously, maternal health navigation is highly effective but lacks scale, serving only 285 clients in 2025 [2] despite 11.59% of surveyed Richmond mothers receiving inadequate prenatal care [3]. 

Crucially, both pathways rely on the Greater Richmond Transit Company (GRTC) zero-fare policy, which is funded through fiscal year 2026 but faces a $6.8 million funding gap thereafter due to the loss of a $3.8 million match from VCU and the expiration of state grants [4] [5]. The MVP must be designed to assume free fares for the next year while degrading gracefully if fares return, utilizing existing data rails like the Emergency Department Care Coordination (EDCC) program to scale maternal alerts without rebuilding an entire Health Information Exchange (HIE) [6].

## Why These Unknowns Matter Now

MVP choices for the civic hackathon team hinge entirely on transit, placement capacity, and data interoperability. Building a matching algorithm for youth employment is useless if the placements do not count toward graduation or if students cannot physically reach the job site. Similarly, building a new maternal health referral platform will fail if it duplicates the existing EDCC infrastructure [6]. The team must use the 48-hour sprint to quantify placement supply, map transit feasibility, and confirm local hospital adoption of EDCC alerts to ensure the MVP solves actual operational bottlenecks rather than theoretical ones.

## Youth Employment Pathways: Capacity is Opaque While Credentials Surge

Certifications are up sharply in RPS, but without clear WBL slot counts, employer intent, and transit fit, youth will struggle to convert skills into paid, for-credit experiences.

### RPS Skills Momentum Outpaces Placement Visibility
Strong skills growth exists within the district. In the 2024-2025 school year, RPS students earned 1,960 industry certifications, representing a 26% year-over-year increase [1]. Furthermore, 1,535 students earned one or more credentials, a 39% jump from the previous year [1]. However, the constraint is finding placements that actually count toward graduation.

### Aligning to High-Quality Work-Based Learning (HQWBL)
Aligning the MVP to HQWBL ensures graduation and accountability impact; misalignment risks low uptake. RPS explicitly defines HQWBL as experiences related to career goals, connected to a course, and performed with local partners [7]. Registered apprenticeships require approval from Virginia Works [7]. Conversely, "Career Connected Experiences" like job shadowing, guest speakers, and resume workshops do not count toward the 3E accountability measure or fulfill graduation requirements [7]. The MVP must default to HQWBL.

### The Placement Supply Black Box
While programs like the Mayor's Youth Academy provide structured summer WBL internships [8], the published capacity, waitlists, and sector demand are missing from the public record. This blocks the creation of effective matching logic in the MVP.

### Out-of-School Time (OST) as a Critical Feeder
Building bridges from OST participation to HQWBL placements captures immense prevention and pathway value. NextUp RVA manages a network of over 150 youth development organizations [9]. The city has attributed a 64% drop in youth gun violence incidents since 2017 to investments in these out-of-school time programs [9]. The MVP should track OST-to-WBL conversion as a core KPI.

### Transit as the Ultimate Enabler
Free fares help, but route and time feasibility remain barriers. GRTC is on track to exceed 11 million riders in FY25 [10]. The agency has expanded high-frequency routes and completed the first full year of LINK microtransit in five pilot zones [10]. The MVP must build transit scoring into every match to ensure youth can actually reach their placements.

## Maternal Health Data Coordination: Target Early Access and Postpartum Continuity

The small reach of current navigation programs compared to the high population need argues for EDCC-enabled alerts and Social Determinants of Health (SDoH) referrals triggered at diagnosis and discharge.

### High Demand vs. Limited Navigation Reach
Maternity navigation must scale to meet community needs. The Richmond and Henrico Health Districts (RHHD) Maternity Navigation team served 285 clients in 2025 [2]. However, 2022 PRAMS data for the Richmond City Health District reveals significant gaps: 11.59% of respondents had inadequate prenatal care, 9.58% had no insurance to pay for prenatal care, 13.35% felt depressed or lost interest postpartum, and only 6.99% received a home visit [3]. 

### Existing Data Rails: The EDCC Opportunity
The MVP should leverage the existing EDCC platform rather than duplicating it. VHI's EDCC program already features targeted functionality for maternal and infant health, including alerts for patients presenting with a recent history of delivery, maternal cohort tracking, and a specific Substance Exposed Infant (SEI) flag [6]. The unknown factor is the exact configuration and adoption rate among local Richmond hospitals.

### Leveraging Clinical Touchpoints for Referral Loops
Clinical touchpoints must be used to capture SDoH needs and measure referral closure. The RHHD WIC program serves an average of 8,781 people per month [2]. Additionally, 86.92% of surveyed mothers discussed postpartum contraception with a healthcare provider, and 85.97% had a postpartum checkup [3]. These high-volume touchpoints are ideal triggers for MVP referral workflows.

## Cross-Cutting Enablers and Risks

The MVP must be dependency-aware, flexing with transit funding realities while respecting HIPAA regulations to maximize SDoH impact.

### Zero-Fare Transit Through FY26, Unclear After
Plan A is free fares; Plan B is employer sponsorships and microtransit vouchers. GRTC's zero-fare program will continue through the FY26 budget, but keeping it in place results in a $6.8 million loss (6% of the proposed budget) [4]. The state's Transit Ridership Incentive Program (TRIP) grant has decreased, and VCU decided not to continue its $3.8 million matching contribution [4] [5]. GRTC is actively seeking community partners and philanthropic contributions to sustain the program long-term [4] [10].

### Privacy-First Design
To protect trust and accelerate integration approvals, the MVP must practice PHI minimalism with explicit consent. The EDCC should handle clinical data [6], while the MVP handles SDoH and navigation workflows.

## MVP Design Implications

The hackathon team should focus on two core modules with shared infrastructure:

### Module 1: Youth HQWBL Matching
* **Features**: Employer intent intake; RPS credit tagging (HQWBL vs. enrichment); transit feasibility scoring (integrating GRTC routes and LINK zones); OST-to-WBL conversion tracking.
* **Success Metrics**: Time-to-placement; percentage of placements counting for 3E accountability; show-up rate for placements with a transit-fit score of 80 or higher.

### Module 2: Maternal Navigation
* **Features**: Intake at pregnancy confirmation and hospital discharge; EDCC alert routing plan; WIC, home-visit, and PPD referral flows; closed-loop tracking.
* **Success Metrics**: Percentage of first-trimester care started; postpartum visits kept; PPD follow-up within 7 days; overall referral closure rate.

### Shared Infrastructure
* Consent management, data provenance tracking, dependency toggles (e.g., a "fares on/off" switch), and a unified KPI dashboard.

## 48-Hour Research Sprints: The Top 10 Open Questions

A focused weekend sprint can sufficiently de-risk placements, provider integration, and transit assumptions to greenlight the MVP scope. Here are the 10 most important open research questions for the hackathon team:

1. **Which Richmond hospitals and RHHD teams actively use EDCC maternal cohorts, alerts, and SEI flags?**
 * *Why it matters*: Determines the technical feasibility of an alert-driven navigation MVP. If hospitals aren't using it, the MVP must rely on manual clinic referrals.
 * *Source*: VHI EDCC program contacts; RHHD Population Health leaders; hospital CIOs.
 * *Answerable in 48h*: Likely yes (directional confirmation).
2. **What is the current WBL placement capacity, waitlist size, and sector breakdown across RPS, MYA, and ChamberRVA?**
 * *Why it matters*: Drives the matching logic and sector focus of the MVP. Without supply data, the app is an empty shell.
 * *Source*: RPS WBL office; Mayor's Youth Academy coordinators; ChamberRVA employer council.
 * *Answerable in 48h*: Partially (can likely get aggregate estimates).
3. **What is the youth transportation feasibility (transit-fit score) to the top 20 likely WBL placement sites?**
 * *Why it matters*: Predicts show rates and filters out unviable sites before youth apply.
 * *Source*: GRTC GTFS data; LINK microtransit zone maps; employer site addresses.
 * *Answerable in 48h*: Yes (via API/mapping tools).
4. **What is the local NEET (Not in Employment, Education, or Training) estimate for Richmond City by neighborhood/school tract?**
 * *Why it matters*: Targets outreach and pilot geographies. Nationally, 12% of 16-24 year olds are NEET [11], but local hotspots are unknown.
 * *Source*: ACS Public Use Microdata; KIDS COUNT data; RPS chronic absenteeism proxies.
 * *Answerable in 48h*: Yes (can generate a data-driven estimate).
5. **Which NextUp OST programs confer skills that credibly map to RPS HQWBL requirements?**
 * *Why it matters*: Converts after-school engagement into credit-bearing experiences, bridging the gap between violence prevention and workforce entry.
 * *Source*: NextUp OST Landscape studies; quick calls with top providers.
 * *Answerable in 48h*: Partially.
6. **What are the specific postpartum discharge workflows at local birthing hospitals?**
 * *Why it matters*: Identifies exactly where to embed PPD, WIC, and home-visit referrals to capture mothers at a high-yield coordination moment.
 * *Source*: L&D/postpartum nurse manager interviews; RHHD Maternity Navigation staff.
 * *Answerable in 48h*: Partially.
7. **What is the employer appetite for youth apprenticeships in priority sectors (healthcare, IT, trades)?**
 * *Why it matters*: Anchors the pipeline and curriculum. If employers only want college grads, the youth WBL model fails.
 * *Source*: ChamberRVA outreach; VCW Capital Region provider lists.
 * *Answerable in 48h*: Partially.
8. **If zero-fare ends, which employer or community partners are willing to fund transit passes via the Transit Access Partnership (TAP)?**
 * *Why it matters*: Ensures MVP resilience against funding volatility.
 * *Source*: GRTC TAP program contacts; RVA Rapid Transit advocates; major employer HR departments.
 * *Answerable in 48h*: Yes (can build a target list).
9. **What data-sharing constraints and consent templates are acceptable to RHHD and RPS legal teams?**
 * *Why it matters*: Speeds up integration approvals and prevents the MVP from being blocked by compliance issues prior to launch.
 * *Source*: RHHD legal/policy documents; RPS data governance guidelines.
 * *Answerable in 48h*: Partially.
10. **What are the specific referral integration points at high-throughput WIC sites?**
 * *Why it matters*: Identifies easy on-ramps for SDoH screening, given WIC serves an average of 8,781 people monthly [2].
 * *Source*: RHHD WIC managers.
 * *Answerable in 48h*: Yes.

## Data Integration Map

The MVP must use existing rails and avoid rebuilding infrastructure.

| System | What It Offers | Access Path | Constraints | MVP Integration |
| :--- | :--- | :--- | :--- | :--- |
| **VHI EDCC** | Real-time maternal/infant alerts; cohorts; SEI flags [6] | VHI/health system onboarding | HIPAA; BAAs; org configuration | Alert-to-navigator routing; care-team visibility |
| **RHHD Maternity Navigation** | Case management; benefits/WIC; referrals [2] | RHHD Population Health | Capacity; staffing limits | Intake + referral closure tracking |
| **RPS WBL/CTE** | Course/credential data; HQWBL tracking [1] [7] | RPS CTE/WBL leads | FERPA; SIS/API limits | Credit-tagging; placement verification artifacts |
| **NextUp Platform** | OST provider network; impact studies [9] | NextUp staff/reports | Non-standard data; MoUs | OST-to-HQWBL mapping |
| **GRTC (GTFS/LINK)** | Routes, headways, microtransit zones [10] | Public GTFS; GRTC ops | Service changes; funding volatility [4] | Transit feasibility scoring |

## Risks, Failure Cases, and Mitigations

Anticipate these three likely failure modes and bake mitigations into the MVP from day one:

* **Transit funding reversal mid-year**: If the $6.8 million gap [4] forces a return to fares, the MVP must have a pass sponsorship workflow ready and automatically re-match youth to nearer sites.
* **Non-credit experiences dominate**: If employers only offer job shadowing, youth won't get 3E credit [7]. The MVP must default to HQWBL and require a credit-tag before publishing opportunities.
* **Parallel data silos (The "Rebuild-the-HIE" trap)**: Do not build a new clinical database. Use EDCC for clinical alerts [6]; the MVP should handle SDoH and navigation only, utilizing rigorous consent protocols.

## KPIs and 90-Day Pilot Plan

A dual-track pilot across two high-need schools and one birthing hospital can validate matching logic and care coordination in 90 days.

* **Youth KPIs**: Time-to-placement $\le$ 21 days; $\ge$ 70% of placements count for HQWBL; $\ge$ 85% attendance when the transit-fit score is $\ge$ 80.
* **Maternal KPIs**: +15% timely prenatal initiation among navigated clients; $\ge$ 60% PPD screen follow-up within 7 days; $\ge$ 50% home-visit referral closure where eligible.

## Inferences and Unknowns

* **Inferences**: 
 * Because 86.92% of mothers receive postpartum contraception counseling and 85.97% attend a postpartum checkup [3], we infer that clinical discharge and immediate postpartum visits are the most reliable physical touchpoints to intercept mothers for SDoH and PPD navigation.
 * Because GRTC zero-fare requires $6.8M to sustain [4] and VCU pulled its $3.8M match [4] [5], we infer that transit access for youth and mothers is highly vulnerable post-FY26, necessitating software-level contingencies (like transit-fit scoring).
* **Unknowns**: 
 * The exact number of available, credit-bearing HQWBL employer slots currently open in Richmond.
 * The specific neighborhood-level NEET rates in Richmond (only the national 12% rate is confirmed [11]).
 * Which specific Richmond hospitals have actively turned on and configured the VHI EDCC maternal alerts and SEI flags [6] for their care coordinators.

## References

1. *Career & Technical Education - Richmond Public Schools*. https://www.rvaschools.net/academics/secondary/career-technical-education
2. *RHHD Highlights Women’s Health Services for International Women's Day 2026 - Richmond City Health Department*. https://www.vdh.virginia.gov/richmond-city/2026/03/06/rhhd-highlights-womens-health-services-for-international-womens-day-2026
3. *RCHD, VA PRAMS FACTS- 2022*. https://www.vdh.virginia.gov/content/uploads/sites/67/2025/01/RCHD-PRAMS-FACTS-2022.pdf
4. *Despite recent headlines, GRTC plans to continue zero-fare policy through 2026 budget*. https://www.richmonder.org/despite-recent-headlines-grtc-plans-to-continue-zero-fare-policy-through-2026-budget/
5. *VCU not committed to future funding for GRTC's $0 fares*. https://www.vpm.org/news/2025-04-08/grtc-vcu-rva-rapid-transit-free-fare-bus-ride-funding-faith-walker
6. *Strengthening Maternal and Infant Care in Virginia ⎸ VHI*. https://www.vhi.org/2026/01/13/strengthening-virginias-maternal-and-infant-care-through-data
7. *Workbased Learning - Richmond Public Schools*. https://www.rvaschools.net/academics/secondary/career-technical-education/workbased-learning
8. *Mayor's Youth Academy - Summer Work-Based Learning - ChamberRVA*. https://www.chamberrva.com/mayors-youth-academy-summer-work-based-learning
9. *Impact and Reports - NextUp RVA*. https://nextuprva.org/impact-and-reports/
10. *FISCAL YEAR 2026 BUDGET DOCUMENT - Richmond*. https://www.ridegrtc.com/wp-content/uploads/2025/07/Fiscal-Year-2026-Budget-Book.pdf
11. *The Disconnected Youth Problem | Richmond Fed*. https://www.richmondfed.org/podcasts/speaking_of_the_economy/2025/speaking_2025_09_03_disconnected_youth_labor