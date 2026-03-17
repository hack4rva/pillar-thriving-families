# Thriving Families, Faster: Closing Richmond’s First-Job and Maternal Data Gaps in 48 Hours

## Executive Summary — Two targeted MVPs can unlock access now while preparing Richmond for deeper coordination

The highest-leverage 48-hour wins for the Richmond Civic Hackathon are (1) a unified first-job finder and compliance wizard for 14–18-year-olds, and (2) a Richmond City Health District (RCHD) maternal data joiner that harmonizes PRAMS, Vital Stats, and CDC WONDER. Transportation is a make-or-break lever for teen jobs, and with GRTC’s zero-fare funding facing a potential cliff as early as summer 2025 [1], transit-aware job matching is critical. Meanwhile, Richmond has a rare advantage for maternal insights because the Virginia Pregnancy Risk Assessment Monitoring System (PRAMS) oversamples the RCHD [2]. However, local outcome data remains scattered across multiple portals. By focusing on orchestration over invention, these two MVPs can immediately close discovery and data gaps for Richmond families and analysts.

## Context and Objectives — Why these two problems, why now

Transit uncertainty, fragmented opportunity discovery, and siloed maternal data slow outcomes for Richmond families. High-touch internships serve a narrow slice of high-achieving students, leaving many teens facing closed doors or missed application windows. Simultaneously, maternal health stakeholders struggle to combine behavioral survey data with vital statistics because the data lives in different formats across state and federal portals. Light-weight orchestration—stitching together existing programs and datasets—can move families forward quickly without requiring massive new funding or multi-year policy changes.

## Youth Employment Pathways — What exists and where teens get stuck

Richmond has strong but narrow youth employment programs. Discovery and compliance friction block many teens before they ever receive their first paycheck.

### Richmond Program Landscape: PFF, RPS Hub, and ecosystem entry points

Partnership for the Future (PFF) delivers intensive, paid, multi-summer internships with transportation support, but it focuses heavily on high-achievers. Students must maintain a 3.0 GPA and participate in a 7-week, Monday through Thursday, 9:00 AM to 5:00 PM summer model [3] [4]. Sponsors pay students at least minimum wage plus a $1,500 fee that covers transportation and up to a $2,000 scholarship match [5] [3]. Meanwhile, the Richmond Public Schools (RPS) Student Opportunities Hub surfaces opportunities with tight deadlines, such as a PFF deadline extended to March 17 [6]. 

| Program/Portal | Target ages/eligibility | Schedule/Duration | Compensation | Transportation support | Application window |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Partnership for the Future (PFF)** | High school freshmen; 3.0 GPA required | 7 weeks (Summer); Mon-Thu 9am-5pm | Min wage + up to $2,000 college match | Yes, fully coordinated | Spring (e.g., March 17 deadline) |
| **RPS Student Opportunities Hub** | RPS Students | Varies by posted program | Varies | Varies | Rolling/Deadline-driven |

*Takeaway: Existing high-quality programs are highly structured and competitive, leaving a gap for a broader, lower-barrier entry-level job discovery tool.*

### Transportation Dependency and Risk: Zero-fare today, uncertain tomorrow

Fareless transit expands job access, but a funding sunset would reintroduce cost barriers. GRTC's zero-fare service is currently supported by grants, and the Transit Access Partnership (TAP) is actively seeking tax-deductible donations to keep it running [7] [8] [9]. Reporting indicates that the one-time grant and corporate funds allowing free rides could expire by summer 2025 [1]. 

### Discovery Friction: Deadlines and disjointed channels

Teens miss windows due to scattered postings and inconsistent eligibility clarity. The RPS Hub posts dated deadline alerts [6], while programs like PFF run their own separate intake and application sites [5]. No single, teens-first directory currently aggregates these opportunities with clear filters for age and legal working hours.

### Compliance and Documents: What teens and employers need to know

Legal and document steps are not packaged in a single, authoritative place for families. This research pass could not verify a definitive, easily discoverable 2026 Virginia Department of Labor and Industry (DOLI) minors' work-permit page or process checklist. This implies a massive discoverability gap for teens trying to gather their I-9 documents, SSNs, and state permits.

## Maternal Health Data Coordination — From scattered sources to a Richmond-first view

Richmond has unusually strong local maternal survey data via PRAMS oversampling; the primary blocker is harmonization across disparate portals.

### What's Publicly Available Now

Multiple official sources cover overlapping indicators across different geographies and years. VDH HealthStats provides infant deaths by city/county from 2006 to 2020 [10]. CDC WONDER provides infant death counts and rates by county of mother's residence with rich stratifiers (race, age, birth weight) dating back to 1995 [11]. 

| Source | Geography | Years | Key indicators/fields | Access method |
| :--- | :--- | :--- | :--- | :--- |
| **VDH PRAMS Dashboards** | State, RCHD, BRHD | Updated Mar 2025 | Pregnancy intention, breastfeeding | Online Dashboards |
| **VDH HealthStats** | City/County | 2006-2020 | Infant deaths by race | Statistical Tables |
| **CDC WONDER** | County of residence | 1995-Present | Infant deaths, birth weight, maternal demographics | Online Database |
| **Virginia Open Data** | State/Locality | Varies | Low birthweight live births | Data Portal |

*Takeaway: Analysts currently have to manually pull and normalize data from at least four different state and federal portals to build a complete picture of Richmond's maternal health.*

### Granularity and Equity: Small-area and disparity views

Small-area estimates and locality aggregations exist, and careful joins can surface disparities. A 2026 AAP study aggregated infant mortality, preterm birth, and low birthweight by Virginia locality for 2020–2022 using the Child Opportunity Index [12]. Furthermore, PRAMS offers a Small Area Estimates Map [13] and explicitly stratifies data for the Richmond City Health District [2].

### Fragmentation Risks and Data Hygiene

Different portals and suppression rules can lead to inconsistent trends if not normalized. VDH HealthStats and CDC WONDER use different reporting years and fields [10] [11], while PRAMS focuses on behaviors and experiences rather than raw vital outcomes [2].

## MVP Proposals — What can be built in 48 hours with clear value

Two MVPs, each scoped to orchestration and clarity, can launch quickly and scale.

### MVP 1: Richmond Teen First-Job Finder + Compliance Wizard

**What it does:** A unified directory of teen-suitable roles and programs with filters, deadline alerts, and transit-aware scheduling. It includes a dynamic document checklist (I-9 IDs, SSN, DOLI links).
**Evidence basis:** PFF's strict schedule and eligibility [3] [4]; RPS Hub's deadline-driven posts [6]; GRTC's zero-fare funding risk [1].
**Success metrics:** Sign-ups, alert click-throughs, applications started, and trips planned.
**Risks & Mitigations:** Legal advice boundaries (mitigated by linking directly to official guidance) and transit funding volatility (mitigated by adding a "fare contingency" toggle).

### MVP 2: RCHD Maternal Equity Dashboard (PRAMS + Vital Stats + CDC WONDER)

**What it does:** Harmonizes PRAMS indicators (e.g., pregnancy intention, breastfeeding initiation) [2] with infant mortality and low birthweight rates by Richmond City [10] [11]. 
**Evidence basis:** PRAMS RCHD oversampling [2]; VDH HealthStats locality tables [10]; CDC WONDER county-level series [11].
**Success metrics:** Datasets joined, indicators published with metadata, and reduced time-to-answer for key equity questions.
**Risks & Mitigations:** Small-number suppression (mitigated by documenting suppression rules and aggregating to rolling 3-year windows).

### MVP 3 (Optional/Stretch): Ecosystem Partnership Hooks

**What it does:** In-app CTAs and partner pages to "Become a PFF host" and "Support zero-fare transit (TAP)."
**Why:** Sustainability is a critical constraint. PFF relies on $1,500 sponsor fees [3], and GRTC relies on TAP donations [7]. The MVP should strengthen ecosystem capacity.

## Evidence Deep Dives — Source-backed details for credibility

Every claim links back to an official page for auditability. 
* **PFF Program Specifics:** The program runs for 7 weeks, Monday through Thursday, 9:00 AM to 5:00 PM [3] [4]. Students must maintain a 3.0 GPA [4]. Sponsors pay a $1,500 fee, and students receive up to a $2,000 college match [5] [3]. Transportation is guaranteed [3].
* **RPS Opportunity Cadence:** Deadlines are tight and posted on the Student Opportunities Hub (e.g., March 17 extension for PFF) [6].
* **GRTC Fareless Status:** Currently grant-supported, but funding could run out in summer 2025 [1]. TAP accepts tax-deductible donations to support the service [7] [8].
* **PRAMS Scope:** Represents over 81% of U.S. births, oversamples RCHD, and dashboards were updated March 13, 2025 [2].
* **Locality-Level Outcomes:** Available via VDH HealthStats (2006-2020) [10] and CDC WONDER (since 1995) [11].

## Gaps, Unknowns, and "But What About...?" — What we can't verify yet and how to proceed

We will not guess on law or claims; we will capture unknowns and instrument the MVP to be source-driven.
**Known unknowns from this pass:**
* Current 2026 Virginia minors' work permit requirements, hour restrictions, and prohibited occupations (no definitive DOLI source found in this pass).
* Active Richmond WIOA Youth providers and application platforms.
* Comprehensive inventory of Richmond teen programs beyond PFF.
* Richmond-specific maternal disparities beyond PRAMS dashboards (e.g., race/ethnicity cross-tabs within RCHD).

**Actions:** Queue targeted lookups, add a "Report an error/link" feature, and prefer linking to official pages over paraphrasing.

## Implementation Plan — Weekend build roadmap with roles

**Day 1:** Focus on data adapters (PRAMS, HealthStats, CDC WONDER) and scrapers (RPS Hub, PFF pages). Establish the database schema, integrate transit routing APIs, and map out the compliance links.
**Day 2:** Build out the UX flows for the teen job finder and the maternal dashboard. Implement SMS/email alerts, partner CTAs, and conduct QA to ensure all source citations and metadata are accurate.

## Measurement and Learning Plan — How we'll know it worked

Success will be measured by tracking applications started before deadlines, the number of compliance checklists completed by teens, and the reduction in time-to-answer for maternal health data queries by local analysts.

## Appendices — Tables and Source Notes

**Top 3 Open Research Questions:**
1. What is the definitive 2026 Virginia DOLI position on youth employment certificates, hour limits, and prohibited occupations?
2. Who are the current WIOA Youth providers for the Virginia Career Works Capital Region?
3. Which Richmond-specific maternal disparities are available at the RCHD level via PRAMS requestable data, and what suppression rules apply?

**Source Notes:**
* Transit Access Partnership (GRTC): [7] [8] [9]
* Virginia Mercury (Apr 2, 2025): [1]
* Partnership for the Future: [5] [3] [4]
* Richmond Public Schools: [6]
* VDH PRAMS: [2] [13]
* VDH HealthStats: [10]
* CDC WONDER: [11]
* AAP Pediatrics Open Science (2026): [12]

## References

1. *Richmond’s zero-fare bus funding could run out soon • Virginia Mercury*. https://virginiamercury.com/2025/04/02/richmonds-zero-fare-bus-funding-could-run-out-soon/
2. *Data Dashboards - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/
3. *Host an Intern | Partnership for the Future*. https://partnershipforthefuture.org/host-an-intern/
4. *Program Details | Partnership for the Future*. https://www.partnershipforthefuture.org/how-we-work/program-details/
5. *Become a Student | Partnership for the Future*. https://www.partnershipforthefuture.org/become-a-student/
6. *Partnership for the Future. Apply Today! | Details Page*. https://www.rvaschools.net/students-families/student-opportunities-hub/details-page/~board/posts/post/partnership-for-the-future-deadline-extended-until-march-17-1771270643849
7. *Transit Access Partnership -GRTC*. https://www.ridegrtc.com/community/transit-access-partnership-2/
8. *Testing - TAP – Testing*. https://www.ridegrtc.com/tap-testing/
9. *Transit Access Partnership (TAP) - Richmond*. https://www.ridegrtc.com/community/transit-access-partnership/
10. *Statistical Reports and Tables*. https://apps.vdh.virginia.gov/HealthStats/stats.htm
11. *CDC WONDER: Mortality - Infant Deaths - Dataset - Virginia Open Data Portal*. https://data.virginia.gov/dataset/cdc-wonder-mortality-infant-deaths
12. *An Ecologic Study Using the Child Opportunity Index 3.0*. https://publications.aap.org/pediatricsopenscience/article/2/1/1/205926/Virginia-Locality-and-Perinatal-Health-An-Ecologic
13. *Small Area Estimates Map - PRAMS*. https://www.vdh.virginia.gov/prams/data-dashboards/small-area-estimates-map/