# Winning Civic-Tech Demos: A Credibility Playbook for Public Health and Youth-Services Judges

## Executive Summary
In civic-tech hackathons judged by public health and youth-services experts, credibility is a visible system of choices, not just a slick prototype. Domain experts evaluate demos through the lens of ethical responsibility, data rigor, and user safety. This playbook translates public health frameworks and open-data compliance standards into actionable presentation strategies. 

**Key Strategic Insights:**
* **Show sources early and disclaim endorsement:** Open data portals explicitly forbid implying official government status [1] [2]. Placing a one-line source and a "not official" disclaimer directly on every chart builds immediate trust and complies with U.S. Census data visualization guidelines [3].
* **Under-claiming beats over-claiming:** In public health, overselling limitations damages credibility permanently [4]. Adopting language from epidemiological reporting standards (like STROBE) signals rigor [5] [6].
* **Data readiness is judged by surveillance attributes:** Public health judges evaluate data using CDC surveillance system attributes, specifically looking for completeness, timeliness, and representativeness [7] [8]. Quantifying these in your demo proves you understand the data's real-world utility.
* **Accessibility is a fast trust win:** Demonstrating WCAG 2.2 compliance [9] [10] and colorblind-friendly palettes [3] proves you respect marginalized end-users, a critical metric in ethical tech rubrics [11].
* **Structure the pitch to hit rubric dimensions:** With pitches often limited to 3 minutes [12], allocating specific time blocks to address the problem, product, SMART objectives [13], and operating environment ensures no scoring category is left blank.

## Source Transparency That Stands Up to Scrutiny
When presenting to domain experts, how you cite your data is as important as the data itself. Open data portals require strict attribution and explicitly prohibit derivative works from masquerading as official government publications. 

### What to Show, Where, and When
The U.S. Census Bureau recommends that for stand-alone visuals or presentations, the full citation should be included directly on the visual itself [3]. Do not wait until a final "References" slide to reveal your sources. Furthermore, portals like the California Health and Human Services (CalHHS) Open Data Portal mandate that users "may not claim the data is 'official government data'" [1], and the City of Houston requires a specific disclaimer stating the city "makes no claims as to the content, accuracy, timeliness, or completeness of the data" [2].

### Table: Data Type vs. On-Screen Citation vs. Required Disclaimers
| Data Type | Example Source | On-Screen Citation Text | Disclaimer Text (Verbatim/Condensed) |
| :--- | :--- | :--- | :--- |
| **Aggregate Surveillance** | CalHHS Portal | "Source: CalHHS Open Data, 2019–2024" | "Not official government data; derivative work." [1] |
| **City Program Data** | Houston Open Data | "Source: City of Houston Open Data, 2023" | "No endorsement; accuracy not guaranteed." [2] |
| **Federal Statistics** | U.S. Census Bureau | "Source: ACS 2019–2023 5-yr" | "See methodology/SE: [link]" [3] |

*Takeaway:* Embed these citations and disclaimers directly into the footer of your demo UI or presentation slides. This preempts judges' concerns about data provenance and legal compliance.

## Curated vs. Official Content
Misrepresenting curated content as an official government tool is a fatal credibility error. The CDC explicitly states it is not responsible for confidentiality or information shared by users on third-party devices [14]. 

### UI Patterns for Non-Endorsement
To prevent misrepresentation in your UI and narration:
* **Badge Curated Content:** Add a persistent UI badge stating, "Curated from [Portal], not an official publication."
* **About Modal:** Include an "About" modal in your prototype that houses the full terms of use snippets from your data sources.
* **Verbal Framing:** Before showing government branding or logos, verbally state: *"Using publicly available data from X, we built this independent prototype..."*

## 3–5 Minute Pitch Architecture Mapped to Rubric Dimensions
Hackathon pitches are notoriously brief. The Harvard Health Systems Innovation Lab Hackathon restricts pitches to exactly 3 minutes [12]. To maximize impact, you must map your narrative directly to the judging rubric, which typically weights presentation, storytelling, and explainability heavily (up to 40% combined in some ethical AI rubrics) [11].

### Timeboxed Script (3-Minute Model)
* **0:00–0:10 (Introduction):** Briefly introduce the team and role [12].
* **0:10–0:30 (Problem Statement):** Clearly describe the problem, the root causes, and whose lives will be improved [12].
* **0:30–1:30 (Product Demo):** Explain the technical aspects and showcase the live demo [12].
* **1:30–2:00 (Data Readiness & Uncertainty):** Address data sources, completeness, and limitations.
* **2:00–2:30 (Impact & SMART Metrics):** Define success using SMART objectives [13].
* **2:30–3:00 (Champion, Environment & Accessibility):** Name the community partner, operating constraints, and accessibility features.

### Table: Rubric Dimension Mapping and Evidence
| Rubric Dimension | What to Show in 1–2 Sentences | Evidence to Prep | Time Allocation |
| :--- | :--- | :--- | :--- |
| **Clarity / Problem** | One-sentence problem and tangible impact [12]. | Problem statistic with cited source. | 20s |
| **Scope** | What is in/out of scope for this weekend's build. | Backlog showing "won't do" items. | 10s |
| **Data Readiness** | Completeness %, update cadence, representativeness [8]. | Data profile, % of blank responses [7]. | 20–30s |
| **Champion / Partner** | Named title of community partner or end-user [15]. | Slide with partner logo (with disclaimer). | 15s |
| **Population** | Who benefits and where, addressing marginalized groups [11]. | Demographic/need statistic (Census/CDC). | 10–15s |
| **Operating Environment** | Constraints designed for (e.g., low bandwidth). | Offline mode toggle or low-tech fallback. | 15–20s |
| **Success Criteria** | 2–3 SMART objectives [13]. | Metrics with specific timeframes. | 20–30s |
| **Accessibility** | WCAG-informed choices and inclusive design [16]. | High-contrast mode, captions. | 15–20s |

*Takeaway:* Rehearse this flow meticulously. Judges score based on what they hear; if you run out of time before mentioning your community champion or accessibility features, you score a zero in those dimensions.

## Data Readiness & Uncertainty, the Public Health Way
Public health judges evaluate data through the lens of surveillance system evaluation frameworks. The CDC assesses systems based on attributes including simplicity, flexibility, data quality, acceptability, sensitivity, predictive value positive, representativeness, timeliness, and stability [7] [17]. 

### "Data Readiness" Micro-Panel
Instead of just saying "we used CDC data," include a "Data Readiness" micro-panel in your presentation that quantifies:
* **Completeness:** The frequency of unknown or blank responses to data items [8]. (e.g., "92% completeness on key demographic fields").
* **Timeliness:** How quickly reports are received and updated [18].
* **Representativeness:** Whether the system accurately describes the distribution of cases by time, place, and person [8]. Acknowledge if the data is only from a sentinel system.

### Visualizing Uncertainty
The European Food Safety Authority (EFSA) recommends a pluralistic approach to communicating uncertainty, as no single representation suits all audiences [19]. 
* Use **box plots** to represent probability distributions and ranges, as they are generally better understood than complex cumulative distribution functions [19].
* Accompany numerical uncertainty with simple, plain-language text explaining the basis for the probability [19].

## Accessibility That's Visible in 30 Seconds
Accessibility addresses disparities and ensures inclusivity, a core judging criterion in public health hackathons [16]. Furthermore, the U.S. Census Bureau warns that a percentage of the population cannot distinguish between certain colors (commonly red and green), making colorblind-friendly palettes mandatory for functional visuals [3].

### Table: Accessibility Quick Checks for Demos
| Check | How to Show it Live | Tool / Standard |
| :--- | :--- | :--- |
| **Color Contrast** | Toggle dark mode or high-contrast theme during demo. | WCAG 2.2 Quick Reference [9] |
| **Colorblind Safety** | Point out the avoidance of red/green reliance. | Census Data Viz Guidelines [3] |
| **Keyboard Navigation** | Navigate a core user flow using only the keyboard. | WCAG Operable Guidelines [10] |
| **Explainability** | Show how users can follow the logic behind AI/data outputs. | CGU Ethical AI Rubric [11] |

*Takeaway:* Explicitly stating "This demo is informed by WCAG 2.2 guidelines" signals deep product maturity and care for vulnerable populations.

## Language Patterns Bank: Signaling Rigor Over Hype
Incomplete and inadequate reporting hampers the assessment of strengths and weaknesses in medical literature [5] [6]. The same applies to hackathon pitches. Using causal language when you only have observational data destroys credibility with scientific judges.

### Table: Say-This / Not-That for Demos
| Situation | Credible Phrasing (Say This) | Risky Phrasing (Avoid) | Why it Matters |
| :--- | :--- | :--- | :--- |
| **Observational Data** | "is associated with," "is consistent with" | "causes," "proves," "solves" | Aligns with STROBE/CONSORT norms for observational studies [5] [6]. |
| **Product Status** | "prototype," "alpha," "pilot-ready" | "production-ready," "deployable now" | Honesty about limitations increases credibility; overselling damages it [4]. |
| **Data Coverage** | "Based on 2019–2023 data for County X" | "Real-time," "Statewide" (if untrue) | Accurately reflects representativeness and timeliness [8]. |
| **User Privacy** | "Aggregated, de-identified data" | "Anonymous data" | Acknowledges the complexity of true anonymization in youth data [20] [21]. |

## Hard Question Preparation Guide
During the Q&A, judges will test the boundaries of your knowledge. The Trier Social Stress Test proves that public speaking and impassive panels induce high stress [22]. Preparation is your best defense. Acknowledging what your product *doesn't* do builds trust with investors and partners [4].

### Table: Tough Questions and Response Patterns
| Tough Question | Best Response Pattern | Proof to Have Ready |
| :--- | :--- | :--- |
| **"Isn't this misleading without [missing data]?"** | "You're right, it is incomplete regarding X. We measure completeness at Y% [8], label the representativeness, and plan to mitigate this by..." | Data profile showing % of blank responses [7]. |
| **"How will you protect youth privacy?"** | "We avoid PII entirely, use only aggregated data, and align with Responsible Data for Children (RD4C) principles [21]." | Architecture diagram showing data flow and lack of PII storage. |
| **"What if your algorithm/data is wrong?"** | "Here is our uncertainty band using a box plot [19]. Even at the lower bound, the decision improves because..." | EFSA-style uncertainty visualization [19]. |
| **"Can this actually scale?"** | "We are scoping a pilot with [Champion]. Our SMART objectives [13] for the next 6 months are strictly bounded to..." | Letter of Intent (LoI) or quote from community partner. |

## Risks, Trade-offs, and Failure Modes
The CDC notes that efforts to improve one system attribute (like sensitivity) might detract from another (like simplicity or timeliness) [7]. 
* **Failure Mode:** Claiming your tool is both 100% comprehensive and perfectly real-time. 
* **Mitigation:** Explicitly name your trade-off. *"We prioritized data completeness over real-time timeliness, meaning our dashboard operates on a 48-hour delay, which our community partner confirmed fits their workflow."*

## Credibility-Building Checklist for the Demo
Use this checklist in the final hours of the hackathon to ensure all credibility markers are in place:

1. [ ] **Source Citations:** One-line source citations are visible on every chart/map [3].
2. [ ] **Disclaimers:** "Not official government data" disclaimer is present in the UI footer [1].
3. [ ] **Data Readiness Stats:** Completeness (% blanks) and timeliness metrics are calculated and ready to share [8].
4. [ ] **Accessibility Check:** Color palette is colorblind-safe [3]; high-contrast mode is functional.
5. [ ] **Language Check:** All instances of "proves" or "causes" are changed to "suggests" or "is associated with" [5].
6. [ ] **SMART Objectives:** Success criteria are Specific, Measurable, Achievable, Realistic, and Time-phased [13].
7. [ ] **Uncertainty Viz:** Box plots or clear ranges are used instead of single, overly-precise data points [19].
8. [ ] **Youth Privacy:** Explicit verbal confirmation that no PII is collected or stored [20].
9. [ ] **Champion Named:** Community partner or specific end-user persona is explicitly named in the pitch [15].
10. [ ] **Timing Rehearsal:** Pitch is strictly timed to hit all rubric dimensions within the 3-5 minute limit [12].

## Inferences
* **Inference on Rubric Mapping:** We infer that CDC surveillance attributes (timeliness, completeness, representativeness) map perfectly to the "data readiness" and "technical execution" scoring criteria found in standard civic/public-health hackathons.
* **Inference on Presentation Weight:** Based on the CGU Ethical AI rubric (20% presentation) and Harvard's strict 3-minute structure, we infer that presentation flow and storytelling carry equal weight to technical execution in domain-expert judging.
* **Inference on SMARTIE:** While the CDC formally uses SMART objectives, we infer that in youth services and civic tech, extending this to SMARTIE (adding Inclusive and Equitable) will score higher on "Socially Responsible Impact" dimensions.

## Unknowns
* **Specific Local Privacy Laws:** The exact data privacy constraints (e.g., state-level youth data protection laws beyond general UNICEF/RD4C guidelines) are unknown and vary by jurisdiction.
* **Exact Rubric Weights:** While we know the dimensions, the exact percentage weight given to "Impact" vs. "Technical Execution" varies by specific hackathon organizers.
* **Live Demo Connectivity:** The operating environment of the presentation stage (Wi-Fi stability) is unknown, making offline-capable demos a necessary fallback.

## References

1. *CalHHS Open Data Portal Terms of Use - California Health and Human Services Open Data Portal*. https://data.chhs.ca.gov/pages/terms
2. *City of Houston Open Data Portal – Terms of Use - City of Houston Open Data*. https://data.houstontx.gov/pages/terms-of-use
3. *Data Visualization*. https://www.census.gov/content/dam/Census/library/working-papers/2017/demo/communicating-with-census-data-data-visualization.pdf
4. *What is honesty about product limitations and why does it increase credibility? | Opagio FAQ*. https://opag.io/intangibles/faq/honest-product-limitations-credibility
5. *STROBE - Strengthening the reporting of observational studies in epidemiology*. https://www.strobe-statement.org/
6. *The Strengthening the Reporting of Observational Studies in Epidemiology (STROBE) Statement: guidelines for reporting observational studies | EQUATOR Network*. https://www.equator-network.org/reporting-guidelines/strobe/
7. *Updated Guidelines for Evaluating Public Health Surveillance Systems*. https://www.cdc.gov/mmwr/preview/mmwrhtml/rr5013a1.htm
8. *Framework for Evaluating Public Health Surveillance ...*. https://www.cdc.gov/mmwr/pdf/rr/rr5305.pdf
9. *How to Meet WCAG (Quickref Reference)*. https://www.w3.org/WAI/WCAG22/quickref
10. *Web Content Accessibility Guidelines (WCAG) 2.2*. https://www.w3.org/TR/WCAG22
11. *JUDGING RUBRIC - Ethical AI Hackathon*. https://research.cgu.edu/hackathon/home/judging-rubric/
12. *Harvard Health Systems Innovation Lab 2026 Hackathon ...*. https://hsph.harvard.edu/wp-content/uploads/2025/10/Participants-guide.pdf
13. *Evaluation Briefs - Writing SMART Objectives*. https://www.cdc.gov/healthy-youth/funded-programs/pdf/brief3b.pdf
14. *Website Disclaimers | Other | CDC*. https://www.cdc.gov/other/disclaimer.html
15. *CIVIC TECH INITIATIVES:*. http://ncoc.org/wp-content/uploads/2016/09/KidsCountToolkit_FINAL.pdf
16. *RE-AIM Public Health IDEAS Hackathon 2025-26*. https://www.memphis.edu/publichealth/initiatives/ph-hackathon/2025-26.php
17. *Updated Guidelines for Evaluating Public Health ...*. https://www.cdc.gov/mmwr/pdf/rr/rr5013.pdf
18. *Introduction to Public Health Surveillance*. https://www.cdc.gov/training-publichealth101/media/pdfs/introduction-to-surveillance.pdf
19. *
            Guidance on Communication of Uncertainty in Scientific Assessments - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC7292191/
20. *PRIVACY, PROTECTION OF PERSONAL INFORMATION ...*. https://www.unicef.org/childrightsandbusiness/media/281/file/UNICEF-CRB-Digital-World-Series-Privacy.pdf
21. *RESPONSIBLE DATA FOR CHILDREN*. https://thegovlab.org/static/files/publications/rd4c-report.pdf
22. *How to Nail the Q&A After Your Presentation*. https://hbr.org/2020/01/how-to-nail-the-qa-after-your-presentation