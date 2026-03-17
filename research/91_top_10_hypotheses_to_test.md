# Building MVPs That Matter: Testable Paths to Thriving Families in Richmond

## Executive Summary
To drive meaningful outcomes for the "Thriving Families" pillar in Richmond, Virginia, civic-tech teams must focus on actionable, data-driven interventions. Current data reveals significant gaps in maternal health coordination, particularly for uninsured and minority mothers, alongside a critical blind spot regarding youth employment metrics. By leveraging existing state infrastructure like the Virginia Health Information (VHI) Emergency Department Care Coordination (EDCC) platform and the CRISP Shared Services network, teams can avoid reinventing the wheel and focus on closing referral loops. The following report outlines 10 highly testable hypotheses designed to inform Minimum Viable Product (MVP) development, spanning maternal health data coordination and youth employment, including specific assumptions to be validated or invalidated during hackathon user research.

## Context and Objectives
The objective of these MVPs is to align technical solutions with Richmond's "Thriving Families" goals. For maternal health, the focus is on mitigating risks identified in the 2021 Pregnancy Risk Assessment Monitoring System (PRAMS) data for the Richmond City Health District, which highlights high rates of unintended pregnancy, maternal depression, and inadequate prenatal care [1]. For youth employment, the objective is to rapidly fill data gaps through primary research to build tools that reduce friction in program enrollment and job access.

## Top 10 Hypotheses to Test

**1. The Digital Triage Hypothesis (Maternal Health)**
* **Hypothesis:** A bilingual digital intake triage for the Richmond and Henrico Health Districts (RHHD) Maternity Navigation program will significantly reduce the "time-to-first prenatal appointment" for uninsured mothers.
* **Confirmation/Disconfirmation:** Confirmed if the median days from intake to the first scheduled prenatal visit decreases by 20% compared to the current phone-only baseline. Disconfirmed if digital intake completion rates are low or do not accelerate scheduling.
* **Supporting Evidence:** 10.16% of Richmond City PRAMS 2021 respondents reported having no insurance to pay for prenatal care, and 11.60% had inadequate prenatal care [1]. RHHD already runs a bilingual Maternity Navigation line specifically to connect uninsured pregnant people to care and coverage [2].
* **Risk if Wrong:** Building a digital front door that target users cannot or will not use, wasting development resources while the phone line remains the actual bottleneck.

**2. The Wraparound Integration Hypothesis (Maternal Health)**
* **Hypothesis:** Embedding one-click warm referrals for WIC, dental care, and behavioral health into navigation and home visiting intakes will increase connection rates to these services within 14 days.
* **Confirmation/Disconfirmation:** Confirmed if the percentage of at-risk clients connected to at least one ancillary service within 14 days of intake exceeds 50%. Disconfirmed if referrals are generated but "show rates" to the actual services remain flat.
* **Supporting Evidence:** PRAMS 2021 data shows overlapping risks: 16.83% reported depression, 22.21% needed to see a dentist for a problem, and WIC enrollment sits at only 25.08% [1].
* **Risk if Wrong:** Cluttering the intake workflow with irrelevant prompts, leading to alert fatigue for case workers and false hope for mothers.

**3. The Postpartum Alert Hypothesis (Maternal Health)**
* **Hypothesis:** Subscribing to VHI EDCC delivery alerts will increase the percentage of postpartum mothers receiving RHHD or home visiting outreach within 7 days of discharge.
* **Confirmation/Disconfirmation:** Confirmed if 80%+ of flagged deliveries receive documented outreach within 7 days. Disconfirmed if alerts are generated but staffing capacity cannot support the outreach volume.
* **Supporting Evidence:** The VHI EDCC program now features targeted functionality for maternal and infant health, allowing providers to set up alerts for patients with a recent history of delivery and includes a Substance Exposed Infant (SEI) flag [3].
* **Risk if Wrong:** Over-engineering an alert system that outpaces the operational capacity of RHHD or home visiting programs to actually intervene.

**4. The Infrastructure Reuse Hypothesis (Maternal Health)**
* **Hypothesis:** Routing MVP data flows through VHI and CRISP Shared Services endpoints will reduce integration time and compliance exposure compared to building bespoke APIs with individual hospitals.
* **Confirmation/Disconfirmation:** Confirmed if a data-sharing pilot can be legally and technically scoped with VHI within 30 days. Disconfirmed if VHI/CRISP onboarding requirements are too heavy for a lightweight civic-tech MVP.
* **Supporting Evidence:** VHI is the statewide Health Information Exchange (HIE) [4]. The Public Health Reporting Pathway (PHRP) transfers data securely in partnership with CRISP Shared Services [5], and VDH mandates transitioning to CRISP for public health messages [6].
* **Risk if Wrong:** Delays in MVP deployment due to unforeseen bureaucratic hurdles with the state HIE, stalling the project entirely.

**5. The Closed-Loop Referral Hypothesis (Maternal Health)**
* **Hypothesis:** A shared referral status board between hospitals, RHHD, and Healthy Families Richmond will increase referral acceptance rates and decrease the days to the first home visit.
* **Confirmation/Disconfirmation:** Confirmed if the referral acceptance rate increases and the average time to the first home visit drops. Disconfirmed if partners refuse to update the shared board, rendering the data stale.
* **Supporting Evidence:** Healthy Families Richmond is an intensive home visiting program that relies on referrals from hospitals, medical offices, and schools [7].
* **Risk if Wrong:** Creating another standalone dashboard that case workers must log into, adding administrative burden without improving care coordination.

**6. The Preventive Checklist Hypothesis (Maternal Health)**
* **Hypothesis:** Implementing mandatory encounter checklists for preventive counseling (e.g., HIV testing, dental education) in navigation workflows will raise baseline performance for these metrics.
* **Confirmation/Disconfirmation:** Confirmed if checklist completion rates correlate with an uptick in downstream service utilization. Disconfirmed if workers pencil-whip the checklists without actually providing the counseling.
* **Supporting Evidence:** PRAMS 2021 data indicates inconsistent preventive care: only 57% of respondents were tested for HIV, and only 48.19% discussed dental care with a healthcare worker during pregnancy [1].
* **Risk if Wrong:** Checklist fatigue, where the administrative burden detracts from the quality of the human interaction between the navigator and the mother.

**7. The Trust and Privacy Hypothesis (Cross-Cutting / Invalidatable by User Research)**
* **Hypothesis:** Black and Spanish-speaking mothers will abandon digital intake forms that do not explicitly state data privacy protections and offer immediate live-language support options.
* **Confirmation/Disconfirmation:** Can be invalidated during the hackathon by A/B testing paper prototypes or wireframes with and without explicit privacy/language trust markers. Confirmed if the version with trust markers yields significantly higher willingness to complete.
* **Supporting Evidence:** 41.21% of PRAMS respondents in Richmond City reported experiencing discrimination or harassment due to their race, ethnicity, or culture [1]. RHHD explicitly highlights its bilingual (English/Spanish) capabilities to build trust [2].
* **Risk if Wrong:** If invalidated, it means users are more tolerant of standard forms than expected, but if true and ignored, the MVP will suffer from fatal adoption failures among the most vulnerable populations.

**8. The Youth Enrollment Friction Hypothesis (Youth Employment / Invalidatable by User Research)**
* **Hypothesis:** The primary barrier to youth (16-24) enrollment in local employment programs is the friction of mobile document upload for ID/eligibility verification, rather than a lack of interest.
* **Confirmation/Disconfirmation:** Can be invalidated during hackathon intercept interviews. Confirmed if youth cite "paperwork/ID submission" as the reason they abandoned an application. Disconfirmed if youth cite "pay rate," "schedule," or "didn't know about it" as the primary barriers.
* **Supporting Evidence:** While specific youth data is missing from the corpus, civic-tech patterns frequently show document verification as the highest drop-off point in benefits enrollment.
* **Risk if Wrong:** Building a sophisticated mobile document scanner when the actual problem is a lack of awareness or misaligned job incentives.

**9. The Transit Integration Hypothesis (Youth Employment)**
* **Hypothesis:** Integrating zero-fare transit proof or route-planning directly into youth employment portals will increase interview show rates and job retention.
* **Confirmation/Disconfirmation:** Confirmed if youth utilizing the transit-integrated portal have a higher interview attendance rate than those using standard communications. Disconfirmed if transportation is not a limiting factor for the target demographic.
* **Supporting Evidence:** Transportation is a universally recognized barrier to entry-level employment, though specific GRTC zero-fare impact data requires further hackathon validation.
* **Risk if Wrong:** Wasting API integration efforts on transit mapping if the target youth population primarily relies on ridesharing, family, or walking.

**10. The Granular Consent Hypothesis (Cross-Cutting)**
* **Hypothesis:** A unified eConsent module that allows users to grant granular share-scopes (e.g., sharing with medical providers vs. social services) will yield higher overall consent rates than a blanket "share all" agreement.
* **Confirmation/Disconfirmation:** Confirmed if the opt-in rate for granular consent exceeds the historical baseline for blanket consent forms. Disconfirmed if users find the granular options confusing and abandon the consent process entirely.
* **Supporting Evidence:** Data coordination across entities (hospitals, RHHD, WIC, home visiting) requires robust consent management, especially when dealing with sensitive flags like Substance Exposed Infants (SEI) [3].
* **Risk if Wrong:** Overcomplicating the legal and technical onboarding process for users, resulting in data silos persisting because users default to "no" out of confusion.

## Inferences
* **Behavioral Health Urgency:** The high rate of unintended pregnancy (45.19%) combined with a 16.83% depression rate [1] infers that maternal navigation cannot just be about physical health; early, integrated behavioral health screening is urgently required at the first point of contact.
* **HIE Modernization:** The explicit instruction from VDH that reporters must transition to CRISP Shared Services [6] infers that legacy point-to-point interfaces are being deprecated. MVPs must align with CRISP standards to be viable long-term.
* **Capacity Constraints:** The existence of multiple home visiting programs (Healthy Families Richmond, Family Lifeline) [7] [8] infers a fragmented ecosystem where capacity balancing (knowing who has an open slot) is likely a major operational pain point.

## Unknowns
* **Youth Employment Metrics:** The current research corpus lacks hard data on youth employment outcomes in Richmond (e.g., Mayor's Youth Academy metrics, WIOA youth participation rates, specific employer demand). This is a critical blind spot that must be filled via primary research on day one of the hackathon.
* **GRTC Zero-Fare Impact:** The specific impact of the GRTC zero-fare program on youth employment access and whether transit passes are seamlessly integrated into Richmond Public Schools' infrastructure remains unknown.
* **Hospital Consent Policies:** While the VHI EDCC platform technically supports data sharing [3], the specific legal and consent policies required by local Richmond hospitals to share postpartum alerts with community-based organizations (like RHHD or Healthy Families) are not detailed in the current data.

## References

1. *RCHD, VA PRAMS FACTS- 2021*. https://www.vdh.virginia.gov/content/uploads/sites/67/2023/12/Richmond-City-Health-District-2021.pdf
2. *Healthy Childbirth and Infancy - Richmond City Health Department*. https://www.vdh.virginia.gov/richmond-city/healthy-childbirth-and-infancy
3. *Strengthening Maternal and Infant Care in Virginia ⎸ VHI*. https://www.vhi.org/2026/01/13/strengthening-virginias-maternal-and-infant-care-through-data/
4. *Virginia Statewide Health Information Exchange ⎸ VHI*. https://www.vhi.org/hie
5. *Public Health Reporting Pathway ⎸ VHI*. https://www.vhi.org/hie/public-health-reporting-pathway/
6. *VDH Message Transport Options - Meaningful Use - Virginia.gov*. https://www.vdh.virginia.gov/meaningful-use/messagetransportoptions/
7. *CFA - Healthy Families Richmond | Richmond*. https://www.rva.gov/social-services/cfa-healthy-families-richmond
8. *Family Lifeline | Home Visiting | Virginia*. https://www.familylifeline.org/