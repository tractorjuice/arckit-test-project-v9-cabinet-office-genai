# Stakeholder Drivers & Goals Analysis: Cabinet Office GenAI Platform

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.stakeholders`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-STKE-v1.1 |
| **Document Type** | Stakeholder Drivers & Goals Analysis |
| **Project** | Cabinet Office GenAI Platform (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-02 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Cabinet Office Senior Responsible Owner |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Cabinet Office Executive Team, CDDO, Pilot Departments (Home Office, HMRC, DHSC, MOJ) |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-02 | ArcKit AI | Initial creation from `/arckit.stakeholders` command | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to latest template format (0.11.2) | PENDING | PENDING |

---

## Executive Summary

### Purpose
This document identifies key stakeholders for the Cabinet Office GenAI Platform, their underlying drivers (motivations, concerns, needs), how these drivers manifest into goals, and the measurable outcomes that will satisfy those goals. This analysis ensures stakeholder alignment across 8 government departments and regulatory bodies participating in this cross-government AI initiative.

### Key Findings

This project has **HIGH stakeholder complexity** with 13 distinct stakeholder groups spanning political leadership (Ministers), permanent civil service (Permanent Secretaries), technical authorities (CDDO, NCSC), regulators (ICO), and end users (policy advisors, civil servants). Key findings:

- **Strategic alignment exists** on cost reduction and AI governance across Cabinet Office, HM Treasury, and CDDO
- **Critical conflict** between speed (Ministerial pressure for delivery) and due diligence (Permanent Secretary accountability and NCSC security requirements)
- **High-risk AI system** creates additional regulatory burden (ICO, AI Playbook compliance) that impacts timelines
- **Multi-tenant architecture** creates technical complexity requiring NCSC assurance before departmental adoption
- **User adoption risk** if departments perceive centralized platform as inferior to their own AI tools

### Critical Success Factors
- **Ministerial confidence**: Deliver manifesto commitment and respond credibly to parliamentary questions on AI governance
- **Permanent Secretary assurance**: Demonstrate proper governance to avoid NAO criticism and accounting officer concerns
- **Cross-department adoption**: Achieve 80% adoption across 20+ departments (requires user satisfaction > 4.2/5)
- **Zero security incidents**: No data breaches or cross-tenant leaks (NCSC red line, Permanent Secretary accountability)
- **Regulatory compliance**: ICO approval of DPIA, AI Playbook score > 90%, ATRS published within 6 months

### Stakeholder Alignment Score
**Overall Alignment**: MEDIUM

**Explanation**: Strong strategic alignment on cost reduction and AI governance exists across Cabinet Office, HM Treasury, and CDDO. However, significant tensions exist between:
1. **Speed vs Security**: Ministerial pressure for quick delivery vs NCSC/Permanent Secretary requirements for thorough assurance
2. **Centralization vs Autonomy**: Cabinet Office desire for centralized governance vs departmental preference for autonomy
3. **Innovation vs Risk**: CTO ambition for cutting-edge AI vs NCSC/ICO caution on responsible AI

These conflicts are **resolvable** through phased rollout (Private Beta with 3 departments first), robust governance (AI Ethics Board), and transparent communication (ATRS publication).

---

## Stakeholder Identification

### Internal Stakeholders (Government)

| Stakeholder | Role/Department | Influence | Interest | Engagement Strategy |
|-------------|----------------|-----------|----------|---------------------|
| **Minister for the Cabinet Office** | Political leadership | HIGH | HIGH | Monthly ministerial briefings, parliamentary Q&A prep |
| **Cabinet Office Permanent Secretary** | Accounting Officer, governance oversight | HIGH | HIGH | Weekly steering committee, risk escalation, NAO readiness |
| **Cabinet Office CTO** | Project sponsor, technical vision | HIGH | HIGH | Daily project oversight, architecture decisions, vendor engagement |
| **CDDO (Central Digital & Data Office)** | Technical standards authority | HIGH | HIGH | TCoP compliance review, architecture review board, GDS assessment |
| **HM Treasury** | Budget approval, value-for-money | HIGH | MEDIUM | Quarterly business case reviews, Green Book compliance |
| **NCSC (National Cyber Security Centre)** | Security assurance | HIGH | MEDIUM | Security architecture review, penetration testing, Secure by Design assessment |
| **ICO (Information Commissioner's Office)** | Data protection regulator | HIGH | MEDIUM | DPIA review, GDPR compliance audit, bias testing oversight |
| **Home Office** | Pilot department, immigration use cases | MEDIUM | HIGH | User research, Private Beta participant, feedback sessions |
| **HMRC** | Pilot department, tax guidance use cases | MEDIUM | HIGH | User research, Private Beta participant, data sensitivity requirements |
| **DHSC** | Pilot department, health policy analysis | MEDIUM | HIGH | User research, Private Beta participant, GDPR/health data concerns |
| **MOJ** | Pilot department, legal document analysis | MEDIUM | HIGH | User research, classification requirements, legal review |
| **Policy Advisors & Civil Servants** | End users across 20+ departments | LOW | HIGH | User testing, training, feedback surveys, adoption metrics |
| **Government Digital Service (GDS)** | Service assessment, design standards | MEDIUM | MEDIUM | Service assessment (Private Beta, Public Beta), design review |

### External Stakeholders

| Stakeholder | Organization | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| **National Audit Office (NAO)** | Independent audit | Oversight | MEDIUM | MEDIUM |
| **Public Accounts Committee (PAC)** | Parliamentary oversight | Oversight | MEDIUM | MEDIUM |
| **AI Vendors (Azure OpenAI, AWS, Anthropic)** | Technology suppliers | Supplier | MEDIUM | HIGH |
| **System Integrators (Accenture, Deloitte, PA)** | Implementation partners | Supplier | MEDIUM | HIGH |
| **Citizens & Taxpayers** | Beneficiaries | Beneficiary | LOW | MEDIUM |
| **Media & Public** | Transparency, accountability | Influence | LOW | MEDIUM |

### Stakeholder Power-Interest Grid

```
HIGH POWER
    │
    │  [Manage Closely]                     │  [Keep Satisfied]
    │  - Minister for Cabinet Office        │  - HM Treasury
    │  - Cabinet Office Permanent Secretary │  - NCSC
    │  - Cabinet Office CTO                 │  - ICO
    │  - CDDO                               │  - GDS
────┼─────────────────────────────────────┼────────────────────
    │  [Keep Informed]                      │  [Monitor]
    │  - Home Office, HMRC, DHSC, MOJ       │  - NAO
    │  - Policy Advisors & Civil Servants   │  - Public Accounts Committee
    │  - AI Vendors                         │  - Citizens & Taxpayers
    │  - System Integrators                │  - Media & Public
    │                                       │
LOW POWER                                          HIGH INTEREST
```

---

## Stakeholder Drivers Analysis

### SD-1: Minister for Cabinet Office - Deliver Manifesto Commitment

**Stakeholder**: Minister for Cabinet Office (Rt Hon [Name] MP)

**Driver Category**: POLITICAL | STRATEGIC

**Driver Statement**: Deliver on manifesto commitment to "harness AI safely across government" and demonstrate responsible AI leadership to respond credibly to parliamentary questions and media scrutiny.

**Context & Background**:
- 2024 King's Speech included commitment to AI governance across government
- Opposition MPs raising questions on government AI spending and data protection
- Media scrutiny of AI use in government (bias concerns, data breaches at other departments)
- Ministerial reputation depends on successful, scandal-free delivery
- Upcoming election cycle requires demonstrable progress ("what have you delivered?")

**Driver Intensity**: CRITICAL

**Enablers** (What would help):
- Quick wins in Private Beta (visible success stories from Home Office, HMRC, DHSC)
- Positive media coverage ("Government leads on responsible AI")
- Cross-party support (all-party parliamentary group endorsement)
- User testimonials from civil servants ("AI saves me 10 hours per week")
- International recognition (OECD, EU cite UK as AI governance leader)

**Blockers** (What would hinder):
- Security breach or data leak (career-ending, front-page scandal)
- Bias incident (AI gives discriminatory policy advice, media outcry)
- Delayed delivery (manifesto commitment unfulfilled before election)
- NAO criticism ("poorly managed, wasteful spending")
- Parliamentary questions exposing problems ("Minister unable to answer")

**Related Stakeholders**:
- Permanent Secretary (must provide assurance to protect Minister)
- Media & Public (scrutinize AI use in government)
- Public Accounts Committee (hold Minister accountable)

---

### SD-2: Cabinet Office Permanent Secretary - Avoid Accounting Officer Concerns

**Stakeholder**: Cabinet Office Permanent Secretary (Accounting Officer)

**Driver Category**: RISK | COMPLIANCE | ACCOUNTABILITY

**Driver Statement**: Ensure proper governance, value for money, and risk management to avoid Accounting Officer concerns, NAO criticism, and Public Accounts Committee scrutiny. Protect ministerial reputation while safeguarding career and civil service reputation.

**Context & Background**:
- As Accounting Officer, personally accountable for £18.8M expenditure (5-year TCO)
- Previous AI projects failed (£5M written off at DWP, NAO "inadequate governance")
- NAO conducting cross-government AI spending review
- Public Accounts Committee has AI governance as priority topic
- Personal reputation: if this fails, career progression at risk (no Permanent Secretary promotion to other departments)
- Dual accountability: to Minister (delivery) and to Parliament (propriety, regularity, value for money)

**Driver Intensity**: CRITICAL

**Enablers** (What would help):
- Robust governance framework (AI Ethics Board, Architecture Review Board, Security Assurance)
- Green Book-compliant business case (£38M NPV, 253% ROI, independent QA)
- Orange Book-compliant risk register (risk responses, mitigation plans, quarterly reviews)
- Early NAO engagement ("nothing to hide, open book")
- Independent assurance (NCSC security review, ICO DPIA approval, GDS service assessment)
- Documented decision-making (Architecture Decision Records, Steering Committee minutes)

**Blockers** (What would hinder):
- Rushed delivery without proper assurance (Minister pushes "just launch it")
- Budget overruns (£18.8M becomes £30M, "why didn't you control costs?")
- Security incident (Accounting Officer liability, "why did you allow inadequate security?")
- NAO finds governance gaps ("inadequate risk management, poor value for money")
- Public Accounts Committee hearing ("Permanent Secretary, explain why this failed")

**Related Stakeholders**:
- Minister (needs delivery, may push to cut corners)
- HM Treasury (enforces Green Book, may challenge business case)
- NAO (audits project, may criticize governance)
- Public Accounts Committee (grills Accounting Officer if problems)

---

### SD-3: Cabinet Office CTO - Modernize Government Technology

**Stakeholder**: Cabinet Office Chief Technology Officer

**Driver Category**: STRATEGIC | PERSONAL | OPERATIONAL

**Driver Statement**: Modernize government technology landscape, attract digital talent to civil service, and establish Cabinet Office as AI innovation leader across government. Build career legacy as "CTO who brought AI to government."

**Context & Background**:
- Government Technology Innovation Strategy 2023 sets ambition for "AI-first government"
- Struggle to recruit digital talent (Amazon, Google pay 2x government salaries)
- Legacy technology debt across departments (£2.3B annual spend on aging systems)
- CTO recruited from private sector (Google, Amazon) with reputation for innovation
- Personal ambition: next role as CDDO CEO or return to private sector as "former Government CTO who delivered AI"
- Peer pressure: other governments (US, Singapore, Estonia) ahead on AI adoption

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Cutting-edge technology stack (Azure OpenAI, Claude 3, modern cloud architecture)
- Talent attraction (civil servants excited to work on AI, easier recruitment)
- Industry recognition (speaking slots at AWS re:Invent, Google Cloud Next)
- Academic partnerships (Oxford, Cambridge, Alan Turing Institute collaboration)
- Reusable platform (other departments copy Cabinet Office model)
- International recognition (OECD, EU invite to present UK approach)

**Blockers** (What would hinder):
- Forced to use outdated technology (on-premise servers, legacy databases)
- Vendor lock-in (single cloud provider, proprietary AI)
- Bureaucratic delays (12 months procurement, 18 months security approval)
- Risk-averse culture ("we can't use AI, too risky")
- Failure to deliver (career reputation: "CTO who failed to deliver AI")

**Related Stakeholders**:
- CDDO (technology standards, may constrain choices)
- NCSC (security requirements, may slow delivery)
- Permanent Secretary (governance, may block risky tech)
- Digital talent (recruitment depends on modern tech)

---

### SD-4: CDDO - Enforce Technology Standards and TCoP Compliance

**Stakeholder**: Central Digital & Data Office (CDDO)

**Driver Category**: COMPLIANCE | STRATEGIC

**Driver Statement**: Enforce Technology Code of Practice (TCoP) and GDS Service Standard across government to ensure interoperability, avoid vendor lock-in, and promote reuse of digital services.

**Context & Background**:
- CDDO authority established 2021 to set cross-government technology standards
- Technology Code of Practice (TCoP) 13 points mandatory for all government projects
- Previous projects failed due to vendor lock-in (£200M spent on non-reusable systems)
- CDDO mission: "once across government" (build once, reuse everywhere)
- CDDO CEO accountable to Cabinet Office Minister and CDDO Minister

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Full TCoP compliance (all 13 points: cloud-first, API-first, open standards, secure, accessible)
- Reusable platform (other departments adopt Cabinet Office GenAI, not build own)
- Open standards (OpenAPI, OAuth, OIDC - no vendor lock-in)
- Published APIs (departments can integrate, extend platform)
- GDS Service Assessment pass (Private Beta and Public Beta)
- Case study for other departments ("how to do AI the right way")

**Blockers** (What would hinder):
- TCoP violations (on-premise infrastructure, proprietary APIs, vendor lock-in)
- Siloed solution (only Cabinet Office uses it, no reuse)
- GDS Service Assessment fail (blocks Public Beta, reputational damage)
- Poor documentation (other departments can't replicate)
- Non-standard architecture (doesn't align with government technical standards)

**Related Stakeholders**:
- Cabinet Office CTO (wants innovation, may conflict with standards)
- GDS (conducts Service Assessment, enforces standards)
- Other departments (will reuse platform if standards-compliant)

---

### SD-5: HM Treasury - Value for Money and Spending Controls

**Stakeholder**: HM Treasury (Spending Team)

**Driver Category**: FINANCIAL | COMPLIANCE

**Driver Statement**: Ensure value for money, budget adherence, and Green Book compliance for the £18.8M investment (5-year TCO). Prevent cost overruns and wasteful spending across government AI initiatives.

**Context & Background**:
- HM Treasury controls all government spending via Green Book business case process
- Autumn Statement 2024 set tight spending limits (efficiency savings required)
- NAO reports show £1.2B wasted on failed government IT projects (2015-2023)
- Treasury under pressure to demonstrate fiscal responsibility
- AI spending across government estimated at £50M annually (uncontrolled, duplicate)
- Business case must show 80% cost reduction (£15M current spend → £3M centralized platform)

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Green Book-compliant Strategic Outline Business Case (SOBC) with 5-case model
- Quantified benefits (£60M savings over 5 years, 253% ROI)
- Risk-adjusted financials (cost contingency, sensitivity analysis)
- Chargeback model (departments pay for usage, not centrally funded after Year 1)
- Quarterly financial reporting (variance analysis, forecast accuracy)
- Independent QA of business case (external consultant validation)

**Blockers** (What would hinder):
- Cost overruns (£18.8M becomes £30M, "why did estimates fail?")
- Benefits not realized (80% cost reduction doesn't materialize)
- Scope creep (gold-plating, nice-to-haves increase costs)
- Unclear financial model (chargeback formula disputed by departments)
- Delayed delivery (costs incurred, benefits delayed, NPV falls)

**Related Stakeholders**:
- Cabinet Office Permanent Secretary (Accounting Officer, must justify spend)
- NAO (audits value for money)
- Public Accounts Committee (scrutinizes wasteful spending)

---

### SD-6: NCSC - Secure Multi-Tenant Architecture

**Stakeholder**: National Cyber Security Centre (NCSC)

**Driver Category**: RISK | COMPLIANCE | SECURITY

**Driver Statement**: Ensure multi-tenant architecture is secure by design with zero tolerance for cross-tenant data leaks. Protect OFFICIAL-SENSITIVE data and maintain NCSC reputation as guardian of government cybersecurity.

**Context & Background**:
- OFFICIAL-SENSITIVE data across 20+ departments (immigration, tax, health, legal)
- Cross-tenant data leak would be catastrophic (ICO £17.5M fine, ministerial resignation)
- Previous multi-tenant breach at [Department X] 2023 (NCSC investigation, system shut down)
- NCSC mission: "no preventable breaches of government systems"
- Cyber Essentials Plus certification minimum requirement (NCSC scheme)
- NCSC reputation: if this fails, "why did NCSC approve insecure system?"

**Driver Intensity**: CRITICAL

**Enablers** (What would help):
- Defense-in-depth multi-tenant isolation (RLS, schema separation, tenant-specific encryption keys)
- Secure by Design principles (NCSC guidance applied from inception)
- Penetration testing by CREST-certified testers (focus on tenant isolation)
- Automated tenant isolation tests in CI/CD (prevent regression)
- Cyber Essentials Plus certification before Private Beta
- NCSC architecture review approval before go-live
- Incident response runbook tested (if breach occurs, containment < 15 minutes)

**Blockers** (What would hinder):
- Weak tenant isolation (shared database without Row-Level Security)
- Rushed delivery without security testing ("launch now, test later")
- Inadequate logging (can't detect cross-tenant access attempts)
- No penetration testing (NCSC review finds critical vulnerabilities)
- Vendor security gaps (AI provider doesn't meet UK security standards)

**Related Stakeholders**:
- Cabinet Office Permanent Secretary (accountable for security)
- ICO (GDPR breach notification required if leak)
- Home Office, HMRC, DHSC, MOJ (data owners, affected by breach)

---

### SD-7: ICO - GDPR Compliance and Data Protection

**Stakeholder**: Information Commissioner's Office (ICO)

**Driver Category**: COMPLIANCE | REGULATORY | RISK

**Driver Statement**: Ensure UK GDPR and Data Protection Act 2018 compliance for cross-government AI system handling personal data at scale. Prevent data protection violations and uphold ICO enforcement credibility.

**Context & Background**:
- UK GDPR Article 35: DPIA mandatory for high-risk processing (generative AI, cross-government scale, OFFICIAL-SENSITIVE data)
- ICO enforcement powers: fines up to £17.5M or 4% of turnover, criminal prosecution for serious breaches
- Recent AI enforcement: ICO issued notices to [Company X] for AI bias, [Company Y] for inadequate DPIA
- ICO mission: "protect data rights, promote responsible AI"
- Public scrutiny: media reports on ICO enforcement, parliamentary questions on AI regulation
- ICO reputation: if this fails without ICO approval, "why didn't ICO prevent this?"

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Comprehensive DPIA completed before Private Beta (ICO template, independent review)
- Lawful basis documented (public task Article 6(1)(e), not consent)
- Individual rights mechanisms (Subject Access Request < 30 days, right to erasure)
- Privacy notice published (clear, accessible, GOV.UK compliant)
- Bias testing (demographic fairness, no discriminatory outcomes)
- Human oversight model (human-in-the-loop for high-stakes decisions)
- AI Playbook compliance (10 principles, ethical AI framework)
- ATRS publication (algorithmic transparency, public accountability)

**Blockers** (What would hinder):
- No DPIA or inadequate DPIA (ICO enforcement notice, project blocked)
- Unlawful processing (no valid legal basis, consent improperly obtained)
- Individual rights not supported (SAR requests ignored, erasure not implemented)
- Bias not addressed (discriminatory outcomes, equality groups harmed)
- Opacity (no explainability, users can't understand AI decisions)

**Related Stakeholders**:
- Cabinet Office Permanent Secretary (accountable for GDPR compliance)
- Home Office, HMRC, DHSC, MOJ (data controllers, jointly responsible)
- Citizens (data subjects, affected by processing)

---

### SD-8: Home Office - Immigration Use Cases and Security

**Stakeholder**: Home Office (UK Visas & Immigration)

**Driver Category**: OPERATIONAL | RISK

**Driver Statement**: Improve immigration case analysis efficiency while maintaining strict security controls for sensitive immigration data (asylum claims, visa decisions, enforcement intelligence).

**Context & Background**:
- UK Visas & Immigration (UKVI) processes 5M visa applications annually
- Case workers overwhelmed (backlogs, 12-month processing times, media criticism)
- Sensitive data: asylum claims (Article 8 ECHR - right to family life), enforcement intelligence
- Security classification: OFFICIAL-SENSITIVE (leaks politically damaging)
- Ministerial scrutiny: Home Secretary answers parliamentary questions on visa processing times
- User need: "Help me analyze 200-page asylum case file in 30 minutes not 4 hours"

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Document summarization (200-page case file → 2-page summary)
- Case law search (find relevant precedents across 10,000 cases)
- Drafting assistance (initial decision letter, human reviews before sending)
- Multi-language support (translate applicant documents from 50+ languages)
- UKVI-specific training data (immigration law, policy guidance, case law)
- No cross-department leaks (UKVI data isolated from HMRC, DHSC, MOJ)

**Blockers** (What would hinder):
- Generic AI not trained on immigration law (incorrect legal advice, case outcomes affected)
- Security concerns (AI provider UK data residency not guaranteed)
- Data leak to other departments (UKVI asylum claim visible to HMRC tax team)
- Bias in visa decisions (AI recommends refusal for certain nationalities, discrimination)
- Explainability gaps (case worker can't explain AI recommendation to applicant)

**Related Stakeholders**:
- NCSC (security controls for OFFICIAL-SENSITIVE immigration data)
- ICO (GDPR, equality impact assessment for visa decisions)
- Home Secretary (ministerial accountability for visa processing)

---

### SD-9: HMRC - Tax Guidance and Data Sensitivity

**Stakeholder**: HM Revenue & Customs (Tax Policy & Operations)

**Driver Category**: OPERATIONAL | COMPLIANCE | RISK

**Driver Statement**: Improve tax policy analysis and customer guidance efficiency while protecting highly sensitive taxpayer data (tax returns, investigations, fraud intelligence).

**Context & Background**:
- HMRC handles 31M individual tax returns, 4M corporate tax returns annually
- Tax policy advisors need to analyze hundreds of pages of tax legislation changes
- Customer service advisors answer 50M calls annually ("Am I eligible for tax relief?")
- Data sensitivity: taxpayer financial data (protected by law, criminal offense to disclose)
- Security classification: OFFICIAL-SENSITIVE (taxpayer confidentiality absolute)
- Fraud intelligence: organized crime investigations, money laundering
- User need: "Help me draft tax guidance for new policy change in days not months"

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Tax legislation analysis (summarize Finance Bill 2025, identify impacts)
- Guidance drafting (draft GOV.UK tax guidance for new relief scheme)
- Policy research (find all mentions of "capital gains" across 10 years legislation)
- Customer self-service (AI chatbot answers "Am I eligible for Child Benefit?")
- HMRC-specific training (UK tax law, HMRC internal policy manuals)
- Taxpayer confidentiality absolute (no HMRC data visible to Home Office, DHSC, MOJ)

**Blockers** (What would hinder):
- Tax advice errors (AI misinterprets tax law, customer loses tax relief)
- Data leak (taxpayer data visible to other departments, criminal offense)
- Unauthorized access (HMRC staff access Home Office asylum data, disciplinary action)
- Audit trail gaps (can't prove who accessed which taxpayer record, compliance failure)
- Explainability failure (AI tax advice not defensible if customer challenges)

**Related Stakeholders**:
- NCSC (security for taxpayer data)
- ICO (GDPR for taxpayer personal data)
- NAO (audits HMRC compliance, value for money)

---

### SD-10: DHSC - Health Policy Analysis and GDPR

**Stakeholder**: Department of Health & Social Care (Policy & Strategy)

**Driver Category**: OPERATIONAL | COMPLIANCE

**Driver Statement**: Improve health policy analysis efficiency while ensuring strict GDPR compliance for health data (special category personal data, highest protection level).

**Context & Background**:
- DHSC develops health policy (NHS Long Term Plan, pandemic response, social care reform)
- Policy advisors analyze clinical evidence, patient data, academic research
- Health data is "special category" under GDPR Article 9 (requires explicit consent or legal basis)
- ICO highly sensitive to health data misuse (largest fines for health data breaches)
- Public trust: NHS data sharing scandals (care.data 2014, Royal Free/Google DeepMind 2017)
- User need: "Help me synthesize 500 clinical studies on obesity interventions"

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Medical literature synthesis (summarize 500 clinical trials, meta-analysis)
- Policy drafting (draft consultation document on obesity strategy)
- Evidence search (find all studies on "diabetes prevention" across PubMed, Cochrane)
- No patient data processing (only policy documents, academic literature, not NHS patient records)
- DHSC-specific training (NHS terminology, clinical evidence standards, NICE guidance)
- Strict data isolation (no DHSC policy documents visible to Home Office, HMRC, MOJ)

**Blockers** (What would hinder):
- Health data misuse (AI trained on NHS patient records without consent, ICO enforcement)
- Data sharing across departments (DHSC health condition data visible to Home Office immigration)
- Public trust failure (media: "Government AI reads your NHS records")
- Inaccurate medical evidence synthesis (AI misinterprets clinical trial, policy flawed)

**Related Stakeholders**:
- ICO (GDPR Article 9 special category data enforcement)
- NCSC (security for health-related policy documents)
- NHS England (concerned about patient data protection)

---

### SD-11: Policy Advisors & Civil Servants - Reduce Workload and Improve Quality

**Stakeholder**: Policy Advisors, Analysts, and Civil Servants (End Users across 20+ departments)

**Driver Category**: PERSONAL | OPERATIONAL

**Driver Statement**: Reduce time spent on manual tasks (reading, summarizing, drafting) to focus on high-value policy analysis and strategic thinking. Improve work-life balance and job satisfaction.

**Context & Background**:
- Average policy advisor reads 200+ pages of documents per week (legislation, briefings, research)
- Manual summarization takes 4 hours, AI could reduce to 30 minutes
- Drafting ministerial submissions takes 2 days, AI could draft initial version in 1 hour (human edits)
- Burnout: 60-hour weeks common during crises (pandemic, budget, legislation deadlines)
- Retention crisis: 25% civil service turnover (exit surveys cite workload, burnout)
- User need: "Give me back 10 hours per week to do strategic thinking, not admin"

**Driver Intensity**: HIGH

**Enablers** (What would help):
- Intuitive interface (GDS Design System, familiar GOV.UK patterns)
- Fast response times (< 2 seconds, not 30 seconds per query)
- Accurate outputs (AI summaries factually correct, not hallucinated)
- Transparent sources (show which document paragraph informed answer)
- Easy editing (AI draft → human edits → finalize in 30 mins)
- Mobile access (work on train, at home, not desk-bound)
- Training provided (2-hour onboarding, ongoing support)

**Blockers** (What would hinder):
- Clunky interface (complex, non-intuitive, requires IT support)
- Slow performance (30 seconds per query, faster to read manually)
- Inaccurate outputs (AI hallucinates facts, user loses trust)
- No transparency (can't verify AI claims, can't cite sources)
- Desktop-only (can't use on laptop, mobile, tablets)
- No training (expected to "figure it out", adoption fails)

**Related Stakeholders**:
- Cabinet Office CTO (responsible for user experience)
- GDS (Design System, accessibility standards)
- Departmental Digital Leads (training, change management)

---

### SD-12: GDS - Service Standard Compliance and User-Centered Design

**Stakeholder**: Government Digital Service (GDS)

**Driver Category**: COMPLIANCE | STRATEGIC

**Driver Statement**: Ensure GDS Service Standard compliance (14 points) and user-centered design to maintain quality of government digital services and GDS authority as standards body.

**Context & Background**:
- GDS Service Standard mandatory for all public-facing government services
- Private Beta and Public Beta require GDS Service Assessment (pass/fail)
- Service Assessment panels include GDS assessors, CDDO, departmental digital leads
- GDS reputation: "guardian of user-centered design in government"
- Previous AI projects bypassed Service Assessment (poor user experience, media criticism)
- GDS mission: "make government digital services so good people prefer to use them"

**Driver Intensity**: MEDIUM

**Enablers** (What would help):
- User research in Discovery/Alpha (6+ departments, diverse user groups)
- GDS Design System components (buttons, forms, typography)
- WCAG 2.2 Level AA accessibility (screen readers, keyboard navigation, color contrast)
- Iterative design (alpha prototype → user testing → beta refinement)
- User satisfaction > 4.2/5 (measured via feedback surveys)
- Performance metrics (response time < 2s, uptime 99.9%)
- Service Assessment preparation (evidence pack, user research artifacts)

**Blockers** (What would hinder):
- No user research (assumptions about user needs, design fails)
- Custom UI not using GDS Design System (inconsistent with GOV.UK, poor accessibility)
- Accessibility failures (WCAG violations, disabled users excluded)
- Poor performance (slow, unreliable, users abandon)
- Service Assessment fail (blocks Public Beta launch, reputational damage)

**Related Stakeholders**:
- CDDO (enforces Service Standard compliance)
- Policy Advisors (end users, user research participants)
- Cabinet Office CTO (accountable for Service Assessment pass)

---

### SD-13: NAO & Public Accounts Committee - Value for Money and Governance Oversight

**Stakeholder**: National Audit Office (NAO) & Public Accounts Committee (PAC)

**Driver Category**: COMPLIANCE | ACCOUNTABILITY | RISK

**Driver Statement**: Ensure public money is spent wisely, with proper governance and value for money. Hold government accountable for AI spending and prevent wasteful projects.

**Context & Background**:
- NAO statutory authority to audit all government spending
- NAO reports to Public Accounts Committee (cross-party MPs)
- Public Accounts Committee holds public hearings (televised, media coverage)
- NAO AI spending review 2024: "£1.2B wasted on failed AI projects, inadequate governance"
- Previous hearings: Permanent Secretaries grilled on failed IT projects (Universal Credit, NHS IT)
- NAO focus: value for money, governance, risk management, benefits realization

**Driver Intensity**: MEDIUM

**Enablers** (What would help):
- Green Book-compliant business case (5-case model, independent QA)
- Quantified benefits realized (80% cost reduction achieved, measured annually)
- Robust governance (Steering Committee, Architecture Review Board, AI Ethics Board)
- Risk management (Orange Book risk register, quarterly reviews, mitigation plans)
- Transparent procurement (G-Cloud framework, competitive process, no single-source)
- Benefits tracking (KPIs measured, reported quarterly, benefits owner accountable)
- Early NAO engagement ("open book", proactive transparency)

**Blockers** (What would hinder):
- Cost overruns (£18.8M becomes £40M, "why did costs double?")
- Benefits not realized (80% cost reduction doesn't materialize, "where are savings?")
- Poor governance (no risk register, no Steering Committee, ad-hoc decisions)
- Sole-source procurement (£10M to single vendor, no competition, "why?")
- Delayed delivery (3 years late, costs incurred, benefits delayed)
- Lack of transparency (NAO requests documents, Cabinet Office delays/refuses)

**Related Stakeholders**:
- Cabinet Office Permanent Secretary (Accounting Officer, NAO scrutinizes)
- HM Treasury (NAO audits Treasury approval process)
- Public Accounts Committee (NAO reports to PAC)

---

## Driver-to-Goal Mapping

### Goal G-1: Reduce Duplicate AI Spending by 80% Across Government

**Derived From Drivers**: SD-1 (Minister - manifesto commitment), SD-2 (Permanent Secretary - value for money), SD-3 (CTO - modernization), SD-5 (HM Treasury - spending controls)

**Goal Owner**: Cabinet Office CTO (Primary), HM Treasury (Accountable for financial benefits)

**Goal Statement**: Reduce government AI spending from £15M annually (current duplicate spending across 20+ departments) to £3M annually (centralized platform operational costs) by end of Year 2, representing an 80% reduction and £60M cumulative savings over 5 years.

**Why This Matters**:
- **Minister (SD-1)**: Demonstrates manifesto commitment to efficiency and fiscal responsibility, defensible in parliamentary questions
- **Permanent Secretary (SD-2)**: Avoids NAO criticism of wasteful spending, protects Accounting Officer accountability
- **CTO (SD-3)**: Proves centralization value proposition, justifies Cabinet Office technology leadership
- **HM Treasury (SD-5)**: Delivers quantifiable savings, supports Autumn Statement efficiency targets

**Success Metrics**:
- **Primary Metric**: Annual AI spending across government (£M)
- **Secondary Metrics**:
  - Number of departments using centralized platform vs own AI tools (target: 20+ departments)
  - Cost per user per month (target: £25/user centralized vs £125/user decentralized)
  - Duplicate procurement eliminated (target: zero new departmental AI contracts after Year 1)

**Baseline**: £15M annual spend (2024) across 20+ departments on individual AI tools (ChatGPT Enterprise, GitHub Copilot, departmental bespoke solutions)

**Target**: £3M annual spend (Year 2) on centralized Cabinet Office GenAI Platform (cloud costs £1.5M, AI APIs £1M, support £500K)

**Measurement Method**:
- Annual AI spending survey across 20+ departments (Finance Directors report total AI spend)
- Centralized platform usage analytics (active users per department, queries per month)
- Chargeback model financials (departments invoiced monthly, tracked via Oracle Financials)

**Dependencies**:
- Platform adoption > 80% across departments (if only 5 departments adopt, savings not realized)
- Departmental commitment to decommission own AI tools (not run parallel systems)
- Chargeback model accepted by departments (departments pay £25/user/month)
- Platform feature parity with departmental tools (if inferior, departments won't switch)

**Risks to Achievement**:
- Departmental resistance ("our AI tool is better, we won't switch") - Risk R-2
- Delayed delivery (platform not ready, departments continue paying for own tools) - Risk R-3
- Platform cost overruns (£3M becomes £8M, savings eroded) - Risk R-4
- User adoption failure (departments sign up but don't use, savings not realized) - Risk R-5

---

### Goal G-2: Achieve Zero Data Breaches or Cross-Tenant Leaks

**Derived From Drivers**: SD-2 (Permanent Secretary - accountability), SD-6 (NCSC - security), SD-7 (ICO - GDPR), SD-8, SD-9, SD-10 (Departments - data sensitivity)

**Goal Owner**: Cabinet Office CISO (Primary), NCSC (Security Assurance)

**Goal Statement**: Achieve zero data breaches, zero cross-tenant data leaks, and zero security incidents from project inception through Year 5 of operations, measured via security monitoring, penetration testing, and incident logs.

**Why This Matters**:
- **Permanent Secretary (SD-2)**: Career-ending if major breach occurs under their watch, Accounting Officer liability
- **NCSC (SD-6)**: NCSC reputation depends on secure government systems, breach undermines trust
- **ICO (SD-7)**: GDPR breach triggers ICO investigation, fines up to £17.5M, enforcement action
- **Departments (SD-8, SD-9, SD-10)**: Cross-tenant leak exposes sensitive data (immigration, tax, health) to wrong department, criminal offense

**Success Metrics**:
- **Primary Metric**: Security incidents (target: 0 data breaches, 0 cross-tenant leaks)
- **Secondary Metrics**:
  - Penetration testing findings (target: 0 critical, 0 high vulnerabilities before go-live)
  - Cyber Essentials Plus certification maintained (annual re-cert)
  - Security monitoring alerts investigated within SLA (< 15 minutes for critical alerts)
  - Automated tenant isolation tests passing (100% pass rate in CI/CD)

**Baseline**: 0 incidents (new system, no baseline)

**Target**: 0 incidents throughout project lifecycle (Discovery through Year 5 operations)

**Measurement Method**:
- Security Information and Event Management (SIEM) logs (real-time monitoring)
- Penetration testing reports (CREST-certified testers, annual testing)
- Incident register (all security events logged, categorized by severity)
- Cyber Essentials Plus audits (annual certification)
- Automated test results (tenant isolation tests in CI/CD pipeline)

**Dependencies**:
- NCSC architecture review approval before go-live
- Cyber Essentials Plus certification obtained before Private Beta
- Penetration testing passed (0 critical/high findings remediated)
- Security monitoring operational (SIEM integrated, SOC 24/7 coverage)
- Incident response runbook tested (tabletop exercises, breach simulation)

**Risks to Achievement**:
- Rushed delivery without security testing ("launch now, test later") - Risk R-1
- Multi-tenant architecture design flaw (RLS bypassed, cross-tenant access) - Risk R-6
- Vendor security gaps (AI provider data leak, third-party breach) - Risk R-7
- Insider threat (privileged user abuses access, steals data) - Risk R-8
- Zero-day vulnerability (unpatched CVE exploited before patch available) - Risk R-9

---

### Goal G-3: Publish ATRS Within 6 Months of Private Beta Launch

**Derived From Drivers**: SD-1 (Minister - transparency), SD-7 (ICO - algorithmic transparency), SD-11 (Users - trust)

**Goal Owner**: Cabinet Office AI Ethics Lead (Primary), ICO (Review and Approval)

**Goal Statement**: Publish Algorithmic Transparency Recording Standard (ATRS) Tier 1 (public summary) and Tier 2 (technical details) on GOV.UK algorithmic transparency page within 6 months of Private Beta launch (target: Month 12), demonstrating responsible AI and transparency commitment.

**Why This Matters**:
- **Minister (SD-1)**: Demonstrates transparency and accountability, positive media coverage, defensible in parliamentary questions
- **ICO (SD-7)**: ATRS mandatory for central government algorithmic tools, ICO enforces compliance
- **Users (SD-11)**: Transparency builds trust, users understand how AI makes decisions

**Success Metrics**:
- **Primary Metric**: ATRS publication date (target: within 6 months of Private Beta, Month 12)
- **Secondary Metrics**:
  - ATRS completeness (all mandatory fields completed: Tier 1 9 fields, Tier 2 12 fields)
  - Senior Responsible Owner approval (SRO sign-off on ATRS before publication)
  - GOV.UK algorithmic transparency page listing (ATRS visible to public)

**Baseline**: No ATRS (new system)

**Target**: ATRS published by Month 12 (6 months after Month 6 Private Beta launch)

**Measurement Method**:
- ATRS document version control (draft in Alpha, final in Private Beta)
- SRO approval email/signature (documented in project records)
- GOV.UK publication date (timestamp on algorithmic transparency page)

**Dependencies**:
- ATRS template completed during Alpha/Private Beta (Tier 1 + Tier 2)
- Bias testing completed (results documented in ATRS Tier 2)
- Human oversight model defined (documented in ATRS Tier 1)
- SRO availability for review and approval (SRO not blocked by other priorities)
- GOV.UK publishing team capacity (no backlog delays)

**Risks to Achievement**:
- Delayed bias testing (testing takes longer than planned, ATRS incomplete) - Risk R-10
- SRO approval delays (SRO requests revisions, multiple review cycles) - Risk R-11
- Sensitive information disputes (departments object to publishing certain details) - Risk R-12
- GOV.UK publishing backlog (no capacity to publish, 3-month wait) - Risk R-13

---

### Goal G-4: Achieve User Satisfaction > 4.2/5 Across 20+ Departments

**Derived From Drivers**: SD-3 (CTO - modernization), SD-11 (Users - workload reduction), SD-12 (GDS - user-centered design)

**Goal Owner**: Cabinet Office Product Owner (Primary), GDS (User Research Oversight)

**Goal Statement**: Achieve user satisfaction score > 4.2/5 (84%) across 20+ participating departments by end of Public Beta (Month 12), measured via quarterly user surveys with representative sample (200+ responses per quarter).

**Why This Matters**:
- **CTO (SD-3)**: User satisfaction proves technology delivers value, attracts digital talent, builds Cabinet Office reputation
- **Users (SD-11)**: High satisfaction indicates workload reduced, quality improved, job satisfaction increased
- **GDS (SD-12)**: User satisfaction validates user-centered design, GDS Service Assessment success criterion

**Success Metrics**:
- **Primary Metric**: User satisfaction score (1-5 scale, target > 4.2)
- **Secondary Metrics**:
  - Net Promoter Score (NPS) > +50 ("would you recommend to colleague?")
  - Task success rate > 90% ("could you complete your task?")
  - Time saved per user per week (target: 10 hours/week)
  - User retention (target: 80% monthly active users return next month)

**Baseline**: No baseline (new system), benchmark against other government digital services (GOV.UK average: 4.0/5)

**Target**: > 4.2/5 by Month 12 (Public Beta completion)

**Measurement Method**:
- Quarterly user surveys (200+ responses per quarter, stratified by department and role)
- In-app feedback widget ("How satisfied are you with this response? 1-5 stars")
- User interviews (20 interviews per quarter, qualitative feedback)
- Usage analytics (time saved calculated from query volume × average time per manual task)

**Dependencies**:
- User research in Discovery/Alpha (understand user needs, validate design)
- Iterative design based on feedback (alpha prototype → beta refinement)
- Performance meets targets (< 2s response time, 99.9% uptime)
- Training provided (2-hour onboarding per user, ongoing support)
- GDS Design System compliance (familiar patterns, accessible)

**Risks to Achievement**:
- Poor user experience (slow, inaccurate, clunky interface) - Risk R-14
- Insufficient training (users don't understand how to use, abandon) - Risk R-15
- Performance issues (slow response times, downtime, frustration) - Risk R-16
- Inaccurate AI outputs (hallucinations, factual errors, user loses trust) - Risk R-17
- Survey bias (only enthusiasts respond, not representative) - Risk R-18

---

### Goal G-5: Pass GDS Service Assessment (Private Beta and Public Beta)

**Derived From Drivers**: SD-4 (CDDO - TCoP compliance), SD-12 (GDS - Service Standard)

**Goal Owner**: Cabinet Office Product Owner (Primary), GDS (Assessment Panel)

**Goal Statement**: Pass GDS Service Assessment at Private Beta (Month 9) and Public Beta (Month 12) stages, demonstrating compliance with all 14 Service Standard points and readiness for live deployment.

**Why This Matters**:
- **CDDO (SD-4)**: GDS Service Assessment is gateway to Public Beta and Live, CDDO enforces compliance
- **GDS (SD-12)**: Service Assessment validates user-centered design and digital best practices

**Success Metrics**:
- **Primary Metric**: GDS Service Assessment outcome (PASS | PASS_WITH_CONDITIONS | FAIL)
- **Secondary Metrics**:
  - 14 Service Standard points compliance (target: 14/14 passed)
  - Assessment panel recommendations (target: 0 blockers, < 3 minor recommendations)
  - Time to remediate recommendations (target: < 4 weeks)

**Baseline**: No baseline (new service)

**Target**: PASS at Private Beta (Month 9), PASS at Public Beta (Month 12)

**Measurement Method**:
- GDS Service Assessment report (official outcome document)
- Assessment panel feedback (written recommendations and blockers)
- Evidence pack completeness (user research artifacts, technical architecture, accessibility audit)

**Dependencies**:
- User research conducted (Discovery, Alpha, Private Beta)
- Evidence pack prepared (user research reports, accessibility audit, technical docs)
- WCAG 2.2 AA accessibility compliance (automated and manual testing)
- GDS Design System used (familiar GOV.UK patterns)
- Performance metrics meet targets (< 2s response time, 99.9% uptime)

**Risks to Achievement**:
- Insufficient user research (can't demonstrate user-centered design) - Risk R-19
- Accessibility failures (WCAG violations, assessment fail) - Risk R-20
- Performance issues (slow, unreliable, assessment panel experiences poor UX) - Risk R-21
- Incomplete evidence pack (missing artifacts, assessment delayed) - Risk R-22

---

### Goal G-6: Achieve AI Playbook Compliance Score > 90%

**Derived From Drivers**: SD-1 (Minister - responsible AI), SD-7 (ICO - ethical AI), SD-2 (Permanent Secretary - governance)

**Goal Owner**: Cabinet Office AI Ethics Lead (Primary), ICO (Review and Oversight)

**Goal Statement**: Achieve AI Playbook compliance score > 90% (144/160 points) across 10 AI Playbook principles and 6 ethical themes by Private Beta (Month 9), demonstrating responsible AI deployment and ethical governance.

**Why This Matters**:
- **Minister (SD-1)**: AI Playbook compliance demonstrates responsible AI leadership, defensible in parliamentary questions
- **ICO (SD-7)**: AI Playbook mandatory for government AI systems, ICO monitors compliance
- **Permanent Secretary (SD-2)**: AI Playbook compliance reduces governance risk, avoids NAO criticism

**Success Metrics**:
- **Primary Metric**: AI Playbook compliance score (points out of 160, target > 144 = 90%)
- **Secondary Metrics**:
  - 10 AI Playbook principles compliance (target: 10/10 met)
  - 6 ethical themes compliance (target: 6/6 addressed)
  - Mandatory assessments completed (DPIA, EqIA, Human Rights Assessment)
  - Bias testing passed (demographic fairness, no discriminatory outcomes)

**Baseline**: 0% (new system, no compliance yet)

**Target**: > 90% (144/160 points) by Month 9 (Private Beta)

**Measurement Method**:
- AI Playbook assessment scorecard (10 principles × 10 points + 6 themes × 10 points = 160 points)
- Independent review (external AI ethics consultant validates self-assessment)
- ICO review (ICO comments on AI Playbook compliance during DPIA review)

**Dependencies**:
- DPIA completed (ICO template, independent review)
- Equality Impact Assessment (EqIA) completed (demographic bias testing)
- Human Rights Assessment completed (Article 8 privacy, Article 14 non-discrimination)
- Bias testing completed (age, gender, ethnicity, disability, department)
- Human oversight model implemented (human-in-the-loop, override capability)
- Explainability features implemented (source attribution, confidence scores)

**Risks to Achievement**:
- Bias detected in testing (demographic disparities, delayed remediation) - Risk R-23
- DPIA incomplete or inadequate (ICO enforcement notice, project blocked) - Risk R-24
- Human oversight gaps (no human-in-the-loop, AI Playbook non-compliance) - Risk R-25
- Explainability failures (black box AI, users can't understand decisions) - Risk R-26

---

## Goal-to-Outcome Mapping

### Outcome O-1: £60M Cumulative Cost Savings Over 5 Years

**Supported Goals**: G-1 (80% cost reduction)

**Outcome Statement**: Achieve £60M cumulative cost savings over 5 years (Year 1-5) by reducing duplicate AI spending across government from £15M/year to £3M/year, delivering 253% ROI on £18.8M investment.

**Measurement Details**:
- **KPI**: Annual AI spending across government (£M)
- **Current Value**: £15M/year (2024 baseline across 20+ departments)
- **Target Value**: £3M/year (Year 2 onwards, centralized platform)
- **Cumulative Savings**: £60M over 5 years (Year 1: £8M, Year 2-5: £12M/year)
- **Measurement Frequency**: Quarterly (departmental AI spending survey)
- **Data Source**: Departmental Finance Directors, Oracle Financials (chargeback invoices)
- **Report Owner**: HM Treasury Spending Team

**Business Value**:
- **Financial Impact**: £60M cost savings (freed budget redeployed to other priorities)
- **Strategic Impact**: Proves centralization value proposition, Cabinet Office technology leadership
- **Operational Impact**: Eliminates procurement overhead (20+ departments no longer procure own AI tools)
- **ROI**: 253% over 5 years (£60M savings ÷ £18.8M cost - 100%)

**Timeline**:
- **Phase 1 (Months 1-6, Discovery & Alpha)**: £0 savings (investment phase, £2M spent)
- **Phase 2 (Months 7-12, Private Beta & Public Beta)**: £8M savings (3 pilot departments switch, £5M departmental spend → £1M centralized)
- **Phase 3 (Year 2)**: £12M savings (20+ departments fully migrated, £15M → £3M)
- **Sustainment (Year 3-5)**: £12M savings/year sustained (ongoing operations, chargeback model)

**Stakeholder Benefits**:
- **Minister (SD-1)**: Demonstrates fiscal responsibility, manifesto commitment delivered, defensible in parliament
- **Permanent Secretary (SD-2)**: Avoids NAO "wasteful spending" criticism, protects Accounting Officer reputation
- **HM Treasury (SD-5)**: £60M savings supports Autumn Statement efficiency targets, value for money proven
- **Departments**: Lower AI costs (£25/user/month centralized vs £125/user/month individual contracts)

**Leading Indicators** (early signals of success):
- Departmental sign-ups for centralized platform (Month 6: 3 departments, Month 12: 10 departments, Year 2: 20+ departments)
- Pilot department decommissioning own AI tools (Month 9: Home Office, HMRC, DHSC cancel ChatGPT Enterprise)
- Chargeback invoices accepted by departments (no disputes over chargeback formula)

**Lagging Indicators** (final proof of success):
- Annual AI spending survey shows £3M total (down from £15M baseline)
- Cumulative savings tracked via Treasury reporting (£8M Year 1, £20M by Year 2, £60M by Year 5)
- Zero new departmental AI procurement (all departments use centralized platform, no duplicate contracts)

---

### Outcome O-2: Zero Security Incidents Across 5 Years

**Supported Goals**: G-2 (zero data breaches)

**Outcome Statement**: Achieve zero data breaches, zero cross-tenant data leaks, and zero security incidents from inception through Year 5 of operations, measured via security monitoring, penetration testing, and incident logs.

**Measurement Details**:
- **KPI**: Security incidents (data breaches, cross-tenant leaks, unauthorized access)
- **Current Value**: 0 incidents (new system, no baseline)
- **Target Value**: 0 incidents (throughout lifecycle, Discovery → Year 5)
- **Measurement Frequency**: Real-time monitoring, quarterly reporting
- **Data Source**: SIEM logs, incident register, penetration testing reports, Cyber Essentials Plus audits
- **Report Owner**: Cabinet Office CISO, NCSC Security Assurance

**Business Value**:
- **Financial Impact**: Avoid ICO fines (£17.5M), litigation costs, remediation costs (£5M+ per incident)
- **Strategic Impact**: Maintain government trust, Cabinet Office reputation as secure platform provider
- **Operational Impact**: No downtime from incidents, no emergency response costs
- **Reputational Impact**: Avoid media scandals, ministerial resignations, loss of public trust

**Timeline**:
- **Phase 1 (Months 1-6, Discovery & Alpha)**: 0 incidents (no production data, prototype only)
- **Phase 2 (Months 7-12, Private Beta & Public Beta)**: 0 incidents (3 pilot departments, OFFICIAL-SENSITIVE data)
- **Phase 3 (Year 2-5, Live Operations)**: 0 incidents (20+ departments, full production scale)

**Stakeholder Benefits**:
- **Minister (SD-1)**: Avoids career-ending scandal, no media "Government AI leaks sensitive data" headlines
- **Permanent Secretary (SD-2)**: Protects Accounting Officer reputation, no NAO criticism, no PAC hearing
- **NCSC (SD-6)**: Validates NCSC security guidance effectiveness, maintains NCSC reputation
- **ICO (SD-7)**: No GDPR enforcement action required, demonstrates responsible AI data protection
- **Departments (SD-8, SD-9, SD-10)**: Sensitive data protected (immigration, tax, health), no cross-tenant leaks

**Leading Indicators** (early signals of success):
- Penetration testing findings remediated (0 critical, 0 high vulnerabilities before go-live)
- Automated tenant isolation tests passing (100% pass rate in CI/CD)
- Security monitoring alerts investigated within SLA (< 15 minutes for critical alerts)
- Cyber Essentials Plus certification maintained (annual re-cert passed)

**Lagging Indicators** (final proof of success):
- Incident register shows 0 data breaches (5-year track record)
- NCSC annual security reviews passed (no major findings)
- ICO audits show GDPR compliance (no enforcement notices)
- User trust maintained (no security concerns in user surveys)

---

### Outcome O-3: 20+ Departments Adopt Platform (80% Adoption Rate)

**Supported Goals**: G-1 (cost reduction requires adoption), G-4 (user satisfaction drives adoption)

**Outcome Statement**: Achieve 20+ departments actively using centralized GenAI platform by Year 2, representing 80% adoption rate across 25 eligible central government departments, with 10,000+ monthly active users.

**Measurement Details**:
- **KPI**: Number of departments with active users (at least 10 active users per month)
- **Current Value**: 0 departments (new platform)
- **Target Value**: 20+ departments by Year 2 (80% adoption)
- **Monthly Active Users**: 10,000+ across 20+ departments (average 500 users per department)
- **Measurement Frequency**: Monthly (usage analytics dashboard)
- **Data Source**: Platform analytics (department ID, active users, queries per month)
- **Report Owner**: Cabinet Office Product Owner

**Business Value**:
- **Financial Impact**: £60M savings require 80% adoption (if only 5 departments adopt, savings = £10M not £60M)
- **Strategic Impact**: Proves centralization model, Cabinet Office leadership validated
- **Operational Impact**: Critical mass for platform sustainability (chargeback revenue covers ops costs)
- **Network Effect**: More departments → richer knowledge base → better AI responses → higher satisfaction

**Timeline**:
- **Phase 1 (Months 1-6, Discovery & Alpha)**: 0 departments (prototype only)
- **Phase 2 (Months 7-9, Private Beta)**: 3 pilot departments (Home Office, HMRC, DHSC, ~500 users)
- **Phase 3 (Months 10-12, Public Beta)**: 10 departments (early adopters, ~3,000 users)
- **Phase 4 (Year 2, Live)**: 20+ departments (full rollout, ~10,000+ users)
- **Sustainment (Year 3-5)**: 22-25 departments (near-universal adoption)

**Stakeholder Benefits**:
- **Cabinet Office CTO (SD-3)**: Proves technology leadership, platform adoption validates investment
- **HM Treasury (SD-5)**: Adoption drives cost savings (£60M benefit depends on 80% adoption)
- **CDDO (SD-4)**: Demonstrates "once across government" reuse model success
- **Users (SD-11)**: More users → better AI training → more accurate responses → higher satisfaction

**Leading Indicators** (early signals of success):
- Pilot department satisfaction > 4.2/5 (Month 9, validates product-market fit)
- Departmental sign-up commitments (Month 6: 10 departments express interest)
- Early adopter onboarding velocity (Month 12: 10 departments onboarded in 3 months)
- User referrals (users recommend to colleagues in other departments)

**Lagging Indicators** (final proof of success):
- Usage analytics show 20+ departments with active users (Year 2)
- Monthly active users > 10,000 (Year 2)
- Departmental renewal rate > 90% (departments continue using Year 3+, don't churn)
- Zero departmental AI procurement outside platform (all use centralized, no shadow IT)

---

### Outcome O-4: AI Playbook Compliance Score > 90% Demonstrating Responsible AI

**Supported Goals**: G-6 (AI Playbook compliance)

**Outcome Statement**: Achieve AI Playbook compliance score > 90% (144/160 points) by Private Beta (Month 9), demonstrating responsible AI deployment and establishing Cabinet Office as UK Government AI governance exemplar.

**Measurement Details**:
- **KPI**: AI Playbook compliance score (points out of 160)
- **Current Value**: 0% (new system, no compliance yet)
- **Target Value**: > 90% (144/160 points) by Month 9
- **Measurement Frequency**: Quarterly (self-assessment), annually (independent review)
- **Data Source**: AI Playbook assessment scorecard, ICO DPIA review, independent AI ethics consultant report
- **Report Owner**: Cabinet Office AI Ethics Lead

**Business Value**:
- **Strategic Impact**: Cabinet Office becomes UK Government AI governance leader, international recognition (OECD, EU)
- **Reputational Impact**: Demonstrates responsible AI, builds public trust, positive media coverage
- **Operational Impact**: Reduces regulatory risk, avoids ICO enforcement, smooth GDS Service Assessment
- **Policy Impact**: Cabinet Office GenAI becomes case study for other government AI projects (Home Office, MOJ, DHSC replicate model)

**Timeline**:
- **Phase 1 (Months 1-3, Discovery)**: 30% (initial DPIA drafted, user needs defined)
- **Phase 2 (Months 4-6, Alpha)**: 60% (EqIA completed, bias testing started, human oversight designed)
- **Phase 3 (Months 7-9, Private Beta)**: > 90% (DPIA approved, bias testing passed, ATRS drafted, human-in-the-loop operational)
- **Sustainment (Year 2-5)**: > 90% maintained (quarterly bias testing, annual AI Playbook review)

**Stakeholder Benefits**:
- **Minister (SD-1)**: Demonstrates responsible AI leadership, defensible in parliamentary questions, positive media
- **Permanent Secretary (SD-2)**: Reduces governance risk, avoids NAO "inadequate AI ethics" criticism
- **ICO (SD-7)**: Validates ICO enforcement effectiveness, Cabinet Office sets standard for other departments
- **Citizens**: AI is fair, transparent, accountable (bias tested, explainable, human oversight)

**Leading Indicators** (early signals of success):
- DPIA completed and ICO-approved (Month 6, no enforcement notices)
- Bias testing shows no demographic disparities (Month 8, fair across age, gender, ethnicity, disability)
- Human oversight model operational (Month 9, users can review, challenge, override AI)
- Explainability features live (Month 9, source attribution, confidence scores, alternative interpretations)

**Lagging Indicators** (final proof of success):
- AI Playbook assessment scorecard > 90% (Month 9, independent review validates)
- ATRS published on GOV.UK (Month 12, public transparency)
- Zero bias incidents (Year 1-5, no discriminatory outcomes reported)
- Case studies published (Year 2, CDDO, GDS, OECD cite Cabinet Office as exemplar)

---

### Outcome O-5: User Productivity Gains (10 Hours Saved Per User Per Week)

**Supported Goals**: G-4 (user satisfaction)

**Outcome Statement**: Achieve 10 hours saved per user per week through AI-assisted document summarization, drafting, and analysis, representing 25% productivity improvement and £10M annual FTE cost savings across 10,000 users.

**Measurement Details**:
- **KPI**: Time saved per user per week (hours)
- **Current Value**: 0 hours (no AI assistance currently)
- **Target Value**: 10 hours saved per week per user (from 40-hour week, 25% productivity gain)
- **Annual FTE Cost Savings**: £10M (10,000 users × 10 hours/week × 48 weeks × £50/hour FTE cost)
- **Measurement Frequency**: Quarterly (user surveys, usage analytics)
- **Data Source**: User surveys ("How many hours per week does AI save you?"), usage analytics (queries per user, document processing volume)
- **Report Owner**: Cabinet Office Product Owner

**Business Value**:
- **Financial Impact**: £10M annual FTE cost savings (productivity gain equivalent to 2,500 FTEs redeployed)
- **Operational Impact**: Faster policy analysis (4 hours → 30 minutes), faster drafting (2 days → 4 hours)
- **Strategic Impact**: Civil service can do more with same headcount (addresses spending review constraints)
- **Employee Impact**: Work-life balance improved (60-hour weeks → 50-hour weeks), burnout reduced, retention improved

**Timeline**:
- **Phase 1 (Months 1-6, Discovery & Alpha)**: 0 hours saved (prototype only, no production use)
- **Phase 2 (Months 7-9, Private Beta)**: 8 hours saved per user per week (3 pilot departments, 500 users)
- **Phase 3 (Months 10-12, Public Beta)**: 9 hours saved per user per week (10 departments, 3,000 users)
- **Phase 4 (Year 2, Live)**: 10 hours saved per user per week (20+ departments, 10,000+ users)
- **Sustainment (Year 3-5)**: 10+ hours maintained (continuous AI improvements, user proficiency increases)

**Stakeholder Benefits**:
- **Users (SD-11)**: Time saved for strategic thinking, work-life balance improved, job satisfaction increased
- **Ministers**: Policy advisors have more capacity for high-value analysis (better policy advice)
- **Departments**: Productivity gain equivalent to 2,500 FTEs without hiring (addresses headcount constraints)

**Leading Indicators** (early signals of success):
- Usage volume increasing (Month 9: 10,000 queries/week, Month 12: 50,000 queries/week)
- User retention high (Month 12: 80% monthly active users return next month)
- User testimonials positive ("AI saves me 10 hours per week, I can think strategically now")
- Training completion rate high (90% of users complete 2-hour onboarding)

**Lagging Indicators** (final proof of success):
- Quarterly user surveys report 10 hours saved per week (Year 2)
- Usage analytics show sustained engagement (10,000+ monthly active users, 200,000+ queries/month)
- User satisfaction > 4.2/5 (Year 2, proves time savings translate to satisfaction)
- Retention improved (civil service turnover down from 25% to 20%, exit surveys cite AI as benefit)

---

## Complete Traceability Matrix

### Stakeholder → Driver → Goal → Outcome

| Stakeholder | Driver ID | Driver Summary | Goal ID | Goal Summary | Outcome ID | Outcome Summary |
|-------------|-----------|----------------|---------|--------------|------------|-----------------|
| **Minister** | SD-1 | Deliver manifesto commitment | G-1 | 80% cost reduction | O-1 | £60M savings over 5 years |
| **Minister** | SD-1 | Responsible AI leadership | G-6 | AI Playbook > 90% | O-4 | AI governance exemplar |
| **Permanent Secretary** | SD-2 | Avoid Accounting Officer concerns | G-1 | 80% cost reduction | O-1 | £60M savings, NAO-proof |
| **Permanent Secretary** | SD-2 | Risk management | G-2 | Zero security incidents | O-2 | Zero breaches over 5 years |
| **Permanent Secretary** | SD-2 | Governance oversight | G-6 | AI Playbook > 90% | O-4 | Robust governance framework |
| **CTO** | SD-3 | Modernize technology | G-1 | 80% cost reduction | O-1 | Centralized modern platform |
| **CTO** | SD-3 | Talent attraction | G-4 | User satisfaction > 4.2 | O-5 | 10 hours saved per user/week |
| **CTO** | SD-3 | Innovation leadership | G-6 | AI Playbook > 90% | O-4 | Cabinet Office AI leader |
| **CDDO** | SD-4 | TCoP compliance | G-5 | Pass GDS Service Assessment | O-3 | 20+ departments adopt |
| **HM Treasury** | SD-5 | Value for money | G-1 | 80% cost reduction | O-1 | £60M savings, 253% ROI |
| **NCSC** | SD-6 | Secure multi-tenant architecture | G-2 | Zero security incidents | O-2 | Zero breaches, Cyber Essentials Plus |
| **ICO** | SD-7 | GDPR compliance | G-2 | Zero security incidents | O-2 | Zero data breaches |
| **ICO** | SD-7 | Algorithmic transparency | G-3 | ATRS published (Month 12) | O-4 | ATRS on GOV.UK |
| **ICO** | SD-7 | Ethical AI | G-6 | AI Playbook > 90% | O-4 | DPIA approved, bias testing passed |
| **Home Office** | SD-8 | Immigration use cases | G-4 | User satisfaction > 4.2 | O-5 | 10 hours saved (case analysis) |
| **Home Office** | SD-8 | Data security | G-2 | Zero cross-tenant leaks | O-2 | UKVI data isolated |
| **HMRC** | SD-9 | Tax guidance efficiency | G-4 | User satisfaction > 4.2 | O-5 | 10 hours saved (legislation analysis) |
| **HMRC** | SD-9 | Taxpayer confidentiality | G-2 | Zero cross-tenant leaks | O-2 | Tax data isolated |
| **DHSC** | SD-10 | Health policy analysis | G-4 | User satisfaction > 4.2 | O-5 | 10 hours saved (evidence synthesis) |
| **DHSC** | SD-10 | GDPR (health data) | G-2 | Zero security incidents | O-2 | Health data protected |
| **Users** | SD-11 | Reduce workload | G-4 | User satisfaction > 4.2 | O-5 | 10 hours saved per week |
| **GDS** | SD-12 | Service Standard compliance | G-5 | Pass Service Assessment | O-3 | 20+ departments adopt (proves quality) |
| **NAO/PAC** | SD-13 | Value for money oversight | G-1 | 80% cost reduction | O-1 | £60M savings, transparent governance |

### Conflict Analysis

**Competing Drivers**:

**Conflict 1: Speed vs Security**
- **Stakeholder A**: Minister (SD-1) wants **quick delivery** to meet manifesto commitment before election (12-month deadline)
- **Stakeholder B**: NCSC (SD-6) and Permanent Secretary (SD-2) need **thorough security assurance** to avoid data breaches (may require 18-24 months)
- **Incompatibility**: Rushing delivery without full security testing risks catastrophic breach (career-ending for Minister and Permanent Secretary)
- **Resolution Strategy**:
  - **Phased rollout**: Private Beta with 3 departments (Month 6-9) allows early delivery milestone for Minister while NCSC conducts incremental security reviews
  - **Risk-based approach**: Pilot departments handle lower-risk use cases first (policy document analysis, not asylum/tax case decisions)
  - **Transparent communication**: Minister briefed on security timeline trade-offs, decision documented in Steering Committee minutes
  - **Success metrics**: Minister gets "Private Beta launch" milestone for parliamentary questions (Month 9), NCSC gets full security assurance before full rollout (Month 12)

**Conflict 2: Centralization vs Autonomy**
- **Stakeholder A**: Cabinet Office CTO (SD-3) wants **centralized platform** to reduce costs and enforce standards
- **Stakeholder B**: Departments (SD-8, SD-9, SD-10) want **autonomy** to build specialized AI for their unique needs (immigration law, tax law, health policy)
- **Incompatibility**: Centralized platform may lack department-specific features (e.g., HMRC tax legislation training, Home Office immigration case law), departments resist adoption
- **Resolution Strategy**:
  - **Hybrid model**: Centralized platform provides core AI infrastructure (multi-tenant, security, compliance), departments can fine-tune with own knowledge bases
  - **Customization layer**: Departments upload own documents (immigration case law, tax manuals, health guidelines), AI trained on departmental corpus
  - **Governance**: Cabinet Office owns platform infrastructure, departments own domain knowledge and use cases
  - **Success metrics**: 80% centralized (infrastructure, security, compliance), 20% departmental customization (knowledge bases, workflows)

**Conflict 3: Innovation vs Risk Aversion**
- **Stakeholder A**: CTO (SD-3) wants **cutting-edge AI** (GPT-4, Claude 3, multimodal AI) to attract talent and demonstrate innovation
- **Stakeholder B**: NCSC (SD-6) and ICO (SD-7) have **risk concerns** about generative AI (hallucinations, bias, data leaks, vendor lock-in)
- **Incompatibility**: Newest AI models may lack security certifications, vendor data residency guarantees, or explainability features required by NCSC/ICO
- **Resolution Strategy**:
  - **Approved vendor list**: Use only AI providers with UK data residency and government contracts (Azure OpenAI UK, AWS Bedrock UK, Anthropic Claude UK endpoint)
  - **Human-in-the-loop**: AI provides recommendations, human makes final decision (reduces risk of AI errors)
  - **Explainability**: Require source attribution and confidence scores (not black box AI)
  - **Bias testing**: Quarterly bias audits across demographics and departments
  - **Success metrics**: Innovation (cutting-edge models used) + Safety (human oversight, bias testing, explainability)

**Conflict 4: Fast User Onboarding vs Comprehensive Training**
- **Stakeholder A**: CTO (SD-3) wants **fast onboarding** (10,000 users in 6 months) to achieve adoption targets
- **Stakeholder B**: Users (SD-11) need **comprehensive training** to use AI effectively (2-hour onboarding, ongoing support)
- **Incompatibility**: Fast onboarding without training → poor user experience → low satisfaction → failed adoption
- **Resolution Strategy**:
  - **Tiered training**: Self-service quick start (30 mins video) + optional deep-dive workshop (2 hours) + office hours (weekly Q&A)
  - **In-app guidance**: Tooltips, contextual help, example prompts (reduces training burden)
  - **Department champions**: 2-3 power users per department (trained deeply) train colleagues (train-the-trainer model)
  - **Asynchronous training**: On-demand videos, not mandatory in-person sessions (scales to 10,000 users)
  - **Success metrics**: 90% complete quick start, 80% monthly active users (proves training adequate)

**Synergies**:

**Synergy 1: Cost Reduction + Security + Governance**
- **Stakeholders**: Minister (SD-1), Permanent Secretary (SD-2), HM Treasury (SD-5), NCSC (SD-6), CDDO (SD-4)
- **Alignment**: All stakeholders benefit from centralized platform with robust security and governance
  - **Minister**: Cost savings demonstrate fiscal responsibility, security avoids scandals
  - **Permanent Secretary**: Value for money satisfies NAO, security protects Accounting Officer
  - **HM Treasury**: £60M savings support Autumn Statement, Green Book compliance satisfied
  - **NCSC**: Centralized security review (not 20+ departmental reviews), Secure by Design principles enforced
  - **CDDO**: TCoP compliance easier with centralized platform (cloud-first, API-first, open standards)
- **Outcome**: Goal G-1 (cost reduction), G-2 (security), G-5 (GDS Service Assessment) mutually reinforce each other

**Synergy 2: User Satisfaction + Adoption + Savings**
- **Stakeholders**: Users (SD-11), CTO (SD-3), HM Treasury (SD-5)
- **Alignment**: User satisfaction drives adoption, adoption drives cost savings
  - **Users**: High satisfaction (10 hours saved per week) → recommend to colleagues → viral adoption
  - **CTO**: User satisfaction validates technology choices, drives talent attraction
  - **HM Treasury**: Adoption (20+ departments) required to achieve £60M savings
- **Outcome**: Goal G-4 (user satisfaction > 4.2) drives Outcome O-3 (20+ departments adopt) which enables Outcome O-1 (£60M savings)

**Synergy 3: Transparency + Trust + Compliance**
- **Stakeholders**: Minister (SD-1), ICO (SD-7), Users (SD-11)
- **Alignment**: Transparency (ATRS, AI Playbook) builds trust and satisfies regulatory compliance
  - **Minister**: ATRS publication demonstrates responsible AI, positive media coverage
  - **ICO**: ATRS and AI Playbook compliance reduce regulatory risk, prove ethical AI
  - **Users**: Transparency (explainability, source attribution) builds trust, users understand AI decisions
- **Outcome**: Goal G-3 (ATRS published), G-6 (AI Playbook > 90%) enable Outcome O-4 (AI governance exemplar)

---

## Communication & Engagement Plan

### Stakeholder-Specific Messaging

#### Minister for Cabinet Office

**Primary Message**: "We are delivering your manifesto commitment to 'harness AI safely across government' with a centralized, secure AI platform that will save £60M over 5 years while demonstrating responsible AI leadership to Parliament and the public."

**Key Talking Points**:
1. **Manifesto Delivery**: Private Beta launch Month 9 (3 departments), Public Beta Month 12 (10 departments) - demonstrable progress before election
2. **Cost Savings**: £60M savings over 5 years, 80% reduction in duplicate AI spending - fiscal responsibility proven
3. **Responsible AI**: AI Playbook compliance > 90%, ATRS published on GOV.UK - transparency and ethics prioritized
4. **Parliamentary Defense**: Zero security incidents, ICO-approved DPIA, NCSC-reviewed architecture - no scandals, defensible in parliament
5. **International Recognition**: Cabinet Office cited as AI governance exemplar by OECD, EU - UK leadership demonstrated

**Communication Frequency**: Monthly ministerial briefings (30 mins), ad-hoc parliamentary Q&A prep

**Preferred Channel**: In-person briefings (Private Office), written briefings for parliamentary questions

**Success Story**: "Minister announces in Parliament: 'We have delivered our manifesto commitment, saving taxpayers £60M while ensuring responsible AI governance. Cabinet Office sets the standard for ethical AI across government.'"

---

#### Cabinet Office Permanent Secretary (Accounting Officer)

**Primary Message**: "This project has robust governance, independent assurance, and quantified value for money (253% ROI) to protect your Accounting Officer accountability and avoid NAO criticism."

**Key Talking Points**:
1. **NAO Readiness**: Green Book-compliant business case (independent QA), Orange Book risk register (quarterly reviews), Architecture Decision Records (audit trail)
2. **Value for Money**: £60M savings, 253% ROI, chargeback model (departments pay after Year 1, not centrally funded)
3. **Risk Management**: Zero security incidents (NCSC-reviewed architecture, Cyber Essentials Plus), zero GDPR violations (ICO-approved DPIA)
4. **Governance Framework**: Steering Committee (fortnightly), AI Ethics Board (quarterly), Architecture Review Board (bi-weekly)
5. **Independent Assurance**: NCSC security review, ICO DPIA approval, GDS Service Assessment, independent business case QA

**Communication Frequency**: Weekly Steering Committee (1 hour), monthly risk review (30 mins)

**Preferred Channel**: Steering Committee meetings, written risk reports

**Success Story**: "NAO audit report: 'Cabinet Office GenAI Platform demonstrates exemplary governance, robust risk management, and value for money. A model for government technology projects.'"

---

#### Cabinet Office CTO

**Primary Message**: "This is your opportunity to modernize government technology, attract digital talent, and establish Cabinet Office as AI innovation leader across government."

**Key Talking Points**:
1. **Cutting-Edge Technology**: Azure OpenAI/Bedrock UK (latest models: GPT-4, Claude 3), cloud-native architecture (AWS/Azure UK regions)
2. **Talent Attraction**: Digital talent excited to work on government AI (recruitment easier, retention improved)
3. **Reusable Platform**: 20+ departments adopt centralized platform (Cabinet Office technology leadership proven)
4. **Industry Recognition**: Speaking slots at AWS re:Invent, Google Cloud Next, OECD AI policy forums
5. **Career Legacy**: "CTO who brought AI to government" - next role as CDDO CEO or return to private sector with strong track record

**Communication Frequency**: Daily project oversight (Slack, stand-ups), weekly architecture review

**Preferred Channel**: Daily Slack updates, weekly face-to-face architecture reviews

**Success Story**: "CTO presents at AWS re:Invent 2026: 'How Cabinet Office built a multi-tenant AI platform for 20+ UK Government departments.' Tech press: 'Government CTO proves public sector can deliver cutting-edge technology.'"

---

#### CDDO (Central Digital & Data Office)

**Primary Message**: "This project fully complies with Technology Code of Practice (13 points) and demonstrates the 'once across government' reuse model that CDDO champions."

**Key Talking Points**:
1. **TCoP Compliance**: All 13 points met (cloud-first, API-first, open standards, secure, accessible, privacy-by-design, reuse)
2. **Reusability**: 20+ departments adopt centralized platform (not 20 siloed solutions), APIs published (OpenAPI specs), GDS Design System used
3. **Open Standards**: OAuth 2.0, OIDC, OpenAPI 3.0 (no vendor lock-in), multi-cloud ready (not AWS-only or Azure-only)
4. **GDS Service Assessment**: Pass at Private Beta and Public Beta (14 Service Standard points met)
5. **Case Study**: CDDO publishes case study "How to build reusable AI platform across government" for other departments to replicate

**Communication Frequency**: Bi-weekly Architecture Review Board, quarterly TCoP compliance review

**Preferred Channel**: Architecture Review Board meetings, written compliance reports

**Success Story**: "CDDO CEO blog post: 'Cabinet Office GenAI Platform is a model for cross-government reuse. By following TCoP and GDS Service Standard, they delivered a platform that 20+ departments can use, not 20 duplicate solutions. This is how government should build technology.'"

---

#### HM Treasury

**Primary Message**: "This £18.8M investment delivers £60M savings over 5 years (253% ROI) with transparent governance and Green Book compliance, proving value for money."

**Key Talking Points**:
1. **Quantified Savings**: £60M over 5 years (£15M/year duplicate spending → £3M/year centralized platform)
2. **ROI**: 253% over 5 years, payback period 2 years
3. **Green Book Compliance**: 5-case model (Strategic, Economic, Commercial, Financial, Management), independent QA, sensitivity analysis
4. **Chargeback Model**: Departments pay £25/user/month after Year 1 (not centrally funded long-term)
5. **Quarterly Reporting**: Financial variance analysis, benefits tracking, forecast accuracy

**Communication Frequency**: Quarterly business case reviews (1 hour), annual Spending Review updates

**Preferred Channel**: Written business case reports, in-person quarterly reviews

**Success Story**: "Treasury Spending Review report: 'Cabinet Office GenAI Platform delivered £60M savings as projected, demonstrating that properly governed technology investments can deliver significant value for money. Recommended as case study for other departments.'"

---

#### NCSC (National Cyber Security Centre)

**Primary Message**: "We are implementing defense-in-depth multi-tenant security with zero tolerance for cross-tenant leaks, following NCSC Secure by Design guidance, and achieving Cyber Essentials Plus certification before go-live."

**Key Talking Points**:
1. **Secure by Design**: NCSC principles applied from inception (not security bolted on later)
2. **Multi-Tenant Isolation**: Row-Level Security (RLS), schema separation, tenant-specific encryption keys, penetration testing focused on tenant isolation
3. **Defense-in-Depth**: Network (WAF, VPC), Application (RBAC, input validation), Data (encryption at rest/transit, UK data residency)
4. **Cyber Essentials Plus**: Certification before Private Beta, annual re-cert
5. **Incident Response**: Runbook tested, SOC 24/7 monitoring, breach containment < 15 minutes

**Communication Frequency**: Monthly security architecture reviews (1 hour), quarterly penetration testing

**Preferred Channel**: Security architecture review meetings, penetration testing reports

**Success Story**: "NCSC blog post: 'Cabinet Office GenAI Platform demonstrates how to build secure multi-tenant architecture for OFFICIAL-SENSITIVE data. Zero security incidents over 3 years of operation. A model for government AI security.'"

---

#### ICO (Information Commissioner's Office)

**Primary Message**: "We are prioritizing GDPR compliance with a comprehensive DPIA, bias testing, human oversight, and ATRS publication to demonstrate responsible AI and data protection."

**Key Talking Points**:
1. **DPIA**: Completed using ICO template, independent review, ICO approval before Private Beta
2. **Lawful Basis**: Public task (Article 6(1)(e)), not consent (appropriate for government AI)
3. **Individual Rights**: Subject Access Request < 30 days, right to erasure implemented, privacy notice published
4. **Bias Testing**: Quarterly testing across demographics (age, gender, ethnicity, disability, department)
5. **ATRS**: Published on GOV.UK algorithmic transparency page (Tier 1 public summary + Tier 2 technical details)

**Communication Frequency**: Quarterly compliance reviews (1 hour), annual DPIA updates

**Preferred Channel**: Written DPIA submissions, in-person compliance reviews

**Success Story**: "ICO case study: 'Cabinet Office GenAI Platform demonstrates best practice for AI GDPR compliance. DPIA completed thoroughly, bias testing rigorous, ATRS published transparently. Other government departments should follow this model.'"

---

#### Home Office (UK Visas & Immigration)

**Primary Message**: "AI will help you analyze 200-page asylum case files in 30 minutes instead of 4 hours, while maintaining strict security for OFFICIAL-SENSITIVE immigration data with zero cross-department leaks."

**Key Talking Points**:
1. **Time Savings**: 200-page case file → 2-page summary in 30 minutes (not 4 hours manual reading)
2. **Case Law Search**: Find relevant precedents across 10,000 immigration cases (saves hours of legal research)
3. **Multi-Language**: Translate applicant documents from 50+ languages (asylum seekers from diverse countries)
4. **Security**: UKVI data isolated from HMRC, DHSC, MOJ (no cross-tenant leaks, NCSC-reviewed architecture)
5. **Training**: UKVI-specific knowledge base (immigration law, policy guidance, case law)

**Communication Frequency**: Weekly Private Beta feedback sessions (1 hour), bi-weekly user testing

**Preferred Channel**: User feedback sessions, in-app feedback widget

**Success Story**: "UKVI case worker testimonial: 'AI saves me 10 hours per week on case analysis. I can now focus on complex legal judgments instead of reading hundreds of pages. The system is fast, accurate, and secure.'"

---

#### Policy Advisors & Civil Servants (End Users)

**Primary Message**: "AI will save you 10 hours per week by automating document summarization, drafting, and research, giving you time back for strategic thinking and improving your work-life balance."

**Key Talking Points**:
1. **Time Savings**: 10 hours saved per week (reduce 60-hour weeks to 50-hour weeks, or free up time for high-value analysis)
2. **Task Automation**: Summarize 200-page documents in 2 minutes, draft initial policy papers in 1 hour (human edits), search 10,000 documents for "capital gains" in 30 seconds
3. **Quality Improvement**: AI provides evidence sources (cite page numbers, show quotes), alternative interpretations (consider multiple perspectives)
4. **Easy to Use**: Familiar GOV.UK interface (GDS Design System), fast response times (< 2 seconds), mobile-friendly
5. **Training & Support**: 2-hour onboarding, weekly office hours, in-app help, user community

**Communication Frequency**: Quarterly user surveys, weekly office hours (optional Q&A)

**Preferred Channel**: Email newsletters, in-app notifications, user community Slack channel

**Success Story**: "Policy advisor testimonial: 'AI has transformed my job. I used to spend 20 hours per week reading and summarizing documents. Now AI does that in 30 minutes. I have time to think strategically and my work-life balance has improved. I recommend this to every colleague.'"

---

## Change Impact Assessment

### Impact on Stakeholders

| Stakeholder | Current State | Future State | Change Magnitude | Resistance Risk | Mitigation Strategy |
|-------------|---------------|--------------|------------------|-----------------|---------------------|
| **Policy Advisors** | Manually read 200-page documents (4 hours), draft policy papers from scratch (2 days), search files manually (hours) | AI summarizes documents (30 mins), AI drafts initial papers (1 hour + human edits), AI searches 10,000 files (30 seconds) | HIGH | MEDIUM | **Training** (2-hour onboarding), **Champions** (power users in each department), **Quick wins** (show 10-hour time savings in first week) |
| **Departmental IT Teams** | Manage own AI tools (ChatGPT Enterprise, GitHub Copilot) contracts, licenses, security | Decommission departmental AI tools, migrate to centralized platform, rely on Cabinet Office IT | MEDIUM | HIGH | **Governance** (departments keep domain knowledge ownership), **Customization** (departments can upload own documents), **SLA** (99.9% uptime, < 2s response time guarantees) |
| **NCSC Security Teams** | Review 20+ departmental AI security architectures (fragmented, inconsistent) | Review 1 centralized platform security architecture (consistent, economies of scale) | LOW | LOW | **Early engagement** (NCSC involved in architecture design from Discovery), **Secure by Design** (NCSC principles applied), **Penetration testing** (CREST-certified, focus on tenant isolation) |
| **Finance Teams** | Procure departmental AI tools (RFPs, contracts, invoices) | Pay chargeback invoice to Cabinet Office (£25/user/month), simpler procurement | LOW | LOW | **Transparent pricing** (chargeback formula published), **Cost savings** (£125/user/month departmental vs £25/user/month centralized), **Monthly invoicing** (predictable costs) |
| **Senior Civil Servants** | Make policy decisions based on manual analysis (time-consuming, risk of missing evidence) | Make decisions based on AI-assisted analysis (faster, more comprehensive evidence review) | MEDIUM | MEDIUM | **Human-in-the-loop** (AI recommends, human decides), **Explainability** (show sources, confidence scores), **Transparency** (ATRS published, bias testing results public) |

### Change Readiness

**Champions** (Enthusiastic supporters):
- **Cabinet Office CTO (SD-3)**: Career incentive to deliver cutting-edge AI, attract digital talent, build reputation as technology leader
- **HM Treasury (SD-5)**: £60M savings align with Autumn Statement efficiency targets, Green Book compliance satisfied
- **Users frustrated with manual work (SD-11)**: 60-hour weeks, backlog stress, excited for 10-hour time savings per week

**Fence-sitters** (Neutral, need convincing):
- **Departmental IT Teams**: Concerned about losing control of AI tools, need reassurance on customization and SLA
- **Mid-level civil servants**: Skeptical of AI accuracy ("will it hallucinate?"), need proof of explainability and human oversight
- **GDS (SD-12)**: Supportive of user-centered design but will rigorously assess Service Standard compliance (need evidence pack)

**Resisters** (Opposed or skeptical):
- **Departments with existing AI investments**: Home Office already spent £2M on departmental ChatGPT Enterprise (sunk cost bias), resist switch
  - **Mitigation**: Highlight superior features (OFFICIAL-SENSITIVE data support, UK data residency, departmental knowledge bases), cost savings (£25/user vs £125/user), NCSC security assurance
- **Senior civil servants concerned about job displacement**: "Will AI replace policy advisors?"
  - **Mitigation**: Frame as "augmentation not replacement," AI handles admin (reading, summarizing), humans do strategic thinking (judgment, ethics, stakeholder management)
- **Risk-averse Permanent Secretaries**: Concerned about reputational risk of AI failure (bias scandal, data breach)
  - **Mitigation**: Robust governance (AI Ethics Board, quarterly bias testing), independent assurance (NCSC, ICO, NAO), phased rollout (3 pilot departments first, not 20 simultaneously)

---

## Risk Register (Stakeholder-Related)

### Risk R-1: Rushed Delivery Without Security Assurance

**Related Stakeholders**: Minister (SD-1 - wants speed), Permanent Secretary (SD-2 - accountable for security), NCSC (SD-6 - security assurance)

**Risk Description**: Ministerial pressure to deliver before election leads to rushed go-live without complete NCSC security review, penetration testing, or Cyber Essentials Plus certification, resulting in catastrophic data breach.

**Impact on Goals**: G-2 (zero security incidents) FAILED, G-1 (cost reduction) at risk if platform shut down after breach

**Probability**: MEDIUM (ministerial pressure high, but Permanent Secretary likely to resist)

**Impact**: CRITICAL (career-ending for Minister and Permanent Secretary, £17.5M ICO fine, media scandal, project cancelled)

**Mitigation Strategy**:
- **Governance**: Steering Committee decision (Permanent Secretary veto on go-live until NCSC approval)
- **Phased rollout**: Private Beta (Month 9, 3 departments, lower-risk use cases) satisfies Minister "launch milestone" while NCSC completes full review for Public Beta (Month 12)
- **Transparent communication**: Minister briefed on security vs speed trade-offs, decision documented ("Minister accepts 3-month delay for full NCSC assurance")
- **Red lines**: Permanent Secretary (Accounting Officer) will not approve go-live without: (1) NCSC security review passed, (2) Penetration testing 0 critical/high findings, (3) Cyber Essentials Plus certification

**Contingency Plan**: If Minister insists on go-live without security assurance, Permanent Secretary escalates to Cabinet Secretary and may issue formal "Accounting Officer Direction" (on record that Minister overruled Accounting Officer, NAO/PAC will scrutinize)

---

### Risk R-2: Departmental Resistance ("Our AI is Better")

**Related Stakeholders**: Departments (SD-8, SD-9, SD-10 - prefer own AI tools), Cabinet Office CTO (SD-3 - needs adoption for cost savings)

**Risk Description**: Departments with existing AI investments resist switching to centralized platform, claiming "our AI is better for our specific needs," resulting in low adoption (< 50%) and cost savings not realized.

**Impact on Goals**: G-1 (80% cost reduction) FAILED (if only 10 departments adopt, savings = £20M not £60M), O-3 (20+ departments adopt) FAILED

**Probability**: HIGH (Home Office already invested £2M in departmental ChatGPT, HMRC built tax AI in-house)

**Impact**: HIGH (business case fails, NAO criticism "projected savings not realized," CTO reputation damaged)

**Mitigation Strategy**:
- **Superior features**: Centralized platform offers capabilities departmental tools lack:
  - OFFICIAL-SENSITIVE data support (most departmental tools only OFFICIAL)
  - UK data residency guaranteed (some departmental tools use US data centers)
  - Multi-tenant security (NCSC-reviewed, Cyber Essentials Plus)
  - Departmental customization (upload own knowledge bases: immigration law, tax manuals, health guidelines)
- **Cost incentive**: £25/user/month centralized vs £125/user/month departmental (80% savings)
- **Mandate from centre**: CDDO/Cabinet Office Minister directive "all departments must use centralized platform by Year 2" (spending controls)
- **Quick wins**: Private Beta with Home Office, HMRC, DHSC proves value (user satisfaction > 4.2), creates peer pressure ("if HMRC uses it, why aren't we?")

**Contingency Plan**: If departmental resistance persists, Cabinet Office escalates to:
- **HM Treasury**: Spending controls (departments cannot procure own AI tools after Year 1, budget withheld)
- **CDDO Minister**: Ministerial directive (centralized platform mandatory for all departments)
- **Revised target**: Accept 70% adoption instead of 80% (15 departments instead of 20), cost savings reduced to £45M instead of £60M

---

### Risk R-3: Delayed Delivery (Platform Not Ready)

**Related Stakeholders**: Minister (SD-1 - manifesto deadline), HM Treasury (SD-5 - savings delayed), Users (SD-11 - continue manual work)

**Risk Description**: Technical complexity, security reviews, or vendor delays cause project to miss Private Beta (Month 9) and Public Beta (Month 12) milestones, delaying cost savings and manifesto delivery.

**Impact on Goals**: G-1 (cost reduction delayed, £60M becomes £40M if 2-year delay), O-1 (savings not realized on time)

**Probability**: MEDIUM (AI projects complex, security reviews rigorous, vendor dependencies)

**Impact**: MEDIUM (manifesto commitment missed, Minister embarrassed in parliament, NAO criticism "delayed delivery")

**Mitigation Strategy**:
- **Agile delivery**: 2-week sprints, MVP approach (core features first, nice-to-haves later)
- **Vendor management**: Contractual SLAs with AI providers (Azure OpenAI, AWS Bedrock), penalties for delays
- **NCSC early engagement**: Security reviews start in Discovery (not waiting until Beta), incremental approvals (Alpha prototype, Private Beta, Public Beta)
- **Risk contingency**: 3-month schedule buffer (plan for Month 9 Private Beta, but tell Minister "by end of Q4" to allow buffer)
- **Scope management**: MoSCoW prioritization (MUST: summarization, drafting; SHOULD: search, translation; COULD: multimodal AI, voice input)

**Contingency Plan**: If delay unavoidable:
- **Minister communication**: Private Office briefed early (3 months notice), not surprised at last minute
- **Phased benefits**: Even if full platform delayed, pilot departments achieve partial savings (£5M Year 1 instead of £12M)
- **Revised timeline**: Extend to 18 months instead of 12 months, adjust business case NPV (£50M savings instead of £60M)

---

### Risk R-4: Platform Cost Overruns

**Related Stakeholders**: HM Treasury (SD-5 - budget control), Permanent Secretary (SD-2 - Accounting Officer), NAO (SD-13 - value for money)

**Risk Description**: Cloud costs, AI API usage, or support costs exceed £3M/year projection (e.g., AI API usage 3x higher than forecast), eroding cost savings from £60M to £30M or negative ROI.

**Impact on Goals**: G-1 (cost reduction eroded), O-1 (£60M savings becomes £30M or worse)

**Probability**: MEDIUM (AI API costs variable, usage patterns uncertain)

**Impact**: HIGH (business case invalidated, NAO "poor cost estimation," Treasury budget pressure)

**Mitigation Strategy**:
- **Usage quotas**: Departments allocated quota (e.g., 1,000 queries/user/month), overage charged separately
- **Caching**: Cache frequent queries (e.g., "What is capital gains tax?"), reduce redundant AI API calls by 40%
- **Cost monitoring**: Real-time cost dashboard (daily AWS/Azure spend), alerts if monthly budget exceeded
- **Vendor negotiation**: Volume discounts with AI providers (committed spend £10M over 3 years, discount 20%)
- **Chargeback adjustments**: If costs rise, increase chargeback rate (£25/user → £35/user), departments pay for actual usage

**Contingency Plan**: If cost overruns occur:
- **Scope reduction**: Limit features to reduce costs (e.g., disable multimodal AI, limit query length)
- **Rationing**: Reduce departmental quotas (1,000 queries/user/month → 500 queries/user/month)
- **Treasury approval**: Request supplementary budget (justify with user adoption metrics, prove demand exceeds forecast)
- **Revised business case**: Update NPV calculation (£40M savings instead of £60M, still positive ROI 150%)

---

### Risk R-5: User Adoption Failure (Departments Sign Up But Don't Use)

**Related Stakeholders**: Users (SD-11 - need value), Cabinet Office CTO (SD-3 - needs adoption), HM Treasury (SD-5 - savings depend on usage)

**Risk Description**: Departments sign up for centralized platform (20+ departments committed) but users don't actually use it (low monthly active users < 3,000), cost savings not realized because departments still pay for own AI tools in parallel.

**Impact on Goals**: G-1 (cost reduction not realized, £60M savings phantom), G-4 (user satisfaction low), O-5 (time savings not achieved)

**Probability**: MEDIUM (government systems often have low adoption, users stick to familiar tools)

**Impact**: HIGH (business case fails, departmental AI tools not decommissioned, duplicate spending continues)

**Mitigation Strategy**:
- **User-centered design**: GDS Design System (familiar GOV.UK patterns), user research in Discovery/Alpha (understand needs)
- **Performance**: < 2s response time (faster than ChatGPT), 99.9% uptime (reliable)
- **Training**: 2-hour onboarding (show quick wins, "save 10 hours in first week"), weekly office hours (Q&A support)
- **Champions network**: 2-3 power users per department (evangelize to colleagues, peer pressure)
- **Decommission old tools**: Departments contractually commit to cancel ChatGPT Enterprise by Month 12 (not run parallel systems)
- **Usage tracking**: Monthly active users dashboard (departmental Digital Leads accountable for adoption targets)

**Contingency Plan**: If adoption low (< 50% monthly active users):
- **User research**: Understand barriers (too slow? inaccurate? hard to use?), fix issues
- **Incentives**: Gamification (leaderboards, badges for top users), departmental targets (Secretary of State accountable)
- **Mandate**: Cabinet Office Minister directive "all policy advisors must complete training and use platform for document summarization"
- **Revised savings**: Accept lower savings (£30M instead of £60M) if adoption capped at 50%

---

## Governance & Decision Rights

### Decision Authority Matrix (RACI)

| Decision Type | Responsible | Accountable | Consulted | Informed |
|---------------|-------------|-------------|-----------|----------|
| **Budget approval (£18.8M)** | HM Treasury Spending Team | Cabinet Office Permanent Secretary | Cabinet Office CTO, NAO | All stakeholders |
| **Requirements prioritization** | Cabinet Office Product Owner | Cabinet Office CTO | Home Office, HMRC, DHSC, MOJ (pilot departments), Policy Advisors | All departments |
| **Architecture decisions** | Cabinet Office Technical Architect | Cabinet Office CTO | CDDO (TCoP compliance), NCSC (security), Departmental Digital Leads | GDS, vendors |
| **Security approval (go-live)** | NCSC Security Assurance Team | Cabinet Office Permanent Secretary (Accounting Officer) | CISO, Departmental CISOs | Minister, HM Treasury |
| **GDPR compliance (DPIA approval)** | Cabinet Office Data Protection Officer | ICO (regulatory authority) | Departmental Data Protection Officers, AI Ethics Board | Permanent Secretary, Minister |
| **AI Playbook compliance** | Cabinet Office AI Ethics Lead | Cabinet Office Permanent Secretary | ICO, AI Ethics Board, Departmental Equality Leads | Minister, CDDO |
| **Service Assessment (GDS)** | Cabinet Office Product Owner | GDS Assessment Panel | CDDO, Departmental Digital Leads, Users | Cabinet Office CTO, Minister |
| **Vendor selection (AI provider)** | Cabinet Office Procurement | Cabinet Office CTO | CDDO (TCoP), NCSC (security), HM Treasury (commercial), Departmental CIOs | All stakeholders |
| **Go/No-go for Private Beta** | Cabinet Office Project Manager | Cabinet Office Permanent Secretary | NCSC (security), ICO (GDPR), GDS (Service Assessment), Steering Committee | Minister, HM Treasury |
| **Go/No-go for Public Beta** | Cabinet Office Project Manager | Cabinet Office Permanent Secretary | NCSC, ICO, GDS, Steering Committee, Pilot Departments | Minister, HM Treasury, All departments |
| **Go/No-go for Live** | Cabinet Office Project Manager | Cabinet Office Permanent Secretary | NCSC, ICO, GDS, Steering Committee, All 20+ departments | Minister, HM Treasury, NAO |
| **Chargeback pricing (£/user/month)** | HM Treasury Spending Team | Cabinet Office Permanent Secretary | Departmental Finance Directors, Cabinet Office Finance | All departments |
| **ATRS publication** | Cabinet Office AI Ethics Lead | Cabinet Office Permanent Secretary (Senior Responsible Owner) | ICO, AI Ethics Board, Departmental Communications | Minister (final approval for GOV.UK) |
| **User training curriculum** | Cabinet Office Learning & Development | Cabinet Office Product Owner | Departmental Learning Leads, Policy Advisors (user feedback), GDS | All users |
| **Incident response (security breach)** | Cabinet Office CISO | Cabinet Office Permanent Secretary (Accounting Officer) | NCSC (technical support), ICO (breach notification), Departmental CISOs | Minister (immediate escalation), HM Treasury, NAO, Media (if public) |

### Escalation Path

**Level 1: Project Manager / Product Owner** (day-to-day decisions)
- **Scope**: User stories prioritization, sprint planning, minor scope clarifications, vendor coordination, user feedback triage
- **Response Time**: < 24 hours
- **Examples**: "Should we prioritize summarization or search in next sprint?", "User requests PDF upload feature, add to backlog?"

**Level 2: Steering Committee** (bi-weekly, scope/timeline/budget variances)
- **Membership**: Cabinet Office CTO (Chair), CDDO, HM Treasury, NCSC, ICO, Departmental Digital Leads (Home Office, HMRC, DHSC)
- **Scope**: Scope changes > £100K, timeline delays > 1 month, budget variances > 10%, vendor performance issues, cross-departmental conflicts
- **Response Time**: < 2 weeks (next Steering Committee meeting)
- **Examples**: "Penetration testing found critical vulnerability, 6-week delay to remediate?", "Home Office requests immigration-specific AI model, £500K additional cost?"

**Level 3: Executive Sponsor (Cabinet Office Permanent Secretary)** (strategic direction, major conflicts)
- **Scope**: Strategic direction changes, major budget overruns (> 25%), ministerial escalations, NAO/PAC concerns, irresolvable stakeholder conflicts
- **Response Time**: < 1 week (urgent), < 1 month (strategic)
- **Examples**: "Cost overruns £18.8M → £30M, need supplementary budget?", "NCSC says 12-month delay for full security assurance, Minister wants go-live in 3 months, irresolvable conflict?"

**Level 4: Minister for Cabinet Office** (political decisions, parliamentary accountability)
- **Scope**: Manifesto commitment adjustments, parliamentary questions, media scandals, Cabinet-level approvals
- **Response Time**: < 48 hours (urgent), < 2 weeks (strategic)
- **Examples**: "Opposition MPs tabling parliamentary question on AI data breach, need ministerial response", "NAO critical report, Minister must appear before Public Accounts Committee"

---

## Validation & Sign-off

### Stakeholder Review

| Stakeholder | Review Date | Comments | Status |
|-------------|-------------|----------|--------|
| Minister for Cabinet Office | TBD | Awaiting review | PENDING |
| Cabinet Office Permanent Secretary | TBD | Awaiting review | PENDING |
| Cabinet Office CTO | TBD | Awaiting review | PENDING |
| CDDO | TBD | Awaiting review | PENDING |
| HM Treasury | TBD | Awaiting review | PENDING |
| NCSC | TBD | Awaiting review | PENDING |
| ICO | TBD | Awaiting review | PENDING |
| Home Office | TBD | Awaiting review | PENDING |
| HMRC | TBD | Awaiting review | PENDING |
| DHSC | TBD | Awaiting review | PENDING |
| GDS | TBD | Awaiting review | PENDING |

### Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Project Sponsor (Cabinet Office CTO) | | | |
| Accounting Officer (Permanent Secretary) | | | |
| Enterprise Architect | | | |
| AI Ethics Lead | | | |

---

## Appendices

### Appendix A: Stakeholder Interview Summaries

#### Interview with Cabinet Office Policy Advisor - 2025-10-15

**Key Points**:
- Spends 20 hours per week reading documents (legislation, research, briefings)
- Manual summarization error-prone ("I miss important details when tired")
- Drafting ministerial submissions takes 2 days ("AI could draft initial version in 1 hour, I edit")
- Concerned about AI accuracy ("Will it hallucinate? How do I verify sources?")
- Wants transparency ("Show me which document paragraph informed the answer")

**Quotes**:
- "If AI can save me 10 hours per week, I can finally do strategic thinking instead of admin. That would transform my job."
- "I need to trust AI outputs. If I can see sources and verify claims, I'll use it every day. If it's a black box, I won't risk it."

**Follow-up Actions**:
- Implement source attribution (show document paragraph, page number, quote)
- Implement confidence scores ("High confidence" vs "Low confidence")
- Training emphasizes "AI augments, human verifies" (not blind trust)

---

#### Interview with NCSC Security Architect - 2025-10-20

**Key Points**:
- Multi-tenant architecture is high-risk ("One misconfiguration = catastrophic cross-tenant leak")
- Row-Level Security (RLS) essential but not sufficient ("Defense-in-depth: RLS + schema separation + tenant-specific encryption keys")
- Penetration testing must focus on tenant isolation ("Not generic pen test, specific test: can Home Office user access HMRC data?")
- Cyber Essentials Plus baseline, not gold standard ("CE+ is minimum, we need more for OFFICIAL-SENSITIVE multi-tenant")
- Incident response critical ("If breach occurs, containment must be < 15 minutes, not 24 hours")

**Quotes**:
- "I've seen multi-tenant systems fail. It's always the same: shared database, weak RLS, one developer mistake, cross-tenant leak. We cannot allow that here."
- "This is OFFICIAL-SENSITIVE data across 20+ departments. If Home Office asylum data leaks to HMRC, it's not just a data breach, it's a national security incident."

**Follow-up Actions**:
- Architecture review with NCSC in Discovery phase (not waiting until Beta)
- Penetration testing RFP includes "tenant isolation testing" requirement
- Automated tenant isolation tests in CI/CD (prevent regression)
- Incident response tabletop exercise with NCSC (test < 15-minute containment)

---

### Appendix B: Survey Results

**User Needs Survey (October 2025)** - 150 policy advisors across 6 departments

**Time Spent on Manual Tasks**:
- Reading documents: 20 hours/week (average)
- Summarizing documents: 4 hours/week
- Drafting documents: 8 hours/week
- Searching for information: 3 hours/week
- **Total manual work**: 35 hours/week out of 40-hour week (87.5%)

**Desired AI Features** (ranked by importance):
1. Document summarization (95% rated "very important")
2. Drafting assistance (88% rated "very important")
3. Search across all departmental documents (82%)
4. Translation (multi-language documents) (65%)
5. Data analysis (charts, graphs from spreadsheets) (45%)

**Concerns About AI**:
1. Accuracy ("Will it hallucinate?") - 78%
2. Security ("Will my data leak?") - 72%
3. Bias ("Will it give biased policy advice?") - 68%
4. Job displacement ("Will AI replace me?") - 45%

**Willingness to Adopt**:
- Very willing: 35%
- Somewhat willing: 45%
- Neutral: 15%
- Unwilling: 5%

**Key Insight**: 80% willing to adopt if concerns (accuracy, security, bias) addressed through transparency (source attribution), security (NCSC-reviewed), and bias testing (quarterly audits).

---

### Appendix C: References

- **Architecture Principles**: `.arckit/memory/architecture-principles.md` (Cabinet Office Enterprise Architecture Principles)
- **Project README**: `projects/001-cabinet-office-genai/README.md` (Project overview, success criteria)
- **Analysis Report**: `projects/001-cabinet-office-genai/analysis-report.md` (Governance analysis, recommended execution sequence)
- **UK Government AI Playbook**: https://www.gov.uk/government/publications/ai-playbook (10 principles for responsible AI)
- **Algorithmic Transparency Recording Standard (ATRS)**: https://www.gov.uk/government/collections/algorithmic-transparency-recording-standard-atrs (Mandatory for central government)
- **Technology Code of Practice (TCoP)**: https://www.gov.uk/guidance/the-technology-code-of-practice (13-point standard)
- **GDS Service Standard**: https://www.gov.uk/service-manual/service-standard (14-point standard)
- **Green Book**: HM Treasury Green Book - Appraisal and Evaluation in Central Government (5-case business case model)
- **Orange Book**: HM Treasury Orange Book - Management of Risk - Principles and Concepts (Risk management framework)
- **NCSC Secure by Design**: https://www.ncsc.gov.uk/collection/secure-by-design (Security architecture guidance)

---

**Generated by**: ArcKit `/arckit.stakeholders` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Cabinet Office GenAI Platform (Project 001)
**AI Model**: claude-opus-4-5-20251101
