> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Richmond Youth Jobs Navigator — Credible, Privacy-Safe Pathways That Work

## Executive Summary
This pitch guide and demo script provides a comprehensive strategy for presenting the Richmond Youth Jobs Navigator to civic tech hackathon judges. The tool solves a critical friction point in youth employment: navigating the complex web of state and federal labor laws, privacy regulations, and transportation logistics without relying on a fragile, proprietary dataset. 

By anchoring the solution to official Virginia Department of Labor and Industry (DOLI) processes [1], enforcing federal hours restrictions [2], and leveraging GRTC's zero-fare transit [3], the tool de-risks the hiring process for both teens and employers. Furthermore, it is designed with strict adherence to the Virginia Consumer Data Protection Act (VCDPA) [4], ensuring minors' data is protected. The proposed continuation strategy partners with the Boys & Girls Clubs of Metro Richmond (BGCMR) to ensure long-term community stewardship [5] [6].

## Demo Narrative that Judges Can Picture

### Opening Hook (30–45 seconds)
**Speaker:** "Meet Jamal. He’s 15, lives on the Southside, and wants to get his first part-time job this summer. He knows he can ride the GRTC bus for free to get to work. But before he can take his first shift, he has to navigate a maze: he needs a state work permit, he has to find a role that isn't legally classified as 'hazardous,' and he has to make sure his manager doesn't schedule him for hours that violate federal law. If he or his employer gets it wrong, the job falls through. Today, we’re showing you the Richmond Youth Jobs Navigator—a tool that gets Jamal from 'I want to work' to his first legal, safe shift in five simple steps, without collecting his private data."

## Tool Walkthrough Script (2–3 minutes)

### Step 1: Age + Situation Check (10–15 sec)
**Speaker:** "Jamal opens the app. We don't ask for his name or email. We just ask his age. He selects '15'. Instantly, the tool sets the guardrails. It informs him that because he is 14 or 15, Virginia law requires him to get an Employment Certificate [1]. It also previews his legal working hours: no more than 3 hours on a school day, and he can't work past 7:00 p.m. during the school year [7] [8]."

### Step 2: Safe-Role Explorer (30–40 sec)
**Speaker:** "Next, Jamal explores types of jobs. Instead of a static job board that goes out of date, we provide a 'Safe-Role Explorer.' Federal and state laws prohibit minors under 18 from hazardous jobs, and 14-15 year olds specifically cannot work in manufacturing, freezers, or operate power-driven machinery [1] [7]. The tool filters out these prohibited roles and highlights allowable jobs like retail or tutoring, linking directly to U.S. DOL Fact Sheet #43 so employers and parents can verify the rules [2]."

### Step 3: Legal Checklist (40–50 sec)
**Speaker:** "Here is where most teens get stuck. You cannot apply for a Virginia work permit until you have a firm job offer [1]. Our tool asks: 'Do you have a job offer?' Once Jamal clicks yes, we give him the exact checklist he needs: an 'Intent to Employ' form for his boss, a 'Permission to Employ' form for his parent, and Proof of Age [9]. We then deep-link him directly to DOLI’s Virginia Electronic Employment Certificate System. We nudge him toward this electronic path because DOLI generally reviews these within 24 hours, whereas the manual paper process takes up to 10 business days and requires a notary [1] [10]."

### Step 4: Schedule Sanity Check (20–30 sec)
**Speaker:** "Jamal gets the job. His manager suggests a schedule. Jamal uses our 'Schedule Sanity Check' to input the hours. The tool instantly validates them against federal limits—flagging if a shift exceeds 18 hours in a school week or goes past the 7 p.m. cutoff [2] [11]. If there's a conflict, it suggests compliant alternatives."

### Step 5: Getting There on GRTC (20–30 sec)
**Speaker:** "Finally, logistics. Jamal needs to get to work. We integrate a transit step that links to GRTC route planning and reminds him that all GRTC buses are currently Zero Fare [3]. It also notes that Richmond Public Schools high school students have historically had access to unlimited local rides through specific ridership programs [12]. He can print or screenshot this transit plan for his first day."

## Credibility and Limits Statement (30 seconds)

**Speaker:** "You might be wondering: how do we maintain this data? The answer is, we don't invent a dataset. We route to the law. Every rule and step in this tool has a visible 'Source' link with a 'Last Checked' timestamp—for example, 'DOLI Youth Employment — checked Mar 17, 2026.' Where federal and state laws conflict, we automatically apply the strictest rule, as required by DOLI [1]. We don't own the policy; we orchestrate the official guidance so teens and employers get it right the first time."

## Privacy Design

### Built for Minors Under Virginia’s VCDPA
**Speaker:** "Because our users are minors, privacy isn't a feature; it's the foundation. Under the Virginia Consumer Data Protection Act (VCDPA), which has strict provisions for known children under 18, controllers cannot process data for targeted advertising, sale, or profiling without verifiable parental consent [4] [13] [14]. The Attorney General is actively enforcing this with fines up to $7,500 per violation [15] [16]. 

Therefore, our tool requires no accounts, serves no ads, and uses no trackers. We store nothing server-side beyond anonymous analytics. We do not collect precise geolocation [4]; any transit routing is done via optional, client-side lookups. If a future version requires saved profiles, we are already prepared to conduct the legally required Data Protection Assessment and implement COPPA-aligned parental consent [4] [13]."

## Handling Judge Skepticism

### Freshness, Duplication, and Impact
* **Freshness:** We handle skepticism about outdated information by not hosting the core data. We use live links to official pages with "Last Checked" stamps. We will implement an automated weekly link-health job to flag broken URLs or changed content for manual review.
* **Duplication:** We are not replicating the DOLI portal. DOLI issues the permits [10]. We are the orchestration layer that prepares the teen *before* they hit the portal, preventing the common failure case of applying without a firm job offer [1].
* **Impact:** We measure success through process KPIs, not empty promises. Our metrics will track the percentage of 14-15-year-old users who successfully confirm a job offer and click through to the DOLI electronic portal, aiming to increase the use of the 24-hour electronic path over the 10-day manual path [1] [10].

## Continuation Pitch (30 seconds)

**Speaker:** "A civic tech tool dies without a community steward. We aren't just pitching software; we are pitching a 90-day pilot with a real partner. The Boys & Girls Clubs of Metro Richmond (BGCMR) already operates the Ready2Win teen workforce development program [6]. We propose handing off content governance and user testing to BGCMR, specifically aligning with their Life & Work Readiness leadership [5]. Because the tool relies on canonical links rather than a heavy database, it requires less than 0.25 FTE to maintain, making it a sustainable addition to their existing career readiness programming [17]."

## Anticipated Judge Questions and Responses

* **Q: How do you ensure the rules are current?**
 * **A:** We use visible "last-checked" stamps, a weekly automated link health checker, and a quarterly review log. We don't host the laws; we link to them.
* **Q: Why not just build a job board?**
 * **A:** Job boards for minors carry high liability and go stale quickly. Our value is compliance gating and routing to official flows, which actually solves the bottleneck for employers.
* **Q: Do 16 and 17-year-olds even need this tool?**
 * **A:** Yes. While they don't need an Employment Certificate in Virginia, they are still legally barred from hazardous occupations under state and federal law [9] [2]. The tool helps them identify safe roles.
* **Q: What about transportation costs?**
 * **A:** GRTC is currently zero fare [3], and RPS students have historically had unlimited local rides [12]. We integrate this directly into the planning step.
* **Q: What if you want to add user accounts later?**
 * **A:** We would trigger a formal Data Protection Assessment and build verifiable parental consent flows to comply with the VCDPA and COPPA [4] [13].

## Source Map and Compliance Matrix

### Official Sources Relied Upon

| Source | What It Covers | How We Use It |
| :--- | :--- | :--- |
| DOLI Youth Employment | 14-15 certificate requirements; 3-party e-process; ~24h review; manual path [1] [10] | Permit gating, timelines, deep links |
| U.S. DOL YouthRules / Fact Sheet #43 | Hours limits (14-15); prohibited tasks; non-hazardous standards [7] [2] | Schedule validator; job eligibility logic |
| VCDPA (Code of Virginia) | Child data protections; consent; geolocation limits; $7,500/violation enforcement [4] [16] | Privacy-by-default design; future DPA readiness |
| GRTC Transit | Zero-fare operations; rider guides [3] | Transit planning step |
| BGCMR | Local workforce readiness partner (Ready2Win) [5] [6] | Continuation and stewardship strategy |

*Takeaway: Every feature in the tool maps directly to a canonical, verifiable source, ensuring credibility with judges and users.*

### Age-Based Compliance Matrix

| Age | Work Permit Needed? | Hours Limits | Occupation Limits |
| :--- | :--- | :--- | :--- |
| 14–15 | Yes (DOLI e-certificate preferred) [1] | ≤3 hrs school days; ≤18 hrs/week in school; 7 a.m.–7 p.m. (9 p.m. summer) [7] [8] | No hazardous; no power-driven machinery; no manufacturing [7] |
| 16–17 | No [9] | No federal hour caps [2] | No hazardous occupations under 18 [9] [2] |
| 18+ | No | None | None [7] |

*Takeaway: This matrix drives the conditional logic of the application, ensuring users only see information relevant to their specific legal bracket.*

## Inferences (Clearly Labeled)
* **Inference:** Teens benefit from a transit step because zero fare reduces a barrier; adding route planning likely increases show-up reliability for first shifts.
* **Inference:** A partner like BGCMR can maintain content governance with minimal staff time (≤0.25 FTE) because the tool links to canonical sources rather than hosting volatile datasets.
* **Inference:** A visible "strictest rule wins" policy and on-screen citations increase employer and parent trust, reducing disputes during onboarding.

## Unknowns
* **RPS Transit Specifics:** The current operational details of the RPS-specific ridership program pages (historical posts exist [12]; system is zero fare today [3]). We must verify current student ID uses before referencing specifics in-app.
* **DOLI Updates:** The frequency of changes to DOLI forms/links. We need to confirm if webhook or RSS options exist; otherwise, we will rely on weekly automated link audits.
* **Employer Adoption:** Local employer willingness to provide the "Intent to Employ" digitally. We need to identify 3–5 pilot employers to test the end-to-end certificate flow messaging.
* **Language Needs:** The need for Spanish and other language support at launch. We will confirm this with the BGCMR user base and budget for translation if necessary.

## References

1. *DOLI – Virginia Department of Labor and Industry  - Youth Employment*. https://doli.virginia.gov/programs/labor-law/youth-employment/
2. *Fact Sheet #43: Child Labor Provisions of the Fair Labor Standards Act (FLSA) for Nonagricultural Occupations | U.S. Department of Labor*. https://www.dol.gov/agencies/whd/fact-sheets/43-child-labor-non-agriculture
3. *How To Ride*. https://www.ridegrtc.com/rider-guide/how-to-ride/
4. *Code of Virginia Code - Chapter 53. Consumer Data Protection Act*. https://law.lis.virginia.gov/vacodefull/title59.1/chapter53/
5. *Teen & Community Center — Boys & Girls Clubs of Metro Richmond*. https://www.bgcmr.org/teen-community-center
6. *Working Together for a Stronger Workforce — Boys & Girls Clubs of Metro Richmond*. https://www.bgcmr.org/stories/2018/7/19/working-together-for-a-stronger-workforce
7. *Non-Agricultural Jobs - 14-15 | U.S. Department of Labor*. https://www.dol.gov/agencies/whd/youthrules/young-workers/non-ag-14-15
8. *Rules and Regulations for Youth Employment | Youth.gov*. https://youth.gov/youth-topics/youth-employment/rules-and-regulations-youth-employment
9. *Teens and Employment – Virginia Rules*. https://virginiarules.org/varules_topics/teens-and-employment/
10. *VIRGINIA DEPARTMENT OF LABOR AND INDUSTRY*. https://townhall.virginia.gov/L/GetFile.cfm?File=C:%5CTownHall%5Cdocroot%5CGuidanceDocs%5C181%5CGDoc_DOLI_3197_v3.pdf
11. *What jobs and hours can teens work?*. https://www.dol.gov/sites/dolgov/files/WHD/child-labor/child-labor2023-educators-minors-parents.pdf
12. *Support Richmond Public Schools | Richmond Public-SchoolsStudent Pass Program Update:  | Facebook*. https://www.facebook.com/groups/969056046503304/posts/1954072521334980/
13. *Heightened Privacy Protections for Children in Virginia | Davis Wright Tremaine*. https://www.dwt.com/blogs/privacy--security-law-blog/2024/05/virginia-data-privacy-law-amended-for-under-18
14. *SB783 - 2025 Regular Session*. https://lis.virginia.gov/bill-details/20251/SB783
15. *Virginia AG to Enforce VCDPA Provisions Restricting Minors’ Use of Social Media*. https://www.hunton.com/privacy-and-cybersecurity-law-blog/virginia-ag-to-enforce-vcdpa-provisions-restricting-minors-use-of-social-media
16. *Virginia Consumer Data Protection Act*. https://www.oag.state.va.us/consumer-protection/files/tips-and-info/Virginia-Consumer-Data-Protection-Act-Summary-2-2-23.pdf
17. *Workforce Readiness*. https://www.bgcrichmond.org/s/workforce-readiness