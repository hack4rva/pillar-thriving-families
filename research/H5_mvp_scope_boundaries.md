> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.


# Thriving Families MVP Boundaries: Build-Now Decisions That Ship

## Executive Summary
Success at the Hack for RVA event (March 27–29, 2026) requires teams to make ruthless scope decisions to deliver functional Minimum Viable Products (MVPs) within 48 hours [1] [2]. For the "Thriving Families" pillar, teams must avoid rebuilding existing infrastructure. Virginia already mandates that youth secure job offers before obtaining work permits [3], GRTC provides Zero Fare transit [4], and the Virginia Department of Health (VDH) maintains comprehensive maternal health dashboards [5]. The winning strategy is to curate, connect, and contextualize these existing resources rather than engineering net-new data pipelines or compliance-heavy account systems.

## Context and Constraints
The City of Richmond's first-ever civic hackathon challenges participants to build "community-centered solutions" aligned with the Mayoral Action Plan (MAP), including the "Thriving families" pillar [1]. Teams have exactly 48 hours to design, build, and pitch their solutions [1]. 

Given this extreme time constraint, teams must design for immediate public impact. The primary users are Richmond teens (ages 14–24) seeking employment and public audiences seeking clarity on maternal health outcomes. Non-goals for this MVP include building new data infrastructure, implementing heavy authentication/compliance systems for minors, or creating employer Customer Relationship Management (CRM) tools.

## Local Ecosystem Facts That Should Drive Scope
Leveraging existing local infrastructure is critical for MVP feasibility. Teams should build on top of these established realities:

* **Transit is Free:** GRTC has operated Zero Fare service since 2020 and is "100% committed" to maintaining it through the fiscal year 2026 budget, absorbing a $6.8 million annual cost [4] [6]. Even if reversed, reintroducing fares would take up to two years [4].
* **Youth Infrastructure Exists:** The City's Youth Engagement Services (YES) already operates the Youth Works RVA program for ages 14–24, offering specific tracks like Work-Based Learning and Founders Mark [7]. Additionally, Virginia Career Works (VCW) serves WIOA-eligible youth ages 17–24 who face employment barriers [8] [9].
* **Maternal Data is Robust:** VDH updated its Maternal & Child Health dashboards on October 10, 2025 [5]. The data is highly granular, showing 5.8 infant deaths per 1,000 live births, 34.5 maternal deaths per 100,000 live births (2019 to 2023), and revealing that 40% of pregnancy-associated deaths (2018 to 2022) were due to accidental overdose [5].

## Decision Inventory — Youth Employment
To unlock job offers quickly, teams must prioritize discovery and guidance over administrative overhead. 

| Decision Area | Option A | Option B | Recommended Choice | Rationale |
| :--- | :--- | :--- | :--- | :--- |
| **Core Function** | Program Listings | Document Prep Only | **Program Listings** | Virginia law requires 14 and 15-year-olds to have a "firm offer of employment" *before* applying for an employment certificate [3]. Document prep is useless without a job offer. |
| **Transit Integration** | Transit Directions | Locations Only | **Transit Directions** | With GRTC operating Zero Fare [4], cost is removed, but navigation remains a barrier. Use lightweight deep links to map apps rather than building custom routing. |
| **User State** | User Accounts | Saved State (Local) | **Saved State (Local)** | Serving minors (14-15) triggers COPPA and parental consent requirements. Local device saves avoid massive compliance overhead in a 48-hour sprint. |
| **Target Audience** | Serve Employers | Only Teens | **Only Teens** | YES already handles employer partner enrollment [7]. Splitting focus dilutes the MVP; serve teens first and link out to YES for employers. |

**Key Takeaway:** Build a tool that helps teens find and secure opportunities first, followed by a lightweight, step-by-step guide on how to use the Virginia Electronic Employment Certificate System once an offer is in hand [3].

## Decision Inventory — Maternal Health
For maternal health, the goal is clarity and translation of existing data, not redundant data plumbing.

| Decision Area | Option A | Option B | Recommended Choice | Rationale |
| :--- | :--- | :--- | :--- | :--- |
| **Data Architecture** | Live Data API | Cached/Curated Data | **Cached/Curated Data** | VDH already provides comprehensive, updated dashboards [5]. Live API integration in 48 hours risks demo failure and adds unnecessary complexity. |
| **Health Scope** | All Richmond Health | Maternal Health Only | **Maternal Health Only** | The MAP pillar specifically targets thriving families [1]. Expanding to all health issues guarantees scope creep and an unfinished MVP. |
| **Output Format** | Downloadable Reports | Dashboard View | **Dashboard View** | VDH already allows users to "download data" directly from their dashboards [5]. A curated dashboard with print-to-PDF styling is sufficient. |
| **Target Audience** | Public Audiences | Researchers Only | **Public Audiences** | The hackathon demands "community-centered solutions" [1]. Researchers already use VDH's raw data; the public needs plain-language translation. |

**Key Takeaway:** Treat VDH as the definitive source of truth. Allocate hackathon hours to UX, plain-language explainers, and local resource wayfinding rather than net-new data engineering.

## Risks and Failure Modes
Choosing the wrong scope boundaries introduces severe risks that can derail a hackathon project:

* **Choosing Document-Prep Only:** This contradicts the legal sequence of youth employment in Virginia, leaving teens with prepped documents but no legal way to submit them without an employer [3].
* **Building Live Integrations:** Attempting to build live data pipelines in 48 hours frequently results in unstable data, broken demos, and wasted time that should have been spent on user experience.
* **Implementing User Accounts:** Storing Personally Identifiable Information (PII) for minors introduces severe security and compliance risks (COPPA) that cannot be responsibly managed during a weekend hackathon.
* **Serving Employers:** Attempting a two-sided marketplace splits the team's focus, resulting in a shallow, unusable experience for both teens and employers.
* **Targeting Researchers:** A highly technical, researcher-focused tool limits public value and misaligns with the Mayor's goal of solutions grounded in lived experience [1].

## Implementation Blueprint
To ship a successful MVP in 48 hours, teams should follow this structured approach:

* **Day 1 (Discovery & Curation):** Curate content from YES and VCW [7] [8]. Capture Richmond-specific maternal health snapshots from VDH [5]. Finalize UX wireframes.
* **Day 2 (Build & Connect):** Build the public dashboard and youth program finder. Implement deep links for transit directions and VDH data downloads. Implement local-storage saved states.
* **QA & Polish:** Conduct accessibility checks, ensure mobile responsiveness, and verify that all external links (especially to the Virginia Electronic Employment Certificate System) function correctly [3].

## Measurement and Validation
Teams must prove their MVP's usefulness quickly during the pitch. Validate the tool with 3–5 end users per domain. For the youth tool, track the percentage of users who successfully click through to the YES application [7] or launch map directions. For the maternal health tool, measure the time-to-understand for key facts (e.g., the impact of accidental overdoses [5]) and track clicks to local support resources.

## Compliance, Data Governance, and Content Stewardship
Strict adherence to data governance is required. The MVP must feature no account creation and no PII storage; all saved states must remain local to the user's device. For maternal health data, teams must explicitly label VDH as the source and include "last-updated" notices (e.g., October 10, 2025) [5]. 

## Inferences and Assumptions
* **Inference:** Deep linking to existing map applications (Google Maps, Apple Maps) satisfies the transit routing requirement better than a custom-built routing engine, especially given GRTC's Zero Fare policy [4].
* **Inference:** Building a public-first maternal health tool aligns better with the hackathon's judging criteria for "community-centered solutions" [1] than a researcher-focused tool.
* **Assumption:** The City of Richmond and VDH prefer that hackathon teams route users to their official intake forms (like the Youth Works RVA application [7]) rather than creating shadow databases.

## Unknowns and Fast-Track Answers
Specific technical details are currently unavailable. Teams should resolve these within the first three hours of the hackathon:
* **VDH Dashboard Constraints:** Are there specific API or iFrame constraints for embedding VDH dashboard elements directly? (Fast-track: Ping a VDH data contact or default to static snapshots with deep links).
* **OCWB Data Feeds:** Does the Office of Community Wealth Building (OCWB) have a JSON/CSV feed of youth programs, or must it be scraped/manually curated from the YES website? [7] (Fast-track: Ask City mentors immediately; if no, manually curate top 10 programs).

## Post-Hack Roadmap
Once the MVP is validated and governance frameworks are established post-hackathon, the tools can be expanded. For youth employment, a lightweight employer interest form could be added and securely routed to YES [7]. For maternal health, automated nightly data refreshes and neighborhood-level overlays could be integrated once a permanent hosting and maintenance owner is identified.

## References

1. *City of Richmond to Partner in City’s First-Ever Civic Hack-a-thon | Richmond*. https://www.rva.gov/press-releases-and-announcements/news/city-richmond-partner-citys-first-ever-civic-hack-thon
2. *Hack for RVA 2026 | Building a Thriving Economy*. https://rvahacks.org/
3. *DOLI – Virginia Department of Labor and Industry - Youth Employment*. https://doli.virginia.gov/programs/labor-law/youth-employment/
4. *Despite recent headlines, GRTC plans to continue zero-fare policy through 2026 budget*. https://www.richmonder.org/despite-recent-headlines-grtc-plans-to-continue-zero-fare-policy-through-2026-budget/
5. *Maternal & Child Health - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/
6. *FISCAL YEAR 2026 BUDGET DOCUMENT - Richmond*. https://www.ridegrtc.com/wp-content/uploads/2025/07/Fiscal-Year-2026-Budget-Book.pdf
7. *Youth Engagement Services | Richmond*. https://www.rva.gov/community-wealth-building/youth-engagement-services
8. *Page not found – Virginia Career Works, Capital Region*. https://vcwcapital.com/about/public-documents/reports/
9. *Staff Resources Content – Virginia Career Works, Capital Region*. https://vcwcapital.com/staff-resources/