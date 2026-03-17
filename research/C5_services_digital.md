# Closing the Digital Gap: Youth Jobs and Maternal Health Data Tools in Richmond

## Executive Summary
Richmond’s digital service delivery landscape for youth workforce and maternal health reveals a stark contrast between robust statewide data infrastructure and fragmented, analog local execution. 

For youth employment, the City of Richmond’s YouthWorks RVA program successfully captures teen applications online, but its employer onboarding remains entirely analog, relying on emails and social media posts. Furthermore, teens face a fragmented search experience with no centralized digital aggregator for youth jobs. 

Conversely, maternal health organizations in Richmond benefit from a powerful suite of Virginia Department of Health (VDH) dashboards—including the Health Opportunity Index (HOI) and the Pregnancy Risk Assessment Monitoring System (PRAMS), which specifically oversamples Richmond. While local health districts like the Richmond and Henrico Health Districts (RHHD) effectively use digital referral platforms like Unite Us for maternity navigation, there is a critical absence of a shared, cross-organizational analytics workspace to align hospitals, clinics, and community-based organizations around these rich data sets. 

**Immediate Strategic Actions:**
* **Launch an Employer Intake Portal:** Replace the email-based YouthWorks partner enrollment with a lightweight web form and CRM to capture lost internship slots.
* **Deploy a "Youth Jobs RVA" Aggregator:** Create a single digital destination combining YouthWorks opportunities with other local listings before the March 31 application deadline.
* **Establish a Shared MCH Analytics Workspace:** Embed VDH’s maternal health dashboards into a shared BI environment (e.g., Power BI/Tableau) for RHHD and local health systems to eliminate siloed analysis.
* **Target Interventions using HOI/COI:** Leverage the proven correlation between the Health Opportunity Index/Child Opportunity Index and infant mortality to direct prenatal and doula resources to high-risk census tracts.

## Scope and Decision Goals
This report inventories the current digital touchpoints for Richmond youth employment and maternal health data access as of March 2026. It isolates critical gaps in the user experience for teens, employers, and health analysts, and lays out a 90-day action plan to close them. The goal is to transition fragmented, manual processes into streamlined digital workflows that increase youth job placements and improve maternal health outcomes through targeted data utilization.

## Youth Employment: Current Digital Touchpoints
Teens seeking employment in Richmond have access to online applications, but the ecosystem lacks a unified discovery platform, and employers face significant digital friction when trying to participate.

| Program / Platform | Target Audience | Digital Asset | Apply Online? | Employer Portal? | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **YouthWorks RVA (YES)** | Ages 14–24 | rva.gov web form | Yes | No (Email only) | Goal of 750 placements; deadline March 31, 2026 [1] [2]. |
| **NextUp RVA** | Ages 11–19 | nextuprva.org | N/A (Program discovery) | No | Focuses on out-of-school time (OST) programs, not direct employment [3] [4]. |
| **Richmond Public Schools** | High School Students | MajorClarity (Unconfirmed) | Unknown | Unknown | MajorClarity is widely used in VA, but RPS public deployment requires validation [5] [6]. |

**Key Takeaway:** While the city has successfully digitized the youth-facing application for its flagship summer program, the lack of an employer portal and a centralized job aggregator limits the program's scale and visibility.

### YouthWorks RVA Online Application
The FY26 Youth Works RVA application, managed by the Youth Engagement Services (YES) unit, is currently live on the city's website [1]. The program aims to serve 750 Richmond youth through paid work experiences, with the application window closing on March 31, 2026 [2]. The digital touchpoint is a standard web form hosted on rva.gov [7] [2].

### Analog Employer Partner Process
Despite the digital application for youth, the employer partner enrollment process is highly manual. Employers interested in hosting interns are directed to call or email the Program Coordinator [1]. A recent Facebook post by the City of Richmond announced an extension of the community partner application to February 20, again directing interested mentors to an email address [8]. This lack of a self-serve digital portal creates friction that likely depresses employer participation.

### The Missing Youth Jobs Aggregator
No single, citywide digital hub for youth employment surfaced in the research. NextUp RVA provides a robust directory for afterschool and summer programs, but it functions as an OST intermediary rather than a job board [3] [9]. Teens are left to navigate a fragmented digital landscape, relying on word-of-mouth or navigating individual city and corporate websites to find opportunities.

## Youth UX Assessment and Immediate Fixes
*(Inference: User Digital Experience)* The current YouthWorks application relies on a fixed-deadline web form. Without visible SMS integration, save-and-resume functionality, or mobile-first optimization, the application funnel likely suffers from high drop-off rates, particularly among younger teens relying on smartphones.

| Failure Point | Evidence / Inference | 30-Day Fix |
| :--- | :--- | :--- |
| **Application Drop-off** | Long web forms on mobile devices typically see high abandonment. | Implement save-and-resume functionality and progress bars. |
| **Deadline Awareness** | Fixed March 31 deadline requires proactive tracking by youth [2]. | Add SMS nudge campaigns for incomplete applications. |
| **Language Barriers** | Form appears primarily in English. | Deploy Spanish/English toggles and microcopy tooltips. |
| **Employer Friction** | Email-only intake requires manual follow-up [1] [8]. | Launch a 2-page web intake form linked to a basic CRM. |

**Key Takeaway:** Small, fast UX additions—such as SMS reminders, mobile-optimized microcopy, and bilingual support—can significantly lift completion rates among the 14–17-year-old cohort before the summer cycle closes.

## Maternal Health Data Tools: Statewide Assets Richmond Already Uses
Richmond's maternal health organizations benefit from a highly developed, statewide digital data infrastructure. VDH dashboards serve as the de facto data backbone for local health assessments.

| Data Tool | Owner | Granularity | Last Updated | Typical Local Use |
| :--- | :--- | :--- | :--- | :--- |
| **MCH Indicators Dashboard** | VDH | City/County | 2023 data (Launched Apr 2025) | Tracking preterm birth, low birthweight, infant mortality [10] [11]. |
| **Maternal Mortality Dashboard** | VDH | Statewide/Regional | Oct 2025 | Monitoring pregnancy-associated deaths [12] [13]. |
| **PRAMS Dashboards** | VDH | RCHD Oversample | March 2025 | Assessing pregnancy intention, breastfeeding, prenatal care [14]. |
| **Health Opportunity Index (HOI)** | VDH OHE | Census Tract | 2025 | Mapping social determinants of health against life expectancy [15] [16]. |
| **VA Community Health Portal** | CHS / VDH | Locality | Live | Baseline data for hospital Community Health Needs Assessments [17] [18]. |

**Key Takeaway:** VDH provides comprehensive, recently upgraded dashboards (April 2025) that break down maternal and infant health data by region, race, and ethnicity [12] [11]. These tools are already heavily relied upon by local institutions.

### Evidence of Local Adoption
Local health systems actively use these digital touchpoints. Both the VCU Health Community Memorial Hospital and the Children's Hospital of Richmond (CHoR) 2024/2025 Community Health Needs Assessments (CHNAs) explicitly cite the Virginia Community Health Improvement Data Portal and VDH data to profile maternal and infant health disparities [17] [18]. 

## Local Operations: Referrals and Collaboration
While the data exists, the digital tools used for daily operations and cross-organizational collaboration show a mix of success and inadequacy.

### Operational Referral Tech is Working
The Richmond and Henrico Health Districts (RHHD) successfully utilize digital referral platforms for on-the-ground operations. According to their 2024 Annual Report, the Maternity Navigation team uses the "Unite Us" platform to connect expectant parents to resources like car seat programs and Medicaid application assistance [19]. 

### Gap: No Shared Analytics Workspace
While RHHD notes collaboration with internal data teams to analyze birth outcomes [19], there is no evidence of a shared, cross-organizational digital workspace. Hospitals, FQHCs, and the health district are likely pulling from the same VDH dashboards [17] [18] but analyzing the data in silos, leading to duplicated efforts and disjointed community interventions.

## Targeting Equity: Where to Focus
Digital indices provide a clear roadmap for place-based targeting in Richmond, allowing organizations to move from broad dashboards to specific neighborhood interventions.

### The Power of HOI and COI
The Virginia Department of Health's Health Opportunity Index (HOI) demonstrates a strong, positive correlation with life expectancy, explaining 76 percent of the variation at the census tract level [16]. Furthermore, a 2026 study by the American Academy of Pediatrics utilizing the Child Opportunity Index (COI) 3.0 in Virginia found that a 1-Standard Deviation increase in community opportunity is associated with a 20% lower risk of infant mortality, as well as lower odds of preterm and low birthweight births [20]. 

By overlaying HOI/COI data with VDH's MCH indicators, Richmond health organizations can precisely target census tracts for doula supports, transportation assistance, and early prenatal outreach.

## Gaps in Digital Coverage
The investigation reveals three primary gaps where digital delivery is currently absent or inadequate.

| Identified Gap | Evidence | Risk if Unaddressed | 30-Day Fix |
| :--- | :--- | :--- | :--- |
| **Missing Employer Portal** | Partner enrollment relies on email (erika.love@rva.gov) [1]. | Loss of potential internship slots due to high friction. | Launch a web-based employer intake form and simple CRM. |
| **No Youth Jobs Aggregator** | Searches yield no centralized hub; NextUp focuses on OST [3]. | Low program awareness and fragmented youth experience. | Publish a "Youth Jobs RVA" landing page aggregating opportunities. |
| **Siloed MCH Analytics** | CHNAs show parallel data pulls [17] [18]; no shared BI tool visible. | Duplicated analyses and misaligned community interventions. | Stand up a shared Power BI/Tableau workspace embedding VDH data. |

**Key Takeaway:** The most critical digital holes are the lack of an employer onboarding portal, the absence of a youth jobs aggregator, and the need for a shared maternal analytics workspace.

## 90-Day Action Plan
To close these digital gaps rapidly, the following low-lift, high-impact actions should be executed over the next 90 days:

### 1. Launch Employer Intake and CRM
Within two weeks, the YES team must stand up a 2-page digital employer intake form (capturing interest and slot details) connected to a lightweight CRM (e.g., Airtable). This should be paired with a 3-week digital campaign targeting local businesses via LinkedIn and city newsletters, with a goal of securing 100 net-new internship slots.

### 2. Optimize the YouthWorks Application Funnel
Before the March 31 deadline, instrument the rva.gov application with funnel analytics to identify drop-off points. Add SMS reminder capabilities and mobile-optimized microcopy (in English and Spanish) to guide applicants. The target is a 15% increase in application completion rates among 14–17-year-olds.

### 3. Publish a "Youth Jobs RVA" Aggregator
Launch a lightweight aggregator page on the city's website that pulls YouthWorks internships alongside partner listings. Pilot this with 10 major employers and promote it heavily through school counselors and social channels to drive 500 unique youth visits.

### 4. Stand Up a Shared MCH Dashboard Workspace
Designate the VDH dashboards as the "single source of truth." Create a shared BI workspace that embeds VDH MCH indicators, PRAMS Richmond cuts, and local Unite Us referral KPIs. Host a 60-minute training session to onboard 25 users from local hospitals, FQHCs, and CBOs.

## Governance, Data Sharing, and DUAs
To enable deeper, localized use of maternal health data without violating privacy, a structured governance approach is required.

Because public dashboards often suppress locality-level infant and maternal indicators due to small sample sizes [18], RHHD and its partners should file a Data Use Agreement (DUA) with VDH. This will allow access to de-identified microdata via REDCap requests [10] [14]. Additionally, partners should convene a quarterly Richmond MCH Data Roundtable to lock in shared definitions (e.g., late/no prenatal care) and review a unified KPI scorecard.

## KPIs and Impact Tracking
Success will be measured by tracking placement capacity, youth conversion, and maternal navigation efficiency.

| Metric | Baseline | 90-Day Target | Data Source |
| :--- | :--- | :--- | :--- |
| **Employer Slots Committed** | Unknown (Analog) | +100 | New Employer CRM |
| **YouthWorks Completion Rate (Ages 14-17)** | TBD (Needs instrumentation) | +15% | Web Form Analytics |
| **Aggregator Unique Youth Users** | 0 | 500 | Web Analytics |
| **Time-to-Referral (Prenatal to Service)** | Current Unite Us average | -20% | Unite Us Reports |
| **Shared Workspace Active Users** | 0 | 25 | BI Audit Logs |

**Key Takeaway:** Establishing clear baselines through immediate instrumentation will allow the city and health districts to prove the ROI of these digital interventions.

## Risks and Mitigations
Anticipating potential roadblocks ensures the 90-day plan remains viable.

* **Privacy and Data Suppression:** Small-n suppression on public dashboards limits neighborhood-level insights [18]. *Mitigation:* Execute a DUA with VDH for microdata access and aggregate data over 3-year rolling averages to protect privacy while maintaining statistical significance.
* **Staff Bandwidth:** City and health district staff may lack the capacity to build new digital tools. *Mitigation:* Utilize no-code/low-code solutions (Airtable, standard BI embeds) that require minimal IT overhead to deploy.
* **Data Freshness:** Vital statistics often lag by 1-2 years (e.g., 2025 dashboards showing 2023 data) [10]. *Mitigation:* Supplement lagging state data with real-time operational data from the Unite Us referral platform to track immediate community needs.

## Unknowns and Validation Plan
Several assumptions must be validated immediately to de-risk execution.

| Unknown Question | Why It Matters | Validation Step | Timeline |
| :--- | :--- | :--- | :--- |
| **Does RPS use MajorClarity?** | Determines if YouthWorks can integrate directly into school platforms. | 30-min call with RPS CTE leadership. | 1 Week |
| **What is the current YouthWorks drop-off rate?** | Needed to measure the impact of UX improvements. | Add basic analytics to the rva.gov form. | 1 Week |
| **What are the employer slot goals by sector?** | Required for targeted digital recruitment campaigns. | Add sector fields to the new employer intake form. | At Launch |
| **Which partners need dashboard training?** | Ensures the shared BI workspace is actually adopted. | Survey local hospital and CBO data analysts. | 2 Weeks |

**Key Takeaway:** Resolving the status of Richmond Public Schools' career platform (MajorClarity) is the highest priority unknown, as it represents a massive, untapped digital distribution channel for youth jobs.

## References

1. *Youth Engagement Services | Richmond*. https://www.rva.gov/community-wealth-building/youth-engagement-services
2. *Youth Works RVA: Summer 2026 Applications Now Open! | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/news/youth-works-rva-summer-2026/
3. *NextUp - Find Afterschool and Summer Programs in Richmond*. https://nextuprva.org/
4. *Careers and Job Openings - NextUp RVA*. https://nextuprva.org/careers/
5. *Curriculum & Instruction  - Richmond Public Schools*. https://www.rvaschools.net/office-sandbox-pages/academics/curriculum-instruction
6. *MajorClarity by Edmentum | Career & College Readiness Solutions*. https://majorclarity.com/
7. *Youth Works RVA Application 26' | Richmond*. https://www.rva.gov/form/youth-works-rva-application-26
8. *The community partner application for YouthWorks RVA ...*. https://www.facebook.com/RVAGov/posts/update-the-community-partner-application-for-youthworks-rva-summer-program-has-b/1456432953156183/
9. *About - NextUp RVA*. https://nextuprva.org/about/
10. *Maternal & Child Health Indicators - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/mch-indicators/
11. *Virginia launches new dashboards to track maternal deaths, improve pregnancy outcomes • Virginia Mercury*. https://virginiamercury.com/2025/04/18/virginia-launches-new-dashboards-to-track-maternal-deaths-improve-pregnancy-outcomes/
12. *Governor Youngkin Announces New Virginia Department of Health Maternal and Child Health Data Dashboards - Virginia Department of Health*. https://www.vdh.virginia.gov/blog/2025/04/17/governor-youngkin-announces-new-virginia-department-of-health-maternal-and-child-health-data-dashboards/
13. *Maternal Mortality - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/maternal-mortality/
14. *Data Dashboards - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/
15. *Health Opportunity Index - Virginia - Dataset - Virginia Open Data Portal*. https://data.virginia.gov/dataset/health-opportunity-index
16. *Virginia Department of Health, Office of Health Equity*. https://puttinglocaldatatowork.urban.org/grantee/virginia-department-health-office-health-equity.html
17. *Community Health Needs Assessment Report 2024*. https://www.vcuhealth.org/media/vcuhealth/media/files/2024CMHCommunityHealthNeedsAssessment.pdf
18. *Community Health Needs Assessment Study Report*. https://www.chrichmond.org/media/chrichmond/content-assets/media/media/file/childrens-hospital-community-health-needs-assessment-2025.pdf
19. *Annual Report Working together for a healthier community*. https://www.vdh.virginia.gov/content/uploads/sites/119/2025/03/2024-Annual-Report-RHHD.pdf
20. *Virginia Locality and Perinatal Health: An Ecologic Study Using the Child Opportunity Index 3.0 | Pediatrics Open Science | American Academy of Pediatrics*. https://publications.aap.org/pediatricsopenscience/article/2/1/1/205926/Virginia-Locality-and-Perinatal-Health-An-Ecologic