> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Build Safely: Red Flags That Can Derail Richmond’s Thriving Families Tech

## Executive Summary
Civic-tech teams building tools for Richmond’s "Thriving Families" pillar face a complex web of regulatory, legal, and equity constraints. As initiatives like Youth Works RVA scale to serve hundreds of youth [1] and the city deploys $5 million in American Rescue Plan (ARP) funds for maternal and infant health [2], the digital tools supporting these programs must be designed with strict guardrails. 

The most critical risks stem from a misalignment between user demographics and privacy laws. While the Children's Online Privacy Protection Act (COPPA) and the Virginia Consumer Data Protection Act (VCDPA) strictly protect children under 13 [3], Richmond's youth employment programs primarily serve teens aged 14 to 24 [4]. This creates a "compliance gap" where platforms might inadvertently collect sensitive data, track geolocation, or facilitate illegal employment contracts for minors. Furthermore, while HIPAA may not legally apply to consumer health apps [5], providing inaccurate maternal health guidance carries severe clinical and reputational risks. Finally, with broadband adoption in Richmond City at 85% [6] and affordability remaining a primary barrier [7], assuming smartphone and high-speed internet access will systematically exclude the most vulnerable families. 

This report provides a comprehensive risk inventory, specific guardrail language, and an actionable roadmap to safely deploy civic-tech tools in Richmond.

## Why This Risk Inventory Matters Now
Richmond’s Office of Community Wealth Building (OCWB) and the Richmond City Health District (RCHD) are rapidly expanding their services. The Youth Engagement Services (YES) program, formerly the Mayor's Youth Academy, offers multiple tracks for youth aged 14-24, including in-person internships, virtual learning, and leadership development [4]. Simultaneously, the city has allocated $5 million to a Health Equity fund managed by the RCHD to support maternal and infant health [2]. 

As civic-tech teams build platforms to coordinate these services, missteps in data privacy, health advice, and employment facilitation can cause real harm. A platform that inadvertently brokers an illegal shift for a 14-year-old, exposes a teen's precise geolocation, or provides outdated prenatal guidance will not only face legal scrutiny but will permanently lose the trust of Richmond families and city partners.

## Legal and Compliance Landscape You Must Design For
Civic-tech tools operating in Virginia must navigate a strict matrix of state and federal regulations regarding data privacy, health information, and child labor.

### Under-13 Privacy and Virginia's Sensitive Data Triggers
The VCDPA defines a "child" as any natural person younger than 13 years of age [3]. Under this law, personal data collected from a known child is automatically classified as "sensitive data" [3]. Controllers are strictly prohibited from processing a known child's data for targeted advertising, the sale of personal data, or profiling without obtaining verifiable parental consent in accordance with COPPA [3] [8]. Furthermore, the VCDPA prohibits collecting precise geolocation data from a known child unless it is reasonably necessary to provide the service, and even then, the platform must provide a persistent signal indicating that geolocation is being collected [3] [8].

### The 13–17 Teen Compliance Gap
Because COPPA and the VCDPA's strictest protections apply to children under 13 [3], teens aged 13-17 fall into a regulatory gray area. However, since Richmond's YES programs target youth starting at age 14 [4], platforms will heavily index in this demographic. Treating 13-17 year olds as standard adult consumers is a massive risk. Platforms must adopt data minimization norms, disable targeted ads, and restrict geolocation by default for all minors to avoid regulatory scrutiny and maintain trust.

### School Partnerships and FERPA Boundaries
The VCDPA explicitly states it does not apply to personal data subject to the federal Family Educational Rights and Privacy Act (FERPA) [9]. FERPA takes precedence for educational records like grades, attendance, and disciplinary files [9]. If a civic-tech tool integrates with Richmond Public Schools to verify enrollment (a requirement for some YES programs [10]), strict FERPA-compliant data-sharing agreements must be established. Data not subject to FERPA, such as non-educational surveys or app analytics, remains subject to VCDPA rules [9].

### Health Apps and the HIPAA Illusion
Many developers mistakenly assume all health data is protected by the Health Insurance Portability and Accountability Act (HIPAA). However, the U.S. Department of Health and Human Services (HHS) clarifies that an app developer is only a HIPAA business associate if they create, receive, maintain, or transmit protected health information (PHI) on behalf of a covered entity [11] [5]. If a consumer independently selects an app to track maternal health and the developer has no relationship with the user's healthcare provider, the developer is likely not a business associate [5]. While this removes HIPAA compliance burdens, it does not remove the risk of FTC enforcement under the Health Breach Notification Rule or the clinical risk of providing harmful medical advice [12].

### Virginia Youth Labor and Work Certificates
Virginia enforces strict child labor laws that platforms must not inadvertently violate. All 14- and 15-year-old workers in Virginia must obtain an Employment Certificate (work permit) before performing any work [13] [14]. Furthermore, minors under 16 face severe hour restrictions: they cannot work during school hours, are limited to 3 hours on a school day (18 hours per school week), and can only work between 7 a.m. and 7 p.m. (extended to 9 p.m. from June 1 through Labor Day) [15] [14]. Employers must keep time records and employment certificates on-site for three years [14] [16].

## Category-by-Category Risk Inventory

The following table outlines the seven critical risk categories for Thriving Families civic-tech tools, detailing the severity, required guardrails, and potential failure cases.

| Risk Category | Severity | Evidence & Context | Required Guardrails | Potential Failure Case |
| :--- | :--- | :--- | :--- | :--- |
| **1. Minor Privacy & Data Protection** | High | VCDPA treats under-13 data as sensitive; requires parental consent for geolocation, ads, and profiling [3] [8]. | Age-gate all users; require COPPA-grade parental consent for under-13s; disable precise geolocation and targeted ads for all users under 18. | An analytics SDK logs precise location for a 14-year-old user, violating state privacy norms and eroding trust. |
| **2. Unsafe Youth Employment Records** | High | Virginia requires employers of minors under 16 to keep time records and certificates for 3 years [14] [16]. | Do not store "hours worked" or shift logs; purge messaging logs quickly; explicitly state the platform is not a system of record. | A "timesheet" feature on the app is subpoenaed during a wage dispute, creating legal liability for the tech team. |
| **3. Health Claims** | High | HIPAA often excludes consumer apps [5], but ARP funds target maternal health via RCHD [2]. | Label all content as educational; source strictly from VDH/RCHD/CDC/ACOG; provide clear escalation paths to licensed clinicians. | A symptom-checker chatbot provides incorrect prenatal advice, leading to medical harm and severe reputational damage. |
| **4. Employer-Teen Matching** | High | 14-15 year olds require work permits [13]; strict hour limits apply to under-16s [15]. | Act as a navigator to YES programs [4]; block direct in-person job applications for 14-15 year olds; require employer compliance attestations. | A direct-messaging feature is used by an employer to schedule a 15-year-old for an illegal 10 p.m. shift. |
| **5. Data Staleness** | Medium-High | Youth Works applications are strictly timebound (e.g., closing March 31) [1]. | Implement "last updated" timestamps; auto-expire old listings; establish a source-of-truth registry with data owners. | The app displays a closed summer internship, resulting in wasted applications and frustration for low-income families. |
| **6. Digital Equity** | High | Richmond broadband adoption is 85% [6]; affordability is a primary barrier statewide [7]. | Design SMS-based workflows; create low-bandwidth pages; provide offline printables and kiosk access. | An app requiring constant high-speed data excludes mobile-only, low-income youth from accessing city resources. |
| **7. Overclaiming** | High | YES and RCHD are official city entities [4] [2]; civic-tech tools are often third-party. | Use clear non-endorsement statements; attribute sources accurately; only use official validation badges with explicit MOUs. | Users assume the app is an official City of Richmond medical diagnostic tool, leading to over-reliance on its outputs. |

*Key Takeaway*: The highest severity risks involve inadvertently acting as an employer of record, brokering illegal child labor, or providing unauthorized medical advice. Civic-tech tools must strictly position themselves as information navigators, not brokers or clinicians.

## Guardrail Language Library
To mitigate the risks outlined above, integrate the following pre-approved copy blocks directly into the product UI, terms of service, and user communications.

* **Minor Privacy & Data Protection**: "We do not knowingly collect personal information from children under 13 without verifiable parental consent. Teen users aged 13–17 should not share sensitive personal details. This service is not used for targeted advertising, data sales, or profiling. Location features are disabled for youth users."
* **Employment Non-Affiliation**: "This platform is an information and referral tool. It is not an employer, timekeeping system, or system of record for employment-related documentation."
* **Employer-Teen Matching**: "We provide connections to City-vetted programs. We do not facilitate or finalize employment offers. Employers are responsible for obtaining required Employment Certificates and complying with all Virginia child labor laws and hour limits."
* **Medical Disclaimers**: "Information provided is for educational purposes only and is not medical advice. Pregnant and postpartum users should consult a licensed clinician or the Richmond City Health District."
* **Data Freshness**: "Program details and eligibility requirements change frequently. Always confirm details directly with the hosting agency. Last updated: [Timestamp]."
* **Overclaiming/Attribution**: "This site is operated by [Organization Name]. It is not an official publication of the City of Richmond, the Office of Community Wealth Building, or the Richmond City Health District unless explicitly stated."

## Data Governance and Update Discipline
Stale data regarding program availability or maternal health statistics rapidly destroys user trust. Because programs like Youth Works RVA operate on strict seasonal timelines [1], data governance must be automated and rigorous.

### Source Registry and Automated Ingests
Establish a centralized source-of-truth registry that maps every data point to an official owner (e.g., OCWB for youth jobs, RCHD for health data). Where possible, utilize the City of Richmond’s Open Data Portal [17] or scrape official RVA.gov pages to auto-ingest updates. Every piece of programmatic data must feature a visible "Last Updated" UI element.

### Content Provenance and Expiry
Implement default auto-expiry for timebound data. For example, summer internship applications should automatically hide from the user interface at 11:59 PM on the deadline date (e.g., March 31 [1]). Validation badges should only be applied to data that is directly pulled via API from an official city source.

## Safe Employer and Program Integrations
To avoid facilitating illegal child labor, the platform must use programmatic filters and strict partner onboarding protocols.

### Age, Hour, and Season Filters
The platform must automatically filter opportunities based on the user's inputted age. 
* **14-15 Year Olds**: Route exclusively to virtual programs (like the Virtual Earn and Learn Program [4]), Counselors in Training [4], or explicitly vetted roles. Block all roles requiring work during school hours.
* **Under 16**: Hard-code logic to flag or block opportunities that exceed 3 hours on a school day, 18 hours in a school week, or require work past 7 p.m. (or 9 p.m. in summer) [15] [14].

### Partner Attestations
Before an employer can list an opportunity, they must digitally sign an attestation confirming they understand Virginia Code §40.1-84 to 96 [14]. They must agree to obtain the Employer Intent to Employ form, verify the minor's Employment Certificate, and maintain accurate time records on-site [14] [16].

## Health Content Safety System
Maternal health content must be treated as a living clinical asset. Incorrect information regarding prenatal care or postpartum resources can lead to severe health outcomes.

### Clinical Sourcing and Review Cadences
Never generate original medical advice. All maternal health content must be whitelisted and sourced directly from the Virginia Department of Health (VDH), the Richmond City Health District (RCHD), the CDC, or the American College of Obstetricians and Gynecologists (ACOG). Establish a quarterly clinical review cadence to ensure links to RCHD resources (funded by the $5M ARP allocation [2]) remain active and accurate.

### Escalation Paths
Design the UI to push users toward human, clinical help. If a user searches for symptoms or urgent care, the platform must immediately trigger an escalation pattern: "Call your clinician or contact the Richmond City Health District at [Phone Number]."

## Digital Equity-by-Design
Virginia's Digital Opportunity Plan identifies affordability as a primary barrier to digital equity [7]. With 15% of Richmond City lacking broadband access [6] and federal digital equity funding facing suspensions [7], civic-tech tools cannot rely solely on high-bandwidth mobile apps.

To reach mobile-only youth and low-income families, the platform must offer multi-channel delivery. This includes SMS/USSD workflows for basic program queries, low-bandwidth HTML pages that load quickly on throttled data plans, and offline printables that can be distributed at Richmond community centers (such as the T.B. Smith or Southside Community Centers funded by ARP [2]). Success metrics must track completion rates by connectivity tier to ensure the platform isn't systematically excluding the most vulnerable residents.

## Implementation Roadmap

| Phase | Timeframe | Key Actions |
| :--- | :--- | :--- |
| **Phase 1: Foundation & Safety** | 0–30 Days | Implement age-gating; deploy guardrail copy library; disable precise geolocation and targeted ads for all users under 18; establish data source whitelist. |
| **Phase 2: Integration & Filtering** | 31–60 Days | Build referral integrations to YES programs [4]; implement automated age/hour eligibility filters based on Virginia law [15]; launch SMS MVP for low-bandwidth users. |
| **Phase 3: Governance & Equity** | 61–90 Days | Establish quarterly clinical review cadence for maternal health data; automate content expiry; track equity metrics (channel mix, completion rates). |

## Unknowns and Assumptions

### Unknowns to Clarify with City Partners
* **Formal Endorsement Status**: Does the civic-tech team have a formal MOU with the Office of Community Wealth Building or the Richmond City Health District that allows the use of official city logos?
* **Data-Sharing Agreements**: If the tool verifies school enrollment for YES eligibility [10], is there an active FERPA-compliant data-sharing agreement with Richmond Public Schools?
* **Open Data Terms**: Are there specific legal encumbrances or disclaimers required when utilizing the Richmond Open Data Portal [17] beyond standard attribution?
* **Employer Vetting**: What are the exact background-check standards YES uses for its employer partners, and must the civic-tech tool replicate them?

### Inferences (Explicitly Labeled)
* *Inference*: The safest, highest-trust path is to route youth employment through the official YES infrastructure and maternal content through the RCHD, using the civic-tech tool strictly as a navigator rather than a broker or a clinician.
* *Inference*: Because the VCDPA strictly regulates geolocation for children under 13 [3], and distinguishing a 12-year-old from a 14-year-old digitally is prone to error, under-18 precise geolocation should be disabled by default to eliminate legal exposure.

## References

1. *Youth Works RVA: Summer 2026 Applications Now Open! | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/news/youth-works-rva-summer-2026
2. *American Rescue Plan | Richmond*. https://www.rva.gov/arp
3. *Code of Virginia Code - Chapter 53. Consumer Data Protection Act*. https://law.lis.virginia.gov/vacodefull/title59.1/chapter53/
4. *Youth Engagement Services | Richmond*. https://www.rva.gov/community-wealth-building/youth-engagement-services
5. *HHS Releases Guidance on Health Apps and HIPAA Security Rule Crosswalk*. https://www.hunton.com/privacy-and-cybersecurity-law-blog/hhs-releases-guidance-on-health-apps-and-hipaa-security-rule-crosswalk
6. *Broadband Table for Virginia Counties | HDPulse Data Portal*. https://hdpulse.nimhd.nih.gov/data-portal/_physical/broadband/table?demo=235&statefips=51
7. *Beyond Access: Broadband Affordability & Adoption*. https://dls.virginia.gov/commissions/jcots/materials/broadband_report_nov_2025.pdf
8. *Heightened Privacy Protections for Children in Virginia | Davis Wright Tremaine*. https://www.dwt.com/blogs/privacy--security-law-blog/2024/05/virginia-data-privacy-law-amended-for-under-18
9. *All About the Virginia Consumer Data Protection Act for K–12 Districts*. https://www.cybernut.com/blog/all-about-the-virginia-consumer-data-protection-act-for-k12-districts
10. *FAQ | Richmond*. https://www.rva.gov/community-wealth-building/faq
11. *The access right, health apps, & APIs | HHS.gov*. https://www.hhs.gov/hipaa/for-professionals/privacy/guidance/access-right-health-apps-apis/index.html
12. *Resources for Mobile Health Apps Developers | HHS.gov*. https://www.hhs.gov/hipaa/for-professionals/special-topics/health-apps/index.html
13. *DOLI – Virginia Department of Labor and Industry  - Youth Employment*. https://doli.virginia.gov/programs/labor-law/youth-employment/
14. *
		Virginia Child Labor Laws for Teens 14-and 15-years Old	*. https://premieraquatics.com/news/view/virginia_child_labor_laws_teens_14_15_years_old
15. *Chapter 40. Virginia Hours of Work for Minors*. https://law.lis.virginia.gov/admincodefull/title16/agency15/chapter40/
16. *§ 40.1-81.1. Records to be kept by employers*. https://law.lis.virginia.gov/vacode/title40.1/chapter5/section40.1-81.1/
17. *Open Data Portal | Richmond*. https://www.rva.gov/information-technology/open-data-portal