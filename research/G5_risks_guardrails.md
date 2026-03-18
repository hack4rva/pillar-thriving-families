---
title: "Building Safe-by-Design Thriving Families Tools: Guardrails That Ship"
pillar: thriving-families
section: G
problem_statement: general
tags:
  - guardrails
  - safe-by-design
  - content limits
  - AI constraints
  - regulatory compliance
  - hackathon checklist
summary: "Comprehensive guardrails checklist for Thriving Families tools covering content limits, user flow constraints, AI behavior limits, data display rules, and review checkpoints implementable within a hackathon timeline."
geography: Richmond, VA
source: parallel-ai
status: raw
related_reports:
  - G1_risks_minor_data_privacy
  - G2_risks_health_claims
  - F5_opportunities_do_not_build
---

# Building Safe-by-Design Thriving Families Tools: Guardrails That Ship

## Executive Summary

The Thriving Families hackathon presents a unique challenge: building innovative digital tools for vulnerable populations (youth and maternal health) while navigating a complex web of federal and state regulations. The fastest path to a successful, deployable prototype is not building the most complex AI, but rather designing a tool that inherently avoids regulatory tripwires. 

The highest risks cluster around five areas: making eligibility determinations, providing clinical advice, mishandling youth data, unauthorized sharing of health data, and deploying hiring-related AI. By implementing strict "never build" constraints—such as banning individualized clinical guidance and prohibiting the storage of minors' Personally Identifiable Information (PII)—teams can bypass the most severe legal liabilities. 

Success requires a content-forward approach. Tools should act as navigators and educators, relying on structured citations and clear disclaimers rather than acting as decision-makers. A responsible demo will explicitly acknowledge these boundaries, utilizing phase banners, seeded data, and a clear articulation of failure modes and mitigations.

## Risk Landscape Synthesis — Where Prototypes Most Often Go Wrong

The regulatory environment for digital tools touching health, employment, and benefits is unforgiving of scope creep. When tools transition from providing information to making decisions or recommendations, they trigger stringent oversight.

### Five High-Risk Zones

1. **Eligibility Determinations:** Government pre-screeners, such as the USDA SNAP tool, are explicitly designed as estimators, not determiners [1]. If a tool claims to determine eligibility, it assumes the legal authority of the agency, creating massive liability.
2. **Clinical Advice:** The FDA regulates software that meets the definition of a medical device. To remain outside this scope (as "Non-Device CDS"), software must allow users to review the basis of recommendations so they do not rely primarily on the tool for clinical diagnosis or treatment decisions [2].
3. **Health Data Sharing:** The FTC's updated Health Breach Notification Rule (HBNR) applies to health apps not covered by HIPAA [3] [4]. Crucially, the FTC defines a "breach of security" to include unauthorized disclosures, such as sharing health data with advertising platforms [3] [4].
4. **Youth Data:** Tools targeting minors face heightened privacy and safety expectations. The NTIA emphasizes minimizing data collection and designing for youth safety [5].
5. **Hiring-Related AI:** The use of automated employment decision tools (AEDTs) is heavily scrutinized. NYC Local Law 144 requires bias audits and public notices for such tools [6]. Furthermore, the EEOC warns that algorithmic tools can result in disparate impact under Title VII or screen out individuals with disabilities under the ADA [7] [8].

### Cautionary Enforcement Cases

Recent FTC enforcement actions highlight the severe consequences of unauthorized data sharing. Settlements with GoodRx and Easy Healthcare (Premom) occurred because these companies failed to report that they shared consumers' health data with advertising platforms, violating their privacy promises and triggering the HBNR [3]. Similarly, the enforcement of NYC Local Law 144 demonstrates the growing regulatory focus on bias in automated employment tools [6].

## Cross-Cutting Language and UX Guardrails

Disclaimers are necessary but insufficient on their own; they must be paired with design guardrails and transparent citations to be effective.

### Universal Copy Components

Every user-facing page must include:
* **Phase Banner:** Use an "Alpha" or "Beta" banner to indicate the service is still being worked on [9] [10].
* **Scope Module:** Clearly state what the tool can and cannot do.
* **Last Updated Date:** Ensure content currency [11].
* **Visible Sources:** Demonstrate authoritativeness by including required links and clearly labeling non-governmental content [11].

### Required Disclaimer Language by Context

Different problem areas require specific disclaimer language to mitigate their unique risks.

| Context | Must-Say Disclaimer | Verify/Route Language | Emergency Language | Source Types to Cite |
| :--- | :--- | :--- | :--- | :--- |
| **Global** | "This is a prototype for informational purposes." | "Verify all information with official sources." | N/A |.gov,.edu, official program sites |
| **Maternal Health** | "This resource does not constitute advice from your physician... and it is not intended to replace the advice or counsel of a physician." [12] | "You should consult with, and rely only on the advice of, physicians..." [12] | "Call 911 for medical emergencies." | ACOG, FDA, CDC, local health depts |
| **Benefits Pre-Screener** | "This tool is only an estimator." [1] | "Contact the local agency to determine actual eligibility." [1] | N/A | State/Federal benefit portals (e.g., Benefits.gov) |
| **Youth Employment** | "Information provided is for educational purposes and does not guarantee employment." | "Verify specific labor rules with your state department of labor." | N/A | U.S. Department of Labor (YouthRules), State labor depts |

### Source Citation and Link Hygiene

Follow federal content guidelines to optimize for search and demonstrate authoritativeness [11]. Use the U.S. Web Design System’s identifier component to display required agency links [11]. When citing sources, follow established formats (e.g., APA, Chicago, MLA) and include the last modified date and a direct link [13].

## "Never Build" Features

Prohibiting a specific set of features prevents the majority of foreseeable regulatory and legal issues.

| Feature to Avoid | Why It's Risky | Safer Alternative | Evidence |
| :--- | :--- | :--- | :--- |
| **Eligibility Determinations** | Usurps agency authority; creates legal liability if incorrect. | Provide estimates and route to official agency for actual determination. | USDA SNAP pre-screener is explicitly an "estimator" [1]. |
| **Clinical Guidance/Diagnosis** | Triggers FDA medical device regulation if users rely primarily on the software [2]. | Provide educational information, cite sources, and state it is not medical advice [12]. | FDA CDS Guidance [2]; ACOG Disclaimer [12]. |
| **Health Data to Ads/Analytics** | Unauthorized disclosure constitutes a breach under the FTC HBNR [3]. | Use no third-party trackers; maintain strict data minimization. | FTC enforcement against GoodRx and Premom [3]. |
| **Automated Hiring Decisions/Rankings** | Triggers bias audit requirements (NYC LL144) and risks EEOC Title VII/ADA violations [6] [7] [8]. | Provide learning content and navigation assistance; do not rank or score candidates. | NYC DCWP [6]; EEOC Guidance [7] [8]. |
| **Storing PII for Minors** | Heightened privacy and safety obligations for youth data. | Default to no accounts, no storage, or anonymous use. | NTIA recommended practices [5]. |

## Features Requiring Legal or Expert Review

Some features offer significant value but require careful implementation and expert sign-off before deployment.

| Feature Concept | Risk Theme | Reviewer Needed | Pre-conditions to Proceed |
| :--- | :--- | :--- | :--- |
| **Benefits "Pre-Screener" Calculators** | Eligibility confusion | Program owner / Legal | Must include strong "estimator only" language and route to agency [1]. |
| **Symptom Education with Triage Links** | Medical scope creep | Clinical advisor | Must include "not medical advice" disclaimer, cite sources, and provide emergency links [12]. |
| **Job Matching Suggestions** | AEDT spillover | Employment counsel | Must not rank or score; must include transparency notes regarding how suggestions are generated [6]. |
| **Multilingual Content** | Accuracy risk | Language access lead | Must manually validate machine translations before publication [11]. |
| **Any Analytics** | Privacy/Security | Privacy officer | Must not collect PHI/PII; prefer self-hosted metrics to avoid third-party sharing [3]. |

## Data Protection and Privacy

A minimal data posture is a competitive advantage. Collecting less data means triggering fewer regulations and accelerating the approval process.

### Health Data: HBNR Do's and Don'ts

The FTC's Health Breach Notification Rule applies to vendors of personal health records (PHRs) and related entities not covered by HIPAA [3] [4] [14]. A "breach of security" includes unauthorized disclosures, not just hacks [3] [4]. Teams must avoid sharing health data with third-party advertising or analytics platforms and must have a plan for breach notification that includes contacting affected individuals, the FTC, and potentially the media [14].

### Youth Data: Safety and Minimization

For youth-facing tools, default to collecting no PII. Block account creation for minors where possible, and provide vetted helplines and resources.

### Model Privacy Notice and Dependency Allowlist

Utilize the ONC's Model Privacy Notice (MPN) generator to create a clear, understandable privacy policy [15]. Maintain a strict allowlist of pre-cleared SDKs and dependencies, explicitly disabling any ad tracking or unauthorized data export.

## Partners to Consult Before Public Deployment

Early alignment with stakeholders prevents costly rewrites and ensures the tool meets domain-specific requirements.

| Problem Area | Partners to Consult | What They Review |
| :--- | :--- | :--- |
| **Youth Employment** | State Labor Dept, School District CTE, Legal/Privacy | Compliance with state-specific youth labor rules; data minimization practices. |
| **Maternal Health** | Local Public Health, OB/GYN Advisor, Privacy Officer | Clinical accuracy of educational content; adherence to "Non-Device CDS" criteria; HBNR compliance. |
| **Benefits Navigation** | Agency Program Owner, Legal, Accessibility Lead | Accuracy of estimator logic; clarity of disclaimers; Section 508 compliance. |

## Responsible Demo Standards

A credible demo demonstrates an understanding of the regulatory landscape and prioritizes safety over flashy, high-risk features.

### Demo Checklist for Credibility and Safety

* **Alpha/Beta Banner:** Prominently displayed to indicate prototype status [9] [10].
* **No Live PII:** Use only seeded or offline data; disable input fields for real personal information.
* **Visible Citations:** Show how the tool links to authoritative sources [11].
* **Clear Disclaimers:** Demonstrate the presence of context-appropriate disclaimers (e.g., "estimator only," "not medical advice").

### Failure Modes and Mitigations Slide

Include a dedicated slide in the presentation that explicitly addresses potential risks:
* **Bias:** How the tool avoids disparate impact (e.g., by not ranking candidates).
* **Misinterpretation:** How UX design and disclaimers prevent users from mistaking estimates for determinations or education for medical advice.
* **Data Leakage:** How the minimal data architecture prevents unauthorized disclosures.

## Guardrail Checklist (Actionable Items)

**Pre-Demo Review:**
- [ ] Alpha/Beta phase banner is visible on all screens.
- [ ] "Not medical advice" disclaimer is present (if applicable).
- [ ] "Estimator only / Verify with agency" language is present (if applicable).
- [ ] Emergency routing (e.g., 911) is included for health-related flows.
- [ ] Tool does NOT make eligibility determinations.
- [ ] Tool does NOT provide individualized clinical diagnosis or treatment recommendations.
- [ ] Tool does NOT rank or score job candidates.
- [ ] Tool does NOT store PII for minors.
- [ ] No third-party advertising or analytics trackers are installed.
- [ ] All external links are clearly labeled and route to authoritative sources (.gov,.edu, official orgs).
- [ ] Demo uses ONLY seeded/fake data (no live PII).
- [ ] Presentation includes a "Failure Modes and Mitigations" slide.

## Inferences and Unknowns

### Inferences (Clearly Labeled)
* **Jurisdiction:** We infer the primary target is the United States, given the reliance on federal guidance (FTC, FDA, EEOC, USDA).
* **Audience:** We infer the tools will be directly user-facing (patients, youth, benefit seekers) rather than solely enterprise/employer-facing, necessitating strong consumer protection guardrails.
* **Scope:** We infer that hackathon teams are building prototypes, not production-ready systems, making phase banners and seeded data appropriate.

### Unknowns to Resolve Before Pilot
* **State-Specific Regulations:** While federal baselines are established, specific state laws regarding youth employment or health data privacy (e.g., CCPA/CPRA) need validation based on the deployment location.
* **Data Retention Requirements:** If a tool *must* store data temporarily for session management, the exact retention limits and deletion protocols must be defined.
* **Specific Agency Partnerships:** The exact government or non-profit partners for the pilot phase are unknown and will dictate final approval workflows.

## References

1. *
      Federal Register
       :: 
      Agency Information Collection Activities; Comment Request; Supplemental Nutrition Assistance Program Pre-Screening Tool
    *. https://www.federalregister.gov/documents/2017/12/08/2017-26494/agency-information-collection-activities-comment-request-supplemental-nutrition-assistance-program
2. *Clinical Decision Support Software - Guidance for Industry ...*. https://www.fda.gov/media/109618/download
3. *Updated FTC Health Breach Notification Rule puts new provisions in place to protect users of health apps and devices | Federal Trade Commission*. https://www.ftc.gov/business-guidance/blog/2024/04/updated-ftc-health-breach-notification-rule-puts-new-provisions-place-protect-users-health-apps
4. *FTC Finalizes Changes to the Health Breach Notification Rule | Federal Trade Commission*. https://www.ftc.gov/news-events/news/press-releases/2024/04/ftc-finalizes-changes-health-breach-notification-rule
5. *Industry’s Role in Promoting Kids’ Online Health, Safety, and Privacy: Recommended Practices for Industry | National Telecommunications and Information Administration*. https://www.ntia.gov/report/2024/kids-online-health-and-safety/online-health-and-safety-for-children-and-youth/taskforce-guidance/recommended-practices-for-industry
6. *Automated Employment Decision Tools (AEDT) - DCWP*. https://www.nyc.gov/site/dca/about/automated-employment-decision-tools.page
7. *EEOC Issues Title VII Guidance on Employer Use of AI, Other Algorithmic Decision-Making Tools | Insights | Mayer Brown*. https://www.mayerbrown.com/en/insights/publications/2023/07/eeoc-issues-title-vii-guidance-on-employer-use-of-ai-other-algorithmic-decisionmaking-tools
8. *U.S. EEOC and U.S. Department of Justice Warn against Disability Discrimination | U.S. Equal Employment Opportunity Commission*. https://www.eeoc.gov/newsroom/us-eeoc-and-us-department-justice-warn-against-disability-discrimination
9. *Phase banner – GOV.UK Design System*. https://design-system.service.gov.uk/components/phase-banner/
10. *Alpha and Beta Banners - Design guide - HSE*. http://design.hse.gov.uk/alpha-beta-banners.htm
11. *An introduction to content | Digital.gov*. https://digital.gov/resources/an-introduction-to-content
12. *Disclaimer | ACOG*. https://www.acog.org/womens-health/about-acog/disclaimer
13. *How to cite USA.gov | USAGov*. https://www.usa.gov/how-to-cite
14. *Complying with FTC’s Health Breach Notification Rule | Federal Trade Commission*. https://www.ftc.gov/business-guidance/resources/complying-ftcs-health-breach-notification-rule-0
15. *Model Privacy Notice (MPN) - ASTP - Assistant Secretary for Technology Policy*. https://healthit.gov/privacy-security/model-privacy-notice-mpn/