# Applicant Tracking System (ATS)

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An open-source, AI-native ATS that delivers structured hiring, explainable AI screening, and built-in compliance without enterprise lock-in.

This project is a modern applicant tracking system covering job posting, candidate pipeline, interview scheduling, and AI-assisted screening. It is aimed at startups through mid-market companies priced out of Greenhouse, Workday, and SAP SmartRecruiters, and at any operator who wants candidate data on infrastructure they control. The core problem it solves is that the ATS market is entirely proprietary SaaS, AI screening features are closed and unaudited, and the only existing open-source option (OpenCATS) is effectively unmaintained.

---

## Why an Open ATS?

- Greenhouse charges roughly $12,250/yr for mid-size and $40,000–$70,000/yr at enterprise scale; Workday Recruiting runs $100,000–$300,000+/yr and requires a Workday HCM commitment. Mid-market teams are persistently priced out.
- Recent consolidation (SAP acquired SmartRecruiters in September 2025; Workday acquired Paradox/Olivia in October 2025 for ~$1B) is locking AI screening behind major ERP suites, narrowing buyer choice.
- Closed AI screening tools (Winston Match, Olivia, iCIMS Copilot, Workable AI) publish no bias audit methodologies, while NYC Local Law 144 and the EU AI Act push the compliance burden onto employers.
- OpenCATS, the only actively listed open-source ATS, lacks AI features, structured interview kits, DEI analytics, scheduling, and modern UX, and has had minimal active development in years.
- GDPR Article 22 prohibits solely automated employment decisions; an auditable, explainable, override-friendly screening layer is a structural fit for an open implementation.

---

## Key Features

### Pipeline & Structured Hiring

- Multi-stage candidate pipeline with drag-and-drop stage management and automated stage-transition emails
- Structured interview kits with competency-mapped scorecards and per-stage interviewer assignment
- Job approval and requisition management with configurable multi-level sign-off chains
- Offer management with templated letters, approval routing, and e-signature workflow
- Role-based access control for hiring managers, recruiters, and executives

### Sourcing, Posting & Candidate Experience

- One-click distribution to LinkedIn Apply, Indeed Apply, and major job boards
- Resume parsing with structured candidate profile creation from unstructured documents
- Candidate self-scheduling with calendar integration and conflict detection
- Async video interviewing embedded in the pipeline
- Passive candidate CRM with automated multi-step outreach sequences

### AI Screening & Augmentation

- AI candidate ranking with interpretable per-criterion scores rather than black-box sorting
- Adaptive async interview that scores responses against the job scorecard and produces a ranked shortlist
- AI-assisted job description rewriting and A/B testing driven by application conversion data
- Automated bias detection in scorecard language before submission
- Conversational AI screening for high-volume roles via SMS, web chat, and voice

### Analytics & DEI

- Funnel conversion, time-in-stage, time-to-hire, and source ROI reporting as first-class objects
- DEI dashboard showing representation drop-off by stage and source channel
- Interviewer performance metrics and offer acceptance analysis
- Candidate experience analytics measuring drop-off on the application form itself

### Compliance & Integrations

- OFCCP/EEOC applicant flow log export and audit trail
- Published bias audit methodology aligned with NYC Local Law 144 and EU AI Act expectations
- Human override mechanism for any AI-influenced decision per GDPR Article 22
- HRIS sync for BambooHR, Rippling, and Workday via standard REST API
- HR Open Standards data interchange for requisitions, applications, and interview feedback

---

## AI-Native Advantage

AI is built into the data model rather than bolted on: every screening score is auditable, every decision is explainable per criterion, and bias audit results are published rather than left to the customer. The platform can run a structured async interview, score it against the job scorecard in real time, and surface a ranked shortlist before a recruiter logs in — compressing screening for high-volume roles from days to minutes. AI also rewrites and A/B tests job descriptions against historical conversion data, prioritises passive candidates from engagement signals, and flags biased language in interviewer notes before submission.

---

## Tech Stack & Deployment

The system is designed for self-hosted deployment so candidate data never leaves the operator's infrastructure, with an optional managed cloud offering for teams that prefer not to run their own stack. Integrations follow HR Open Standards for data interchange and the LinkedIn Apply / Indeed Apply APIs for one-click application capture. HRIS sync is exposed as a standard REST API with first-class connectors for BambooHR, Rippling, and Workday. The career site and application portal target WCAG 2.1 AA accessibility.

---

## Market Context

The global applicant tracking software market was USD $3.28B in 2025 and is forecast to grow at 8.2% CAGR through 2030, with the broader talent acquisition software market at roughly $5B in 2026 and ~9% CAGR; high-volume hourly hiring is the fastest-growing segment at ~12% CAGR. Incumbent pricing spans $189/mo for SMB tools like Workable up to $300,000+/yr for Workday Recruiting, with Greenhouse mid-market deployments around $12,250/yr. Primary buyers are startup recruiters and founders, heads of talent at Series B–D companies, TA directors at mid-market firms, CHROs at enterprises, and high-volume hourly hiring operators in retail and logistics.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
