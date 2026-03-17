# From Zero to Useful: Shipping a Youth Jobs MVP in Richmond Without a Dataset

## Executive Summary

Building a civic-tech MVP when no structured dataset exists (a "D3=1" data readiness problem) requires a shift from aggregating data to curating high-value pathways. In Richmond, Virginia, the current landscape offers enough authoritative sources to seed a credible MVP immediately. The City-run Youth Works RVA program is actively accepting applications for Summer 2026, targeting 750 youth, with a strict deadline of March 31, 2026 [1]. Virginia Career Works (VCW) provides WIOA Youth services for ages 14–24 [2] [3], and NextUp coordinates programs for ages 11–19 [4]. 

Instead of attempting to build an exhaustive "one-stop shop"—which Open Referral notes often fails due to the significant investment required for maintenance [5] —teams should curate a "Starter 12" dataset. This focused approach delivers immediate value by routing users to direct application links and verified phone numbers. To future-proof this small dataset, teams should structure it using the Human Services Data Specification (HSDS), the industry exchange format for resource directories [6]. 

Small datasets require specific UI strategies. Interfaces must rely on guidance rather than long lists, utilizing empty states to teach users and route them to the next best action [7] [8]. When deciding between manual curation and automated scraping, teams should prioritize demo stability and compliance. While recent rulings like *hiQ v. LinkedIn* and *Van Buren v. United States* suggest scraping public data likely does not violate the Computer Fraud and Abuse Act (CFAA), scraping remains fragile and prone to breaking during demos [9] [10]. Ultimately, a successful MVP will establish a lightweight Data Collaborative model for maintenance, ensuring the curated content remains accurate and actionable [5].

## Problem Frame — Ship value with D3=1 data by scoping to “paid summer jobs” and “re-entry paths”

With no pre-existing structured data, the fastest path to a useful MVP is a narrow, verifiable slice aligned to current demand and authoritative sources. Attempting to scrape every possible opportunity creates a brittle product filled with stale data.

### Richmond Youth Employment Now — 750 summer slots and open apps create urgency

The seasonal window for summer employment concentrates user intent and creates a natural deadline for the MVP. Applications for Youth Engagement Services — Youth Works RVA: Summer 2026 are officially open and will remain open until March 31st, 2026 [1]. Richmond’s Office of Community Wealth Building aims to serve 750 Richmond youth, ages 14 through 24, through paid work experiences and career exploration [1]. 

This time-sensitive demand provides a clear use case. The MVP should be designed around this specific window, making the homepage a deadline-first call to action.

### Two Priority Journeys — Ages 14–24 summer jobs vs. 18–24 not in school

To maximize impact with minimal data, the MVP should focus on two high-value user journeys. The first journey addresses the question, "How do I get a paid summer job?" by routing users to the various Youth Works RVA tracks [11]. The second journey addresses the question, "I’m 18–24 and not in school—what now?" by routing users to YES Forward and VCW WIOA Youth programs [11] [2]. 

By focusing exclusively on these two paths, the MVP can deliver highly relevant, verified information without needing a massive database.

## Content Curation Workflow — Build a credible “Starter 12” in 48 hours

A disciplined curation process seeds a reliable dataset fast. This workflow ensures the data is accurate, standardized, and ready for immediate use.

### Step 1: Source Discovery from authoritative pages

Start by identifying official, authoritative pages that provide direct contact information and clear eligibility requirements. Key sources for Richmond include the City's Youth Engagement Services (YES) and Youth Works RVA pages [11], the Virginia Career Works (VCW) WIOA Youth program pages [2], and the NextUp RVA portal [4]. Capture direct application links, phone numbers, and named staff contacts.

### Step 2: Extract + Normalize to HSDS minimal fields

Even a dataset of 10–15 items benefits from consistent structuring. Use the Human Services Data Specification (HSDS), an exchange format for publishing machine-readable data about human services [6]. Extract the data into a spreadsheet aligned to HSDS minimal fields: organization, service, location, eligibility, contacts, and a custom "last_verified" field.

### Step 3: Verify and Timestamp

Credibility relies on accuracy. Verify the extracted information by checking the official pages or contacting the listed staff. For example, the YES program lists Dr. Lerone Joseph as the Program Manager and Erika Love as the Program Coordinator [11]. Record the exact date the information was confirmed in the "last_verified" field.

### Step 4: Publish as Static JSON + Lightweight API

Serve the curated data as a stable, static JSON file via a lightweight API endpoint (e.g., `/resources`). This ensures the MVP remains fast and stable during hackathon demos, avoiding the latency and failure risks associated with live scraping.

### Step 5: Instrument and Iterate

Log user clickthroughs and search terms to understand demand. Use this data to identify missing records and inform the next round of curation targets, ensuring the dataset grows based on actual user needs.

### Table — “Starter 12” Records and Fields

| Program | Age Range | Residency/Status | Apply Link / Phone | Contact Person | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Youth Works: TRIP | 14–24 | Richmond resident | rva.gov/form/youth-works... | Erika Love | City of Richmond [11] |
| Youth Works: CIT | 14–16 | Richmond resident | rva.gov/form/youth-works... | Erika Love | City of Richmond [11] |
| Youth Works: Virtual | 14–15 | Richmond resident | rva.gov/form/youth-works... | Erika Love | City of Richmond [11] |
| Youth Works: In-Person | 16–24 | Richmond resident | rva.gov/form/youth-works... | Erika Love | City of Richmond [11] |
| Youth Works: Founders | 16–24 | Richmond resident | rva.gov/form/youth-works... | Erika Love | City of Richmond [11] |
| YES Forward | 18–24 | Richmond, Out of school | lerone.joseph@rva.gov | Dr. Lerone Joseph | City of Richmond [11] |
| VCW Capital Region | 14–24 | Regional | 804-652-3241 | Center Staff | VCW / 211 VA [2] [12] |
| NextUp RVA | 11–19 | Richmond | nextuprva.org | NextUp Staff | NextUp [4] |

*Takeaway: This focused dataset covers the most critical youth employment pathways in Richmond, providing immediate, actionable contact points for users.*

## Scope Rules That Preserve Credibility — What’s in, what’s out

To maintain trust, the MVP must strictly control what information is included. A small, highly accurate directory is vastly superior to a large, outdated one.

### Inclusion Criteria with Evidence

To be included in the MVP, a program must meet three strict criteria: it must come from an official source, it must be applicable to the current year (e.g., Summer 2026), and it must have a reachable contact or direct application link. Programs like Youth Works RVA and VCW WIOA Youth perfectly fit these criteria [1] [2].

### Exclusion & Deferral List

Exclude unverified third-party lists, ambiguous "opportunity" aggregators, and employer-specific job postings unless they are officially partnered with the city or VCW. Deferring these items prevents the MVP from becoming cluttered with dead links and unverified claims.

## UI for Limited Datasets — Turn 10–15 records into confident action

When a dataset is small, the UI must work harder to guide the user. Users scan rather than read, so the interface must provide direct pathways and clear next steps [8].

### 3-Question Eligibility Wizard

Instead of presenting a long list of eligibility conditions, ask questions to establish eligibility [8]. A simple 3-question wizard asking for age, Richmond residency, and in-school status can instantly route users to the correct program (e.g., Youth Works vs. YES Forward vs. VCW WIOA) [11] [2].

### Deadline-First Homepage and Action Tiles

Capitalize on the urgency of the March 31 deadline. Prominently feature action tiles like "Apply by Mar 31" for Youth Works [1] and "Call VCW: 804-652-3241" [12]. Add a "Text me a reminder" feature to capture users who aren't ready to apply immediately.

### Empty-State and “No Results” Design

Totally empty states cause confusion about how and whether the system is working [7]. When a search yields no results, use the empty state to provide system-status messages, education cues, and next-best actions [7]. For example, display "No direct matches—two strong options" with buttons to call VCW or explore NextUp programs [12] [4].

### Plain Language Microcopy

Follow GOV.UK design principles: start with less, use simple questions, and only add help text if user research shows it is needed [8]. If you find yourself having to explain how the user interface works, fix the interface so it doesn’t need explaining [8].

## Communicating Data Limitations — Honesty that builds trust

Transparency about the dataset's size and sourcing methods builds credibility with users and stakeholders.

### “How We Source” + “Report an Update”

Include a brief "How We Source" note explaining that the data is manually curated from official city and state pages. Mention the use of the HSDS standard to signal technical maturity [6]. Provide a clear "Report an Update" webform or email link to create a fast feedback loop for corrections.

### Verification Badges and Timestamps

Visibly date-stamp all listings with a "Last verified on [Date]" badge. This visual cue immediately communicates that the information is actively maintained, addressing the common user fear of calling a disconnected number.

## Maintenance Pathways — From manual upkeep to shared stewardship

Resource data requires a significant investment of resources to collect and maintain, and maintenance isn't reliably automatable [5]. The MVP must include a realistic plan for keeping the data fresh.

### Table — Maintenance Models Compared: Curated vs Scraped vs Hybrid

| Model | Coverage | Demo Stability | ToS / Legal Risk | Maintenance Cost | Data Freshness |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Curated (Static)** | Low (10-20 items) | High (Never breaks) | None | High (Manual updates) | High (If verified regularly) |
| **Scraped (Automated)** | High (100+ items) | Low (Breaks silently) | Moderate (ToS violations) | High (Fixing broken scrapers) | Variable (Depends on scraper health) |
| **Hybrid** | Medium | High (Static fallback) | Low (Public gov pages only) | Medium | High for core, variable for rest |

*Takeaway: While scraping public websites likely does not violate the CFAA [10], it remains technically fragile. A curated or hybrid approach ensures the MVP functions flawlessly during critical demonstrations.*

### Table — Open Referral Models: Service Register, Data Utility, Data Collaborative

| Model | Who Maintains | How Sustained | Benefits | Challenges |
| :--- | :--- | :--- | :--- | :--- |
| **Service Register** | Service Providers | Authority mandates it (e.g., funder) | Canonical data directly from the source | Requires monitoring and enforcement [5] |
| **Data Utility** | One Steward | Fees for premium services | Single source of truth, sustainable business model | Single point of failure, uncertain business model [5] |
| **Data Collaborative** | A Federation | Shared responsibility, mutual benefit | Efficient distribution of labor, resilient | Cooperation requires resources to sustain [5] |

*Takeaway: Open Referral identifies these three patterns for sustainable resource data production [5]. For a hackathon MVP, the Data Collaborative is the most viable starting point.*

### Richmond Maintenance Plan (90–180 days)

Start with a lightweight Data Collaborative model. Ask the Office of Community Wealth Building (OCWB) and VCW to "adopt" their respective records. Schedule automated quarterly verification emails to the listed contacts (e.g., Dr. Lerone Joseph) asking them to confirm or update their details [11]. Publish the resulting HSDS open data to encourage reuse by platforms like 211 Virginia.

## Legal, ToS, and Ethics — Pragmatic guardrails for a hackathon

If the team decides to incorporate any automated data collection, they must navigate the legal and ethical landscape carefully.

### Case Law Snapshot

Recent rulings have clarified the legal risks of web scraping. In *hiQ Labs, Inc. v. LinkedIn Corp.*, the Ninth Circuit Court of Appeals ruled that automated scraping of publicly accessible data likely does not violate the Computer Fraud and Abuse Act (CFAA) [13] [10]. The Supreme Court's decision in *Van Buren v. United States* further narrowed the CFAA's "exceeds authorized access" clause [9] [10]. However, this does not grant blanket permission; Terms of Service (ToS) and other civil claims (like trespass or tortious interference) may still apply [10].

### Scraping Checklist

If scraping is utilized, limit it strictly to non-authenticated, public government pages. Always check and respect the `robots.txt` file and the site's Terms of Service. Implement rate limiting (throttling) to avoid overwhelming the target servers. Set up alerts for HTML structure changes, and crucially, always maintain a static JSON fallback to ensure the MVP remains functional if the scraper breaks.

## Partnership Map — Who to call, who can verify

Identifying named maintainers reduces data drift and speeds up the verification process.

### Table — Core Partners and Contacts

| Organization / Program | Role | Contact Person | What They Verify |
| :--- | :--- | :--- | :--- |
| **YES / Youth Works RVA** | Program Manager | Dr. Lerone Joseph [11] | YES Forward eligibility, overall program status |
| **YES / Youth Works RVA** | Program Coordinator | Erika Love [11] | Summer tracks, application deadlines, partner enrollment |
| **VCW Capital Region** | Center Operations | Center Staff (804-652-3241) [12] | WIOA Youth intake process, center hours |
| **NextUp RVA** | Program Coordination | NextUp Staff [4] | Afterschool/summer program availability for ages 11-19 |

*Takeaway: Direct relationships with these individuals and offices are more valuable than any automated scraping script for maintaining a high-quality D3=1 dataset.*

## Analytics & Impact — Prove value with action metrics

Because the dataset is small, the MVP cannot be judged on catalog size. Impact must be measured through user actions and successful routing.

### Pilot KPIs and Targets

Track specific action metrics during the pilot phase. Key Performance Indicators (KPIs) should include:
1. **Apply Clicks**: Number of users clicking through to the Youth Works RVA application form [1]. (Target: 30+ in week 1).
2. **Call Taps**: Number of users tapping the VCW or YES phone numbers on mobile devices [11] [12]. (Target: 50+ in week 1).
3. **Wizard Completions**: Number of users successfully routed through the 3-question eligibility wizard.
4. **Search Terms**: Analyze zero-result search queries to identify missing programs and guide the next round of curation.

## Roadmap — 4-week hackathon sprint to sustainable prototype

A structured sprint ensures the team moves from zero data to a functional, maintainable MVP.

### Week 1–2: Curate + Normalize + Publish

Focus entirely on building the "Starter 12" dataset. Extract data from the City of Richmond, VCW, and NextUp pages [11] [2] [4]. Normalize the data into the HSDS format [6] and make the verification calls to confirm the March 31 deadline and contact details [1]. Publish the static JSON.

### Week 3: UI + Analytics + Copy

Develop the front-end interface. Implement the 3-question eligibility wizard, the deadline-first homepage, and the robust empty-state designs [7] [8]. Integrate analytics tracking for apply clicks and call taps. Refine the microcopy using plain language principles [8].

### Week 4: Maintenance Handshake + Demo Readiness

Finalize the maintenance strategy. Draft "adopt-a-record" emails to the identified partners (e.g., OCWB, VCW). Ensure the static JSON fallback is securely cached for the final presentation. Prepare the demo script to highlight the action metrics and the sustainable Data Collaborative maintenance model [5].

## References

1. *Youth Works RVA: Summer 2026 Applications Now Open! | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/news/youth-works-rva-summer-2026/
2. *Youth Programs - Virginia Career Works*. https://virginiacareerworks.com/youth-programs/
3. *Attachment C WIOA Youth Eligibility*. https://virginiacareerworks.com/wp-content/uploads/postVWL-15-02-WIOA-Youth-Eligibility-Attachment-C-UPDATED-10-27-2015.docx.pdf
4. *NextUp - Find Afterschool and Summer Programs in Richmond*. https://nextuprva.org/
5. *Producing resource directory information as a public good*. https://openreferral.org/wp-content/uploads/2023/12/Open_Referral_Data_Production_Strategies_Whitepaper.pdf
6. *Human Services Data Specification (HSDS) — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/overview.html
7. *Designing Empty States in Complex Applications: 3 Guidelines - NN/G*. https://www.nngroup.com/articles/empty-state-interface-design/
8. *Writing for user interfaces - Service Manual - GOV.UK*. https://www.gov.uk/service-manual/design/writing-for-user-interfaces
9. *19-783 Van Buren v. United States (06/03/2021)*. https://www.supremecourt.gov/opinions/20pdf/19-783_k53l.pdf
10. *                HIQ LABS, INC. V. LINKEDIN CORPORATION, No. 17-16783 (9th Cir. 2022) :: Justia    *. https://law.justia.com/cases/federal/appellate-courts/ca9/17-16783/17-16783-2022-04-18.html
11. *Youth Engagement Services | Richmond*. https://www.rva.gov/community-wealth-building/youth-engagement-services
12. *Programs by Virginia Career Works - Capital Region serving Beaumont, VA | findhelp.org*. https://www.findhelp.org/provider/virginia-career-works---capital-region--richmond-va/5370694754500608?postal=23014
13. *hiQ v. LinkedIn | Electronic Frontier Foundation*. https://www.eff.org/cases/hiq-v-linkedin