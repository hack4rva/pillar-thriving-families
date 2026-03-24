# Prior-Art Review: Workforce Navigator Programs

## Executive Summary
This document consolidates publicly-available information on workforce-navigator models implemented across North America, providing foundational prior art for the "E3 Navigator" concept. Research indicates these programs operate primarily across three contexts: federal workforce systems (e.g., WIOA), state-level educational benefits navigation (e.g., Washington and Oregon), and sector-specific coalitions (e.g., Salesforce). Key findings reveal a bifurcation in service delivery: state and federal models rely heavily on human-led, high-touch counseling for basic needs and training referrals, whereas emerging state portals (New Jersey, Massachusetts) and private programs leverage AI-driven matching and digital hubs. Funding mechanisms vary significantly, from federal appropriations to state-mandated institutional budgets (e.g., Washington's $32,515 annual reimbursement per college navigator). For a new E3 Navigator, a hybrid approach combining scalable AI-driven skill matching with targeted human intervention for complex barrier resolution is recommended.

---

## 1. Introduction
Workforce-navigator programmes are intermediary services that help job-seekers, students, or people with disabilities connect to employment-related resources (training, benefits, mentorship, and job openings). They have emerged in three broad contexts:

| Context | Typical Operator | Primary Goal |
|---------|------------------|--------------|
| **Federal** | U.S. Department of Labor (WIOA) | Deliver coordinated career-services to millions of workers. |
| **State / Regional** | State education or workforce agencies (WA, OR, NJ, MA) | Bridge local gaps in basic-needs, benefits, and skill-mapping. |
| **Sector-Specific / Private-Non-profit Coalitions** | Salesforce Workforce Navigators; community-college consortia | Upskill under-represented groups (e.g., people with disabilities). |

Understanding these precedents informs the design of any new "E3 Navigator" concept, especially around eligibility criteria, funding streams, measurable outcomes, and scalability.

---

## 2. Programme Profiles

### 2.1. Workforce Navigators – Salesforce (Canada & U.S.)
*Operator*: Salesforce Office of Accessibility in partnership with nonprofit training partners (e.g., Blind Institute of Technology) [1].
*Launch*: First public rollout announced at Dreamforce 2023 [1].
*Target Users*: Professionals with disabilities in the U.S. and Canada who are seeking Salesforce certification or employment [1] [2].
*Key Features*:

| Feature | Detail |
|--------|--------|
| **Three-tiered support** | Mentorship (meeting at least 2 hours per month), virtual bootcamps (live & self-paced), and scholarships [2]. |
| **Exam accommodations** | Coordinated with Salesforce certification exams via formal request processes [2]. |
| **Partner ecosystem** | Corporate, nonprofit, and community-college partners provide pipeline jobs (e.g., Blind Institute of Technology certification prep) [1]. |
| **Digital hub** | Centralized portal for resources, events, and success-stories at workforcenavigators.salesforce.com [1]. |

*Evidence of impact*: Specific certification completion and employment rates are not publicly disclosed in the cited documentation, though the program actively tracks success stories and partner placements [1].

---

### 2.2. Benefits Navigator – Washington State Community & Technical Colleges
*Operator*: Washington State Board for Community and Technical Colleges (SBCTC) – campus-level Benefits Navigators [3].
*Launch*: Program documentation and funding plans extend through FY26 (published 2025-06) [4].
*Target Users*: Students enrolled (or intending to enroll) at any Washington community or technical college who experience basic-needs insecurity (food, housing, childcare, health) [5].
*Key Features*:

| Feature | Description |
|---------|-------------|
| **One-stop referral** | Connects students to state-wide resources including Basic Food, Working Connections Childcare, and emergency assistance grants [5]. |
| **Eligibility** | Open to any prospective or current student with demonstrated basic needs that hurt their ability to begin or continue school [5]. |
| **Funding** | The college BFET program can claim reimbursement for the Benefits Navigator at $32,515 per year, broken out by salary and benefits each quarter [4]. |
| **Outcome tracking** | Colleges report usage statistics to SBCTC annually (exact aggregate metrics not publicly disclosed). |

---

### 2.3. Benefits Navigator – Oregon House Bill 2835 (2021)
*Operator*: Each Oregon public university and community college must hire a benefits navigator [6].
*Enactment*: 2021-06 (HB 2835 signed into law) [7].
*Target Users*: All enrolled students who need assistance determining eligibility and applying for federal, state, and local benefits programs [6].
*Key Features*:

| Feature | Detail |
|---------|--------|
| **Mandated staffing** | Requires each community college and public university to hire a benefits navigator [6]. |
| **Consortium coordination** | Requires institutions to establish a statewide consortium to enable navigators to coordinate and develop best practices [6]. |
| **Student Feedback** | Requires institutions to develop an internal process for students to provide feedback and recommendations on assistance [6]. |
| **Emergency declaration** | Declared an emergency, effective on passage to allow immediate deployment [6]. |

---

### 2.4. NJ Career Navigator (MyCareer NJ)
*Operator*: State of New Jersey – "My Career NJ" portal [8].
*Launch*: Beta version active as of recent portal updates [8].
*Target Users*: New Jersey residents seeking personalized job recommendations and training pathways [8].
*Key Features*:

| Feature | Description |
|---------|-------------|
| **Data-Driven matching** | Uses data and machine learning to compare user skills/experience to current job openings and other New Jerseyans' experiences [8]. |
| **Training link-outs** | Directs users to high-value training programs and open jobs to apply to [8]. |
| **Continuous improvement** | Recommendation engine improves over time as it learns more about the user [8]. |
| **High Potential Pathways** | Algorithm presents new career pathways informed by successful transitions made by other state workers [8]. |

---

### 2.5. MassHire Career Information System (CIS) – Massachusetts
*Operator*: Commonwealth of Massachusetts (MassHire) [9].
*Target Users*: Job-seekers needing tools to make better-informed career and school choices [9].
*Key Features*:

| Feature | Detail |
|---------|--------|
| **Unified job-search platform** | Provides tools needed to help people make better-informed career and school choices [9]. |
| **Personalised accounts** | To access MassHireCIS, job seekers must complete a simple login process [9]. |
| **Career Exploration** | Helps users explore how skills, interests, and values translate to satisfying and sustainable career paths [10]. |

---

### 2.6. Federal WIOA Career Navigator (U.S.)
*Operator*: U.S. Department of Labor, Employment & Training Administration (ETA) [11].
*Legislation*: Workforce Innovation & Opportunity Act (WIOA) [11].
*Target Users*: Millions of job seekers, including specific vulnerable populations (Job Corps, YouthBuild, Indian and Native American Program, Reentry Employment Opportunities) [11].
*Key Features*:

| Feature | Detail |
|---------|--------|
| **Comprehensive services** | Job search assistance, workforce preparation, career development, and classroom/work-based learning opportunities [11]. |
| **Employer alignment** | Helps businesses find skilled workers by referring qualified job seekers and filling job orders [11]. |
| **Network scale** | Services are available through a network of approximately 2,400 American Job Centers (AJCs) nationwide [11]. |

---

## 3. Comparative Summary

| Programme | Operator | Geography | Primary Users | Core Services |
|----------|----------|-----------|---------------|--------------|
| **Salesforce Workforce Navigators** | Salesforce + NGOs | Canada & U.S. | People with disabilities | Mentorship, bootcamps, scholarships, accommodations [1] [2] |
| **WA Benefits Navigator** | SBCTC (state) | Washington State | Community/technical college students | Referral to food, housing, childcare, emergency grants [5] |
| **OR Benefits Navigator (HB 2835)** | Public colleges & universities | Oregon | All post-secondary students | Benefit-eligibility counseling, consortium coordination [6] |
| **NJ Career Navigator** | State of NJ | New Jersey | Residents seeking jobs & training | Machine-learning job matching, training links [8] |
| **MassHire CIS** | MassHire (MA) | Massachusetts | Job-seekers | Career exploration, school choice tools [9] |
| **WIOA Career Navigator** | U.S. Dept. of Labor | Nationwide (U.S.) | All job-seekers (incl. vulnerable groups) | Career counseling, training referrals, employer services [11] |

---

## 4. Key Patterns & Take-aways

1. **Targeted equity focus** – Private-sector (Salesforce) and state programmes (WA, OR) explicitly serve *people with disabilities* or *students with basic-needs insecurity* [1] [5].
2. **Funding models vary** – Federal WIOA relies on national appropriations [11]; states use per-institution budgets (e.g., WA reimburses $32,515 annually per navigator) [4]; private programmes offer scholarships funded by corporate partners [2].
3. **Technology enablement** – Machine-learning recommendation engines appear in NJ [8], while Salesforce leverages its own Trailhead platform [2]. Most other basic-needs programmes are manual-referral models.
4. **Scalability constraints** – Programs limited to a single jurisdiction (e.g., OR HB 2835) face funding and staffing caps [6], while national programmes (WIOA) benefit from economies of scale across 2,400 centers but lack granular personalization [11].

---

## 5. Recommendations for a New "E3 Navigator"

| Recommendation | Rationale (based on prior art) | Quick-Start Action |
|----------------|--------------------------------|--------------------|
| **Hybrid model** | Addresses both *high-volume efficiency* (like NJ's algorithm) [8] and *deep-needs counseling* (like WA/OR) [5] [6]. | Pilot AI-matching module using open-source skill-taxonomy; hire 1-2 pilot navigators in a mid-size community college. |
| **Multi-jurisdiction funding pool** | Provides sustainable budget and leverages corporate CSR (similar to Salesforce scholarships) [2]. | Draft joint-proposal to U.S. Dept. of Labor's WIOA Innovation Fund; approach private sector for co-branding. |
| **Inclusive eligibility** | Captures a larger at-risk cohort by addressing holistic barriers (food, housing, childcare) [5]. | Update eligibility guide; train navigators on comprehensive resource referrals. |
| **Scalable training pathways** | Provides clear career ladders and measurable skill acquisition (mirroring Salesforce's bootcamps) [2]. | Partner with local community-college CTE programs to co-develop micro-credential badges. |

## References

1. *Workforce Navigators: Homepage*. https://workforcenavigators.salesforce.com/
2. *Join Workforce Navigators Program - Trailhead*. https://trailhead.salesforce.com/content/learn/modules/workforce-navigators-career-pathways-for-trailblazers-with-disabilities/join-the-workforce-navigators
3. *Benefits Navigation Program Information for College Staff*. https://www.sbctc.edu/colleges-staff/programs-services/workforce-education/benefits-navigation/default.aspx
4. *[PDF] benefits navigator and campus strategic plans (2shb 1559)*. https://www.sbctc.edu/resources/documents/colleges-staff/programs-services/workforce-education/benefits-navigation/fy26-navigator-plan-guide.pdf
5. *Benefits Navigation Program Information for Students*. https://www.sbctc.edu/colleges-staff/programs-services/workforce-education/benefits-navigation/students.aspx
6. *HB2835 2021 Regular Session - Oregon Legislative Information ...*. https://olis.oregonlegislature.gov/liz/2021R1/Measures/Overview/HB2835
7. *Oregon bill funds 'benefits navigators' at public universities, colleges*. https://www.opb.org/article/2021/06/23/oregon-bill-funds-benefits-navigators-at-public-universities/
8. *New Jersey Career Navigator*. https://mycareer.nj.gov/navigator/
9. *MassHireCIS - MassHire Career Information System - Mass.gov*. https://www.mass.gov/info-details/masshirecis-masshire-career-information-system
10. *Western Mass Career Exploration Resources*. https://www.masshirefhcareers.org/for-job-seekers/career-exploration-resources
11. *WIOA Workforce Programs*. https://www.dol.gov/agencies/eta/wioa/programs