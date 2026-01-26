# Cabinet Office Enterprise Architecture Principles

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.principles`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-PRIN-v1.1 |
| **Document Type** | Enterprise Architecture Principles |
| **Project** | Cabinet Office GenAI Platform (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-02 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Annual |
| **Next Review Date** | 2027-01-26 |
| **Owner** | Cabinet Office Chief Technology Officer |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Cabinet Office Architecture Team, Cross-Government Digital Services |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-02 | ArcKit AI | Initial creation from `/arckit.principles` command | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to latest template format (0.11.2) | PENDING | PENDING |

---

## Executive Summary

This document establishes the immutable principles governing all technology architecture decisions at Cabinet Office and cross-government digital services. These principles ensure consistency, security, scalability, and alignment with UK Government standards across all projects and initiatives.

**Scope**: All Cabinet Office technology projects and cross-government digital services
**Authority**: Cabinet Office Enterprise Architecture Review Board
**Compliance**: Mandatory unless exception approved by CTO/CIO

**Philosophy**: These principles are **technology-agnostic** - they describe WHAT qualities the architecture must have, not HOW to implement them with specific products. Technology selection happens during research and design phases guided by these principles.

**UK Government Context**: These principles align with:
- **Technology Code of Practice (TCoP)**: UK Government's 13-point standard for technology projects
- **GDS Service Standard**: 14-point standard for digital services
- **NCSC Guidance**: National Cyber Security Centre security principles
- **AI Playbook**: Responsible AI principles for government AI systems
- **Green Book**: HM Treasury business case appraisal framework
- **Orange Book**: HM Treasury risk management framework

---

## I. Strategic Principles

### 1. Cloud-First (UK Government TCoP Point 5)

**Principle Statement**:
All systems MUST use public cloud infrastructure with UK-based data centers unless an explicit exception is granted. On-premise infrastructure is prohibited for new systems without CTO approval.

**Rationale**:
Cloud platforms provide scalability, resilience, pay-as-you-go economics, and security capabilities that on-premise infrastructure cannot match cost-effectively. UK Government TCoP mandates cloud-first approach.

**Implications**:
- Design for cloud-native patterns (stateless services, managed services, auto-scaling)
- Use UK regions for all data storage (UK South, UK West, eu-west-2 London)
- Avoid cloud provider lock-in through abstraction layers and open standards
- Leverage managed services (databases, message queues, object storage) over self-managed infrastructure
- Plan for multi-cloud capabilities where mission-critical (no single provider dependency)

**UK Data Residency Requirements**:
- All data MUST reside in UK data centers for data sovereignty
- Cross-border data transfers require legal basis (adequacy decisions, standard contractual clauses)
- Cloud services MUST support UK GDPR compliance
- Cloud providers MUST NOT be subject to extraterritorial data access laws that conflict with UK law

**Validation Gates**:
- [ ] System deployed to public cloud (AWS, Azure, GCP)
- [ ] All data centers located in UK regions
- [ ] No on-premise infrastructure without approved exception
- [ ] Managed services used where available (not self-managed VMs)
- [ ] Multi-cloud or cloud-agnostic design for critical systems
- [ ] Data residency requirements validated

**Exception Process**:
Valid exceptions require CTO approval:
- Legal/regulatory requirement for on-premise (e.g., SECRET data)
- Integration with legacy systems during transition period (time-boxed)
- Specific security requirements not met by public cloud

---

### 2. API-First and Interoperability (UK Government TCoP Point 3, 9)

**Principle Statement**:
All systems MUST expose functionality through well-defined, versioned APIs using open standards. Direct database access across system boundaries is prohibited. APIs MUST use open standards to enable interoperability and avoid vendor lock-in.

**Rationale**:
UK Government TCoP requires use of open standards and interoperable systems. APIs enable service reuse, integration, and independent evolution of systems.

**Open Standards Requirements**:
- HTTP REST APIs MUST provide OpenAPI 3.0+ specifications
- GraphQL APIs MUST provide published schemas
- Event-driven systems MUST use AsyncAPI specifications
- Authentication MUST use OAuth 2.0, OpenID Connect (OIDC), or SAML 2.0
- Data formats MUST use open standards (JSON, XML, CSV) not proprietary formats
- Avoid vendor-specific protocols or proprietary APIs

**API Design Standards**:
- Use semantic versioning (v1, v2, v3)
- Maintain backward compatibility for at least 12 months
- Provide deprecation notices 6 months before breaking changes
- Use standard HTTP status codes (200, 201, 400, 401, 403, 404, 500)
- Implement rate limiting and throttling
- Provide pagination for list endpoints
- Use HATEOAS for discoverability (Hypertext As The Engine Of Application State)

**Validation Gates**:
- [ ] API specifications published (OpenAPI, AsyncAPI, GraphQL schema)
- [ ] Open standards used (no proprietary protocols)
- [ ] Versioning strategy defined and documented
- [ ] Authentication uses OAuth 2.0 / OIDC / SAML 2.0
- [ ] No direct database coupling across system boundaries
- [ ] API documentation published for consumers
- [ ] Rate limiting and throttling implemented

**Common Violations to Avoid**:
- ❌ Using vendor-specific APIs (AWS-only, Azure-only without abstraction)
- ❌ Direct database access across systems
- ❌ Breaking API changes without versioning
- ❌ Proprietary data formats (e.g., vendor-specific binary formats)

---

### 3. Reuse Before Buy, Buy Before Build (UK Government TCoP Point 4, 8)

**Principle Statement**:
Systems MUST reuse existing government shared services and open-source components before procuring commercial off-the-shelf (COTS), and MUST procure COTS before custom development.

**Rationale**:
Reuse reduces cost, accelerates delivery, and benefits from collective investment across government. UK Government TCoP mandates making use of open source and sharing/reusing technology.

**Decision Hierarchy**:
1. **REUSE**: UK Government shared services (GOV.UK Notify, Pay, Verify, PaaS)
2. **REUSE**: Open-source components with active communities
3. **BUY**: Commercial off-the-shelf (COTS) via G-Cloud framework
4. **BUILD**: Custom development only when above options unsuitable

**GOV.UK Shared Services** (use where applicable):
- **GOV.UK Notify**: Emails, SMS, letters
- **GOV.UK Pay**: Payment processing
- **GOV.UK Verify**: Identity verification
- **GOV.UK PaaS**: Platform as a Service (Cloud Foundry)
- **GOV.UK Design System**: UI components and patterns
- **GOV.UK Forms**: Form building and processing

**Open Source Considerations**:
- Prefer open-source components with active maintenance
- Evaluate license compatibility (Apache 2.0, MIT, BSD preferred)
- Assess community health (contributors, release frequency, issue response)
- Contribute improvements back to open-source projects (where beneficial to government)

**Build vs Buy Decision Criteria**:
Document justification if building custom instead of buying:
- [ ] Existing solutions evaluated (shared services, open-source, COTS)
- [ ] Cost comparison (5-year TCO) between build and buy
- [ ] Risk assessment (vendor lock-in, support, security)
- [ ] Capability gap analysis (why existing solutions insufficient)
- [ ] Wardley Mapping to validate build vs buy decision

**Validation Gates**:
- [ ] GOV.UK shared services evaluated and used where applicable
- [ ] Open-source components evaluated before COTS
- [ ] Commercial solutions evaluated before custom build
- [ ] Build vs buy decision documented with justification
- [ ] Open-source contributions considered for custom components

---

### 4. Security by Design (UK Government TCoP Point 6, NCSC Principles)

**Principle Statement** (NON-NEGOTIABLE):
All architectures MUST implement defense-in-depth security with zero-trust principles aligned with NCSC guidance. Security is NOT a feature to be added later—it is a foundational requirement.

**Rationale**:
UK Government handles sensitive data (OFFICIAL, OFFICIAL-SENSITIVE, SECRET) requiring robust security. NCSC principles mandate security by design, defense-in-depth, and zero trust architecture.

**NCSC Secure by Design Principles**:
1. **Establish context before designing**: Understand threat landscape, data classification, user needs
2. **Make compromise difficult**: Defense-in-depth, least privilege, secure defaults
3. **Make disruption difficult**: Resilience, redundancy, graceful degradation
4. **Make compromise detection easier**: Logging, monitoring, anomaly detection
5. **Reduce impact of compromise**: Segmentation, blast radius reduction, rapid response

**Zero Trust Architecture** (MUST implement):
1. **Verify Explicitly**: Every access request authenticated and authorized
2. **Least Privilege Access**: Minimum permissions, time-boxed where possible
3. **Assume Breach**: Design for containment, detection, and response

**Mandatory Security Controls**:

**Identity and Access**:
- [ ] Multi-factor authentication (MFA) for all human users
- [ ] Service-to-service authentication (mutual TLS, signed tokens, or API keys with rotation)
- [ ] Role-Based Access Control (RBAC) with least privilege
- [ ] Privileged Access Management (PAM) for administrative access
- [ ] Single Sign-On (SSO) via Government Gateway or departmental identity provider

**Data Protection**:
- [ ] Encryption at rest for all data stores (databases, object storage, backups)
- [ ] Encryption in transit for all network communication (TLS 1.2+ minimum, prefer TLS 1.3)
- [ ] Secrets management via secure vault (AWS Secrets Manager, Azure Key Vault, HashiCorp Vault)
- [ ] No secrets in code, configuration files, or environment variables
- [ ] Key rotation policy defined and automated

**Network Security**:
- [ ] Network segmentation with micro-segmentation where feasible
- [ ] Web Application Firewall (WAF) for internet-facing services
- [ ] DDoS protection for public endpoints
- [ ] Private subnets for data and application tiers
- [ ] No direct internet access from backend systems (use NAT gateways)

**Application Security**:
- [ ] Input validation and output encoding (prevent injection attacks)
- [ ] Dependency scanning for vulnerabilities (daily scans)
- [ ] Static Application Security Testing (SAST) in CI/CD pipeline
- [ ] Dynamic Application Security Testing (DAST) in pre-production
- [ ] Software Bill of Materials (SBOM) maintained for all components

**Monitoring and Response**:
- [ ] Structured logging of all authentication and authorization events
- [ ] Security Information and Event Management (SIEM) integration
- [ ] Automated alerting for security anomalies
- [ ] Incident response runbook with escalation procedures
- [ ] Regular security testing (penetration testing, red team exercises)

**Cyber Essentials / Cyber Essentials Plus**:
- [ ] Cyber Essentials certification for OFFICIAL data
- [ ] Cyber Essentials Plus certification for OFFICIAL-SENSITIVE data
- [ ] Annual re-certification maintained

**Data Classification-Specific Controls**:

| Classification | Controls Required |
|----------------|-------------------|
| **PUBLIC** | Basic security hygiene, no special controls |
| **OFFICIAL** | Encryption in transit, access controls, Cyber Essentials |
| **OFFICIAL-SENSITIVE** | Encryption at rest/transit, MFA, audit logging, Cyber Essentials Plus, Data Protection Impact Assessment (DPIA) |
| **SECRET** | Air-gap or assured network, personnel security clearance (SC), enhanced physical security, encryption with CESG-approved cryptography |
| **TOP SECRET** | Compartmented security, DV-cleared personnel, strict need-to-know, air-gapped systems |

**Validation Gates**:
- [ ] Threat model completed and reviewed
- [ ] Data classification assigned and controls mapped
- [ ] Security controls implemented per classification
- [ ] Cyber Essentials (Plus) certification obtained
- [ ] Penetration testing passed
- [ ] Incident response runbook created and tested
- [ ] Security logging and monitoring operational

**Exceptions**:
NONE. Security principles are non-negotiable. Specific control implementations may vary with compensating controls approved by NCSC or departmental security team.

---

### 5. Privacy by Design and GDPR/UK GDPR Compliance (UK Government TCoP Point 7)

**Principle Statement** (NON-NEGOTIABLE):
All systems MUST embed privacy by design principles and comply with GDPR/UK GDPR. Data Protection Impact Assessments (DPIA) are MANDATORY for systems processing personal data at scale or sensitive personal data.

**Rationale**:
UK Government is subject to UK GDPR and Data Protection Act 2018. Information Commissioner's Office (ICO) enforces compliance with fines up to £17.5M or 4% of turnover. Privacy by design is a legal requirement, not optional.

**Privacy by Design Principles** (Article 25 GDPR):
1. **Data Minimization**: Collect only data necessary for stated purpose
2. **Purpose Limitation**: Use data only for original purpose (or compatible purpose)
3. **Storage Limitation**: Retain data only as long as necessary
4. **Accuracy**: Keep data accurate and up to date
5. **Integrity and Confidentiality**: Protect data with appropriate security
6. **Accountability**: Demonstrate compliance with GDPR

**GDPR/UK GDPR Mandatory Requirements**:

**Lawful Basis for Processing**:
- [ ] Lawful basis identified for all personal data processing (consent, contract, legal obligation, vital interests, public task, legitimate interests)
- [ ] Public task is most common basis for government (Article 6(1)(e))
- [ ] Consent obtained where required (explicit, informed, freely given, specific)

**Individual Rights** (MUST support):
- [ ] **Right to be informed**: Privacy notices provided
- [ ] **Right of access**: Subject Access Requests (SAR) fulfilled within 30 days
- [ ] **Right to rectification**: Ability to correct inaccurate data
- [ ] **Right to erasure**: "Right to be forgotten" implemented (within legal constraints)
- [ ] **Right to restrict processing**: Ability to pause processing
- [ ] **Right to data portability**: Export data in machine-readable format
- [ ] **Right to object**: Ability to object to processing

**Data Protection Impact Assessment (DPIA)**:
MANDATORY when processing is likely to result in high risk, including:
- [ ] Large-scale processing of sensitive personal data (special categories)
- [ ] Systematic monitoring of public areas (CCTV, biometrics)
- [ ] Automated decision-making with legal or significant effects
- [ ] Processing of children's data
- [ ] Innovative use of technology (AI, machine learning)

**DPIA Required for This Project**: YES (generative AI, cross-government scale, OFFICIAL-SENSITIVE data)

**Data Breach Procedures**:
- [ ] Breach detection capability (security monitoring)
- [ ] Breach notification to ICO within 72 hours (if high risk)
- [ ] Breach notification to affected individuals (if high risk to rights and freedoms)
- [ ] Breach investigation and remediation process
- [ ] Breach register maintained

**Data Sharing and Transfers**:
- [ ] Data sharing agreements for inter-departmental sharing
- [ ] Standard Contractual Clauses (SCCs) for international transfers
- [ ] Adequacy decisions validated for international transfers (UK-EU adequacy)
- [ ] No transfers to inadequate jurisdictions without safeguards

**Validation Gates**:
- [ ] Data Protection Impact Assessment (DPIA) completed
- [ ] Lawful basis for processing identified
- [ ] Privacy notice published
- [ ] Individual rights mechanisms implemented (SAR, erasure, portability)
- [ ] Data retention policy defined with automated deletion
- [ ] Breach detection and notification procedures in place
- [ ] Data sharing agreements documented
- [ ] ICO registration updated

**Exceptions**:
NONE. GDPR compliance is a legal requirement. Exemptions exist for specific scenarios (e.g., national security, law enforcement) but require legal review.

---

### 6. Accessibility and Inclusion (UK Government TCoP Point 2, GDS Service Standard)

**Principle Statement**:
All digital services MUST meet WCAG 2.2 Level AA accessibility standards and follow GDS Design System patterns. Services MUST be usable by all citizens regardless of disability, device, or digital literacy.

**Rationale**:
UK Public Sector Bodies Accessibility Regulations 2018 legally require WCAG 2.1 AA compliance. GDS Service Standard Point 5 mandates accessibility. Approximately 1 in 5 UK citizens have a disability.

**WCAG 2.2 Level AA Requirements** (MANDATORY):

**Perceivable**:
- [ ] Text alternatives for non-text content (images, videos, audio)
- [ ] Captions and transcripts for multimedia
- [ ] Content adaptable to different presentations (mobile, tablet, desktop, screen readers)
- [ ] Sufficient color contrast (4.5:1 for text, 3:1 for large text and UI components)
- [ ] Text resizable up to 200% without loss of functionality

**Operable**:
- [ ] All functionality available via keyboard (no mouse-only interactions)
- [ ] No keyboard traps (users can navigate away)
- [ ] Sufficient time to complete tasks (or ability to extend time)
- [ ] No content that causes seizures (flashing < 3 times per second)
- [ ] Clear navigation and focus indicators

**Understandable**:
- [ ] Content readable at appropriate literacy level (Plain English)
- [ ] Predictable navigation and interaction patterns
- [ ] Error messages clear and actionable
- [ ] Help and guidance available

**Robust**:
- [ ] Compatible with assistive technologies (screen readers, voice control, magnifiers)
- [ ] Valid HTML/CSS (parseable by assistive technologies)
- [ ] Progressive enhancement (works without JavaScript where possible)

**GDS Design System** (MUST use):
- [ ] GOV.UK Design System components (buttons, forms, navigation, notifications)
- [ ] GDS typography, spacing, and layout
- [ ] GDS accessibility patterns (skip links, error summaries, focus styles)
- [ ] GOV.UK Frontend library (not custom CSS frameworks)

**Assisted Digital Support**:
- [ ] Alternative channels for users unable to use digital service (phone, post, in-person)
- [ ] Support for users with low digital literacy
- [ ] Multi-language support where user base requires (Welsh for Wales-specific services)

**Validation Gates**:
- [ ] WCAG 2.2 Level AA compliance validated
- [ ] Automated accessibility testing in CI/CD pipeline (axe, Pa11y, WAVE)
- [ ] Manual accessibility testing with assistive technologies
- [ ] User research with disabled users
- [ ] GDS Design System components used
- [ ] Accessibility statement published
- [ ] Accessibility audit conducted before Public Beta

**Legal Requirement**:
Accessibility statement MUST be published at `/accessibility-statement` with:
- Compliance status (fully compliant, partially compliant, non-compliant)
- Known accessibility issues and planned remediation
- Contact details for accessibility feedback
- Enforcement procedure (how to escalate complaints)

---

### 7. Observability and Operational Excellence

**Principle Statement**:
All systems MUST emit structured telemetry (logs, metrics, traces) enabling real-time monitoring, troubleshooting, capacity planning, and security incident detection. Service Level Objectives (SLOs) MUST be defined and monitored.

**Rationale**:
We cannot operate what we cannot observe. GDS Service Standard requires continuous monitoring and performance measurement. NCSC requires security logging for incident detection.

**Telemetry Requirements** (MUST implement):

**Logging** (Structured JSON logs):
- [ ] Application logs with correlation IDs (request tracing)
- [ ] Security logs (authentication, authorization, access, failures)
- [ ] Audit logs (who did what, when) for compliance
- [ ] Error logs with stack traces and context
- [ ] Business event logs (transactions, user actions)

**Metrics** (Time-series data):
- [ ] Request volume (requests per second, per minute)
- [ ] Latency percentiles (p50, p95, p99, p99.9)
- [ ] Error rate (4xx, 5xx HTTP status codes)
- [ ] Resource utilization (CPU, memory, disk, network)
- [ ] Business metrics (transactions completed, users active, revenue impact)

**Tracing** (Distributed tracing):
- [ ] Request tracing across microservices
- [ ] Trace context propagation (W3C Trace Context standard)
- [ ] End-to-end latency breakdown (identify bottlenecks)

**Service Level Objectives (SLOs)**:
- [ ] **Availability SLO**: e.g., 99.9% uptime (< 43.8 min downtime/month)
- [ ] **Latency SLO**: e.g., p95 response time < 2 seconds
- [ ] **Error Rate SLO**: e.g., < 0.1% error rate
- [ ] Error budgets calculated and tracked

**Alerting**:
- [ ] SLO-based alerts (not threshold-based)
- [ ] Actionable alerts with runbooks
- [ ] Escalation procedures for critical alerts
- [ ] Alert fatigue mitigation (reduce noise, aggregate related alerts)

**Log Retention** (UK Government):
- [ ] **Audit logs**: 7 years (HM Government retention schedule)
- [ ] **Security logs**: 12 months minimum (NCSC guidance)
- [ ] **Application logs**: 90 days for troubleshooting
- [ ] **Metrics**: 1-2 years with aggregation for long-term trends

**Validation Gates**:
- [ ] Structured logging implemented with correlation IDs
- [ ] Metrics instrumented (request volume, latency, errors, resource utilization)
- [ ] Distributed tracing implemented
- [ ] Dashboards created for service health
- [ ] SLOs defined and monitored
- [ ] Alerts configured with runbooks
- [ ] Log retention complies with government schedule

---

### 8. Resilience and Fault Tolerance

**Principle Statement**:
All systems MUST gracefully degrade when dependencies fail and recover automatically without data loss or manual intervention. Systems MUST be designed for failure.

**Rationale**:
Failures are inevitable in distributed systems. GDS Service Standard requires services to work reliably. NCSC requires resilience against disruption.

**Resilience Patterns** (MUST implement):

**Circuit Breaker**:
- [ ] Detect failures in downstream dependencies
- [ ] Open circuit after threshold failures (stop calling failing service)
- [ ] Half-open circuit periodically to test recovery
- [ ] Close circuit when service recovers

**Timeouts and Retries**:
- [ ] Timeouts on all network calls (no infinite waits)
- [ ] Retry transient failures with exponential backoff
- [ ] Maximum retry attempts to prevent retry storms
- [ ] Idempotency for safe retries

**Graceful Degradation**:
- [ ] Identify critical vs non-critical functionality
- [ ] Degrade non-critical features when dependencies fail (e.g., recommendations, analytics)
- [ ] Maintain core functionality even in degraded mode
- [ ] Communicate degraded state to users

**Bulkhead Isolation**:
- [ ] Isolate thread pools, connection pools, and resources per dependency
- [ ] Prevent cascading failures (one slow dependency doesn't block all requests)
- [ ] Resource limits per tenant in multi-tenant systems

**Health Checks**:
- [ ] Liveness probes (is the service running?)
- [ ] Readiness probes (is the service ready to accept traffic?)
- [ ] Dependency health checks (are downstream services healthy?)
- [ ] Automated remediation (restart unhealthy instances)

**Chaos Engineering** (SHOULD perform):
- [ ] Fault injection testing (simulate failures)
- [ ] Game Days (practice incident response)
- [ ] Chaos experiments in pre-production

**Validation Gates**:
- [ ] Failure modes identified and mitigated
- [ ] Circuit breakers implemented for external dependencies
- [ ] Timeouts and retries configured
- [ ] Graceful degradation designed and tested
- [ ] Health checks implemented
- [ ] Recovery Time Objective (RTO) and Recovery Point Objective (RPO) defined
- [ ] Chaos testing performed (or planned)

---

## II. AI and Machine Learning Principles

### 9. Responsible AI and Ethical AI Governance (UK Government AI Playbook)

**Principle Statement** (NON-NEGOTIABLE for AI systems):
All AI systems MUST comply with UK Government AI Playbook principles, ensure transparency, fairness, accountability, and safety. HIGH-RISK AI systems require additional safeguards including Data Protection Impact Assessment (DPIA), Equality Impact Assessment (EqIA), and algorithmic transparency (ATRS).

**Rationale**:
UK Government AI Playbook mandates responsible AI deployment. Central government MUST publish Algorithmic Transparency Recording Standard (ATRS) for algorithmic tools. AI systems can cause harm through bias, opacity, and errors if not governed properly.

**AI Playbook 10 Principles** (MUST comply):

1. **Understand the users and their needs**
   - [ ] User research with diverse user groups
   - [ ] Understand how AI affects different demographics

2. **Define the outcome you're trying to achieve**
   - [ ] Clear success criteria for AI system
   - [ ] Benefits measurable and validated

3. **Decide whether AI is the right approach**
   - [ ] Non-AI alternatives evaluated
   - [ ] AI provides measurable benefit over rules-based systems

4. **Make sure you have diverse data**
   - [ ] Training data representative of user population
   - [ ] Bias assessment of training data
   - [ ] Data quality validation

5. **Understand the limitations of your AI model**
   - [ ] Model performance metrics defined (accuracy, precision, recall, F1)
   - [ ] Edge cases and failure modes identified
   - [ ] Confidence scores provided with predictions

6. **Make sure your AI system is explainable**
   - [ ] Ability to explain individual predictions (local explanations)
   - [ ] Model interpretability (feature importance, attention mechanisms)
   - [ ] Plain language explanations for non-technical users

7. **Make your AI system auditable and accountable**
   - [ ] Model versioning and lineage tracking
   - [ ] Training data provenance
   - [ ] Decision logs for auditability
   - [ ] Clear ownership and accountability

8. **Make your AI fair and address bias**
   - [ ] Bias testing across protected characteristics (age, gender, ethnicity, disability)
   - [ ] Fairness metrics defined and monitored
   - [ ] Bias mitigation strategies implemented
   - [ ] Regular bias audits

9. **Make your AI system legally compliant**
   - [ ] GDPR/UK GDPR compliance (lawful basis, individual rights)
   - [ ] Equality Act 2010 compliance (no unlawful discrimination)
   - [ ] Human Rights Act 1998 compliance (right to fair trial, privacy)
   - [ ] Sector-specific regulations (e.g., financial services, healthcare)

10. **Make your AI safe, secure, and robust**
    - [ ] Adversarial testing (robustness to adversarial inputs)
    - [ ] Security testing (model poisoning, data poisoning, evasion attacks)
    - [ ] Fallback mechanisms when AI fails
    - [ ] Human override capability

**AI Risk Classification** (determines requirements):

**HIGH-RISK AI** (this project is HIGH-RISK):
- Generative AI with potential for harm
- Large-scale deployment (cross-government)
- Handles sensitive data (OFFICIAL-SENSITIVE)
- Decision-support for policy or legal matters

**MANDATORY for HIGH-RISK AI**:
- [ ] Data Protection Impact Assessment (DPIA)
- [ ] Equality Impact Assessment (EqIA)
- [ ] Human Rights Assessment
- [ ] Bias testing across demographics
- [ ] Human-in-the-loop for high-stakes decisions
- [ ] Explainability for all AI recommendations
- [ ] ATRS publication within 6 months of deployment

**MEDIUM-RISK AI**:
- Narrow AI with limited scope
- Low potential for harm
- Non-sensitive data

**MANDATORY for MEDIUM-RISK AI**:
- [ ] Bias testing
- [ ] Explainability
- [ ] Human oversight

**LOW-RISK AI**:
- Minimal potential for harm
- No personal data
- No decision-making authority

**MANDATORY for LOW-RISK AI**:
- [ ] Basic transparency (users know they're interacting with AI)

**Validation Gates**:
- [ ] AI Playbook assessment completed
- [ ] Risk level determined (HIGH / MEDIUM / LOW)
- [ ] DPIA completed (if HIGH-RISK)
- [ ] EqIA completed (if HIGH-RISK)
- [ ] Human Rights Assessment completed (if HIGH-RISK)
- [ ] Bias testing completed
- [ ] Explainability mechanisms implemented
- [ ] Human oversight model defined
- [ ] ATRS record created (if central government)

---

### 10. Human-in-the-Loop and Human Oversight (AI Playbook Requirement)

**Principle Statement**:
AI systems MUST provide human oversight mechanisms for high-stakes decisions. Users MUST have the ability to review, challenge, and override AI recommendations.

**Rationale**:
AI is fallible. High-stakes decisions (policy, legal, financial, personnel) require human judgment. Users must maintain agency and accountability.

**Human-in-the-Loop Requirements**:

**Oversight Models** (select appropriate model):

1. **Human-in-Command**: Human makes final decision, AI provides recommendations
   - **Use for**: High-stakes decisions (policy, legal, financial)
   - **Example**: AI summarizes policy paper, human makes final policy decision

2. **Human-on-the-Loop**: AI acts autonomously, human monitors and can intervene
   - **Use for**: Medium-stakes decisions with human monitoring
   - **Example**: AI drafts document, human reviews before sending

3. **Human-out-of-the-Loop**: AI acts fully autonomously (only for LOW-RISK)
   - **Use for**: Low-stakes decisions, no significant impact
   - **Example**: AI autocompletes sentence, user can delete

**HIGH-RISK AI requires Human-in-Command or Human-on-the-Loop** (not Human-out-of-the-Loop)

**User Controls** (MUST provide):
- [ ] **Review**: Users can review AI reasoning and data sources
- [ ] **Challenge**: Users can flag AI outputs as incorrect or biased
- [ ] **Override**: Users can override AI recommendations
- [ ] **Feedback**: Users can provide feedback to improve AI
- [ ] **Opt-out**: Users can opt out of AI features (use manual alternative)

**Decision Transparency**:
- [ ] Show confidence scores for AI predictions
- [ ] Provide source attribution (which documents informed answer)
- [ ] Explain reasoning in plain language
- [ ] Show alternative interpretations or options
- [ ] Highlight uncertainty or limitations

**Escalation Procedures**:
- [ ] Mechanism to escalate to human expert
- [ ] Clear escalation criteria (e.g., low confidence, high stakes, user request)
- [ ] Escalation response time defined (e.g., < 24 hours)

**Validation Gates**:
- [ ] Human oversight model defined (Human-in-Command, Human-on-the-Loop, Human-out-of-the-Loop)
- [ ] User controls implemented (review, challenge, override, feedback, opt-out)
- [ ] Decision transparency mechanisms in place
- [ ] Escalation procedures defined and tested

---

### 11. Algorithmic Transparency (ATRS - Mandatory for Central Government)

**Principle Statement**:
All algorithmic decision-making tools in central government departments MUST publish an Algorithmic Transparency Recording Standard (ATRS) record on GOV.UK within 6 months of deployment.

**Rationale**:
UK Government commitment to algorithmic transparency. ATRS enables public scrutiny, accountability, and trust. Mandatory for central government departments (Cabinet Office, HMRC, Home Office, MOJ, etc.).

**ATRS Structure** (MUST complete):

**Tier 1 - Public Summary** (published on GOV.UK):
- [ ] System name and purpose
- [ ] Organization responsible
- [ ] Scope (who is affected, geographic coverage)
- [ ] Owner contact details
- [ ] Data types processed
- [ ] Human oversight model
- [ ] Risk level (HIGH / MEDIUM / LOW)

**Tier 2 - Technical Details** (published on GOV.UK or internal):
- [ ] Algorithm type (e.g., "Large Language Model - GPT-4 / Claude")
- [ ] Training data sources and quality
- [ ] Performance metrics (accuracy, latency, error rate)
- [ ] Bias testing results
- [ ] Explainability mechanisms
- [ ] Fallback procedures
- [ ] Review and update frequency

**Publication Timeline**:
- [ ] Draft ATRS during Discovery/Alpha phase
- [ ] Complete ATRS before Private Beta
- [ ] Publish ATRS within 6 months of Public Beta
- [ ] Update ATRS annually or when material changes occur

**Validation Gates**:
- [ ] ATRS Tier 1 (public summary) completed
- [ ] ATRS Tier 2 (technical details) completed
- [ ] Senior Responsible Owner (SRO) approval obtained
- [ ] Publication on GOV.UK algorithmic transparency page
- [ ] Annual review scheduled

**Exemptions**:
Limited exemptions for:
- National security systems (classified)
- Law enforcement systems (operational sensitivity)
- Commercial confidentiality (vendor IP protection)

All exemptions require justification and approval from departmental Accounting Officer.

---

## III. Data Principles

### 12. Data Sovereignty and UK Data Residency

**Principle Statement**:
All government data MUST be stored and processed in UK data centers. Cross-border data transfers require legal basis (adequacy decisions, standard contractual clauses). Cloud providers MUST NOT be subject to extraterritorial data access laws that conflict with UK sovereignty.

**Rationale**:
Data sovereignty ensures UK legal jurisdiction over government data. Protection from foreign government access (e.g., US CLOUD Act). GDPR/UK GDPR requires safeguards for international transfers.

**UK Data Residency Requirements**:
- [ ] All data centers in UK regions (UK South, UK West, eu-west-2 London)
- [ ] No data replication to non-UK regions (except approved transfers)
- [ ] Cloud provider guarantees UK data residency
- [ ] Cloud provider contractually prohibited from transferring data outside UK without approval

**International Data Transfers**:

**Permitted with Safeguards**:
- [ ] UK-EU transfers (UK-EU adequacy decision in place)
- [ ] Transfers to adequate jurisdictions (EU, Japan, South Korea, etc.)
- [ ] Transfers with Standard Contractual Clauses (SCCs)
- [ ] Transfers under Binding Corporate Rules (BCRs)
- [ ] Transfers with explicit consent (rare for government)

**Prohibited**:
- ❌ Transfers to inadequate jurisdictions without safeguards (e.g., China, Russia)
- ❌ Cloud providers subject to CLOUD Act or similar extraterritorial laws (without contractual protections)

**Cloud Act Concerns**:
- US cloud providers (AWS, Azure, Google) subject to US CLOUD Act (allows US government to compel data access)
- Mitigation: Contractual protections, encryption with UK-held keys, UK-based support

**Validation Gates**:
- [ ] Data centers located in UK regions
- [ ] Cloud provider data residency guarantees in contract
- [ ] International transfer mechanisms documented (adequacy, SCCs, BCRs)
- [ ] No prohibited international transfers
- [ ] Data sovereignty risk assessment completed

---

### 13. Data Classification and Handling (UK Government)

**Principle Statement**:
All data MUST be classified according to UK Government classification scheme (PUBLIC, OFFICIAL, OFFICIAL-SENSITIVE, SECRET, TOP SECRET) with security controls proportionate to classification.

**Rationale**:
UK Government Security Classification Policy mandates data classification. Different classifications require different security controls.

**UK Government Classification Scheme**:

| Classification | Description | Security Controls |
|----------------|-------------|-------------------|
| **PUBLIC** | No restrictions, intended for public disclosure | Basic security hygiene |
| **OFFICIAL** | Routine government business, not for public disclosure | Encryption in transit, access controls, Cyber Essentials |
| **OFFICIAL-SENSITIVE** | Requires heightened protective measures, impact if lost/stolen | Encryption at rest/transit, MFA, audit logging, Cyber Essentials Plus, DPIA |
| **SECRET** | Very sensitive information, serious harm if compromised | Air-gap or assured network, SC clearance, enhanced physical security, CESG crypto |
| **TOP SECRET** | Exceptionally sensitive, catastrophic harm if compromised | Compartmented security, DV clearance, strict need-to-know, air-gapped systems |

**This Project Classification**: OFFICIAL to OFFICIAL-SENSITIVE

**Mandatory Controls for OFFICIAL-SENSITIVE** (this project):
- [ ] Encryption at rest (AES-256 or equivalent)
- [ ] Encryption in transit (TLS 1.2+ minimum, prefer TLS 1.3)
- [ ] Multi-factor authentication (MFA)
- [ ] Role-Based Access Control (RBAC) with least privilege
- [ ] Audit logging (7 years retention)
- [ ] Cyber Essentials Plus certification
- [ ] Data Protection Impact Assessment (DPIA)
- [ ] Personnel security clearance (Baseline Personnel Security Standard minimum)
- [ ] Secure deletion when data no longer needed

**Data Handling Requirements**:
- [ ] Data classification labels on all data stores
- [ ] Access controls enforce classification (OFFICIAL-SENSITIVE not accessible without clearance)
- [ ] Data cannot be downgraded without approval
- [ ] Data aggregation considered (combining OFFICIAL data may create OFFICIAL-SENSITIVE)

**Validation Gates**:
- [ ] All data classified (PUBLIC, OFFICIAL, OFFICIAL-SENSITIVE, SECRET, TOP SECRET)
- [ ] Security controls mapped to classification
- [ ] Access controls enforce classification
- [ ] Personnel security clearances appropriate for classification
- [ ] Data handling procedures documented

---

### 14. Data Quality and Lineage

**Principle Statement**:
Data pipelines MUST maintain data quality standards and provide end-to-end lineage for auditability and troubleshooting.

**Rationale**:
Poor data quality leads to poor decisions. Government decisions must be auditable and defensible.

**Data Quality Dimensions**:

1. **Completeness**: No unexpected nulls in required fields
   - [ ] Required fields enforced at source
   - [ ] Completeness metrics tracked (% of records with all required fields)

2. **Accuracy**: Data reflects reality
   - [ ] Validation rules at data entry (e.g., email format, date ranges)
   - [ ] Cross-system reconciliation (data matches across systems)
   - [ ] User feedback mechanism to report inaccuracies

3. **Consistency**: No conflicting data
   - [ ] Referential integrity enforced (foreign keys)
   - [ ] Data formats standardized (dates, phone numbers, addresses)
   - [ ] Duplicate detection and deduplication

4. **Timeliness**: Data is fresh and up-to-date
   - [ ] Freshness SLAs defined (e.g., data < 24 hours old)
   - [ ] Staleness alerts for critical data
   - [ ] Data refresh frequency documented

5. **Validity**: Data conforms to business rules
   - [ ] Business rule validation (e.g., age > 0, salary > 0)
   - [ ] Allowed value lists (enumerations)
   - [ ] Cross-field validation (e.g., end date > start date)

**Data Lineage**:
- [ ] Source-to-target mapping for all data flows
- [ ] Transformation logic version-controlled
- [ ] Data quality metrics per pipeline stage
- [ ] Impact analysis for schema changes
- [ ] Audit trail (who created, updated, deleted data and when)

**Data Contracts**:
- [ ] Schema specifications (column names, types, constraints)
- [ ] Data quality SLAs (completeness %, accuracy %, freshness)
- [ ] Breaking change notification period (30 days minimum)
- [ ] Versioning for schema changes

**Validation Gates**:
- [ ] Data quality rules defined and automated
- [ ] Data quality metrics monitored (completeness, accuracy, consistency, timeliness, validity)
- [ ] Data lineage captured and queryable
- [ ] Data contracts between producers and consumers
- [ ] Schema evolution strategy documented

---

### 15. Single Source of Truth

**Principle Statement**:
Every data domain MUST have a single authoritative source. Derived copies must be clearly labeled and synchronized.

**Rationale**:
Multiple authoritative sources create inconsistency, reconciliation overhead, and data integrity issues.

**Implications**:
- [ ] Identify the **system of record** for each data domain
- [ ] Derived/cached copies are read-only and clearly labeled
- [ ] Synchronization strategy defined (real-time, batch, event-driven)
- [ ] Avoid bidirectional synchronization (creates split-brain scenarios)

**Master Data Domains** (examples):
- **User identity**: Government Gateway (SSO system of record)
- **Department registry**: Cabinet Office departmental registry
- **Organisation data**: Companies House (for UK companies)
- **Address data**: Ordnance Survey AddressBase
- **Postcode data**: Royal Mail Postcode Address File

**Validation Gates**:
- [ ] System of record identified for each data entity
- [ ] Derived copies documented with sync frequency
- [ ] No bidirectional sync without conflict resolution strategy
- [ ] Master Data Management (MDM) strategy for shared reference data

---

## IV. Integration Principles

### 16. Loose Coupling

**Principle Statement**:
Systems MUST be loosely coupled through published interfaces, avoiding shared databases, file systems, or tight runtime dependencies.

**Rationale**:
Loose coupling enables independent deployment, technology diversity, team autonomy, and system evolution without breaking dependencies.

**Implications**:
- [ ] Communicate through published APIs or asynchronous events
- [ ] No direct database access across system boundaries
- [ ] Each system manages its own data lifecycle
- [ ] Shared libraries kept minimal (favor duplication over coupling)
- [ ] Avoid distributed transactions across systems (use eventual consistency)

**Database Per Service Pattern**:
- Each microservice has its own database
- No shared database between services
- Data sharing via APIs or events, not database queries

**Common Violations to Avoid**:
- ❌ Direct SQL queries across databases
- ❌ Shared mutable state (shared cache, shared file system)
- ❌ Tight runtime coupling (synchronous calls to 10+ services)
- ❌ Shared libraries with business logic (creates coupling)

**Validation Gates**:
- [ ] Systems communicate via APIs or events, not database
- [ ] No shared mutable state
- [ ] Each system has independent data store
- [ ] Deployment of one system doesn't require deployment of another
- [ ] Interface changes versioned with backward compatibility

---

### 17. Asynchronous Communication

**Principle Statement**:
Systems SHOULD use asynchronous communication for non-real-time interactions to improve resilience and decoupling.

**Rationale**:
Asynchronous patterns reduce temporal coupling, improve fault tolerance, and enable better scalability.

**When to Use Async** (SHOULD):
- [ ] Non-real-time business processes (order fulfillment, batch jobs)
- [ ] Event notification and pub/sub patterns
- [ ] Long-running operations (AI model inference, report generation)
- [ ] Integration with unreliable or slow external systems
- [ ] Cross-department data sharing

**When Synchronous is Acceptable** (MAY):
- [ ] Real-time user interactions requiring immediate feedback (search, query)
- [ ] Query operations (read-only, idempotent)
- [ ] Transactions requiring immediate consistency

**Asynchronous Patterns**:
- **Message Queues**: Point-to-point, guaranteed delivery, at-least-once processing
- **Pub/Sub**: Broadcast to multiple subscribers, event-driven
- **Event Streaming**: Log-based, replay capability, event sourcing

**Message Reliability**:
- [ ] At-least-once delivery (messages not lost)
- [ ] Idempotency (safe to process same message multiple times)
- [ ] Dead letter queues for failed messages
- [ ] Message retention for debugging and replay

**Validation Gates**:
- [ ] Async patterns used for non-real-time flows
- [ ] Message durability and delivery guarantees defined
- [ ] Event schemas versioned and published (AsyncAPI specs)
- [ ] Dead letter queues and error handling configured
- [ ] Idempotency for message processing

---

## V. Quality Attributes

### 18. Performance and Efficiency

**Principle Statement**:
All systems MUST meet defined performance targets under expected load with efficient use of computational resources.

**Rationale**:
GDS Service Standard requires services to work fast. Poor performance impacts user satisfaction and accessibility (slow services exclude users on slow connections).

**Performance Targets** (define for each system):

**This Project Performance Targets** (from README):
- [ ] **Response Time**: p95 < 2 seconds
- [ ] **Throughput**: 10,000 concurrent users
- [ ] **Availability**: 99.9% uptime SLA

**General Performance Requirements**:
- [ ] **Latency**: p50, p95, p99 latency targets
- [ ] **Throughput**: Requests per second, transactions per minute
- [ ] **Concurrency**: Simultaneous user/request capacity
- [ ] **Resource Efficiency**: CPU/memory utilization < 70% at peak

**Performance Best Practices**:
- [ ] Performance requirements defined before implementation
- [ ] Load testing performed at 2x expected capacity
- [ ] Performance monitoring continuous (not point-in-time)
- [ ] Optimize hot paths (profile to identify bottlenecks)
- [ ] Caching strategies for expensive operations (database queries, AI inference)
- [ ] Content Delivery Network (CDN) for static assets
- [ ] Database query optimization (indexes, query plans)
- [ ] Connection pooling for databases and external services

**Validation Gates**:
- [ ] Performance requirements defined with measurable targets
- [ ] Load testing performed at expected capacity (and 2x capacity)
- [ ] Performance metrics monitored in production
- [ ] Capacity planning model defined
- [ ] p95 response time meets target (< 2s for this project)

---

### 19. Availability and Reliability

**Principle Statement**:
All systems MUST meet defined availability targets with automated recovery and minimal data loss.

**Rationale**:
GDS Service Standard requires services to work reliably. Government services are essential services - downtime impacts citizens and businesses.

**Availability Targets** (define for each system):

**This Project Availability Target**: 99.9% uptime SLA (< 43.8 min downtime/month)

**High Availability Patterns**:
- [ ] Redundancy across availability zones / regions
- [ ] Automated health checks and failover
- [ ] Active-active or active-passive configurations
- [ ] Load balancing across multiple instances
- [ ] No single points of failure

**Disaster Recovery**:
- [ ] **Recovery Time Objective (RTO)**: Maximum acceptable downtime (e.g., 4 hours)
- [ ] **Recovery Point Objective (RPO)**: Maximum acceptable data loss (e.g., 15 minutes)
- [ ] Backup strategy (frequency, retention, encryption)
- [ ] Backup restoration tested quarterly
- [ ] Disaster recovery plan documented and rehearsed

**Validation Gates**:
- [ ] Availability SLA defined (99.9% for this project)
- [ ] RTO and RPO requirements documented
- [ ] Redundancy strategy implemented (multi-AZ)
- [ ] Automated failover tested
- [ ] Backup and restore procedures validated
- [ ] Disaster recovery plan tested

---

### 20. Maintainability and Evolvability

**Principle Statement**:
All systems MUST be designed for change, with clear separation of concerns, modular architecture, and comprehensive documentation.

**Rationale**:
Software spends most of its lifetime in maintenance. Design decisions should optimize for understandability and modifiability. GDS Service Standard requires systems to be iterable and improvable.

**Modular Architecture**:
- [ ] Clear module boundaries with defined responsibilities
- [ ] Separation of concerns (business logic, data access, presentation, integration)
- [ ] High cohesion within modules, low coupling between modules
- [ ] Domain-Driven Design (DDD) for complex domains

**Documentation Requirements**:
- [ ] **Architecture documentation**: C4 diagrams (System Context, Container, Component)
- [ ] **Architecture Decision Records (ADRs)**: Document key architectural choices with context, decision, consequences
- [ ] **API documentation**: OpenAPI specs with examples
- [ ] **Runbooks**: Operational procedures for common tasks and incidents
- [ ] **README**: Getting started guide for developers

**Code Quality**:
- [ ] Code is self-documenting (meaningful names, clear structure)
- [ ] Automated tests enable confident refactoring
- [ ] Code reviews required before merge
- [ ] Static analysis and linting in CI/CD

**Validation Gates**:
- [ ] Architecture documentation exists and is current
- [ ] Architecture Decision Records (ADRs) document key choices
- [ ] Module boundaries clear with defined responsibilities
- [ ] Automated test coverage enables safe refactoring (>70% unit test coverage)
- [ ] API documentation published

---

## VI. Development Practices

### 21. Infrastructure as Code

**Principle Statement**:
All infrastructure MUST be defined as code, version-controlled, and deployed through automated pipelines.

**Rationale**:
Manual infrastructure changes create drift, inconsistency, and undocumented state. Infrastructure as Code (IaC) enables repeatability, auditability, and disaster recovery. GDS Service Standard requires automated deployment.

**Infrastructure as Code Requirements**:
- [ ] All infrastructure defined in declarative code (not imperative scripts)
- [ ] Infrastructure code version-controlled (Git)
- [ ] Infrastructure changes go through code review
- [ ] Environments are reproducible from code
- [ ] No manual changes to production infrastructure (immutable infrastructure)
- [ ] Infrastructure versioned alongside application code

**IaC Tools** (technology-agnostic, select appropriate tool):
- Declarative IaC (preferred): Terraform, CloudFormation, Azure Resource Manager
- Configuration management: Ansible, Chef, Puppet
- Container orchestration: Kubernetes manifests, Helm charts

**Validation Gates**:
- [ ] Infrastructure defined as code (100% coverage)
- [ ] Infrastructure code version-controlled
- [ ] Automated deployment pipeline for infrastructure
- [ ] No manual infrastructure changes in production
- [ ] Infrastructure code reviewed before merge

---

### 22. Automated Testing

**Principle Statement**:
All code changes MUST be validated through automated testing before deployment to production.

**Rationale**:
Manual testing is slow, error-prone, and inconsistent. Automated tests enable rapid iteration and confident refactoring. GDS Service Standard requires automated testing.

**Test Pyramid**:

1. **Unit Tests** (70-80% of tests):
   - [ ] Fast (< 1 second per test)
   - [ ] Isolated (no dependencies on database, network, file system)
   - [ ] High coverage (> 70% code coverage)
   - [ ] Test individual functions/methods

2. **Integration Tests** (15-20% of tests):
   - [ ] Test component interactions (API + database, service + message queue)
   - [ ] Use test doubles for external dependencies (mocks, stubs)
   - [ ] Slower than unit tests (< 1 minute per test)

3. **End-to-End Tests** (5-10% of tests):
   - [ ] Test critical user journeys (complete workflows)
   - [ ] Run against production-like environment
   - [ ] Slowest tests (minutes per test)
   - [ ] Minimal number (only critical paths)

**Required Test Types**:
- [ ] **Functional tests**: Does it work? (unit, integration, E2E)
- [ ] **Performance tests**: Is it fast enough? (load testing, stress testing)
- [ ] **Security tests**: Is it secure? (SAST, DAST, dependency scanning)
- [ ] **Accessibility tests**: Is it accessible? (axe, Pa11y, WAVE)
- [ ] **Resilience tests**: Does it handle failures? (chaos engineering)

**Validation Gates**:
- [ ] Automated tests exist and pass before merge
- [ ] Test coverage meets thresholds (> 70% unit tests)
- [ ] Critical paths have end-to-end tests
- [ ] Performance tests run regularly (weekly)
- [ ] Security tests in CI/CD pipeline (SAST, dependency scanning)
- [ ] Accessibility tests in CI/CD pipeline

---

### 23. Continuous Integration and Deployment (CI/CD)

**Principle Statement**:
All code changes MUST go through automated build, test, and deployment pipelines with quality gates at each stage.

**Rationale**:
Manual deployments are error-prone and slow. Automated CI/CD enables rapid iteration and reduces risk. GDS Service Standard requires automated deployment.

**CI/CD Pipeline Stages** (MUST implement):

1. **Source Control**: All changes committed to version control (Git)
2. **Build**: Automated compilation and packaging
3. **Test**: Automated test execution (unit, integration, E2E)
4. **Security Scan**: Dependency and code vulnerability scanning (SAST, DAST, SCA)
5. **Accessibility Scan**: Automated accessibility testing
6. **Deploy to Dev/Test**: Automated deployment to lower environments
7. **Deploy to Production**: Automated deployment with approval gate

**Quality Gates** (pipeline fails if not met):
- [ ] All tests must pass (unit, integration, E2E)
- [ ] No critical or high security vulnerabilities (SAST, dependency scan)
- [ ] No accessibility violations (WCAG 2.2 AA)
- [ ] Code review approval required (at least 1 reviewer)
- [ ] Production deployment requires change approval (CAB)

**Deployment Strategies**:
- [ ] **Blue/Green**: Deploy to new environment, switch traffic (zero downtime)
- [ ] **Canary**: Deploy to small % of traffic, gradually increase (detect issues early)
- [ ] **Rolling**: Deploy incrementally across instances (gradual rollout)
- [ ] Rollback capability tested (< 15 minutes to rollback)

**Validation Gates**:
- [ ] Automated CI/CD pipeline exists
- [ ] Pipeline includes security scanning (SAST, dependency scan)
- [ ] Pipeline includes accessibility scanning
- [ ] Deployment is automated and repeatable
- [ ] Zero-downtime deployment capability (blue/green or canary)
- [ ] Rollback capability tested (< 15 min)

---

## VII. Multi-Tenant Architecture Principles (Specific to This Project)

### 24. Tenant Isolation and Data Segregation

**Principle Statement**:
Multi-tenant systems MUST ensure complete data isolation between tenants with defense-in-depth controls to prevent cross-tenant data leakage. Zero tolerance for cross-tenant data breaches.

**Rationale**:
This project serves multiple government departments with sensitive data. Cross-tenant data leakage would be catastrophic (breach of OFFICIAL-SENSITIVE data across departments).

**Tenant Isolation Models**:

**Recommended for This Project: Hybrid Isolation** (Balance security and cost)

1. **Physical Isolation** (Siloed):
   - Separate database per tenant, separate infrastructure
   - **Pros**: Maximum security, complete isolation
   - **Cons**: High cost, operational complexity
   - **Use for**: SECRET data or extremely high-risk tenants

2. **Logical Isolation** (Pool):
   - Shared infrastructure, row-level security (RLS) in database
   - **Pros**: Cost-effective, scalable
   - **Cons**: Risk of misconfiguration, shared blast radius
   - **Use for**: OFFICIAL data with strong controls

3. **Hybrid Isolation** (Recommended):
   - Shared application tier, separate database schemas per tenant
   - **Pros**: Balance security and cost, schema-level isolation
   - **Cons**: More complex than fully pooled
   - **Use for**: OFFICIAL-SENSITIVE data (this project)

**Mandatory Isolation Controls** (Defense-in-Depth):

**Database Layer**:
- [ ] Row-Level Security (RLS) enforced (PostgreSQL RLS, database views)
- [ ] Tenant ID in every row (foreign key to tenant table)
- [ ] Database queries MUST include tenant ID filter (enforced by ORM/framework)
- [ ] Separate database schemas per tenant (preferred for OFFICIAL-SENSITIVE)
- [ ] Database connection pooling per tenant (prevent connection reuse across tenants)

**Application Layer**:
- [ ] Tenant context extracted from JWT token (not user-supplied)
- [ ] Tenant ID validated on every request
- [ ] Authorization checks enforce tenant boundaries (cannot access other tenant's data)
- [ ] Middleware/interceptor enforces tenant isolation (fail-safe)
- [ ] API responses filtered by tenant ID

**API Layer**:
- [ ] Tenant ID in JWT token (signed, not tamperable)
- [ ] API gateway enforces tenant routing
- [ ] Rate limiting per tenant (prevent noisy neighbor)
- [ ] Tenant-specific API keys or tokens

**Storage Layer**:
- [ ] Object storage uses tenant-prefixed keys (`tenant-123/document.pdf`)
- [ ] Bucket policies enforce tenant isolation (deny cross-tenant access)
- [ ] Encryption keys per tenant (tenant-specific KMS keys)

**Testing for Tenant Isolation** (MANDATORY):
- [ ] Automated tests for cross-tenant access attempts (must fail)
- [ ] Penetration testing focused on tenant isolation
- [ ] Chaos testing (simulate misconfiguration, ensure fail-safe)
- [ ] Security audit of tenant isolation controls

**Validation Gates**:
- [ ] Tenant isolation model documented (Physical / Logical / Hybrid)
- [ ] Row-Level Security (RLS) enforced in database
- [ ] Tenant ID in JWT token (signed, validated on every request)
- [ ] Authorization checks enforce tenant boundaries
- [ ] Automated tests for cross-tenant access (must fail)
- [ ] Penetration testing passed (no cross-tenant leaks)

**Exception**:
NONE. Tenant isolation is NON-NEGOTIABLE for this project. Any cross-tenant data leak is a critical security incident.

---

## VIII. Exception Process

### Requesting Architecture Exceptions

Principles are mandatory unless a documented exception is approved by the Enterprise Architecture Review Board.

**Valid Exception Reasons**:
- [ ] Technical constraints that prevent compliance (explain why)
- [ ] Regulatory or legal requirements (cite specific regulation)
- [ ] Transitional state during migration (time-boxed, remediation plan required)
- [ ] Pilot/proof-of-concept with defined end date (not for production)

**Exception Request Requirements**:
- [ ] Justification with business/technical rationale
- [ ] Alternative approach and compensating controls
- [ ] Risk assessment and mitigation plan
- [ ] Expiration date (exceptions are time-bound, max 12 months)
- [ ] Remediation plan to achieve compliance

**Approval Process**:
1. Submit exception request to Enterprise Architecture team (arc-exceptions@cabinetoffice.gov.uk)
2. Review by Architecture Review Board (meets bi-weekly)
3. CTO/CIO approval for exceptions to CRITICAL principles (Security, Privacy, Accessibility)
4. Document exception in project architecture documentation (ADR)
5. Quarterly review of exceptions (ARB reviews all active exceptions)

**Exception Tracking**:
- [ ] Exception register maintained (all active exceptions)
- [ ] Expiration dates tracked (alert 30 days before expiration)
- [ ] Remediation progress monitored
- [ ] Expired exceptions automatically revoked (must reapply or remediate)

---

## IX. Governance and Compliance

### Architecture Review Gates

All projects must pass architecture reviews at key GDS Service Standard assessment points:

**Discovery Phase**:
- [ ] Architecture principles understood
- [ ] High-level approach aligns with principles
- [ ] No obvious principle violations
- [ ] Technology options analysis considers principles

**Alpha Phase**:
- [ ] Detailed architecture documented (C4 diagrams)
- [ ] Compliance with each principle validated
- [ ] Exceptions requested and approved
- [ ] Security and privacy principles validated (threat model, DPIA)
- [ ] Prototype demonstrates key architectural patterns

**Private Beta Phase**:
- [ ] Implementation matches approved architecture
- [ ] All validation gates passed
- [ ] Operational readiness verified (monitoring, runbooks, incident response)
- [ ] Security testing completed (pen test, SAST, DAST)
- [ ] Accessibility testing completed (WCAG 2.2 AA)
- [ ] Performance testing completed (meets SLOs)

**Public Beta Phase**:
- [ ] GDS Service Assessment passed (14 points)
- [ ] TCoP assessment completed (13 points)
- [ ] AI Playbook assessment completed (if AI system)
- [ ] ATRS published (if algorithmic tool)
- [ ] Cyber Essentials Plus certification obtained
- [ ] Production monitoring and alerting operational

**Live Phase**:
- [ ] All validation gates passed
- [ ] No outstanding critical exceptions
- [ ] Operational readiness confirmed
- [ ] Change approval obtained (if required)

### Enforcement

- Architecture reviews are **MANDATORY** for all projects
- Principle violations must be remediated before production deployment
- Approved exceptions are time-bound (max 12 months) and reviewed quarterly
- Retrospective compliance reviews for live systems (annual)
- Non-compliance escalated to CTO/CIO

---

## X. Appendix

### Principle Summary Checklist

| Principle | Category | Criticality | UK Gov Requirement | Validation |
|-----------|----------|-------------|-------------------|------------|
| Cloud-First | Strategic | HIGH | TCoP Point 5 | UK data centers, managed services |
| API-First and Interoperability | Strategic | HIGH | TCoP Point 3, 9 | OpenAPI specs, open standards |
| Reuse Before Buy | Strategic | HIGH | TCoP Point 4, 8 | GOV.UK shared services used |
| Security by Design | Strategic | CRITICAL | TCoP Point 6, NCSC | Threat model, Cyber Essentials Plus, pen test |
| Privacy by Design | Strategic | CRITICAL | TCoP Point 7, GDPR | DPIA, individual rights, ICO registration |
| Accessibility | Strategic | CRITICAL | WCAG 2.2 AA, GDS Standard | WCAG 2.2 AA, GDS Design System |
| Observability | Strategic | HIGH | GDS Standard | Logs, metrics, traces, SLOs |
| Resilience | Strategic | CRITICAL | GDS Standard | Chaos testing, RTO/RPO |
| Responsible AI | AI/ML | CRITICAL | AI Playbook | DPIA, EqIA, bias testing |
| Human-in-the-Loop | AI/ML | CRITICAL | AI Playbook | Human oversight, override capability |
| Algorithmic Transparency | AI/ML | CRITICAL | ATRS (mandatory) | ATRS published on GOV.UK |
| UK Data Residency | Data | CRITICAL | Data sovereignty | UK data centers only |
| Data Classification | Data | CRITICAL | Gov Security Policy | OFFICIAL-SENSITIVE controls |
| Data Quality | Data | MEDIUM | Good practice | Quality metrics monitored |
| Single Source of Truth | Data | HIGH | Good practice | System of record identified |
| Loose Coupling | Integration | HIGH | Good practice | No shared databases |
| Asynchronous Communication | Integration | MEDIUM | Good practice | Async for non-real-time |
| Performance | Quality | HIGH | GDS Standard | p95 < 2s |
| Availability | Quality | CRITICAL | GDS Standard | 99.9% uptime |
| Maintainability | Quality | MEDIUM | GDS Standard | ADRs, documentation |
| Infrastructure as Code | DevOps | HIGH | Good practice | 100% IaC |
| Automated Testing | DevOps | HIGH | GDS Standard | > 70% coverage |
| CI/CD | DevOps | HIGH | GDS Standard | Automated pipeline |
| Tenant Isolation | Multi-Tenant | CRITICAL | This project | RLS, pen test, zero leaks |

---

### UK Government Compliance Mapping

| Principle | TCoP | GDS Standard | NCSC | AI Playbook | GDPR |
|-----------|------|--------------|------|-------------|------|
| Cloud-First | Point 5 | - | - | - | - |
| API-First | Point 3, 9 | Point 13 | - | - | - |
| Reuse Before Buy | Point 4, 8 | Point 13 | - | - | - |
| Security by Design | Point 6 | Point 9 | Secure by Design | Principle 10 | Article 32 |
| Privacy by Design | Point 7 | Point 9 | - | Principle 9 | Article 25 |
| Accessibility | Point 2 | Point 5 | - | - | - |
| Observability | - | Point 10 | - | - | - |
| Resilience | - | Point 10 | Secure by Design | - | - |
| Responsible AI | - | - | - | 10 Principles | - |
| Human-in-the-Loop | - | - | - | Principle 7 | Article 22 |
| Algorithmic Transparency | - | - | - | ATRS | - |
| Data Residency | - | - | - | - | Article 44-49 |

---

**Document Version History**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-11-02 | ArcKit AI | Initial creation with UK Government-specific principles |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to latest template format (0.11.2) |

---

**Generated by**: ArcKit `/arckit.principles` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Cabinet Office GenAI Platform (Project 001)
**AI Model**: claude-opus-4-5-20251101
