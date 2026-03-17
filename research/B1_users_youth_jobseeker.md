# Designing for Real Teens: Richmond’s 14–18 Job Seekers, Their Barriers, and the Supports That Actually Move Them to Work

## Executive Summary

Richmond teens face a complex web of opportunities and systemic barriers when entering the workforce. While the city offers robust programmatic supports and zero-fare transit, the highest-leverage product decisions for a youth employment pathway tool revolve around navigating documentation, transit realities, and digital access constraints. 

The data reveals that hiring frequently breaks down on ID and I-9 compliance for minors, especially with E-Verify employers who mandate photo IDs [1] [2]. Transit access is highly solvable—GRTC operates from 5 AM to 1 AM daily with zero fares [3] —but teens need guidance on route planning and shift-fit to avoid being stranded. Furthermore, while digital equity initiatives are advancing [4], many teens rely on the Richmond Public Library (RPL), which enforces strict 60-minute session limits and auto-erases saved work [5]. To succeed, the employment tool must feature an age-aware document flow, transit-aware job matching, and a centralized program router that connects teens to built-in supports like Communities In Schools (CIS) or Partnership for the Future (PFF).

## Teen Landscape and Constraints

Understanding the day-to-day realities of 14–18-year-olds in Richmond is critical for designing an effective employment tool. Free transit and school-based supports exist, but documentation and digital access constraints still cause significant friction at the point of hiring.

### GRTC Zero-Fare and RPS Passes Enable Citywide Mobility
Transportation is a solvable barrier in Richmond. GRTC buses run from 5 AM to 1 AM daily, seven days a week, operating in the City of Richmond and surrounding counties [3]. The system is zero-fare, and the Pulse BRT is open access with no fare required [6] [7]. Furthermore, Richmond Public High School students (Grades 9-12) receive GRTC IDs for free unlimited rides on local routes, connecting them to internships and jobs [8]. For teens who are intimidated by public transit, GRTC offers a Travel Training Program for customers 15 years of age or older to learn how to navigate the bus routes [9].

### Digital Access is Real but Time-Limited at Libraries
While the Richmond City Council has advanced a "Digital Equity Implementation Plan" to bridge the digital divide [4], many teens currently rely on the Richmond Public Library (RPL) for internet access. All RPL locations offer free wireless internet and public use computers [10]. However, strict policies shape the user experience: patrons are limited to two 60-minute sessions per day, must use their own library card, and any work saved on RPL computers is automatically erased when the patron logs off [5]. Additionally, borrowing a laptop requires a valid government-issued photo ID [5], which many younger teens lack.

### Hiring Compliance Friction Points for Minors
The I-9 employment eligibility verification process presents a massive hurdle. For minors under the age of 18 who cannot present a List B identity document, a parent or legal guardian can establish identity by completing specific sections of Form I-9 [1] [11]. However, if the employer participates in E-Verify, this parent attestation is invalid; the minor must present a List B document that contains a photograph [1] [11] [2]. 

### Program Supports That Translate Into Jobs
Richmond has a rich ecosystem of youth programs. The City's Youth Engagement Services (YES) serves youth ages 14–24 with work-based learning and job readiness [12]. Richmond Public Schools (RPS) offers High-Quality Work-based Learning (HQWBL), including internships and registered apprenticeships [13]. Partnership for the Future (PFF) provides paid professional summer work experiences and college savings matches [14]. Communities In Schools (CIS) of Richmond supports K-12 students in 40 neighborhood schools, boasting a 98% graduation rate for its seniors [15].

## Persona Segmentation Framework

Age, support network strength, and prior experience define the needs of Richmond's teen job seekers. Building three to four primary flows based on these personas will allow the tool to personalize steps, adjust checklists, and provide the right level of scaffolding.

### Persona 1: The Eager Beginner (Ages 14–15)
* **Goal**: Secure a first job or introductory internship to gain experience.
* **Knowledge**: Knows they want to work and earn money; comfortable with basic mobile apps.
* **Gaps**: Confused about labor laws, age restrictions, and how to build a resume with no experience.
* **Barriers**: Age limits on most traditional jobs; lacks a government-issued photo ID; requires parent/guardian signatures for I-9 attestation [11].
* **First-Step Questions**: "Who actually hires 14-year-olds?" "How do I get a work permit?" "What is an I-9?"
* **Tool Routing**: Route to YES Counselors in Training (CIT) program (designed for ages 14-16) [12] or non-E-Verify employers.

### Persona 2: The Solo Navigator (Ages 16–17, Limited Adult Guidance, Transportation Barrier)
* **Goal**: Earn money for essential needs and gain independence.
* **Knowledge**: Knows how to hustle; highly motivated; familiar with their immediate neighborhood.
* **Gaps**: Unsure how to navigate corporate hiring compliance (I-9) without a parent; unaware of how to use the broader GRTC network.
* **Barriers**: **Transportation barrier** (no car, relies entirely on GRTC); **Limited adult guidance** (cannot easily get a parent to sign an I-9 attestation); may be in the foster care system.
* **First-Step Questions**: "How do I get to work if the bus stops running late at night?" "How do I prove my identity for a job if my parents aren't around to sign the forms?"
* **Tool Routing**: Warm handoff to DSS Independent Living Program (ILP) which assists foster youth 14-21 with transportation and job skills [16], or CIS site coordinators [15]. Suggest GRTC Travel Training (eligible at 15+) [9].

### Persona 3: The Ambitious Scholar (Ages 16–17, Strong Support, High GPA)
* **Goal**: Build a professional resume for college applications and save for tuition.
* **Knowledge**: Excels academically; understands basic application processes.
* **Gaps**: Lacks corporate workplace etiquette and professional networking skills.
* **Barriers**: Needs a structured environment that accommodates a rigorous academic schedule.
* **First-Step Questions**: "How do I get a professional internship instead of a fast-food job?" "Are there programs that help pay for college?"
* **Tool Routing**: Route to Partnership for the Future (PFF), which requires a 3.0 GPA, provides paid internships, coordinates transportation, and offers up to a $2,000 college savings match [14] [17] [18].

### Persona 4: The Transitioning Adult (Age 18, Prior Experience, Digital Access Barrier)
* **Goal**: Secure steady, higher-paying employment post-high school.
* **Knowledge**: Has prior retail/food service experience; knows how to interview.
* **Gaps**: Navigating complex digital Applicant Tracking Systems (ATS).
* **Barriers**: Relies on Richmond Public Library for internet access; faces 60-minute session limits and auto-erasing computers [5].
* **First-Step Questions**: "How can I save my resume and apply to multiple jobs before my library computer logs me out?"
* **Tool Routing**: Provide "save-safe" mobile-first flows; route to RPS Work-based Learning apprenticeships [13].

### Table: Age x Support x Experience — What Changes in the Tool

| Age Band | Key Constraints | Transit Options | Document Path | Eligible Programs | Coaching Intensity |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **14–15** | Age restrictions; no photo ID | GRTC Zero Fare; RPS Pass | Parent I-9 attestation (Non-E-Verify only) | YES CIT track | High (Guardian involvement required) |
| **16–17** | E-Verify photo ID rules; late shift risks | GRTC + Travel Training (15+) | Needs photo ID for E-Verify; Parent attestation otherwise | RPS WBL; PFF; YES | Medium to High (Depends on adult support) |
| **18** | Digital access limits; transitioning out of youth programs | GRTC Zero Fare | Standard Adult I-9 (List A or B+C) | YES (up to 24); RPS Apprenticeships | Low (Self-guided, save-safe UX needed) |

*Takeaway: The tool must dynamically adjust its workflow based on the user's age and support network, particularly regarding document preparation and program eligibility.*

## Transportation Realities -> Design Implications

Transit-aware job and schedule fit is essential to prevent stranded youth and failed job placements. While Richmond offers excellent zero-fare transit, the realities of shift work require careful planning.

### GRTC Access and Hours vs. Typical Shift Patterns
GRTC buses run from 5 AM to 1 AM daily [3]. While this covers most standard working hours, retail and food service jobs frequently require late-night closing shifts or early-morning opening shifts that may fall outside this window or operate on reduced frequencies. The Pulse BRT offers reliable open-access transit along its corridor [7], making jobs located near Pulse stations highly desirable for teens.

### Training and Confidence to Ride
Having free access to the bus does not equal knowing how to ride it. High schoolers use the RPS pass to get comfortable with public transportation [19], but the tool should actively promote the GRTC Travel Training Program (available for ages 15+) to build confidence [9].

### Table: Transportation Options and Supports

| Option | Eligibility / Age | Cost | Hours | Coverage | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **GRTC Zero Fare** | All riders | $0 | 5 AM – 1 AM daily | City of Richmond & surrounding counties | Pulse BRT is open access [3] [6] [7] |
| **RPS Student Pass** | Grades 9-12 | $0 | 5 AM – 1 AM daily | Local routes (excludes express) | Requires permission slip [8] |
| **GRTC Travel Training** | Ages 15+ | $0 | Varies | System-wide | Teaches skills to follow bus routes [9] |
| **PFF Transport** | PFF Interns | $0 | Mon-Thu, 9 AM - 5 PM | Internship sites | PFF ensures transportation is never a barrier [17] |

*Takeaway: The tool must include a "Shift Fit Checker" that cross-references job hours with GRTC schedules, prioritizing Pulse-corridor jobs and programs like PFF that eliminate the transit barrier entirely.*

## Documentation and Hiring Compliance

Failing to produce the correct documentation on day one is a primary reason teen job placements fall through. The document path diverges sharply based on age and the employer's E-Verify status.

### I-9 for Minors and the E-Verify Photo Requirement
For standard employers, a parent or legal guardian can establish identity for a minor under 18 by completing Section 1 of Form I-9 and entering "minor under age 18" in the signature field [1]. However, if the employer uses E-Verify, this workaround is strictly prohibited. E-Verify employers must only accept List B documentation that contains a photograph [1] [11] [2]. 

### Practical Barriers to Obtaining Photo ID
Obtaining a government-issued photo ID requires a trip to the DMV, which presents a massive barrier for teens with limited adult support or transportation. While school records, report cards, and clinic records are acceptable identity documents for minors under standard I-9 rules [20], they do not satisfy E-Verify requirements unless they contain a photograph.

### Table: Employer Type x Minor Documents Needed

| Employer E-Verify? | List B Requirement | Path for Under-18 Without Photo ID | Risks |
| :--- | :--- | :--- | :--- |
| **E-Verify YES** | MUST contain a photograph [2] | Cannot be hired until photo ID is obtained [11] | High risk of day-one termination; requires DMV visit |
| **E-Verify NO** | Photograph not strictly required | Parent/Guardian completes Section 1 attestation [1] | Fails if teen has limited adult guidance/no guardian |

*Takeaway: The tool must feature a "Documents Wizard" that asks if the teen has a photo ID and routes them to non-E-Verify employers if they do not, while providing a step-by-step guide to obtaining a DMV ID.*

## Digital Access and Product Design for Low-Resource Contexts

Designing for Richmond teens requires acknowledging that home broadband is not a guarantee. While the City of Richmond has declared high-speed internet a public necessity and is developing a Digital Equity Implementation Plan [4], and the state DHCD is advancing a Digital Opportunity Plan [21], these are long-term fixes.

### RPL Policies Drive Session Length and Save-Safe Design
Currently, many teens rely on the Richmond Public Library. Because RPL limits users to two 60-minute sessions per day and automatically erases all saved work upon logoff [5], the employment tool must be designed for intermittent access. It must feature auto-save to the cloud, email/PDF export capabilities, and "no account" flows that allow a teen to build a resume and apply for a job within a single 20-to-40-minute window. Furthermore, because borrowing an RPL laptop requires a government-issued photo ID [5], teens without IDs are restricted to desktop workstations.

## Program Ecosystem that Unlocks Opportunity

A smart router within the tool can align teens to programs that bundle transportation, coaching, and paid experience, bypassing traditional barriers entirely.

### Table: Richmond Youth Programs — Eligibility and Supports

| Program | Age / Grade | Pay | Transportation | Academic Requirement | Primary Supports |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Youth Engagement Services (YES)** | Ages 14–24 | Paid tracks available | Relies on GRTC | None specified | Job readiness, WBL, CIT track for 14-16 [12] |
| **RPS Work-Based Learning** | High School | Paid/Unpaid | RPS Pass / GRTC | Tied to CTE courses | Internships, registered apprenticeships [13] |
| **Partnership for the Future (PFF)** | High School | Paid (Min. wage+) | Provided by PFF [17] | 3.0 GPA [18] | College prep, $2,000 scholarship match [14] |
| **Communities In Schools (CIS)** | K-12 | N/A (Support org) | N/A | None | Workforce readiness, individual student plans [22] [15] |

*Takeaway: Centralizing an eligibility screener that outputs the "best next steps" based on age, GPA, and support needs will drastically reduce drop-off rates.*

## Risk Scenarios and Mitigations

Anticipating and defusing failure modes within the UX is critical for the tool's success.

* **Late/Early Shift with No Transit**: 
 * *Risk*: Teen is stranded after 1 AM when GRTC stops [3].
 * *Mitigation*: Implement a Shift Fit Checker; highlight employers near the Pulse BRT [7]; route to PFF for guaranteed transport [17].
* **E-Verify Employer + No Photo ID**: 
 * *Risk*: Teen is hired but cannot complete I-9 [2].
 * *Mitigation*: ID path planning; filter out E-Verify roles for teens without IDs; educate on parent attestation [1].
* **No Adult Support for I-9/Onboarding**: 
 * *Risk*: Teen cannot get a guardian signature for I-9 [11].
 * *Mitigation*: Warm handoffs to DSS Independent Living Program (ages 14-21) [16] or CIS site coordinators [15].
* **Library-Only Access, No Save**: 
 * *Risk*: Teen loses all resume progress after 60 minutes [5].
 * *Mitigation*: Auto-save/export features; 20-minute quick flows; SMS follow-ups.

## Product Requirements and Prioritization

To unlock the most value quickly, the tool should be developed with four MVP capabilities:

1. **MVP-1: Program Match Router**: A screener that routes users to YES, RPS WBL, PFF, or CIS based on age, GPA, and support needs.
2. **MVP-2: Document Wizard**: An age-aware, E-Verify-aware checklist that prepares teens for day-one compliance.
3. **MVP-3: Transit-Aware Job Finder + Shift Fit Checker**: Integrates GRTC hours (5 AM - 1 AM) [3] and routes to ensure safe commutes.
4. **MVP-4: Mobile-First, Save-Safe Resume Builder**: Designed to survive RPL's 60-minute session limits and auto-erase policies [5].

## Partnerships and Data Feeds

Lightweight integrations will make the tool's recommendations precise and credible. The tool should integrate feeds for GRTC routes and hours [3], RPS pass information [8], and Travel Training signups [9]. Employer onboarding must include mandatory flags for E-Verify status and shift windows to power the Document Wizard and Shift Fit Checker.

## Assumptions, Inferences, and Unknowns

### Inferences (Clearly Labeled)
* *Inference*: Many 14–15-year-olds lack government-issued photo IDs, given that RPL requires them for laptop checkouts [5] and USCIS has special carve-outs for minors without them [1].
* *Inference*: Retail and food service jobs commonly require late shifts that may conflict with GRTC's 1 AM shutdown [3].
* *Inference*: Teens prefer mobile over desktop, and library constraints (60-min limits, ID requirements for laptops) reinforce the need for a mobile-first design [5].

### Unknowns / Next Research
* What percentage of Richmond employers hiring teens currently use E-Verify?
* What are the exact DMV ID acquisition timelines and costs for minors in Richmond?
* Will employers accept RPS school IDs as a List B document if they contain a photograph?
* What is the actual home broadband access rate for RPS high schoolers following the rollout of the Digital Equity Implementation Plan [4]?

## Implementation Roadmap

* **Phase 1 (0–90 days)**: Launch MVP-1 (Program Router) and MVP-2 (Document Wizard). Pilot in two high schools with CIS and YES partners. Onboard 10 initial employers, requiring them to flag their E-Verify status.
* **Phase 2 (90–180 days)**: Roll out MVP-3 (Transit-Aware Job Finder). Expand routing to include RPS WBL and PFF. Introduce SMS flows to bypass library time limits.
* **Phase 3 (180–360 days)**: Deepen data integrations with GRTC. Track 30/90-day employment persistence analytics. Execute a citywide rollout in partnership with the City of Richmond and RPS.

## References

1. *Minors | USCIS*. https://www.uscis.gov/i-9-central/complete-correct-form-i-9/minors
2. *Instructions for Form I-9, Employment Eligibility Verification*. https://www.uscis.gov/sites/default/files/document/forms/i-9instr.pdf
3. *GRTC: Home*. https://www.ridegrtc.com/
4. *Richmond City Council passes resolution to improve internet speed throughout the city | WRIC ABC 8News*. https://www.wric.com/news/local-news/richmond/richmond-city-council-passes-resolution-to-improve-internet-speed-throughout-the-city/
5. *06.01 Computer and Acceptable Use Policy-Reviewed 07-23 ...*. https://rvalibrary.org/wp-content/uploads/2025/08/06.01-Computer-and-Acceptable-Use-Policy-Reviewed-07-23-2025-Copy.pdf
6. *Transit Access Partnership*. https://www.ridegrtc.com/community/transit-access-partnership-2/
7. *Pulse (BRT) -GRTC*. https://www.ridegrtc.com/grtc-services/pulse-brt/
8. *Support Richmond Public Schools | Richmond Public-SchoolsStudent Pass Program Update:  | Facebook*. https://www.facebook.com/groups/969056046503304/posts/1954072521334980/
9. *Travel Training Program*. https://www.ridegrtc.com/rider-guide/travel-training-program/
10. *Services - Richmond Public Library*. https://rvalibrary.org/services/
11. *4.2 Minors (Individuals under Age 18) | USCIS*. https://www.uscis.gov/i-9-central/form-i-9-resources/handbook-for-employers-m-274/40-completing-section-2-employer-review-and-verification/42-minors-individuals-under-age-18
12. *Youth Engagement Services | Richmond*. https://www.rva.gov/community-wealth-building/youth-engagement-services
13. *Workbased Learning - Richmond Public Schools*. https://www.rvaschools.net/academics/secondary/career-technical-education/workbased-learning
14. *Become a Student | Partnership for the Future*. https://www.partnershipforthefuture.org/become-a-student/
15. *Communities In Schools Richmond*. https://cisrva.org/
16. *Services for Older Youth - Virginia Department of Social Services*. https://www.dss.virginia.gov/family/fc/independent.cgi
17. *Host an Intern | Partnership for the Future*. https://partnershipforthefuture.org/host-an-intern/
18. *Program Details | Partnership for the Future*. https://www.partnershipforthefuture.org/how-we-work/program-details/
19. *RPS highschoolers can get around the city for free on GRTC | WRIC ABC 8News*. https://www.wric.com/news/local-news/richmond/rps-highschoolers-can-get-around-the-city-for-free-on-grtc/
20. *Form I-9 Acceptable Documents | USCIS*. https://www.uscis.gov/i-9-central/form-i-9-acceptable-documents
21. *Digital Opportunity | DHCD*. http://www.dhcd.virginia.gov/digital-opportunity
22. *Workforce Readiness | Strengthening the School-to-Work-Pipeline*. https://cisofva.org/equitable-education/