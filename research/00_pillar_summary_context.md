# Closing Richmond’s Data Gaps: Tech Paths to Youth Jobs & Maternal Health Wins

## Executive Summary

Richmond faces two critical, data-driven challenges that directly impact family stability and economic mobility: a fragmented youth employment ecosystem and a siloed maternal health data landscape. For the upcoming Richmond Civic Hackathon, these problem areas present immediate opportunities for high-impact technological interventions. 

First, the youth employment pathway is obstructed by discovery and administrative friction. While programs like Youth Works RVA aim to place 750 youth in paid experiences [1], the lack of a centralized directory (Data Readiness Score: D3=1) forces stakeholders into inefficient manual matching. Furthermore, legal requirements—such as the Virginia Department of Labor and Industry (DOLI) mandate that 14- and 15-year-olds secure an employment certificate *after* receiving a firm job offer but *before* starting work [2] —create narrow windows where paperwork delays can cost youth their jobs. 

Second, maternal health organizations are burning critical staff hours duplicating data analysis. Despite the existence of robust public datasets from the Virginia Department of Health (VDH) [3] and the KIDS COUNT Data Center [4], agencies independently compile the same metrics. With federal funding facing pressure, creating a unified, automated data coordination platform is no longer just a convenience—it is a fiscal necessity. 

**Key Strategic Imperatives:**
* **Build a Unified Youth Job Portal:** Consolidate fragmented program data into a single discovery platform to eliminate the "invisible maze" of opportunities.
* **Automate Compliance Workflows:** Integrate a "permit wizard" to guide youth through DOLI employment certificates and USCIS I-9 document collection, preventing administrative job loss.
* **Leverage Transit Data:** Overlay GRTC's Zero Fare routes (funded through FY26) [5] onto job maps to ensure equitable access, while planning for potential funding cliffs by 2031 [6].
* **Deploy a Shared Maternal Health Schema:** Centralize VDH, ACS, and KIDS COUNT data into a single dashboard template to reclaim wasted analytical hours and standardize reporting across Richmond nonprofits.

## 1. Richmond Youth Employment Landscape—Programs, Capacity & Deadlines

The current youth employment landscape in Richmond is characterized by high demand, limited slots, and severely fragmented information. Youth and their families must navigate multiple disparate portals, deadlines, and eligibility requirements to secure summer employment or internships.

### Mayor’s Youth Academy vs. Youth Works RVA: Overlap & Gaps

The Office of Community Wealth Building is currently driving the Youth Works RVA program for Summer 2026, aiming to serve 750 Richmond youth ages 14 through 24 [1]. The program offers paid work experiences, career exploration, and professional development [1]. However, the application window is tight, closing on March 31, 2026 [1]. This creates a bottleneck for discovery, as youth must find the application, attend virtual information sessions (held March 11 and March 16), and secure necessary documentation within a matter of weeks [1].

### Non-profit Add-ons—Girls For A Change, RPS Ed Fund, Freedom School

Beyond municipal programs, various non-profits and educational institutions offer parallel opportunities, further complicating the discovery process:

| Organization / Program | Target Audience | Opportunity Type | Key Details |
| :--- | :--- | :--- | :--- |
| **Youth Works RVA** | Ages 14-24 | Paid work, career exploration | 750 slots; March 31, 2026 deadline [1]. |
| **Richmond Public Schools (RPS)** | Students / Aspiring Educators | Student interns, practicums | Placements for the 2025-2026 academic year [7]. |
| **Richmond Freedom School** | Young Leaders | Servant Leader Interns (SLIs) | Paid leadership opportunity for Summer 2026 [8]. |
| **Youth Engagement Services** | Ages 14-24 | Career exploration | Safe space to explore diverse career paths [9]. |

*Takeaway: The lack of a centralized API or directory means youth must independently track at least four different organizational timelines and application portals, increasing the risk of missed opportunities.*

### Stakeholder Map & Data-Readiness Score (D3 = 1)

The problem statement's critical D3=1 data readiness score highlights the absence of a compiled dataset of Richmond youth employment programs, employer directories, or transit overlays. Hackathon teams must prioritize data scraping, aggregation, and schema standardization to build a functional prototype.

## 2. Administrative & Legal Hurdles—Permits, IDs, I-9

Securing a job offer is only the first step; the administrative onboarding process is where many youth fall out of the pipeline. A single missing document can cancel a job offer, making tech-enabled preparation critical.

### DOLI E-Certificate Flow & Drop-Off Points

Virginia law requires all 14- and 15-year-old workers to obtain an Employment Certificate prior to performing any work [2]. Crucially, youth *must not* begin the registration process until they have a firm offer of employment [2]. 

The Virginia Electronic Employment Certificate System (VAeECS) requires three distinct registrations: Youth, Employer, and Parent/Guardian/Custodian [2]. Once all three are complete, the system generally approves the application within 24 hours, but it only becomes valid once signed by the youth worker [2]. This multi-party dependency creates significant drop-off risk if any party delays their portion of the application.

### I-9 Acceptable Documents Checklist for Minors

Federal USCIS Form I-9 compliance presents another hurdle. Employees must present either one List A document (establishing both identity and employment authorization) or a combination of one List B (identity) and one List C (employment authorization) document [10] [11]. 

For minors under 18 who lack standard IDs (like a driver's license), USCIS provides specific List B alternatives:

| Document Category | Standard Acceptable Documents | Alternatives for Minors (Under 18) |
| :--- | :--- | :--- |
| **List B (Identity)** | Driver's license, State ID card, School ID with photograph [10] [11]. | School record or report card; Clinic, doctor, or hospital record; Day-care or nursery school record [10] [11]. |
| **List C (Employment)** | Unrestricted Social Security Card, Original/certified Birth Certificate [10] [11]. | N/A (Must provide standard List C document) [10] [11]. |

*Takeaway: Hackathon solutions should include a digital checklist or "wizard" that helps youth identify which specific documents they possess before they apply, reducing employer rejection rates.*

### Cost/Time Analysis of DMV ID Acquisition

To aid in identity verification, the Richmond Redevelopment & Housing Authority and the City of Richmond host DMV Pop-Up Events to help youth secure Virginia Identification Cards [1]. However, payment is required at the time of service, with costs ranging from $10 to $26 [1]. For low-income youth, this out-of-pocket expense, combined with the need to pre-register for limited pop-up slots [1], represents a tangible barrier to entry.

## 3. Transit Access Advantage—Zero Fare, Pulse BRT, Micro-Transit Zones

Transportation is a primary determinant of employment access. GRTC's current fare policies significantly expand the job catchment area for Richmond youth, but long-term fiscal realities threaten this advantage.

### High-Frequency Corridors & Youth Employment Hotspots

GRTC's network, including the Pulse BRT and high-frequency local routes, connects key residential areas to commercial hubs [12]. The Zero Fare program, launched in 2020, has removed financial barriers and boosted ridership, which is on track to exceed 11 million riders in FY25 [13]. 

### Funding Scenario Table: FY26 Secure vs. FY27-31 Gap

While Zero Fare is fully funded through June 30, 2026 (FY26) via a mix of DRPT TRIP grants, VCU contributions, and GRTC reserves [13] [5], the long-term outlook is precarious. 

| Fiscal Year | Zero Fare Status | Projected Operating Deficit | Key Funding Sources |
| :--- | :--- | :--- | :--- |
| **FY25** | Active | N/A | TRIP Grant ($4.56M), VCU ($1.2M), GRTC Reserve ($1.04M) [13] [5]. |
| **FY26** | Active | N/A | TRIP Grant ($4.56M), VCU ($100K), GRTC Reserve ($3.2M) [5]. |
| **FY30** | At Risk | Major deficit begins [6]. | TBD (Requires TAP, Advertising, Philanthropy) [13] [6]. |
| **FY31** | At Risk | $39.5 Million (30% gap) [6]. | TBD [6]. |

*Takeaway: Hackathon transit overlays must account for current Zero Fare routes to maximize job discovery for Summer 2026, but should be architected to handle potential fare reinstatements in future iterations.*

### Micro-Transit Pilot Costs per Trip—What to Scale, What to Skip

GRTC's LINK microtransit service operates in five pilot zones, providing crucial first-mile/last-mile connectivity [6]. However, the cost per trip varies wildly, indicating which zones are most efficient for youth transit routing:

| Pilot Zone | FY25 Cost | Cost per Trip |
| :--- | :--- | :--- |
| **Azalea** | $815,603.39 | $29.81 [6]. |
| **Ashland** | $948,294.73 | $45.52 [6]. |
| **Sandston** | $610,151.09 | $58.25 [6]. |
| **Powhatan** | $256,132.27 | $81.66 [6]. |
| **Cloverdale** | $549,572.98 | $83.04 [6]. |

*Takeaway: Routing algorithms should prioritize fixed-route transit (which accounts for 97% of ridership but only 84% of costs) [6] and highly efficient microtransit zones like Azalea, while deprioritizing expensive zones like Cloverdale and Powhatan for daily youth commuting.*

## 4. Maternal Health Data Ecosystem—Current Dashboards vs. Duplication

The maternal health ecosystem in Richmond suffers from analytical redundancy. Multiple agencies independently pull from the same public data sources, wasting resources and producing inconsistent reporting metrics.

### Inventory Table: VDH MCH, PRAMS, Kids Count, VHI, ACS

The data required to track maternal and child health outcomes already exists across several robust platforms:

| Data Source | Key Metrics Available | Geographic Granularity |
| :--- | :--- | :--- |
| **VDH Maternal & Child Health** | Birth/death certificates, inpatient hospitalizations, PAMSS [3]. | State, Local Health Districts [3]. |
| **VA PRAMS** | Pre-pregnancy, pregnancy, and postpartum experiences [14]. | Stratified by Richmond City Health District (RCHD) [14]. |
| **KIDS COUNT Data Center** | Infant mortality (deaths under 1 year per 1,000 live births), teen birth rates [4] [15]. | State, County, Locality (Richmond City) [4]. |
| **Census ACS (data.census.gov)** | Median household income, poverty status (S1701), fertility (S1301) [16] [17]. | City, Census Tract [18] [16]. |
| **Virginia Health Information (VHI)** | Healthcare data, comprehensive dashboards, statewide data exchange [19]. | Statewide [19]. |

### Typical Redundant Workflow—Case Study of Three Agencies

Currently, stakeholders independently download raw data from VDH (e.g., infant mortality rates [4]) and the Census Bureau (e.g., poverty status [16]), clean the data, and build custom visualizations for grant reporting. This duplicated effort drains capacity that could be spent on direct service, especially critical given reduced federal funding.

### Proposed Unified Metrics Schema & Governance Model

Hackathon teams should focus on building a unified data pipeline that automatically ingests APIs from VDH, KIDS COUNT, and the Census Bureau. By establishing a shared schema, nonprofits can access a single, auto-updating dashboard that exports standardized CSVs and charts tailored to common grant requirements.

## 5. Socio-Economic & Equity Context—Poverty, Birth Outcomes, Youth Demographics

Effective technological interventions must be grounded in the socio-economic realities of Richmond. The intersection of poverty, transit access, and health outcomes dictates where resources should be targeted.

### ACS Snapshot—Income, Insurance Coverage for Women 15-44

According to the U.S. Census Bureau, the median household income in Richmond city (in 2024 dollars) for the 2020-2024 period was $64,587 [18]. However, poverty remains a significant issue, as tracked by ACS Table S1701 (Poverty Status in the Past 12 Months) [16] [20]. This economic baseline directly impacts both a youth's need for early employment and a mother's access to consistent prenatal care.

### Kids Count Indicators—Infant Mortality, Teen Births

The KIDS COUNT Data Center tracks critical localized metrics. Infant mortality is measured as the number of deaths among children under one year of age per 1,000 live births, reported by the mother's place of residence [4] [21]. Additionally, teen birth rates are tracked for youth ages 15-19 [15]. These indicators serve as primary benchmarks for maternal health interventions.

### GIS Overlay: Poverty + Transit + Birth Outcomes

The most valuable tool a hackathon team could build is a GIS overlay that maps ACS poverty data [16], KIDS COUNT infant mortality rates [4], and GRTC Zero Fare transit routes [12]. This would allow policymakers to visually identify "transit-poor, high-risk" census tracts and deploy targeted microtransit or mobile health clinics accordingly.

## 6. Opportunity Space for Hackathon Teams—Feature Backlog & API Hooks

To deliver maximum value during the March 27–29 hackathon, teams should focus on high-impact, low-code integrations.

### Must-Have Features—Permit Wizard, Program Finder, Data-Share Hub

1. **Youth Program Finder:** A map-based directory aggregating Youth Works RVA [1], RPS internships [7], and Freedom School slots [8].
2. **Permit & I-9 Wizard:** An interactive checklist guiding youth through the DOLI VAeECS requirements (emphasizing the need for a firm job offer first) [2] and USCIS List B/C document collection (highlighting school/clinic records for minors) [10] [11].
3. **Maternal Health Data Hub:** A centralized dashboard pulling VDH MCH indicators [3] and KIDS COUNT data [4] into a unified view.

### “Nice-to-Have” Predictive Layers—Commute Time, Risk Scores

Advanced teams can integrate GRTC's system map [12] to calculate transit commute times from specific neighborhoods to major youth employers, factoring in the efficiency of microtransit zones like Azalea vs. Powhatan [6].

### API & Data License Cheat-Sheet

Teams should utilize the Census Data API for S1701 (Poverty) [16] and S1301 (Fertility) [17], alongside the Annie E. Casey Foundation's KIDS COUNT data center exports for localized infant mortality [4].

## 7. Risks & Failure Cases—Funding, Privacy, and Adoption

### Funding Cliff Matrix—Zero Fare & Federal MCH Cuts

Any transit-dependent youth employment solution must acknowledge that GRTC's Zero Fare is only guaranteed through FY26 [5]. Projections show a $39.5 million operating deficit by 2031 [6], meaning apps should eventually support fare-calculation logic.

### Data-Privacy Table—HIPAA vs. FERPA vs. FOIA

When handling maternal health data, teams must rely strictly on aggregated, de-identified public datasets (like PRAMS, which is stratified at the health district level [14]) to avoid HIPAA violations. Youth employment portals must avoid storing sensitive PII (like Social Security Numbers required for I-9s [10]), acting instead as a guide rather than a repository.

### Adoption Barriers—Employer Tech Readiness & Youth Digital Divide

The DOLI electronic certificate system requires employer registration [2]. If employers find the state portal cumbersome, they may simply refuse to hire 14- and 15-year-olds. Hackathon solutions must focus on youth preparedness to offset employer friction.

## 8. Implementation Roadmap—90-Day MVP to 12-Month Scale-Up

### Timeline Gantt

| Phase | Timeframe | Key Deliverables |
| :--- | :--- | :--- |
| **Sprint 1 (Hackathon)** | Days 1-3 | MVP Program Finder; Static Maternal Health Dashboard; I-9 Checklist. |
| **Sprint 2 (Pilot)** | 30-60 Days | Integrate GRTC transit overlays; automate VDH/Kids Count API ingestion. |
| **Sprint 3 (Scale)** | 90-120 Days | Launch Permit Wizard; onboard local nonprofits to shared data schema. |

### Roles & Ownership—Product, Data Steward, Outreach

Successful deployment requires the Office of Community Wealth Building to own the youth program directory, while a coalition of health nonprofits must agree to designate a single "Data Steward" to maintain the maternal health dashboard schema.

### Success Metrics—Permit Processing Time, Program-Fill Rate, Dashboard Reuse Count

The ultimate measure of success will be a reduction in unfilled Youth Works RVA slots (aiming to fill all 750 [1]), a decrease in DOLI certificate rejection rates, and the number of hours saved by nonprofits utilizing the unified maternal health dashboard.

## Appendix—Source Fact Sheets & URLs

**Output Requirements Addressed:**
* **Facts (with URLs):** 
 * Youth Works RVA Summer 2026 application deadline is March 31, 2026 (https://www.rrha.com/news/youth-works-rva-summer-2026/) [1].
 * 14- and 15-year-olds in VA must have a firm job offer before applying for an Employment Certificate (https://doli.virginia.gov/programs/labor-law/youth-employment/) [2].
 * GRTC Zero Fare is funded through FY26 (https://www.ridegrtc.com/wp-content/uploads/2025/05/GRTC-Board-Packet-05-20-2025.pdf) [5].
 * Richmond city median household income is $64,587 (https://www.census.gov/quickfacts/fact/table/richmondcityvirginia/INC110224) [18].
* **Inferences (clearly labeled):** 
 * *Inference:* Because DMV pop-up IDs cost $10-$26 [1] and Richmond has a high poverty rate [16], the cost of obtaining an ID is likely a primary barrier preventing low-income youth from completing I-9 requirements and securing employment.
 * *Inference:* Given GRTC's projected $39.5M deficit by 2031 [6], the Zero Fare program is highly vulnerable to cancellation, which would drastically shrink the accessible job market for youth.
* **Unknowns (what cannot be verified publicly):** 
 * The exact number of youth who receive job offers but fail to start due to incomplete DOLI certificates or I-9 documentation.
 * The specific amount of federal maternal health funding cut for Richmond-area nonprofits in FY26.
* **Richmond-specific context:** 
 * PRAMS data is uniquely stratified for the Richmond City Health District (RCHD) [14], providing a localized advantage for maternal health analysis.
 * GRTC's microtransit (LINK) operates in specific zones relevant to the metro area (Azalea, Ashland, Sandston, Cloverdale, Powhatan) [6], which must be factored into regional job accessibility.

## References

1. *Youth Works RVA: Summer 2026 Applications Now Open! | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/news/youth-works-rva-summer-2026/
2. *DOLI – Virginia Department of Labor and Industry  - Youth Employment*. https://doli.virginia.gov/programs/labor-law/youth-employment/#:~:text=Minors%2014%20and%2015%20must,in%20certain%20particularly%20hazardous%20jobs.
3. *Maternal & Child Health - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/
4. *Infant mortality | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/3236-infant-mortality
5. *Board of Directors Meeting Agenda*. https://www.ridegrtc.com/wp-content/uploads/2025/05/GRTC-Board-Packet-05-20-2025.pdf
6. *Board Retreat - Richmond*. https://www.ridegrtc.com/wp-content/uploads/2025/10/FY2026-Board-Retreat.pdf
7. *Teacher & Leader Pathways - Richmond Public Schools*. https://www.rvaschools.net/talent-office/teacherpathways
8. *Richmond Freedom School is currently recruiting Servant ...*. https://www.facebook.com/edfundwest/posts/richmond-freedom-school-is-currently-recruiting-servant-leader-interns-slis-for-/1311813167661235/
9. *Summer internships | Announcement Details*. https://rtc.rvaschools.net/about-us/announcement-details/~board/richmond-technical-center-board/post/summer-internships
10. *Form I-9 Acceptable Documents | USCIS*. https://www.uscis.gov/i-9-central/form-i-9-acceptable-documents
11. *13.0 Acceptable Documents for Verifying Employment Authorization and Identity | USCIS*. https://www.uscis.gov/i-9-central/form-i-9-resources/handbook-for-employers-m-274/130-acceptable-documents-for-verifying-employment-authorization-and-identity
12. *Bus Routes - Richmond*. https://www.ridegrtc.com/maps-and-schedules/system-map/
13. *FISCAL YEAR 2026 BUDGET DOCUMENT - Richmond*. https://www.ridegrtc.com/wp-content/uploads/2025/07/Fiscal-Year-2026-Budget-Book.pdf
14. *Data Dashboards - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/
15. *Teen birth rate per 1,000 by age group | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/3235-teen-birth-rate-per-1000-by-age-group
16. *Population for whom poverty status is determined - Census Data*. https://data.census.gov/map?q=Richmond+County,+Virginia+Income+and+Poverty&tid=ACSST5Y2023.S1701
17. *S1301: Fertility - Census Bureau Table*. https://data.census.gov/table/ACSST1Y2023.S1301?q=Fertility&y=2023
18. *U.S. Census Bureau QuickFacts: Richmond city, Virginia*. https://www.census.gov/quickfacts/fact/table/richmondcityvirginia/INC110224
19. *Virginia Health Information ⎸ VHI*. https://www.vhi.org/
20. *S1701: Poverty Status in the Past ... - Census Bureau Table*. https://data.census.gov/table/ACSST1Y2023.S1701?q=s1701
21. *Infant mortality | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/6051-infant-mortality