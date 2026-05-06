# Standards & API Reference

> Project: Applicant Tracking System · Generated: 2026-05-06

## Industry Standards & Specifications

### ISO Standards

**ISO/IEC 27001 — Information Security Management Systems**
- URL: https://www.iso.org/standard/27001
- The primary information security standard relevant to ATS platforms. Governs the protection of candidate records, user credentials, and communications within ATS systems. Multiple enterprise ATS providers (Workable, PageUp, iCIMS) hold ISO 27001 certification as a baseline enterprise requirement.

**ISO/IEC 27701 — Privacy Information Management**
- URL: https://www.iso.org/standard/71670.html
- Extension to ISO 27001 specifically for privacy information management. Directly relevant to ATS platforms that process personally identifiable information (PII) of candidates across multiple jurisdictions. Maps to GDPR controller and processor obligations.

**ISO 9001 — Quality Management Systems**
- URL: https://www.iso.org/standard/62085.html
- Governs the standardization of recruitment service workflows including job intake, candidate sourcing, screening, interview coordination, placement tracking, and feedback management. Applicable to ATS vendors and recruitment agencies using the platform.

**ISO/IEC 42001 — Artificial Intelligence Management Systems**
- URL: https://www.iso.org/standard/81230.html
- Emerging standard for responsible AI governance. Pinpoint ATS is among the first applicant tracking systems globally to achieve ISO/IEC 42001 certification. Critical for ATS platforms deploying AI screening, ranking, or decision-support features, particularly given the EU AI Act's August 2026 compliance deadline for high-risk HR AI systems.

**ISO/IEC 27017 — Cloud Security Controls**
- URL: https://www.iso.org/standard/43757.html
- Provides guidelines for information security controls applicable to cloud services. Relevant for SaaS ATS deployments where candidate data is stored and processed in cloud infrastructure.

---

### W3C & IETF Standards

**Schema.org JobPosting — Structured Data Vocabulary**
- URL: https://schema.org/JobPosting
- The de-facto structured data standard for job listings on the web. Maintained collaboratively by Google, Microsoft, Yahoo, and Yandex. ATS platforms that publish to career sites must emit JSON-LD JobPosting markup to be eligible for Google's rich job search results. Key properties include `title`, `description`, `employmentType`, `datePosted`, `validThrough`, `hiringOrganization`, `jobLocation`, `baseSalary`, and `directApply`.

**Google Structured Data — Job Posting Guidelines**
- URL: https://developers.google.com/search/docs/appearance/structured-data/job-posting
- Google's implementation guide for the Schema.org JobPosting type. ATS platforms generating job posting pages must comply with these guidelines to enable job listings in Google Search's job experience. Defines required vs. recommended properties and validation requirements.

**RFC 6749 — The OAuth 2.0 Authorization Framework**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- The foundation for delegated authorization used in ATS integrations. Required for partner/marketplace integrations where third-party tools access ATS data on behalf of recruiters (e.g., background check vendors, video interview platforms, HRIS systems).

**RFC 7519 — JSON Web Token (JWT)**
- URL: https://datatracker.ietf.org/doc/html/rfc7519
- Standard for compact, URL-safe tokens used in ATS authentication and API security. Used by OpenID Connect flows for identity propagation across ATS and integrated HR systems.

**RFC 7231 — Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content**
- URL: https://datatracker.ietf.org/doc/html/rfc7231
- Foundational HTTP semantics standard. All ATS REST APIs are built on HTTP, and correct implementation of verbs (GET, POST, PUT, PATCH, DELETE), status codes, and content negotiation is required for standards-compliant API design.

**RFC 8288 — Web Linking**
- URL: https://datatracker.ietf.org/doc/html/rfc8288
- Defines the `Link` header and link relation types used in paginated REST API responses (cursor-based and offset pagination patterns common in ATS APIs returning large candidate or application lists).

**W3C WCAG 2.1 (Web Content Accessibility Guidelines)**
- URL: https://www.w3.org/TR/WCAG21/
- Accessibility standard at Level AA is legally required in many jurisdictions for career sites and candidate application portals. ATS platforms and their job application forms must meet WCAG 2.1 AA to serve candidates with disabilities and to comply with the Americans with Disabilities Act (ADA) and similar legislation.

---

### Data Model & API Specifications

**HR Open Standards — Recruiting Specification v3.3**
- URL: https://www.hropenstandards.org/standards
- The primary industry standard for structured data interchange between ATS platforms, job boards, HRIS systems, and recruiting agencies. Key document types include:
  - `PositionOpening` — job requisition with role requirements, compensation, and application instructions
  - `Candidate` — structured applicant profile with education, experience, skills, and preferences
  - `SearchDocument` — query format for candidate searches between ATS and resume banks
  - `ApplicationForm` — standardized application submission format
  - `WorkerOnBoarding` — handoff data from ATS to HRIS upon hire
- Both JSON and XML schema formats are available for free download from HR Open Standards.

**HR Open Standards — Learning and Employment Record Resume Standard (LER-RS) v2**
- URL: https://www.hropenstandards.org/standards
- A skills-focused extension enabling verifiable credentials and digital badges within resume/candidate profile data. Allows ATS platforms to ingest and verify claimed skills and certifications cryptographically, relevant for AI-native ATS skill-matching features.

**HR Open Standards — Trusted Career Profile (TCP) v4.5**
- URL: https://www.hropenstandards.org/standards
- Released February 2026. Combines learning records with verifiable credentials into a portable, tamper-evident candidate record. Represents the emerging direction for credential-verified candidate profiles in future ATS systems.

**JSON Resume Schema v1.0.0**
- URL: https://jsonresume.org/schema / https://github.com/jsonresume/resume-schema
- Community-driven open standard for structuring resume data in JSON format. Machine-readable and widely supported by parsing tools and portfolio platforms. Relevant as an import/export format for candidate profiles in open-source ATS implementations.

**OpenAPI Specification (OAS) v3.1.0**
- URL: https://spec.openapis.org/oas/v3.1.0.html / https://www.openapis.org/
- The industry-standard format for describing RESTful APIs. All major ATS platforms (SmartRecruiters, Greenhouse via Harvest v3, iCIMS) publish or are moving toward OpenAPI-described endpoints. Key features in OAS 3.1 include full JSON Schema Draft 2020-12 compatibility, native webhook definitions, and improved support for API-first design. An AI-native ATS should publish its API surface as an OpenAPI 3.1 document.

---

### Security & Authentication Standards

**OAuth 2.0 (RFC 6749) + PKCE (RFC 7636)**
- URL: https://datatracker.ietf.org/doc/html/rfc7636
- PKCE (Proof Key for Code Exchange) is the required extension to OAuth 2.0 for public clients and modern single-page ATS applications. All ATS partner integrations (background screening, assessments, HRIS sync) should use OAuth 2.0 with PKCE for secure delegated access.

**OpenID Connect (OIDC) 1.0**
- URL: https://openid.net/connect/
- Identity layer built on OAuth 2.0. Used in ATS platforms for enterprise SSO, enabling recruiters and hiring managers to authenticate via their organization's identity provider (IdP). Modern cloud-first ATS platforms prefer OIDC; legacy enterprise integrations often require SAML 2.0 in addition.

**SAML 2.0 — Security Assertion Markup Language**
- URL: https://www.oasis-open.org/standards#samlv2.0
- The dominant enterprise SSO federation protocol, required for integration with corporate Active Directory and legacy identity infrastructure. Enterprise ATS customers (Workday, iCIMS, SAP SmartRecruiters tier) consistently require SAML 2.0 support for single sign-on.

**SOC 2 Type II**
- URL: https://www.aicpa-cima.com/topic/audit-assurance/audit-and-assurance-greater-than-soc-2
- Not a formal standard but a widely required attestation for enterprise ATS procurement. Covers Security, Availability, Processing Integrity, Confidentiality, and Privacy trust services. Major ATS vendors (Greenhouse, Workable, iCIMS) hold SOC 2 Type II reports; essential for enterprise sales.

**OWASP Top 10 — Application Security Risks**
- URL: https://owasp.org/www-project-top-ten/
- Reference standard for web application security. ATS platforms are high-value targets (PII rich, often publicly accessible application portals). Compliance with OWASP Top 10 mitigations — particularly injection prevention, broken access control, and security misconfiguration — is baseline hygiene.

---

### Regulatory Compliance Frameworks

**GDPR — General Data Protection Regulation (EU 2016/679)**
- URL: https://gdpr.eu/
- The most impactful data regulation for ATS platforms globally. Key obligations for recruitment:
  - Article 6: lawful basis for processing (contractual necessity or consent)
  - Article 13/14: privacy notices at point of data collection
  - Article 17: right to erasure — candidates may request deletion of their data
  - Article 22: right not to be subject to solely automated decision-making
  - Typical recommended retention for unsuccessful candidate data: 6 months (varies by jurisdiction)
  - Fines up to €20M or 4% of global annual turnover. Cumulative enforcement reached €5.88 billion through 2024.

**EU AI Act — Regulation (EU) 2024/1689**
- URL: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- AI systems used for recruitment, candidate screening, shortlisting, and employment decision-making are explicitly classified as **high-risk** under Annex III. Compliance deadline: **2 August 2026**. Mandatory obligations include:
  - Risk assessments and technical documentation
  - Bias testing and ongoing monitoring
  - Human oversight mechanisms with audit logs
  - Transparency disclosures to candidates
  - Training for human overseers
  - Fines up to €35M or 7% of global turnover for serious violations.

**CCPA / CPRA — California Consumer Privacy Act (as amended)**
- URL: https://oag.ca.gov/privacy/ccpa
- Effective 2026, California employers must conduct privacy risk assessments before processing California candidate and employee personal information. The California Privacy Protection Agency (CPPA) began rulemaking on HR data application in May 2026, with formal rules expected by 2027. ATS platforms serving US customers must support data access, deletion, and correction rights for California candidates.

**OFCCP / EEOC — Federal Contractor Equal Employment Compliance (US)**
- URL: https://www.dol.gov/agencies/ofccp
- Office of Federal Contract Compliance Programs requirements mandate that federal contractors maintain detailed applicant flow logs — a core ATS function. ATS platforms serving US enterprise customers must capture disposition codes, applicant demographics (via self-identification), and maintain audit trails for OFCCP compliance reviews.

**NYC Local Law 144 (2023)**
- URL: https://www.nyc.gov/site/dca/about/automated-employment-decision-tools.page
- First US law requiring independent bias audits for automated employment decision tools (AEDTs) used in hiring within New York City. Sets a regulatory precedent being adopted in other US jurisdictions. ATS platforms with AI scoring, ranking, or filtering features used by NYC employers must undergo annual audits and publish bias audit summaries.

**NIST AI Risk Management Framework (AI RMF 1.0)**
- URL: https://www.nist.gov/itl/ai-risk-management-framework
- The US government's voluntary but influential framework for managing AI risks across four functions: Govern, Map, Measure, and Manage. Specifically addresses algorithmic bias as a risk category. Relevant for ATS vendors building AI screening and ranking features who want to demonstrate responsible AI practices to enterprise buyers.

---

### MCP Server Specifications

**Model Context Protocol (MCP)**
- URL: https://modelcontextprotocol.io/
- Anthropic's open protocol for connecting AI models to external data sources and tools. Highly relevant for an AI-native ATS: an MCP server exposing ATS data (candidates, jobs, pipeline stages, interview feedback) would allow AI models to query and update recruiting workflows through a standardized interface, enabling agentic recruiting copilots, automated screening, and conversational access to hiring pipeline data without custom API integration per AI tool.

---

## Similar Products — Developer Documentation & APIs

### Greenhouse

- **Description:** Mid-to-enterprise ATS with structured interviewing, pipeline management, and DEI analytics. One of the most widely integrated ATS platforms with 360+ partner integrations.
- **API Documentation:** https://developers.greenhouse.io/
- **Harvest API (v3):** https://developers.greenhouse.io/harvest.html — Primary REST API for full programmatic access to candidates, applications, jobs, interviews, and scorecards. Note: Harvest API v1 and v2 will be deprecated after 31 August 2026; all new integrations should use v3.
- **Ingestion API:** https://developers.greenhouse.io/candidate-ingestion.html — For sourcing candidates from third-party systems into Greenhouse and retrieving stage/status updates.
- **Job Board API:** https://developers.greenhouse.io/job-board.html — For building custom career sites and importing candidate applications.
- **Onboarding API:** https://developers.greenhouse.io/onboarding.html — GraphQL API (queries and mutations) for employee profiles and company information.
- **SDKs/Libraries:** Community-maintained wrappers; no official SDK. Harvest v3 API guide available at https://bindbee.dev/blog/greenhouse-api-guide
- **Standards:** REST/JSON; Basic Auth (API token as username); moving toward OpenAPI documentation.
- **Authentication:** HTTP Basic Auth — API token as the username, blank password.

---

### Lever

- **Description:** Mid-market ATS/CRM hybrid with strong pipeline visibility, two-way email sync, and recruiter-friendly UX. Popular with high-growth tech companies.
- **API Documentation:** https://hire.lever.co/developer/documentation
- **Data API:** Full programmatic access to opportunities, applications, pipeline stages, feedback, offers. Requires API key or OAuth 2.0.
- **Postings API:** https://github.com/lever/postings-api — Publicly accessible without authentication; designed for building job listing sites.
- **SDKs/Libraries:** No official SDK; see unified API platforms (Kombo, Merge) for normalized access.
- **Standards:** REST/JSON; root URL https://api.lever.co/v1.
- **Authentication:** OAuth 2.0 (required for partner/marketplace integrations) or API Key for private integrations. Authorization endpoint: `https://auth.lever.co/authorize`. Access tokens expire after 1 hour; refresh tokens last 1 year.

---

### iCIMS

- **Description:** Enterprise talent acquisition platform covering ATS, CRM, onboarding, and video interviewing. Serves Fortune 500 and high-volume hiring organizations.
- **API Documentation:** https://developer.icims.com/
- **Developer Community:** https://developer-community.icims.com/
- **REST API Reference:** https://developer.icims.com/REST-API/Object-Types-Commands — Covers Search API, Schema API, List API, and object CRUD operations.
- **SDKs/Libraries:** No official SDK. Integrations via partner program.
- **Standards:** REST/JSON; rate limit of 10,000 API calls per day per customer by default.
- **Authentication:** OAuth 2.0 (recommended for all new integrations); HMAC authentication also supported for legacy integrations.

---

### SmartRecruiters

- **Description:** Enterprise ATS acquired by SAP in September 2025. Features Winston Match AI for automated screening (claims 75% reduction in manual screening). Global compliance focus.
- **API Documentation:** https://developers.smartrecruiters.com/
- **Customer API Reference:** https://developers.smartrecruiters.com/docs/api-reference — Posting API, Application API, Job API, Candidate API; OpenAPI Specification (OAS) available in the Overview section of each API component; Swagger UI available as alternate interface.
- **Marketplace API:** https://dev.smartrecruiters.com/ — For building marketplace integrations.
- **SDKs/Libraries:** https://github.com/smartrecruiters — Official GitHub organization; openapi-first Node.js package.
- **Standards:** REST/JSON with OpenAPI 3.x specifications; Swagger-documented endpoints.
- **Authentication:** API Key for custom integrations; OAuth 2.0 for Marketplace apps.

---

### Ashby

- **Description:** Modern ATS targeting high-growth tech companies with analytics-first design. All-in-one platform covering ATS, CRM, scheduling, and analytics. Strong adoption in engineering-led organizations.
- **API Documentation:** https://developers.ashbyhq.com/
- **API Reference:** https://developers.ashbyhq.com/reference/introduction
- **Architecture:** RPC-style API — endpoints follow the form `/CATEGORY.method`; most endpoints use POST requests even for read operations.
- **SDKs/Libraries:** No official SDK. See https://docs.ashbyhq.com for platform documentation.
- **Standards:** JSON over HTTPS; RPC-style rather than REST.
- **Authentication:** HTTP Basic Auth (API key) or Bearer token in Authorization header.

---

### Workday Recruiting

- **Description:** Enterprise HCM-embedded ATS with conversational AI (Olivia, acquired from Paradox in October 2025). Dominant in large enterprise alongside SAP SuccessFactors.
- **API Documentation:** https://community.workday.com/sites/default/files/file-hosting/restapi/index.html (requires Workday Community login)
- **Developer Guide:** https://www.getknit.dev/blog/workday-api-integration-in-depth
- **API Types:** Both SOAP (legacy, complex workflows) and REST APIs are available.
- **SDKs/Libraries:** No public SDK; access typically through Workday Studio or third-party unified API layers.
- **Standards:** REST (OAuth 2.0 protected) and SOAP; OData patterns in some endpoints.
- **Authentication:** OAuth 2.0 required for REST API access; API client registration required through "Register API Client for Integration" in Workday admin.

---

### Kombo (Unified ATS API)

- **Description:** Unified API platform connecting to 250+ ATS, HRIS, payroll, and assessment systems through a single normalized API. Enables product teams to build a single integration rather than per-ATS implementations.
- **API Documentation:** https://docs.kombo.dev/
- **Integration Catalog:** https://www.kombo.dev/integrations — Covers Greenhouse, Ashby, Lever, Workday, SAP SuccessFactors, SmartRecruiters, Oracle Recruiting Cloud, and 240+ more.
- **Key Objects:** Candidate, Application, Job, Department, Stage, Interview, Offer, Attachment — normalized across all connected ATS platforms.
- **SDKs/Libraries:** REST API with webhook support; dashboard for sync monitoring and debugging.
- **Standards:** REST/JSON; unified data model normalizing field names across all integrations.
- **Authentication:** API Key; individual per-customer OAuth flows handled by Kombo for end-system connections.

---

### Merge (Unified ATS API)

- **Description:** Alternative unified HR/ATS API platform similar to Kombo. Widely used by B2B SaaS companies to add ATS integration features without building per-platform integrations.
- **API Documentation:** https://docs.merge.dev/ats/
- **Integration Catalog:** https://www.merge.dev/categories/ats-api — Greenhouse, Lever, iCIMS, SmartRecruiters, Ashby, Workday, and others.
- **Standards:** REST/JSON with normalized data models and OpenAPI specification.
- **Authentication:** API Key; end-user linking via Merge Link OAuth flow.

---

### Microsoft Dynamics 365 Human Resources — ATS Integration API

- **Description:** Microsoft's ATS integration API for connecting external applicant tracking systems to Dynamics 365 HR. Uses OData query patterns.
- **API Documentation:** https://learn.microsoft.com/en-us/dynamics365/human-resources/hr-admin-integration-ats-api-introduction
- **Standards:** OData v4 / REST; standard Dataverse Web API patterns.
- **Authentication:** Azure Active Directory (Azure AD / Entra ID) OAuth 2.0.

---

## Notes

**Emerging Standards and Evolving Areas**

- The **EU AI Act** (August 2026 deadline for high-risk HR AI) is the most immediately impactful emerging regulatory requirement. An AI-native ATS must implement bias auditing, human oversight logging, and candidate transparency disclosures before this date to serve EU customers.
- **HR Open Standards' Trusted Career Profile (TCP v4.5)** and the **LER-RS v2** represent the future direction for verifiable, skills-first candidate profiles — relevant for AI-native ATS platforms that want to move beyond keyword matching to verified competency assessment.
- **Model Context Protocol (MCP)** is an emerging integration layer that could allow AI agents to interact with ATS data directly, enabling agentic recruiting workflows without traditional REST integration overhead.
- The **NYC Local Law 144 bias audit requirement** is widely expected to expand to additional US states and cities through 2026–2028, making bias auditability a near-term table-stakes feature for ATS platforms serving US enterprise customers.
- **JSON Resume** and **OpenCATS** remain the primary open-source reference implementations for open resume data formats, useful for understanding community-driven data model conventions.
- There is currently no single dominant open API standard specifically for ATS-to-ATS or ATS-to-HRIS data exchange; HR Open Standards Recruiting 3.3 is the closest, but adoption is uneven, which is why unified API intermediaries (Kombo, Merge, Apideck) have become a significant market in their own right.
