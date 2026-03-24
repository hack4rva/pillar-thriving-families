# F5 Strategic Opportunities: Partner and Buy vs. Build (2025 to 2026)

## Executive Summary

As of early 2026, F5 has successfully transitioned its strategic focus toward hybrid multi-cloud architectures, enterprise AI, and platform convergence. Driven by the launch of the Application Delivery and Security Platform (ADSP), F5 achieved $3.09 billion in FY2025 revenue, representing a 10% annual growth rate [1]. Rather than building every capability in-house, F5 is aggressively leveraging a "partner and buy" strategy to fill functional gaps, particularly in AI runtime security and specialized infrastructure integrations. This document outlines F5's current roadmap, highlighting core internal development areas versus strategic ecosystem partnerships and acquisitions.

## Financial and Market Momentum

F5's recent financial performance validates its converged platform strategy, with strong growth in systems revenue driven by AI and hybrid cloud tech refreshes. 

| Metric | FY2025 Performance | Q1 2026 Performance | Key Drivers |
| :--- | :--- | :--- | :--- |
| **Total Revenue** | $3.09 billion (10% YoY growth) [1] | $822 million (7% YoY growth) [2] | Hybrid multi-cloud adoption, AI investments, and platform convergence. |
| **Systems Revenue** | $706 million (31% YoY growth) [1] | $218 million (37% YoY growth) [2] | Tech refresh, capacity expansion for AI, and hybrid multi-cloud. |
| **Software Revenue** | $803 million (9% YoY growth) [1] | $192 million (8% YoY decline) [2] | Expected decline against exceptionally strong Q1 2025 results; subscription software grew 1%. |
| **Services Revenue** | $1.58 billion (2% YoY growth) [1] | $412 million (4% YoY growth) [2] | Maintenance and recurring service models. |

*F5's recurring revenue now accounts for 69% of total revenue, providing a stable foundation as the company navigates near-term sales cycle disruptions related to security assessments [3] [4].*

## Core "Build" Initiatives: The ADSP and AI Integration

F5 is focusing its internal engineering resources on converging its flagship products into the Application Delivery and Security Platform (ADSP) and embedding AI capabilities across its portfolio.

### BIG-IP and High-Throughput AI Workloads
F5 has positioned BIG-IP as a critical component for AI data delivery. In November 2025, F5 launched BIG-IP version 21.0, which natively supports the Model Context Protocol (MCP) and S3 interfaces [5]. This internal build addresses the terabit-scale ingestion requirements of multimodal AI data, solving throughput bottlenecks that traditional infrastructure cannot handle [5]. Furthermore, F5 is bringing API discovery capabilities from its Distributed Cloud directly to on-premises BIG-IP deployments [6].

### AI Assistants Across the Portfolio
Following the introduction of the AI assistant for F5 Distributed Cloud Services in December 2024 [7], F5 introduced an AI assistant for F5 NGINX One at AppWorld 2025 [8]. Powered by a large language model specifically trained for NGINX, this tool provides contextually aware guidance to trim hours from troubleshooting [8]. F5 plans to expand this by bringing an AI assistant to BIG-IP later in the year [9].

## "Do Not Build": Strategic Partnerships and Ecosystem

To accelerate customer adoption and avoid reinventing specialized technologies, F5 launched the F5 ADSP Partner Program in November 2025, replacing the legacy Technology Alliance Program (TAP) [10] [11]. This program provides pre-validated integrations without the need for formal certification, allowing F5 to rely on partners for adjacent security and infrastructure capabilities [10].

| Partner | Integration Focus | Strategic Value (Why Partner vs. Build) |
| :--- | :--- | :--- |
| **NVIDIA** | BIG-IP Next for Kubernetes on BlueField DPUs | Leverages NVIDIA's hardware acceleration for large-scale AI infrastructures, improving performance without F5 building custom silicon [12]. |
| **Equinix** | Distributed Cloud on Network Edge Platform | Simplifies deployment of secure applications across hybrid environments using Equinix's global infrastructure [13]. |
| **AppViewX** | Centralized orchestration | Delivers automated certificate and app service management across distributed environments [11]. |
| **CrowdStrike & OPSWAT** | Advanced Threat Protection | Integrates specialized endpoint and malware security directly into the ADSP ecosystem [11]. |
| **Red Hat & Nutanix** | Kubernetes and OpenShift | Combines NGINX high-performance delivery with enterprise Kubernetes management platforms [14]. |

*By leveraging these Select partners (which also include DigiCert, Kasm Technologies, KeyFactor, and MazeBolt), F5 allows customers to fill technical gaps and reduce operational risk without F5 having to divert R&D from its core traffic management and API security competencies [11].*

## "Do Not Build": Strategic Acquisitions

When critical new technology paradigms emerge that require immediate market presence, F5 has opted to buy rather than build. 

### CalypsoAI and AI Runtime Security
As generative AI systems access sensitive data, security and compliance have become bottlenecks [15]. Rather than building a native AI security guardrail system from scratch, F5 acquired CalypsoAI to deliver end-to-end AI runtime protection [16]. This acquisition has already yielded early customer adoption, allowing F5 to safeguard AI applications, APIs, and models from prompt injection and data leaks immediately [15] [17].

**Description:** Analysis of F5's 2025 to 2026 "partner and buy vs. build" strategy, with verified financial results and official program/product announcements supporting decisions around ADSP, BIG-IP v21.0, AI assistants, partner integrations, and the CalypsoAI acquisition.

**Information of interest:**
**Item:** output
**Description:** F5's strategic execution demonstrates a clear delineation between core internal development (ADSP, BIG-IP v21.0, AI Assistants) and external ecosystem expansion (CalypsoAI acquisition, ADSP Partner Program), driving a 10% YoY revenue growth in FY2025 and establishing a 69% recurring revenue base.

## References

1. *F5 Reports Strong Fourth Quarter Results with 8% Revenue Growth; FY25 Revenue  of $3.1 Billion Reflects 10% Annual Growth, Driven by Transformative Industry Trends | F5*. https://www.f5.com/company/news/press-releases/earnings-fy25-q4
2. *F5 Reports Strong First Quarter Results with 7% Revenue Growth  Including 11% Product Growth | F5*. https://www.f5.com/company/news/press-releases/earnings-q1-fy26
3. *F5, Inc. (NASDAQ:FFIV) Q1 2026 earnings call transcript*. https://www.msn.com/en-us/money/companies/f5-inc-nasdaqffiv-q1-2026-earnings-call-transcript/ar-AA1VaoSn?ocid=BingNewsVerp
4. *F5 (FFIV) Q1 2026 Earnings Call Transcript | The Motley Fool*. https://www.fool.com/earnings/call-transcripts/2026/01/27/f5-ffiv-q1-2026-earnings-call-transcript/
5. *F5 launches BIG-IP v21.0 to power application delivery and security in the AI era | F5*. https://www.f5.com/company/news/press-releases/f5-launches-big-ip-v21-0-to-power-application-delivery-and-security-in-the-ai-era
6. *API security without compromise: Introducing flexible new discovery options with F5 API security | F5*. https://www.f5.com/company/blog/api-security-without-compromise-introducing-flexible-new-discovery
7. *Introducing the AI Assistant for F5 Distributed Cloud Services | F5*. https://www.f5.com/company/blog/introducing-ai-assistant
8. *Introducing the AI Assistant for F5 NGINX One | F5*. https://www.f5.com/company/blog/nginx/introducing-the-ai-assistant-for-f5-nginx-one
9. *F5 expands application security with new platform and AI-powered automation tools - SiliconANGLE*. https://siliconangle.com/2025/02/26/f5-expands-application-security-new-platform-ai-powered-automation-tools/
10. *F5 ADSP Partner Program streamlines adoption of F5 ...*. https://www.f5.com/company/blog/f5-adsp-partner-program-streamlines-adoption-of-f5-platform
11. *F5 launches ADSP Partner Program with leading technology companies to revolutionize application delivery and security  | F5*. https://www.f5.com/company/news/press-releases/f5-launches-adsp-partner-program-with-leading-technology-companies-to-revolutionize-application
12. *F5 Leverages NVIDIA RTX PRO Server to Deliver High-Performance Enterprise AI Infrastructure | F5*. https://www.f5.com/company/news/press-releases/f5-nvidia-rtx-pro-server-enterprise-ai-infrastructure
13. *F5 and Equinix unite to simplify secure multicloud application delivery | F5*. https://www.f5.com/company/blog/f5-and-equinix-unite-to-simplify-secure-multicloud-application-delivery
14. *F5*. https://www.nutanix.com/partners/technology-alliances/f5
15. *F5 to acquire CalypsoAI to bring advanced AI guardrails to large enterprises | F5*. https://www.f5.com/company/news/press-releases/f5-to-acquire-calypsoai-to-bring-advanced-ai-guardrails-to-large-enterprises
16. *ffiv-20250930*. https://www.sec.gov/Archives/edgar/data/1048695/000104869525000157/ffiv-20250930.htm
17. *F5 completes acquisition of CalypsoAI, introduces F5 AI ...*. https://www.f5.com/company/blog/what-are-ai-guardrails