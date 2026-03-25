# F5 Strategic Opportunities: Partner and Buy vs. Build (2025-2026)

## Executive Summary

As of early 2026, F5 has successfully transitioned its strategic focus toward hybrid multi-cloud architectures, enterprise AI, and platform convergence. Driven by the launch of the Application Delivery and Security Platform (ADSP), F5 achieved $3.09 billion in FY2025 revenue, representing a 10% annual growth rate [1]. Rather than building every capability in-house, F5 is aggressively leveraging a "partner and buy" strategy to fill functional gaps, particularly in AI runtime security and specialized infrastructure integrations. This document outlines F5's current roadmap, highlighting core internal development areas versus strategic ecosystem partnerships and acquisitions.

## Financial and Market Momentum

F5's recent financial performance validates its converged platform strategy, with strong growth in systems revenue driven by AI and hybrid cloud tech refreshes. 

| Metric | FY2025 Performance | Q1 2026 Performance | Key Drivers |
| :--- | :--- | :--- | :--- |
| **Total Revenue** | $3.09 billion (10% YoY growth) | $822 million (7% YoY growth) | Hybrid multi-cloud adoption, AI investments, and platform convergence [2] [1]. |
| **Systems Revenue** | Not specified | $218 million (37% YoY growth) | Tech refresh, capacity expansion for AI, and hybrid multi-cloud [2]. |
| **Software Revenue** | $803 million (9% YoY growth) | $192 million (8% YoY decline) | Expected decline against exceptionally strong Q1 2025 results; subscription software grew 1% [2] [1]. |
| **Services Revenue** | Not specified | $412 million (4% YoY growth) | Maintenance and recurring service models [2]. |

*F5's recurring revenue now accounts for 69% of total revenue, providing a stable foundation as the company navigates near-term sales cycle disruptions related to security assessments [2] [1].*

## Core "Build" Initiatives: The ADSP and AI Integration

F5 is focusing its internal engineering resources on converging its flagship products into the Application Delivery and Security Platform (ADSP) and embedding AI capabilities across its portfolio.

### BIG-IP and High-Throughput AI Workloads
F5 has positioned BIG-IP as a critical component for AI data delivery. In November 2025, F5 launched BIG-IP version 21.0, which natively supports the Model Context Protocol (MCP) and S3 interfaces [2]. This internal build addresses the terabit-scale ingestion requirements of multimodal AI data, solving throughput bottlenecks that traditional infrastructure cannot handle [2]. Furthermore, F5 is bringing API discovery capabilities from its Distributed Cloud directly to on-premises BIG-IP deployments [2].

### AI Assistants Across the Portfolio
Following the introduction of the AI assistant for F5 Distributed Cloud Services in December 2024, F5 introduced an AI assistant for F5 NGINX One at AppWorld 2025 [3]. Powered by a large language model specifically trained for NGINX, this tool provides contextually aware guidance to trim hours from troubleshooting [3]. F5 plans to expand this by bringing an AI assistant to BIG-IP later in the year [3].

## "Do Not Build": Strategic Partnerships and Ecosystem

To accelerate customer adoption and avoid reinventing specialized technologies, F5 launched the F5 ADSP Partner Program in November 2025, replacing the legacy Technology Alliance Program (TAP) [4]. This program provides pre-validated integrations without the need for formal certification, allowing F5 to rely on partners for adjacent security and infrastructure capabilities [4].

| Partner | Integration Focus | Strategic Value (Why Partner vs. Build) |
| :--- | :--- | :--- |
| **NVIDIA** | BIG-IP Next for Kubernetes on BlueField-3 DPUs | Leverages NVIDIA's hardware acceleration for large-scale AI infrastructures, improving performance without F5 building custom silicon [3]. |
| **Equinix** | Distributed Cloud on Network Edge Platform | Simplifies deployment of secure applications across hybrid environments using Equinix's global infrastructure [3]. |
| **AppViewX** | Centralized orchestration | Delivers automated certificate and app service management across distributed environments [3] [4]. |
| **CrowdStrike & OPSWAT** | Advanced Threat Protection | Integrates specialized endpoint and malware security directly into the ADSP ecosystem [4]. |
| **Red Hat & Nutanix** | Kubernetes and OpenShift | Combines NGINX high-performance delivery with enterprise Kubernetes management platforms [3] [4]. |

*By leveraging these Select partners (which also include DigiCert, Kasm Technologies, KeyFactor, and MazeBolt), F5 allows customers to fill technical gaps and reduce operational risk without F5 having to divert R&D from its core traffic management and API security competencies [4].*

## "Do Not Build": Strategic Acquisitions

When critical new technology paradigms emerge that require immediate market presence, F5 has opted to buy rather than build. 

### CalypsoAI and AI Runtime Security
As generative AI systems access sensitive data, security and compliance have become bottlenecks [2]. Rather than building a native AI security guardrail system from scratch, F5 acquired CalypsoAI to deliver end-to-end AI runtime protection [4]. This acquisition has already yielded early customer adoption, allowing F5 to safeguard AI applications, APIs, and models from prompt injection and data leaks immediately [2].

## References

1. *FY25 Revenue of $3.1 Billion Reflects 10% Annual Growth ...*. https://www.f5.com/company/news/press-releases/earnings-fy25-q4
2. *F5 (FFIV) Q1 2026 Earnings Call Transcript | The Motley Fool*. https://www.fool.com/earnings/call-transcripts/2026/01/27/f5-ffiv-q1-2026-earnings-call-transcript/
3. *Six Takeaways from F5's Flagship AppWorld Conference | F5*. https://www.f5.com/company/blog/six-takeaways-from-f5s-flagship-appworld-conference
4. *F5 ADSP Partner Program streamlines adoption of F5 platform*. https://www.f5.com/company/blog/f5-adsp-partner-program-streamlines-adoption-of-f5-platform