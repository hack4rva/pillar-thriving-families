# Unblocking Richmond's Thriving Families MVP: High-impact data gaps, 48-hour bridges, and risk-proof choices

## Executive Summary
Developing a high-quality MVP for Richmond's Thriving Families pillar requires navigating significant information gaps across youth employment and maternal health data. While some assumed gaps—like plain-language labor laws and ACS table codes—are actually resolved and ready for immediate integration, others pose critical risks. The lack of a centralized youth employer directory and unconfirmed Virginia Department of Health (VDH) data endpoints threaten the MVP's matching quality and analytical accuracy. By implementing targeted 48-hour workarounds—such as bootstrapping a seed directory, leveraging Census API data for baseline metrics, and mapping existing referral networks like Unite Virginia—the development team can safely unblock the MVP while systematically resolving remaining unknowns.

## Gap Inventory with Severity, Bridgeability, and Consequences

Prioritizing these gaps ensures that development efforts focus on unblocking core logic and compliance while transparently labeling pending data.

| Gap | Severity | 48h Bridgeable? | Likely Source/Owner | Consequence if Ignored | Evidence vs. Inference |
| :--- | :--- | :--- | :--- | :--- | :--- |
| No compiled list of Richmond youth employment programs | High | Partial | City/nonprofits/schools | Broken routing, low trust | Evidence: YMCA pages [1] [2]; Inference: city/school anchors |
| No employer directory for youth-friendly businesses | Critical | Partial | Chamber/employer partners | Mis-matches; compliance risk | Inference |
| VA youth labor law plain-language summary not published | Low (Resolved) | Yes | Virginia Rules + DOLI | Compliance ambiguity; legal risk | Evidence: Virginia Rules [3] [4]; DOLI pages [5] [6] |
| GRTC transit overlay not compiled | High | Unclear | GRTC Planning/GIS | Equity blind spots | Inference |
| VDH maternal health data URL/format unconfirmed | Critical | Partial | VDH OFHS/Data | Misleading/outdated analytics | Inference |
| ACS table codes not documented in repo | Medium (Resolved) | Yes | Census APIs | Slower dev; inconsistent metrics | Evidence: S1301 [7], B13002 [8], DP05 [9] |
| Tools used by maternal orgs unknown | High | Partial | RCHD/hospitals/CBOs | Low adoption; duplication | Evidence: Unite Virginia [10]; Help1RVA [1]; Inference: local tools |

*Takeaway: Three gaps are immediately bridgeable (compliance content, ACS codebook, seed program list), two need targeted outreach (GRTC, VDH), and two require structured partner engagement.*

## Youth Employment Pathways—From Compliance-First to Match-Ready

We can deliver a safe, useful v1 by combining plain-language labor rules, a curated seed program list, and a transparent employer intake while transit overlays are confirmed.

### Compliance Guardrails Now: Embed Virginia Rules + DOLI

Age-aware rules can be integrated today to prevent unsafe matches. Virginia Rules and the Department of Labor and Industry (DOLI) provide clear, plain-language guidelines for youth employment [5] [3].

| Age Band | Hours (School Year) | Hours (Summer: June 1 - Labor Day) | Prohibited Examples | Source |
| :--- | :--- | :--- | :--- | :--- |
| 14–15 | 3 hrs/day, 18 hrs/week; 7 AM to 7 PM [3] [6] | 8 hrs/day, 40 hrs/week; 7 AM to 9 PM [3] [6] | Construction, manufacturing, scaffolding [4] | Virginia Rules [3] [4]; DOLI [6] |
| 16–17 | No restrictions on hours [3] [6] | No restrictions on hours [3] [6] | Hazardous occupations [5] | Virginia Rules [3]; DOLI [6] |

*Takeaway: Hardcode these hour limits and prohibited sectors into the MVP's matching logic to avoid severe civil and criminal penalties for employers [3].*

### Program Discovery: Seed List + Intake to Overcome Fragmentation

A curated starter directory plus a public intake form enables immediate utility and rapid growth. Currently, only individual programs like the YMCA's Teen Leaders Club and NextGen-Leaders in Training are highly visible [1] [2] [11]. 
* **Action:** Curate 15–25 anchor entries (YMCA branches, known nonprofits).
* **Action:** Build an intake form capturing age served, paid/unpaid status, and schedule.
* **Action:** Implement a "Verified / Unverified" transparency tag.

### Youth-Friendly Employers: Risk-aware Bootstrapping

Without a directory, focus on safe-entry sectors and self-identification.
* **Action:** Deploy an employer interest form with age-band eligibility and roles, auto-flagging prohibited tasks for 14–15-year-olds.
* **Action:** Publish criteria for a "Verified Youth Employer" badge.

## Transit Equity—Securing the GRTC Overlay

Confirm GTFS/ArcGIS within 48 hours; until then, expose transit uncertainty transparently.
* **Action:** Request GTFS/ArcGIS from GRTC Planning/GIS.
* **Interim:** Map locations and link to directions, exposing a "Transit suitability: unknown" badge to avoid privileging car owners.

## Maternal Health Data Coordination—De-risking with ACS Now, VDH Next

Use ACS for denominators today and lock down VDH endpoints before publishing event/outcome claims.

### ACS Codebook for Richmond—Ready-to-Use

The following ACS tables are confirmed and sufficient to scaffold population and fertility indicators immediately.

| Table | Purpose | Vintage | API Readiness |
| :--- | :--- | :--- | :--- |
| S1301 (5-year) | Fertility by age/race/education [7] | 2024 [7] | Yes [7] |
| B13002 (1-/5-year) | Births by marital status and age [8] [12] | 2024/2023 [8] [12] | Yes [8] [12] |
| DP05 | Female 15–44 denominators [9] | 2022+ [9] | Yes [9] |

*Takeaway: Integrate these tables immediately to establish baseline metrics while awaiting state-level health data.*

### Confirming VDH Data Endpoints and Formats

Confirm URLs and formats with VDH; assume Tableau/Socrata with CSV/JSON until verified.
* **Action:** Outreach to VDH Office of Family Health Services.
* **Action:** Add "data currency" labels in the UI until confirmations are in place to prevent misleading analytics.

### Tool Interoperability—Adoption Hinges on Not Duplicating Referrals

Evidence shows the existence of Unite Virginia, a statewide closed-loop coordinated care network connecting health and social services [13] [10] [14]. Additionally, local resources like Help1RVA are actively linked by community partners [1].
* **Action:** Map current tools used by Richmond hospital OB teams and CBOs via discovery calls.
* **Action:** Define minimal interoperability to avoid double data entry, which would cripple provider adoption.

## Inferences and Unknowns—Validation Plan with Owners and SLAs

Label assumptions, assign owners, and set 48-hour validation targets to keep the MVP honest.

| Item | What we think (Inference) | Evidence | How we'll validate | Owner | SLA |
| :--- | :--- | :--- | :--- | :--- | :--- |
| GRTC GTFS exists | Likely GTFS/ArcGIS | Common practice | Email GRTC; confirm URL | PM | 48h |
| Maternal dashboards have CSV/JSON | Many VDH dashboards do | State practice | Call VDH OFHS/Data | Data lead | 48h |
| Employers via Chamber/VCW | Likely partners | Program norms | Outreach to Chamber/VCW | Partnerships | 1 week |
| Youth program anchors | MYA/RPS CTE | Local norms | Direct contact | PM | 1 week |

*Takeaway: Clear ownership and tight SLAs ensure that inferences are rapidly converted into facts or discarded.*

## Risk Register—Failure Scenarios and Mitigations

The biggest risks are unsafe job matching, equity blind spots, and duplicative workflows.

| Risk | Likelihood | Impact | Mitigation | Status |
| :--- | :--- | :--- | :--- | :--- |
| Mis-matching minors to prohibited work | Medium | High | Embed Virginia Rules guardrails [3] [4]; manual vetting | Active |
| Transit inequity | High | Medium | GRTC overlay or "unknown" badge + distance bias | Active |
| Misleading maternal analytics | Medium | High | Use ACS for denominators [7] [8]; gate VDH events | Active |
| Low provider adoption | Medium | High | Align with Unite Us [10] /Help1RVA [1]; discovery calls | Planned |

*Takeaway: Proactive mitigation strategies are required to maintain user trust and legal compliance.*

## 48-Hour Sprint Plan—Deliverables, Owners, and Effort

Ship a safe, value-creating MVP slice with visible honesty about unknowns.

| Deliverable | Description | Owner | Effort (hrs) |
| :--- | :--- | :--- | :--- |
| Compliance module | Age-aware labor rules + links | Content lead | 6 |
| ACS codebook | S1301/B13002/DP05 + API URLs | Data eng | 6 |
| Seed program list | 15–25 curated entries + intake form | PM/Research | 10 |
| Outreach packets | GRTC + VDH inquiry emails | PM | 2 |
| UI flags | "Verified," "Transit unknown," "Data currency" | Design/FE | 8 |

*Takeaway: This sprint plan focuses on immediate unblocking actions while setting up the infrastructure to ingest missing data as it becomes available.*

## References

1. *Teen Leaders Club - YMCA of Greater Richmond/RVA*. https://www.ymcarichmond.org/programs/teens/leaders-club/
2. *Teens Programs - YMCA of Greater Richmond*. https://www.ymcarichmond.org/programs/teens/
3. *Teens and Employment – Virginia Rules*. https://virginiarules.org/varules_topics/teens-and-employment/
4. *Teens and Employment*. https://resources.finalsite.net/images/v1728319861/fcps1org/su0t8os9wqnpis7gdxlx/Teens-Employment-Student-Handout-2023.pdf
5. *DOLI – Virginia Department of Labor and Industry  - Youth Employment*. https://doli.virginia.gov/programs/labor-law/youth-employment/
6. *VIRGINIA DEPARTMENT OF LABOR AND INDUSTRY*. https://townhall.virginia.gov/L/GetFile.cfm?File=C:%5CTownHall%5Cdocroot%5CGuidanceDocs%5C181%5CGDoc_DOLI_3197_v3.pdf
7. *S1301: Fertility - Census Bureau Table*. https://data.census.gov/table/ACSST5Y2024.S1301?tid=ACSST5Y2024.S1301
8. *B13002: Women 15 to 50 Years Who ... - Census Bureau Table*. https://data.census.gov/table/ACSDT1Y2024.B13002?q=B13002
9. *DP05: ACS Demographic and ... - Census Bureau Table*. https://data.census.gov/table/ACSDP1Y2022.DP05
10. *Virginia to Partner with Unite Us to Create Statewide Infrastructure Connecting Health and Social Services - uniteus.com*. https://uniteus.com/press/virginia-to-partner-with-unite-us-to-create-statewide-infrastructure-connecting-health-and-social-services-3/
11. *NextGen-Leaders In Training | YMCA of the Virginia Peninsulas*. https://www.ymcavp.org/programs-and-classes/youth-and-teen-programs/nextgen
12. *B13002: Women 15 to 50 Years Who ... - Census Bureau Table*. https://data.census.gov/table/ACSDT5Y2023.B13002?q=ZCTA5+03833+Health
13. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/get-help/richmond-city-resources/
14. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/