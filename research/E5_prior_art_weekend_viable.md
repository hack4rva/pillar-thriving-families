# From Weekend Hack to Civic Impact: What Actually Works

## Executive Summary

The fastest civic tech wins from weekend hackathons share a common DNA: they reuse existing standards, solve one specific job, and secure an institutional owner before a single line of code is written. An analysis of successful 24-to-48-hour civic tech projects reveals several critical insights for building weekend-viable minimum viable products (MVPs):

* **Reuse over reinvent:** Weekend wins come from standing on mature open-source software (OSS) and data standards. Multiple teams stood up Ohana API instances in 24–48 hours by transforming existing data into the Open Referral format [1]. 
* **Anchor a real owner before you code:** Projects paired with agency champions move from demo to deployment. For example, the San Francisco Adult Probation Department adapted Ohana to replace a 400-page printed reentry directory [1].
* **Ruthless scope to one high-frequency decision:** Narrow journeys ship and stick. DiscoverBPS focused solely on helping parents filter eligible schools, logging 15,000 users in its first year and 48,000 sessions in 2014 [2].
* **Meet moments of peak demand:** Timing drives uptake. Chicago's Flu Shot Finder ties directly to seasonal demand, utilizing a public dataset that follows Code for America's flu-shot specification [3].
* **SMS is an inclusion unlock:** Lowering tech barriers broadens reach. Textizen's SMS surveys expanded civic input [4], and mRelief's SMS eligibility screeners were actively used by Chicago Department of Family and Support Services staff [5].
* **Data governance is the hidden blocker:** Avoid private or regulated data early. Code for America's original "student app store" in Boston stalled under privacy concerns, prompting a pivot to public data for DiscoverBPS [6].
* **Show outcomes early:** Samaritan (which originated from a hackathon concept) reported that 20 unsheltered individuals navigated to housing or employment with the support of its app, catalyzing further partnerships [7].

## Why This Playbook Now: Weekend MVPs Can Move Needles

For Thriving Families (TF) teams, hackathon constraints map directly to the urgent needs of youth, workforce, health, and navigation outcomes. The fastest civic wins reuse standards, solve one job, and secure an owner before code. By focusing on a single high-frequency decision—such as finding an open shelter bed or checking program eligibility—teams can deliver a minimum credible demo in 48 hours that proves value to stakeholders and secures the runway for further development.

## Project Inventory: Comparable Weekend-Viable Builds

Most durable projects either redeployed an existing platform or laser-focused on a single decision moment with a committed public partner.

| Project | Built in 24–48h? | What was built | Data used | Team size/skills | Post-event outcome/status | Notes/Unknowns |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Sheltr.org** (RHoK Philly, 2011) | Yes (weekend launch) | Mobile web directory + map; later SMS | OSH intake facility info; Coalition Against Hunger meal data | ~7 (dev + design) | Best in Show; continued iterations across events; agency interest | Adoption by providers: unknown [8] [9] |
| **Ohana Redeploys** (CodeAcross/ODD, 2015) | Yes (weekend prototypes) | HSDS/Ohana API instances + custom search UIs | 2-1-1 data; SAMHSA/USDA; SF APD directory | Brigade-scale teams (dev, data, UX) | Set agenda, prototypes used to scope official efforts | Long-term adoption varies; data maintenance unresolved [1] |
| **Textizen** (Philadelphia, 2012) | No (fellowship; 4 months to pilot) | SMS engagement tool | Survey content; phone/SMS infra | CfA fellows (PM, design, eng) | Piloted with City Planning; later used by NYC PB | Comparable scope for weekend SMS MVP [4] [10] |
| **Chicago Flu Shot Finder** (2018+) | Unknown weekend origin | Flu clinic finder; data standard | Flu shot locations dataset; CfA flu-shot spec | Unclear (partnered build) | Live site and dataset maintained via portal | Good model for seasonal minimum demo [3] |
| **DiscoverBPS** (2011–2014) | No (months) | School choice navigator | BPS school/location/quality data; rules | CfA + City partners | 15k users yr1; 48k sessions 2014; policy/API changes | Scope lessons for "pathway guides" [2] [6] |
| **Hack to End Homelessness** (Seattle, 2014) | Yes (weekend) | YouthCare intake UI; UGM field data app | Provider intake fields; internal ops data | Mixed (dev, design, NPO) | Immediate field test (beta tested same night) | Good example of "field-first" MVP [11] |
| **Samaritan / GiveSafe** (2016–) | Concept from hackathon | Beacon + giving app + counselor flow | Merchant network; counselor notes; user stories | Startup team (PM, eng, ops) | ~7,000 residents; 500 people engaged; 20 early outcomes | Not weekend-built but outcome model relevant [7] [12] |

### Mini-Profiles of Civic Tech Projects

**Sheltr.org:** Built at the 2011 Random Hacks of Kindness in Philadelphia by a team of seven, Sheltr is a mobile-friendly web application displaying nearby housing and food services [8]. It utilized data from the Office of Supportive Housing and the Greater Philadelphia Coalition Against Hunger, winning Best in Show and sparking immediate agency interest [8].

**Ohana Redeploys:** During the 2015 CodeAcross and Open Data Day, multiple cities (Miami, San Francisco, Sacramento, Raleigh) deployed instances of the Ohana API [1]. Teams transformed local 2-1-1 or government data into the Open Referral format, creating functional search prototypes that helped set the agenda for future data interoperability conversations [1].

**Textizen:** Developed by Code for America fellows in partnership with the Philadelphia City Planning Commission, Textizen allows citizens to provide feedback via SMS [4]. Piloted just four months after the initial meeting, it drastically lowered barriers to civic participation by placing prompts on posters in public spaces [4].

**Chicago Flu Shot Finder:** Developed in partnership with the Department of Public Health, this web site helps residents find flu shot availability based on date and location [3]. It relies on a public dataset that approximately follows the Code for America flu-shot specification, demonstrating the power of aligning with seasonal demand [3].

**DiscoverBPS:** Created by Code for America fellows to simplify Boston's complex school assignment process, DiscoverBPS allows parents to filter schools by specific needs and locations [2]. The tool logged over 48,000 sessions in 2014 and ultimately prompted the school department to develop a new API for managing school data [2].

**Hack to End Homelessness UIs:** At a 2014 Seattle hackathon, teams built an intake interface for YouthCare to help place homeless youth in shelters, and an app for on-site data collection by Union Gospel Mission volunteers that was beta-tested the very same night [11].

**Samaritan:** Originally conceived at a hackathon, Samaritan uses small Bluetooth beacons to help city residents learn the stories of and invest in people experiencing homelessness [7] [12]. The platform has enabled 20 unsheltered individuals to navigate to housing or employment through financial resources and newfound relationships [7].

## Scoping Lessons for TF Teams

To ensure weekend MVPs succeed, teams must reuse standards, pick one job, pair with an anchor, and plan the handoff.

* **Leverage standards and OSS:** Do not invent new data formats. Use established standards like the Open Referral Human Services Data Specification (HSDS) and the Ohana API [1], or the Code for America flu-shot spec [3].
* **Secure an institutional owner:** Projects need a champion. The SF Adult Probation Department actively sought to adapt Ohana for their reentry directory [1], and the Philadelphia City Planning Commission co-designed Textizen [4].
* **Constrain to one primary user/job:** Focus on a single, high-value interaction. DiscoverBPS focused on parents choosing schools [6], while the Flu Shot Finder focused purely on locating the nearest clinic [3].
* **Field-test during the weekend:** Get the tool into users' hands immediately. The Union Gospel Mission field data app was beta-tested on Saturday night of the hackathon [11].
* **Add SMS as a default fallback:** SMS reaches vulnerable populations effectively. Textizen [4] and mRelief [5] proved that text messaging drastically lowers barriers to entry for social services.
* **Pre-plan maintenance and governance:** Open Referral notes that complex challenges cannot be solved in a day, and many prototypes rely on dummy data initially [1]. Plan for how the data will be maintained post-event.

## Minimum Credible Demos by MVP Shape

Each project shape has a smallest "trustworthy" slice that can be shipped in 48 hours.

| MVP Shape | Must-Have Features | Data Sources/Format | Proof it Works (Weekend) | Stretch Goal (Post-Event) |
| :--- | :--- | :--- | :--- | :--- |
| **Pathway Guide** (e.g., eligibility) | 3–5 question wizard; top 3 actions; SMS fallback; printable summary | Rules as JSON; public program rules; static content | 5 live user walk-throughs; 1 staff champion quote | Add account save; multi-language support |
| **Data Dashboard** (e.g., flu, capacity) | 1–2 KPIs; last-updated stamp; downloadable CSV; mobile friendly | One public dataset (portal/CSV); cached daily | Stakeholder demo + one operational decision made | Add alerts; cohort filters |
| **Program Directory** (e.g., youth services) | Search + map/list; hours/eligibility; open/closed indicator | HSDS flat CSV; Ohana API; seed 50–200 records | 10 successful lookups in the field; provider confirms accuracy | Add claim/edit functionality; feedback loop |

## Highest-Risk Scope Decisions

Don't invent standards, integrate regulated systems, or build for everyone at once in a 48-hour window.

| Risk | Why it Kills Momentum | Safer Weekend Alternative |
| :--- | :--- | :--- |
| **New data standards / platform plays** | Code for America's initial "student app store" stalled under legal and privacy reviews [6]. | Use existing standards (e.g., Open Referral) and public data [1]. |
| **PHI/PII or EHR integrations** | Privacy and governance delays will block deployment. | Start with public/publishable datasets or dummy data to prove the concept [1]. |
| **Multi-role, multi-tenant admin suites** | Massive time sink that distracts from the core user journey. | Constrain to one user role; defer back-office tooling beyond simple CSV importers. |
| **Real-time capacity tracking** | Requires complex integrations and provider behavior changes. | Use proxy signals or simple open/closed flags first. |
| **Citywide data cleanups** | Too large a scope for a weekend. | Start with one specific provider or region's dataset. |

## Evidence-Backed Patterns and Counterexamples

Pairing successes with cautionary tales makes scoping choices explicit.

* **Success:** DiscoverBPS achieved massive user impact by focusing on public data and transparent rules [2] [6]. **Counter:** Their initial "app store for students" failed due to privacy and legal reviews [6].
* **Success:** Ohana was successfully redeployed across multiple cities in a weekend [1]. **Counter:** Many of these prototypes relied on dummy data and required significant post-event handoffs to achieve real adoption [1].
* **Success:** Textizen achieved rapid pilot adoption by co-designing with the City Planning Commission [4]. **Counter:** It still required a 4-month runway to launch the actual pilot [4].
* **Success:** Sheltr built a functional mobile directory and map in a single weekend [8]. **Counter:** Long-term adoption by providers beyond the initial "agency interest" remains unverified.

## Inferences vs. Knowns

It is critical to be explicit about assumptions versus documented facts.

**Labeled Inferences:**
* *Team Composition:* It is inferred that brigade redeploys of Ohana (like Code for Miami) utilized standard brigade team structures (developers, data analysts, UX designers).
* *Flu Shot Finder Origin:* The weekend viability of the Flu Shot Finder is inferred from its simple scope and alignment with the CfA specification, though its exact hackathon origins are undocumented.

**Documented Facts:**
* Sheltr had a team size of ~7, was built over a weekend, and garnered immediate agency interest [8].
* Ohana weekend prototypes were successfully deployed in Miami, SF, Sacramento, and Raleigh [1].
* DiscoverBPS logged 15,000 users in year one and prompted the creation of a canonical API [2] [6].
* Textizen piloted with Philadelphia City Planning and was later used in NYC participatory budgeting [4] [10].
* Samaritan has engaged ~7,000 residents to support 500 unsheltered people, resulting in 20 early life-changing outcomes [7].

## Unknowns and How to Close Them

A short validation plan resolves the gaps that matter for TF decisions.

* **Sheltr provider adoption and longevity:** Conduct 2–3 stakeholder interviews with the Office of Supportive Housing, Project HOME, or Bethesda Project to determine if the tool was integrated into daily workflows.
* **Flu Shot Finder origin and maintenance:** Contact the dataset owner (Jonathan Levy) to gather build notes and understand the maintenance workflow.
* **Ohana redeploys' sustained usage:** Reach out to Code for Miami or Code for Sacramento maintainers to assess long-term handoff success.
* **Hack to End Homelessness outputs:** Follow up with YouthCare and Union Gospel Mission staff to determine the long-term adoption of the intake and field apps.

## Action Plan for TF Weekend Builds

Pre-wire a standard and an owner, ship one job in 48 hours, then sprint to credibility.

* **Pre-weekend (Week -2 to 0):** Pick the MVP shape and data standard (e.g., HSDS). Secure an institutional owner. Collect seed data (50-200 records). Schedule a field test for the weekend. Define 3 core KPIs.
* **Weekend (Days 1–2):** Build the thin slice. Add SMS fallback via Twilio. Instrument metrics. Run 5–10 field tests with real users. Capture quotes and write a 1-page adoption brief.
* **Post-weekend (Days 3–30):** Fix the top 5 issues identified in field testing. Add a simple data importer. Conduct a governance check. Hold weekly check-ins with the institutional owner. Publish the pilot link and documentation.
* **60/90 days:** Prove outcomes based on the defined KPIs. Document maintenance procedures. Scope v1.1 or execute a formal handoff. Make funding and ownership decisions.

## References

1. *Open Referral all over: hacks at Code Across and Open Data Day – Open Referral*. https://openreferral.org/open-referral-all-over-hacks-at-code-across-and-open-data-day/
2. *Great Starts (Formerly Discover BPS) | Boston.gov*. https://www.boston.gov/departments/new-urban-mechanics/discover-bps
3. *Flu Shot Locations - 2014 - Present | City of Chicago | Data Portal*. https://data.cityofchicago.org/Health-Human-Services/Flu-Shot-Locations-2014-Present/w3hg-pyhz
4. *City of Philadelphia and Code for America launch Textizen - WHYY*. https://whyy.org/articles/city-philadelphia-and-code-america-launch-textizen/
5. *@CivicWhitaker Anthology*. https://hackathon-planning-kit.org/files/civicwhitaker-anthology.pdf
6. *Open Data and the Future of Civic Innovation*. https://beyondtransparency.org/pdf/BeyondTransparency.pdf
7. *20 Chronically Homeless Led to Life-Changing Outcomes Through Good Samaritans | by Jonathan Kumar | Samaritan Journal | Medium*. https://medium.com/samaritan-journal/20-chronically-homeless-led-to-life-changing-outcomes-through-good-samaritans-with-an-app-e2a77626e0a0
8. *Sheltr.org stars at Random Hacks of Kindness Philadelphia [VIDEO]*. https://technical.ly/software-development/sheltr-org-stars-at-random-hacks-of-kindness-philadelphia-video/
9. *Random Hacks 5: What's Going On! afterschool program finder wins*. https://technical.ly/software-development/random-hacks-kindness-5-winner/
10. *Tech & Policy Initiative, Working Paper Series 1*. https://www.sipa.columbia.edu/sites/default/files/2022-09/WorkingPaperSeries_1.pdf
11. *Hack to End Homelessness: Maps, social networks and other ideas to help Seattle's homeless – GeekWire*. https://www.geekwire.com/2014/hack-end-homelessness-recap-maps-social-networks-startup-ideas/
12. *GiveSafe is now Samaritan. I want to let you know about a decision… | by Jonathan Kumar | Samaritan Journal | Medium*. https://medium.com/samaritan-journal/givesafe-is-now-samaritan-a094785297b4