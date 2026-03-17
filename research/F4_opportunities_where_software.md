# Software That Actually Moves the Needle: A hard-nosed map of where code helps (and doesn’t) in youth jobs and maternal health data

## Executive Summary

To drive meaningful outcomes in the Thriving Families initiative, we must separate technological solutionism from high-leverage software applications. An analysis of youth employment and maternal health data reveals that software’s comparative advantage lies in orchestration, standardization, and measurement—not in substituting scarce human or physical capital. 

**Key Strategic Insights:**
* **Strong employer ties, not apps, drive youth earnings gains:** The Year Up randomized controlled trial (RCT) demonstrated large, sustained earnings impacts (nearly $2,000 per quarter initially) driven by a model where employers pay 59% of internship costs [1]. Software should be relegated to CRM and placement operations, while primary investments must flow toward human business development and paid work-based learning.
* **Navigation and aggregation are real gaps software can close:** Fragmented information depresses program take-up. A unified "youth work navigator" that aggregates local Summer Youth Employment Programs (SYEPs), deadlines, and eligibility can solve the exact problem researchers identify: the lack of a system to help young people navigate programs and move up [2].
* **Transportation remains a binding constraint software cannot code away:** Research shows a negative relationship between distance from transit access points and employment [3]. Software-only maps without tangible transit funding can be counterproductive by exposing options youths cannot physically reach.
* **Maternal health data standardization is a high-yield software zone:** Mature, standards-aligned tools exist. Adopting DHIS2 toolkits out-of-the-box for Reproductive, Maternal, Newborn, Child, and Adolescent Health (RMNCAH) provides immediate value [4]. However, data sharing stalls on incentives and trust; with health data valued at $300–$450 billion annually, organizations are disincentivized to share without policy mandates [5].
* **Clinical outcomes require bundles and practice change, not just dashboards:** Implementation of obstetric hemorrhage bundles reduced severe maternal morbidity (SMM) by 20.8% in California collaboratives [6] and by 55% among hemorrhage cases in Michigan [7]. Software is merely an enabler here (e.g., tracking quantitative blood loss); the real work requires funding carts, supplies, and team drills.
* **Weekend hackathons are poor vehicles for systemic fixes:** Studies consistently find that short-term civic hackathons prize technological solutionism over reinvestment into existing systems, often flattening complex social issues and failing to produce sustained change [8] [9].

## Objective and Scope

This report pinpoints precisely where software creates net-positive impact within two core domains of the Thriving Families initiative: youth employment and maternal health data. By mapping software helpfulness against policy, funding, and relationship constraints, this analysis provides concrete actions for resource allocation. We aim to identify where software can make a meaningful difference versus where the problem is primarily one of systemic barriers that code cannot fix.

## Decision Matrix: Where Software Helps vs. Doesn’t

The following matrix evaluates problem dimensions against software helpfulness, providing evidence-based rationales and highlighting necessary policy or funding prerequisites.

| Domain | Problem Dimension | Software Helpfulness | Rationale & Prerequisites |
| :--- | :--- | :--- | :--- |
| **Youth Employment** | Navigation & Info Aggregation | **High** | Fragmented SYEPs depress take-up. Software excels at aggregating deadlines, eligibility, and applications [10] [2]. |
| **Youth Employment** | Preparation Guidance | **Medium** | Bots can schedule and remind, but human coaching drives persistence. Enhanced academic coaching increased internship progression by 10 points in Year Up [1]. |
| **Youth Employment** | Transportation Access | **Low / Counterproductive** | Distance to transit negatively impacts employment [3]. Apps showing unreachable jobs cause frustration. Requires transit subsidies/shuttles. |
| **Youth Employment** | Adult Mentorship | **Low** | Trust and relationship-building require humans. Software should only be used for matching and caseload management. |
| **Youth Employment** | Employer Relationships | **Low** | Outcomes flow from employer-paid internships [1]. Software acts only as a CRM; human business development is the true driver. |
| **Youth Employment** | Work Permit Enforcement | **Medium** | Work permits enhance investigatory capacity and reduce child labor violations [11]. Digitizing issuance helps, but requires labor agency enforcement. |
| **Maternal Data** | Data Aggregation & Standards | **High** | DHIS2 and WHO provide ready-to-use metadata, core indicators, and dashboards for RMNCAH and EmONC [4]. |
| **Maternal Data** | Shared Access & Incentives | **Low** | Health data is a $300–$450B market [5]. Misaligned financial incentives and lack of trust block sharing [12]. Requires policy mandates. |
| **Maternal Data** | Expert Interpretation | **Medium** | Dashboards visualize data, but WHO guidance emphasizes the need for staff training to interpret indicator values for program management [4] [13]. |
| **Maternal Data** | Funding Decisions | **Low** | Software can highlight gaps, but allocating resources requires political will and governance structures. |
| **Maternal Data** | Clinical Interventions | **Low** | Software tracks quantitative blood loss, but SMM reductions (20.8% in CA, 55% in MI) stem from physical hemorrhage carts, TXA, and staff drills [6] [7]. |

**Inferences:**
* Software's comparative advantage is orchestration and measurement, not substituting scarce human or physical capital. Programs with large effects embed software inside high-trust, resourced delivery systems.
* Aggregation without authority can backfire; unilateral data aggregation erodes participation without shared governance.

**Unknowns:**
* The exact effect size of pure navigation tools on long-term employment retention without paired human coaching.
* The marginal gain of automated Electronic Health Record (EHR) alerts for quantitative blood loss versus manual tracking protocols.

## Youth Employment: High-ROI Software Adjacent to Human/Policy Levers

Software excels in navigation, operations, and compliance support, but the biggest gains in youth employment come from employer partnerships, coaching, and transport funding.

### Unified Youth Work Navigator Can Lift Take-Up Across Fragmented SYEPs
Summer youth employment programs (SYEPs) provide crucial early work experiences, but the landscape is highly fragmented across social service agencies and economic development organizations [10]. MDRC notes that while individual programs serve specific segments, "what’s missing is the system to help young people navigate these programs and move up" [2]. Building a unified, mobile-first "youth work navigator" that aggregates local SYEPs, internships, deadlines, and eligibility requirements is a low-cost, high-yield software intervention.

### Transportation is the Hard Constraint—Pair Apps with Funds and Routes
Transportation availability, reliability, and cost fundamentally shape young people's access to employment [14]. Research demonstrates a clear negative relationship between distance from transit access points and employment [3]. Providing a job-matching app without addressing mobility creates "matching without mobility." Software must be paired with tangible transport solutions, such as attendance-linked transit stipends, employer shuttle coordination, and shift-aware routing.

### Employer Relationships and Paid Internships Drive Outcomes
The Year Up program evaluation demonstrates that strong connections to employment and six-month internships at local employers yield massive results [1]. The program increased quarterly earnings by nearly $2,000 initially, with employers covering 59% of the costs ($22,404 per intern) [1]. This "skin in the game" creates incentives for companies to support interns [1]. Software cannot build these relationships; investments must focus on business development staff, using software merely as a CRM and outcomes reporting tool.

### Coaching and Mentorship: Software Supports, Humans Deliver
While software can handle scheduling and reminders, human relationships drive persistence. In the Year Up evaluation, modest refinements in coaching practices aimed at increasing attention to academic issues generated a 10-point increase in the fraction of participants reaching the internship phase [1]. Programs must budget for stipended mentors and use software strictly for caseload management, risk flagging, and data-informed outreach.

### Compliance and Work Permits: Digitize to Reduce Violations
Work permits enhance the investigatory capacity of federal enforcement agencies by providing basic documentation about youth employment, which research shows reduces child labor violations [11]. Rather than building standalone "youth gig" apps that bypass compliance, software efforts should focus on digitizing permit issuance through e-permit portals with employer APIs and automated age/shift checks in partnership with labor departments.

## Maternal Health Data: Standardize, Share with Incentives, and Drive Practice Change

To improve maternal health, software must adopt existing global standards and be paired with governance, aligned incentives, and clinical quality improvement resourcing.

### Adopt DHIS2 RMNCAH/EmONC/MPDSR Metadata "As-Is"
There is no need to build maternal health dashboards from scratch. The WHO and the HISP Centre have developed DHIS2-based tools for integrating program data into national health information management systems [4]. The DHIS2 toolkits provide out-of-the-box dashboards and core indicators for RMNCAH, Emergency Obstetric and Newborn Care (EmONC), and Maternal and Perinatal Death Surveillance and Response (MPDSR) [4]. Adopting these standards accelerates deployment and ensures global comparability.

### Data Sharing Barriers are Incentive and Trust Problems
Building a comprehensive dataset requires leveraging diverse data, but health data is estimated to be worth $300–$450 billion per year, creating strong incentives against sharing or interoperability [5]. The National Academy of Medicine identifies a misalignment of financial incentives and a profound lack of trust among stakeholders as primary barriers to data sharing [12]. Technology cannot fix this; data sharing must be tied to payments and grants, governed by standardized Data Use Agreements (DUAs), and secured with role-based access and audit trails.

### From Dashboards to Outcomes: Fund Bundles, Supplies, and Drills
Software can track metrics, but clinical practice changes save lives. The implementation of the obstetric hemorrhage patient safety bundle in California reduced severe maternal morbidity (SMM) among women with hemorrhage by 20.8% [6]. In Michigan, bundle implementation reduced the SMM rate among hemorrhage patients by 55% [7]. Software should be used to integrate quantitative blood loss (QBL) tools into EHRs and track bundle compliance, but funding must flow to physical hemorrhage carts, tranexamic acid (TXA), and clinical team training [6] [7].

### Expert Interpretation and Equity: Build Analysis Capacity
Dashboards are useless if staff cannot interpret them. The WHO emphasizes that the use of DHIS2 modules is optimized by training staff to interpret indicator values and understand their implications for program management [4]. Programs must budget for routine data-use meetings, outlier reviews, and capacity-building workshops using WHO facilitator guides [13] [15].

## Hackathon Realism: When Sprints Help and When They Harm

Weekend hackathons are frequently proposed as cheap ways to generate civic tech, but they are poor vehicles for systemic fixes and can actively divert resources from communities.

### Evidence of Performativity and Solutionism
Academic critiques highlight that issue-based hackathons prize "technological solutionism over reinvestment into existing systems" and often fail to make actionable change [8]. They flatten the complexity of societal issues to justify easy technological interventions that fail to address root causes [9]. Furthermore, solutions in the public sector require buy-in from residents and government workers, which cannot be achieved in a weekend sprint [16].

### A Better Model: Staged Pilots with Community Governance
Organizers should only conduct civic hacks if they have sufficient financial resources to create inclusive events that tackle systems [8]. A better approach replaces the "build-a-thon" with 6-to-12-month funded product and policy pilots under community governance. Short events should be restricted to discovery, networking, and onboarding to a fully funded roadmap with explicit adoption agreements.

## Implementation Roadmap: 12-Month Phased Plan

Software must be sequenced with policy and funding moves to de-risk adoption.

### 0–90 Days: MOUs, Standards, and Discovery
* **Youth:** Form an employer coalition to secure internship commitments; establish partnerships with labor agencies for permit digitization; define requirements for the youth work navigator.
* **Maternal:** Adopt DHIS2 metadata standards; convene a multi-stakeholder governance committee; draft standardized Data Use Agreements (DUAs) to address trust barriers.

### 3–6 Months: Build Light, Integrate Deep
* **Youth:** Launch the MVP youth work navigator; pilot the e-permit system; deploy a lightweight CRM for employer business development; initiate a transit stipend pilot.
* **Maternal:** Deploy DHIS2 dashboards at pilot facilities; integrate quantitative blood loss (QBL) prompts into EHRs; begin tracking hemorrhage bundle compliance.

### 6–12 Months: Scale What Works, Sunset What Doesn’t
* **Youth:** Expand the employer network based on CRM data; evaluate earnings and persistence metrics; codify transit subsidies into permanent program budgets.
* **Maternal:** Roll out statewide DHIS2 dashboards; institute monthly data-use review meetings; measure changes in severe maternal morbidity (SMM) rates.

## Risks, Dependencies, and Mitigations

| Risk | Likelihood | Impact | Mitigation Strategy |
| :--- | :--- | :--- | :--- |
| **Data Sharing Stall** | High | High | Tie data sharing requirements directly to funding and grant payments; establish clear DUAs [12]. |
| **"App Without Adoption"** | High | Medium | Require post-event budgets, owners, and adoption partners before greenlighting any software build. |
| **Mentor/Coach Shortage** | Medium | High | Budget for stipended mentors; partner with community-based organizations for human capital. |
| **Matching Without Mobility** | High | High | Braid transit subsidies into programs; do not launch job maps without verified transit access [3]. |

## Measurement and Learning Plan

Success must be defined by behavior and outcomes, not software installs or dashboard views.

**Youth KPIs:**
* Application conversion rates via the navigator.
* Internship placement and 90-day retention rates.
* Long-term earnings (measured via National Directory of New Hires data).
* On-time work permit issuance rates.
* Transit stipend utilization.

**Maternal KPIs:**
* Data completeness and timeliness in DHIS2.
* Hemorrhage bundle adherence rates (e.g., % of facilities with carts, % conducting risk assessments) [7].
* Quantitative blood loss (QBL) utilization rates [7].
* Severe maternal morbidity (SMM) rates, specifically hemorrhage-related [6] [7].

**Experiments to Run:**
* A/B testing of navigator nudges for application completion.
* RCT of attendance-contingent transit stipends.
* Stepped-wedge rollout of EHR QBL alerts.

## Budget and Resourcing Guidance

The majority of funding must be allocated to human and policy levers, keeping software lean and standards-based. 

**Suggested Resource Split:**
* **30–40% Software & Configuration:** DHIS2 deployment, navigator MVP, EHR integrations, and basic CRM licensing.
* **60–70% Human Capital & Physical Resources:** Employer business development staff, stipended coaches/mentors, transit subsidies, hemorrhage carts, clinical training, and governance administration.

## Appendix: Evidence Backbone and Case References

| Source | Key Finding | How it Informs Strategy |
| :--- | :--- | :--- |
| **MDRC Year Up RCT** [1] | 38% higher earnings at 5 years; 59% of costs paid by employers; +10 points in progression from enhanced coaching. | Prioritize employer BD and human coaching over apps; use software as CRM. |
| **Urban Institute / ITF** [3] [14] | Negative relationship between distance to transit and employment. | Pair job matching software with tangible transit subsidies. |
| **EPI** [11] | Work permits enhance investigatory capacity and reduce child labor violations. | Digitize permit workflows rather than bypassing compliance. |
| **WHO / DHIS2** [4] [13] | Standardized RMNCAH, EmONC, and MPDSR dashboards exist; require training for interpretation. | Adopt standards out-of-the-box; fund data-use training. |
| **NAM / PMC** [5] [12] | Health data is a $300–$450B market; financial and trust barriers block sharing. | Mandate sharing via policy/funding; software cannot fix misaligned incentives. |
| **CMQCC / AIM** [6] [7] | Hemorrhage bundles reduced SMM by 20.8% in CA and 55% in MI. | Fund physical carts and drills; use software to track QBL and compliance. |
| **Hackathon Critiques** [8] [9] | Hackathons prize solutionism over reinvestment and flatten complex issues. | Avoid weekend sprints for systemic issues; fund 6-12 month pilots. |

## References

1. *Long-Term Impact and Cost-Benefit Findings for Year Up*. https://acf.gov/sites/default/files/documents/opre/year%20up%20long-term%20impact%20report_apr2022.pdf
2. *Helping Young People Move Up | MDRC*. https://www.mdrc.org/work/publications/helping-young-people-move
3. *Transportation access | Urban Institute | Upward Mobility Initiative*. https://upward-mobility.urban.org/framework/neighborhoods/transportation
4. *Health Data Toolkit - DHIS2*. https://dhis2.org/health-data-toolkit/
5. *
            Determining what matters: data resources for examining maternal health equity - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC11906469/
6. *Hemorrhage | California Maternal Quality Care Collaborative*. https://www.cmqcc.org/toolkits-quality-improvement/hemorrhage
7. *Obstetric Hemorrhage | AIM*. https://saferbirth.org/psbs/obstetric-hemorrhage/
8. *Social Performance and Harm in Civic Hackathons*. https://peer.asee.org/engagement-in-practice-social-performance-and-harm-in-civic-hackathons.pdf
9. *Articulating Social Issues with Open Data: Exploring a Game Jam Approach | Proceedings of the 8th International Conference on Game Jams, Hackathons and Game Creation Events*. https://dl.acm.org/doi/10.1145/3697789.3697798
10. *Recruiting Employer Partners for Summer Youth Employment Programs | MDRC*. https://www.mdrc.org/work/publications/recruiting-employer-partners-summer-youth-employment-programs
11. *New research reveals how work permits reduce child labor violations | Economic Policy Institute*. https://www.epi.org/blog/new-research-reveals-how-work-permits-reduce-child-labor-violations/
12. *EXECUTIVE SUMMARY - Health Data Sharing to Support Better Outcomes - NCBI Bookshelf*. https://www.ncbi.nlm.nih.gov/books/NBK594315/
13. *WHO Toolkit for Routine Health Information Systems Data*. https://www.who.int/data/data-collection-tools/health-service-data/toolkit-for-routine-health-information-system-data/modules
14. *Young People and Transport in the 21st Century | ITF*. https://www.itf-oecd.org/sites/default/files/docs/youth-transport-21st-century.pdf
15. *Analysis and use of health facility data*. https://platform.who.int/docs/default-source/mca-documents/rmncah/who-mca-2023.10.02-eng.pdf?Status=Master&sfvrsn=60aab372_9
16. *Should Cities Use Hackathons to Solve Social Problems? Lessons from America’s Datafest at Harvard - HKS Student Policy Review HKS Student Policy Review*. https://studentreview.hks.harvard.edu/should-cities-use-hackathons-to-solve-social-problems-lessons-from-americas-datafest-at-harvard/