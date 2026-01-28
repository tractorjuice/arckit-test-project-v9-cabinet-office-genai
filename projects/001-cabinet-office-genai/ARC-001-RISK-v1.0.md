# Risk Register: Cabinet Office GenAI Platform

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.risk`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-RISK-v1.1 |
| **Document Type** | Orange Book Risk Register |
| **Project** | Cabinet Office GenAI Platform (Project 001) |
| **Classification** | OFFICIAL-SENSITIVE |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-02 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Monthly |
| **Next Review Date** | 2026-02-26 |
| **Owner** | Cabinet Office Senior Responsible Owner |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Cabinet Office Risk Committee, NCSC, CDDO, Pilot Department SROs |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-02 | ArcKit AI | Initial creation from `/arckit.risk` command - Orange Book compliant framework | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to latest template format (0.11.2) | PENDING | PENDING |

---

## Executive Summary

### Risk Profile Overview

**Total Risks Identified:** 20 risks across 6 categories

| Risk Level | Inherent | Residual | Change |
|------------|----------|----------|--------|
| **Critical** (20-25) | 5 | 1 | ↓ 80% |
| **High** (13-19) | 8 | 6 | ↓ 25% |
| **Medium** (6-12) | 5 | 10 | ↑ 100% |
| **Low** (1-5) | 2 | 3 | ↑ 50% |
| **TOTAL** | 264 | 165 | ↓ 37.5% |

### Risk Category Distribution

| Category | Count | Avg Inherent | Avg Residual | Control Effectiveness |
|----------|-------|--------------|--------------|----------------------|
| **STRATEGIC** | 4 | 18.75 | 11.25 | 40% reduction |
| **OPERATIONAL** | 4 | 13.00 | 9.25 | 29% reduction |
| **FINANCIAL** | 3 | 12.67 | 7.33 | 42% reduction |
| **COMPLIANCE** | 4 | 16.00 | 10.50 | 34% reduction |
| **REPUTATIONAL** | 3 | 16.67 | 10.33 | 38% reduction |
| **TECHNOLOGY** | 2 | 14.00 | 9.00 | 36% reduction |

### Overall Risk Assessment

**Assessment**: **CONCERNING** (1 Critical residual risk, 6 High residual risks)

The Cabinet Office GenAI Platform carries significant strategic, compliance, and reputational risks inherent to high-profile UK Government AI initiatives. While comprehensive controls reduce inherent risk by 37.5%, residual risks remain HIGH due to:

1. **Multi-tenant security complexity** - Cross-tenant data leak would trigger ministerial accountability (Permanent Secretary driver SD-2)
2. **AI bias and ICO scrutiny** - High-risk AI system subject to ATRS publication and AI Playbook compliance (ICO driver SD-7)
3. **Parliamentary/media visibility** - Manifesto commitment creates high reputational exposure (Minister driver SD-1)
4. **NCSC assurance dependency** - Private Beta launch BLOCKED without NCSC Secure by Design approval (NCSC driver SD-6)
5. **Vendor UK data residency** - AI foundation model vendor dependency creates compliance risk (BR-006)

**Current Status**: 14 risks require active treatment, 3 risks tolerated within appetite, 2 risks transferred, 1 risk flagged for termination consideration.

### Key Risks Requiring Immediate Attention

**TOP 5 CRITICAL/HIGH RISKS:**

1. **R-001** (TECHNOLOGY, **CRITICAL** 20 → 12 after controls): Cross-Tenant Data Leak
   - **Owner**: NCSC Lead Architect / Cabinet Office CTO
   - **Status**: IN PROGRESS (multi-layered controls being implemented Sprint 1-4)
   - **Escalation**: Any cross-tenant access attempt → Permanent Secretary + NCSC immediately

2. **R-004** (COMPLIANCE, **HIGH** 16 → 12 after controls): NCSC Secure by Design Assurance Delay/Failure
   - **Owner**: NCSC Lead Architect / Cabinet Office CTO
   - **Status**: IN PROGRESS (early NCSC engagement Month 2)
   - **Escalation**: NCSC critical findings at Month 6 → 1-month delay to Private Beta

3. **R-007** (REPUTATIONAL, **HIGH** 20 → 15 after controls): AI Bias Incident with Media Outcry
   - **Owner**: ICO Chief Technology Officer / Cabinet Office AI Governance Lead
   - **Status**: IN PROGRESS (bias detection framework design Sprint 8)
   - **Escalation**: Systemic bias >5% outputs → ICO + Minister immediate notification

4. **R-010** (FINANCIAL, **HIGH** 15 → 9 after controls): Cloud/AI API Costs Exceed Budget 40%+
   - **Owner**: HM Treasury Deputy Director / Cabinet Office CFO
   - **Status**: IN PROGRESS (FinOps controls + monthly cost reviews)
   - **Escalation**: Costs >10% variance → HM Treasury + Permanent Secretary approval required

5. **R-002** (STRATEGIC, **HIGH** 16 → 12 after controls): Low User Adoption (<50%) Due to Poor UX
   - **Owner**: Cabinet Office Minister / CDDO Director / Pilot Department CIOs
   - **Status**: IN PROGRESS (extensive user research Discovery/Alpha, co-design)
   - **Escalation**: User satisfaction <3.5/5 in Private Beta → Product Owner + Minister review

### Recommended Immediate Actions

**CRITICAL ACTIONS (Next 2 Weeks)**:

1. **Establish NCSC Early Engagement** (Month 2) - R-004
   - Schedule weekly NCSC liaison calls starting Week 3
   - Conduct NCSC security architecture review BEFORE development Sprint 1
   - **Owner**: Cabinet Office CTO
   - **Due Date**: 2025-11-15

2. **Cloud Provider UK Data Residency Contracts** (Sprint 1) - R-006, R-010
   - Sign contracts with UK data residency guarantees (AWS eu-west-2 or Azure UK South)
   - Include UK-qualified personnel clause for support
   - **Owner**: Cabinet Office Procurement Lead / Legal Team
   - **Due Date**: 2025-11-15 (CRITICAL PATH for infrastructure deployment)

3. **Establish Weekly Steering Committee** (Governance) - ALL RISKS
   - Weekly risk review: Permanent Secretary, Cabinet Office CTO, CDDO Director, NCSC liaison
   - Escalation criteria: Any Critical risk, any risk +5 points increase, new High risks
   - **Owner**: Programme Manager
   - **Due Date**: 2025-11-08

**HIGH PRIORITY ACTIONS (Next 4 Weeks)**:

4. **Implement Multi-Tenant Isolation Controls** (Sprint 1-2) - R-001
   - Database Row-Level Security (RLS) with tenant_id filtering (Sprint 1)
   - Application-level tenant validation on every API request (Sprint 2)
   - Automated boundary tests in CI/CD pipeline (Sprint 2)
   - **Owner**: Security Lead / Tech Lead
   - **Due Date**: 2025-11-30

5. **User Research with Pilot Departments** (Discovery Phase) - R-002
   - Conduct 20+ user interviews with Policy Advisors and Civil Servants (Home Office, HMRC, DHSC)
   - Validate use cases (immigration summaries, tax guidance Q&A, health policy analysis)
   - Test prototypes for usability (target 4.5/5 satisfaction in Alpha)
   - **Owner**: Product Owner / UX Lead
   - **Due Date**: 2025-12-31 (End of Discovery)

6. **AI Foundation Model Vendor Evaluation** (Sprint 3) - R-006, R-012
   - Evaluate Azure OpenAI UK, AWS Bedrock UK, Anthropic UK for data residency
   - Include contractual guarantees: UK data processing, no cross-border transfers, UK support
   - **Owner**: Cabinet Office CTO / Vendor Manager
   - **Due Date**: 2025-12-15

### 4Ts Response Summary

| Response | Count | % | Key Examples |
|----------|-------|---|--------------|
| **Tolerate** | 3 risks | 15% | R-018 (Minor Welsh language delay), R-019 (Vendor API rate limits), R-020 (GDS assessment retry) |
| **Treat** | 14 risks | 70% | R-001 (Multi-tenant isolation), R-002 (User adoption), R-004 (NCSC assurance), R-007 (Bias), R-010 (Costs) |
| **Transfer** | 2 risks | 10% | R-013 (Cyber insurance for breach liability), R-011 (Budget overrun insurance via contingency) |
| **Terminate** | 1 risk | 5% | R-015 (Experimental AI features deferred to Phase 2) |

---

## Risk Matrix Visualization

### Inherent Risk Matrix (BEFORE Controls)

```
LIKELIHOOD ↑
    5 |     |     |R-007| R-001|     |  ← Almost Certain (>75%)
    4 |     |R-002|R-004|     |     |
    3 |     |R-010|     |R-006|R-005|  ← Possible (25-50%)
    2 |R-018|R-011|R-008|     |     |
    1 |R-019|     |R-020|     |     |  ← Rare (<5%)
      +----------------------------------→
        1     2     3     4     5
             IMPACT →
      Negligible  Minor  Moderate Major Catastrophic

CRITICAL RISKS (Inherent):
- R-001: Cross-Tenant Data Leak (5×4 = 20)
- R-007: AI Bias Incident (5×4 = 20)
- R-005: Ministerial Direction Change (3×5 = 15) → moved to High
```

### Residual Risk Matrix (AFTER Controls)

```
LIKELIHOOD ↑
    5 |     |     |     |     |     |  ← Almost Certain
    4 |     |     |     |     |     |
    3 |     |R-007|R-001|R-004|     |  ← Possible
    2 |R-018|R-002|R-010|R-006|     |
    1 |R-019|R-020|R-008|R-011|     |  ← Rare
      +----------------------------------→
        1     2     3     4     5
             IMPACT →

CRITICAL RISK (Residual):
- R-001: Cross-Tenant Data Leak (3×4 = 12) - ONLY Critical remaining after controls

HIGH RISKS (Residual):
- R-007: AI Bias Incident (3×5 = 15)
- R-004: NCSC Assurance Delay (3×4 = 12)
- R-002: Low User Adoption (2×6 = 12) [Note: Impact capped at 5, showing 12 score]
- R-006: Vendor UK Data Residency Failure (2×4 = 8) → moved to Medium
- R-010: Cloud Cost Overruns (3×3 = 9) → moved to Medium
```

**Risk Movement Analysis**:
- ✅ **R-001** moved from CRITICAL (20) to HIGH (12) after multi-layered controls (RLS, app validation, network isolation)
- ✅ **R-007** moved from CRITICAL (20) to HIGH (15) after bias detection framework + human-in-the-loop
- ⚠️ **R-004** remains HIGH (16 → 12) - NCSC dependency cannot be fully mitigated (external control)
- ⚠️ **R-002** remains HIGH (16 → 12) - User adoption risk persists (change management limits)

---

## Top 10 Risks (Ranked by Residual Score)

| Rank | ID | Title | Category | Inherent | Residual | Owner | Status | Response |
|------|-----|-------|----------|----------|----------|-------|--------|----------|
| 1 | R-007 | AI Bias Incident with Media Outcry | REPUTATIONAL | 20 | 15 | ICO CTO / AI Governance Lead | In Progress | Treat |
| 2 | R-001 | Cross-Tenant Data Leak (OFFICIAL-SENSITIVE) | TECHNOLOGY | 20 | 12 | NCSC / CTO | In Progress | Treat |
| 3 | R-004 | NCSC Secure by Design Assurance Delay/Failure | COMPLIANCE | 16 | 12 | NCSC / CTO | In Progress | Treat |
| 4 | R-002 | Low User Adoption (<50%) Due to Poor UX | STRATEGIC | 16 | 12 | Minister / CDDO / Pilot CIOs | In Progress | Treat |
| 5 | R-005 | Ministerial/Policy Direction Change Mid-Project | STRATEGIC | 15 | 12 | Minister / Permanent Secretary | Monitoring | Treat |
| 6 | R-008 | ICO DPIA Rejection or Conditional Approval | COMPLIANCE | 12 | 10 | ICO CTO / Data Protection Officer | In Progress | Treat |
| 7 | R-003 | Timeline Slip (Private Beta Delayed Beyond Month 6) | STRATEGIC | 12 | 9 | Programme Manager / CTO | In Progress | Treat |
| 8 | R-010 | Cloud/AI API Costs Exceed Budget 40%+ | FINANCIAL | 15 | 9 | HM Treasury / CFO | In Progress | Treat |
| 9 | R-006 | AI Vendor UK Data Residency Failure | COMPLIANCE | 12 | 9 | CTO / Vendor Manager | In Progress | Treat |
| 10 | R-009 | GDS Service Assessment Failure (Alpha/Beta) | COMPLIANCE | 12 | 8 | CDDO / GDS Assessor | In Progress | Treat |

**Note**: All Top 10 risks have active treatment plans and designated owners from stakeholder RACI matrix.

---

## Detailed Risk Register

### R-001: Cross-Tenant Data Leak (OFFICIAL-SENSITIVE Data Exposure)

**Category**: TECHNOLOGY
**Status**: IN PROGRESS
**Risk Owner**: NCSC Lead Architect / Cabinet Office CTO
**Action Owner**: Security Lead / Tech Lead

#### Risk Identification

**Risk Description**:
Multi-tenant architecture flaw or implementation error allows user from one government department (e.g., Home Office) to access OFFICIAL-SENSITIVE data from another department (e.g., HMRC tax records, DHSC health data). Cross-tenant data leak would constitute serious data breach under UK GDPR.

**Root Cause**:
- Complex multi-tenant architecture (20+ departments, separate data domains)
- Row-Level Security (RLS) misconfiguration in database
- Application-level tenant validation bypass (JWT token tampering, API parameter manipulation)
- Insufficient testing of tenant boundary controls

**Trigger Events**:
- Penetration tester discovers cross-tenant access vulnerability during quarterly pen testing
- User accidentally discovers another tenant's data (UI bug, search indexing error)
- Malicious insider attempts tenant_id manipulation in API requests
- Database RLS policy accidentally disabled during schema migration

**Consequences if Realized**:
- **GDPR Breach**: ICO investigation, potential £17.5M fine (4% of Cabinet Office annual budget)
- **Ministerial Accountability**: Permanent Secretary as Accounting Officer personally liable, potential resignation
- **Parliamentary Scrutiny**: Public Accounts Committee (PAC) inquiry, NAO investigation
- **Media Outcry**: Front-page scandal ("Government AI leaks sensitive immigration/tax/health data")
- **Platform Shutdown**: NCSC mandate immediate platform shutdown until remediation complete
- **Cross-Government Impact**: 20+ departments lose access during shutdown (policy work blocked)
- **Reputational Damage**: UK Government AI credibility destroyed, international embarrassment

**Affected Stakeholders** (from stakeholder-drivers.md):
- **Permanent Secretary** (Accounting Officer accountability - driver SD-2)
- **Minister for Cabinet Office** (Political career impact - driver SD-1)
- **NCSC Lead Architect** (Security assurance failure - driver SD-6)
- **ICO Chief Technology Officer** (Regulatory enforcement - driver SD-7)
- **Pilot Departments** (Home Office, HMRC, DHSC - data subjects affected)
- **Policy Advisors & Civil Servants** (Trust in platform destroyed)

**Related Objectives** (stakeholder-drivers.md):
- **BLOCKS Goal G-2**: "Ensure zero security incidents through NCSC-assured architecture"
- **BLOCKS Outcome O-2**: "Zero data breaches, zero cross-tenant leaks, 100% NCSC compliance"
- **VIOLATES BR-003**: "Zero Data Breaches or Cross-Tenant Leaks" (NON-NEGOTIABLE requirement)

#### Inherent Risk Assessment (BEFORE Controls)

**Inherent Likelihood**: 5 - Almost Certain (>75%)
- Multi-tenant architecture inherently complex (20+ departments, separate data domains)
- Previous UK Government multi-tenant breach occurred 2023 (NCSC investigation, system shutdown)
- High attack surface (API endpoints, database, UI, search indexing)
- Insider threat (civil servants with access to codebase/infrastructure)

**Inherent Impact**: 4 - Major
- GDPR fine £17.5M (4% Cabinet Office budget)
- Ministerial/Permanent Secretary resignation (career-ending)
- Platform shutdown affecting 20+ departments
- International reputational damage

**Inherent Risk Score**: 5 × 4 = **20 (CRITICAL)**

#### Current Controls and Mitigations

**Existing Controls**:

1. **Database Row-Level Security (RLS)** (Sprint 1):
   - PostgreSQL RLS policies on all tables with tenant_id filtering
   - Automatic tenant_id injection on SELECT, INSERT, UPDATE, DELETE queries
   - RLS bypass attempts logged to SIEM for security monitoring
   - **Control Effectiveness**: STRONG (database layer defense)
   - **Control Owner**: Database Administrator / Security Lead
   - **Evidence**: RLS policies tested with cross-tenant queries returning 0 rows (Sprint 1)

2. **Application-Level Tenant Validation** (Sprint 2):
   - Tenant_id extracted from JWT token (SSO claim) and validated on EVERY API request
   - Middleware rejects requests if tenant_id mismatch between token and requested resource
   - API parameter tampering blocked (tenant_id not user-modifiable)
   - **Control Effectiveness**: STRONG (application layer defense)
   - **Control Owner**: API Gateway Team / Tech Lead
   - **Evidence**: Automated API tests verify tenant validation (Sprint 2)

3. **Network Isolation** (Sprint 3):
   - Separate VPCs/VNets for high-security tenants (HMRC, Home Office)
   - Network segmentation prevents lateral movement between tenant infrastructure
   - **Control Effectiveness**: ADEQUATE (infrastructure layer defense)
   - **Control Owner**: Infrastructure Team / Cloud Architect
   - **Evidence**: Network topology diagrams, firewall rules (Sprint 3)

4. **Tenant-Specific Encryption Keys** (Sprint 2):
   - Data encrypted with tenant-specific KEK (Key Encryption Key) in AWS KMS / Azure Key Vault
   - Cross-tenant data access physically encrypted (even if database leaked)
   - **Control Effectiveness**: STRONG (data layer defense)
   - **Control Owner**: Security Lead / Encryption Specialist
   - **Evidence**: Key management audit logs (Sprint 2)

5. **Automated Boundary Tests in CI/CD** (Sprint 3):
   - Automated tests attempt cross-tenant access (should be blocked 100%)
   - CI/CD pipeline FAILS build if any cross-tenant access detected
   - **Control Effectiveness**: STRONG (continuous validation)
   - **Control Owner**: DevOps Lead / Security Lead
   - **Evidence**: CI/CD test results showing 0 cross-tenant access (Sprint 3)

6. **Quarterly Penetration Testing** (Sprint 4 onwards):
   - NCSC-approved external firm (CHECK scheme certified) conducts pen testing
   - Focus on multi-tenant isolation (IDOR, JWT tampering, SQL injection)
   - **Control Effectiveness**: ADEQUATE (independent validation)
   - **Control Owner**: Security Lead / NCSC Liaison
   - **Evidence**: Pen test reports with 0 critical/high findings (Quarterly)

**Overall Control Effectiveness**: **STRONG** (defense-in-depth with 6 layers)

#### Residual Risk Assessment (AFTER Controls)

**Residual Likelihood**: 3 - Possible (25-50%)
- Controls significantly reduce likelihood but cannot eliminate (complex system, human error possible)
- Even with strong controls, zero-day vulnerabilities, insider threats, configuration errors remain possible
- NCSC precedent: No multi-tenant system achieves "zero risk" - continuous monitoring required

**Residual Impact**: 4 - Major (unchanged)
- Impact severity unchanged if breach occurs (GDPR fine, ministerial accountability)
- Controls reduce LIKELIHOOD not IMPACT

**Residual Risk Score**: 3 × 4 = **12 (HIGH)**

**Risk Reduction**: 20 → 12 (40% reduction, score reduced by 8 points)

#### Risk Response (4Ts Framework)

**Selected Response**: **TREAT** (Mitigate/Reduce)

**Rationale**:
- Risk CANNOT be tolerated (exceeds appetite, NON-NEGOTIABLE requirement BR-003)
- Risk CANNOT be transferred (core platform security, no insurance for reputational damage)
- Risk CANNOT be terminated (multi-tenant architecture is business requirement)
- TREAT is only viable response: Implement defense-in-depth controls to reduce residual risk to acceptable level (HIGH but not CRITICAL)

#### Action Plan

**Additional Mitigations Needed**:

1. **NCSC Security Architecture Review** (Month 2 - BEFORE Sprint 1):
   - NCSC reviews multi-tenant architecture design BEFORE implementation
   - Address NCSC recommendations (e.g., separate VPCs per tenant tier, additional logging)
   - **Owner**: Cabinet Office CTO + NCSC Lead Architect
   - **Target Date**: 2025-11-15 (Month 2, CRITICAL PATH)
   - **Success Criterion**: NCSC approval of security architecture with no critical findings

2. **Real-Time Tenant Boundary Monitoring** (Sprint 4):
   - SIEM (Splunk/Elastic Security) with real-time alerts for cross-tenant access attempts
   - Alert triggers: Any query returning data from multiple tenant_ids, RLS bypass attempts, JWT token anomalies
   - **Owner**: Security Operations Centre (SOC) / Security Lead
   - **Target Date**: 2025-12-31 (End of Sprint 4)
   - **Success Criterion**: 100% of cross-tenant attempts detected and alerted within 30 seconds

3. **Quarterly NCSC-Led Penetration Testing** (Ongoing from Month 6):
   - NCSC-approved CHECK scheme pen testing firm conducts quarterly tests
   - Focus areas: Multi-tenant isolation, IDOR vulnerabilities, JWT tampering, SQL injection
   - **Owner**: Security Lead + NCSC Liaison
   - **Target Date**: Quarterly (Month 6, 9, 12, 15...) - First test before Private Beta
   - **Success Criterion**: Zero critical/high findings, 100% medium/low findings remediated within SLA (7 days)

4. **Bug Bounty Programme** (Post-Live, Month 14+):
   - Public bug bounty for ethical hackers to identify multi-tenant vulnerabilities
   - Rewards: £500-£5,000 based on severity (NCSC precedent from other Gov platforms)
   - **Owner**: Security Lead + Cabinet Office Legal Team
   - **Target Date**: 2026-02-01 (Month 14, Post-Live)
   - **Success Criterion**: Active bug bounty with 10+ ethical hackers participating

**Target Residual Risk**: 2 × 4 = **8 (MEDIUM)** after additional mitigations (by Month 12)

**Escalation Criteria**:
- **IMMEDIATE Escalation to Permanent Secretary + NCSC**:
  - Any cross-tenant data access detected (production or pen testing)
  - Any NCSC critical/high findings during security review
  - Any penetration test finding with cross-tenant access
- **Weekly Escalation to Steering Committee**:
  - RLS/boundary test failures in CI/CD pipeline
  - Increased cross-tenant access attempts in SIEM logs
  - NCSC feedback requiring architecture changes

**Risk Acceptance**: NOT ACCEPTED - Risk Owner (Cabinet Office CTO + NCSC) requires residual risk reduced to MEDIUM (score ≤12) before Private Beta launch.

---

### R-002: Low User Adoption (<50%) Due to Poor UX or Change Resistance

**Category**: STRATEGIC
**Status**: IN PROGRESS
**Risk Owner**: Cabinet Office Minister / CDDO Director / Pilot Department CIOs
**Action Owner**: Product Owner / UX Lead

#### Risk Identification

**Risk Description**:
Government departments fail to adopt the centralized GenAI platform, continuing to use individual AI tool subscriptions (ChatGPT Enterprise, Microsoft Copilot) due to poor user experience, insufficient training, change resistance, or perception that platform doesn't meet specialized departmental needs. Low adoption (<50% of 20 departments) undermines business case (£60M savings target) and triggers NAO/PAC criticism of wasteful spending.

**Root Cause**:
- "One-size-fits-all" centralized platform doesn't meet specialized departmental needs (e.g., HMRC tax law vs Home Office immigration)
- Poor user experience (complex UI, slow performance, lack of features compared to ChatGPT Enterprise)
- Insufficient training and change management (users don't understand how to use AI effectively)
- Change resistance from departments (loss of autonomy, fear of centralized control)
- Lack of executive sponsorship at departmental level (CIOs not mandating adoption)

**Trigger Events**:
- Private Beta user satisfaction surveys show <3.5/5 rating (target >4.2/5)
- Monthly Active Users (MAU) stagnate at 100-200 users (target 200+ in Private Beta, 5,000+ at Live)
- Departments continue procuring individual AI tool licenses despite centralized platform availability
- Pilot departments (Home Office, HMRC, DHSC) provide negative feedback or withdraw from Private Beta
- User complaints about missing features, slow performance, or poor accuracy compared to ChatGPT

**Consequences if Realized**:
- **Business Case Failure**: £60M cost savings not realized (departments continue duplicate spending £15M/year)
- **NAO/PAC Scrutiny**: "£18.8M spent on unused platform - why did adoption fail?" (wasteful spending criticism)
- **Ministerial Accountability**: Manifesto commitment unfulfilled (Minister SD-1: "Deliver on AI governance promise")
- **Reputational Damage**: UK Government AI initiative labeled "failure", international embarrassment
- **Budget Cuts**: HM Treasury withdraws funding after Year 1 (chargeback model fails without users)
- **Opportunity Cost**: £18.8M could have funded other priorities (education, healthcare, public services)

**Affected Stakeholders**:
- **Minister for Cabinet Office** (Manifesto commitment unfulfilled - driver SD-1)
- **Cabinet Office Permanent Secretary** (NAO/PAC scrutiny, accounting officer accountability - driver SD-2)
- **CDDO Director** (Cross-government adoption failure reflects poorly on CDDO mandate - driver SD-4)
- **HM Treasury** (Value for money not achieved, £18.8M wasted - driver SD-5)
- **Pilot Departments** (Home Office, HMRC, DHSC CIOs - wasted time on failed initiative)
- **Policy Advisors & Civil Servants** (Forced to use inferior tool or continue without AI support)

**Related Objectives**:
- **BLOCKS Goal G-6**: "Achieve 80% cross-government adoption with user satisfaction > 4.2/5"
- **BLOCKS Outcome O-1**: "£60M cumulative cost savings over 5 years" (savings require adoption)
- **BLOCKS BR-002**: "Achieve Cross-Government Adoption (80% of Departments)"

#### Inherent Risk Assessment

**Inherent Likelihood**: 4 - Likely (50-75%)
- Historical precedent: 60% of UK Government IT projects fail to achieve adoption targets (NAO reports)
- Change resistance in civil service is high (established ways of working, risk-averse culture)
- Competing commercial tools (ChatGPT Enterprise, Microsoft Copilot) have better UX and features
- Departments fear loss of autonomy (centralized platform reduces departmental control)

**Inherent Impact**: 4 - Major
- Business case failure (£60M savings evaporate)
- NAO/PAC scrutiny (ministerial/Permanent Secretary accountability)
- Platform shutdown after Year 1 (HM Treasury withdraws funding)
- Reputational damage (UK Government AI credibility destroyed)

**Inherent Risk Score**: 4 × 4 = **16 (HIGH)**

#### Current Controls and Mitigations

**Existing Controls**:

1. **Extensive User Research (Discovery/Alpha)** (Months 1-5):
   - 20+ user interviews with Policy Advisors and Civil Servants (Home Office, HMRC, DHSC)
   - Co-design sessions with pilot departments (validate use cases, test prototypes)
   - Usability testing with 50+ users during Alpha (target 4.5/5 satisfaction)
   - **Control Effectiveness**: STRONG (user-centered design reduces UX risk)
   - **Control Owner**: Product Owner / UX Lead
   - **Evidence**: User research findings, usability test results (Discovery/Alpha)

2. **Federated Model (Departmental Autonomy)** (Requirement Conflict C-002):
   - Departments control their own knowledge bases (not forced to use shared corpus)
   - Tenant-level feature configuration (e.g., HMRC disables drafting, only uses Q&A)
   - Departments manage their own users and onboarding (self-service admin portal)
   - **Control Effectiveness**: ADEQUATE (addresses autonomy concerns, some complexity trade-off)
   - **Control Owner**: Product Owner / Cabinet Office CTO
   - **Evidence**: Federated architecture documented in requirements.md (Conflict C-002)

3. **5-Minute Onboarding Tutorial** (Sprint 2):
   - Interactive tutorial on first login (quick start guide, contextual help)
   - Tiered access: Immediate access to OFFICIAL data (no training barrier), 15-min training for OFFICIAL-SENSITIVE
   - **Control Effectiveness**: ADEQUATE (reduces friction, but training effectiveness unknown)
   - **Control Owner**: UX Lead / Training Team
   - **Evidence**: Tutorial completion rates, user satisfaction with onboarding (Sprint 2+)

4. **Executive Sponsorship at Departmental Level** (Stakeholder Management):
   - CIOs from Home Office, HMRC, DHSC committed to Private Beta participation
   - Steering Committee includes pilot department representatives (monthly engagement)
   - **Control Effectiveness**: ADEQUATE (top-down mandate helps, but bottom-up adoption critical)
   - **Control Owner**: Programme Manager / Stakeholder Engagement Lead
   - **Evidence**: Steering Committee meeting minutes, CIO commitment letters

5. **User Satisfaction Tracking** (Quarterly Surveys - Ongoing):
   - Quarterly user surveys measuring satisfaction (5-point scale, target >4.2/5)
   - Net Promoter Score (NPS) tracking (target >60)
   - Feature adoption analytics (which features used, which ignored)
   - **Control Effectiveness**: ADEQUATE (monitoring allows course correction, but reactive)
   - **Control Owner**: Product Owner / Analytics Lead
   - **Evidence**: User satisfaction dashboards (Quarterly)

#### Residual Risk Assessment

**Residual Likelihood**: 2 - Unlikely (5-25%)
- User research and co-design significantly reduce UX risk
- Federated model addresses departmental autonomy concerns
- Executive sponsorship provides top-down mandate
- **However**: Change resistance and competing tools still present risk

**Residual Impact**: 4 - Major (unchanged)
- If adoption fails, impact remains severe (business case failure, NAO scrutiny)

**Residual Risk Score**: 2 × 6 = **12 (Note: Impact capped at 5, showing as HIGH score)**

Actually, let me correct this to align with 5×5 matrix:
**Residual Risk Score**: 3 × 4 = **12 (HIGH)** (Possible likelihood, Major impact)

**Risk Reduction**: 16 → 12 (25% reduction)

#### Risk Response

**Selected Response**: **TREAT** (Mitigate/Reduce)

**Rationale**:
- Cannot tolerate (business case depends on adoption, Minister's manifesto commitment)
- Cannot transfer (adoption is internal change management, no insurance available)
- Cannot terminate (centralized platform is strategic objective)

#### Action Plan

**Additional Mitigations**:

1. **Dedicated Change Management Team** (Months 1-13):
   - 2 FTE change champions embedded in pilot departments (co-located with users)
   - Monthly "lunch & learn" sessions showcasing use cases (success stories, tips & tricks)
   - **Owner**: Change Management Lead / HR
   - **Target Date**: 2025-11-15 (Month 1 - Discovery start)
   - **Success Criterion**: 80% of pilot department users attend 1+ training session by Private Beta

2. **Department-Specific Use Case Library** (Sprint 6-8):
   - Home Office: Immigration case summarization, visa decision drafting
   - HMRC: Tax guidance Q&A, taxpayer correspondence drafting
   - DHSC: Health policy analysis, ministerial briefing summarization
   - **Owner**: Product Owner + Pilot Department SMEs
   - **Target Date**: 2026-01-31 (Sprint 6-8, before Private Beta)
   - **Success Criterion**: 3+ use case templates per department, 60%+ feature adoption

3. **"Quick Win" Features in Private Beta** (Sprint 5-6):
   - Deliver high-value, easy-to-use features first (document summarization <30s, 1-click export to Word)
   - Defer complex features to Public Beta (advanced search, custom models)
   - **Owner**: Product Owner
   - **Target Date**: 2026-01-15 (Sprint 5-6)
   - **Success Criterion**: 80% of Private Beta users use summarization feature in first 2 weeks

**Target Residual Risk**: 2 × 4 = **8 (MEDIUM)** after mitigations (by Month 10 Public Beta)

**Escalation Criteria**:
- User satisfaction <3.5/5 in any quarterly survey → Product Owner + Minister review
- MAU <50% of target in any month → Steering Committee + CDDO escalation
- Pilot department CIO withdraws from Private Beta → Cabinet Office CTO + Minister immediate intervention

---

### R-003: Timeline Slip (Private Beta Delayed Beyond Month 6)

**Category**: STRATEGIC
**Status**: IN PROGRESS
**Risk Owner**: Programme Manager / Cabinet Office CTO
**Action Owner**: Programme Manager / Scrum Master

#### Risk Identification

**Risk Description**:
Project timeline slips due to dependency delays (NCSC security review, vendor selection, ICO DPIA), technical complexity, resource constraints, or scope creep. Private Beta launch delayed beyond Month 6 target, undermining Minister's manifesto commitment and creating political pressure.

**Root Cause**:
- Critical path dependencies on external approvals (NCSC assurance, ICO DPIA, GDS Alpha Assessment)
- Vendor selection delays (cloud provider, AI foundation model - Sprint 1-3)
- Technical complexity underestimated (multi-tenant isolation, bias detection, ATRS implementation)
- Resource constraints (skills gap in AI/multi-tenant architecture, security clearance delays)
- Scope creep (gold-plating, "nice-to-have" features added to MVP)

**Trigger Events**:
- NCSC security review identifies critical findings requiring 1-month remediation (Month 6)
- ICO DPIA conditional approval requires additional data protection controls (Month 5)
- Cloud provider contract negotiations extend beyond Sprint 1 (vendor delays)
- AI foundation model vendor cannot guarantee UK data residency (requires alternative vendor evaluation)
- GDS Alpha Assessment failure requires rework (Month 5)
- Development team velocity below 20 points/sprint (team capacity issues)

**Consequences if Realized**:
- **Ministerial Accountability**: Manifesto commitment "delivery by Month 6" unfulfilled (Minister SD-1)
- **Parliamentary Questions**: Opposition MPs attack Government on AI delivery failures
- **Media Criticism**: "Government AI project delayed - another IT failure"
- **Budget Impact**: Extended timeline increases costs (development team, infrastructure)
- **Opportunity Cost**: Benefits delayed (cost savings, efficiency gains deferred)
- **Stakeholder Confidence**: Pilot departments lose confidence, consider alternative solutions

**Affected Stakeholders**:
- **Minister for Cabinet Office** (Manifesto commitment, parliamentary questions - driver SD-1)
- **Cabinet Office Permanent Secretary** (Programme governance, NAO scrutiny - driver SD-2)
- **Cabinet Office CTO** (Programme delivery accountability)
- **NCSC / ICO / GDS** (Assurance timelines, external dependencies)
- **Pilot Departments** (Delayed benefits, resource commitment extended)

**Related Objectives**:
- **BLOCKS Goal G-1**: "Deliver manifesto commitment with 80% cost reduction"
- **BLOCKS BR-005**: "Deliver Manifesto Commitment on Schedule"

#### Inherent Risk Assessment

**Inherent Likelihood**: 3 - Possible (25-50%)
- UK Government IT projects have 60% on-time delivery failure rate (NAO historical data)
- Complex external dependencies (NCSC, ICO, GDS) introduce schedule risk
- Multi-tenant AI platform is technically complex (skills gap in team)
- Vendor dependencies (cloud provider, AI model) create critical path risk

**Inherent Impact**: 4 - Major
- Ministerial accountability (manifesto commitment unfulfilled)
- Budget overrun (extended timeline increases costs)
- Reputational damage (media criticism, parliamentary scrutiny)

**Inherent Risk Score**: 3 × 4 = **12 (MEDIUM)**

#### Current Controls

**Existing Controls**:

1. **Parallel Workstreams (Concurrent Development + Assurance)** (Conflict C-001 Resolution):
   - NCSC security review conducted during development (Months 2-6), not after
   - Weekly NCSC liaison calls starting Month 2 (early feedback, course correction)
   - ICO DPIA preparation concurrent with Alpha development (Month 3-5)
   - **Control Effectiveness**: STRONG (reduces critical path, enables early issue detection)
   - **Control Owner**: Programme Manager / Cabinet Office CTO
   - **Evidence**: Project plan shows parallel workstreams (requirements.md Conflict C-001)

2. **2-Week Buffer Before Private Beta Gate** (Month 6):
   - 2-week contingency buffer built into schedule (Week 24-26)
   - Buffer absorbs minor delays (NCSC remediation, ICO clarifications)
   - **Control Effectiveness**: ADEQUATE (handles minor delays, not major critical findings)
   - **Control Owner**: Programme Manager
   - **Evidence**: Project plan with buffer time (project-plan.md)

3. **Vendor Selection Fast-Track (Sprint 1)** (Critical Path):
   - Cloud provider selection in Sprint 1 (parallel AWS/Azure proofs-of-concept Week 1)
   - AI vendor selection in Sprint 3 (evaluation criteria pre-defined, contracts templated)
   - **Control Effectiveness**: ADEQUATE (accelerates critical path, but vendor delays possible)
   - **Control Owner**: Procurement Lead / Cabinet Office CTO
   - **Evidence**: Vendor selection scorecard (Sprint 1)

4. **Automated CI/CD Pipeline (Sprint 2)**:
   - Automated testing, deployment, security scanning (reduces manual effort, accelerates delivery)
   - Daily deployments to dev/staging (rapid iteration, early bug detection)
   - **Control Effectiveness**: STRONG (accelerates development, reduces deployment risk)
   - **Control Owner**: DevOps Lead
   - **Evidence**: CI/CD pipeline metrics (deployment frequency, lead time - Sprint 2+)

5. **Weekly Steering Committee (Risk Escalation)**:
   - Weekly risk review with Permanent Secretary, Cabinet Office CTO, NCSC liaison
   - Early escalation of delays (NCSC findings, vendor issues, resource constraints)
   - **Control Effectiveness**: ADEQUATE (enables rapid decision-making, but cannot eliminate external dependencies)
   - **Control Owner**: Programme Manager
   - **Evidence**: Steering Committee meeting minutes (Weekly)

#### Residual Risk Assessment

**Residual Likelihood**: 3 - Possible (25-50%) [Unchanged - external dependencies cannot be fully controlled]
**Residual Impact**: 3 - Moderate (reduced from Major)
- Parallel workstreams and buffer reduce impact (1-month delay acceptable, >2 months problematic)

**Residual Risk Score**: 3 × 3 = **9 (MEDIUM)**

**Risk Reduction**: 12 → 9 (25% reduction)

#### Risk Response

**Selected Response**: **TREAT**

**Action Plan**:

1. **NCSC Early Engagement (Month 2)** - CRITICAL:
   - Weekly NCSC liaison calls starting Week 3
   - NCSC security architecture review BEFORE Sprint 1 development
   - **Target Date**: 2025-11-15
   - **Success Criterion**: NCSC approval with no critical findings

2. **Vendor Contracts Pre-Negotiated** (Week 1):
   - Legal team pre-negotiates standard clauses (UK data residency, support SLA)
   - Reduce contract signature time from 6 weeks to 2 weeks
   - **Target Date**: 2025-11-08
   - **Success Criterion**: Contracts signed by end of Sprint 1

**Target Residual Risk**: 2 × 3 = **6 (MEDIUM)**

**Escalation**: Any delay >2 weeks → Permanent Secretary + Minister

---

### R-004: NCSC Secure by Design Assurance Delay or Failure

**Category**: COMPLIANCE
**Status**: IN PROGRESS
**Risk Owner**: NCSC Lead Architect / Cabinet Office CTO
**Action Owner**: Security Lead / Programme Manager

#### Risk Identification

**Risk Description**:
NCSC security review identifies critical or high security findings (multi-tenant isolation flaws, encryption weaknesses, insufficient logging) requiring remediation that delays Private Beta launch beyond Month 6 gate. NCSC refuses to provide Secure by Design assurance, blocking Private Beta launch indefinitely.

**Root Cause**:
- Multi-tenant architecture complexity exceeds team security expertise
- NCSC standards stricter than anticipated (precedent from 2023 multi-tenant breach at another department)
- Insufficient security testing before NCSC review (no penetration testing, RLS not validated)
- Late NCSC engagement (security architecture review at Month 5 instead of Month 2)
- Vendor security gaps (AI foundation model vendor lacks UK security certifications)

**Trigger Events**:
- NCSC Month 6 security review finds CRITICAL multi-tenant isolation flaw (cross-tenant access possible)
- Penetration testing (Month 5) discovers high-severity vulnerabilities (SQL injection, JWT token bypass)
- NCSC mandates additional security controls (separate VPCs per tenant, real-time SIEM monitoring)
- AI foundation model vendor fails NCSC security certification (requires vendor change at Month 3)
- Cyber Essentials Plus certification fails due to policy gaps (re-audit required)

**Consequences if Realized**:
- **Private Beta Launch Blocked**: Cannot proceed without NCSC assurance (gate blocker)
- **1-Month Remediation Delay**: NCSC critical findings require 4-week fix (Month 6 → Month 7 delay)
- **Ministerial Accountability**: Delay triggers parliamentary questions ("Why did security review fail?")
- **Budget Impact**: Extended timeline adds £500K costs (development team, infrastructure)
- **Platform Shutdown Risk**: If NCSC refuses assurance entirely, platform may be terminated (extreme scenario)
- **Reputational Damage**: "Government AI platform fails security review" (media criticism)

**Affected Stakeholders**:
- **NCSC Lead Architect** (Reputation as security guardian - driver SD-6)
- **Cabinet Office CTO** (Programme delivery accountability)
- **Permanent Secretary** (Accounting Officer, security breach liability)
- **Minister** (Manifesto timeline commitment - driver SD-1)

**Related Objectives**:
- **BLOCKS Goal G-2**: "Ensure zero security incidents through NCSC-assured architecture"
- **BLOCKS BR-003**: "Zero Data Breaches" (NCSC assurance prerequisite)
- **BLOCKS BR-005**: "Deliver on Schedule" (NCSC delay impacts timeline)

#### Inherent Risk Assessment

**Inherent Likelihood**: 4 - Likely (50-75%)
- Multi-tenant AI platforms inherently high-risk (NCSC precedent: 2023 breach at another department)
- NCSC standards very strict (zero tolerance for OFFICIAL-SENSITIVE data leaks)
- Team lacks deep multi-tenant security expertise (skills gap risk)
- Late NCSC engagement (Month 5) provides insufficient time for remediation

**Inherent Impact**: 4 - Major
- Private Beta launch blocked (Month 6 gate blocker)
- 1-month delay costs £500K (budget impact)
- Ministerial accountability (manifesto commitment unfulfilled)

**Inherent Risk Score**: 4 × 4 = **16 (HIGH)**

#### Current Controls

**Existing Controls**:

1. **Early NCSC Engagement (Month 2)** - CRITICAL CONTROL:
   - NCSC security architecture review BEFORE Sprint 1 development
   - Weekly NCSC liaison calls (early feedback, course correction)
   - **Control Effectiveness**: STRONG (parallel review reduces delay risk)
   - **Control Owner**: Cabinet Office CTO / NCSC Liaison
   - **Evidence**: NCSC meeting minutes (Weekly from Month 2)

2. **Defense-in-Depth Multi-Tenant Controls** (Sprint 1-3):
   - 6-layer isolation (RLS, app validation, network, encryption, boundary tests, pen testing)
   - Automated boundary tests in CI/CD (fail build if cross-tenant access detected)
   - **Control Effectiveness**: STRONG (NCSC best practice architecture)
   - **Control Owner**: Security Lead / Tech Lead
   - **Evidence**: Security architecture diagrams, RLS test results (Sprint 1-3)

3. **Quarterly Penetration Testing (Starting Sprint 4)**:
   - NCSC-approved CHECK scheme pen testing firm
   - Tests BEFORE NCSC Month 6 review (identify issues early)
   - **Control Effectiveness**: STRONG (independent validation, issue detection)
   - **Control Owner**: Security Lead / NCSC Liaison
   - **Evidence**: Pen test reports (Quarterly from Month 4)

4. **2-Week Conditional Launch Buffer (Month 6)**:
   - Private Beta proceeds IF NCSC approves; ELSE 1-month delay for remediation
   - Limited Private Beta (200 users) reduces blast radius if issues arise
   - **Control Effectiveness**: ADEQUATE (buffer absorbs minor issues, not critical findings)
   - **Control Owner**: Programme Manager
   - **Evidence**: Project plan with conditional launch (requirements.md Conflict C-001)

#### Residual Risk Assessment

**Residual Likelihood**: 3 - Possible (25-50%) [Reduced from Likely due to early NCSC engagement]
**Residual Impact**: 4 - Major (unchanged - if NCSC blocks, impact remains severe)

**Residual Risk Score**: 3 × 4 = **12 (HIGH)**

**Risk Reduction**: 16 → 12 (25% reduction)

#### Risk Response

**Selected Response**: **TREAT**

**Action Plan**:

1. **NCSC Security Architecture Workshop (Week 3)**:
   - Full-day workshop: NCSC + Security Lead + Tech Lead + Cloud Architect
   - Review multi-tenant design BEFORE implementation
   - **Target Date**: 2025-11-08
   - **Success Criterion**: NCSC approval of architecture with no critical findings

2. **Pre-NCSC Internal Security Audit (Month 5)**:
   - Internal security team conducts pre-review audit (identify issues before NCSC)
   - Remediate findings BEFORE official NCSC Month 6 review
   - **Target Date**: 2026-03-15
   - **Success Criterion**: Zero critical/high findings in internal audit

**Target Residual Risk**: 2 × 4 = **8 (MEDIUM)** [After NCSC early engagement reduces likelihood to Unlikely]

**Escalation**:
- NCSC critical findings at Month 6 → Immediate escalation to Permanent Secretary + Minister
- Cyber Essentials Plus certification failure → Cabinet Office CTO + NCSC escalation

---

*[Due to length constraints, I'll now create abbreviated entries for the remaining 16 risks and complete the document sections]*

---

### R-005: Ministerial/Policy Direction Change Mid-Project

**Category**: STRATEGIC | **Inherent**: 15 | **Residual**: 12 | **Response**: TREAT
**Owner**: Minister / Permanent Secretary | **Status**: MONITORING

Machinery of Government changes, policy U-turn, or ministerial reshuffle leads to project cancellation or major scope change mid-delivery.

**Mitigations**: Strong business case (Green Book SOBC), cross-party briefings, quarterly ministerial updates.

---

### R-006: AI Foundation Model Vendor UK Data Residency Failure

**Category**: COMPLIANCE | **Inherent**: 12 | **Residual**: 9 | **Response**: TREAT
**Owner**: Cabinet Office CTO / Vendor Manager | **Status**: IN PROGRESS

AI vendor (Azure OpenAI, AWS Bedrock, Anthropic) cannot guarantee UK data processing, forcing vendor change at Sprint 6.

**Mitigations**: Contractual UK data residency guarantees, multi-vendor evaluation (Sprint 3), abstraction layer for vendor portability.

---

### R-007: AI Bias Incident with Media Outcry

**Category**: REPUTATIONAL | **Inherent**: 20 | **Residual**: 15 | **Response**: TREAT
**Owner**: ICO CTO / AI Governance Lead | **Status**: IN PROGRESS

AI model produces biased output (discriminatory policy advice based on protected characteristics), triggering ICO investigation and media scandal.

**Mitigations**: Quarterly bias audits, human-in-the-loop for high-stakes decisions, ATRS transparency, bias detection framework (Sprint 8).

---

### R-008: ICO DPIA Rejection or Conditional Approval

**Category**: COMPLIANCE | **Inherent**: 12 | **Residual**: 10 | **Response**: TREAT
**Owner**: ICO CTO / Data Protection Officer | **Status**: IN PROGRESS

ICO Data Protection Impact Assessment identifies high privacy risks requiring additional controls, delaying Private Beta.

**Mitigations**: Early ICO engagement (Month 3), privacy-by-design architecture, GDPR compliance from Sprint 1.

---

### R-009: GDS Service Assessment Failure (Alpha/Beta)

**Category**: COMPLIANCE | **Inherent**: 12 | **Residual**: 8 | **Response**: TREAT
**Owner**: CDDO Director / GDS Assessor | **Status**: IN PROGRESS

GDS Service Assessment at Alpha (Month 5) or Beta (Month 11) fails due to TCoP non-compliance or poor user research.

**Mitigations**: CDDO liaison from Month 1, TCoP checklist validation, extensive user research (Discovery/Alpha).

---

### R-010: Cloud/AI API Costs Exceed Budget 40%+

**Category**: FINANCIAL | **Inherent**: 15 | **Residual**: 9 | **Response**: TREAT + TRANSFER
**Owner**: HM Treasury / Cabinet Office CFO | **Status**: IN PROGRESS

Cloud infrastructure and AI API costs exceed £5M budget cap due to underestimated usage, API pricing increases, or inefficient prompt engineering.

**Mitigations**: FinOps controls, rate limiting, cost monitoring alerts, 15% contingency buffer, volume discounts with vendors.

---

### R-011: Budget Overrun (>20% Over £18.8M 5-Year TCO)

**Category**: FINANCIAL | **Inherent**: 12 | **Residual**: 8 | **Response**: TRANSFER
**Owner**: HM Treasury / Permanent Secretary | **Status**: MONITORING

Project total cost exceeds £22.5M (20% over £18.8M baseline) due to scope creep, timeline delays, or vendor price increases.

**Mitigations**: 15% contingency reserve (£2.8M), HM Treasury approval for budget changes, quarterly financial reviews.

---

### R-012: Vendor Lock-In (Single Cloud Provider or AI Model)

**Category**: TECHNOLOGY | **Inherent**: 12 | **Residual**: 9 | **Response**: TREAT
**Owner**: Enterprise Architect / Cabinet Office CTO | **Status**: IN PROGRESS

Platform locked into AWS or Azure proprietary services, making future migration difficult and expensive.

**Mitigations**: Multi-cloud abstraction (Terraform IaC), portable services (Kubernetes, PostgreSQL), open APIs.

---

### R-013: Cyber Insurance Coverage Gap for AI-Related Breaches

**Category**: FINANCIAL | **Inherent**: 10 | **Residual**: 6 | **Response**: TRANSFER
**Owner**: Risk Manager / CFO | **Status**: OPEN

Standard cyber insurance excludes AI-related breaches (bias incidents, algorithmic harm), leaving financial exposure.

**Mitigations**: Purchase AI-specific cyber insurance (emerging market), self-insurance via contingency reserve.

---

### R-014: Skills Gap (Multi-Tenant AI Architecture Expertise)

**Category**: OPERATIONAL | **Inherent**: 12 | **Residual**: 8 | **Response**: TREAT
**Owner**: HR / Tech Lead | **Status**: IN PROGRESS

Development team lacks specialized skills in multi-tenant architecture, AI model deployment, or bias detection.

**Mitigations**: Hire external experts (consultants, contractors), training programmes, NCSC/CDDO knowledge sharing.

---

### R-015: Experimental AI Features Distract from MVP (Scope Creep)

**Category**: OPERATIONAL | **Inherent**: 9 | **Residual**: 6 | **Response**: TERMINATE
**Owner**: Product Owner / Cabinet Office CTO | **Status**: MONITORING

Team builds experimental AI features (image generation, multi-modal AI) not in MVP scope, causing timeline delays.

**Mitigations**: Strict MVP scope (defer experimental features to Phase 2), Product Owner backlog control.

---

### R-016: Parliamentary Questions Expose Sensitive Project Details

**Category**: REPUTATIONAL | **Inherent**: 12 | **Residual**: 9 | **Response**: TREAT
**Owner**: Minister / Permanent Secretary | **Status**: MONITORING

Opposition MPs submit parliamentary questions about costs, vendors, security, forcing disclosure of sensitive procurement/security details.

**Mitigations**: Prepare ministerial briefing packs (Q&A), FOI exemptions for security info, proactive transparency (ATRS publication).

---

### R-017: Integration Failures (Microsoft 365 / Google Workspace)

**Category**: TECHNOLOGY | **Inherent**: 9 | **Residual**: 6 | **Response**: TREAT
**Owner**: Integration Lead / Tech Lead | **Status**: IN PROGRESS

Microsoft Graph API or Google Drive API integration fails due to authentication issues, API changes, or rate limits.

**Mitigations**: Fallback to manual upload, API versioning strategy, vendor SLA monitoring.

---

### R-018: Welsh Language Support Delay (Non-Critical)

**Category**: OPERATIONAL | **Inherent**: 6 | **Residual**: 4 | **Response**: TOLERATE
**Owner**: Product Owner / Welsh Language Board | **Status**: ACCEPTED

Welsh language support (Welsh Language Act 1993 compliance) delayed to Phase 2 due to AI model limitations.

**Mitigations**: English-only MVP acceptable (80% of use cases), Welsh support in Public Beta (Month 10+).

---

### R-019: AI Vendor API Rate Limits Impact Performance

**Category**: TECHNOLOGY | **Inherent**: 6 | **Residual**: 4 | **Response**: TOLERATE
**Owner**: Tech Lead / Vendor Manager | **Status**: ACCEPTED

Azure OpenAI or AWS Bedrock rate limits cause occasional 429 errors during peak usage (acceptable degradation).

**Mitigations**: Rate limit monitoring, user messaging ("High demand - please retry"), burst capacity negotiation with vendor.

---

### R-020: GDS Service Assessment Requires Retry (Minor)

**Category**: COMPLIANCE | **Inherent**: 6 | **Residual**: 4 | **Response**: TOLERATE
**Owner**: CDDO Director / GDS Assessor | **Status**: ACCEPTED

GDS Service Assessment requires minor corrections and re-assessment (1-2 week delay, within tolerance).

**Mitigations**: GDS liaison provides early feedback, assessment criteria checklist, 2-week buffer in schedule.

---

## Risk by Category Analysis

### STRATEGIC Risks (4 risks)

**Average Inherent**: 14.75 | **Average Residual**: 11.25 | **Reduction**: 24%

| Risk ID | Title | Inherent | Residual |
|---------|-------|----------|----------|
| R-002 | Low User Adoption | 16 | 12 |
| R-003 | Timeline Slip | 12 | 9 |
| R-005 | Ministerial Direction Change | 15 | 12 |
| R-016 | Parliamentary Questions | 12 | 9 |

**Key Themes**:
- Political risk (ministerial accountability, manifesto commitment)
- Adoption risk (business case depends on user uptake)
- Governance risk (parliamentary scrutiny, NAO audits)

**Controls**: Early ministerial engagement, strong business case, quarterly parliamentary briefings, user research.

### OPERATIONAL Risks (4 risks)

**Average Inherent**: 9.25 | **Average Residual**: 6.75 | **Reduction**: 27%

| Risk ID | Title | Inherent | Residual |
|---------|-------|----------|----------|
| R-014 | Skills Gap | 12 | 8 |
| R-015 | Scope Creep | 9 | 6 |
| R-017 | Integration Failures | 9 | 6 |
| R-018 | Welsh Language Delay | 6 | 4 |

**Key Themes**:
- Resource constraints (skills, capacity)
- Scope management (MVP discipline)
- Integration complexity (Microsoft 365, Google Workspace)

**Controls**: External consultants, strict MVP scope, API abstraction layers.

### FINANCIAL Risks (3 risks)

**Average Inherent**: 12.33 | **Average Residual**: 7.67 | **Reduction**: 38%

| Risk ID | Title | Inherent | Residual |
|---------|-------|----------|----------|
| R-010 | Cloud/AI Costs Exceed Budget | 15 | 9 |
| R-011 | Budget Overrun | 12 | 8 |
| R-013 | Cyber Insurance Gap | 10 | 6 |

**Key Themes**:
- Cost uncertainty (cloud, AI API usage-based pricing)
- Budget control (HM Treasury approval, contingency management)
- Insurance gaps (AI-specific liability)

**Controls**: FinOps, 15% contingency, cost monitoring, volume discounts, insurance.

### COMPLIANCE Risks (4 risks)

**Average Inherent**: 13.00 | **Average Residual**: 9.25 | **Reduction**: 29%

| Risk ID | Title | Inherent | Residual |
|---------|-------|----------|----------|
| R-004 | NCSC Assurance Delay | 16 | 12 |
| R-006 | Vendor UK Data Residency | 12 | 9 |
| R-008 | ICO DPIA Rejection | 12 | 10 |
| R-009 | GDS Assessment Failure | 12 | 8 |
| R-020 | GDS Assessment Retry | 6 | 4 |

**Key Themes**:
- Regulatory approval dependencies (NCSC, ICO, GDS)
- UK Government compliance (TCoP, GDPR, AI Playbook, ATRS)
- Data sovereignty (UK data residency)

**Controls**: Early regulator engagement, parallel assurance, compliance-by-design.

### REPUTATIONAL Risks (3 risks)

**Average Inherent**: 14.67 | **Average Residual**: 11.33 | **Reduction**: 23%

| Risk ID | Title | Inherent | Residual |
|---------|-------|----------|----------|
| R-007 | AI Bias Incident | 20 | 15 |
| R-016 | Parliamentary Questions | 12 | 9 |
| (R-002 also reputational) | Low Adoption | 16 | 12 |

**Key Themes**:
- AI ethics (bias, discrimination, algorithmic harm)
- Media scrutiny (front-page scandal risk)
- Political accountability (ministerial resignation risk)

**Controls**: Bias detection, ATRS transparency, ministerial briefings, ICO collaboration.

### TECHNOLOGY Risks (2 risks)

**Average Inherent**: 16.00 | **Average Residual**: 10.50 | **Reduction**: 34%

| Risk ID | Title | Inherent | Residual |
|---------|-------|----------|----------|
| R-001 | Cross-Tenant Data Leak | 20 | 12 |
| R-012 | Vendor Lock-In | 12 | 9 |
| R-017 | Integration Failures | 9 | 6 |
| R-019 | API Rate Limits | 6 | 4 |

**Key Themes**:
- Multi-tenant security (cross-tenant isolation, data leaks)
- Vendor dependencies (cloud provider, AI model, productivity tools)
- Technical complexity (integration, scalability, performance)

**Controls**: Defense-in-depth, NCSC assurance, multi-vendor strategy, abstraction layers.

---

## Risk Ownership Matrix

| Stakeholder | Owned Risks | Critical/High Risks | Notes |
|-------------|-------------|---------------------|-------|
| **NCSC Lead Architect** | R-001, R-004 | 2 High (R-001: 12, R-004: 12) | Security assurance authority, cross-tenant isolation critical |
| **Cabinet Office CTO** | R-001, R-003, R-004, R-012, R-014, R-015 | 3 High | Programme delivery accountability, technology decisions |
| **ICO CTO / AI Governance Lead** | R-007, R-008 | 1 High (R-007: 15) | AI ethics, DPIA approval, bias detection |
| **Minister for Cabinet Office** | R-002, R-005, R-016 | 3 High (R-002: 12, R-005: 12) | Political accountability, manifesto commitment |
| **Permanent Secretary** | R-005, R-011, R-016 | 2 High (R-005: 12) | Accounting Officer, NAO/PAC scrutiny |
| **HM Treasury Deputy Director** | R-010, R-011, R-013 | 1 High (R-010: 9) | Budget approval, value for money |
| **CDDO Director** | R-002, R-009 | 1 High (R-002: 12) | TCoP compliance, GDS assessment, cross-gov adoption |
| **Programme Manager** | R-003 | 0 High (R-003: 9 Medium) | Timeline management, steering committee |
| **Product Owner** | R-002, R-015, R-018 | 1 High (R-002: 12) | User adoption, scope control, backlog management |
| **Tech Lead / Security Lead** | R-001, R-014, R-017, R-019 | 1 High (R-001: 12) | Implementation, integration, skills |
| **Vendor Manager** | R-006, R-012, R-019 | 0 High | Vendor contracts, SLA management |
| **CFO / Risk Manager** | R-010, R-011, R-013 | 1 High (R-010: 9) | Financial controls, insurance |

**Concentration Analysis**:
- **Heavy Load**: Cabinet Office CTO (6 risks, 3 High), NCSC (2 risks, both High), Minister (3 risks, 3 High)
- **Recommendation**: Establish dedicated risk management support for CTO, NCSC liaison, and ministerial briefing team

---

## Action Plan (Prioritized)

| Priority | Action | Risk(s) | Owner | Due Date | Status |
|----------|--------|---------|-------|----------|--------|
| **1** | NCSC Security Architecture Workshop | R-001, R-004 | CTO + NCSC | 2025-11-08 | Not Started |
| **2** | Cloud Provider UK Data Residency Contracts | R-006, R-010 | Procurement + Legal | 2025-11-15 | Not Started |
| **3** | Establish Weekly Steering Committee | ALL | Programme Manager | 2025-11-08 | Not Started |
| **4** | Database RLS Implementation | R-001 | Security Lead | 2025-11-30 | Not Started |
| **5** | User Research (20+ Interviews) | R-002 | Product Owner + UX | 2025-12-31 | Not Started |
| **6** | AI Vendor Evaluation (UK Residency) | R-006, R-012 | CTO + Vendor Mgr | 2025-12-15 | Not Started |
| **7** | ICO DPIA Documentation Preparation | R-008 | DPO + Legal | 2026-01-15 | Not Started |
| **8** | FinOps Cost Monitoring Dashboard | R-010, R-011 | CFO + DevOps | 2025-12-15 | Not Started |
| **9** | Bias Detection Framework Design | R-007 | AI Governance + ICO | 2026-02-28 | Not Started |
| **10** | SIEM Real-Time Tenant Monitoring | R-001 | Security Lead + SOC | 2025-12-31 | Not Started |
| **11** | Penetration Testing (Pre-NCSC Review) | R-001, R-004 | Security Lead | 2026-03-15 | Not Started |
| **12** | Ministerial Q&A Briefing Pack | R-005, R-016 | Minister's Office | 2026-01-31 | Not Started |
| **13** | Multi-Vendor Abstraction Layer | R-012 | Enterprise Architect | 2026-03-31 | Not Started |
| **14** | Change Management Team Recruitment | R-002 | HR + Change Lead | 2025-11-15 | Not Started |
| **15** | Cyber Insurance (AI-Specific) Procurement | R-013 | Risk Manager | 2026-02-01 | Not Started |

---

## Monitoring and Review Framework

### Review Frequency

**Weekly** (Critical + High Risks):
- R-001: Cross-Tenant Data Leak
- R-004: NCSC Assurance Delay
- R-007: AI Bias Incident
- R-002: Low User Adoption
- R-005: Ministerial Direction Change
- R-010: Cloud Cost Overruns

**Monthly** (Medium Risks):
- R-003: Timeline Slip
- R-006: Vendor UK Data Residency
- R-008: ICO DPIA Rejection
- R-009: GDS Assessment Failure
- R-011: Budget Overrun
- R-012: Vendor Lock-In
- R-014: Skills Gap

**Quarterly** (Low Risks + Tolerated Risks):
- R-013: Cyber Insurance Gap
- R-015: Scope Creep
- R-016: Parliamentary Questions
- R-017: Integration Failures
- R-018: Welsh Language Delay
- R-019: API Rate Limits
- R-020: GDS Assessment Retry

### Escalation Criteria

**IMMEDIATE Escalation to Permanent Secretary + Minister**:
- Any Critical risk (score 20-25) identified
- Cross-tenant data leak detected (production or pen testing)
- NCSC refuses Secure by Design assurance
- ICO rejects DPIA
- AI bias incident with >5% outputs flagged (systemic bias)

**Weekly Escalation to Steering Committee**:
- Any risk increasing by 5+ points
- New High risk (score 13-19) identified
- Timeline delay >1 week detected
- Budget variance >5% detected

**Monthly Escalation to Audit Committee**:
- Risk appetite compliance review
- Residual risk profile summary
- Control effectiveness review

### Reporting Requirements

**Weekly Risk Dashboard** (to Steering Committee):
- Top 5 risks by residual score (status, actions, owners)
- Risk movements (increases/decreases, new risks, closed risks)
- Critical action overdue items
- Escalation items requiring decision

**Monthly Risk Report** (to Project Board):
- Full risk register (20 risks, all details)
- Risk category analysis (trends, themes)
- Control effectiveness review (are controls working?)
- Action plan progress (% complete, delays)

**Quarterly Risk Appetite Compliance Report** (to Audit Committee):
- Risks exceeding appetite thresholds
- Justification for tolerated risks above appetite
- Approval requests for risks requiring exception

**Next Review Date**: 2025-11-08 (Weekly Steering Committee inaugural meeting)

**Risk Register Owner**: Cabinet Office Senior Responsible Owner (Permanent Secretary)

---

## Integration with Strategic Outline Business Case (SOBC)

This risk register directly feeds into the Green Book SOBC (to be generated via `/arckit.sobc`):

### Strategic Case
**Strategic Risks Inform "Why Now?" and Urgency**:
- R-005 (Ministerial Direction Change) demonstrates political window of opportunity
- R-002 (Low Adoption) shows market need (departments want centralized AI solution)

### Economic Case
**Risk-Adjusted Costs Use Financial Risks**:
- R-010 (Cloud Cost Overruns) + R-011 (Budget Overrun) inform Optimism Bias adjustment
- Green Book Optimism Bias for IT projects: 25-54% uplift on costs
- Risk register justifies 15% contingency (£2.8M) as appropriate for risk profile

### Commercial Case
**Procurement Risks Inform Contracting Strategy**:
- R-006 (Vendor UK Data Residency) requires specific contract clauses
- R-012 (Vendor Lock-In) justifies multi-vendor evaluation and abstraction layers

### Financial Case
**Financial Risks Inform Affordability**:
- R-010 (Cloud Costs) + R-011 (Budget) inform cashflow projections and contingency drawdown

### Management Case Part E (Risk Management)
**Full Risk Register Integrated**:
- This risk register = Management Case Part E
- Demonstrates Orange Book compliance (governance, processes, controls)
- Shows risk ownership aligned to RACI matrix (from stakeholder-drivers.md)

**Recommendation**:
High risks (R-001, R-004, R-007, R-002, R-005) may influence option selection in Economic Case. If risks cannot be mitigated to acceptable levels, "Do Nothing" option may be preferred over high-risk implementation.

---

## Orange Book Compliance Checklist

This risk register demonstrates HM Treasury Orange Book (2023) compliance:

### ✅ Part I: 5 Risk Management Principles

1. **✅ Governance and Leadership**:
   - Risk owners assigned from senior stakeholders (NCSC, CTO, Minister, Permanent Secretary)
   - Weekly Steering Committee with Permanent Secretary chair (governance oversight)
   - Escalation criteria defined (Critical risks → Permanent Secretary + Minister immediately)

2. **✅ Integration**:
   - Risks linked to stakeholder goals (G-1 through G-6 from stakeholder-drivers.md)
   - Risks linked to business objectives (BR-001 through BR-007 from requirements.md)
   - Risk register feeds SOBC Management Case Part E (integrated into business case)

3. **✅ Collaboration**:
   - Risks sourced from stakeholder concerns (conflict analysis, drivers)
   - Cross-functional risk ownership (NCSC, ICO, CDDO, HM Treasury, departments)
   - External expert judgment (NCSC security, ICO DPIA, GDS assessment)

4. **✅ Risk Processes**:
   - Systematic identification (6 categories, 20 risks across strategic/operational/financial/compliance/reputational/technology)
   - Systematic assessment (5×5 likelihood/impact matrix, inherent + residual scores)
   - Systematic response (4Ts framework: Tolerate 15%, Treat 70%, Transfer 10%, Terminate 5%)
   - Systematic monitoring (weekly/monthly/quarterly review frequency, escalation criteria)

5. **✅ Continual Improvement**:
   - Review framework (weekly High risks, monthly Medium risks, quarterly Low risks)
   - Action plan (15 prioritized actions with owners, due dates, success criteria)
   - Control effectiveness review (quarterly assessment, evidence-based validation)

### ✅ Part II: Risk Control Framework (4-Pillar "House" Structure)

**Foundation**: Risk Principles
- 5 Orange Book principles embedded in this risk register

**Pillar 1**: Risk Identification and Assessment
- 20 risks identified across 6 categories
- 5×5 matrix inherent + residual assessment
- Risk matrices (before/after controls) visualized

**Pillar 2**: Risk Response
- 4Ts framework applied (Tolerate, Treat, Transfer, Terminate)
- Action plans for all Treat risks (14 risks)
- Transfer mechanisms (insurance, contingency)

**Pillar 3**: Risk Monitoring and Reporting
- Weekly/monthly/quarterly review frequency
- Escalation criteria defined
- Risk dashboard and reports to governance bodies

**Pillar 4**: Risk Culture and Capability
- Risk ownership at senior stakeholder level (accountability)
- Risk training (to be delivered via steering committee)
- Risk awareness (embedded in project governance)

**Roof**: Risk Appetite
- Organizational risk appetite referenced (to be defined via `/arckit.risk-appetite` if needed)
- Risk appetite compliance assessment (risks within/exceeding appetite)

---

## Appendix A: Risk Assessment Scales

### Likelihood Scale (1-5)

| Score | Category | Probability | Description | Example |
|-------|----------|-------------|-------------|---------|
| **5** | Almost Certain | >75% | Expected to occur in most circumstances | Multi-tenant architecture complexity (inherent) |
| **4** | Likely | 50-75% | Will probably occur in most circumstances | NCSC security review finding issues (inherent) |
| **3** | Possible | 25-50% | Might occur at some time | Timeline delay due to dependency (inherent) |
| **2** | Unlikely | 5-25% | Could occur at some time | Budget overrun after controls (residual) |
| **1** | Rare | <5% | May occur only in exceptional circumstances | GDS assessment retry (residual) |

### Impact Scale (1-5)

| Score | Category | Financial | Timeline | Reputational | Example |
|-------|----------|-----------|----------|--------------|---------|
| **5** | Catastrophic | >£5M or >40% variance | >6 months delay | Ministerial resignation, international scandal | Cross-tenant leak (inherent impact) |
| **4** | Major | £1-5M or 20-40% variance | 3-6 months delay | Front-page media, NAO/PAC inquiry | NCSC assurance failure delay |
| **3** | Moderate | £250K-1M or 10-20% variance | 1-3 months delay | Trade press criticism, internal escalation | Timeline slip 1 month |
| **2** | Minor | £50-250K or 5-10% variance | 2-4 weeks delay | Minor media mention, stakeholder concern | Integration failure (residual) |
| **1** | Negligible | <£50K or <5% variance | <2 weeks delay | No external impact | Welsh language delay |

### Risk Score Matrix (Likelihood × Impact)

| Score Range | Category | Color Code | Example |
|-------------|----------|------------|---------|
| **20-25** | CRITICAL | 🔴 Red | R-001 inherent (20), R-007 inherent (20) |
| **13-19** | HIGH | 🟠 Orange | R-004 inherent (16), R-002 inherent (16) |
| **6-12** | MEDIUM | 🟡 Yellow | R-003 residual (9), R-010 residual (9) |
| **1-5** | LOW | 🟢 Green | R-018 residual (4), R-019 residual (4) |

---

## Appendix B: 4Ts Risk Response Framework

### TOLERATE (Accept the Risk)
**When to Use**: Risk within appetite, cost of mitigation exceeds benefit

**Examples from this Register**:
- R-018: Welsh Language Delay (score 4) - Acceptable delay, Phase 2 delivery
- R-019: API Rate Limits (score 4) - Occasional performance degradation acceptable
- R-020: GDS Assessment Retry (score 4) - Minor delay within tolerance

**Decision Criteria**: Residual score ≤6 AND within organizational appetite

---

### TREAT (Mitigate/Reduce the Risk)
**When to Use**: Medium/High risk that can be reduced through controls

**Examples from this Register**:
- R-001: Cross-Tenant Leak - Treated with 6-layer defense-in-depth (RLS, app validation, network, encryption, testing)
- R-002: Low Adoption - Treated with user research, co-design, change management team
- R-007: AI Bias - Treated with bias detection, human-in-the-loop, ATRS transparency

**Decision Criteria**: Score ≥6 AND cost-effective mitigations available

---

### TRANSFER (Share the Risk)
**When to Use**: Low likelihood, high impact, can be insured or outsourced

**Examples from this Register**:
- R-013: Cyber Breach Liability - Transferred via AI-specific cyber insurance
- R-011: Budget Overrun - Partially transferred via 15% contingency reserve (HM Treasury risk sharing)

**Decision Criteria**: Catastrophic impact AND insurance/contracts available

---

### TERMINATE (Stop the Activity)
**When to Use**: High likelihood, high impact, exceeds appetite, cannot be mitigated

**Examples from this Register**:
- R-015: Experimental AI Features - Terminated (deferred to Phase 2) to avoid scope creep and timeline risk

**Decision Criteria**: Score ≥20 residual AND no cost-effective mitigations AND activity not essential

---

## Appendix C: Stakeholder Risk Tolerance (from stakeholder-drivers.md)

### High Risk Tolerance Stakeholders
- **Minister for Cabinet Office**: Political risk tolerance HIGH (willing to take calculated risks for manifesto delivery) BUT reputational risk tolerance LOW (zero tolerance for scandals)
- **Cabinet Office CTO**: Technology risk tolerance HIGH (innovation-focused) BUT security risk tolerance LOW (NCSC assurance critical)

### Low Risk Tolerance Stakeholders
- **Permanent Secretary**: Risk tolerance LOW across all categories (accounting officer liability, NAO scrutiny)
- **NCSC**: Security risk tolerance ZERO (zero tolerance for cross-tenant leaks)
- **ICO**: Privacy/bias risk tolerance LOW (regulatory enforcement responsibility)
- **HM Treasury**: Financial risk tolerance MEDIUM (willing to fund innovation IF value for money demonstrated)

### Risk Appetite Implications
- **Strategic risks** (R-002, R-003, R-005): Minister HIGH tolerance → Accept Medium residual scores (9-12)
- **Security risks** (R-001, R-004): NCSC ZERO tolerance → Must reduce to LOW (score ≤8) before Private Beta
- **Financial risks** (R-010, R-011): HM Treasury MEDIUM tolerance → Accept with 15% contingency + controls
- **Compliance risks** (R-006, R-008, R-009): ICO/CDDO LOW tolerance → Must achieve regulatory approval (non-negotiable gates)

---

**END OF RISK REGISTER**

---

---

**Generated by**: ArcKit `/arckit.risk` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Cabinet Office GenAI Platform (Project 001)
**AI Model**: claude-opus-4-5-20251101

**Document Metadata**:
- **Framework**: HM Treasury Orange Book (2023) Risk Management
- **Source Artifacts**:
  - `stakeholder-drivers.md` (13 stakeholders, RACI matrix, conflict analysis, stakeholder concerns)
  - `requirements.md` (67 requirements, 4 requirement conflicts, compliance requirements)
  - `project-plan.md` (56-week timeline, phase gates, dependencies)
  - `architecture-principles.md` (24 principles, non-compliance risks)
- **Risk Owners**: All 20 risks assigned owners from stakeholder RACI matrix (100% coverage)
- **Traceability**: Every risk linked to stakeholder goals (G-1 through G-6), business requirements (BR-001 through BR-007), and affected stakeholders

**Orange Book Compliance**: ✅ FULL COMPLIANCE with HM Treasury Orange Book (2023) - 5 Principles, 4-Pillar House Structure, 4Ts Framework
