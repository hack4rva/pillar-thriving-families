# Thriving Families Hackathon: Avoiding Regulatory Tripwires with Safer Builds

## Executive Summary
The central problem of software is that anything can be built, but in the civic technology space, building the wrong thing can create massive legal liability and public harm [1]. For the "Thriving Families" hackathon, the fastest path to impact is avoiding regulated functions and focusing on navigation, education, and logistics that help families act safely. 

Hackathon teams often gravitate toward "solving" complex legal, medical, or eligibility problems through automation. However, these areas are heavily regulated by federal and state laws. Misinterpreting youth labor laws, collecting data from minors, acting as an unauthorized consumer reporting agency, or dispensing unregulated medical advice can trigger severe penalties and erode public trust. This guide outlines exactly what teams should **not** build, the regulatory tripwires hidden in common hackathon ideas, and the safer, high-impact alternatives that meet the same underlying user needs without the risk.

## Regulatory Risk Map for Common Hackathon Ideas
Seven recurring idea types create outsized legal and ethical risks for civic tech teams. Understanding the governing rules is the first step in avoiding them.

| Idea Type (Example) | Governing Rule(s) | What Triggers Regulation | Consequence if Wrong |
| :--- | :--- | :--- | :--- |
| **Youth job compliance calculators** | FLSA child labor provisions + state laws [2] | Occupational/hour judgments | Illegal youth work; liability for violations |
| **Minors' accounts/PII** | COPPA [3]; FTC 2026 age verification policy [4] | Under-13 data collection | COPPA enforcement penalties |
| **Employer "certification"** | Fair Credit Reporting Act (FCRA) [5] | Reports used for employment eligibility | FCRA duties; defamation claims |
| **City-branded apps** | NYC Admin Code § 2-102 [6]; COIB Rule § 1-18 [7] | Seal/title use; implied endorsement | Sanctions; fines; public confusion |
| **Maternal clinical advice** | FDA mobile apps [8]; Clinical Decision Support [9] | Patient/caregiver recommendations | FDA device oversight and scrutiny |
| **Eligibility "deciders"** | Benefits/Marketplace policies [10] [11] | Determination claims | Misrepresentation; legal complaints |
| **Private data dependencies** | 7 CFR 272.1 [12]; 20 CFR Part 603 [13]; FERPA [14]; HIPAA [15] | Access to restricted datasets | Unlawful access; project stalls |

*Key Takeaway: If a proposed feature touches any of the triggers listed above, the team must pivot to a safer alternative to remain viable.*

## Do-Not-Build List with Harms and Safer Alternatives
For every risky build, there is a safer way to meet the same user need. Teams should use this definitive list to scope their projects safely.

| Do Not Build | Harm / Failure Mode | Safer Alternative |
| :--- | :--- | :--- |
| **Youth labor "eligibility" tools** (e.g., "Can a 15-year-old take Job X?") | Misstates job/hour legality, leading to child labor violations. Federal and state laws vary significantly [2]. | Build navigation to official resources (YouthRules.gov) and route users to DOL/WHD opinion request channels or local job centers [16]. |
| **Minors' PII stores** (e.g., youth profiles or accounts) | COPPA consent failures and data breaches. COPPA requires verifiable parental consent before collecting personal info from children under 13 [4]. | Design no-login, no-PII tools. If age-gating is needed, use third-party age verification that stores nothing else [4]. |
| **Employer "verified" badges or vetting systems** | Triggers FCRA duties. Background screening reports are "consumer reports" under the FCRA when they serve as a factor in determining employment eligibility [5]. | Publish neutral checklists on spotting red flags. Link to official wage theft resources. Prohibit employment-use of ratings in terms of service. |
| **City-endorsed branding** (e.g., using the NYC seal or implying official status) | Unauthorized use of the City seal is prohibited and can result in fines [6]. Implied endorsement causes public confusion. | Use independent branding. Include a prominent "Not affiliated with or endorsed by the City of New York" disclaimer. |
| **Maternal clinical recommenders** (e.g., triage bots or dosage calculators) | Software providing treatment/diagnosis recommendations to patients may be a regulated medical device, posing severe safety risks [8] [9]. | Build resource navigators, appointment/transport helpers, and general wellness education with clear "not medical advice" language. |
| **Eligibility determiners** (e.g., "You are eligible for Medicaid/SNAP") | Denied applicants blame the tool, leading to legal complaints and reputational damage. | Offer pre-screeners that return "may be eligible" results, cite sources, and deep link to the agency's official application [11] [17]. |
| **Apps depending on SNAP/UI/FERPA/PHI feeds** | Project stalls due to unavailable data, or worse, unlawful access. These datasets are strictly confidential by law [14] [12] [13]. | Use public/open data, user-held documents, or consent-based uploads stored locally on the user's device. |

*Key Takeaway: The most successful civic tech projects often avoid building complex backend logic entirely, focusing instead on user-centric wayfinding and service navigation [1].*

## Youth Employment: Safe Boundaries and Useful Features
Legal judgments in youth employment are not "hackathon-able." The U.S. Department of Labor (DOL) enforces strict limits on the hours 14- and 15-year-olds can work and the types of jobs they can do, while 16- and 17-year-olds are barred from hazardous occupations [2]. Furthermore, employers must comply with both federal and state laws, which often differ [2]. 

**What to avoid:** Do not publish "fast-follow" legal checklists as if they are authoritative for every state, and do not build calculators that auto-approve youth for specific jobs. 
**What to build:** Point to official guidance. Build dynamic "find your state rule" links to official sources. Preface all information with "this is not legal advice" and prompt users to contact the Wage and Hour Division (WHD) at 1-866-487-9243 or visit local American Job Centers [2] [16].

## Minors' Data and Privacy-by-Design
Collecting minors' personal data triggers the Children's Online Privacy Protection Rule (COPPA), which requires operators to obtain verifiable parental consent before collecting, using, or disclosing personal information from a child under 13 [4]. While a February 2026 FTC policy statement announced a relaxed enforcement approach for data collected *solely* for determining a user's age via age verification technologies, this does not exempt broader data collection [4]. 

Furthermore, if your app handles health information but is not a HIPAA-covered entity or business associate, the data is not protected by HIPAA [15]. However, you may still be subject to the FTC's Health Breach Notification Rule [18].
**What to build:** Data minimization must be the default. Use no-account architectures, device-only local storage, and ephemeral sessions. If age-gating is required, use a third-party service limited strictly to that purpose [4].

## Employer Information Without FCRA Exposure
If your tool rates, vets, or "certifies" employers, and employers or intermediaries use that information to determine a person's eligibility for employment, your platform may be classified as a consumer reporting agency under the Fair Credit Reporting Act (FCRA) [5]. This triggers strict legal duties regarding consent, accuracy standards, and adverse action notices.
**What to build:** Provide process knowledge, not ratings. Offer educational content on how to spot workplace red flags, how to file complaints, and where to find union information. Ensure your Terms of Service explicitly forbid the use of any user-generated content for employment eligibility decisions.

## Branding and Endorsement Controls
City endorsement is tightly controlled. The New York City Administrative Code § 2-102 mandates that the City seal be used only for requisite purposes by authorized officers; unauthorized representations are strictly prohibited, and misuse on vehicles can even result in fines or imprisonment [6] [19]. Additionally, Conflicts of Interest Board (COIB) Rule § 1-18 requires written approval from an agency head before a public servant's City title or agency can be used in promotional materials for non-City products [7].
**What to build:** Stay clearly independent. Never use the City seal, official flag, or look-alike branding. Include a prominent disclaimer: *"Not affiliated with or endorsed by the City of New York."*

## Maternal and Child Health Content Boundaries
Maternal health "advice" easily crosses into regulated medical device territory. The FDA regulates software functions that meet the definition of a medical device, specifically those whose functionality could pose a risk to a patient's safety if the device fails to function as intended [8]. While some Clinical Decision Support (CDS) software is excluded from device definitions, software intended to provide treatment or diagnosis recommendations directly to patients or caregivers remains under FDA oversight [9] [20].
**What to build:** Focus on education and navigation. Build community doula directories, transportation schedulers, and "general wellness" education. Always include prominent "not medical advice—seek emergency care" language and establish a strict QA protocol for sourcing medical content.

## Benefits Screening That Builds Trust
Eligibility "determination" tools create liability and false expectations. Official government portals carefully frame their screeners to avoid making definitive claims. For example, the USA.gov Benefit Finder states it provides a "customized list of potential government benefits you may be eligible for" [11] [17], and Healthcare.gov tells users to check if they "might be able to get or change health coverage" [10].
**What to build:** Phrase carefully and hand off cleanly. Use language like "might qualify" or "may be eligible." Never tell a user "You are eligible." Display source links, never store sensitive financial data, and deep-link directly to the official agency applications.

## Data Access Reality Check and Alternatives
Many datasets that hackathon teams covet are legally sealed. Planning a product around the assumption that you will get access to this data is a guaranteed failure mode.

| Data Sought | Governing Rule | Access Constraint | Safe Alternative |
| :--- | :--- | :--- | :--- |
| **SNAP case files** | 7 CFR 272.1(c) [12] | Strict disclosure limits; withheld from public | User-upload proofs; agency linkouts |
| **UI wage records** | 20 CFR Part 603; UIPL 20-15 [13] | Public officials only; strict safeguards | Self-reported wages; job center verification |
| **Student rosters** | FERPA 34 CFR Part 99 [14] | Consent required; limited exceptions | Parent-provided info; school portals |
| **PHI/EHR feeds** | HIPAA [15] | Covered entity/Business Associate only | Patient-directed share into user's device; no central storage |

## Gray-Zone Decision Framework
Use this 5-question screen to kill bad ideas early. If the answer to any of these is "Yes," the team must pivot:
1. Does it render legal or clinical judgments?
2. Does it collect personally identifiable information (PII) from minors?
3. Does it imply official City endorsement or use official insignia?
4. Does it claim to make final eligibility determinations?
5. Does it depend on restricted, confidential data feeds?

## Implementation Checklist
Embed compliance by design using this lightweight 10-step lifecycle:
1. **Problem validation:** Are users already trying to do this? [1]
2. **Risk screen:** Run the 5-question Gray-Zone framework.
3. **Data minimization plan:** Default to no-login, local-storage architectures.
4. **Content sourcing:** Link to official.gov resources.
5. **Disclaimers:** Draft non-affiliation and non-medical/non-legal advice banners.
6. **Accessibility:** Ensure multi-lingual support and screen-reader compatibility.
7. **Legal review touchpoint:** Have mentors review disclaimers.
8. **QA:** Test that no definitive eligibility claims are made.
9. **User testing:** Verify users understand the tool is a guide, not an authority.
10. **Analytics:** Measure navigation success (clicks to official sites), not outcomes you cannot control.

## Inferences and Unknowns

**Inferences (Assumptions made in this strategy):**
* Projects will not have official City co-hosting, legal review, or formal endorsement at launch, necessitating strict independent branding.
* Hackathon teams lack dedicated legal counsel for FLSA, FDA CDS, or FCRA compliance, making a highly conservative scope prudent.
* Target users for "Thriving Families" include minors, meaning COPPA-safe design must be the default architecture.

**Unknowns (Areas requiring clarification from organizers):**
* Are there any City-approved branding kits, "civic tech" badges, or endorsement pathways available for winning teams?
* Are there any officially sanctioned APIs or open datasets specifically provisioned for this hackathon regarding benefits navigation?
* What are the sponsor expectations for data retention and hosting environments post-hackathon?
* Will City legal representatives be available to review team disclaimers prior to Demo Day?

## References

1. *
		Don't Build It. A Guide for Practitioners in Civic Tech - MIT GOV/LAB | MIT GOV/LAB	*. https://mitgovlab.org/resources/dont-build-it-a-guide-for-practitioners-in-civic-tech/
2. *Youth Employment Compliance Assistance Toolkit | U.S. Department of Labor*. https://www.dol.gov/agencies/whd/compliance-assistance/toolkits/youth-employment
3. *Children's Online Privacy Protection Rule ("COPPA") | Federal Trade Commission*. https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa
4. *FTC Issues COPPA Policy Statement to Incentivize the Use of Age Verification Technologies to Protect Children Online | Federal Trade Commission*. https://www.ftc.gov/news-events/news/press-releases/2026/02/ftc-issues-coppa-policy-statement-incentivize-use-age-verification-technologies-protect-children
5. *What Employment Background Screening Companies ...*. https://www.ftc.gov/business-guidance/resources/what-employment-background-screening-companies-need-know-about-fair-credit-reporting-act
6. *§ 2-102 City seal.*. https://codelibrary.amlegal.com/codes/newyorkcity/latest/NYCadmin/0-0-0-65
7. *§ 1-18 Use of City Title in Promotional Materials.*. https://codelibrary.amlegal.com/codes/newyorkcity/latest/NYCrules/0-0-0-126769
8. *Policy for Device Software Functions and Mobile Medical Applications | FDA*. https://www.fda.gov/regulatory-information/search-fda-guidance-documents/policy-device-software-functions-and-mobile-medical-applications
9. *Clinical Decision Support Software - Guidance*. https://www.fda.gov/regulatory-information/search-fda-guidance-documents/clinical-decision-support-software
10. *Find out if you can get health coverage now*. https://www.healthcare.gov/screener/
11. *Find government benefits and financial help | USAGov*. https://www.usa.gov/benefit-finder
12. *
    eCFR :: 7 CFR 272.1 -- General terms and conditions.
  *. https://www.ecfr.gov/current/title-7/subtitle-B/chapter-II/subchapter-C/part-272/section-272.1
13. *UIPL_20-15_Acc.pdf | U.S. Department of Labor*. https://www.dol.gov/node/160209
14. *FERPA - Protecting Student Privacy - Department of Education*. https://studentprivacy.ed.gov/ferpa
15. *The access right, health apps, & APIs | HHS.gov*. https://www.hhs.gov/hipaa/for-professionals/privacy/guidance/access-right-health-apps-apis/index.html
16. *Youth & Young Worker Employment | U.S. Department of Labor*. https://www.dol.gov/general/topic/youthlabor
17. *GovBenefits.gov becomes Benefits.gov | U.S. Department of Labor*. https://www.dol.gov/newsroom/releases/oasam/oasam20100930
18. *Complying with FTC’s Health Breach Notification Rule | Federal Trade Commission*. https://www.ftc.gov/business-guidance/resources/complying-ftcs-health-breach-notification-rule-0
19. *Seal of New York City - Wikipedia*. https://en.wikipedia.org/wiki/Seal_of_New_York_City
20. *
      Federal Register
       :: 
      Clinical Decision Support Software; Guidance for Industry and Food and Drug Administration Staff; Availability
    *. https://www.federalregister.gov/documents/2022/09/28/2022-20993/clinical-decision-support-software-guidance-for-industry-and-food-and-drug-administration-staff