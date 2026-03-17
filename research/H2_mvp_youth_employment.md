# 48-Hour Richmond Youth Jobs MVP — Manual Curation to Mobile Demo

## Executive Summary
Building a functional, trustworthy youth employment directory for Richmond in 48 hours without pre-existing data is highly feasible by leveraging a no-code stack and manual curation of high-signal public sources. The core strategy relies on extracting 12–20 authoritative programs from city, school, and established nonprofit websites to create a "seed" database. Because seasonality and program closures are the primary risks to user trust, the MVP must prioritize data integrity features: visible "last verified" timestamps, clear application windows, and status badges (Open/Waitlist/Closed). 

To deliver maximum value immediately, the MVP will default to filtering for ages 14–18, unlocking the summer placements that parents and teens are actively seeking right now. A plain-language, DOLI-based work permit guide can be drafted in under two hours to complement the directory. By utilizing a framework like Softr or Glide connected to an Airtable or Google Sheets backend, the team can bypass custom front-end development and focus entirely on data accuracy, mobile UX, and demonstrating a credible, phone-first solution by Saturday.

## MVP Scope and Decision Frame

The primary objective is to deliver a useful, phone-first directory alongside a plain-language work guide within a strict 48-hour window. The MVP will not attempt to be exhaustive; instead, it will provide a highly curated, verified list of 12–20 programs that demonstrate immediate availability or clear application timelines. 

### Must-Haves in 48 Hours
To achieve a credible "find something you can do this summer" experience, the MVP must include:
* An age-filtered directory with detail pages outlining eligibility, dates, contacts, location, and direct application links.
* A plain-language "Can I work at 14/15/16?" guide based on Virginia Department of Labor and Industry (DOLI) standards, complete with a timestamp.
* Prominent disclaimers, a "Report an issue" form, and a visible "last verified" date on every program card.
* An administrative spreadsheet (Airtable or Google Sheets) that serves as the database and supports JSON export.

## Content Curation Plan

Building a high-signal directory from official pages requires a disciplined 2–3 hour sprint. The team must start with city/school programs and well-known nonprofits, verifying dates and contacts by phone where pages appear outdated, and meticulously recording verification notes.

### Seed Program List
The following 10+ entries can be immediately sourced from official public pages to populate the MVP database.

| Program | Organization | Age | Type | Application Window | Stipend/Pay | Source |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Youth Engagement Services (YES) | City of Richmond | 14–24 | Work-Based Learning | Summer tracks | Varies | [1] |
| Counselor In Training (CIT) | City of Richmond Parks & Rec | 14–15 | Leadership/Training | Starts in March | $800 incentive | [2] |
| Teens in Richmond & Parks (TRIP) | City of Richmond | 14–24 | Hands-on experience | Summer | Varies | [1] |
| Work-Based Learning (WBL) | Richmond Public Schools | High School | Internships/Apprenticeships | School Year/Summer | Paid/Unpaid | [3] |
| PFF Student Program | Partnership for the Future | 9th Grade Entry | Paid Internships | Summer (7 weeks) | Paid | [4] [5] |
| Teen Leaders Club | YMCA of Greater Richmond | Middle/High School | Leadership/Service | Year-long (Starts Sept) | Volunteer | [6] [7] |
| Pre-Employment Transition Services | Goodwill of Central & Coastal VA | 16–22 | Workplace Readiness | 8-week Summer | Unpaid/Training | [8] |
| Job Corps | US Dept of Labor | 16–24 | Career Training | Rolling | Paid Training | [9] |

*Takeaway: This seed list covers a spectrum of opportunities—from paid internships to leadership development—ensuring the MVP appeals to various youth needs and age groups.*

### 2–3 Hour Sprint Process
To curate this content efficiently before the Saturday build time begins, the team should follow a strict timeboxed process:
* **30 mins - Sourcing:** Compile URLs from rva.gov, rvaschools.net, partnershipforthefuture.org, ymcarichmond.org, and jobcorps.gov. Exclude any non-Richmond service areas to prevent regional misalignment.
* **60 mins - Extraction:** Extract core fields into Airtable. Flag any pages older than 12 months for phone verification (e.g., the City of Richmond CIT page dates back to 2018 [2]).
* **30–45 mins - Verification:** Conduct phone or email verification for high-traffic entries like CIT, YES, and PFF. Log notes and update the `last_verified_at` field.
* **15 mins - Status Assignment:** Assign a definitive status (`accepting`, `waitlist`, `closed`) and define the `application_window`.
* **15 mins - Copywriting:** Perform a quick copy pass to ensure plain-language descriptions of 70 words or less per card.

## Work Permit Guide (DOLI)

A concise, age-based "Can I work?" page increases the MVP's usefulness and reduces misinformation. This can be drafted in 1–2 hours using authoritative anchors.

### Sources and Structure
While DOLI is the authoritative source, local schools heavily rely on these regulations for their own programs (e.g., RPS requires Virginia Works approval for Registered Apprenticeships [3]). The guide should be structured as follows:
* **"If you are 14–15 / 16–17"**: Clear age-bracketed rules.
* **"Hours you can work"**: Distinguishing between school-year and summer limits.
* **"Jobs you can't do"**: A simplified list of prohibited occupations.
* **"How to get a certificate"**: Steps to obtain an employment certificate if required.
* **"Where to ask questions"**: Direct contact information for DOLI.

### Quality and Legal Safeguards
Because labor laws are complex and subject to change, the guide must include a prominent disclaimer: *"Laws change—always check DOLI. This is guidance, not legal advice."* It must also feature a timestamp, direct source links to DOLI, and a "Report an update" form.

## Minimum Data Structure

A lightweight JSON schema of 12–15 fields will cover 80% of use cases, supporting search, filtering, and trustworthy UI displays.

### Core Fields Schema

| Field Name | Type | Required | Example | Notes |
| :--- | :--- | :--- | :--- | :--- |
| `id` | String | Yes | `prog_001` | Unique identifier |
| `name` | String | Yes | `Counselor In Training (CIT)` | Program title |
| `org_name` | String | Yes | `City of Richmond Parks & Rec` | Hosting organization |
| `opportunity_type` | Enum | Yes | `leadership` | e.g., paid_internship, stipend, training |
| `ages_min` | Integer | Yes | `14` | Minimum age requirement |
| `ages_max` | Integer | Yes | `15` | Maximum age requirement |
| `stipend_or_pay` | String | No | `$800 incentive` | Compensation details |
| `application_window` | String | Yes | `Starts in March` | Open/close dates |
| `status` | Enum | Yes | `accepting` | accepting, waitlist, closed, unknown |
| `service_area` | String | Yes | `Richmond City` | Geographic restriction |
| `contact_phone` | String | No | `(804) 646-7480` | E.164 format preferred |
| `website_url` | String | Yes | `https://www.rva.gov/...` | Direct link to apply/learn more |
| `last_verified_at` | Date | Yes | `2026-03-17` | ISO 8601 format |
| `verified_by` | String | Yes | `JD` | Initials of curator |

*Takeaway: This schema enforces data integrity by making `status`, `application_window`, and `last_verified_at` required fields, directly addressing the risk of stale listings.*

```json
{
 "id": "prog_001",
 "name": "Counselor In Training (CIT)",
 "org_name": "City of Richmond Parks & Rec",
 "opportunity_type": "leadership",
 "ages_min": 14,
 "ages_max": 15,
 "stipend_or_pay": "$800 incentive",
 "application_window": "Starts in March",
 "status": "accepting",
 "service_area": "Richmond City",
 "contact_phone": "+18046467480",
 "website_url": "https://www.rva.gov/parks-recreation/counselor-training-cit",
 "last_verified_at": "2026-03-17",
 "verified_by": "JD"
}
```

## UI Approach

Given the 48-hour constraint and the lack of pre-existing data, a no-code or low-code platform is the only viable path to a credible, mobile-friendly demo. [**Inference**]

### Framework Comparison

| Option | Setup Time | Mobile UX | Filters/Search | Forms | Trade-offs |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Softr + Airtable** | 2–4 hours | Good | Excellent | Native | Best for rapid directory builds; highly customizable lists. |
| **Glide + Google Sheets** | 1–3 hours | Excellent | Good | Native | Feels most like a native app; slightly less layout flexibility. |
| **Webflow CMS** | 8–12 hours | Excellent | Requires plugins | Native | Too slow for a 48-hour MVP; overkill for simple data. |
| **Next.js + Vercel** | 16+ hours | Excellent | Custom | Custom | Requires heavy developer resources; risks missing the deadline. |

*Takeaway: Softr or Glide are the recommended frameworks. They provide out-of-the-box mobile lists, multi-filtering (by age, pay, deadline), and form integrations that write directly back to the database.*

### Information Architecture and Components
The UI should consist of three primary screens:
1. **Home/Results**: Age chips (e.g., "14-15", "16-18"), search bar, and program cards.
2. **Detail Page**: Clear eligibility criteria, dates, CTA buttons ("Apply Now", "Call to Confirm"), and location.
3. **Resources**: The Work Permit Guide and a "Report an Issue" form.

To build trust by design, every card must feature badging: "Gov," "School," or "Nonprofit"; a status badge ("Open now," "Next opens: [date]"); and a verification stamp ("Verified [date]").

## Data Integrity Playbook

Handling outdated information and program closures is the most critical operational challenge for this MVP. For example, the City of Richmond's CIT page still displays a 2018 date [2], which could immediately erode user trust if not manually verified.

### Policies and Escalations
* **Verification Cadence**: The top 20 programs must be verified weekly. All entries must be date-stamped. Non-government pages require a two-source rule (e.g., cross-referencing a school announcement with the program's main site).
* **Handling Wrong Phone Numbers**: If a listed phone number is dead, curators should try the organization's main line, RVA 311, or list an alternate channel (email/web form). The database should flag `"contact_unconfirmed": true`, triggering a specific disclaimer on that program's card.
* **The "Programs Fill/Close" Problem**: Never delete a closed program. Instead, change the status to `closed`, keep the entry visible, and display the next known open date. Add a "Sign up to be notified" button to capture user interest for the next cycle.

## Disclaimers and UX Language

Clear, plain-language disclaimers mitigate risk and sustain credibility when relying on manually curated, third-party data.

* **General Directory Disclaimer**: *"We manually check these listings, but programs change fast. Always click through to the official website or call the program directly to confirm details before applying."*
* **Status Disclaimer (Top of Detail Page)**: *"Status may change—call to confirm. Last verified by our team on [Date]."*
* **Work-Permit Legal Disclaimer**: *"Labor laws change frequently. This guide is for general information and is not legal advice. Always check the Virginia DOLI website for the most current rules."*
* **Feedback Loop**: *"Help us improve. Did you find a wrong number or a closed program? [Report an issue here]."*

## Demo Flow + Success Criteria

The Saturday demo should prove that the team can deliver findability, trust signals, and useful guidance in under two minutes. 

**Success Criteria for the Demo:**
1. Display 12–20 fully curated, local entries.
2. Demonstrate working age and status filters.
3. Showcase the three trust badges (Org Type, Status, Last Verified) on a mobile layout.
4. Execute a one-click call action from a detail page.
5. Submit a "Report an issue" form and show it routing successfully to the Airtable backend.

## Execution Plan

To meet the 48-hour deadline, curation, verification, and UI assembly must happen in parallel. [**Inference**]

| Time Block | Owner | Deliverable | Acceptance Criteria |
| :--- | :--- | :--- | :--- |
| **Friday 5 PM - 8 PM** | Content Team | Seed Database | 15 programs extracted to Airtable; URLs and phone numbers logged. |
| **Friday 8 PM - 10 PM** | Content Team | Work Permit Guide | 1-page DOLI guide drafted with disclaimers. |
| **Saturday 9 AM - 12 PM** | Content Team | Verification Sprint | All 15 programs called/verified; statuses updated; copy finalized. |
| **Saturday 9 AM - 1 PM** | Tech Team | UI Assembly | Softr/Glide connected to Airtable; filters working; mobile layout set. |
| **Saturday 1 PM - 3 PM** | Joint Team | QA & Badging | Badges rendering correctly; forms tested; broken links fixed. |
| **Saturday 3 PM - 5 PM** | Joint Team | Demo Prep | Demo script finalized; test data cleared from forms. |

## Inferences and Unknowns

**Inferences (Assumptions to Validate):**
* Softr or Glide is the fastest stack for the team's current skill level and tool access.
* The target audience is primarily phone-first, necessitating a mobile-optimized UI over a desktop experience.
* 12–20 high-quality listings are sufficient to prove MVP value.
* A weekly manual verification cadence is sustainable post-launch.

**Unknowns:**
* Current real-time status for YES and CIT programs for the upcoming summer season (requires immediate phone verification).
* Any unannounced 2026 changes to RPS Work-Based Learning requirements or application links.
* The exact current URLs for DOLI work-certificate forms (must be validated during the Work Permit Guide drafting).

## References

1. *Youth Engagement Services | Richmond*. https://www.rva.gov/community-wealth-building/youth-engagement-services
2. *Counselor In Training (CIT) | Richmond*. https://www.rva.gov/parks-recreation/counselor-training-cit
3. *Workbased Learning - Richmond Public Schools*. https://www.rvaschools.net/academics/secondary/career-technical-education/workbased-learning
4. *Become a Student | Partnership for the Future*. https://www.partnershipforthefuture.org/become-a-student/
5. *Host an Intern | Partnership for the Future*. https://partnershipforthefuture.org/host-an-intern/
6. *Teen Leaders Club - YMCA of Greater Richmond/RVA*. https://www.ymcarichmond.org/programs/teens/leaders-club/
7. *Teens Programs - YMCA of Greater Richmond*. https://www.ymcarichmond.org/programs/teens/
8. *Pre-Employment Transition Services - Goodwill of Central and Coastal VA*. https://goodwillvirginia.org/get-job-ready/vocational-services/pre-employment-transition-services
9. *Your Job Corps Journey*. https://enroll.jobcorps.gov/