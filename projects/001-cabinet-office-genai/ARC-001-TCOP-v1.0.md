# Technology Code of Practice (TCoP) Review: Cabinet Office GenAI Platform

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.tcop`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-TCOP-v1.1 |
| **Document Type** | Technology Code of Practice Assessment |
| **Project** | Cabinet Office GenAI Platform (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-02 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Cabinet Office Chief Technology Officer |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Project Team, Architecture Team, GDS Assessment Team |
| **Assessment Phase** | Discovery |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-02 | ArcKit AI | Initial TCoP assessment from `/arckit.tcop` command | [PENDING] | [PENDING] |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 format | [PENDING] | [PENDING] |

---

## Executive Summary

### Assessment Overview

This document provides a comprehensive assessment of the **Cabinet Office GenAI Platform** against all 13 points of the UK Government Technology Code of Practice (TCoP). The assessment is based on project requirements, architecture principles, stakeholder drivers, product backlog, and risk register.

**Project Summary**:
- **Purpose**: Multi-tenant generative AI platform for UK Government departments
- **Scope**: 20+ departments, 5,000+ users at Live, OFFICIAL-SENSITIVE data classification
- **Timeline**: 13-month delivery (Discovery → Alpha → Private Beta → Public Beta → Live)
- **Budget**: £18.8M over 5 years (£12.8M development + £6M operational)
- **Business Case**: £60M cumulative cost savings (80% reduction vs individual AI tool subscriptions)

**Assessment Phase**: **Discovery** - This assessment represents baseline TCoP compliance planning. Full compliance validation will occur at GDS Service Assessment gates (Alpha - Month 5, Beta - Month 11, Live - Month 13).

### Overall TCoP Compliance Score

**COMPLIANCE STATUS**: ✅ **11/13 COMPLIANT** (85%)

| TCoP Point | Compliance Status | Phase Gate | Critical Issues |
|------------|-------------------|------------|-----------------|
| **1. Define user needs** | ✅ Compliant | Discovery | 0 issues |
| **2. Make things accessible and inclusive** | ✅ Compliant | Alpha | 1 Medium (Welsh language deferred) |
| **3. Be open and use open source** | ✅ Compliant | Alpha | 0 issues |
| **4. Make use of open standards** | ✅ Compliant | Alpha | 0 issues |
| **5. Use cloud first** | ✅ Compliant | Discovery | 0 issues |
| **6. Make things secure** | ✅ Compliant | Private Beta | 2 High risks (cross-tenant leak, NCSC assurance) |
| **7. Make privacy integral** | ✅ Compliant | Private Beta | 1 High risk (ICO DPIA approval) |
| **8. Share, reuse and collaborate** | ✅ Compliant | Discovery | 0 issues |
| **9. Integrate and adapt technology** | ✅ Compliant | Alpha | 1 Medium (API versioning gap) |
| **10. Make better use of data** | ✅ Compliant | Alpha | 1 Medium (test coverage metrics undefined) |
| **11. Define your purchasing strategy** | ⚠️ Partially Compliant | Discovery | 1 High (vendor evaluation incomplete) |
| **12. Make your technology sustainable** | ⚠️ Partially Compliant | N/A | 1 High (sustainability requirements missing) |
| **13. Meet the Service Standard** | ✅ Compliant | Live | 0 issues (GDS assessment planned) |

### Critical Findings

**HIGH PRIORITY (2 findings)**:

1. **Point 11 - Purchasing Strategy**: Cloud provider and AI foundation model vendor selection incomplete (Sprint 1-3 critical path). UK data residency contracts must be signed by Week 2 to avoid timeline delay.
   - **Risk**: R-006 (Vendor UK Data Residency Failure), R-010 (Cloud/AI Cost Overruns)
   - **Mitigation**: Parallel AWS/Azure evaluation Week 1, contracts pre-negotiated with legal team
   - **Owner**: Cabinet Office CTO / Procurement Lead
   - **Due Date**: 2025-11-15 (Sprint 1)

2. **Point 12 - Sustainability**: No explicit sustainability requirements defined (energy efficiency, carbon footprint, circular economy principles). TCoP Point 12 compliance gap.
   - **Risk**: New risk identified - TCoP non-compliance at GDS Service Assessment
   - **Mitigation**: Add sustainability requirements to NFRs, measure cloud carbon footprint, optimize AI model inference efficiency
   - **Owner**: Cabinet Office CTO / Enterprise Architect
   - **Due Date**: 2026-01-31 (Alpha phase)

**MEDIUM PRIORITY (3 findings)**:

3. **Point 2 - Welsh Language**: Welsh Language Act 1993 compliance deferred to Public Beta (Month 10+) due to AI model limitations. Legal compliance risk.
   - **Risk**: R-018 (Welsh Language Support Delay), Finding H-001 from analysis-report.md
   - **Mitigation**: English-only MVP acceptable for 80% use cases, Welsh language support in Public Beta
   - **Owner**: Product Owner / Welsh Language Board
   - **Status**: TOLERATED (legal risk accepted by stakeholders)

4. **Point 9 - API Versioning**: API versioning strategy mentioned in principles but not detailed in requirements.
   - **Risk**: Finding L-001 from analysis-report.md
   - **Mitigation**: Document API versioning policy (semantic versioning, 12-month backward compatibility, 6-month deprecation notice)
   - **Owner**: Tech Lead / API Architect
   - **Due Date**: 2026-01-15 (Alpha)

5. **Point 10 - Test Coverage Metrics**: Test coverage thresholds undefined in NFRs (>70% coverage stated in backlog DoD but not in requirements).
   - **Risk**: Finding M-001 from analysis-report.md
   - **Mitigation**: Add NFR for automated test coverage (unit >70%, integration >60%, E2E critical paths 100%)
   - **Owner**: Tech Lead / QA Lead
   - **Due Date**: 2025-12-31 (Discovery)

### Recommendation

**PROCEED TO ALPHA PHASE** with the following conditions:

1. ✅ **Discovery Phase (Months 1-2)**: Address Point 11 (vendor selection) and Point 12 (sustainability requirements) BEFORE Sprint 1 development
2. ✅ **Alpha Phase (Months 3-5)**: Validate security controls (Point 6), privacy controls (Point 7), and GDS Service Standard compliance (Point 13)
3. ✅ **Private Beta Gate (Month 6)**: BLOCKED until NCSC Secure by Design assurance (Point 6) and ICO DPIA approval (Point 7) obtained
4. ✅ **Public Beta Phase (Months 7-11)**: Address Welsh language support (Point 2) and complete vendor exit strategy (Point 11)
5. ✅ **Live Gate (Month 13)**: Full TCoP compliance validated at GDS Live Assessment (13/13 points compliant)

**Overall Verdict**: The Cabinet Office GenAI Platform demonstrates **STRONG TCoP ALIGNMENT** (11/13 compliant in Discovery phase). The 2 partially compliant points (11, 12) are addressable within project timeline. No TCoP violations or non-negotiable blockers identified.

---

## Detailed TCoP Assessment

### Point 1: Define User Needs

**TCoP Requirement**: Understand your users and their needs. Build and deliver services that meet those needs.

**Compliance Status**: ✅ **COMPLIANT**

#### Evidence of Compliance

**User Research & Discovery** (stakeholder-drivers.md):
- **13 stakeholder groups identified** with detailed drivers, concerns, and goals
- **Primary users**: Policy Advisors (3,000+ across departments), Civil Servants (2,000+), Senior Civil Service (200+)
- **Pilot departments**: Home Office (immigration use cases), HMRC (tax guidance), DHSC (health policy analysis)
- **User research planned**: 20+ user interviews during Discovery (Months 1-2), co-design sessions with pilot departments
- **User personas documented**: Policy Advisor (primary), Power User (data analysts), Admin (governance leads), Governance Lead (AI oversight)

**User Needs from Stakeholder Drivers** (stakeholder-drivers.md):
1. **SD-9 (Policy Advisors)**: "Need AI to summarize 50MB documents in <30 seconds to meet ministerial briefing deadlines (48-hour turnaround)"
2. **SD-10 (Civil Servants)**: "Need AI-assisted drafting to reduce time spent on routine correspondence (20% time savings target)"
3. **SD-8 (Pilot Departments)**: "Need semantic search across 100,000+ departmental documents (Home Office immigration case law, HMRC tax guidance)"

**User-Centered Requirements** (requirements.md):
- **BR-002**: Achieve 80% cross-government adoption with user satisfaction >4.2/5
- **FR-010**: User feedback loop (thumbs up/down) to improve AI recommendations
- **NFR-A-002**: WCAG 2.2 Level AA accessibility for users with disabilities
- **FR-002**: Document summarization <30 seconds (95th percentile) to meet user workflow needs

**Usability Testing Planned** (backlog.md):
- **Sprint 2-3**: User onboarding & tutorial testing (STORY-004, target 80% completion rate)
- **Alpha Phase (Month 5)**: Usability testing with 50+ users, target satisfaction 4.5/5
- **Private Beta (Month 6)**: Limited rollout to 200 pilot users with quarterly satisfaction surveys

**User Research Methods** (architecture-principles.md - Principle 9, AI Playbook):
- User interviews with diverse user groups (Policy Advisors, Civil Servants, Senior Civil Service)
- Co-design workshops with pilot departments (validate use cases, test prototypes)
- Quarterly user satisfaction tracking (5-point scale, Net Promoter Score NPS >60)
- Feature adoption analytics (which features used, which ignored)

#### Assessment

**STRENGTHS**:
- ✅ Extensive user research planned (20+ interviews, co-design, usability testing)
- ✅ User needs clearly documented (stakeholder drivers, user personas, use cases)
- ✅ User satisfaction metrics defined (>4.2/5 target, NPS >60)
- ✅ User feedback loop integrated into product (FR-010, thumbs up/down mechanism)
- ✅ Pilot departments provide real-world validation (Home Office, HMRC, DHSC)

**GAPS**: None identified.

**RISKS**:
- R-002 (Low User Adoption) - Risk that poor UX or change resistance causes <50% adoption, undermining business case
- **Mitigation**: User research, co-design, change management team (2 FTE embedded in pilot departments)

**GDS Service Standard Alignment**: Point 1 (Understand users and their needs), Point 4 (Make the service simple to use)

---

### Point 2: Make Things Accessible and Inclusive

**TCoP Requirement**: Make sure your technology, infrastructure and systems are accessible and inclusive for users.

**Compliance Status**: ✅ **COMPLIANT** (with 1 Medium finding)

#### Evidence of Compliance

**WCAG 2.2 Level AA Compliance** (architecture-principles.md - Principle 6):
- **Mandatory requirement**: NFR-A-002 - Achieve WCAG 2.2 Level AA accessibility compliance
- **Legal requirement**: UK Public Sector Bodies Accessibility Regulations 2018
- **Testing**: Automated accessibility testing in CI/CD pipeline (axe, Pa11y, WAVE), manual testing with assistive technologies
- **User research**: User research with disabled users during Alpha phase
- **Accessibility statement**: Published at `/accessibility-statement` before Public Beta

**GDS Design System Usage** (architecture-principles.md - Principle 6):
- **Mandatory**: Use GOV.UK Design System components (buttons, forms, navigation, notifications)
- **Typography**: GDS typography, spacing, and layout (not custom CSS frameworks)
- **Accessibility patterns**: Skip links, error summaries, focus styles, keyboard navigation

**Perceivable, Operable, Understandable, Robust** (POUR principles):
- **Perceivable**: Text alternatives for non-text content, sufficient color contrast (4.5:1 for text, 3:1 for UI components)
- **Operable**: All functionality available via keyboard, no keyboard traps, no seizure-inducing content
- **Understandable**: Plain English content, predictable navigation, clear error messages
- **Robust**: Compatible with assistive technologies (screen readers, voice control, magnifiers), valid HTML/CSS

**Assisted Digital Support** (architecture-principles.md - Principle 6):
- Alternative channels for users unable to use digital service (phone, post, in-person)
- Support for users with low digital literacy (5-minute onboarding tutorial, contextual help)

**Accessibility Validation Gates** (backlog.md - Definition of Done):
- [ ] WCAG 2.2 Level AA compliance validated (automated + manual testing)
- [ ] GDS Design System components used (no custom UI without justification)
- [ ] Accessibility audit conducted before Public Beta (external audit firm)
- [ ] User research with disabled users (Alpha phase)

#### Findings

**MEDIUM PRIORITY - Finding M-2-01: Welsh Language Support Deferred**:
- **Issue**: Welsh Language Act 1993 requires Welsh language support for Wales-specific services. Platform defers Welsh language support to Public Beta (Month 10+) due to AI foundation model limitations (Azure OpenAI, AWS Bedrock, Anthropic have limited Welsh language support).
- **Impact**: Legal compliance risk for Welsh Government departments, potential challenge from Welsh Language Commissioner
- **Traceability**: R-018 (Welsh Language Support Delay), Finding H-001 from analysis-report.md
- **Mitigation**:
  - English-only MVP acceptable for 80% of use cases (Cabinet Office, Home Office, HMRC, DHSC primarily English-language)
  - Welsh language support added in Public Beta (Month 10+) using bilingual AI models or human translation fallback
  - Welsh Language Board stakeholder engagement (confirm acceptability of phased approach)
- **Risk Level**: MEDIUM (tolerated risk, accepted by stakeholders)
- **Owner**: Product Owner / Welsh Language Board
- **Due Date**: 2026-04-30 (Public Beta)

#### Assessment

**STRENGTHS**:
- ✅ WCAG 2.2 Level AA compliance mandatory (legal requirement embedded in NFRs)
- ✅ GDS Design System usage mandatory (proven accessible patterns)
- ✅ Accessibility testing automated in CI/CD (continuous validation)
- ✅ User research with disabled users planned (Alpha phase)
- ✅ Assisted digital support for low digital literacy users (5-minute tutorial, contextual help)

**GAPS**:
- ⚠️ Welsh language support deferred to Public Beta (legal compliance risk, but acceptable mitigation)

**RISKS**:
- Finding M-2-01 (Welsh language delay) - Acceptable risk, tolerated by stakeholders

**GDS Service Standard Alignment**: Point 5 (Make sure everyone can use the service)

---

### Point 3: Be Open and Use Open Source

**TCoP Requirement**: Publish your code and use open source to improve transparency, flexibility and accountability.

**Compliance Status**: ✅ **COMPLIANT**

#### Evidence of Compliance

**Open Source First Principle** (architecture-principles.md - Principle 3):
- **Reuse hierarchy**: 1) GOV.UK shared services, 2) Open-source components, 3) Commercial off-the-shelf (COTS), 4) Custom build (last resort)
- **Open source evaluation criteria**: Active maintenance, license compatibility (Apache 2.0, MIT, BSD preferred), community health (contributors, release frequency, issue response)
- **Contribution back**: Contribute improvements back to open-source projects where beneficial to government

**Open Source Components Planned**:
- **PostgreSQL** (database): Open-source relational database with Row-Level Security (RLS) for multi-tenant isolation
- **Kubernetes** (container orchestration): Open-source platform for cloud-native deployment (vendor portability)
- **Terraform** (Infrastructure as Code): Open-source IaC tool (multi-cloud support, avoid vendor lock-in)
- **OpenAPI 3.0+** (API specifications): Open standard for REST API documentation
- **OAuth 2.0 / OpenID Connect** (authentication): Open standard for SSO and identity federation
- **Prometheus / Grafana** (monitoring): Open-source observability stack

**Code Publication Commitment**:
- **Public code repositories**: Platform code published on GitHub (Cabinet Office organization) where possible
- **Exemptions**: Security-sensitive code (authentication, encryption, multi-tenant isolation logic) may be kept private to avoid exposing vulnerabilities
- **Documentation**: README, architecture diagrams, API documentation published publicly
- **Contribution model**: Open to contributions from other government departments (shared platform approach)

**Open Standards Compliance** (see Point 4 below):
- HTTP REST APIs with OpenAPI 3.0+ specifications
- JSON data formats (not proprietary formats)
- OAuth 2.0 / OIDC authentication (not vendor-specific)

#### Assessment

**STRENGTHS**:
- ✅ Open source first principle embedded in architecture principles (Principle 3)
- ✅ Open-source components preferred (PostgreSQL, Kubernetes, Terraform, Prometheus, Grafana)
- ✅ Code publication commitment (GitHub public repositories where security permits)
- ✅ Contribution model (open to inter-departmental collaboration)

**GAPS**: None identified.

**RISKS**:
- R-012 (Vendor Lock-In) - Mitigated through open-source preference and abstraction layers
- Security code may remain private (acceptable exemption under TCoP guidance)

**GDS Service Standard Alignment**: Point 12 (Make new source code open)

---

### Point 4: Make Use of Open Standards

**TCoP Requirement**: Use open standards and common platforms to ensure interoperability and avoid vendor lock-in.

**Compliance Status**: ✅ **COMPLIANT**

#### Evidence of Compliance

**API-First and Interoperability Principle** (architecture-principles.md - Principle 2):
- **Mandatory**: All systems expose functionality through well-defined, versioned APIs using open standards
- **HTTP REST APIs**: OpenAPI 3.0+ specifications (not proprietary API formats)
- **GraphQL APIs**: Published schemas (for complex query requirements)
- **Event-driven systems**: AsyncAPI specifications (for asynchronous messaging)
- **Authentication**: OAuth 2.0, OpenID Connect (OIDC), or SAML 2.0 (not vendor-specific authentication)
- **Data formats**: JSON, XML, CSV (not proprietary binary formats)

**Open Standards by Category**:

**API Specifications**:
- **OpenAPI 3.0+**: REST API documentation standard (mandatory for all HTTP APIs)
- **AsyncAPI**: Event-driven API documentation (for pub/sub, message queues)
- **GraphQL Schema**: Type system for complex queries

**Authentication & Authorization**:
- **OAuth 2.0**: Industry-standard authorization framework
- **OpenID Connect (OIDC)**: Identity layer on top of OAuth 2.0 (used for Government SSO via Azure AD)
- **SAML 2.0**: Alternative SSO standard (interoperability with legacy systems)

**Data Formats**:
- **JSON**: Lightweight data interchange format (primary API response format)
- **XML**: Structured data format (legacy system compatibility)
- **CSV**: Tabular data export format (user data portability, GDPR compliance)

**Communication Protocols**:
- **HTTP/HTTPS**: Standard web protocol (TLS 1.3 encryption)
- **WebSocket**: Real-time bidirectional communication (for chat-like AI interactions)

**No Proprietary Formats**:
- ❌ No vendor-specific APIs (AWS-only, Azure-only) without abstraction layer
- ❌ No proprietary data formats (vendor-specific binary formats)
- ❌ No direct database coupling across systems (API-first, database per service pattern)

**Interoperability with Existing Systems** (requirements.md):
- **INT-001**: Microsoft 365 integration (Microsoft Graph API - REST with OAuth 2.0)
- **INT-002**: Google Workspace integration (Google Drive API - REST with OAuth 2.0)
- **INT-003**: Government SSO (Azure AD - OIDC standard)
- **FR-009**: Government Gateway integration (SAML 2.0 or OIDC)

#### Assessment

**STRENGTHS**:
- ✅ Open standards mandatory (architecture principle, non-negotiable)
- ✅ OpenAPI 3.0+ specifications for all REST APIs
- ✅ OAuth 2.0 / OIDC for authentication (government SSO interoperability)
- ✅ JSON/XML/CSV data formats (no proprietary formats)
- ✅ Abstraction layers prevent vendor lock-in (Terraform IaC, Kubernetes orchestration)
- ✅ API versioning strategy (semantic versioning v1, v2, v3)

**GAPS**:
- ⚠️ API versioning strategy mentioned in principles but not detailed in requirements (Finding L-001 from analysis-report.md)
- **Mitigation**: Document API versioning policy (semantic versioning, 12-month backward compatibility, 6-month deprecation notice)

**RISKS**:
- R-012 (Vendor Lock-In) - Mitigated through open standards and abstraction layers
- Finding L-001 (API Versioning Strategy) - Low risk, addressable in Alpha phase

**GDS Service Standard Alignment**: Point 13 (Use and contribute to open standards, common components and patterns)

---

### Point 5: Use Cloud First

**TCoP Requirement**: Use public cloud as your first option for hosting, infrastructure and platforms.

**Compliance Status**: ✅ **COMPLIANT**

#### Evidence of Compliance

**Cloud-First Principle** (architecture-principles.md - Principle 1):
- **Mandatory**: All systems MUST use public cloud infrastructure with UK-based data centers unless explicit exception granted
- **On-premise infrastructure prohibited**: No on-premise infrastructure for new systems without CTO approval
- **Cloud benefits**: Scalability, resilience, pay-as-you-go economics, security capabilities, managed services

**UK Cloud Deployment** (requirements.md):
- **BR-006**: UK Data Residency - All data MUST reside in UK data centers (data sovereignty, UK GDPR compliance)
- **Cloud regions**: AWS eu-west-2 (London) or Azure UK South / UK West
- **No cross-border transfers**: Data replication to UK regions only, no international transfers without legal basis
- **INT-004**: UK Cloud Infrastructure - Deploy to public cloud (AWS, Azure, or GCP) with UK region guarantee

**Cloud-Native Architecture** (architecture-principles.md - Principle 1):
- **Stateless services**: Design for auto-scaling, horizontal scaling, ephemeral compute
- **Managed services**: Use cloud-managed databases (RDS PostgreSQL, Azure SQL), object storage (S3, Azure Blob), message queues (SQS, Azure Service Bus)
- **Auto-scaling**: Dynamic scaling based on demand (cost optimization, performance)
- **Infrastructure as Code**: Terraform for multi-cloud portability

**Multi-Cloud Capability** (requirements.md - DR-002):
- **Avoid single provider dependency**: Abstraction layers for critical systems (Terraform IaC, Kubernetes orchestration)
- **Disaster recovery**: Backup to secondary UK region (different availability zone, same cloud provider)
- **Vendor portability**: Use cloud-agnostic services where possible (Kubernetes, PostgreSQL, open-source components)

**Cloud Provider Selection** (backlog.md - STORY-056):
- **Sprint 1**: Cloud provider selection (AWS vs Azure) with UK region availability validation
- **Evaluation criteria**: UK data residency guarantees, Cyber Essentials Plus certification, ISO 27001, cost model (infrastructure + AI API costs <£5M Year 1)
- **Contracts**: UK data residency contractual guarantees, UK-qualified personnel for support

**Managed Services Usage** (architecture-principles.md - Principle 1):
- **Databases**: RDS PostgreSQL (AWS) or Azure SQL Database (managed, automatic backups, encryption at rest)
- **Object Storage**: S3 (AWS) or Azure Blob Storage (UK regions, encryption at rest, versioning)
- **Secrets Management**: AWS Secrets Manager or Azure Key Vault (automated key rotation, audit logging)
- **Message Queues**: SQS (AWS) or Azure Service Bus (managed, at-least-once delivery, dead letter queues)
- **Monitoring**: CloudWatch (AWS) or Azure Monitor + Prometheus/Grafana (observability stack)

#### Assessment

**STRENGTHS**:
- ✅ Cloud-first principle mandatory (architecture principle, non-negotiable)
- ✅ UK cloud deployment (AWS eu-west-2 or Azure UK South/UK West)
- ✅ UK data residency mandatory (BR-006, no cross-border transfers)
- ✅ Cloud-native architecture (stateless services, managed services, auto-scaling)
- ✅ Multi-cloud capability (Terraform IaC, Kubernetes, avoid vendor lock-in)
- ✅ Managed services preferred (RDS, S3, Secrets Manager - not self-managed VMs)

**GAPS**: None identified.

**RISKS**:
- R-010 (Cloud/AI API Costs Exceed Budget) - Mitigated through FinOps controls, rate limiting, cost monitoring, 15% contingency
- R-012 (Vendor Lock-In) - Mitigated through multi-cloud abstraction layers (Terraform, Kubernetes)

**Exception Process**: CTO approval required for on-premise infrastructure (valid exceptions: SECRET data requiring air-gap, legacy system integration during transition).

**GDS Service Standard Alignment**: Point 13 (Use and contribute to open standards, common components and patterns) - Cloud-first enables reuse

---

### Point 6: Make Things Secure

**TCoP Requirement**: Keep systems and data safe with appropriate and proportionate security measures.

**Compliance Status**: ✅ **COMPLIANT** (with 2 High risks requiring mitigation)

#### Evidence of Compliance

**Security by Design Principle** (architecture-principles.md - Principle 4):
- **NON-NEGOTIABLE**: All architectures MUST implement defense-in-depth security with zero-trust principles aligned with NCSC guidance
- **NCSC Secure by Design Principles**: Establish context, make compromise difficult, make disruption difficult, make compromise detection easier, reduce impact of compromise
- **Zero Trust Architecture**: Verify explicitly, least privilege access, assume breach

**Mandatory Security Controls** (architecture-principles.md - Principle 4):

**Identity and Access**:
- [ ] Multi-factor authentication (MFA) for all human users (NFR-SEC-001)
- [ ] Service-to-service authentication (mutual TLS, signed tokens, API keys with rotation)
- [ ] Role-Based Access Control (RBAC) with least privilege (FR-011, 4 roles: User, Power User, Admin, Governance Lead)
- [ ] Privileged Access Management (PAM) for administrative access
- [ ] Single Sign-On (SSO) via Government Gateway or Azure AD (FR-009, INT-003)

**Data Protection**:
- [ ] Encryption at rest for all data stores (AES-256 for OFFICIAL-SENSITIVE data) (NFR-SEC-003)
- [ ] Encryption in transit (TLS 1.3 preferred, TLS 1.2 minimum) (NFR-SEC-003)
- [ ] Secrets management via secure vault (AWS Secrets Manager, Azure Key Vault) (no secrets in code)
- [ ] Key rotation policy defined and automated (tenant-specific encryption keys)

**Network Security**:
- [ ] Network segmentation with micro-segmentation (separate VPCs/VNets for high-security tenants)
- [ ] Web Application Firewall (WAF) for internet-facing services
- [ ] DDoS protection for public endpoints
- [ ] Private subnets for data and application tiers, no direct internet access from backend

**Application Security**:
- [ ] Input validation and output encoding (prevent injection attacks - OWASP Top 10)
- [ ] Dependency scanning for vulnerabilities (daily scans via Snyk, Dependabot)
- [ ] Static Application Security Testing (SAST) in CI/CD pipeline
- [ ] Dynamic Application Security Testing (DAST) in pre-production
- [ ] Software Bill of Materials (SBOM) maintained for all components

**Monitoring and Response**:
- [ ] Structured logging of all authentication and authorization events (audit trail)
- [ ] Security Information and Event Management (SIEM) integration (Splunk/Elastic Security)
- [ ] Automated alerting for security anomalies (cross-tenant access attempts, RLS bypass)
- [ ] Incident response runbook with escalation procedures (STORY-017 - Sprint 4)
- [ ] Regular security testing (quarterly penetration testing, NCSC-approved CHECK scheme)

**Cyber Essentials Plus Certification** (requirements.md):
- **BR-003**: Zero Data Breaches or Cross-Tenant Leaks (NON-NEGOTIABLE)
- **NFR-SEC-004**: Cyber Essentials Plus certification for OFFICIAL-SENSITIVE data
- **Validation**: Annual re-certification maintained

**Data Classification-Specific Controls** (architecture-principles.md - Principle 13):
- **OFFICIAL-SENSITIVE** (this project): Encryption at rest/transit, MFA, audit logging (7-year retention), Cyber Essentials Plus, Data Protection Impact Assessment (DPIA)

**Multi-Tenant Isolation** (requirements.md - FR-001, NFR-SEC-006):
- **6-layer defense-in-depth**:
  1. Database Row-Level Security (RLS) - PostgreSQL RLS policies on all tables (STORY-009 - Sprint 1)
  2. Application-level tenant validation - Tenant_id from JWT token validated on EVERY API request (STORY-010 - Sprint 2)
  3. Tenant-specific encryption keys - Separate KEK per tenant in AWS KMS / Azure Key Vault (STORY-011 - Sprint 2)
  4. Network isolation - Separate VPCs/VNets for high-security tenants (STORY-012 - Sprint 3)
  5. Automated boundary tests - CI/CD pipeline fails if cross-tenant access detected (STORY-013 - Sprint 3)
  6. Quarterly penetration testing - NCSC-approved CHECK scheme firm (STORY-014 - Sprint 4)

**NCSC Secure by Design Assurance** (requirements.md):
- **BR-003**: NCSC assurance required before Private Beta (Month 6 gate blocker)
- **R-004**: NCSC security review scheduled Month 2-6 (parallel with development)
- **Early engagement**: Weekly NCSC liaison calls from Week 3, security architecture review BEFORE Sprint 1
- **Validation**: Pass NCSC review with no critical/high findings

#### Findings

**HIGH PRIORITY - Risk R-001: Cross-Tenant Data Leak**:
- **Issue**: Multi-tenant architecture complexity creates risk of cross-tenant data leak (OFFICIAL-SENSITIVE data exposure between departments)
- **Inherent Risk**: 5 × 4 = 20 (CRITICAL) - Almost certain likelihood, major impact
- **Residual Risk**: 3 × 4 = 12 (HIGH) - After 6-layer defense-in-depth controls
- **Impact**: GDPR breach (£17.5M ICO fine), ministerial accountability (Permanent Secretary resignation), platform shutdown, reputational damage
- **Mitigation**:
  - 6-layer defense-in-depth (RLS, app validation, network, encryption, boundary tests, pen testing)
  - NCSC security architecture review Month 2 (BEFORE Sprint 1)
  - Real-time SIEM monitoring for cross-tenant access attempts (Sprint 4)
  - Quarterly NCSC-led penetration testing (starting Month 6)
- **Owner**: NCSC Lead Architect / Cabinet Office CTO
- **Status**: IN PROGRESS (controls being implemented Sprint 1-4)
- **Target Residual Risk**: 2 × 4 = 8 (MEDIUM) after additional mitigations by Month 12

**HIGH PRIORITY - Risk R-004: NCSC Secure by Design Assurance Delay/Failure**:
- **Issue**: NCSC security review identifies critical findings requiring remediation, delaying Private Beta launch beyond Month 6
- **Inherent Risk**: 4 × 4 = 16 (HIGH) - Likely likelihood, major impact
- **Residual Risk**: 3 × 4 = 12 (HIGH) - After early NCSC engagement and parallel review
- **Impact**: Private Beta launch blocked, 1-month remediation delay (Month 6 → Month 7), ministerial accountability, budget impact (£500K)
- **Mitigation**:
  - Early NCSC engagement (Month 2, weekly liaison calls)
  - NCSC security architecture review BEFORE Sprint 1 development
  - Defense-in-depth controls (NCSC best practice architecture)
  - Quarterly penetration testing BEFORE NCSC Month 6 review
  - 2-week conditional launch buffer (limited Private Beta proceeds if NCSC approves)
- **Owner**: NCSC Lead Architect / Cabinet Office CTO
- **Status**: IN PROGRESS (NCSC engagement starting Week 3)
- **Target Residual Risk**: 2 × 4 = 8 (MEDIUM) after NCSC early engagement

#### Assessment

**STRENGTHS**:
- ✅ Security by design principle mandatory (NON-NEGOTIABLE, architecture principle)
- ✅ NCSC Secure by Design principles embedded (defense-in-depth, zero trust)
- ✅ Comprehensive security controls (identity, data protection, network, application, monitoring)
- ✅ Multi-tenant isolation defense-in-depth (6 layers, automated testing)
- ✅ Cyber Essentials Plus certification required (OFFICIAL-SENSITIVE data)
- ✅ NCSC early engagement (Month 2, parallel review, weekly liaison calls)
- ✅ Quarterly penetration testing (NCSC-approved CHECK scheme)
- ✅ Security requirements traceability (NFR-SEC-001 through NFR-SEC-006)

**GAPS**: None identified (comprehensive security controls planned).

**RISKS**:
- **HIGH**: R-001 (Cross-Tenant Data Leak) - Residual risk 12 after controls, target 8 by Month 12
- **HIGH**: R-004 (NCSC Assurance Delay) - Residual risk 12 after early engagement, target 8 after Month 2 review
- Security risks are highest priority, NCSC assurance is Private Beta gate blocker

**Critical Path**: NCSC security architecture review Week 3 (BEFORE Sprint 1 development) is CRITICAL to avoid Month 6 delay.

**GDS Service Standard Alignment**: Point 9 (Create a secure service which protects users' privacy)

---

### Point 7: Make Privacy Integral

**TCoP Requirement**: Make sure citizens' rights are protected by integrating privacy as an essential part of your system.

**Compliance Status**: ✅ **COMPLIANT** (with 1 High risk requiring mitigation)

#### Evidence of Compliance

**Privacy by Design Principle** (architecture-principles.md - Principle 5):
- **NON-NEGOTIABLE**: All systems MUST embed privacy by design principles and comply with GDPR/UK GDPR
- **DPIA Mandatory**: Data Protection Impact Assessments for systems processing personal data at scale or sensitive data
- **Legal requirement**: UK GDPR and Data Protection Act 2018, ICO enforcement (fines up to £17.5M or 4% turnover)

**Privacy by Design Principles** (GDPR Article 25):
1. **Data Minimization**: Collect only data necessary for stated purpose
2. **Purpose Limitation**: Use data only for original purpose (or compatible purpose)
3. **Storage Limitation**: Retain data only as long as necessary (automated deletion)
4. **Accuracy**: Keep data accurate and up to date
5. **Integrity and Confidentiality**: Protect data with appropriate security
6. **Accountability**: Demonstrate compliance with GDPR

**GDPR/UK GDPR Mandatory Requirements** (architecture-principles.md - Principle 5):

**Lawful Basis for Processing**:
- [ ] Lawful basis identified for all personal data processing (NFR-C-001)
- [ ] **Public task** (Article 6(1)(e)) - Most common basis for government (official authority, public interest)
- [ ] Consent obtained where required (explicit, informed, freely given, specific)

**Individual Rights** (MUST support):
- [ ] **Right to be informed**: Privacy notices provided (published before Private Beta)
- [ ] **Right of access**: Subject Access Requests (SAR) fulfilled within 30 days (STORY-064 - Sprint 4)
- [ ] **Right to rectification**: Ability to correct inaccurate data (user profile management)
- [ ] **Right to erasure**: "Right to be forgotten" implemented (STORY-008, STORY-064 - Sprint 3-4)
- [ ] **Right to restrict processing**: Ability to pause processing
- [ ] **Right to data portability**: Export data in machine-readable format (CSV/JSON - STORY-032, STORY-064)
- [ ] **Right to object**: Ability to object to processing

**Data Protection Impact Assessment (DPIA)** (requirements.md):
- **NFR-C-001**: DPIA MANDATORY for this project (generative AI, cross-government scale, OFFICIAL-SENSITIVE data)
- **DPIA triggers**: Large-scale processing of sensitive personal data, systematic monitoring, automated decision-making with legal/significant effects, innovative use of technology (AI/ML), processing of children's data
- **ICO approval**: DPIA submitted to ICO for review and approval before Private Beta (Month 6 gate blocker)
- **STORY-066**: ICO DPIA Documentation & Submission (Sprint 5)

**Data Breach Procedures** (architecture-principles.md - Principle 5):
- [ ] Breach detection capability (security monitoring, SIEM alerting)
- [ ] Breach notification to ICO within 72 hours (if high risk to rights and freedoms)
- [ ] Breach notification to affected individuals (if high risk)
- [ ] Breach investigation and remediation process (incident response runbook - STORY-017)
- [ ] Breach register maintained (audit trail for ICO audits)

**Data Sharing and Transfers** (architecture-principles.md - Principle 12):
- [ ] Data sharing agreements for inter-departmental sharing (between Home Office, HMRC, DHSC)
- [ ] Standard Contractual Clauses (SCCs) for international transfers (if required)
- [ ] Adequacy decisions validated for international transfers (UK-EU adequacy in place)
- [ ] No transfers to inadequate jurisdictions without safeguards

**GDPR Compliance Requirements** (requirements.md):
- **NFR-C-001**: GDPR Compliance - Achieve full GDPR/UK GDPR compliance including DPIA, data subject rights portal, consent management, breach notification procedures
- **FR-005**: Audit Logging - Immutable Write-Once-Read-Many (WORM) storage for 7-year retention (HM Government retention schedule)
- **STORY-064**: GDPR Data Subject Rights Portal (Access, Deletion, Portability) - Sprint 4
- **STORY-065**: GDPR Consent Management & Audit Trail - Sprint 4

**AI-Specific Privacy Considerations** (architecture-principles.md - Principle 9):
- **AI Playbook Principle 9**: Make your AI legally compliant (GDPR, Equality Act 2010, Human Rights Act 1998)
- **Automated decision-making**: Human-in-the-loop for high-stakes decisions (FR-006, STORY-037, STORY-038)
- **Data minimization**: AI models trained only on necessary data, not full document corpus
- **Explainability**: AI outputs include source citations (DPIA requirement for algorithmic transparency)

#### Findings

**HIGH PRIORITY - Risk R-008: ICO DPIA Rejection or Conditional Approval**:
- **Issue**: ICO Data Protection Impact Assessment identifies high privacy risks requiring additional controls, delaying Private Beta
- **Inherent Risk**: 3 × 4 = 12 (MEDIUM) - Possible likelihood, major impact
- **Residual Risk**: 2 × 5 = 10 (MEDIUM) - After early ICO engagement and privacy-by-design architecture
- **Impact**: Private Beta launch delayed (Month 6 → Month 7), additional privacy controls required (cost impact), ICO enforcement action if non-compliant
- **Mitigation**:
  - Early ICO engagement (Month 3 DPIA preparation)
  - Privacy-by-design architecture (data minimization, encryption, data subject rights from Sprint 1)
  - GDPR compliance controls (data subject rights portal, consent management, breach notification - Sprint 4)
  - Human-in-the-loop for high-stakes AI decisions (DPIA requirement for algorithmic transparency - Sprint 9)
- **Owner**: ICO Chief Technology Officer / Data Protection Officer
- **Status**: IN PROGRESS (DPIA preparation Month 3-5)
- **Target Residual Risk**: 1 × 5 = 5 (LOW) after ICO DPIA approval Month 6

#### Assessment

**STRENGTHS**:
- ✅ Privacy by design principle mandatory (NON-NEGOTIABLE, legal requirement)
- ✅ DPIA mandatory for this project (generative AI, cross-government scale, OFFICIAL-SENSITIVE data)
- ✅ Individual rights mechanisms implemented (SAR, erasure, portability, rectification)
- ✅ Data minimization (collect only necessary data for stated purpose)
- ✅ Encryption at rest/transit (protect data integrity and confidentiality)
- ✅ Audit logging (7-year retention, immutable WORM storage for ICO audits)
- ✅ Data breach procedures (72-hour ICO notification, incident response runbook)
- ✅ Early ICO engagement (Month 3 DPIA preparation, before Private Beta)

**GAPS**: None identified (comprehensive GDPR compliance controls planned).

**RISKS**:
- **MEDIUM**: R-008 (ICO DPIA Rejection) - Residual risk 10 after early engagement, target 5 after DPIA approval
- ICO DPIA approval is Private Beta gate blocker (Month 6)

**Critical Path**: ICO DPIA submission Month 5, approval required by Month 6 for Private Beta launch.

**GDS Service Standard Alignment**: Point 9 (Create a secure service which protects users' privacy)

---

### Point 8: Share, Reuse and Collaborate

**TCoP Requirement**: Avoid duplicating effort and unnecessary costs by collaborating across government and sharing reusable components.

**Compliance Status**: ✅ **COMPLIANT**

#### Evidence of Compliance

**Reuse Before Buy, Buy Before Build Principle** (architecture-principles.md - Principle 3):
- **Decision hierarchy**: 1) GOV.UK shared services (reuse), 2) Open-source components (reuse), 3) Commercial off-the-shelf (buy), 4) Custom build (last resort)
- **Cost savings rationale**: Reuse reduces cost (£60M cumulative savings target), accelerates delivery, benefits from collective investment

**GOV.UK Shared Services Usage** (architecture-principles.md - Principle 3):
- **GOV.UK Notify**: Considered for email/SMS notifications (user onboarding, alerts)
- **GOV.UK Pay**: Not applicable (no payment processing in this platform)
- **GOV.UK Verify**: Identity verification via Government Gateway / Azure AD SSO (INT-003)
- **GOV.UK PaaS**: Evaluated as deployment option (Cloud Foundry-based platform)
- **GOV.UK Design System**: MANDATORY for UI components (buttons, forms, navigation, notifications) - Principle 6
- **GOV.UK Forms**: Not applicable (AI platform, not form-based service)

**Open Source Reuse** (architecture-principles.md - Principle 3):
- **PostgreSQL**: Open-source database (reuse, no licensing costs)
- **Kubernetes**: Open-source container orchestration (reuse, vendor portability)
- **Terraform**: Open-source Infrastructure as Code (reuse, multi-cloud support)
- **Prometheus / Grafana**: Open-source monitoring (reuse, proven observability stack)

**Cross-Government Collaboration** (stakeholder-drivers.md):
- **Centralized platform**: 20+ departments share single platform (avoid duplicate AI tool subscriptions)
- **Cost savings**: £60M over 5 years (80% reduction vs 20 departments each procuring ChatGPT Enterprise £75K/year)
- **Pilot departments**: Home Office, HMRC, DHSC co-design use cases (immigration, tax, health policy)
- **Knowledge sharing**: Departments share knowledge bases (within departmental boundaries for OFFICIAL-SENSITIVE data)
- **Best practices**: Cross-departmental AI governance forum (share bias detection, explainability techniques)

**Contribution Back to Community** (architecture-principles.md - Principle 3):
- **Open-source contributions**: Contribute improvements to PostgreSQL RLS patterns, Kubernetes security configurations, Terraform modules (beneficial to other government departments)
- **Code publication**: Platform code published on GitHub (Cabinet Office organization) where security permits
- **Documentation**: Architecture patterns, multi-tenant isolation techniques shared with NCSC, CDDO, other departments

**Business Case Driven by Reuse** (stakeholder-drivers.md - Goal G-1):
- **Goal G-1**: "Deliver manifesto commitment to centralize AI tools with 80% cost reduction"
- **Outcome O-1**: "£60M cumulative cost savings over 5 years (Year 1: £12M savings, Year 5: £15M savings)"
- **Mechanism**: Replace 20 departments × £75K/year ChatGPT Enterprise subscriptions (£15M/year) with centralized platform (£3M/year operational cost)

#### Assessment

**STRENGTHS**:
- ✅ Reuse before buy principle mandatory (architecture principle)
- ✅ GOV.UK Design System usage mandatory (proven accessible UI patterns)
- ✅ Open-source components preferred (PostgreSQL, Kubernetes, Terraform, Prometheus)
- ✅ Centralized platform (20+ departments share single platform, avoid duplication)
- ✅ Cross-government collaboration (pilot departments co-design, knowledge sharing)
- ✅ Cost savings driven by reuse (£60M over 5 years, 80% reduction)
- ✅ Contribution back to community (open-source contributions, code publication, documentation sharing)

**GAPS**: None identified.

**RISKS**:
- R-002 (Low User Adoption) - If departments don't adopt centralized platform, reuse benefits not realized
- **Mitigation**: User research, co-design, change management team

**GDS Service Standard Alignment**: Point 13 (Use and contribute to open standards, common components and patterns)

---

### Point 9: Integrate and Adapt Technology

**TCoP Requirement**: Your technology should work with existing technologies, processes and infrastructure in your organization.

**Compliance Status**: ✅ **COMPLIANT** (with 1 Medium finding)

#### Evidence of Compliance

**Integration Requirements** (requirements.md):

**Microsoft 365 Integration** (INT-001):
- **FR-015**: Integrate with Microsoft 365 for document access (SharePoint, OneDrive, Teams)
- **STORY-045**: Microsoft Graph API Integration (OAuth 2.0) - Sprint 3
- **STORY-046**: SharePoint Document Retrieval - Sprint 4
- **STORY-047**: OneDrive Document Save - Sprint 4
- **STORY-048**: Microsoft Teams Bot Integration - Sprint 5
- **Open standards**: Microsoft Graph API uses REST + OAuth 2.0 (open standards)

**Google Workspace Integration** (INT-002):
- **FR-015**: Integrate with Google Workspace for document access (Google Drive, Docs)
- **STORY-049**: Google Drive API Integration (OAuth 2.0) - Sprint 5
- **STORY-050**: Google Drive Document Retrieval - Sprint 6
- **Open standards**: Google Drive API uses REST + OAuth 2.0 (open standards)

**Government SSO Integration** (INT-003):
- **FR-009**: Government SSO Integration (Azure AD, Government Gateway)
- **STORY-001**: Government SSO Integration (Azure AD, OAuth 2.0, OpenID Connect) - Sprint 1
- **Seamless authentication**: Users login with existing @gov.uk email (no new credentials)
- **MFA enforcement**: Multi-factor authentication via Azure AD Conditional Access (STORY-002 - Sprint 1)

**AI Foundation Model Integration** (INT-005):
- **STORY-051**: AI Foundation Model Vendor Selection (Azure OpenAI, AWS Bedrock, Anthropic) - Sprint 3
- **STORY-052**: Azure OpenAI UK Region Integration - Sprint 6
- **UK data residency**: AI model API calls processed in UK regions (BR-006, R-006)
- **API abstraction**: Vendor abstraction layer for portability (avoid vendor lock-in R-012)

**API-First Architecture** (architecture-principles.md - Principle 2):
- **All systems expose APIs**: OpenAPI 3.0+ specifications for interoperability
- **Versioning**: Semantic versioning (v1, v2, v3), 12-month backward compatibility, 6-month deprecation notice
- **No direct database coupling**: Systems communicate via APIs, not shared databases (loose coupling)

**Loose Coupling Principle** (architecture-principles.md - Principle 16):
- **Database per service**: Each microservice has its own database (avoid shared database anti-pattern)
- **Event-driven communication**: Asynchronous messaging (SQS, Azure Service Bus) for non-real-time flows
- **Independent deployment**: Deployment of one system doesn't require deployment of another

**Technology Adaptability** (architecture-principles.md):
- **Cloud-agnostic**: Terraform IaC, Kubernetes orchestration (can switch cloud providers)
- **AI model portability**: Abstraction layer allows switching AI vendors (Azure OpenAI → AWS Bedrock → Anthropic)
- **Open standards**: OAuth 2.0, OpenAPI, JSON, PostgreSQL (not vendor-specific)

#### Findings

**MEDIUM PRIORITY - Finding L-001: API Versioning Strategy Detail Gap**:
- **Issue**: API versioning strategy mentioned in architecture principles ("semantic versioning v1, v2, v3") but not detailed in requirements
- **Impact**: Risk of breaking API changes without proper version management, downstream integration failures
- **Traceability**: Finding L-001 from analysis-report.md
- **Mitigation**:
  - Document API versioning policy (semantic versioning v1.0.0, major.minor.patch)
  - 12-month backward compatibility guarantee for major versions (v1 supported until v3 launch)
  - 6-month deprecation notice before breaking changes (email notifications to API consumers)
  - API changelog published (OpenAPI specs versioned in Git)
- **Risk Level**: LOW (standard practice, easily addressable)
- **Owner**: Tech Lead / API Architect
- **Due Date**: 2026-01-15 (Alpha phase)

#### Assessment

**STRENGTHS**:
- ✅ Comprehensive integration plan (Microsoft 365, Google Workspace, Government SSO, AI foundation model)
- ✅ Open standards for interoperability (OAuth 2.0, REST APIs, OpenAPI 3.0+)
- ✅ API-first architecture (all systems expose APIs, no direct database coupling)
- ✅ Loose coupling (database per service, event-driven communication, independent deployment)
- ✅ Technology adaptability (cloud-agnostic Terraform, AI model abstraction, open standards)
- ✅ Integration requirements traced to user stories (INT-001 through INT-005)

**GAPS**:
- ⚠️ API versioning strategy detailed in principles but not in requirements (Finding L-001)
- **Mitigation**: Document API versioning policy (semantic versioning, backward compatibility, deprecation notices)

**RISKS**:
- R-017 (Integration Failures) - Residual risk 6 (LOW) after fallback mechanisms (manual upload, API versioning, vendor SLA monitoring)
- Finding L-001 (API Versioning) - Low risk, addressable in Alpha phase

**GDS Service Standard Alignment**: Point 13 (Use and contribute to open standards, common components and patterns)

---

### Point 10: Make Better Use of Data

**TCoP Requirement**: Use data more effectively by improving your capability, access, quality and management.

**Compliance Status**: ✅ **COMPLIANT** (with 1 Medium finding)

#### Evidence of Compliance

**Data Quality and Lineage Principle** (architecture-principles.md - Principle 14):
- **Data quality dimensions**: Completeness, accuracy, consistency, timeliness, validity
- **Data lineage**: Source-to-target mapping, transformation logic version-controlled, audit trail
- **Data contracts**: Schema specifications, quality SLAs, breaking change notification (30 days)

**Data Quality Requirements**:

**1. Completeness**: No unexpected nulls in required fields
- [ ] Required fields enforced at source (database NOT NULL constraints)
- [ ] Completeness metrics tracked (% records with all required fields)

**2. Accuracy**: Data reflects reality
- [ ] Validation rules at data entry (email format, date ranges, UK postcode format)
- [ ] Cross-system reconciliation (data matches across Microsoft 365, Google Workspace, platform)
- [ ] User feedback mechanism to report inaccuracies (FR-010 - thumbs up/down)

**3. Consistency**: No conflicting data
- [ ] Referential integrity enforced (foreign keys, database constraints)
- [ ] Data formats standardized (ISO 8601 dates, E.164 phone numbers, UK addresses)
- [ ] Duplicate detection and deduplication

**4. Timeliness**: Data is fresh and up-to-date
- [ ] Freshness SLAs defined (e.g., knowledge base indexed within 24 hours of document upload)
- [ ] Staleness alerts for critical data (document older than 90 days flagged)
- [ ] Data refresh frequency documented (real-time for documents, daily for usage analytics)

**5. Validity**: Data conforms to business rules
- [ ] Business rule validation (data classification OFFICIAL/OFFICIAL-SENSITIVE, UK postcode format)
- [ ] Allowed value lists (enumerations for departments, user roles)
- [ ] Cross-field validation (end date > start date, document size < 50MB)

**Data Governance** (requirements.md):

**Data Classification Handling** (FR-007):
- **OFFICIAL vs OFFICIAL-SENSITIVE**: AI automatically detects data classification based on content patterns (STORY-019 - Sprint 5)
- **Classification-specific controls**: OFFICIAL-SENSITIVE requires Cyber Essentials Plus, DPIA, Tier 2 security training (architecture-principles.md - Principle 13)

**Knowledge Base Management** (FR-008):
- **Indexing**: Documents indexed with vector embeddings for semantic search (STORY-026 - Sprint 9)
- **Search quality**: Semantic search returns relevant results in <3 seconds (95th percentile)
- **Q&A accuracy**: Knowledge base Q&A provides source citations (FR-013, STORY-028 - Sprint 10)

**Usage Analytics** (FR-014):
- **Dashboard**: Departmental admins see usage analytics (Monthly Active Users, cost allocation, query volume) - STORY-054 - Sprint 8
- **Chargeback**: Cost allocation per department (usage-based pricing, transparent cost breakdown) - STORY-055 - Sprint 8

**Data Residency** (DR-001 through DR-005):
- **UK data residency**: All data stored in UK regions (AWS eu-west-2, Azure UK South/UK West) - BR-006
- **No international transfers**: Cross-border data transfers prohibited without legal basis (adequacy decisions, Standard Contractual Clauses)
- **Audit trail**: Data residency validated through audit logs (cloud provider region metadata)

**Single Source of Truth Principle** (architecture-principles.md - Principle 15):
- **System of record**: Each data domain has single authoritative source
- **User identity**: Government Gateway / Azure AD (SSO system of record)
- **Documents**: User's own Microsoft 365 / Google Workspace (platform does not duplicate, only references)
- **AI outputs**: Platform is system of record (AI-generated summaries, drafts stored with version history)

**Data Lineage**:
- **Source-to-target mapping**: Document → AI model → Summary/Draft (traceability via audit logs FR-005)
- **Transformation logic**: AI model prompts version-controlled (Git repository)
- **Impact analysis**: Schema changes tracked (OpenAPI specs versioned, breaking changes notified 6 months in advance)

#### Findings

**MEDIUM PRIORITY - Finding M-001: Test Coverage Metrics Undefined**:
- **Issue**: Test coverage thresholds stated in backlog Definition of Done (>70% unit test coverage) but not formalized in NFRs
- **Impact**: Risk of inconsistent test coverage, regression bugs, insufficient quality assurance
- **Traceability**: Finding M-001 from analysis-report.md
- **Mitigation**:
  - Add NFR-Q-001: Automated test coverage thresholds (unit >70%, integration >60%, E2E critical paths 100%)
  - CI/CD pipeline enforces coverage thresholds (build fails if coverage below threshold)
  - Test coverage dashboards (SonarQube, Codecov) show trends over time
- **Risk Level**: MEDIUM (quality risk, but easily addressable)
- **Owner**: Tech Lead / QA Lead
- **Due Date**: 2025-12-31 (Discovery phase)

#### Assessment

**STRENGTHS**:
- ✅ Data quality principles defined (completeness, accuracy, consistency, timeliness, validity)
- ✅ Data lineage tracked (source-to-target mapping, transformation logic version-controlled, audit trail)
- ✅ Data classification handling (OFFICIAL vs OFFICIAL-SENSITIVE, automated detection)
- ✅ Knowledge base management (vector embeddings, semantic search, source citations)
- ✅ Usage analytics dashboard (departmental admins, cost allocation, chargeback)
- ✅ UK data residency (all data in UK regions, no international transfers, audit trail)
- ✅ Single source of truth (system of record defined for each data domain)

**GAPS**:
- ⚠️ Test coverage metrics undefined in NFRs (Finding M-001)
- **Mitigation**: Add NFR-Q-001 for automated test coverage thresholds (unit >70%, integration >60%, E2E critical paths 100%)

**RISKS**:
- Finding M-001 (Test Coverage Metrics) - Medium risk, addressable in Discovery phase

**GDS Service Standard Alignment**: Point 10 (Define what success looks like and publish performance data)

---

### Point 11: Define Your Purchasing Strategy

**TCoP Requirement**: Your purchasing strategy must show you've considered commercial and technology aspects, and contractual limitations.

**Compliance Status**: ⚠️ **PARTIALLY COMPLIANT** (1 High priority issue)

#### Evidence of Compliance

**Build vs Buy Decision Criteria** (architecture-principles.md - Principle 3):
- **Decision hierarchy**: Reuse (GOV.UK shared services, open-source) → Buy (COTS via G-Cloud) → Build (custom development last resort)
- **Justification required**: Document justification if building custom instead of buying (cost comparison 5-year TCO, risk assessment, capability gap analysis, Wardley Mapping)

**Vendor Evaluation Planned** (backlog.md):

**Cloud Provider Selection** (STORY-056 - Sprint 1):
- **Vendors evaluated**: AWS vs Azure (parallel proofs-of-concept Week 1)
- **Evaluation criteria**: UK region availability, UK data residency guarantees, Cyber Essentials Plus certification, ISO 27001, cost model (infrastructure + AI API costs <£5M Year 1)
- **Contracts**: UK data residency contractual guarantees, UK-qualified personnel for support, no cross-border data transfers
- **Owner**: Cabinet Office CTO / Procurement Lead
- **Due Date**: 2025-11-15 (Sprint 1, CRITICAL PATH)

**AI Foundation Model Vendor Selection** (STORY-051 - Sprint 3):
- **Vendors evaluated**: Azure OpenAI UK, AWS Bedrock UK, Anthropic UK
- **Evaluation criteria**: UK data residency, model performance (accuracy, latency <3s P95), cost (API pricing, volume discounts), security (Cyber Essentials Plus, ISO 27001)
- **Contracts**: UK data processing guarantees, no cross-border transfers, UK support team
- **Owner**: Cabinet Office CTO / Vendor Manager
- **Due Date**: 2025-12-15 (Sprint 3)

**Procurement Route** (stakeholder-drivers.md):
- **G-Cloud Framework**: Use Crown Commercial Service (CCS) G-Cloud framework for cloud services (AWS, Azure, AI vendors)
- **Digital Outcomes and Specialists**: Use DOS framework for development team augmentation (consultants, contractors)
- **Compliance**: Public procurement regulations (PCR 2015), value for money (HM Treasury Green Book)

**Contractual Considerations**:

**UK Data Residency Clauses** (BR-006, R-006):
- [ ] Vendor contractually prohibited from transferring data outside UK without approval
- [ ] Cloud provider guarantees UK data residency (no replication to non-UK regions)
- [ ] AI vendor processes all API calls in UK regions (Azure UK South, AWS eu-west-2)
- [ ] Vendor subject to UK jurisdiction (not extraterritorial data access laws like US CLOUD Act)

**Vendor Lock-In Mitigation** (R-012):
- [ ] Abstraction layers (Terraform IaC, Kubernetes, open APIs)
- [ ] Multi-vendor evaluation (AWS vs Azure, Azure OpenAI vs AWS Bedrock vs Anthropic)
- [ ] Exit strategy documented (data export in open formats, knowledge base migration plan)
- [ ] Contractual exit rights (notice period 90 days, data handover support, no lock-in penalties)

**Service Level Agreements (SLAs)**:
- [ ] Cloud infrastructure uptime SLA (99.9% minimum, financial credits for downtime)
- [ ] AI API latency SLA (<3s response time P95, financial credits for SLA breach)
- [ ] Support SLA (UK-based support team, 4-hour response for critical issues, 24-hour for high issues)

**Cost Management** (R-010, R-011):
- [ ] Fixed-price contracts where possible (development team, consultants)
- [ ] Usage-based pricing with volume discounts (cloud infrastructure, AI API calls)
- [ ] Cost caps and alerts (FinOps monitoring, alert if monthly spend >10% variance)
- [ ] 15% contingency reserve (£2.8M) for cost overruns (HM Treasury approval required for drawdown)

**Vendor Performance Monitoring** (Finding L-002):
- [ ] SLA monitoring dashboards (uptime, latency, support response time)
- [ ] Quarterly vendor review meetings (performance against SLAs, cost optimization, roadmap alignment)
- [ ] Escalation procedures (vendor underperformance triggers contract review, potential vendor change)

#### Findings

**HIGH PRIORITY - Finding H-11-01: Vendor Evaluation Incomplete (Critical Path)**:
- **Issue**: Cloud provider and AI foundation model vendor selection incomplete at Discovery phase. Contracts must be signed by Week 2 (Sprint 1) to avoid infrastructure deployment delay.
- **Impact**:
  - Infrastructure deployment blocked until cloud provider selected (STORY-057 depends on STORY-056)
  - AI features blocked until AI vendor selected (STORY-052 depends on STORY-051)
  - Timeline slip risk (R-003) - Private Beta delay beyond Month 6 if vendor contracts delayed
  - Budget risk (R-010) - Rushed vendor selection may miss cost optimization opportunities
- **Traceability**: R-006 (Vendor UK Data Residency Failure), R-010 (Cloud/AI Cost Overruns), R-012 (Vendor Lock-In)
- **Mitigation**:
  - **Week 1 - Parallel AWS/Azure Proofs-of-Concept**: Run parallel PoCs to accelerate vendor evaluation
  - **Week 1 - Legal team pre-negotiates contracts**: Standard clauses (UK data residency, support SLA) pre-negotiated to reduce contract signature time from 6 weeks to 2 weeks
  - **Week 2 - Vendor selection decision**: Cabinet Office CTO approval of vendor selection scorecard
  - **Week 2 - Contracts signed**: Cloud provider and AI vendor contracts signed by 2025-11-15
- **Risk Level**: HIGH (critical path blocker, timeline risk)
- **Owner**: Cabinet Office CTO / Procurement Lead
- **Due Date**: 2025-11-15 (Week 2, Sprint 1)
- **Status**: NOT STARTED (must start Week 1 to avoid delay)

**MEDIUM PRIORITY - Finding L-002: Vendor Performance SLA Monitoring**:
- **Issue**: Vendor SLA monitoring mentioned in risk register (R-010 mitigation) but not detailed in requirements
- **Impact**: Risk of vendor underperformance going undetected (uptime degradation, support delays)
- **Mitigation**:
  - Add NFR-O-001: Vendor SLA monitoring dashboards (uptime, latency, support response time)
  - Quarterly vendor review meetings (performance against SLAs, cost optimization, roadmap alignment)
- **Risk Level**: LOW (monitoring gap, but easily addressable)
- **Owner**: Vendor Manager / Operations Lead
- **Due Date**: 2026-03-31 (Sprint 8)

#### Assessment

**STRENGTHS**:
- ✅ Build vs buy decision criteria defined (architecture principle, Wardley Mapping planned)
- ✅ Vendor evaluation scorecard (cloud provider, AI vendor)
- ✅ Procurement route (G-Cloud framework, DOS framework)
- ✅ UK data residency contractual clauses (no cross-border transfers)
- ✅ Vendor lock-in mitigation (abstraction layers, multi-vendor evaluation, exit strategy)
- ✅ SLA requirements defined (uptime 99.9%, latency <3s, UK support)
- ✅ Cost management controls (FinOps, cost caps, 15% contingency)

**GAPS**:
- ⚠️ **HIGH**: Vendor evaluation incomplete (cloud provider, AI vendor) - Must be completed Week 1-2 to avoid timeline delay
- ⚠️ **MEDIUM**: Vendor SLA monitoring details undefined

**RISKS**:
- **HIGH**: Finding H-11-01 (Vendor evaluation incomplete) - Critical path blocker
- R-006 (Vendor UK Data Residency Failure) - Residual risk 9 (MEDIUM) after UK contracts
- R-010 (Cloud/AI Cost Overruns) - Residual risk 9 (MEDIUM) after FinOps controls
- R-012 (Vendor Lock-In) - Residual risk 9 (MEDIUM) after abstraction layers

**Critical Path**: Vendor selection Week 1-2 (STORY-056) is CRITICAL PATH for infrastructure deployment (STORY-057).

**GDS Service Standard Alignment**: Point 11 (Choose the right tools and technology)

---

### Point 12: Make Your Technology Sustainable

**TCoP Requirement**: Make sure your technology, infrastructure and systems are sustainable.

**Compliance Status**: ⚠️ **PARTIALLY COMPLIANT** (1 High priority issue)

#### Evidence of Compliance

**Sustainability Considerations** (identified gaps):

**Energy Efficiency**:
- Cloud infrastructure auto-scaling (scale down during off-peak hours, reduce energy consumption)
- AI model inference optimization (reduce unnecessary API calls, cache common queries, prompt engineering efficiency)
- Serverless architecture where applicable (AWS Lambda, Azure Functions - pay only for compute time, auto-scale to zero)

**Carbon Footprint**:
- **Cloud provider carbon neutrality**: AWS and Azure both committed to carbon neutrality (AWS: 100% renewable energy by 2025, Azure: carbon negative by 2030)
- **UK data centers**: UK regions (AWS eu-west-2, Azure UK South) use renewable energy sources
- **Data transfer optimization**: Minimize cross-region data transfers (reduce network energy consumption)

**Circular Economy Principles**:
- **Cloud infrastructure**: No physical hardware procurement (cloud provider manages hardware lifecycle, recycling)
- **Software reuse**: Open-source components, GOV.UK Design System (avoid duplicate development)
- **Data retention**: Automated deletion of expired data (reduce storage footprint, GDPR compliance)

**Operational Efficiency**:
- **DevOps automation**: CI/CD pipeline reduces manual effort, faster deployments, fewer errors
- **Infrastructure as Code**: Terraform enables reproducible infrastructure (avoid manual configuration, reduce waste)
- **Monitoring and optimization**: Cost monitoring dashboards identify wasteful spending (over-provisioned resources, unused services)

#### Findings

**HIGH PRIORITY - Finding H-12-01: Sustainability Requirements Missing**:
- **Issue**: No explicit sustainability requirements defined in requirements.md, architecture-principles.md, or project plan. TCoP Point 12 compliance gap.
- **Impact**:
  - TCoP non-compliance at GDS Service Assessment (Point 12 not addressed)
  - Missed opportunity for energy efficiency, carbon footprint reduction, cost savings
  - Reputational risk (UK Government Net Zero commitment, sustainability expectations)
- **Traceability**: NEW FINDING (not identified in analysis-report.md, risk-register.md)
- **Mitigation**:
  - **Add NFR-S-001: Energy Efficiency** - Cloud infrastructure auto-scales during off-peak hours (target 30% reduction in compute resources overnight)
  - **Add NFR-S-002: Carbon Footprint Measurement** - Measure and report cloud carbon footprint (use AWS Customer Carbon Footprint Tool or Azure Sustainability Calculator)
  - **Add NFR-S-003: AI Model Efficiency** - Optimize AI model inference (cache common queries, reduce unnecessary API calls, prompt engineering efficiency, target 20% reduction in API calls vs baseline)
  - **Add DR-006: Sustainability Data Requirements** - Track energy consumption, carbon footprint, resource utilization (monthly reporting to sustainability team)
  - **Add sustainability validation gate**: Include sustainability metrics in GDS Service Assessment preparation (Alpha, Beta, Live)
- **Risk Level**: HIGH (TCoP compliance gap, GDS Service Assessment blocker)
- **Owner**: Cabinet Office CTO / Enterprise Architect / Sustainability Lead
- **Due Date**: 2026-01-31 (Alpha phase, BEFORE GDS Alpha Assessment Month 5)
- **Status**: NOT STARTED (must be added to requirements and architecture principles)

#### Assessment

**STRENGTHS**:
- ✅ Cloud infrastructure enables energy efficiency (auto-scaling, serverless, renewable energy)
- ✅ Carbon neutrality (AWS, Azure committed to carbon neutrality / carbon negative)
- ✅ Circular economy (cloud provider manages hardware lifecycle, software reuse, automated data deletion)
- ✅ Operational efficiency (DevOps automation, IaC, monitoring and optimization)

**GAPS**:
- ⚠️ **HIGH**: No explicit sustainability requirements defined (TCoP Point 12 compliance gap)
- **Mitigation**: Add NFR-S-001 (Energy Efficiency), NFR-S-002 (Carbon Footprint), NFR-S-003 (AI Model Efficiency), DR-006 (Sustainability Data)

**RISKS**:
- **HIGH**: Finding H-12-01 (Sustainability requirements missing) - TCoP non-compliance, GDS Service Assessment blocker
- **NEW RISK**: R-021 (TCoP Point 12 Non-Compliance at GDS Assessment) - Likelihood 3, Impact 3, Score 9 (MEDIUM)

**Critical Path**: Sustainability requirements must be added by Alpha phase (Month 5) BEFORE GDS Alpha Assessment.

**GDS Service Standard Alignment**: Point 13 (Use and contribute to open standards, common components and patterns) - Sustainability is cross-cutting concern

**Recommendation**:
1. Add sustainability requirements (NFR-S-001, NFR-S-002, NFR-S-003, DR-006) to requirements.md by Discovery phase end (Month 2)
2. Measure baseline cloud carbon footprint by Alpha phase (Month 5)
3. Include sustainability metrics in GDS Service Assessment evidence (Alpha, Beta, Live)
4. Appoint sustainability lead (Cabinet Office sustainability team liaison)

---

### Point 13: Meet the Service Standard

**TCoP Requirement**: Ensure your service meets the Digital Service Standard.

**Compliance Status**: ✅ **COMPLIANT**

#### Evidence of Compliance

**GDS Service Standard Alignment** (requirements.md):
- **BR-007**: Technology Code of Practice (TCoP) Compliance - Achieve full compliance with UK Government TCoP 13 points AND pass GDS Service Assessment at Alpha, Beta, and Live phases
- **Success criteria**: TCoP assessment report shows GREEN status on all 13 points, pass GDS Service Assessment at Alpha (Month 5), Beta (Month 11), Live (Month 13)

**GDS Service Assessment Gates** (project plan):
- **Alpha Assessment (Month 5 / Week 20)**: Validate user research, technology choices, prototypes, security architecture (expected pass with 0-2 minor recommendations)
- **Beta Assessment (Month 11 / Week 44)**: Validate Private Beta → Public Beta transition, user satisfaction >4.2/5, NCSC/ICO approvals (expected pass with 0-1 minor recommendation)
- **Live Assessment (Month 13 / Week 56)**: Validate full production readiness, 80% departmental adoption target on track, operational resilience (expected pass, move to Live phase)

**GDS Service Standard 14 Points Coverage**:

| GDS Point | Compliance Status | Evidence |
|-----------|-------------------|----------|
| **1. Understand users and their needs** | ✅ Compliant | User research (20+ interviews), co-design, usability testing (TCoP Point 1) |
| **2. Solve a whole problem for users** | ✅ Compliant | End-to-end AI workflow (upload → summarize → draft → export) |
| **3. Provide a joined up experience** | ✅ Compliant | Microsoft 365, Google Workspace integration (seamless experience) |
| **4. Make the service simple to use** | ✅ Compliant | 5-minute onboarding, GDS Design System, WCAG 2.2 AA (TCoP Point 2) |
| **5. Make sure everyone can use the service** | ✅ Compliant | WCAG 2.2 AA, assisted digital support, accessibility audit (TCoP Point 2) |
| **6. Have a multidisciplinary team** | ✅ Compliant | Product Owner, Tech Lead, UX Lead, Security Lead, QA, DevOps (backlog.md) |
| **7. Use agile ways of working** | ✅ Compliant | 2-week sprints, user stories, backlog grooming, retrospectives (backlog.md) |
| **8. Iterate and improve frequently** | ✅ Compliant | Continuous delivery (CI/CD), quarterly user surveys, feedback loop (FR-010) |
| **9. Create a secure service which protects users' privacy** | ✅ Compliant | NCSC assurance, Cyber Essentials Plus, DPIA, GDPR compliance (TCoP Points 6, 7) |
| **10. Define what success looks like and publish performance data** | ✅ Compliant | User satisfaction >4.2/5, 80% adoption, £60M savings, quarterly reporting |
| **11. Choose the right tools and technology** | ⚠️ Partially Compliant | Vendor evaluation (TCoP Point 11), Finding H-11-01 (vendor selection incomplete) |
| **12. Make new source code open** | ✅ Compliant | GitHub public repositories, open-source components (TCoP Point 3) |
| **13. Use and contribute to open standards, common components and patterns** | ✅ Compliant | OpenAPI, OAuth 2.0, GDS Design System, GOV.UK shared services (TCoP Points 3, 4, 8) |
| **14. Operate a reliable service** | ✅ Compliant | 99.9% uptime SLA, disaster recovery (RTO 4 hours), monitoring (TCoP Point 6) |

**GDS Assessment Preparation** (backlog.md):
- **STORY-067**: GDS Alpha Assessment Preparation (Sprint 5)
  - Compile evidence pack (user research findings, architecture diagrams, security controls, TCoP compliance report)
  - Rehearse assessment presentation with CDDO liaison
  - Address any pre-assessment feedback from CDDO (early engagement)
- **CDDO Liaison**: Monthly liaison calls from Month 1 (early engagement, feedback loop)
- **Assessment pass criteria**: 14/14 points met, 0-2 minor recommendations acceptable

**Service Standard Evidence Pack**:
- **User research**: stakeholder-drivers.md (13 stakeholders, user personas, drivers, concerns)
- **Requirements**: requirements.md (67 requirements, 100% stakeholder traceability)
- **Architecture**: architecture-principles.md (24 principles, TCoP/GDS alignment)
- **Backlog**: backlog.md (42 user stories, 7 epics, 524 story points, 26 sprints)
- **Risk management**: risk-register.md (20 risks, Orange Book compliance, 4Ts framework)
- **Governance**: analysis-report.md (95/100 governance maturity score, 13 findings)
- **TCoP compliance**: tcop-review.md (this document, 11/13 compliant in Discovery, 13/13 target by Live)

#### Assessment

**STRENGTHS**:
- ✅ GDS Service Assessment mandatory (BR-007, non-negotiable)
- ✅ Assessment gates at Alpha, Beta, Live (project plan)
- ✅ 14-point Service Standard coverage (13/14 compliant, 1 partially compliant)
- ✅ CDDO liaison from Month 1 (early engagement, feedback loop)
- ✅ Comprehensive evidence pack (stakeholder drivers, requirements, architecture, backlog, risks, governance, TCoP)
- ✅ Agile delivery (2-week sprints, user stories, CI/CD, retrospectives)
- ✅ User-centered design (user research, co-design, usability testing, feedback loop)

**GAPS**:
- ⚠️ Service Standard Point 11 (Choose the right tools and technology) partially compliant due to TCoP Point 11 vendor evaluation gap (Finding H-11-01)
- **Mitigation**: Complete vendor evaluation Week 1-2 (Sprint 1) to achieve full compliance

**RISKS**:
- R-009 (GDS Service Assessment Failure) - Residual risk 8 (MEDIUM) after CDDO liaison and TCoP compliance
- Finding H-11-01 (Vendor evaluation incomplete) may delay Alpha Assessment pass if not resolved by Sprint 1

**Critical Path**:
- TCoP Point 11 (vendor selection) must be completed by Sprint 1 for Service Standard Point 11 compliance
- TCoP Point 12 (sustainability requirements) must be added by Alpha phase for Service Standard evidence

**GDS Service Standard Alignment**: This document provides TCoP compliance evidence for Service Standard Point 13 (Use and contribute to open standards, common components and patterns).

---

## Summary of Findings

### Critical Issues (0 findings)

None identified.

### High Priority Issues (2 findings)

1. **Finding H-11-01**: Vendor Evaluation Incomplete (TCoP Point 11)
   - **Issue**: Cloud provider and AI vendor selection must be completed Week 1-2 to avoid infrastructure deployment delay
   - **Impact**: Timeline slip risk (Private Beta delay), budget risk (rushed vendor selection)
   - **Owner**: Cabinet Office CTO / Procurement Lead
   - **Due Date**: 2025-11-15 (Week 2, Sprint 1)
   - **Status**: NOT STARTED (CRITICAL PATH)

2. **Finding H-12-01**: Sustainability Requirements Missing (TCoP Point 12)
   - **Issue**: No explicit sustainability requirements defined (energy efficiency, carbon footprint, AI model optimization)
   - **Impact**: TCoP non-compliance at GDS Service Assessment, missed efficiency opportunities
   - **Owner**: Cabinet Office CTO / Enterprise Architect
   - **Due Date**: 2026-01-31 (Alpha phase, BEFORE GDS Alpha Assessment)
   - **Status**: NOT STARTED

### Medium Priority Issues (3 findings)

3. **Finding M-2-01**: Welsh Language Support Deferred (TCoP Point 2)
   - **Issue**: Welsh Language Act 1993 compliance deferred to Public Beta due to AI model limitations
   - **Impact**: Legal compliance risk for Welsh Government departments
   - **Owner**: Product Owner / Welsh Language Board
   - **Due Date**: 2026-04-30 (Public Beta)
   - **Status**: TOLERATED (accepted risk)

4. **Finding L-001**: API Versioning Strategy Detail Gap (TCoP Point 9)
   - **Issue**: API versioning mentioned in principles but not detailed in requirements
   - **Impact**: Risk of breaking API changes, downstream integration failures
   - **Owner**: Tech Lead / API Architect
   - **Due Date**: 2026-01-15 (Alpha)
   - **Status**: NOT STARTED

5. **Finding M-001**: Test Coverage Metrics Undefined (TCoP Point 10)
   - **Issue**: Test coverage thresholds in backlog DoD but not in NFRs
   - **Impact**: Quality risk, inconsistent test coverage
   - **Owner**: Tech Lead / QA Lead
   - **Due Date**: 2025-12-31 (Discovery)
   - **Status**: NOT STARTED

### Low Priority Issues (1 finding)

6. **Finding L-002**: Vendor Performance SLA Monitoring (TCoP Point 11)
   - **Issue**: Vendor SLA monitoring mentioned in risks but not detailed in requirements
   - **Impact**: Vendor underperformance may go undetected
   - **Owner**: Vendor Manager / Operations Lead
   - **Due Date**: 2026-03-31 (Sprint 8)
   - **Status**: NOT STARTED

---

## Risk Summary

### TCoP-Related Risks from Risk Register

| Risk ID | Title | TCoP Point | Inherent | Residual | Status |
|---------|-------|------------|----------|----------|--------|
| **R-001** | Cross-Tenant Data Leak | Point 6 (Security) | 20 (CRITICAL) | 12 (HIGH) | IN PROGRESS |
| **R-004** | NCSC Assurance Delay | Point 6 (Security) | 16 (HIGH) | 12 (HIGH) | IN PROGRESS |
| **R-006** | Vendor UK Data Residency Failure | Point 11 (Purchasing) | 12 (MEDIUM) | 9 (MEDIUM) | IN PROGRESS |
| **R-007** | AI Bias Incident | Point 7 (Privacy) | 20 (CRITICAL) | 15 (HIGH) | IN PROGRESS |
| **R-008** | ICO DPIA Rejection | Point 7 (Privacy) | 12 (MEDIUM) | 10 (MEDIUM) | IN PROGRESS |
| **R-009** | GDS Assessment Failure | Point 13 (Service Standard) | 12 (MEDIUM) | 8 (MEDIUM) | IN PROGRESS |
| **R-010** | Cloud/AI Cost Overruns | Point 11 (Purchasing) | 15 (HIGH) | 9 (MEDIUM) | IN PROGRESS |
| **R-012** | Vendor Lock-In | Point 11 (Purchasing) | 12 (MEDIUM) | 9 (MEDIUM) | IN PROGRESS |

**Overall Risk Assessment**:
- **HIGH** risks require active treatment before Private Beta (R-001, R-004, R-007)
- **MEDIUM** risks have mitigation plans in place (R-006, R-008, R-009, R-010, R-012)
- TCoP compliance risks are manageable with planned controls and early regulator engagement

---

## Recommendations

### Immediate Actions (Next 2 Weeks)

1. **CRITICAL - Week 1-2: Complete Vendor Evaluation** (Finding H-11-01)
   - Run parallel AWS/Azure proofs-of-concept (Week 1)
   - Pre-negotiate UK data residency contracts with legal team (Week 1)
   - Cabinet Office CTO approval of vendor selection scorecard (Week 2)
   - Sign cloud provider and AI vendor contracts by 2025-11-15 (Week 2)
   - **Owner**: Cabinet Office CTO / Procurement Lead
   - **Impact**: Unblocks infrastructure deployment (STORY-057), avoids timeline slip

2. **HIGH - Week 3: NCSC Security Architecture Workshop** (Risk R-001, R-004)
   - Full-day workshop with NCSC + Security Lead + Tech Lead + Cloud Architect
   - Review multi-tenant design BEFORE Sprint 1 implementation
   - **Owner**: Cabinet Office CTO / NCSC Liaison
   - **Impact**: Early NCSC feedback, avoid Month 6 critical findings

3. **HIGH - Week 2: Establish Weekly Steering Committee** (All risks)
   - Weekly risk review: Permanent Secretary, CTO, CDDO Director, NCSC liaison
   - Escalation criteria: Any Critical risk, any risk +5 points increase, new High risks
   - **Owner**: Programme Manager
   - **Impact**: Governance oversight, rapid decision-making

### Short-Term Actions (Next 4 Weeks)

4. **HIGH - Discovery Phase: Add Sustainability Requirements** (Finding H-12-01)
   - Add NFR-S-001 (Energy Efficiency), NFR-S-002 (Carbon Footprint), NFR-S-003 (AI Model Efficiency), DR-006 (Sustainability Data)
   - Appoint sustainability lead (Cabinet Office sustainability team liaison)
   - Measure baseline cloud carbon footprint
   - **Owner**: Cabinet Office CTO / Enterprise Architect
   - **Due Date**: 2026-01-31 (Alpha phase)
   - **Impact**: TCoP Point 12 compliance, GDS Service Assessment readiness

5. **MEDIUM - Sprint 1-2: Implement Multi-Tenant Isolation Controls** (Risk R-001)
   - Database Row-Level Security (RLS) - Sprint 1
   - Application-level tenant validation - Sprint 2
   - Automated boundary tests in CI/CD - Sprint 2
   - **Owner**: Security Lead / Tech Lead
   - **Impact**: Reduce cross-tenant data leak risk (20 → 12)

6. **MEDIUM - Discovery Phase: User Research with Pilot Departments** (Risk R-002)
   - 20+ user interviews with Policy Advisors and Civil Servants (Home Office, HMRC, DHSC)
   - Validate use cases, test prototypes
   - **Owner**: Product Owner / UX Lead
   - **Due Date**: 2025-12-31 (End of Discovery)
   - **Impact**: Reduce low user adoption risk (16 → 12)

### Medium-Term Actions (Next 3 Months)

7. **MEDIUM - Alpha Phase: Document API Versioning Strategy** (Finding L-001)
   - Semantic versioning policy (v1.0.0, major.minor.patch)
   - 12-month backward compatibility guarantee
   - 6-month deprecation notice for breaking changes
   - **Owner**: Tech Lead / API Architect
   - **Due Date**: 2026-01-15 (Alpha)

8. **MEDIUM - Discovery Phase: Add Test Coverage NFR** (Finding M-001)
   - NFR-Q-001: Automated test coverage (unit >70%, integration >60%, E2E critical paths 100%)
   - CI/CD enforcement (build fails if coverage below threshold)
   - **Owner**: Tech Lead / QA Lead
   - **Due Date**: 2025-12-31 (Discovery)

9. **MEDIUM - Month 3-5: ICO DPIA Preparation** (Risk R-008)
   - Early ICO engagement (Month 3)
   - DPIA documentation and submission (Sprint 5)
   - Target ICO approval by Month 6 (Private Beta gate)
   - **Owner**: ICO CTO / Data Protection Officer

10. **MEDIUM - Sprint 8: Add Vendor SLA Monitoring** (Finding L-002)
    - NFR-O-001: Vendor SLA monitoring dashboards (uptime, latency, support)
    - Quarterly vendor review meetings
    - **Owner**: Vendor Manager / Operations Lead
    - **Due Date**: 2026-03-31 (Sprint 8)

### Long-Term Actions (Next 6-12 Months)

11. **MEDIUM - Public Beta: Welsh Language Support** (Finding M-2-01)
    - Add Welsh language AI model or human translation fallback
    - Welsh Language Board stakeholder engagement
    - **Owner**: Product Owner / Welsh Language Board
    - **Due Date**: 2026-04-30 (Public Beta)

12. **HIGH - Month 6: NCSC Secure by Design Assurance** (Risk R-004)
    - NCSC Month 6 security review
    - Private Beta launch BLOCKED until NCSC approval
    - **Owner**: NCSC Lead Architect / Cabinet Office CTO
    - **Target**: Zero critical/high findings, conditional launch if minor issues

13. **HIGH - Month 6: ICO DPIA Approval** (Risk R-008)
    - ICO DPIA approval required for Private Beta launch
    - **Owner**: ICO CTO / Data Protection Officer
    - **Target**: DPIA approved with 0-2 minor recommendations

---

## Phase Gate Recommendations

### Discovery Phase Gate (Month 2 / Week 8)

**Proceed to Alpha**: ✅ **YES** with conditions

**Conditions**:
1. ✅ Complete vendor evaluation (cloud provider, AI vendor) by Week 2 (Finding H-11-01)
2. ✅ Add sustainability requirements (NFR-S-001, NFR-S-002, NFR-S-003) by end of Discovery (Finding H-12-01)
3. ✅ NCSC security architecture review Week 3 (Risk R-001, R-004)
4. ✅ Add test coverage NFR by end of Discovery (Finding M-001)

**TCoP Compliance at Discovery**: **11/13 COMPLIANT** (85%)
- Points 11, 12 partially compliant (vendor evaluation, sustainability)
- Target: 13/13 compliant by Alpha phase

### Alpha Phase Gate (Month 5 / Week 20)

**GDS Alpha Assessment**: Expected **PASS** with 0-2 minor recommendations

**Prerequisites**:
1. ✅ User research completed (20+ interviews, usability testing with 50+ users)
2. ✅ Security architecture validated (NCSC early feedback, no critical findings)
3. ✅ TCoP compliance evidence pack (13/13 points compliant)
4. ✅ API versioning strategy documented (Finding L-001)
5. ✅ Sustainability requirements baseline measured (Finding H-12-01)

**TCoP Compliance at Alpha**: **13/13 COMPLIANT** (100% target)

### Private Beta Phase Gate (Month 6 / Week 26)

**Proceed to Private Beta**: ⚠️ **CONDITIONAL** (NCSC + ICO approval required)

**Gate Blockers**:
1. ⛔ NCSC Secure by Design assurance (Risk R-004) - MUST PASS (no critical/high findings)
2. ⛔ ICO DPIA approval (Risk R-008) - MUST PASS (approved or conditional approval acceptable)
3. ⛔ Cyber Essentials Plus certification - MUST OBTAIN
4. ⛔ Zero cross-tenant data leaks in penetration testing (Risk R-001)

**TCoP Compliance at Private Beta**: **13/13 COMPLIANT** (100%)

### Public Beta Phase Gate (Month 11 / Week 44)

**GDS Beta Assessment**: Expected **PASS** with 0-1 minor recommendation

**Prerequisites**:
1. ✅ User satisfaction >4.2/5 (target achieved in Private Beta)
2. ✅ 200+ Monthly Active Users (Private Beta adoption validated)
3. ✅ Welsh language support implemented (Finding M-2-01)
4. ✅ No security incidents in Private Beta (zero cross-tenant leaks)

**TCoP Compliance at Public Beta**: **13/13 COMPLIANT** (100%)

### Live Phase Gate (Month 13 / Week 56)

**GDS Live Assessment**: Expected **PASS** (move to Live)

**Prerequisites**:
1. ✅ 80% departmental adoption target on track (16+ departments committed)
2. ✅ User satisfaction >4.2/5 (sustained throughout Public Beta)
3. ✅ 99.9% uptime SLA achieved (operational resilience validated)
4. ✅ ATRS published on GOV.UK (algorithmic transparency requirement)
5. ✅ All TCoP points 13/13 compliant (validated at Live Assessment)

**TCoP Compliance at Live**: **13/13 COMPLIANT** (100%)

---

## Appendix A: TCoP Compliance Scorecard

| TCoP Point | Weight | Discovery | Alpha | Private Beta | Public Beta | Live | Target |
|------------|--------|-----------|-------|--------------|-------------|------|--------|
| **1. Define user needs** | 10% | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **2. Make things accessible** | 8% | ✅ 8/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **3. Be open and use open source** | 6% | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **4. Make use of open standards** | 6% | ✅ 9/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **5. Use cloud first** | 8% | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **6. Make things secure** | 12% | ✅ 8/10 | ✅ 9/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **7. Make privacy integral** | 10% | ✅ 8/10 | ✅ 9/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **8. Share, reuse, collaborate** | 6% | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **9. Integrate and adapt** | 6% | ✅ 9/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **10. Make better use of data** | 6% | ✅ 9/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **11. Define purchasing strategy** | 8% | ⚠️ 5/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **12. Make technology sustainable** | 6% | ⚠️ 5/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **13. Meet the Service Standard** | 8% | ✅ 8/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | ✅ 10/10 | 10/10 |
| **TOTAL SCORE** | 100% | **85%** | **98%** | **100%** | **100%** | **100%** | **100%** |

**Key**:
- ✅ **Compliant** (8-10/10): Evidence of compliance, controls in place, minor gaps acceptable
- ⚠️ **Partially Compliant** (5-7/10): Some evidence, significant gaps require mitigation
- ❌ **Non-Compliant** (0-4/10): No evidence, critical gaps, gate blocker

**Phase Progression**:
- **Discovery (85%)**: 11/13 points compliant, 2 partially compliant (Points 11, 12)
- **Alpha (98%)**: 13/13 points compliant, minor gaps in security/privacy (Points 6, 7)
- **Private Beta (100%)**: Full TCoP compliance after NCSC/ICO approvals
- **Public Beta (100%)**: Sustained compliance, Welsh language added
- **Live (100%)**: Full compliance validated at GDS Live Assessment

---

## Appendix B: Evidence Map

This appendix maps TCoP requirements to project evidence (requirements, architecture, backlog, risks).

| TCoP Point | Evidence Files | Key Requirements | User Stories | Risks |
|------------|----------------|------------------|--------------|-------|
| **Point 1** | stakeholder-drivers.md, backlog.md | BR-002, FR-010 | STORY-004 (onboarding), STORY-031 (feedback) | R-002 (low adoption) |
| **Point 2** | architecture-principles.md (Principle 6), requirements.md | NFR-A-002 (WCAG 2.2 AA) | STORY-004 (tutorial), Backlog DoD (accessibility) | R-018 (Welsh language) |
| **Point 3** | architecture-principles.md (Principle 3) | N/A (principle-based) | N/A (technology choices) | R-012 (vendor lock-in) |
| **Point 4** | architecture-principles.md (Principle 2), requirements.md | INT-001, INT-002, INT-003 (OAuth 2.0) | STORY-045 (Microsoft Graph), STORY-049 (Google Drive) | R-017 (integration failures) |
| **Point 5** | architecture-principles.md (Principle 1), requirements.md | BR-006 (UK data residency), INT-004 | STORY-056 (cloud provider), STORY-057 (infrastructure) | R-010 (cloud costs), R-012 (lock-in) |
| **Point 6** | architecture-principles.md (Principle 4), requirements.md, risk-register.md | NFR-SEC-001 through NFR-SEC-006, BR-003 | STORY-009 (RLS), STORY-010 (app validation), STORY-014 (pen testing) | R-001 (cross-tenant leak), R-004 (NCSC assurance) |
| **Point 7** | architecture-principles.md (Principle 5), requirements.md | NFR-C-001 (GDPR), FR-005 (audit logging) | STORY-064 (data subject rights), STORY-065 (consent), STORY-066 (DPIA) | R-007 (AI bias), R-008 (ICO DPIA) |
| **Point 8** | architecture-principles.md (Principle 3), stakeholder-drivers.md | BR-001 (cost savings £60M), Goal G-1 | N/A (centralized platform) | R-002 (low adoption) |
| **Point 9** | architecture-principles.md (Principle 2, 16), requirements.md | INT-001, INT-002, INT-003, INT-005 | STORY-045 through STORY-052 (integrations) | R-017 (integration failures), R-019 (API rate limits) |
| **Point 10** | architecture-principles.md (Principle 14), requirements.md | FR-014 (usage analytics), DR-001 through DR-005 | STORY-054 (analytics), STORY-055 (chargeback) | N/A |
| **Point 11** | architecture-principles.md (Principle 3), backlog.md, risk-register.md | BR-006 (UK contracts), BR-001 (cost model) | STORY-056 (cloud provider), STORY-051 (AI vendor) | R-006 (vendor data residency), R-010 (costs), R-012 (lock-in) |
| **Point 12** | (NEW - Finding H-12-01) | (NFR-S-001, NFR-S-002, NFR-S-003 to be added) | (Sustainability stories to be added) | (R-021 new risk - TCoP Point 12 non-compliance) |
| **Point 13** | requirements.md, backlog.md, project-plan.md | BR-007 (TCoP compliance), GDS assessment gates | STORY-067 (GDS Alpha prep) | R-009 (GDS assessment failure) |

---

## Appendix C: Next Steps and Action Owners

| Action | Owner | Due Date | Status | Priority |
|--------|-------|----------|--------|----------|
| **Complete vendor evaluation (cloud provider, AI vendor)** | Cabinet Office CTO / Procurement Lead | 2025-11-15 (Week 2) | NOT STARTED | 🔴 CRITICAL |
| **NCSC security architecture workshop** | Cabinet Office CTO / NCSC Liaison | 2025-11-08 (Week 3) | NOT STARTED | 🔴 CRITICAL |
| **Establish weekly steering committee** | Programme Manager | 2025-11-08 (Week 2) | NOT STARTED | 🔴 CRITICAL |
| **Add sustainability requirements (NFR-S-001, NFR-S-002, NFR-S-003)** | Cabinet Office CTO / Enterprise Architect | 2026-01-31 (Alpha) | NOT STARTED | 🟠 HIGH |
| **Implement database Row-Level Security (RLS)** | Security Lead / Tech Lead | 2025-11-30 (Sprint 1) | NOT STARTED | 🟠 HIGH |
| **User research (20+ interviews with pilot departments)** | Product Owner / UX Lead | 2025-12-31 (Discovery) | NOT STARTED | 🟠 HIGH |
| **Add test coverage NFR (unit >70%, integration >60%, E2E 100%)** | Tech Lead / QA Lead | 2025-12-31 (Discovery) | NOT STARTED | 🟡 MEDIUM |
| **Document API versioning strategy** | Tech Lead / API Architect | 2026-01-15 (Alpha) | NOT STARTED | 🟡 MEDIUM |
| **ICO DPIA preparation and submission** | ICO CTO / Data Protection Officer | 2026-03-15 (Sprint 5) | NOT STARTED | 🟠 HIGH |
| **Add vendor SLA monitoring (NFR-O-001)** | Vendor Manager / Operations Lead | 2026-03-31 (Sprint 8) | NOT STARTED | 🟡 MEDIUM |
| **Welsh language support implementation** | Product Owner / Welsh Language Board | 2026-04-30 (Public Beta) | NOT STARTED | 🟡 MEDIUM |
| **NCSC Secure by Design assurance (Month 6 review)** | NCSC Lead Architect / Cabinet Office CTO | 2026-05-31 (Month 6) | NOT STARTED | 🔴 CRITICAL |
| **ICO DPIA approval (Private Beta gate blocker)** | ICO CTO / Data Protection Officer | 2026-05-31 (Month 6) | NOT STARTED | 🔴 CRITICAL |
| **GDS Alpha Assessment** | CDDO Director / GDS Assessor | 2026-03-31 (Month 5) | NOT STARTED | 🟠 HIGH |
| **GDS Beta Assessment** | CDDO Director / GDS Assessor | 2026-09-30 (Month 11) | NOT STARTED | 🟠 HIGH |
| **GDS Live Assessment** | CDDO Director / GDS Assessor | 2026-11-30 (Month 13) | NOT STARTED | 🟠 HIGH |

---

**END OF TCOP REVIEW**

---

**Document Metadata**:
- **Generated by**: ArcKit `/arckit.tcop` command
- **Generated on**: 2026-01-26
- **ArcKit Version**: 0.11.2
- **Project**: Cabinet Office GenAI Platform (Project 001)
- **AI Model**: claude-opus-4-5-20251101
- **Framework**: UK Government Technology Code of Practice (TCoP) 13 Points
- **Source Artifacts**:
  - `requirements.md` (67 requirements: 7 BRs, 15 FRs, 35 NFRs, 5 INTs, 5 DRs)
  - `architecture-principles.md` (24 principles with TCoP/GDS/NCSC/AI Playbook alignment)
  - `stakeholder-drivers.md` (13 stakeholders, RACI matrix, conflict analysis)
  - `backlog.md` (42 user stories, 7 epics, 524 story points, 26 sprints)
  - `risk-register.md` (20 risks, Orange Book compliance, 4Ts framework)
  - `analysis-report.md` (95/100 governance maturity, 13 findings)

**TCoP Compliance Summary**:
- **Discovery Phase**: 11/13 points compliant (85%)
- **Alpha Phase**: 13/13 points compliant (98%)
- **Private Beta Phase**: 13/13 points compliant (100%) - After NCSC/ICO approvals
- **Live Phase**: 13/13 points compliant (100%) - Validated at GDS Live Assessment

**Critical Path Actions**:
1. Complete vendor evaluation Week 1-2 (Finding H-11-01)
2. NCSC security architecture workshop Week 3 (Risk R-001, R-004)
3. Add sustainability requirements by Alpha (Finding H-12-01)
4. NCSC assurance Month 6 (Private Beta gate blocker)
5. ICO DPIA approval Month 6 (Private Beta gate blocker)
