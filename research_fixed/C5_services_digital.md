# C5 Services – Digital Cloud Offerings

*Version: 2026-03* 

---

## 1️⃣ Overview

The **Cloud Computing Compliance Criteria Catalogue (C5)** is Germany’s baseline security standard for public-cloud services. First published by the **Bundesamt für Sicherheit in der Informationstechnik (BSI)** in 2016 and updated to **C5:2020** in 2020, it defines 125 detailed controls across 17 security domains — physical security, access control, encryption, vulnerability management, etc [1] [2]. The catalogue is mandatory for German federal agencies and increasingly adopted by private-sector organisations that handle regulated data [3] [4]. 

> **Why it matters:** C5 attestation gives customers documented evidence that a cloud provider meets a rigorous, audit-backed security baseline, reducing legal-compliance risk and simplifying procurement for German-centric workloads [2]. 

---

## 2️⃣ Scope of Digital Services

C5-certified providers must publish a **service-level description** that discloses data-location, jurisdiction, existing certifications and any additional controls [2]. The most widely-used public-cloud platforms now list the services that are **in-scope** for C5. 

### 2.1 AWS – Services in Scope (as of Nov 2025)

| Service Category | Representative Services (✓ = in-scope) | Note |
|------------------|----------------------------------------|------|
| **Compute** | Amazon EC2 ✓, AWS Lambda ✓, AWS Batch ✓ | All core compute services are covered [5] |
| **Storage** | Amazon S3 ✓, Amazon EFS ✓, Amazon FSx ✓ | Data-residency disclosed per region [5] |
| **Database** | Amazon Aurora ✓, Amazon RDS ✓, Amazon DynamoDB ✓ | Encryption-at-rest & in-transit controls applied [5] |
| **Analytics & AI** | Amazon Athena ✓, Amazon SageMaker ✓, Amazon Kinesis Data Analytics ✓ | Some AI-model-training features excluded (see AWS docs) [5] |
| **Networking** | Amazon VPC ✓, AWS CloudFront ✓, AWS Transit Gateway ✓ | Network-segmentation and traffic-filtering controls [5] |
| **Security & Identity** | AWS IAM ✓, AWS KMS ✓, AWS GuardDuty ✓ | Integrated with C5-required logging [5] |
| **Management** | AWS CloudTrail ✓, AWS Config ✓, AWS Systems Manager ✓ | Auditable configuration-change tracking [5] |
| **Application Integration** | Amazon SQS ✓, Amazon SNS ✓, Amazon EventBridge ✓ | Messaging services meet data-integrity requirements [5] |
| **Migration** | AWS Database Migration Service ✓, AWS Server Migration Service ✓ | Supports secure data-transfer processes [5] |
| **Developer Tools** | AWS CodeBuild ✓, AWS CodePipeline ✓, AWS CodeCommit ✓ | Build-pipeline security aligned with C5 controls [5] |

*Source: AWS “Services in Scope by Compliance Program – C5” (last updated Nov 2025) [5].*

### 2.2 Microsoft Azure – In-Scope Services

| Service | In-Scope? | Key C5-relevant feature |
|--------|------------|--------------------------|
| Azure Virtual Machines | ✓ | Disk encryption, region-level data residency |
| Azure Blob Storage | ✓ | Immutable storage + customer-controlled keys |
| Azure SQL Database | ✓ | Transparent data encryption, audit logging |
| Azure Kubernetes Service (AKS) | ✓ | Network policies, role-based access |
| Azure Active Directory | ✓ | Multi-factor authentication, conditional access |
| Azure DevOps | ✓ | Secure pipelines, artifact signing |
| Azure Logic Apps | ✓ | Data-flow traceability |

*Source: Microsoft Learn C5 offering page [3].*

### 2.3 Google Cloud – In-Scope Services

| Service | In-Scope? | C5-aligned control |
|--------|------------|--------------------|
| Compute Engine | ✓ | Shielded VMs, CMEK |
| Cloud Storage | ✓ | Dual-region storage, retention policies |
| BigQuery | ✓ | Column-level security, audit logs |
| Cloud SQL | ✓ | Automated backups, encryption |
| Anthos | ✓ | Hybrid-cloud policy enforcement |
| Cloud Identity & Access Management | ✓ | Fine-grained IAM roles |

*Source: Google Cloud C5 attestation page [4].*

---

## 3️⃣ Compliance Controls — What Is Audited?

| Domain (17) | Example Control | Typical Implementation |
|------------|----------------|------------------------|
| **Physical Security** | Secure data-center access | Biometric entry, CCTV [1] |
| **Access Control** | Least-privilege IAM | Role-based policies, MFA [1] |
| **Encryption** | Data-at-rest & in-transit | Customer-managed keys (CMK) [1] |
| **Vulnerability Management** | Patch cadence ≤ 30 days | Automated OS patching [1] |
| **Incident Management** | Defined response workflow | 24-hour SLA for high-severity |
| **Data Location** | Jurisdiction declaration | Region-level tags in service contracts [2] |
| **Audit & Logging** | Immutable log storage | CloudTrail/Monitor with retention ≥ 1 yr |
| **Business Continuity** | Disaster-recovery testing | RTO ≤ 4 h, RPO ≤ 15 min |
| **Third-Party Assurance** | Cross-certification (SOC 2, ISO 27001) | Combined audit reports [3] |
| *(…and 8 additional domains defined by BSI)* | | |

> **Key Insight:** All three major CSPs map their native security features directly to the 125 C5 controls, allowing customers to reuse existing cloud-native controls for C5 compliance rather than building custom safeguards [1] [3].

---

## 4️⃣ Attestation Process

1. **Self-Assessment** – Provider completes the BSI-provided questionnaire, mapping each service to the C5 control catalogue. 
2. **Independent Audit** – A certified audit firm performs a **Type 2** audit, testing design and operational effectiveness of controls [6]. 
3. **Report Issuance** – The **C5:2020** attestation is published on the provider’s compliance portal (AWS Artifact, Microsoft Trust Center, Google Cloud Compliance Reports) [4] [2]. 
4. **Customer Review** – Organisations download the report, verify service coverage, and incorporate it into their own risk-assessment frameworks. 

*Typical timeline:* 3–6 months from initial request to final report. 

---

## 5️⃣ Business Benefits

| Benefit | Description | Example Impact |
|---------|-------------|----------------|
| **Regulatory Acceptance** | Recognised by German federal procurement | Faster contract award for public-sector projects [2] |
| **Risk Reduction** | Independent third-party evidence of control effectiveness | Lower insurance premiums |
| **Operational Efficiency** | Single audit covers 125 controls across 17 domains | Consolidates SOC 2, ISO 27001 reporting [3] |
| **Market Differentiation** | Demonstrates commitment to EU-centric data sovereignty | Attracts German-based customers |

---

## 6️⃣ Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| **Scope Creep** – Using services not listed as in-scope | Medium | Non-compliant data processing | Verify service version & region before deployment [5] |
| **Audit Lag** – Attestation renewal delays (annual) | Low | Temporary loss of compliance status | Maintain a **continuous compliance dashboard** (e.g., AWS Config Rules) |
| **Vendor Lock-In** – Over-reliance on a single CSP’s C5 report | Medium | Reduced bargaining power | Adopt a **multi-cloud strategy** with cross-CSP C5 coverage |
| **Misinterpretation of Controls** – Assuming CSP-level controls cover customer-specific processes | Medium | Control gaps in customer environment | Perform a **customer-level risk assessment** on top of CSP attestation [3] |

---

## 7️⃣ Recommendations for Organisations

1. **Map Business Requirements to C5 Domains** – Use the 17-domain matrix to identify which controls are critical for your data-type (e.g., PII, health) [1]. 
2. **Select In-Scope Services Only** – Cross-check the provider’s service-level description (AWS, Azure, Google) before provisioning [3] [4] [5]. 
3. **Leverage Provider-Hosted Attestations** – Pull the latest C5 report from the CSP’s compliance portal and store it in your governance repository [2]. 
4. **Integrate Continuous Monitoring** – Enable native logging (CloudTrail, Azure Monitor, GCP Audit Logs) and map logs to the C5 control set for real-time compliance validation. 
5. **Plan for Renewal** – Track attestation expiry dates (typically 12 months) in your compliance calendar; start the audit process 90 days prior. 

---

## 8️⃣ References

1. Microsoft Learn – *Cloud Computing Compliance Criteria Catalog (C5)*, 2025-03 [3]
2. Google Cloud – *BSI C5 2020 attestation* [4]
3. Amazon Web Services – *Services in Scope by Compliance Program – C5*, 2025-11 [5]
4. BSI – *C5:2020 – Criteria Catalogue* (official English version) [7]

## References

1. *C5 Certification in Digital Health: What you need to know - Chino.io*. https://www.chino.io/post/c5-certification-digital-health-compliance-guide
2. *Cloud Computing Compliance Criteria Catalogue (C5) - AWS*. https://aws.amazon.com/compliance/bsi-c5/
3. *Cloud Computing Compliance Criteria Catalog (C5) - Microsoft Learn*. https://learn.microsoft.com/en-us/compliance/regulatory/offering-c5-germany
4. *BSI C5:2020 | Google Cloud*. https://cloud.google.com/security/compliance/bsi-c5
5. *AWS Services in Scope by Compliance Program*. https://aws.amazon.com/compliance/services-in-scope/C5/
6. *2024 C5 Type 2 attestation report available with 179 services in scope*. https://aws.amazon.com/blogs/security/2024-c5-type-2-attestation-report-available-with-179-services-in-scope/
7. *C5 criteria catalogue - BSI*. https://www.bsi.bund.de/EN/Themen/Unternehmen-und-Organisationen/Informationen-und-Empfehlungen/Empfehlungen-nach-Angriffszielen/Cloud-Computing/Kriterienkatalog-C5/kriterienkatalog-c5_node.html