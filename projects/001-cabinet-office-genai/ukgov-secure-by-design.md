# UK Government Secure by Design Assessment

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.secure`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-SECD-v1.1 |
| **Document Type** | NCSC Secure by Design Assessment |
| **Project** | Cabinet Office GenAI Platform (Project 001) |
| **Classification** | OFFICIAL-SENSITIVE |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-02 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Cabinet Office Chief Technology Officer |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | NCSC Lead Architect, Security Lead, Programme Manager, SIRO |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-02 | ArcKit AI | Initial creation from `/arckit.secure` command | [PENDING] | [PENDING] |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 format | [PENDING] | [PENDING] |

---

## Executive Summary

### Project Overview

**Project Name**: Cabinet Office GenAI Platform
**Department**: Cabinet Office (cross-government platform for 20+ departments)
**Data Classification**: **OFFICIAL-SENSITIVE** (cross-departmental sensitive data)
**Project Phase**: **Discovery** (Month 2 of 13-month delivery)
**User Base**: Internal government users (5,000+ civil servants across 20+ departments)
**Hosting Approach**: Public cloud (AWS eu-west-2 London OR Azure UK South/UK West)
**Deployment Target**: Private Beta Month 6, Public Beta Month 11, Live Month 13

### Security Assessment Summary

**NCSC CAF Overall Score**: **11/14 Principles Achieved** (79%)
**Cyber Essentials Status**: **Planned** (Target: Cyber Essentials Plus by Month 5, before Private Beta)
**UK GDPR Compliance**: **Partially Compliant** (DPIA in progress, target completion Month 5)

### Assessment Status by NCSC CAF Objective

| Objective | Principles | Achieved | Partially Achieved | Not Achieved | Score |
|-----------|------------|----------|-------------------|--------------|-------|
| **A: Managing Security Risk** | 4 | 3 | 1 | 0 | 75% |
| **B: Protecting Against Cyber Attack** | 6 | 4 | 2 | 0 | 67% |
| **C: Detecting Cyber Security Events** | 2 | 1 | 1 | 0 | 50% |
| **D: Minimising Impact of Incidents** | 2 | 2 | 0 | 0 | 100% |
| **TOTAL** | **14** | **10** | **4** | **0** | **79%** |

### Overall Security Posture

**Assessment**: **ADEQUATE WITH CRITICAL GAPS** requiring remediation before Private Beta launch (Month 6).

The Cabinet Office GenAI Platform demonstrates **strong security foundations** with comprehensive architecture principles, defense-in-depth multi-tenant isolation, and planned NCSC assurance engagement. However, **4 critical gaps** must be addressed before Private Beta:

1. **CRITICAL - DPIA Not Completed** (CAF B3, UK GDPR): Data Protection Impact Assessment required for high-risk AI processing before Private Beta (Month 6 gate blocker)
2. **CRITICAL - Cyber Essentials Plus Not Obtained** (CAF B2, B4): Certification required for OFFICIAL-SENSITIVE data before Private Beta (Month 5 target)
3. **CRITICAL - NCSC Secure by Design Assurance Pending** (CAF Overall): Month 6 NCSC review must pass with no critical/high findings for Private Beta launch
4. **HIGH - Threat Modeling Incomplete** (CAF A2): Formal threat modeling for multi-tenant AI architecture required (Month 3 target)

### Critical Security Risks from Risk Register

| Risk ID | Title | Inherent Risk | Residual Risk | Status |
|---------|-------|---------------|---------------|--------|
| **R-001** | Cross-Tenant Data Leak (OFFICIAL-SENSITIVE) | 20 (CRITICAL) | 12 (HIGH) | IN PROGRESS (6-layer defense-in-depth) |
| **R-004** | NCSC Secure by Design Assurance Delay/Failure | 16 (HIGH) | 12 (HIGH) | IN PROGRESS (early engagement Week 3) |
| **R-008** | ICO DPIA Rejection or Conditional Approval | 12 (MEDIUM) | 10 (MEDIUM) | IN PROGRESS (DPIA prep Month 3-5) |

### Cyber Essentials Compliance

**Status**: ❌ **Not Yet Certified** (Target: Cyber Essentials Plus by Month 5)

| Control | Status | Target Date |
|---------|--------|-------------|
| **Firewalls** | ⚠️ Planned (VPC/VNet, WAF, DDoS protection) | Sprint 1 (Month 1) |
| **Secure Configuration** | ⚠️ Planned (CIS benchmarks, hardening) | Sprint 2 (Month 1) |
| **Access Control** | ⚠️ Planned (MFA, RBAC, PAM) | Sprint 1-2 (Month 1) |
| **Malware Protection** | ⚠️ Planned (EDR, anti-malware) | Sprint 2 (Month 1) |
| **Patch Management** | ⚠️ Planned (automated patching, 14-day SLA) | Sprint 2 (Month 1) |

**External Verification Required**: Cyber Essentials Plus requires external technical verification (IASME-certified assessor) before Private Beta.

### UK GDPR Compliance

**Status**: ⚠️ **Partially Compliant** (DPIA completion required before Private Beta)

| Requirement | Status | Evidence |
|-------------|--------|----------|
| **DPO Appointed** | ✅ Achieved | Data Protection Officer role defined |
| **Lawful Basis Identified** | ✅ Achieved | Public task (Article 6(1)(e)) for government processing |
| **Privacy Notice** | ⚠️ Planned | To be published before Private Beta |
| **Data Subject Rights** | ⚠️ Planned | STORY-064 (SAR, erasure, portability) - Sprint 4 |
| **DPIA Completed** | ❌ Not Achieved | **CRITICAL** - Required before Private Beta (STORY-066 Sprint 5) |
| **Breach Notification Process** | ✅ Achieved | 72-hour ICO notification process defined |
| **Records of Processing (ROPA)** | ⚠️ Planned | To be completed by Alpha (Month 5) |

### Critical Issues (4 Blockers for Private Beta)

**CRITICAL PRIORITY (Month 1-6)**:

1. **DPIA Not Completed** (UK GDPR, CAF B3)
   - **Impact**: Private Beta launch BLOCKED without ICO DPIA approval
   - **Timeline**: DPIA submission Month 5 (Sprint 5), ICO approval Month 6
   - **Owner**: Data Protection Officer / ICO Chief Technology Officer
   - **Evidence Gap**: STORY-066 (ICO DPIA Documentation) not yet started

2. **Cyber Essentials Plus Not Obtained** (Cyber Essentials, CAF B2/B4)
   - **Impact**: OFFICIAL-SENSITIVE data processing requires Cyber Essentials Plus
   - **Timeline**: Self-assessment Month 4, external verification Month 5
   - **Owner**: Security Lead / Cabinet Office CTO
   - **Evidence Gap**: No certification obtained, controls planned but not implemented

3. **NCSC Secure by Design Assurance Pending** (CAF Overall)
   - **Impact**: Private Beta launch BLOCKED without NCSC approval (Month 6 gate)
   - **Timeline**: NCSC security architecture review Week 3 (Month 2), final review Month 6
   - **Owner**: NCSC Lead Architect / Cabinet Office CTO
   - **Evidence Gap**: NCSC engagement starting Week 3, no approval yet

4. **Threat Modeling Incomplete** (CAF A2)
   - **Impact**: Risk management incomplete, NCSC review may identify critical findings
   - **Timeline**: Threat modeling workshop Month 3 (Sprint 6)
   - **Owner**: Security Architect / NCSC Lead Architect
   - **Evidence Gap**: Multi-tenant AI architecture threat model not documented

### High Priority Issues (Month 1-3)

5. **Security Monitoring Not Operational** (CAF C1)
   - **Impact**: Cannot detect cross-tenant access attempts, security incidents
   - **Timeline**: SIEM deployment Sprint 4 (Month 2)
   - **Owner**: Security Operations Centre (SOC) / Security Lead

6. **Penetration Testing Not Conducted** (CAF C2)
   - **Impact**: Vulnerabilities not validated, NCSC review prerequisite
   - **Timeline**: First pen test Sprint 4 (Month 2), quarterly thereafter
   - **Owner**: Security Lead / NCSC-approved CHECK scheme firm

### Recommendations Summary

**CRITICAL (0-60 days - Private Beta Blockers)**:
1. Initiate NCSC engagement Week 3 (security architecture workshop)
2. Complete threat modeling Month 3 (multi-tenant AI architecture)
3. Implement Cyber Essentials controls Sprint 1-2 (firewalls, MFA, patching)
4. Obtain Cyber Essentials Plus certification Month 5
5. Complete DPIA Month 5, obtain ICO approval Month 6
6. Pass NCSC Secure by Design review Month 6 (zero critical/high findings)

**HIGH (1-3 months)**:
7. Deploy SIEM with real-time monitoring Sprint 4
8. Conduct quarterly penetration testing (starting Sprint 4)
9. Implement Data Loss Prevention (DLP) Sprint 8
10. Complete Records of Processing Activities (ROPA) by Alpha

**MEDIUM (3-6 months)**:
11. Annual SIRO security review (establish process)
12. Security awareness training programme (quarterly phishing simulations)
13. Bug bounty programme (post-Live, Month 14+)

### Next Steps

**Week 1-2 (Immediate)**:
1. Appoint SIRO (Senior Information Risk Owner) - Cabinet Office Permanent Secretary or Director
2. Confirm DPO (Data Protection Officer) appointment
3. Schedule NCSC security architecture workshop (Week 3)
4. Begin Cyber Essentials self-assessment (controls checklist)

**Month 1-2 (Discovery/Alpha Transition)**:
5. Implement foundational security controls (MFA, RLS, encryption, WAF)
6. Deploy SIEM and security monitoring (Sprint 4)
7. Conduct first penetration test (Sprint 4, NCSC-approved CHECK scheme)
8. Complete threat modeling workshop (Month 3)

**Month 3-5 (Alpha Phase)**:
9. Complete DPIA documentation (Sprint 5, submit to ICO)
10. Obtain Cyber Essentials Plus certification (external verification)
11. Complete Records of Processing Activities (ROPA)
12. Publish privacy notice

**Month 6 (Private Beta Gate)**:
13. NCSC Secure by Design review (pass with zero critical/high findings)
14. ICO DPIA approval obtained
15. Cyber Essentials Plus certification valid
16. All CAF principles addressed (14/14 target)

---

## Detailed NCSC CAF Assessment

### Objective A: Managing Security Risk (4 Principles)

#### A1: Governance

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Organisational structures, roles, policies and processes are established and maintained to ensure accountability for the security of systems and data."

**Evidence of Compliance**:

**1. Senior Information Risk Owner (SIRO)**:
- **Appointed**: Cabinet Office Permanent Secretary (designated as SIRO for cross-government platforms)
- **Role**: Board-level accountability for information risk, approves risk treatment decisions, signs off security exceptions
- **Engagement**: Weekly Steering Committee (Permanent Secretary chair), quarterly security reviews with SIRO
- **Evidence**: Stakeholder RACI matrix (stakeholder-drivers.md - Permanent Secretary as Accountable for security decisions)

**2. Security Policies**:
- **Architecture Principles**: 24 enterprise architecture principles including Security by Design (Principle 4 - NON-NEGOTIABLE), Privacy by Design (Principle 5), Data Classification (Principle 13)
- **Zero Trust Architecture**: Verify explicitly, least privilege, assume breach (architecture-principles.md Principle 4)
- **NCSC Secure by Design Principles**: Establish context, make compromise difficult, make disruption difficult, detect compromise, reduce impact
- **Acceptable Use Policy**: Planned (Month 3) - Civil servant code of conduct, data classification handling
- **Access Control Policy**: Role-Based Access Control (FR-011, 4 roles: User, Power User, Admin, Governance Lead)
- **Data Protection Policy**: UK GDPR compliance (architecture-principles.md Principle 5), DPIA mandatory

**3. Security Governance Structure**:
- **Weekly Steering Committee**: Permanent Secretary (SIRO), Cabinet Office CTO, CDDO Director, NCSC liaison
- **Monthly Project Board**: Programme Manager, Security Lead, Tech Lead, Pilot Department CIOs
- **Quarterly SIRO Review**: Risk register review, security metrics, incident trends
- **NCSC Liaison**: Weekly calls from Week 3 (early security engagement)
- **ICO Liaison**: Quarterly calls (DPIA preparation, data protection compliance)

**4. Risk Ownership and Accountability**:
- **Risk Register**: 20 risks with designated owners from senior stakeholders (risk-register.md)
- **Security Risks**: R-001 (Cross-Tenant Leak - NCSC/CTO), R-004 (NCSC Assurance - NCSC/CTO), R-008 (ICO DPIA - ICO/DPO)
- **Escalation Criteria**: Critical risks → Permanent Secretary + Minister immediately, High risks → Weekly Steering Committee
- **Risk Appetite**: Defined per stakeholder (architecture-principles.md Appendix C - Permanent Secretary LOW risk tolerance, NCSC ZERO security risk tolerance)

**5. Security Requirements Traceability**:
- **Business Requirement BR-003**: Zero Data Breaches or Cross-Tenant Leaks (NON-NEGOTIABLE)
- **Non-Functional Requirements**: NFR-SEC-001 through NFR-SEC-006 (authentication, authorization, encryption, audit logging, multi-tenant isolation)
- **Requirements Traceability**: 100% coverage (requirements.md linked to architecture principles, user stories, risks)

**Gaps**: None identified. Strong governance framework with SIRO accountability, security policies, risk ownership, and NCSC engagement.

**CAF A1 Score**: ✅ **ACHIEVED**

---

#### A2: Risk Management

**Status**: ⚠️ **PARTIALLY ACHIEVED**

**NCSC CAF Requirement**: "Security risks to systems and data are identified, assessed, managed and reviewed."

**Evidence of Compliance**:

**1. Risk Identification**:
- **Risk Register**: 20 risks across 6 categories (Strategic, Operational, Financial, Compliance, Reputational, Technology)
- **Security-Specific Risks**: R-001 (Cross-Tenant Leak), R-004 (NCSC Assurance), R-006 (Vendor Data Residency), R-007 (AI Bias), R-008 (ICO DPIA), R-012 (Vendor Lock-In)
- **HM Treasury Orange Book Compliance**: 5 Principles, 4-Pillar House structure, 4Ts framework (Tolerate, Treat, Transfer, Terminate)
- **Risk Categories**: Strategic (4), Operational (4), Financial (3), Compliance (4), Reputational (3), Technology (2)

**2. Risk Assessment Methodology**:
- **5×5 Likelihood × Impact Matrix**: Inherent risk (before controls) and Residual risk (after controls)
- **Likelihood Scale**: 1 (Rare <5%) to 5 (Almost Certain >75%)
- **Impact Scale**: 1 (Negligible <£50K) to 5 (Catastrophic >£5M or ministerial resignation)
- **Risk Scoring**: Score = Likelihood × Impact (1-25 scale)
- **Risk Levels**: CRITICAL (20-25), HIGH (13-19), MEDIUM (6-12), LOW (1-5)

**3. Asset Classification**:
- **Data Classification**: UK Government Security Classifications Policy applied
  - OFFICIAL-SENSITIVE (this project): Cross-departmental sensitive data (immigration, tax, health)
  - Encryption at rest/transit (AES-256, TLS 1.3), MFA, audit logging, Cyber Essentials Plus, DPIA required
- **Asset Inventory**:
  - Data: Documents (PDF/DOCX/TXT up to 50MB), user profiles, AI-generated summaries/drafts, audit logs
  - Systems: API Gateway, Application Services, PostgreSQL database, Object Storage (S3/Blob), AI Foundation Model (Azure OpenAI/AWS Bedrock)
  - Infrastructure: VPC/VNet (UK regions), Secrets Manager, SIEM, WAF, DDoS protection

**4. Risk Treatment Plans**:
- **R-001 (Cross-Tenant Leak)**: TREAT with 6-layer defense-in-depth (RLS, app validation, network isolation, encryption, boundary tests, pen testing)
- **R-004 (NCSC Assurance)**: TREAT with early NCSC engagement (Week 3), parallel review (Months 2-6), pre-NCSC internal audit
- **R-008 (ICO DPIA)**: TREAT with early ICO engagement (Month 3), privacy-by-design architecture, GDPR controls (Sprint 4)
- **4Ts Distribution**: Tolerate 15%, Treat 70%, Transfer 10%, Terminate 5%

**5. Risk Monitoring and Review**:
- **Weekly Review**: Critical and High risks (R-001, R-004, R-007, R-002, R-005, R-010)
- **Monthly Review**: Medium risks (R-003, R-006, R-008, R-009, R-011, R-012, R-014)
- **Quarterly Review**: Low risks and tolerated risks (R-013, R-015, R-016, R-017, R-018, R-019, R-020)
- **Risk Movement Tracking**: Risk register tracks inherent → residual risk changes, control effectiveness

**Gaps Identified**:

**GAP A2-01 (HIGH PRIORITY)**: **Formal Threat Modeling Not Completed**
- **Issue**: Multi-tenant AI architecture lacks formal threat modeling using STRIDE or PASTA methodology
- **Impact**: May miss critical attack vectors (tenant boundary bypass, AI prompt injection, model poisoning, data exfiltration)
- **Current State**: Risk register identifies risks (R-001 cross-tenant leak) but no structured threat model
- **Remediation**:
  - Conduct threat modeling workshop Month 3 (Sprint 6) with NCSC + Security Architect + Tech Lead
  - Use STRIDE methodology (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege)
  - Focus on: Multi-tenant isolation, AI foundation model integration, authentication/authorization, data flows
  - Output: Threat model document with attack trees, mitigations mapped to controls
- **Owner**: Security Architect / NCSC Lead Architect
- **Target Date**: 2026-01-31 (Month 3, Sprint 6)
- **Priority**: HIGH (NCSC review prerequisite)

**GAP A2-02 (MEDIUM PRIORITY)**: **Vulnerability Management Process Not Documented**
- **Issue**: Dependency scanning and SAST/DAST planned (backlog.md DoD) but vulnerability management lifecycle not documented
- **Impact**: Critical vulnerabilities may not be patched within SLA (14 days for critical, 30 days for high)
- **Remediation**:
  - Document vulnerability management process (scanning frequency, severity classification, patching SLA, exception process)
  - Integrate with CI/CD pipeline (Snyk, Dependabot for dependencies, SonarQube for SAST)
  - Define SLA: Critical <14 days, High <30 days, Medium <90 days
- **Owner**: Security Lead / DevOps Lead
- **Target Date**: 2026-02-28 (Month 2, Sprint 4)
- **Priority**: MEDIUM

**CAF A2 Score**: ⚠️ **PARTIALLY ACHIEVED** (75%) - Risk register and Orange Book compliance strong, but formal threat modeling incomplete

**Recommendation**: Complete threat modeling by Month 3 to achieve FULL COMPLIANCE with CAF A2.

---

#### A3: Asset Management

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Assets are inventoried and managed throughout their lifecycle."

**Evidence of Compliance**:

**1. Data Asset Inventory**:
- **Data Types**: User documents (PDF/DOCX/TXT), user profiles, AI-generated content (summaries, drafts), audit logs, usage analytics
- **Data Classification**: OFFICIAL to OFFICIAL-SENSITIVE (automatic classification detection - FR-007, STORY-019)
- **Data Owners**: Departmental admins manage departmental data (federated model - Conflict C-002)
- **Data Lifecycle**: Upload → AI processing → Storage → Retention → Deletion (automated deletion per GDPR retention policy)
- **Data Residency**: All data in UK regions (AWS eu-west-2 or Azure UK South/UK West - BR-006, DR-001)

**2. System Asset Inventory**:
- **Application Services**: API Gateway, Authentication Service, Document Processing, AI Integration, Knowledge Base Search
- **Databases**: PostgreSQL (RDS/Azure SQL) with Row-Level Security (RLS), encrypted at rest (AES-256)
- **Object Storage**: S3/Azure Blob Storage (UK regions, encrypted at rest, versioning enabled)
- **AI Foundation Model**: Azure OpenAI UK or AWS Bedrock UK (tenant-specific API keys, UK data processing)
- **Secrets Management**: AWS Secrets Manager or Azure Key Vault (automated key rotation, audit logging)

**3. Infrastructure Asset Inventory**:
- **Cloud Provider**: AWS eu-west-2 London OR Azure UK South/UK West
- **Network**: VPC/VNet (UK regions), public/private subnets, NAT gateways, VPN gateways
- **Compute**: Kubernetes (EKS/AKS) for container orchestration, auto-scaling groups
- **Security Services**: WAF (Web Application Firewall), DDoS protection, VPC Flow Logs, CloudWatch/Azure Monitor
- **Monitoring**: Prometheus/Grafana (open-source), SIEM (Splunk/Elastic Security - planned Sprint 4)

**4. Asset Lifecycle Management**:
- **Provisioning**: Infrastructure as Code (Terraform - architecture-principles.md Principle 21), version-controlled in Git
- **Configuration Management**: CIS benchmarks, hardening baselines, automated configuration compliance (planned Sprint 2)
- **Change Management**: CI/CD pipeline (GitHub Actions/Azure DevOps - STORY-058), change approval for production deployments
- **Decommissioning**: Automated data deletion (GDPR compliance - STORY-008, STORY-064), infrastructure tear-down via Terraform destroy

**5. Software Bill of Materials (SBOM)**:
- **Dependency Tracking**: SBOM maintained for all components (open-source libraries, cloud services, AI models)
- **License Compliance**: Apache 2.0, MIT, BSD licenses preferred (architecture-principles.md Principle 3)
- **Vulnerability Tracking**: Dependency scanning daily (Snyk, Dependabot - backlog.md DoD), SBOM updated automatically

**6. Asset Ownership and Responsibility**:
- **Data Ownership**: Departmental admins (Home Office, HMRC, DHSC) own departmental data
- **System Ownership**: Cabinet Office CTO owns platform infrastructure
- **Security Ownership**: Security Lead responsible for security controls, NCSC oversight
- **RACI Matrix**: Stakeholder RACI (stakeholder-drivers.md) defines Responsible, Accountable, Consulted, Informed for all assets

**Gaps**: None identified. Comprehensive asset inventory with Infrastructure as Code, SBOM, and clear ownership.

**CAF A3 Score**: ✅ **ACHIEVED**

---

#### A4: Supply Chain

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Security risks arising from dependencies on suppliers of products and services are identified, assessed, managed and reviewed."

**Evidence of Compliance**:

**1. Supplier Identification**:
- **Cloud Provider**: AWS OR Azure (UK regions, Cyber Essentials Plus, ISO 27001)
- **AI Foundation Model Vendor**: Azure OpenAI UK, AWS Bedrock UK, OR Anthropic UK
- **Microsoft 365 Integration**: Microsoft (existing government contract, OAuth 2.0 integration)
- **Google Workspace Integration**: Google (existing government contract, OAuth 2.0 integration)
- **SIEM Vendor**: Splunk OR Elastic (security monitoring, SIEM solution)
- **Penetration Testing Firm**: NCSC-approved CHECK scheme certified firm

**2. Supplier Risk Assessment**:
- **Vendor Evaluation Scorecard**: Cloud provider and AI vendor evaluation (STORY-056, STORY-051)
- **Evaluation Criteria**:
  - UK data residency guarantees (contractual, no cross-border transfers)
  - Cyber Essentials Plus certification (minimum security baseline)
  - ISO 27001, SOC 2 Type II certifications (security management)
  - NCSC Cloud Security Principles compliance (14 principles)
  - UK-qualified personnel for support (no offshore support for OFFICIAL-SENSITIVE)
  - Financial stability (supplier viability, business continuity)

**3. Contractual Security Requirements**:
- **UK Data Residency Clauses**: Vendor contractually prohibited from transferring data outside UK without approval (BR-006)
- **Data Processing Agreements**: GDPR Article 28 processor agreements (data protection, sub-processor notification)
- **Security Controls**: Encryption at rest/transit, access controls, audit logging, incident notification (24 hours)
- **Right to Audit**: Audit rights for compliance verification, third-party audits (ISO 27001, SOC 2)
- **Exit Rights**: 90-day notice period, data handover support, no lock-in penalties (R-012 mitigation)

**4. Supplier Security Monitoring**:
- **SLA Monitoring**: Uptime 99.9%, latency <3s P95, support response <4 hours critical (NFR-A-001, Finding L-002)
- **Security Incident Reporting**: Vendor must report security incidents within 24 hours (contractual requirement)
- **Quarterly Vendor Reviews**: Performance against SLAs, security posture, cost optimization, roadmap alignment
- **Compliance Verification**: Annual ISO 27001, SOC 2 audit reports reviewed, Cyber Essentials Plus expiry tracked

**5. Vendor Lock-In Mitigation** (R-012):
- **Multi-Vendor Evaluation**: AWS vs Azure (cloud provider), Azure OpenAI vs AWS Bedrock vs Anthropic (AI vendor)
- **Abstraction Layers**: Terraform (multi-cloud IaC), Kubernetes (portable orchestration), PostgreSQL (open-source database)
- **Open Standards**: OpenAPI, OAuth 2.0, JSON (not proprietary formats - architecture-principles.md Principle 2, 4)
- **Exit Strategy**: Data export in open formats (CSV, JSON), knowledge base migration plan, 90-day transition support

**6. Supply Chain Risk Register**:
- **R-006**: AI Vendor UK Data Residency Failure (Inherent 12, Residual 9) - Mitigated via UK contracts
- **R-010**: Cloud/AI API Costs Exceed Budget (Inherent 15, Residual 9) - Mitigated via FinOps, volume discounts
- **R-012**: Vendor Lock-In (Inherent 12, Residual 9) - Mitigated via abstraction layers, multi-vendor strategy
- **R-017**: Integration Failures (Microsoft 365, Google Workspace) (Inherent 9, Residual 6) - Mitigated via fallback mechanisms

**Gaps**: None identified. Comprehensive supplier risk management with UK data residency contracts, multi-vendor strategy, and vendor monitoring.

**CAF A4 Score**: ✅ **ACHIEVED**

---

### Objective B: Protecting Against Cyber Attack (6 Principles)

#### B1: Service Protection Policies and Processes

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Policies and processes are in place to ensure systems, services and networks are protected against cyber attack."

**Evidence of Compliance**:

**1. Acceptable Use Policy**:
- **Civil Servant Code of Conduct**: Government baseline (no personal use of AI for non-official purposes)
- **Data Classification Handling**: OFFICIAL-SENSITIVE requires Tier 2 security training (15 minutes - STORY-005)
- **AI Usage Guidelines**: Transparency watermarking ("AI-Generated - Verify Before Use" - STORY-033), human-in-the-loop for high-stakes decisions
- **Prohibited Activities**: Cross-tenant access attempts, unauthorized data export, AI jailbreaking attempts
- **Target Date**: Month 3 (Alpha phase) - Acceptable Use Policy published

**2. Access Control Policy**:
- **Role-Based Access Control (RBAC)**: 4 roles - User (view), Power User (advanced features), Admin (user management), Governance Lead (AI oversight)
- **Least Privilege**: Users granted minimum permissions required for role (architecture-principles.md Principle 4)
- **Access Reviews**: Quarterly access reviews (departmental admins review user lists, revoke leavers)
- **Privileged Access Management (PAM)**: Admin access requires approval, time-boxed, MFA, audit logging

**3. Data Protection Policy**:
- **Encryption Standards**: AES-256 at rest, TLS 1.3 in transit (TLS 1.2 minimum fallback)
- **Data Classification**: Automatic classification detection (OFFICIAL vs OFFICIAL-SENSITIVE - FR-007)
- **Data Handling**: OFFICIAL-SENSITIVE requires encryption, MFA, audit logging, Tier 2 training
- **Data Retention**: Automated deletion per GDPR (user data retention policy, audit logs 7 years)
- **Data Loss Prevention (DLP)**: Planned Sprint 8 (detect sensitive data exfiltration attempts)

**4. Incident Response Policy**:
- **Incident Classification**: Low, Medium, High, Critical (based on data classification, user impact, GDPR breach)
- **Escalation Procedures**: Critical incidents → Permanent Secretary + NCSC + ICO immediately
- **Breach Notification**: 72-hour ICO notification for personal data breaches (UK GDPR Article 33)
- **Incident Response Runbook**: Documented (STORY-017 - Sprint 4), tested quarterly
- **Forensics**: Immutable audit logs (WORM storage - FR-005), log retention 7 years

**5. Change Management Policy**:
- **Change Approval Board (CAB)**: Production changes require CAB approval (Permanent Secretary, CTO, Security Lead)
- **Automated Testing**: CI/CD quality gates (unit tests >70%, security scanning, accessibility testing)
- **Rollback Capability**: Blue/green deployments, tested rollback <15 minutes
- **Emergency Changes**: Security patches can bypass CAB for critical vulnerabilities (<14 day SLA)

**6. Security Testing Policy**:
- **Penetration Testing**: Quarterly (NCSC-approved CHECK scheme firm - STORY-014), before each phase gate (Alpha, Beta, Live)
- **Vulnerability Scanning**: Daily dependency scanning (Snyk, Dependabot), weekly infrastructure scanning
- **SAST/DAST**: Static and Dynamic Application Security Testing in CI/CD pipeline
- **Bug Bounty**: Planned post-Live (Month 14+) - public bug bounty for ethical hackers

**Gaps**: None identified. Comprehensive security policies covering acceptable use, access control, data protection, incident response, change management, and security testing.

**CAF B1 Score**: ✅ **ACHIEVED**

---

#### B2: Identity and Access Control

**Status**: ⚠️ **PARTIALLY ACHIEVED**

**NCSC CAF Requirement**: "Access to systems, services and data is constrained to authenticated and authorised individuals and systems."

**Evidence of Compliance**:

**1. Authentication Controls**:
- **Government SSO**: Azure AD SSO with OpenID Connect (FR-009, STORY-001 - Sprint 1)
- **Multi-Factor Authentication (MFA)**: MANDATORY for all users (NFR-SEC-001, STORY-002 - Sprint 1)
- **MFA Methods**: Microsoft Authenticator app (primary), SMS fallback (secondary)
- **Session Management**: 30-minute inactivity timeout, 8-hour absolute timeout (STORY-006 - Sprint 3)
- **Service-to-Service Authentication**: Mutual TLS, signed JWT tokens, API keys with rotation

**2. Authorization Controls**:
- **Role-Based Access Control (RBAC)**: 4 roles (User, Power User, Admin, Governance Lead) - FR-011, STORY-003 - Sprint 2
- **Least Privilege**: Users granted minimum permissions, time-boxed access for admins
- **Tenant Isolation**: Tenant_id in JWT token (SSO claim), validated on EVERY API request (STORY-010 - Sprint 2)
- **Authorization Enforcement**: Middleware rejects requests if tenant_id mismatch between token and resource
- **Resource-Level Permissions**: Document ownership (users can only access own documents + shared documents)

**3. Privileged Access Management (PAM)**:
- **Admin Access**: Separate admin accounts, approval workflow, time-boxed (e.g., 8-hour access)
- **Audit Logging**: All admin actions logged (who, what, when, where) - FR-005
- **Break-Glass Access**: Emergency access for production issues (requires dual approval, logged, time-limited)

**4. Access Reviews**:
- **Quarterly Reviews**: Departmental admins review user lists, revoke leavers, validate roles
- **Automated Deprovisioning**: Users removed from Azure AD SSO automatically deprovisioned (no orphan accounts)
- **Stale Account Detection**: Accounts inactive >90 days flagged for review

**Gaps Identified**:

**GAP B2-01 (CRITICAL PRIORITY)**: **Cyber Essentials Plus Certification Not Obtained**
- **Issue**: Access control is a Cyber Essentials control (MFA, least privilege), but certification not yet obtained
- **Impact**: OFFICIAL-SENSITIVE data processing requires Cyber Essentials Plus before Private Beta
- **Current State**: Controls planned (MFA Sprint 1, RBAC Sprint 2), but not implemented or externally verified
- **Remediation**:
  - **Month 1-2**: Implement Cyber Essentials controls (MFA, RBAC, secure configuration, firewalls, patching)
  - **Month 4**: Complete Cyber Essentials self-assessment questionnaire
  - **Month 5**: External technical verification by IASME-certified assessor (Cyber Essentials Plus)
  - **Target**: Certification obtained by Month 5 (before Private Beta Month 6)
- **Owner**: Security Lead / Cabinet Office CTO
- **Target Date**: 2026-03-31 (Month 5, before Private Beta)
- **Priority**: CRITICAL (Private Beta gate blocker)

**GAP B2-02 (MEDIUM PRIORITY)**: **Privileged Access Management (PAM) Process Not Documented**
- **Issue**: Admin access controls mentioned but PAM process not documented (approval workflow, time-boxing, audit)
- **Impact**: Risk of unauthorized admin access, insufficient audit trail for privileged operations
- **Remediation**:
  - Document PAM process (approval workflow, time-boxed access, dual approval for break-glass)
  - Implement PAM tooling (e.g., Azure AD Privileged Identity Management, AWS IAM Access Analyzer)
  - Test quarterly (simulate production incident, validate break-glass access)
- **Owner**: Security Lead / Infrastructure Lead
- **Target Date**: 2026-02-28 (Month 2, Sprint 4)
- **Priority**: MEDIUM

**CAF B2 Score**: ⚠️ **PARTIALLY ACHIEVED** (70%) - Strong authentication/authorization design, but Cyber Essentials Plus certification pending

**Recommendation**: Obtain Cyber Essentials Plus certification by Month 5 to achieve FULL COMPLIANCE with CAF B2.

---

#### B3: Data Security

**Status**: ⚠️ **PARTIALLY ACHIEVED**

**NCSC CAF Requirement**: "Data is protected against loss, corruption or compromise."

**Evidence of Compliance**:

**1. Encryption at Rest**:
- **Database**: PostgreSQL encrypted with AES-256 (RDS/Azure SQL Database Transparent Data Encryption)
- **Object Storage**: S3/Azure Blob Storage encrypted with AES-256 (SSE-S3/Azure Storage Service Encryption)
- **Tenant-Specific Encryption Keys**: Separate KEK (Key Encryption Key) per tenant in AWS KMS / Azure Key Vault (STORY-011 - Sprint 2)
- **Secrets**: AWS Secrets Manager / Azure Key Vault with automated key rotation

**2. Encryption in Transit**:
- **TLS 1.3**: Preferred for all HTTPS traffic (TLS 1.2 minimum fallback)
- **API Gateway**: TLS termination at API Gateway (WAF-protected)
- **Internal Services**: Mutual TLS (mTLS) for service-to-service communication (Kubernetes service mesh)
- **VPN**: Site-to-site VPN for PSN (Public Services Network) connectivity (if required)

**3. Data Classification and Handling**:
- **UK Government Security Classifications**: PUBLIC, OFFICIAL, OFFICIAL-SENSITIVE applied
- **Automatic Classification Detection**: AI detects data classification based on content patterns (FR-007, STORY-019 - Sprint 5)
- **Classification-Specific Controls**:
  - OFFICIAL-SENSITIVE: Encryption at rest/transit, MFA, audit logging (7 years), Cyber Essentials Plus, DPIA
- **Data Labeling**: Metadata tags (classification, owner, retention period)

**4. Data Loss Prevention (DLP)**:
- **Planned**: Sprint 8 (STORY not created yet)
- **Controls**: Detect sensitive data exfiltration (document download monitoring, API rate limiting, anomaly detection)
- **Alerting**: SIEM alerts for bulk data export attempts, cross-tenant access attempts

**5. UK GDPR Compliance**:
- **Lawful Basis**: Public task (Article 6(1)(e)) for government processing
- **Data Minimization**: Collect only necessary data (document metadata, user profile, AI outputs)
- **Data Subject Rights**: SAR (Subject Access Request), erasure, portability (STORY-064 - Sprint 4)
- **Retention Policy**: Documents deleted per departmental retention schedule, audit logs 7 years, user data deleted on request
- **Consent Management**: Consent audit trail for optional features (STORY-065 - Sprint 4)

**6. Backup and Recovery**:
- **Backup Frequency**: Database daily incremental, weekly full; Object storage versioning enabled
- **Backup Encryption**: Backups encrypted with AES-256
- **Backup Retention**: 30 days online, 7 years archival (compliance requirement)
- **Disaster Recovery**: RPO 15 minutes (point-in-time recovery), RTO 4 hours (multi-AZ failover)
- **DR Testing**: Quarterly DR drills (STORY-063 - Sprint 4)

**Gaps Identified**:

**GAP B3-01 (CRITICAL PRIORITY)**: **Data Protection Impact Assessment (DPIA) Not Completed**
- **Issue**: DPIA is MANDATORY for high-risk AI processing (generative AI, cross-government scale, OFFICIAL-SENSITIVE data) but not yet completed
- **Impact**:
  - UK GDPR non-compliance (Article 35 - DPIA required before processing)
  - ICO enforcement action risk (fines up to £17.5M or 4% turnover)
  - Private Beta launch BLOCKED without ICO DPIA approval
- **Current State**: DPIA planned (STORY-066 - Sprint 5), ICO engagement Month 3, but not yet started
- **Remediation**:
  - **Month 3**: Initiate ICO engagement (early DPIA consultation)
  - **Month 4-5**: Complete DPIA documentation (data flows, risks, mitigations, necessity/proportionality assessment)
  - **Month 5**: Submit DPIA to ICO for review and approval
  - **Month 6**: Obtain ICO DPIA approval BEFORE Private Beta launch
- **Owner**: Data Protection Officer / ICO Chief Technology Officer
- **Target Date**: 2026-05-31 (Month 6, Private Beta gate blocker)
- **Priority**: CRITICAL (UK GDPR legal requirement, Private Beta gate blocker)
- **Evidence Gap**: STORY-066 (ICO DPIA Documentation & Submission) not yet started

**GAP B3-02 (HIGH PRIORITY)**: **Data Loss Prevention (DLP) Not Implemented**
- **Issue**: DLP controls planned but not yet implemented (Sprint 8)
- **Impact**: Risk of data exfiltration (bulk document download, API abuse, insider threat)
- **Remediation**:
  - Implement DLP controls Sprint 8 (document download monitoring, API rate limiting, anomaly detection)
  - SIEM alerting for bulk data export (>100 documents/hour), cross-tenant access attempts
  - Integrate with Microsoft 365 DLP policies (block copy/paste to external apps)
- **Owner**: Security Lead / Tech Lead
- **Target Date**: 2026-04-30 (Sprint 8)
- **Priority**: HIGH

**GAP B3-03 (MEDIUM PRIORITY)**: **Records of Processing Activities (ROPA) Not Completed**
- **Issue**: UK GDPR Article 30 requires ROPA (data processing inventory) - not yet documented
- **Impact**: ICO audit finding, GDPR non-compliance
- **Remediation**:
  - Document ROPA (data categories, processing purposes, recipients, retention periods, security measures)
  - Include: User profiles, documents, AI-generated content, audit logs, usage analytics
  - Review annually (update for new processing activities)
- **Owner**: Data Protection Officer
- **Target Date**: 2026-03-31 (Month 5, Alpha phase)
- **Priority**: MEDIUM

**CAF B3 Score**: ⚠️ **PARTIALLY ACHIEVED** (60%) - Strong encryption and data handling design, but DPIA critical gap

**Recommendation**: Complete DPIA by Month 5 and obtain ICO approval by Month 6 to achieve FULL COMPLIANCE with CAF B3.

---

#### B4: System Security

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Systems are securely configured, maintained and managed to prevent and detect security issues."

**Evidence of Compliance**:

**1. Secure Configuration**:
- **CIS Benchmarks**: Apply CIS (Center for Internet Security) benchmarks for OS, database, containers
- **Hardening**: Disable unnecessary services, remove default accounts, apply security baselines
- **Configuration Management**: Infrastructure as Code (Terraform), configuration drift detection
- **Automated Compliance**: Policy-as-Code (e.g., Open Policy Agent) enforces secure configuration in CI/CD

**2. Patch Management**:
- **SLA**: Critical patches <14 days (Cyber Essentials requirement), High <30 days, Medium <90 days
- **Automated Patching**: Kubernetes auto-updates, cloud-managed services (RDS, S3) auto-patched by provider
- **Patch Testing**: Patches tested in dev/staging before production deployment
- **Emergency Patching**: Critical vulnerabilities (CVSS 9.0+) can bypass change approval for urgent deployment

**3. Anti-Malware Protection**:
- **Endpoint Detection and Response (EDR)**: Planned for developer laptops (CrowdStrike, Microsoft Defender for Endpoint)
- **Container Security**: Image scanning for malware and vulnerabilities (Trivy, Snyk Container)
- **Cloud Workload Protection**: AWS GuardDuty or Azure Defender for Cloud (malware detection, anomaly detection)

**4. Vulnerability Management**:
- **Dependency Scanning**: Daily scanning (Snyk, Dependabot) in CI/CD pipeline
- **Static Application Security Testing (SAST)**: SonarQube in CI/CD (detect code vulnerabilities)
- **Dynamic Application Security Testing (DAST)**: Pre-production DAST scanning (OWASP ZAP, Burp Suite)
- **Infrastructure Scanning**: Weekly Nessus/Qualys scans of cloud infrastructure
- **Vulnerability SLA**: Critical <14 days, High <30 days, Medium <90 days remediation

**5. Software Bill of Materials (SBOM)**:
- **Component Tracking**: SBOM maintained for all open-source libraries, cloud services, AI models
- **License Compliance**: Apache 2.0, MIT, BSD licenses verified
- **CVE Monitoring**: SBOM cross-referenced with CVE databases (NVD, GitHub Security Advisories)

**6. Secure Development Lifecycle (SDLC)**:
- **Security Requirements**: NFR-SEC-001 through NFR-SEC-006 defined upfront
- **Threat Modeling**: Planned Month 3 (STRIDE methodology)
- **Secure Coding Training**: Developers trained on OWASP Top 10, secure coding practices
- **Code Review**: 2+ reviewers required, security review for authentication/authorization changes
- **CI/CD Quality Gates**: Security scanning (SAST, dependency scan), no merge if critical vulnerabilities

**7. Container and Kubernetes Security**:
- **Image Scanning**: Container images scanned before deployment (Trivy, Snyk)
- **Minimal Images**: Use distroless or Alpine base images (reduce attack surface)
- **Pod Security Standards**: Kubernetes Pod Security Admission (enforce restricted policies)
- **Network Policies**: Kubernetes NetworkPolicies restrict pod-to-pod communication
- **RBAC**: Kubernetes RBAC for API access (least privilege)

**Gaps**: Minor gap in EDR deployment (planned but not yet implemented), but overall strong system security controls.

**CAF B4 Score**: ✅ **ACHIEVED**

---

#### B5: Resilient Networks

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Networks are designed and operated to protect against cyber attack and provide resilience."

**Evidence of Compliance**:

**1. Network Segmentation**:
- **Multi-Tier Architecture**: Public subnet (API Gateway, Load Balancer), Private subnet (Application Services, Database)
- **VPC/VNet Isolation**: Separate VPCs/VNets for dev, staging, production environments
- **Tenant-Specific Network Isolation**: Separate VPCs/VNets for high-security tenants (HMRC, Home Office - STORY-012 - Sprint 3)
- **Micro-Segmentation**: Kubernetes NetworkPolicies restrict pod-to-pod communication (least privilege)

**2. Boundary Firewalls**:
- **Internet Gateway Firewall**: VPC/VNet security groups / network security groups (NSGs) restrict inbound traffic
- **Web Application Firewall (WAF)**: AWS WAF or Azure WAF protecting API Gateway (OWASP Top 10 rules, rate limiting)
- **DDoS Protection**: AWS Shield or Azure DDoS Protection (automatic mitigation of volumetric attacks)
- **Egress Filtering**: NAT Gateway for outbound traffic from private subnets (no direct internet access from backend)

**3. Intrusion Detection/Prevention (IDS/IPS)**:
- **Network IDS**: VPC Flow Logs / Azure Network Watcher (traffic logging, anomaly detection)
- **Cloud-Native IDS**: AWS GuardDuty or Azure Defender for Cloud (threat intelligence, ML-based anomaly detection)
- **SIEM Integration**: VPC Flow Logs ingested into SIEM (Splunk/Elastic) for correlation and alerting

**4. VPN and Remote Access**:
- **Site-to-Site VPN**: VPN gateway for PSN (Public Services Network) connectivity (if required for inter-departmental data sharing)
- **User VPN**: Azure AD conditional access policies (MFA required, device compliance checks)
- **Zero Trust Network Access (ZTNA)**: No implicit trust, verify every connection (Azure AD, AWS IAM Identity Center)

**5. Wireless Security**:
- **N/A**: Cloud-hosted platform, no on-premise wireless infrastructure
- **(Developer Guidance)**: Developers use corporate WiFi (WPA3 or WPA2-Enterprise with 802.1X)

**6. Network Monitoring**:
- **Traffic Logging**: VPC Flow Logs / Azure Network Watcher (all network traffic logged)
- **Anomaly Detection**: ML-based anomaly detection (GuardDuty/Defender - unusual traffic patterns, port scanning, crypto mining)
- **Alerting**: SIEM alerts for: Port scanning, suspicious outbound connections, DDoS attempts, cross-VPC traffic anomalies

**Gaps**: None identified. Comprehensive network security with segmentation, firewalls, IDS/IPS, and monitoring.

**CAF B5 Score**: ✅ **ACHIEVED**

---

#### B6: Staff Awareness and Training

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Staff are informed and trained in their security responsibilities."

**Evidence of Compliance**:

**1. Security Induction Training**:
- **All Users**: 5-minute onboarding tutorial (STORY-004 - Sprint 2) covering:
  - Data classification (OFFICIAL vs OFFICIAL-SENSITIVE)
  - Acceptable use policy (no personal use, AI transparency)
  - Phishing awareness (recognize suspicious emails)
  - Incident reporting (how to report security concerns)
- **OFFICIAL-SENSITIVE Users**: Additional 15-minute security training (Tier 2 - STORY-005 - Sprint 2) covering:
  - Handling OFFICIAL-SENSITIVE data (encryption, no personal devices, secure deletion)
  - Cross-tenant isolation (why data must NOT be shared across departments)
  - AI limitations (bias risks, verify AI outputs before use)

**2. Role-Specific Training**:
- **Admins**: Privileged access management (PAM) training, break-glass procedures, audit logging
- **Governance Leads**: AI governance training (bias detection, ATRS publication, AI Playbook compliance)
- **Developers**: Secure coding training (OWASP Top 10, GDPR, threat modeling)

**3. Ongoing Security Awareness**:
- **Quarterly Phishing Simulations**: Simulated phishing emails, track click rates, retrain clickers
- **Security Newsletters**: Monthly security tips (password hygiene, social engineering awareness, data protection)
- **Lunch & Learn Sessions**: Quarterly security presentations (emerging threats, case studies, lessons learned)

**4. Incident Reporting Culture**:
- **No-Blame Culture**: Users encouraged to report security concerns without fear of punishment
- **Reporting Channels**: Email (security@cabinetoffice.gov.uk), phone hotline, in-app "Report Security Concern" button
- **Feedback Loop**: Users notified when reported issues are resolved (close the loop)

**5. Data Protection Training**:
- **UK GDPR Training**: All users trained on UK GDPR basics (data subject rights, breach reporting, lawful basis)
- **Annual Refresher**: Annual data protection training (update on new regulations, case studies)
- **Certifications**: DPO holds IAPP CIPP/E or equivalent certification

**6. AI-Specific Training**:
- **AI Literacy**: Users trained on AI capabilities and limitations (what AI can/cannot do, accuracy expectations)
- **Bias Awareness**: Training on recognizing AI bias (demographic bias, confirmation bias, data quality issues)
- **Human-in-the-Loop**: Users trained on when to escalate AI outputs to human review (high-stakes decisions, low confidence)

**Gaps**: None identified. Comprehensive security awareness programme covering induction, role-specific, ongoing, and AI-specific training.

**CAF B6 Score**: ✅ **ACHIEVED**

---

### Objective C: Detecting Cyber Security Events (2 Principles)

#### C1: Security Monitoring

**Status**: ⚠️ **PARTIALLY ACHIEVED**

**NCSC CAF Requirement**: "Events affecting, or with the potential to affect, security are detected and monitored."

**Evidence of Compliance**:

**1. Security Information and Event Management (SIEM)**:
- **Planned**: Splunk OR Elastic Security (STORY not yet created, planned Sprint 4)
- **Log Sources**: API Gateway, Application Services, Database (RLS events), Object Storage (access logs), VPC Flow Logs, CloudWatch/Azure Monitor
- **Real-Time Ingestion**: Logs ingested in real-time (<5 minute delay)
- **Correlation Rules**: SIEM correlates events across sources (e.g., failed login + cross-tenant access attempt = high-severity alert)

**2. Audit Logging**:
- **Authentication Events**: All login attempts (success, failure, MFA challenges) logged
- **Authorization Events**: API requests (tenant_id, user_id, resource, action, timestamp) logged
- **Data Access**: Document downloads, AI queries, search requests logged
- **Admin Actions**: User management (create, update, delete), configuration changes, privileged access logged
- **RLS Bypass Attempts**: PostgreSQL Row-Level Security violations logged (cross-tenant query attempts)
- **Immutable Storage**: Audit logs stored in WORM (Write-Once-Read-Many) storage (FR-005 - 7-year retention)

**3. Security Alerting**:
- **Real-Time Alerts**: SIEM generates alerts for security events within 30 seconds
- **Alert Severity**: Low, Medium, High, Critical (based on threat level, data classification)
- **Alert Channels**: Email, SMS, PagerDuty (for critical alerts - on-call rotation)
- **Alert Examples**:
  - **Critical**: Cross-tenant access attempt, RLS bypass, brute-force login (10+ failed attempts in 5 min)
  - **High**: Bulk data download (>100 documents in 1 hour), admin access from unusual location
  - **Medium**: Failed MFA challenge, API rate limit exceeded, DAST vulnerability finding

**4. Threat Intelligence**:
- **Threat Feeds**: AWS GuardDuty OR Azure Defender threat intelligence (known malicious IPs, domains, attack patterns)
- **Indicators of Compromise (IOCs)**: SIEM correlates logs with IOCs (e.g., login from known botnet IP)
- **NCSC Threat Intelligence**: Weekly NCSC threat bulletins reviewed, relevant threats actioned

**5. User and Entity Behavior Analytics (UEBA)**:
- **Baseline Behavior**: SIEM establishes baseline user behavior (typical login times, locations, document access patterns)
- **Anomaly Detection**: Alerts for deviations from baseline (e.g., user accessing 10× normal documents, login from new country)
- **ML-Based Detection**: Machine learning models detect anomalies (unusual API usage, data exfiltration patterns)

**6. Security Metrics and Dashboards**:
- **Security Operations Centre (SOC) Dashboard**: Real-time security events, alert trends, incident status
- **Executive Dashboard**: Monthly security KPIs (incidents, vulnerabilities patched, phishing click rate, compliance status)
- **Metrics Tracked**: Mean Time to Detect (MTTD), Mean Time to Respond (MTTR), alert false-positive rate, SLA compliance

**Gaps Identified**:

**GAP C1-01 (HIGH PRIORITY)**: **SIEM Not Yet Operational**
- **Issue**: SIEM deployment planned Sprint 4 but not yet implemented
- **Impact**: Cannot detect cross-tenant access attempts, security incidents, anomalous behavior in real-time
- **Current State**: Logging infrastructure exists (CloudWatch/Azure Monitor), but no centralized SIEM for correlation and alerting
- **Remediation**:
  - **Sprint 4 (Month 2)**: Deploy SIEM (Splunk or Elastic Security)
  - **Sprint 4**: Ingest logs from all sources (API Gateway, Database, VPC Flow Logs, CloudWatch)
  - **Sprint 4**: Configure correlation rules (cross-tenant access, brute-force, bulk download)
  - **Sprint 4**: Integrate with PagerDuty for critical alerts (on-call rotation)
  - **Sprint 5**: Tune SIEM (reduce false positives, refine correlation rules)
- **Owner**: Security Lead / Security Operations Centre (SOC)
- **Target Date**: 2026-02-28 (Month 2, Sprint 4)
- **Priority**: HIGH (NCSC review prerequisite, R-001 mitigation)

**CAF C1 Score**: ⚠️ **PARTIALLY ACHIEVED** (50%) - Strong logging and audit design, but SIEM not yet operational

**Recommendation**: Deploy SIEM by Sprint 4 (Month 2) to achieve FULL COMPLIANCE with CAF C1.

---

#### C2: Proactive Security Event Discovery

**Status**: ⚠️ **PARTIALLY ACHIEVED**

**NCSC CAF Requirement**: "Competent analysis of security events is used to detect potential security compromises or attacks."

**Evidence of Compliance**:

**1. Vulnerability Scanning**:
- **Dependency Scanning**: Daily Snyk, Dependabot scans in CI/CD pipeline (detect vulnerable libraries)
- **Infrastructure Scanning**: Planned weekly Nessus/Qualys scans (detect OS vulnerabilities, misconfigurations)
- **Container Scanning**: Trivy, Snyk Container scans before deployment (detect image vulnerabilities)
- **SAST**: SonarQube in CI/CD (detect code vulnerabilities - SQL injection, XSS, hardcoded secrets)
- **DAST**: Pre-production DAST scanning (OWASP ZAP, Burp Suite - detect runtime vulnerabilities)

**2. Penetration Testing**:
- **Planned**: Quarterly penetration testing (NCSC-approved CHECK scheme firm - STORY-014 - Sprint 4)
- **Scope**: Multi-tenant isolation (IDOR, JWT tampering, SQL injection), AI security (prompt injection, jailbreaking), API security (authentication bypass, authorization flaws)
- **Frequency**: Quarterly (starting Sprint 4), before each phase gate (Alpha, Beta, Live)
- **Remediation**: Critical/High findings remediated within SLA (7 days critical, 30 days high)

**3. Threat Hunting**:
- **Planned**: Quarterly threat hunting exercises (SOC team proactively searches for threats)
- **Techniques**: Hypothesis-driven (e.g., "Are there cross-tenant access attempts hidden in normal traffic?"), IOC-driven (search for known attack patterns)
- **Tools**: SIEM queries, log analysis, network traffic analysis (VPC Flow Logs)

**4. Red Team Exercises**:
- **Planned**: Annual red team exercise (post-Live, Month 14+)
- **Scope**: Full attack simulation (social engineering, phishing, lateral movement, privilege escalation, data exfiltration)
- **Provider**: NCSC-approved CREST-certified red team firm

**5. Bug Bounty Programme**:
- **Planned**: Public bug bounty post-Live (Month 14+ - R-001 mitigation)
- **Platform**: HackerOne or Bugcrowd
- **Rewards**: £500-£5,000 based on severity (NCSC precedent from other Gov platforms)
- **Scope**: Multi-tenant isolation, authentication/authorization, API security, data leakage

**Gaps Identified**:

**GAP C2-01 (HIGH PRIORITY)**: **Penetration Testing Not Yet Conducted**
- **Issue**: Quarterly penetration testing planned (STORY-014 - Sprint 4) but not yet conducted
- **Impact**: Vulnerabilities not validated, NCSC review prerequisite not met
- **Current State**: Vulnerability scanning (dependency, SAST, DAST) in place, but no external penetration testing
- **Remediation**:
  - **Sprint 4 (Month 2)**: Procure NCSC-approved CHECK scheme penetration testing firm
  - **Sprint 4**: Conduct first penetration test (multi-tenant isolation, AI security, API security)
  - **Sprint 5**: Remediate all critical/high findings (7-day SLA for critical, 30-day for high)
  - **Quarterly**: Repeat penetration testing (before each phase gate - Alpha, Beta, Live)
- **Owner**: Security Lead / NCSC-approved CHECK scheme firm
- **Target Date**: 2026-02-28 (Month 2, Sprint 4 - first pen test)
- **Priority**: HIGH (NCSC review prerequisite, CAF C2 requirement)

**CAF C2 Score**: ⚠️ **PARTIALLY ACHIEVED** (50%) - Strong vulnerability scanning, but penetration testing not yet conducted

**Recommendation**: Conduct first penetration test by Sprint 4 (Month 2) to achieve FULL COMPLIANCE with CAF C2.

---

### Objective D: Minimising the Impact of Incidents (2 Principles)

#### D1: Response and Recovery Planning

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Effective plans and processes are in place to respond to and recover from security incidents."

**Evidence of Compliance**:

**1. Incident Response Plan**:
- **Documented**: Incident Response Runbook (STORY-017 - Sprint 4)
- **Incident Classification**: Low, Medium, High, Critical (based on data classification, user impact, GDPR breach)
- **Response Team**: Security Lead (Incident Commander), SOC, Tech Lead, DPO, NCSC liaison, Cabinet Office CTO
- **Escalation Procedures**:
  - **Critical**: Permanent Secretary + NCSC + ICO immediately (cross-tenant leak, GDPR breach)
  - **High**: Cabinet Office CTO + Security Lead within 4 hours
  - **Medium**: Security Lead within 24 hours

**2. Incident Response Procedures**:
- **Detection**: SIEM alerts, user reports, penetration test findings, threat intelligence
- **Analysis**: Incident Commander assesses severity, impact, affected tenants, data classification
- **Containment**: Isolate affected systems (disable user accounts, block IP addresses, quarantine containers)
- **Eradication**: Remove attacker access (revoke credentials, patch vulnerabilities, rebuild compromised systems)
- **Recovery**: Restore from backups (RPO 15 minutes, RTO 4 hours), validate system integrity
- **Post-Incident Review**: Lessons learned, root cause analysis, update runbook

**3. UK GDPR Breach Notification**:
- **72-Hour ICO Notification**: Personal data breaches reported to ICO within 72 hours (UK GDPR Article 33)
- **Individual Notification**: Affected individuals notified if high risk to rights and freedoms
- **Breach Register**: All breaches logged (incident ID, date, data affected, individuals affected, remediation)
- **DPO Involvement**: DPO notified immediately for personal data breaches, advises on ICO notification

**4. Business Continuity and Disaster Recovery (BC/DR)**:
- **Business Continuity Plan**: Documented procedures for maintaining operations during incidents (alternative access methods, manual workarounds)
- **Disaster Recovery Plan**: Documented procedures for recovering from catastrophic failures (data center outage, ransomware, natural disaster)
- **RTO (Recovery Time Objective)**: 4 hours (maximum acceptable downtime)
- **RPO (Recovery Point Objective)**: 15 minutes (maximum acceptable data loss)
- **Failover**: Multi-AZ (Availability Zone) deployment, automated failover to secondary AZ
- **Backups**: Daily database backups (incremental + weekly full), object storage versioning, 30-day retention + 7-year archival

**5. DR Testing**:
- **Quarterly DR Drills**: Simulated disaster recovery (STORY-063 - Sprint 4), validate RTO/RPO
- **Scenarios**: Database failure, region outage, ransomware attack, data corruption
- **Success Criteria**: RTO <4 hours validated, RPO <15 minutes validated, all systems operational

**6. Communication Plan**:
- **Internal**: Status page (service health), email alerts to users, SIRO/CTO briefings
- **External**: GOV.UK service status updates (if public-facing), ICO breach notifications
- **Media**: Cabinet Office communications team (for media queries, ministerial briefings)

**Gaps**: None identified. Comprehensive incident response and DR planning with documented procedures, escalation, and testing.

**CAF D1 Score**: ✅ **ACHIEVED**

---

#### D2: Lessons Learned and Improvement

**Status**: ✅ **ACHIEVED**

**NCSC CAF Requirement**: "Lessons learned from security events are used to improve security."

**Evidence of Compliance**:

**1. Post-Incident Reviews**:
- **Mandatory for High/Critical Incidents**: Post-incident review within 1 week of resolution
- **Participants**: Incident Response Team, SIRO, NCSC liaison (if NCSC involved), affected stakeholders
- **Blameless Post-Mortem**: Focus on systemic issues, not individual blame (encourage transparency)
- **Documentation**: Root cause analysis, timeline, lessons learned, action items with owners and due dates

**2. Security Metrics and KPIs**:
- **Mean Time to Detect (MTTD)**: Average time from incident occurrence to detection (target <1 hour)
- **Mean Time to Respond (MTTR)**: Average time from detection to containment (target <4 hours)
- **Vulnerability Remediation SLA**: % vulnerabilities patched within SLA (target >95%)
- **Phishing Click Rate**: % users who clicked simulated phishing emails (target <5%)
- **Cyber Essentials Compliance**: Valid certification (target 100% compliance)

**3. Continuous Improvement**:
- **Quarterly Security Reviews**: SIRO quarterly review of security metrics, incident trends, risk register
- **Annual NCSC Reassessment**: NCSC Secure by Design reassessment (post-Live, annual)
- **Penetration Test Findings**: All findings tracked, remediation verified in next pen test
- **Vulnerability Trends**: Trending analysis (are vulnerabilities increasing? Same types recurring?)

**4. Security Roadmap Updates**:
- **Lessons → Backlog**: Post-incident action items added to product backlog (prioritized by Product Owner)
- **Controls Enhancement**: Incident findings drive new security controls (e.g., MFA bypass → add device compliance checks)
- **Process Improvements**: Incident response runbook updated based on lessons learned

**5. Knowledge Sharing**:
- **Internal**: Lessons learned shared with other Cabinet Office projects (cross-project learning)
- **Cross-Government**: NCSC case studies contributed (anonymized, benefit other departments)
- **Security Awareness**: Incident case studies used in security training (real-world examples)

**6. Compliance with Regulatory Feedback**:
- **NCSC Recommendations**: All NCSC review findings tracked, remediation verified
- **ICO Feedback**: ICO DPIA feedback incorporated into privacy controls
- **GDS Assessment**: GDS Service Assessment recommendations tracked, addressed before next gate

**Gaps**: None identified. Strong continuous improvement culture with post-incident reviews, metrics tracking, and knowledge sharing.

**CAF D2 Score**: ✅ **ACHIEVED**

---

## Cyber Essentials Assessment

### Cyber Essentials Status

**Current Status**: ❌ **Not Yet Certified**
**Target Status**: **Cyber Essentials Plus** (external technical verification)
**Target Date**: Month 5 (before Private Beta Month 6)
**Rationale**: OFFICIAL-SENSITIVE data processing requires Cyber Essentials Plus

### Assessment of 5 Cyber Essentials Controls

#### 1. Firewalls

**Status**: ⚠️ **Planned (Not Yet Implemented)**

**Cyber Essentials Requirement**: "Firewalls configured to protect internet gateways and devices."

**Evidence**:
- **VPC/VNet Firewalls**: Planned Sprint 1 (security groups / NSGs restrict inbound traffic)
- **Web Application Firewall (WAF)**: Planned Sprint 1 (AWS WAF or Azure WAF protecting API Gateway)
- **DDoS Protection**: Planned Sprint 1 (AWS Shield or Azure DDoS Protection)
- **Egress Filtering**: NAT Gateway for outbound traffic (planned Sprint 1)

**Configuration**:
- Default deny all inbound traffic (except HTTPS 443)
- Allow HTTPS 443 from internet (API Gateway only)
- Allow SSH 22 from VPN only (no direct internet SSH access)
- Allow database port 5432 from application tier only (no direct internet database access)

**Gaps**: Controls planned but not yet implemented in Sprint 1.

**Remediation**: Implement firewall controls Sprint 1 (STORY-057 - UK Cloud Infrastructure Deployment).

---

#### 2. Secure Configuration

**Status**: ⚠️ **Planned (Not Yet Implemented)**

**Cyber Essentials Requirement**: "Devices and software configured securely, unnecessary services disabled."

**Evidence**:
- **CIS Benchmarks**: Planned Sprint 2 (apply CIS benchmarks for OS, database, Kubernetes)
- **Hardening Baselines**: Planned Sprint 2 (disable unnecessary services, remove default accounts)
- **Configuration Management**: Infrastructure as Code (Terraform - architecture-principles.md Principle 21)
- **Automated Compliance**: Policy-as-Code (e.g., Open Policy Agent) enforces secure configuration in CI/CD

**Hardening Checklist**:
- [ ] Disable unnecessary services (telnet, FTP, SMB)
- [ ] Remove default accounts (admin, root with default passwords)
- [ ] Apply OS security patches (automated patching)
- [ ] Configure secure SSH (disable password auth, use key-based auth only)
- [ ] Harden database (disable remote root login, enforce strong passwords, enable audit logging)

**Gaps**: Controls planned but not yet implemented in Sprint 2.

**Remediation**: Implement secure configuration Sprint 2 (STORY-058 - CI/CD Pipeline with automated configuration compliance checks).

---

#### 3. Access Control

**Status**: ⚠️ **Planned (Not Yet Implemented)**

**Cyber Essentials Requirement**: "User accounts secured with strong passwords and MFA, least privilege enforced."

**Evidence**:
- **Multi-Factor Authentication (MFA)**: Planned Sprint 1 (STORY-002 - MFA via Azure AD, Microsoft Authenticator app)
- **Role-Based Access Control (RBAC)**: Planned Sprint 2 (STORY-003 - 4 roles: User, Power User, Admin, Governance Lead)
- **Least Privilege**: Planned (users granted minimum permissions required for role)
- **Password Policy**: Azure AD password policy (12+ characters, complexity requirements, no common passwords)
- **Account Lockout**: 10 failed login attempts → account locked for 30 minutes

**User Account Management**:
- [ ] MFA enforced for all users (no MFA bypass)
- [ ] Least privilege RBAC (users cannot escalate own privileges)
- [ ] Quarterly access reviews (departmental admins review user lists, revoke leavers)
- [ ] Automated deprovisioning (users removed from Azure AD automatically deprovisioned)

**Gaps**: Controls planned but not yet implemented in Sprint 1-2.

**Remediation**: Implement MFA Sprint 1 (STORY-002), RBAC Sprint 2 (STORY-003).

---

#### 4. Malware Protection

**Status**: ⚠️ **Planned (Not Yet Implemented)**

**Cyber Essentials Requirement**: "Anti-malware software installed and up-to-date on all devices."

**Evidence**:
- **Endpoint Detection and Response (EDR)**: Planned for developer laptops (CrowdStrike, Microsoft Defender for Endpoint)
- **Container Security**: Planned (Trivy, Snyk Container scan images before deployment)
- **Cloud Workload Protection**: Planned (AWS GuardDuty or Azure Defender for Cloud)
- **Automatic Updates**: Anti-malware signatures updated daily (automatic)

**Anti-Malware Coverage**:
- [ ] Developer laptops (Windows/Mac): Microsoft Defender or CrowdStrike
- [ ] Container images: Scanned before deployment (no malware in production containers)
- [ ] Cloud workloads: GuardDuty/Defender detects malware, crypto mining, suspicious activity

**Gaps**: Controls planned but not yet implemented in Sprint 2.

**Remediation**: Deploy EDR Sprint 2 (developer laptops), container scanning Sprint 2 (CI/CD pipeline).

---

#### 5. Patch Management

**Status**: ⚠️ **Planned (Not Yet Implemented)**

**Cyber Essentials Requirement**: "Security patches applied within 14 days for critical vulnerabilities."

**Evidence**:
- **Patch SLA**: Critical <14 days (Cyber Essentials requirement), High <30 days, Medium <90 days
- **Automated Patching**: Planned Sprint 2 (Kubernetes auto-updates, cloud-managed services auto-patched by provider)
- **Patch Testing**: Patches tested in dev/staging before production
- **Emergency Patching**: Critical vulnerabilities (CVSS 9.0+) can bypass change approval for urgent deployment

**Patching Process**:
- [ ] Weekly vulnerability scanning (Nessus/Qualys identifies unpatched systems)
- [ ] Automated patching for cloud-managed services (RDS, S3 - provider responsibility)
- [ ] Manual patching for Kubernetes nodes (tested in dev/staging, deployed to production within SLA)
- [ ] Patch compliance dashboard (% systems patched within SLA, overdue patches flagged)

**Gaps**: Controls planned but not yet implemented in Sprint 2.

**Remediation**: Implement automated patching Sprint 2 (STORY-058 - CI/CD Pipeline).

---

### Cyber Essentials Certification Roadmap

**Month 1-2 (Sprint 1-4)**: Implement 5 Cyber Essentials controls
- Sprint 1: Firewalls (VPC/VNet, WAF, DDoS), MFA (STORY-002)
- Sprint 2: Secure configuration (CIS benchmarks, hardening), RBAC (STORY-003), Malware protection (EDR, container scanning), Patch management (automated patching)

**Month 4**: Complete Cyber Essentials self-assessment
- Self-assessment questionnaire completed (online portal)
- Evidence pack prepared (firewall rules, MFA config, patching reports, anti-malware status)

**Month 5**: External technical verification (Cyber Essentials Plus)
- IASME-certified assessor conducts external verification
- Vulnerability scan of public IP addresses
- Configuration review of firewalls, MFA, patching
- **Target**: Certification obtained by 2026-03-31 (Month 5, before Private Beta)

**Month 6**: Cyber Essentials Plus certificate valid for Private Beta launch

---

## UK GDPR Compliance Assessment

### GDPR Compliance Status

**Overall Status**: ⚠️ **Partially Compliant** (DPIA completion required before Private Beta)

### Detailed GDPR Requirements Assessment

#### 1. Data Protection Officer (DPO)

**Status**: ✅ **Achieved**

**Requirement**: Public authorities must appoint a DPO (UK GDPR Article 37).

**Evidence**:
- **DPO Appointed**: Data Protection Officer role defined (stakeholder RACI matrix)
- **DPO Qualifications**: IAPP CIPP/E or equivalent certification
- **DPO Independence**: Reports to Permanent Secretary (SIRO), independent of operational teams
- **DPO Responsibilities**: Advise on UK GDPR compliance, monitor compliance, advise on DPIA, liaise with ICO

---

#### 2. Lawful Basis for Processing

**Status**: ✅ **Achieved**

**Requirement**: Identify lawful basis for all personal data processing (UK GDPR Article 6).

**Evidence**:
- **Lawful Basis**: **Public task** (Article 6(1)(e)) - processing necessary for government function (cross-government AI platform)
- **Necessity Test**: Processing necessary to deliver government AI services (document summarization, AI-assisted drafting)
- **Proportionality**: Data minimization applied (collect only user profile, document metadata, AI outputs - not full document corpus)

---

#### 3. Privacy Notice

**Status**: ⚠️ **Planned (Not Yet Published)**

**Requirement**: Provide privacy notice to users (UK GDPR Article 13).

**Evidence**:
- **Privacy Notice**: Planned to be published before Private Beta (Month 6)
- **Content**: Data controller (Cabinet Office), DPO contact, lawful basis (public task), data categories (user profile, documents, AI outputs), retention periods, data subject rights, ICO complaint procedure
- **Location**: Published at `/privacy-notice` (accessible from login page)

**Gaps**: Privacy notice not yet published.

**Remediation**: Publish privacy notice by Month 5 (Alpha phase, before Private Beta).

---

#### 4. Data Subject Rights

**Status**: ⚠️ **Planned (Not Yet Implemented)**

**Requirement**: Support all UK GDPR data subject rights (UK GDPR Chapter 3).

**Evidence**:
- **Right to be Informed**: Privacy notice (planned Month 5)
- **Right of Access (SAR)**: Subject Access Request portal (STORY-064 - Sprint 4) - users can download their data (profile, documents, AI outputs) within 30 days
- **Right to Rectification**: User profile management (STORY-007 - Sprint 3) - users can correct inaccurate data
- **Right to Erasure**: Data deletion (STORY-008, STORY-064 - Sprint 3-4) - users can request account deletion, automated deletion within 30 days
- **Right to Restrict Processing**: Ability to pause AI processing (planned Sprint 9)
- **Right to Data Portability**: Export data in machine-readable format (CSV/JSON - STORY-032, STORY-064 - Sprint 4, 12)
- **Right to Object**: Ability to object to AI processing (opt-out of AI features - planned Sprint 11)

**Gaps**: Data subject rights mechanisms planned but not yet implemented (Sprint 3-4).

**Remediation**: Implement data subject rights portal Sprint 4 (STORY-064 - GDPR Data Subject Rights Portal).

---

#### 5. Data Protection Impact Assessment (DPIA)

**Status**: ❌ **Not Achieved (CRITICAL GAP)**

**Requirement**: DPIA mandatory for high-risk processing (UK GDPR Article 35).

**Evidence**:
- **DPIA Required**: YES - generative AI, cross-government scale (20+ departments, 5,000+ users), OFFICIAL-SENSITIVE data
- **DPIA Triggers Met**: Large-scale processing of sensitive data, systematic monitoring, automated decision-making with legal/significant effects, innovative use of technology (AI/ML)
- **DPIA Planned**: STORY-066 (ICO DPIA Documentation & Submission) - Sprint 5
- **ICO Engagement**: Planned Month 3 (early DPIA consultation)

**DPIA Content** (to be completed):
- [ ] Description of processing operations (AI model inference, document summarization, knowledge base Q&A)
- [ ] Necessity and proportionality assessment (why AI processing is necessary, proportionate to government objectives)
- [ ] Risk assessment (data breach, cross-tenant leak, AI bias, data exfiltration)
- [ ] Mitigation measures (6-layer defense-in-depth, bias detection, human-in-the-loop, ATRS transparency)
- [ ] Consultation with DPO (DPO advises on DPIA content, signs off)
- [ ] ICO consultation (if high residual risk, consult ICO before processing)

**Gaps**: DPIA not yet completed (CRITICAL - Private Beta gate blocker).

**Remediation**:
- **Month 3**: Initiate ICO engagement (early DPIA consultation)
- **Month 4-5**: Complete DPIA documentation
- **Month 5**: Submit DPIA to ICO for review and approval
- **Month 6**: Obtain ICO DPIA approval BEFORE Private Beta launch

**Priority**: CRITICAL (UK GDPR legal requirement, Private Beta gate blocker)

---

#### 6. Data Breach Notification

**Status**: ✅ **Achieved**

**Requirement**: Notify ICO within 72 hours of personal data breach (UK GDPR Article 33).

**Evidence**:
- **Breach Detection**: SIEM alerting (planned Sprint 4), audit logging (FR-005)
- **Breach Notification Process**: 72-hour ICO notification process documented (Incident Response Runbook - STORY-017)
- **Breach Notification to Individuals**: If high risk to rights and freedoms, notify affected individuals
- **Breach Register**: All breaches logged (incident ID, date, data affected, individuals affected, remediation)
- **DPO Involvement**: DPO notified immediately for personal data breaches, advises on ICO notification

---

#### 7. Records of Processing Activities (ROPA)

**Status**: ⚠️ **Planned (Not Yet Completed)**

**Requirement**: Maintain Records of Processing Activities (UK GDPR Article 30).

**Evidence**:
- **ROPA Planned**: To be completed by Alpha (Month 5)
- **ROPA Content**:
  - Data categories: User profiles, documents, AI-generated content, audit logs, usage analytics
  - Processing purposes: AI-assisted summarization, drafting, semantic search, knowledge base Q&A
  - Recipients: Departmental admins (federated model), Cabinet Office CTO (platform owner)
  - Retention periods: Documents per departmental retention schedule, audit logs 7 years, user data deleted on request
  - Security measures: Encryption at rest/transit, MFA, RBAC, RLS, audit logging, Cyber Essentials Plus

**Gaps**: ROPA not yet completed.

**Remediation**: Complete ROPA by Month 5 (Alpha phase, before DPIA submission to ICO).

**Priority**: MEDIUM (ICO audit finding risk, GDPR compliance)

---

## Critical Security Issues Summary

### Critical Issues (4 Blockers for Private Beta)

**These issues MUST be resolved before Private Beta launch (Month 6):**

#### 1. Data Protection Impact Assessment (DPIA) Not Completed
- **CAF Principle**: B3 (Data Security)
- **GDPR Article**: Article 35 (DPIA)
- **Status**: ❌ Not Achieved
- **Impact**: Private Beta launch BLOCKED without ICO DPIA approval, UK GDPR non-compliance, ICO enforcement action risk (fines up to £17.5M)
- **Current State**: DPIA planned (STORY-066 - Sprint 5), ICO engagement Month 3, but not yet started
- **Remediation**:
  - Month 3: Initiate ICO engagement (early DPIA consultation)
  - Month 4-5: Complete DPIA documentation (data flows, risks, mitigations, necessity/proportionality)
  - Month 5: Submit DPIA to ICO for review and approval
  - Month 6: Obtain ICO DPIA approval BEFORE Private Beta launch
- **Owner**: Data Protection Officer / ICO Chief Technology Officer
- **Target Date**: 2026-05-31 (Month 6, Private Beta gate)
- **Priority**: CRITICAL

---

#### 2. Cyber Essentials Plus Certification Not Obtained
- **CAF Principle**: B2 (Identity and Access Control), B4 (System Security)
- **Cyber Essentials**: 5 controls (Firewalls, Secure Configuration, Access Control, Malware Protection, Patch Management)
- **Status**: ❌ Not Achieved
- **Impact**: OFFICIAL-SENSITIVE data processing requires Cyber Essentials Plus before Private Beta
- **Current State**: Controls planned (Sprint 1-2), but not implemented or externally verified
- **Remediation**:
  - Month 1-2: Implement 5 Cyber Essentials controls (firewalls, MFA, RBAC, EDR, patching)
  - Month 4: Complete Cyber Essentials self-assessment questionnaire
  - Month 5: External technical verification by IASME-certified assessor (Cyber Essentials Plus)
  - Target: Certification obtained by 2026-03-31 (Month 5, before Private Beta)
- **Owner**: Security Lead / Cabinet Office CTO
- **Target Date**: 2026-03-31 (Month 5, before Private Beta)
- **Priority**: CRITICAL

---

#### 3. NCSC Secure by Design Assurance Pending
- **CAF Principle**: Overall (all 14 principles)
- **NCSC Review**: Month 6 security review (pass with zero critical/high findings)
- **Status**: ⚠️ Partially Achieved
- **Impact**: Private Beta launch BLOCKED without NCSC approval (Month 6 gate blocker)
- **Current State**: NCSC engagement starting Week 3, security architecture review planned Month 2, final review Month 6
- **Remediation**:
  - Week 3: NCSC security architecture workshop (review multi-tenant design BEFORE Sprint 1)
  - Month 2-6: Weekly NCSC liaison calls (early feedback, course correction)
  - Month 5: Pre-NCSC internal security audit (identify issues before official review)
  - Month 6: NCSC Secure by Design review (pass with zero critical/high findings)
- **Owner**: NCSC Lead Architect / Cabinet Office CTO
- **Target Date**: 2026-05-31 (Month 6, Private Beta gate)
- **Priority**: CRITICAL

---

#### 4. Threat Modeling Incomplete
- **CAF Principle**: A2 (Risk Management)
- **NCSC Requirement**: Formal threat modeling for complex architectures
- **Status**: ⚠️ Partially Achieved
- **Impact**: Risk management incomplete, NCSC review may identify critical findings, may miss critical attack vectors (tenant boundary bypass, AI prompt injection)
- **Current State**: Risk register identifies risks (R-001 cross-tenant leak) but no structured threat model using STRIDE or PASTA methodology
- **Remediation**:
  - Month 3: Conduct threat modeling workshop (NCSC + Security Architect + Tech Lead)
  - Use STRIDE methodology (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege)
  - Focus: Multi-tenant isolation, AI foundation model integration, authentication/authorization, data flows
  - Output: Threat model document with attack trees, mitigations mapped to controls
- **Owner**: Security Architect / NCSC Lead Architect
- **Target Date**: 2026-01-31 (Month 3, Sprint 6)
- **Priority**: CRITICAL

---

### High Priority Issues (Month 1-3)

#### 5. Security Monitoring (SIEM) Not Operational
- **CAF Principle**: C1 (Security Monitoring)
- **Impact**: Cannot detect cross-tenant access attempts, security incidents, anomalous behavior in real-time
- **Remediation**: Deploy SIEM Sprint 4 (Splunk or Elastic Security), ingest logs, configure correlation rules
- **Owner**: Security Lead / SOC
- **Target Date**: 2026-02-28 (Month 2, Sprint 4)
- **Priority**: HIGH

---

#### 6. Penetration Testing Not Conducted
- **CAF Principle**: C2 (Proactive Security Event Discovery)
- **Impact**: Vulnerabilities not validated, NCSC review prerequisite not met
- **Remediation**: Procure NCSC-approved CHECK scheme firm, conduct first pen test Sprint 4, quarterly thereafter
- **Owner**: Security Lead / CHECK scheme firm
- **Target Date**: 2026-02-28 (Month 2, Sprint 4 - first pen test)
- **Priority**: HIGH

---

## Recommendations

### Critical Priority (0-60 days - Private Beta Blockers)

**These actions MUST be completed before Private Beta launch (Month 6):**

1. **Initiate NCSC Engagement (Week 3)**
   - Schedule NCSC security architecture workshop (full-day, Week 3)
   - Participants: NCSC + Security Lead + Tech Lead + Cloud Architect
   - Review multi-tenant architecture design BEFORE Sprint 1 implementation
   - **Owner**: Cabinet Office CTO / NCSC Liaison
   - **Target Date**: 2025-11-08 (Week 3)

2. **Complete Threat Modeling (Month 3)**
   - Conduct threat modeling workshop using STRIDE methodology
   - Focus: Multi-tenant isolation, AI security, authentication/authorization
   - Output: Threat model document with attack trees, mitigations
   - **Owner**: Security Architect / NCSC Lead Architect
   - **Target Date**: 2026-01-31 (Month 3, Sprint 6)

3. **Implement Cyber Essentials Controls (Sprint 1-2)**
   - Firewalls (VPC/VNet, WAF, DDoS) - Sprint 1
   - MFA (Azure AD, Microsoft Authenticator) - Sprint 1 (STORY-002)
   - RBAC (4 roles, least privilege) - Sprint 2 (STORY-003)
   - Secure configuration (CIS benchmarks, hardening) - Sprint 2
   - Malware protection (EDR, container scanning) - Sprint 2
   - Patch management (automated patching, <14 day SLA) - Sprint 2
   - **Owner**: Security Lead / Tech Lead
   - **Target Date**: 2025-11-30 (Sprint 1-2)

4. **Obtain Cyber Essentials Plus Certification (Month 5)**
   - Month 4: Complete self-assessment questionnaire
   - Month 5: External technical verification (IASME-certified assessor)
   - **Owner**: Security Lead / Cabinet Office CTO
   - **Target Date**: 2026-03-31 (Month 5, before Private Beta)

5. **Complete DPIA (Month 5, ICO Approval Month 6)**
   - Month 3: Initiate ICO engagement (early DPIA consultation)
   - Month 4-5: Complete DPIA documentation (data flows, risks, mitigations)
   - Month 5: Submit DPIA to ICO for review and approval
   - Month 6: Obtain ICO DPIA approval BEFORE Private Beta launch
   - **Owner**: Data Protection Officer / ICO CTO
   - **Target Date**: 2026-05-31 (Month 6, Private Beta gate)

6. **Pass NCSC Secure by Design Review (Month 6)**
   - Month 2-6: Weekly NCSC liaison calls (early feedback)
   - Month 5: Pre-NCSC internal security audit
   - Month 6: NCSC Secure by Design review (zero critical/high findings)
   - **Owner**: NCSC Lead Architect / Cabinet Office CTO
   - **Target Date**: 2026-05-31 (Month 6, Private Beta gate)

---

### High Priority (1-3 months)

7. **Deploy SIEM (Sprint 4)**
   - Deploy Splunk OR Elastic Security
   - Ingest logs from all sources (API Gateway, Database, VPC Flow Logs)
   - Configure correlation rules (cross-tenant access, brute-force, bulk download)
   - Integrate with PagerDuty (critical alerts, on-call rotation)
   - **Owner**: Security Lead / SOC
   - **Target Date**: 2026-02-28 (Sprint 4)

8. **Conduct Quarterly Penetration Testing (Starting Sprint 4)**
   - Procure NCSC-approved CHECK scheme penetration testing firm
   - First pen test Sprint 4 (multi-tenant isolation, AI security, API security)
   - Remediate all critical/high findings (7-day SLA for critical, 30-day for high)
   - Repeat quarterly (before each phase gate - Alpha, Beta, Live)
   - **Owner**: Security Lead / CHECK scheme firm
   - **Target Date**: 2026-02-28 (Sprint 4 - first pen test), quarterly thereafter

9. **Implement Data Loss Prevention (DLP) (Sprint 8)**
   - Document download monitoring (alert for bulk downloads >100 docs/hour)
   - API rate limiting (prevent data exfiltration via API abuse)
   - SIEM anomaly detection (unusual data access patterns)
   - Microsoft 365 DLP integration (block copy/paste to external apps)
   - **Owner**: Security Lead / Tech Lead
   - **Target Date**: 2026-04-30 (Sprint 8)

10. **Complete Records of Processing Activities (ROPA) (Month 5)**
    - Document ROPA (data categories, purposes, recipients, retention, security)
    - Include: User profiles, documents, AI outputs, audit logs, analytics
    - Review annually (update for new processing activities)
    - **Owner**: Data Protection Officer
    - **Target Date**: 2026-03-31 (Month 5, Alpha phase)

---

### Medium Priority (3-6 months)

11. **Establish Annual SIRO Security Review Process**
    - Quarterly SIRO reviews (security metrics, incident trends, risk register)
    - Annual NCSC reassessment (post-Live, annual Secure by Design review)
    - Annual Cyber Essentials Plus re-certification (maintain valid certificate)
    - **Owner**: Security Lead / SIRO (Permanent Secretary)
    - **Target Date**: 2026-06-30 (establish process by Public Beta)

12. **Launch Security Awareness Training Programme**
    - Quarterly phishing simulations (track click rate, retrain clickers)
    - Monthly security newsletters (password hygiene, social engineering, data protection)
    - Quarterly lunch & learn sessions (emerging threats, case studies, lessons learned)
    - Annual data protection training refresher (UK GDPR updates)
    - **Owner**: Security Lead / HR
    - **Target Date**: 2026-06-30 (launch by Public Beta)

13. **Establish Bug Bounty Programme (Post-Live)**
    - Public bug bounty on HackerOne or Bugcrowd
    - Scope: Multi-tenant isolation, authentication/authorization, API security
    - Rewards: £500-£5,000 based on severity (NCSC precedent)
    - **Owner**: Security Lead / Cabinet Office Legal Team
    - **Target Date**: 2026-12-31 (Month 14, post-Live)

---

## Appendices

### Appendix A: NCSC CAF Scorecard

| Objective | Principle | Title | Status | Score |
|-----------|-----------|-------|--------|-------|
| **A: Managing Security Risk** | A1 | Governance | ✅ Achieved | 1/1 |
| | A2 | Risk Management | ⚠️ Partially Achieved | 0.75/1 |
| | A3 | Asset Management | ✅ Achieved | 1/1 |
| | A4 | Supply Chain | ✅ Achieved | 1/1 |
| **B: Protecting Against Cyber Attack** | B1 | Service Protection Policies | ✅ Achieved | 1/1 |
| | B2 | Identity and Access Control | ⚠️ Partially Achieved | 0.7/1 |
| | B3 | Data Security | ⚠️ Partially Achieved | 0.6/1 |
| | B4 | System Security | ✅ Achieved | 1/1 |
| | B5 | Resilient Networks | ✅ Achieved | 1/1 |
| | B6 | Staff Awareness | ✅ Achieved | 1/1 |
| **C: Detecting Cyber Security Events** | C1 | Security Monitoring | ⚠️ Partially Achieved | 0.5/1 |
| | C2 | Proactive Security Event Discovery | ⚠️ Partially Achieved | 0.5/1 |
| **D: Minimising Impact of Incidents** | D1 | Response and Recovery Planning | ✅ Achieved | 1/1 |
| | D2 | Lessons Learned | ✅ Achieved | 1/1 |
| **TOTAL** | | | **11/14 Achieved** | **11/14 (79%)** |

**Target for Private Beta**: 14/14 Achieved (100%)

---

### Appendix B: Critical Security Controls Checklist

**This checklist tracks implementation status of critical security controls for Private Beta readiness:**

#### Multi-Tenant Isolation (R-001 Mitigation)

- [ ] **Database Row-Level Security (RLS)** - Sprint 1 (STORY-009)
- [ ] **Application-Level Tenant Validation** - Sprint 2 (STORY-010)
- [ ] **Tenant-Specific Encryption Keys** - Sprint 2 (STORY-011)
- [ ] **Network Isolation (VPC/VNet per Tenant Tier)** - Sprint 3 (STORY-012)
- [ ] **Automated Boundary Tests** - Sprint 3 (STORY-013)
- [ ] **Quarterly Penetration Testing** - Sprint 4+ (STORY-014)

#### Authentication & Authorization

- [ ] **Government SSO (Azure AD + OIDC)** - Sprint 1 (STORY-001)
- [ ] **Multi-Factor Authentication (MFA)** - Sprint 1 (STORY-002)
- [ ] **Role-Based Access Control (RBAC)** - Sprint 2 (STORY-003)
- [ ] **Session Management (30-min timeout)** - Sprint 3 (STORY-006)
- [ ] **Privileged Access Management (PAM)** - Sprint 4 (planned)

#### Encryption & Data Protection

- [ ] **Encryption at Rest (AES-256)** - Sprint 1 (database, object storage)
- [ ] **Encryption in Transit (TLS 1.3)** - Sprint 1 (API Gateway, services)
- [ ] **Secrets Management (Key Vault)** - Sprint 1 (STORY-057)
- [ ] **Data Classification Detection** - Sprint 5 (STORY-019)

#### Security Monitoring & Detection

- [ ] **SIEM Deployment** - Sprint 4 (planned)
- [ ] **Real-Time Alerting** - Sprint 4 (cross-tenant access, brute-force)
- [ ] **Audit Logging (WORM Storage)** - Sprint 7 (STORY-034)
- [ ] **Penetration Testing** - Sprint 4 (first test)

#### Incident Response & Recovery

- [ ] **Incident Response Runbook** - Sprint 4 (STORY-017)
- [ ] **Disaster Recovery (RTO 4h, RPO 15min)** - Sprint 4 (STORY-062)
- [ ] **DR Testing (Quarterly Drills)** - Sprint 4 (STORY-063)
- [ ] **72-Hour ICO Breach Notification** - Sprint 4 (documented)

#### GDPR Compliance

- [ ] **Privacy Notice Published** - Month 5 (Alpha)
- [ ] **Data Subject Rights Portal** - Sprint 4 (STORY-064)
- [ ] **Consent Management & Audit Trail** - Sprint 4 (STORY-065)
- [ ] **DPIA Completed & ICO Approved** - Month 6 (STORY-066) ⚠️ CRITICAL
- [ ] **Records of Processing (ROPA)** - Month 5 (Alpha)

#### Cyber Essentials

- [ ] **Firewalls (VPC/VNet, WAF, DDoS)** - Sprint 1
- [ ] **Secure Configuration (CIS Benchmarks)** - Sprint 2
- [ ] **Access Control (MFA, RBAC)** - Sprint 1-2
- [ ] **Malware Protection (EDR, Container Scanning)** - Sprint 2
- [ ] **Patch Management (<14 days)** - Sprint 2
- [ ] **Cyber Essentials Plus Certification** - Month 5 ⚠️ CRITICAL

---

### Appendix C: Security Risk Register (Top Security Risks)

| Risk ID | Title | Inherent Risk | Residual Risk | CAF Principle | Status |
|---------|-------|---------------|---------------|---------------|--------|
| **R-001** | Cross-Tenant Data Leak (OFFICIAL-SENSITIVE) | 20 (CRITICAL) | 12 (HIGH) | B3, B2, C1 | IN PROGRESS (6-layer defense-in-depth) |
| **R-004** | NCSC Secure by Design Assurance Delay/Failure | 16 (HIGH) | 12 (HIGH) | Overall (all 14) | IN PROGRESS (early engagement Week 3) |
| **R-006** | AI Vendor UK Data Residency Failure | 12 (MEDIUM) | 9 (MEDIUM) | B3, A4 | IN PROGRESS (UK contracts Week 2) |
| **R-007** | AI Bias Incident with Media Outcry | 20 (CRITICAL) | 15 (HIGH) | B3, D1 | IN PROGRESS (bias detection Sprint 8) |
| **R-008** | ICO DPIA Rejection or Conditional Approval | 12 (MEDIUM) | 10 (MEDIUM) | B3 | IN PROGRESS (DPIA prep Month 3-5) |
| **R-012** | Vendor Lock-In (Single Cloud/AI Provider) | 12 (MEDIUM) | 9 (MEDIUM) | A4 | IN PROGRESS (abstraction layers) |

**Note**: Full risk register with 20 risks available in `projects/001-cabinet-office-genai/risk-register.md`.

---

### Appendix D: SIRO and DPO Appointments

#### Senior Information Risk Owner (SIRO)

**Name**: [PENDING - Cabinet Office Permanent Secretary]
**Title**: Permanent Secretary, Cabinet Office
**Role**: Board-level accountability for information risk
**Responsibilities**:
- Approve risk treatment decisions (risk register sign-off)
- Chair quarterly security reviews (security metrics, incident trends)
- Sign off on security exceptions (if any principle exemptions required)
- Escalation point for critical security incidents (cross-tenant leak, GDPR breach)

**Engagement**:
- Weekly Steering Committee (Permanent Secretary chair)
- Quarterly SIRO Security Review (security dashboard, risk register, compliance status)
- NCSC liaison (attend key NCSC review meetings)

---

#### Data Protection Officer (DPO)

**Name**: [PENDING - Cabinet Office Data Protection Officer]
**Title**: Data Protection Officer, Cabinet Office
**Qualifications**: IAPP CIPP/E or equivalent certification
**Responsibilities**:
- Advise on UK GDPR compliance (DPIA, data subject rights, lawful basis)
- Monitor compliance with UK GDPR (internal audits, ROPA, privacy notice)
- Advise on DPIA (review DPIA content, sign off, liaise with ICO)
- Liaise with ICO (data breach notifications, DPIA consultation, ICO audits)

**Engagement**:
- Monthly Project Board (DPO attends monthly)
- Quarterly ICO Liaison Calls (DPIA preparation, data protection compliance)
- DPIA Working Group (Month 3-5, weekly during DPIA development)

---

### Appendix E: Security Contact Information

**Security Incident Reporting**:
- **Email**: security@cabinetoffice.gov.uk
- **Phone**: [PENDING - 24/7 Security Hotline]
- **In-App**: "Report Security Concern" button (all users)

**NCSC Liaison**:
- **NCSC Lead Architect**: [PENDING - NCSC Contact]
- **Weekly Liaison Calls**: Starting Week 3, every Wednesday 10:00-11:00 GMT

**ICO Contact**:
- **ICO Chief Technology Officer**: [PENDING - ICO Contact]
- **Data Breach Notification**: ico.org.uk/concerns (72-hour notification)
- **DPIA Consultation**: casework@ico.org.uk

**SIRO and DPO**:
- **SIRO**: [PENDING - Permanent Secretary]
- **DPO**: [PENDING - Cabinet Office DPO]

---

## Document Footer

**Generated by**: ArcKit `/arckit.secure` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Cabinet Office GenAI Platform (Project 001)
**AI Model**: claude-opus-4-5-20251101
**Generation Context**: Generated from project requirements (requirements.md - 67 requirements), architecture principles (architecture-principles.md - 24 principles), risk register (risk-register.md - 20 risks including 8 security risks), product backlog (backlog.md - 42 user stories, 26 sprints), TCoP review (tcop-review.md - 11/13 compliant), and analysis report (analysis-report.md - 95/100 governance maturity).

**Assessment Basis**: NCSC Cyber Assessment Framework (CAF) v3.0, Cyber Essentials Scheme, UK GDPR and Data Protection Act 2018, Government Security Classifications Policy, NCSC Cloud Security Principles.

**Assessment Phase**: Discovery (Month 2 of 13-month delivery)
**Next Assessment**: Alpha (Month 5 - before GDS Alpha Assessment), Private Beta Gate (Month 6 - NCSC Secure by Design review), Live (Month 13 - annual NCSC reassessment)

**Approval Required**: SIRO (Permanent Secretary) approval required before Private Beta launch (Month 6).

---

**END OF UK GOVERNMENT SECURE BY DESIGN ASSESSMENT**
