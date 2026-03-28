> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.


# Unblocking Richmond's Thriving Families MVP: High-impact data gaps, 48-hour bridges, and risk-proof choices

## Executive Summary
Developing a high-quality MVP for Richmond's Thriving Families pillar requires navigating significant information gaps across youth employment and maternal health data. While some assumed gaps—like plain-language labor laws and ACS table codes—are actually resolved and ready for immediate integration, others pose critical risks. The lack of a centralized youth employer directory and fragmented Virginia Department of Health (VDH) data endpoints threaten the MVP's matching quality and analytical accuracy. By implementing targeted 48-hour workarounds—such as bootstrapping a seed directory, leveraging Census API data for baseline metrics, and mapping existing referral networks like Unite Virginia—the development team can safely unblock the MVP while systematically resolving remaining data integration steps.

## Gap Inventory with Severity, Bridgeability, and Consequences

Prioritizing these gaps ensures that development efforts focus on unblocking core logic and compliance while transparently labeling pending data.

| Gap | Severity | 48h Bridgeable? | Likely Source/Owner | Consequence if Ignored | Evidence vs. Inference |
| :--- | :--- | :--- | :--- | :--- | :--- |
| No compiled list of Richmond youth employment programs | High | Partial | City/nonprofits/schools | Broken routing, low trust | Evidence: YMCA pages [1] [2]; Youth Engagement Services [0] |
| No employer directory for youth-friendly businesses | Critical | Partial | Chamber/employer partners | Mis-matches; compliance risk | Evidence: ChamberRVA [11]; VA Career Works [4] |
| VA youth labor law plain-language summary not published | Low (Resolved) | Yes | Virginia Rules + DOLI | Compliance ambiguity; legal risk | Evidence: Virginia Rules [16]; DOLI pages [17] |
| GRTC transit overlay not compiled | High | Yes | Transitland / VA Open Data | Equity blind spots | Evidence: GTFS feeds available [5] [6] |
| VDH maternal health data URL/format unconfirmed | Critical | Partial | VDH OFHS/Data | Misleading/outdated analytics | Evidence: VDH MCH Dashboard [7] [9] |
| ACS table codes not documented in repo | Medium (Resolved) | Yes | Census APIs | Slower dev; inconsistent metrics | Evidence: S1301 [7], B13002 [8], DP05 [9] |
| Tools used by maternal orgs fragmented | High | Partial | RCHD/hospitals/CBOs | Low adoption; duplication | Evidence: Unite Virginia [12]; Help1RVA [10] |

*Takeaway: Three gaps are immediately bridgeable (compliance content, ACS codebook, seed program list), two have confirmed data sources requiring integration (GRTC, VDH), and two require structured partner engagement.*

## Youth Employment Pathways—From Compliance-First to Match-Ready

We can deliver a safe, useful v1 by combining plain-language labor rules, a curated seed program list, and a transparent employer intake while transit overlays are confirmed.

### Compliance Guardrails Now: Embed Virginia Rules + DOLI

Age-aware rules can be integrated today to prevent unsafe matches. Virginia Rules and the Department of Labor and Industry (DOLI) provide clear, plain-language guidelines for youth employment [16] [17].

| Age Band | Hours (School Year) | Hours (Summer: June 1 - Labor Day) | Prohibited Examples | Source |
| :--- | :--- | :--- | :--- | :--- |
| 14–15 | 3 hrs/day, 18 hrs/week; 7 AM to 7 PM [16] [17] | 8 hrs/day, 40 hrs/week; 7 AM to 9 PM [16] [17] | Construction, manufacturing, scaffolding [15] | Virginia Rules [16]; DOLI [17] |
| 16–17 | No restrictions on hours [16] [17] | No restrictions on hours [16] [17] | Hazardous occupations [15] | Virginia Rules [16]; DOLI [17] |

*Takeaway: Hardcode these hour limits and prohibited sectors into the MVP's matching logic to avoid severe civil and criminal penalties for employers [14].*

### Program Discovery: Seed List + Intake to Overcome Fragmentation

A curated starter directory plus a public intake form enables immediate utility and rapid growth. Currently, programs like the YMCA's Teen Leaders Club, NextGen-Leaders in Training, and the City of Richmond's Youth Engagement Services are highly visible [0] [1] [2]. 
* **Action:** Curate 15–25 anchor entries (YMCA branches, known nonprofits, RPS CTE programs [2]).
* **Action:** Build an intake form capturing age served, paid/unpaid status, and schedule.
* **Action:** Implement a "Verified / Unverified" transparency tag.

### Youth-Friendly Employers: Risk-aware Bootstrapping

Without a directory, focus on safe-entry sectors and self-identification.
* **Action:** Deploy an employer interest form with age-band eligibility and roles, auto-flagging prohibited tasks for 14–15-year-olds.
* **Action:** Publish criteria for a "Verified Youth Employer" badge.

## Transit Equity—Securing the GRTC Overlay

GTFS data is confirmed and available via Transitland [5] and the Virginia Open Data Portal [6] [8].
* **Action:** Integrate the GRTC GTFS feed from the Virginia Open Data Portal [6].
* **Interim:** Until integration is complete, map locations and link to directions, exposing a "Transit routing pending" badge to avoid privileging car owners.

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

VDH Maternal & Child Health Indicators Dashboard provides data and visualizations on key maternal and child health measures [7] [9].
* **Action:** Extract CSV/JSON exports from the VDH Office of Family Health Services dashboard [7].
* **Action:** Add "data currency" labels in the UI to prevent misleading analytics.

### Tool Interoperability—Adoption Hinges on Not Duplicating Referrals

Evidence shows the existence of Unite Virginia, a statewide closed-loop coordinated care network connecting health and social services [12]. Additionally, local resources like Help1RVA are actively linked by community partners [10].
* **Action:** Map current tools used by Richmond hospital OB teams and CBOs via discovery calls.
* **Action:** Define minimal interoperability to avoid double data entry, which would cripple provider adoption.

## Inferences and Validations—Validation Plan with Owners and SLAs

Label assumptions, assign owners, and set 48-hour validation targets to keep the MVP honest.

| Item | Current Status | Evidence | Next Steps | Owner | SLA |
| :--- | :--- | :--- | :--- | :--- | :--- |
| GRTC GTFS exists | Confirmed | Transitland [5], VA Open Data [6] | Integrate feed | PM | 48h |
| Maternal dashboards have CSV/JSON | Confirmed | VDH MCH Dashboard [7] | Extract data | Data lead | 48h |
| Employers via Chamber/VCW | Likely partners | ChamberRVA [11] | Outreach to Chamber/VCW | Partnerships | 1 week |
| Youth program anchors | Confirmed | YES [0], RPS CTE [2] | Direct contact | PM | 1 week |

*Takeaway: Clear ownership and tight SLAs ensure that remaining integrations are rapidly completed.*

## Risk Register—Failure Scenarios and Mitigations

The biggest risks are unsafe job matching, equity blind spots, and duplicative workflows.

| Risk | Likelihood | Impact | Mitigation | Status |
| :--- | :--- | :--- | :--- | :--- |
| Mis-matching minors to prohibited work | Medium | High | Embed Virginia Rules guardrails [16] [17]; manual vetting | Active |
| Transit inequity | High | Medium | GRTC overlay integration [6] + distance bias | Active |
| Misleading maternal analytics | Medium | High | Use ACS for denominators [7] [8]; gate VDH events | Active |
| Low provider adoption | Medium | High | Align with Unite Us [12] /Help1RVA [10]; discovery calls | Planned |

*Takeaway: Proactive mitigation strategies are required to maintain user trust and legal compliance.*

## 48-Hour Sprint Plan—Deliverables, Owners, and Effort

Ship a safe, value-creating MVP slice with visible honesty about pending integrations.

| Deliverable | Description | Owner | Effort (hrs) |
| :--- | :--- | :--- | :--- |
| Compliance module | Age-aware labor rules + links | Content lead | 6 |
| ACS codebook | S1301/B13002/DP05 + API URLs | Data eng | 6 |
| Seed program list | 15–25 curated entries + intake form | PM/Research | 10 |
| Data Integration | GRTC GTFS + VDH data extraction | Data eng | 8 |
| UI flags | "Verified," "Transit routing pending," "Data currency" | Design/FE | 8 |

*Takeaway: This sprint plan focuses on immediate unblocking actions while setting up the infrastructure to ingest missing data as it becomes available.*