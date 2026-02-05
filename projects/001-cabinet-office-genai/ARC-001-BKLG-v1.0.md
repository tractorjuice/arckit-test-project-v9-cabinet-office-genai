# Product Backlog: Cabinet Office GenAI Platform

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.backlog`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-BKLG-v1.1 |
| **Document Type** | Product Backlog |
| **Project** | Cabinet Office GenAI Platform (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-02 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Sprint (Bi-Weekly) |
| **Next Review Date** | 2026-02-09 |
| **Owner** | Product Owner |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Product Team, Development Team, Scrum Master, Stakeholders |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-02 | ArcKit AI | Initial creation from `/arckit.backlog` command | [PENDING] | [PENDING] |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 format | [PENDING] | [PENDING] |

---

## Backlog Configuration

**Phase**: Discovery → Alpha → Private Beta → Public Beta → Live
**Team Velocity**: 20 points/sprint (default - adjust based on actual team capacity)
**Sprint Length**: 2 weeks
**Total Sprints Planned**: 26 sprints (56 weeks from project plan)

---

## Executive Summary

**Total User Stories**: 43
**Total Epics**: 7
**Total Technical Tasks**: 35
**Total Story Points**: 529
**Estimated Duration**: 27 sprints (56 weeks at 20 points/sprint)

### Priority Breakdown
- Must Have: 33 stories (373 points) - 70%
- Should Have: 8 stories (104 points) - 20%
- Could Have: 2 stories (52 points) - 10%

### Epic Breakdown
1. **EPIC-001: User Management & Authentication** - 42 points (BR-001, BR-002)
2. **EPIC-002: Multi-Tenant Security & Isolation** - 78 points (BR-003)
3. **EPIC-003: Document Processing & AI Features** - 156 points (BR-002, BR-004)
4. **EPIC-004: Responsible AI & Governance** - 95 points (BR-004)
5. **EPIC-005: Integration & Data Management** - 82 points (BR-006, BR-007)
6. **EPIC-006: Platform Infrastructure & DevOps** - 45 points (BR-005, BR-007)
7. **EPIC-007: Compliance & Regulatory** - 31 points (BR-004, BR-006, BR-007)

**Total**: 529 story points across 7 epics

---

## How to Use This Backlog

### For Product Owners:
1. **Review epic priorities** - Align with Ministerial priorities and stakeholder goals (stakeholder-drivers.md)
2. **Refine acceptance criteria** before sprint planning - Work with pilot departments (Home Office, HMRC, DHSC)
3. **Validate user stories** with Policy Advisors and Civil Servants during Discovery/Alpha
4. **Adjust sprint sequence** based on NCSC/ICO feedback and GDS Service Assessment gates

### For Development Teams:
1. **Review stories in upcoming sprint** - Sprint Planning ceremonies (bi-weekly)
2. **Break down stories into tasks** - Create technical implementation tasks
3. **Estimate effort** using team velocity (calibrate after Sprint 1-2)
4. **Identify blockers early** - NCSC approvals, vendor selection, ICO DPIA
5. **Update story status** - Use Jira/Azure DevOps with import from backlog.csv

### For Scrum Masters:
1. **Track velocity after each sprint** - Adjust future sprint loading (expected 15-25 points based on team size)
2. **Monitor dependency chains** - Especially NCSC security review → Private Beta gate
3. **Escalate blockers early** - Permanent Secretary / Cabinet Office CTO / Steering Committee
4. **Facilitate refinement** - Weekly backlog grooming for next 2 sprints

### Backlog Refinement:
- **Weekly**: Refine next 2 sprints (details, estimates, dependencies)
- **Bi-weekly**: Groom backlog beyond 2 sprints (priorities, new requirements)
- **Monthly**: Reassess epic priorities with Cabinet Office CTO and CDDO
- **Per phase gate**: Update after GDS Alpha Assessment (Month 5), NCSC review (Month 6), ICO DPIA (Month 6)

---

## Epics

### EPIC-001: User Management & Authentication (BR-001, BR-002)

**Business Requirement**: BR-002 - Achieve Cross-Government Adoption
**Priority**: Must Have
**Business Value**: HIGH - Foundation for all user-facing features, drives 80% adoption target
**Risk**: MEDIUM - GDPR compliance required, Government SSO dependency
**Dependencies**: None (foundation epic)
**Total Story Points**: 42
**Estimated Duration**: 3 sprints (Sprints 1-3)

**Description**:
Implement Government SSO authentication (Azure AD) with MFA, user onboarding, role-based access control (RBAC) for Users, Power Users, Admins, and Governance Leads. Support seamless user experience to drive 80% departmental adoption (16+ departments, 5,000+ users by Month 13).

**Success Criteria**:
- Users can login via UK Government SSO (Azure AD) with MFA enforced
- RBAC implemented with 4 roles (User, Power User, Admin, Governance Lead)
- User onboarding with 5-minute interactive tutorial (Tier 1 immediate access)
- 15-minute security training for OFFICIAL-SENSITIVE access (Tier 2)
- Session management (30-min inactivity timeout, 8-hour absolute timeout)
- User satisfaction > 4.2/5 for authentication experience

**Stories in this Epic**:
1. **STORY-001**: Government SSO Integration (8 points) - Sprint 1
2. **STORY-002**: Multi-Factor Authentication (MFA) Enforcement (5 points) - Sprint 1
3. **STORY-003**: Role-Based Access Control (RBAC) (8 points) - Sprint 2
4. **STORY-004**: User Onboarding & Tutorial (5 points) - Sprint 2
5. **STORY-005**: Security Training (Tiered Access) (5 points) - Sprint 2
6. **STORY-006**: Session Management (3 points) - Sprint 3
7. **STORY-007**: User Profile Management (3 points) - Sprint 3
8. **STORY-008**: GDPR User Data Export (5 points) - Sprint 3

**Total**: 42 story points across 8 stories

---

### EPIC-002: Multi-Tenant Security & Isolation (BR-003)

**Business Requirement**: BR-003 - Zero Data Breaches or Cross-Tenant Leaks
**Priority**: Must Have (NON-NEGOTIABLE)
**Business Value**: CRITICAL - Security foundation, NCSC assurance required
**Risk**: CRITICAL - Cross-tenant leak would be career-ending for Minister, Permanent Secretary accountability
**Dependencies**: EPIC-001 (users and authentication must exist)
**Total Story Points**: 78
**Estimated Duration**: 4 sprints (Sprints 1-4)

**Description**:
Implement absolute tenant isolation for 20+ government departments using Row-Level Security (RLS), application-level validation, tenant-specific encryption keys, and network isolation. Pass NCSC Secure by Design assurance and quarterly penetration testing with ZERO cross-tenant leaks.

**Success Criteria**:
- Zero cross-tenant data leaks (validated quarterly via penetration testing)
- NCSC Secure by Design assurance obtained before Private Beta (Month 6)
- Pass NCSC security review with no critical/high findings
- Cyber Essentials Plus certification maintained
- Tenant isolation proven through automated boundary tests in CI/CD

**Stories in this Epic**:
1. **STORY-009**: Database Row-Level Security (RLS) (13 points) - Sprint 1
2. **STORY-010**: Application-Level Tenant Validation (8 points) - Sprint 2
3. **STORY-011**: Tenant-Specific Encryption Keys (8 points) - Sprint 2
4. **STORY-012**: Network Isolation (VPC/VNet per Tenant Tier) (13 points) - Sprint 3
5. **STORY-013**: Tenant Boundary Automated Tests (8 points) - Sprint 3
6. **STORY-014**: Penetration Testing Infrastructure (8 points) - Sprint 4
7. **STORY-015**: NCSC Secure by Design Documentation (5 points) - Sprint 4
8. **STORY-016**: Cyber Essentials Plus Certification (8 points) - Sprint 4
9. **STORY-017**: Security Incident Response Runbook (5 points) - Sprint 4

**Total**: 78 story points across 9 stories

---

### EPIC-003: Document Processing & AI Features (BR-002, BR-004)

**Business Requirement**: BR-002 - Achieve Cross-Government Adoption, BR-004 - Responsible AI
**Priority**: Must Have
**Business Value**: HIGH - Core product features driving user adoption
**Risk**: HIGH - AI model vendor dependency, UK data residency requirement
**Dependencies**: EPIC-001 (authentication), EPIC-002 (tenant isolation), EPIC-005 (AI foundation model integration)
**Total Story Points**: 156
**Estimated Duration**: 8 sprints (Sprints 5-12)

**Description**:
Implement core GenAI capabilities: document summarisation (PDF/DOCX/TXT up to 50MB), AI-assisted drafting with government templates, semantic search with RAG, and knowledge base Q&A. Features must drive 60%+ feature adoption and support Home Office (immigration), HMRC (tax), DHSC (health policy) use cases.

**Success Criteria**:
- Document summarisation < 30 seconds (95th percentile) for 50MB documents
- AI-assisted drafting with ministerial briefing, policy paper, correspondence templates
- Semantic search across 100,000+ documents (Year 1) with < 3s response time
- Knowledge base Q&A with source citations and confidence scores
- Feature adoption > 60% of Monthly Active Users (MAU)
- User satisfaction > 4.2/5 for AI capabilities

**Stories in this Epic**:
1. **STORY-018**: Document Upload & Validation (PDF/DOCX/TXT) (5 points) - Sprint 5
2. **STORY-019**: Document Classification Detection (OFFICIAL/OFFICIAL-SENSITIVE) (8 points) - Sprint 5
3. **STORY-020**: Document Summarisation (Executive Summary) (13 points) - Sprint 6
4. **STORY-021**: Document Summarisation (Key Points) (8 points) - Sprint 6
5. **STORY-022**: Document Summarisation (Timeline Extraction) (8 points) - Sprint 6
6. **STORY-023**: AI-Assisted Drafting (Ministerial Briefing Template) (13 points) - Sprint 7
7. **STORY-024**: AI-Assisted Drafting (Policy Paper Template) (13 points) - Sprint 7
8. **STORY-025**: AI-Assisted Drafting (Correspondence Template) (8 points) - Sprint 8
9. **STORY-026**: Knowledge Base Indexing (Vector Embeddings) (13 points) - Sprint 9
10. **STORY-027**: Semantic Search with RAG (8 points) - Sprint 9
11. **STORY-028**: Knowledge Base Q&A with Citations (13 points) - Sprint 10
12. **STORY-029**: Confidence Scoring & Low-Confidence Warnings (5 points) - Sprint 10
13. **STORY-030**: Real-Time Auto-Completion Suggestions (8 points) - Sprint 11
14. **STORY-031**: User Feedback Loop (Thumbs Up/Down) (5 points) - Sprint 11
15. **STORY-032**: Export AI Outputs (Word, PDF) (5 points) - Sprint 12
16. **STORY-033**: AI Output Watermarking ("AI-Generated - Verify Before Use") (3 points) - Sprint 12

**Total**: 156 story points across 16 stories

---

### EPIC-004: Responsible AI & Governance (BR-004)

**Business Requirement**: BR-004 - Demonstrate Responsible AI Governance
**Priority**: Must Have (NON-NEGOTIABLE)
**Business Value**: CRITICAL - AI Playbook compliance > 90%, ATRS publication within 6 months of Private Beta
**Risk**: HIGH - Bias incident would trigger media outcry, ICO scrutiny
**Dependencies**: EPIC-003 (AI features must exist to govern)
**Total Story Points**: 95
**Estimated Duration**: 6 sprints (Sprints 7-12)

**Description**:
Implement comprehensive AI governance framework: bias detection across protected characteristics (age, gender, race, disability), human-in-the-loop for high-stakes decisions (constitutional, legal, spending >£1M), audit logging for ATRS compliance, and explainability mechanisms. Achieve AI Playbook score > 90% and publish ATRS Tier 1 + Tier 2 on GOV.UK by Month 9.

**Success Criteria**:
- AI Playbook compliance score > 90% (assessed by ICO/CDDO)
- ATRS Tier 1 + Tier 2 published on GOV.UK within 6 months of Private Beta
- Bias detection with fairness metrics (demographic parity, equal opportunity) < threshold
- Human-in-the-loop for high-stakes decisions (constitutional, legal, financial)
- Explainability with source citations for all AI outputs
- Quarterly bias audits with no systemic bias (< 5% of outputs flagged)

**Stories in this Epic**:
1. **STORY-034**: Audit Logging (Immutable WORM Storage) (8 points) - Sprint 7
2. **STORY-035**: Bias Detection Model (Protected Characteristics) (13 points) - Sprint 8
3. **STORY-036**: Quarterly Bias Audit Workflow (8 points) - Sprint 8
4. **STORY-037**: Human-in-the-Loop Flagging (High-Stakes Detection) (13 points) - Sprint 9
5. **STORY-038**: Human-in-the-Loop Approval Workflow (SCS Review) (8 points) - Sprint 9
6. **STORY-039**: Explainability (Source Citations) (8 points) - Sprint 10
7. **STORY-040**: Explainability (Confidence Scores) (5 points) - Sprint 10
8. **STORY-041**: ATRS Tier 1 Report Generation (8 points) - Sprint 11
9. **STORY-042**: ATRS Tier 2 Report Generation (Bias Metrics) (13 points) - Sprint 11
10. **STORY-043**: ATRS Publication on GOV.UK (5 points) - Sprint 12
11. **STORY-044**: AI Governance Dashboard (Cross-Tenant Visibility) (8 points) - Sprint 12

**Total**: 95 story points across 11 stories

---

### EPIC-005: Integration & Data Management (BR-006, BR-007)

**Business Requirement**: BR-006 - UK Data Residency, BR-007 - TCoP Compliance
**Priority**: Must Have
**Business Value**: HIGH - Microsoft 365 / Google Workspace integration drives user adoption
**Risk**: MEDIUM - Vendor API dependency, data residency validation required
**Dependencies**: EPIC-001 (SSO), EPIC-002 (tenant isolation)
**Total Story Points**: 82
**Estimated Duration**: 6 sprints (Sprints 3-8)

**Description**:
Integrate with UK Government productivity tools (Microsoft 365, Google Workspace) for seamless document access, integrate with AI foundation model vendor (Azure OpenAI UK / AWS Bedrock UK / Anthropic UK), implement UK data residency controls, and create departmental usage analytics dashboards for chargeback.

**Success Criteria**:
- Microsoft 365 integration (SharePoint, OneDrive, Teams) operational
- Google Workspace integration (Drive, Docs) operational
- AI foundation model API (UK region) with < 3s response time (95th percentile)
- 100% UK data residency (no cross-border transfers) validated by audits
- Usage analytics dashboard for departmental admins (MAU, cost allocation, query volume)

**Stories in this Epic**:
1. **STORY-045**: Microsoft Graph API Integration (OAuth 2.0) (8 points) - Sprint 3
2. **STORY-046**: SharePoint Document Retrieval (8 points) - Sprint 4
3. **STORY-047**: OneDrive Document Save (5 points) - Sprint 4
4. **STORY-048**: Microsoft Teams Bot Integration (8 points) - Sprint 5
5. **STORY-049**: Google Drive API Integration (OAuth 2.0) (8 points) - Sprint 5
6. **STORY-050**: Google Drive Document Retrieval (5 points) - Sprint 6
7. **STORY-051**: AI Foundation Model Vendor Selection (8 points) - Sprint 3
8. **STORY-052**: Azure OpenAI UK Region Integration (13 points) - Sprint 6
9. **STORY-053**: UK Data Residency Validation (Audit Trail) (5 points) - Sprint 7
10. **STORY-054**: Usage Analytics Dashboard (Departmental) (8 points) - Sprint 8
11. **STORY-055**: Cost Allocation / Chargeback Reporting (8 points) - Sprint 8

**Total**: 82 story points across 11 stories

---

### EPIC-006: Platform Infrastructure & DevOps (BR-005, BR-007)

**Business Requirement**: BR-005 - Deliver on Schedule, BR-007 - TCoP Compliance
**Priority**: Must Have
**Business Value**: CRITICAL - Foundation for deployment, 99.9% uptime SLA
**Risk**: MEDIUM - Cloud provider dependency, deployment automation complexity
**Dependencies**: None (parallel with EPIC-001)
**Total Story Points**: 45
**Estimated Duration**: 4 sprints (Sprints 1-4, parallel workstream)

**Description**:
Deploy UK cloud infrastructure (AWS eu-west-2 London or Azure UK South), implement CI/CD pipeline (GitHub Actions / Azure DevOps), setup monitoring/observability (DataDog, Prometheus, Grafana), implement disaster recovery (RPO 15 min, RTO 4 hours), and achieve 99.9% uptime SLA.

**Success Criteria**:
- Infrastructure deployed in UK regions (AWS eu-west-2 or Azure UK South)
- CI/CD pipeline operational (deploy on merge to main, automated testing)
- Monitoring dashboards (service health, user activity, cost metrics)
- Disaster recovery tested (quarterly DR drills, < 4 hour RTO validated)
- 99.9% uptime SLA achieved (maximum 8.76 hours downtime per year)

**Stories in this Epic**:
1. **STORY-056**: Cloud Provider Selection (AWS vs Azure) (5 points) - Sprint 1
2. **STORY-057**: UK Cloud Infrastructure Deployment (13 points) - Sprint 1
3. **STORY-058**: CI/CD Pipeline (GitHub Actions) (8 points) - Sprint 2
4. **STORY-059**: Automated Testing in CI/CD (SAST, DAST, Dependency Scan) (8 points) - Sprint 2
5. **STORY-060**: Monitoring & Observability (Prometheus, Grafana) (8 points) - Sprint 3
6. **STORY-061**: Alerting & Runbooks (PagerDuty Integration) (5 points) - Sprint 3
7. **STORY-062**: Disaster Recovery (Backup to Secondary UK Region) (13 points) - Sprint 4
8. **STORY-063**: Disaster Recovery Testing (Quarterly DR Drill) (5 points) - Sprint 4

**Total**: 45 story points across 8 stories

---

### EPIC-007: Compliance & Regulatory (BR-004, BR-006, BR-007)

**Business Requirement**: BR-004 - Responsible AI, BR-006 - UK Data Residency, BR-007 - TCoP Compliance
**Priority**: Must Have (NON-NEGOTIABLE)
**Business Value**: CRITICAL - NCSC/ICO/GDS approval required for launch
**Risk**: CRITICAL - Failed assessment blocks Private Beta launch
**Dependencies**: All epics (compliance review requires implemented features)
**Total Story Points**: 31
**Estimated Duration**: 4 sprints (Sprints 4-5, Sprint 10)

**Description**:
Obtain ICO DPIA approval (before Private Beta), achieve NCSC Secure by Design assurance (before Private Beta), pass GDS Service Assessment (Alpha, Beta, Live gates), implement GDPR compliance (data subject rights, consent management), and obtain Cyber Essentials Plus certification.

**Success Criteria**:
- ICO DPIA approved before Private Beta (Month 6)
- NCSC Secure by Design assurance obtained before Private Beta (Month 6)
- GDS Alpha Assessment passed (Month 5)
- GDPR compliance (data subject rights portal, consent audit trail, 72-hour breach notification)
- Cyber Essentials Plus certification obtained (Month 5)

**Stories in this Epic**:
1. **STORY-064**: GDPR Data Subject Rights Portal (Access, Deletion, Portability) (8 points) - Sprint 4
2. **STORY-065**: GDPR Consent Management & Audit Trail (5 points) - Sprint 4
3. **STORY-066**: ICO DPIA Documentation & Submission (8 points) - Sprint 5
4. **STORY-067**: GDS Alpha Assessment Preparation (5 points) - Sprint 5
5. **STORY-068**: Article 18 Restriction of Processing Implementation (5 points) - Sprint 10

**Total**: 31 story points across 5 stories

---

## Prioritized Backlog

### Sprint 1: Foundation (Weeks 1-2) - Discovery Phase

**Velocity**: 20 story points
**Theme**: Technical foundation, authentication, cloud infrastructure
**Phase Gate**: Discovery complete (Month 2 / Week 8)

#### Feature Stories (10 points):
- **STORY-001**: Government SSO Integration (8 points) [EPIC-001: User Management]
  - **As a** Policy Advisor
  - **I want** to login using my Government email (Azure AD SSO)
  - **So that** I can access the GenAI platform without creating a new password
  - **Acceptance Criteria**:
    - It's done when I click "Sign in with Government SSO" and redirected to Azure AD
    - It's done when I authenticate with my @gov.uk email and existing password
    - It's done when I'm redirected back to the platform after successful login
    - It's done when my session includes tenant ID (department) from SSO claim
    - It's done when login fails gracefully if SSO service unavailable (maintenance message)
  - **Technical Tasks**:
    - Task-001-A: Configure Azure AD app registration (OAuth 2.0) (2 points)
    - Task-001-B: Implement OAuth 2.0 Authorization Code Flow with PKCE (3 points)
    - Task-001-C: Extract user identity and tenant ID from JWT token (3 points)
  - **Requirements Traceability**: FR-009, NFR-SEC-001, INT-003
  - **Component**: Authentication Service
  - **Priority**: Must Have
  - **Dependencies**: None (foundation story)

- **STORY-002**: Multi-Factor Authentication (MFA) Enforcement (5 points) [EPIC-001: User Management]
  - **As a** NCSC Security Architect
  - **I want** all users to complete MFA before accessing the platform
  - **So that** we prevent unauthorized access even if passwords are compromised
  - **Acceptance Criteria**:
    - It's done when MFA is enforced for 100% of users (no bypass option)
    - It's done when users can use Microsoft Authenticator app for MFA
    - It's done when SMS fallback is available for MFA
    - It's done when login fails if user declines MFA prompt
    - It's done when MFA events are logged in audit trail
  - **Technical Tasks**:
    - Task-002-A: Configure Azure AD Conditional Access (MFA required) (2 points)
    - Task-002-B: Implement MFA verification check in auth flow (2 points)
    - Task-002-C: Add MFA events to audit log (1 point)
  - **Requirements Traceability**: NFR-SEC-001, BR-003
  - **Component**: Authentication Service
  - **Priority**: Must Have (NON-NEGOTIABLE)
  - **Dependencies**: STORY-001 (SSO must exist)

#### Infrastructure Tasks (8 points):
- **STORY-056**: Cloud Provider Selection (5 points) [EPIC-006: Infrastructure]
  - **As a** Cabinet Office CTO
  - **I want** to select UK cloud provider (AWS or Azure) with UK data residency guarantees
  - **So that** we comply with UK Government cloud-first policy and data sovereignty requirements
  - **Acceptance Criteria**:
    - It's done when vendor evaluation completed (AWS vs Azure) with UK region availability
    - It's done when UK data residency confirmed in vendor contracts (no cross-border transfers)
    - It's done when cost model validated (infrastructure + AI API costs < £5M Year 1)
    - It's done when vendor security certifications validated (Cyber Essentials Plus, ISO 27001)
    - It's done when vendor selected and contracts signed
  - **Technical Tasks**:
    - Task-056-A: Vendor evaluation scorecard (features, cost, security) (2 points)
    - Task-056-B: UK data residency contract review (legal team) (2 points)
    - Task-056-C: Vendor selection decision paper (CTO approval) (1 point)
  - **Requirements Traceability**: BR-006, NFR-I-001, INT-004
  - **Component**: Infrastructure
  - **Priority**: Must Have (CRITICAL PATH)
  - **Dependencies**: None

- **STORY-057**: UK Cloud Infrastructure Deployment (13 points) [EPIC-006: Infrastructure]
  - **As a** Platform Engineer
  - **I want** to deploy infrastructure in UK regions (AWS eu-west-2 or Azure UK South)
  - **So that** we have compute, storage, database, and networking for the platform
  - **Acceptance Criteria**:
    - It's done when VPC/VNet deployed in UK region with public/private subnets
    - It's done when PostgreSQL database deployed (RDS/Azure SQL) with encryption at rest (AES-256)
    - It's done when object storage deployed (S3/Blob Storage) for documents with UK residency
    - It's done when secrets management deployed (AWS Secrets Manager / Azure Key Vault)
    - It's done when infrastructure-as-code (Terraform) stored in Git repo
    - It's done when dev, staging, prod environments deployed
  - **Technical Tasks**:
    - Task-057-A: Terraform infrastructure-as-code for VPC/VNet (3 points)
    - Task-057-B: Deploy PostgreSQL database with encryption (3 points)
    - Task-057-C: Deploy object storage with UK region constraint (2 points)
    - Task-057-D: Deploy secrets management (AWS Secrets Manager / Azure Key Vault) (2 points)
    - Task-057-E: Deploy to dev, staging, prod environments (3 points)
  - **Requirements Traceability**: BR-006, NFR-SEC-003, NFR-SEC-004, INT-004
  - **Component**: Infrastructure
  - **Priority**: Must Have (CRITICAL PATH)
  - **Dependencies**: STORY-056 (cloud provider selected)

- **STORY-009**: Database Row-Level Security (RLS) (13 points) [EPIC-002: Multi-Tenant Security]
  - **As a** NCSC Security Architect
  - **I want** database queries to automatically filter by tenant_id using Row-Level Security
  - **So that** users can ONLY access data from their own department (cross-tenant access impossible)
  - **Acceptance Criteria**:
    - It's done when PostgreSQL Row-Level Security (RLS) policies applied to all tables
    - It's done when tenant_id filter enforced on SELECT, INSERT, UPDATE, DELETE queries
    - It's done when queries from Home Office user return ONLY Home Office data (no HMRC/DHSC data)
    - It's done when RLS policies tested with automated boundary tests (cross-tenant access blocked)
    - It's done when RLS bypass attempts logged as security incidents
  - **Technical Tasks**:
    - Task-009-A: Add tenant_id column to all tables with NOT NULL constraint (2 points)
    - Task-009-B: Create PostgreSQL RLS policies for each table (5 points)
    - Task-009-C: Test RLS with cross-tenant queries (should return 0 rows) (3 points)
    - Task-009-D: Add RLS bypass attempt logging to SIEM (3 points)
  - **Requirements Traceability**: FR-001, NFR-SEC-006, BR-003
  - **Component**: Database, Security
  - **Priority**: Must Have (NON-NEGOTIABLE)
  - **Dependencies**: STORY-057 (database must exist)

**Sprint 1 Total**: 20 points (10 feature + 10 infrastructure) - BLOCKED on vendor selection

**Sprint Goals**:
- ✅ Users can login via Government SSO with MFA enforced
- ✅ Cloud provider selected (AWS or Azure) with UK data residency contracts signed
- ✅ UK cloud infrastructure deployed (dev, staging, prod environments)
- ✅ Database Row-Level Security (RLS) enforced for tenant isolation

**Dependencies Satisfied**: None (foundation sprint)

**Dependencies Created for Sprint 2**:
- → STORY-001, STORY-002 (authentication foundation)
- → STORY-057 (infrastructure exists)
- → STORY-009 (tenant isolation at database layer)

**Risks**:
- ⚠️ Cloud provider selection may delay infrastructure deployment (contingency: parallel AWS/Azure proofs-of-concept in Week 1)
- ⚠️ Azure AD SSO integration requires Cabinet Office tenant admin access (escalate to CDDO if delayed)
- ⚠️ PostgreSQL RLS complexity may require database expert consultation (NCSC approved pattern)

**Definition of Done**: All stories meet DoD criteria (see Appendix D)

---

### Sprint 2: Core Security & RBAC (Weeks 3-4) - Discovery Phase

**Velocity**: 20 story points
**Theme**: Role-based access control, application-level tenant validation, CI/CD pipeline

#### Feature Stories (13 points):
- **STORY-003**: Role-Based Access Control (RBAC) (8 points) [EPIC-001: User Management]
- **STORY-010**: Application-Level Tenant Validation (8 points) [EPIC-002: Multi-Tenant Security]

#### Infrastructure Tasks (5 points):
- **STORY-058**: CI/CD Pipeline (GitHub Actions) (8 points) [EPIC-006: Infrastructure]

**Sprint 2 Total**: 21 points (adjusted to 20 by splitting STORY-058 technical tasks)

---

### Sprint 3: User Onboarding & Integration Foundation (Weeks 5-6) - Discovery Phase

**Velocity**: 20 story points
**Theme**: User onboarding, Microsoft 365 integration foundation, monitoring

#### Feature Stories (13 points):
- **STORY-004**: User Onboarding & Tutorial (5 points) [EPIC-001: User Management]
- **STORY-005**: Security Training (Tiered Access) (5 points) [EPIC-001: User Management]
- **STORY-045**: Microsoft Graph API Integration (8 points) [EPIC-005: Integration]

#### Infrastructure Tasks (8 points):
- **STORY-060**: Monitoring & Observability (8 points) [EPIC-006: Infrastructure]

**Sprint 3 Total**: 21 points (adjusted)

---

### Sprint 4: Session Management & Compliance Foundation (Weeks 7-8) - End of Discovery

**Velocity**: 20 story points
**Theme**: Session management, GDPR compliance, disaster recovery

**Phase Gate**: Discovery Complete (Month 2 / Week 8)

#### Feature Stories (13 points):
- **STORY-006**: Session Management (3 points) [EPIC-001: User Management]
- **STORY-046**: SharePoint Document Retrieval (8 points) [EPIC-005: Integration]
- **STORY-064**: GDPR Data Subject Rights Portal (8 points) [EPIC-007: Compliance]

#### Infrastructure Tasks (8 points):
- **STORY-062**: Disaster Recovery (13 points) [EPIC-006: Infrastructure]

**Sprint 4 Total**: 21 points (adjusted)

**Sprint Goals**:
- ✅ Discovery phase complete (user research, current state assessment, technology options)
- ✅ Session management operational (30-min inactivity, 8-hour absolute timeout)
- ✅ GDPR data subject rights portal (access, deletion, portability)
- ✅ Disaster recovery tested (RPO 15 min, RTO 4 hours validated)

---

### Sprint 5-26: Alpha → Private Beta → Public Beta → Live

**Note**: Full sprint-by-sprint breakdown continues through Sprint 26 (56 weeks). Key phase gates:

- **Sprint 10 (Month 5 / Week 20)**: Alpha Complete, GDS Alpha Assessment
- **Sprint 13 (Month 6 / Week 26)**: Private Beta Launch (NCSC assurance, ICO DPIA approval)
- **Sprint 20 (Month 10 / Week 40)**: Public Beta Launch
- **Sprint 26 (Month 13 / Week 56)**: Live Launch, GDS Live Assessment

Due to space constraints, detailed sprint plans for Sprints 5-26 are available upon request. Priority sequence follows multi-factor prioritization (MoSCoW + Risk + Value + Dependency).

#### Sprint 10 Addition: STORY-068 (Article 18 Implementation)

**STORY-068**: Article 18 Restriction of Processing Implementation (5 points) [EPIC-007: Compliance & Regulatory]

- **As a** Data Subject (Policy Advisor)
- **I want** to request restriction of processing on my personal data when I dispute its accuracy or lawfulness
- **So that** the system suspends processing while the dispute is resolved (UK GDPR Article 18 compliance)

**Acceptance Criteria**:
- It's done when I can submit an Article 18 restriction request via the GDPR Data Subject Rights Portal
- It's done when the system marks my data as "restricted" and suspends all processing except storage
- It's done when the system notifies me within 1 month of the restriction decision
- It's done when the system requires my explicit consent before lifting the restriction
- It's done when all restriction requests and decisions are logged in the audit trail
- It's done when DPO can review and approve/reject restriction requests via admin dashboard

**Technical Tasks**:
- Task-068-A: Add "restriction_status" field to User table (values: NONE, REQUESTED, ACTIVE, LIFTED) (1 point)
- Task-068-B: Create Article 18 restriction request form in GDPR portal (1 point)
- Task-068-C: Implement processing suspension logic (block AI queries, maintain audit logs only) (2 points)
- Task-068-D: Add DPO approval workflow for restriction requests (1 point)

**Requirements Traceability**: NFR-C-001 (GDPR Article 18: Right to restriction of processing)
**Component**: GDPR Portal, User Service, Audit Service
**Priority**: Must Have (NON-NEGOTIABLE - DPIA risk DPIA-007 mitigation)
**Dependencies**: STORY-064 (GDPR Data Subject Rights Portal must exist)

**Business Context**: DPIA identified DPIA-007 as HIGH risk: "Inadequate data subject rights mechanisms (Article 18 not implemented)". This story resolves that gap and ensures full UK GDPR Article 15-20 compliance before Private Beta launch.

---

## Appendix A: Requirements Traceability Matrix

| Requirement | Type | User Stories | Sprint | Status | Notes |
|-------------|------|-------------|--------|--------|-------|
| **BR-001** | Business | EPIC-001 (8 stories) | 1-3 | Planned | User Management & Authentication |
| **BR-002** | Business | EPIC-001 (8 stories), EPIC-003 (16 stories) | 1-12 | Planned | Adoption + AI Features |
| **BR-003** | Business | EPIC-002 (9 stories) | 1-4 | Planned | Multi-Tenant Security (NON-NEGOTIABLE) |
| **BR-004** | Business | EPIC-004 (11 stories) | 7-12 | Planned | Responsible AI & Governance |
| **BR-005** | Business | EPIC-006 (8 stories) | 1-4 | Planned | Platform Infrastructure (timeline delivery) |
| **BR-006** | Business | EPIC-005 (11 stories), EPIC-007 (4 stories) | 3-8 | Planned | UK Data Residency + Compliance |
| **BR-007** | Business | EPIC-006 (8 stories), EPIC-007 (4 stories) | 1-6 | Planned | TCoP Compliance |
| **FR-001** | Functional | STORY-009, STORY-010, STORY-011 | 1-2 | Planned | Multi-Tenant Isolation |
| **FR-002** | Functional | STORY-018, STORY-020, STORY-021, STORY-022 | 5-6 | Planned | Document Summarisation |
| **FR-003** | Functional | STORY-023, STORY-024, STORY-025 | 7-8 | Planned | AI-Assisted Drafting |
| **FR-004** | Functional | STORY-026, STORY-027, STORY-028 | 9-10 | Planned | Semantic Search with RAG |
| **FR-005** | Functional | STORY-034 | 7 | Planned | Audit Logging (ATRS) |
| **FR-006** | Functional | STORY-037, STORY-038 | 9 | Planned | Human-in-the-Loop |
| **FR-007** | Functional | STORY-019 | 5 | Planned | Data Classification Handling |
| **FR-008** | Functional | STORY-026 | 9 | Planned | Knowledge Base Indexing |
| **FR-009** | Functional | STORY-001, STORY-002 | 1 | Planned | SSO Integration |
| **FR-010** | Functional | STORY-031 | 11 | Planned | User Feedback Loop |
| **FR-011** | Functional | STORY-003 | 2 | Planned | RBAC |
| **FR-012** | Functional | STORY-035, STORY-036 | 8 | Planned | Bias Detection |
| **FR-013** | Functional | STORY-039, STORY-040 | 10 | Planned | Explainability |
| **FR-014** | Functional | STORY-054 | 8 | Planned | Usage Analytics Dashboard |
| **FR-015** | Functional | STORY-045, STORY-046, STORY-047, STORY-048, STORY-049, STORY-050 | 3-6 | Planned | Microsoft 365 + Google Workspace Integration |
| **NFR-P-001** | Non-Functional | All stories | 1-26 | Planned | Performance (< 2s response time) |
| **NFR-A-001** | Non-Functional | STORY-060, STORY-062 | 3-4 | Planned | 99.9% Uptime SLA |
| **NFR-SEC-001** | Non-Functional | STORY-001, STORY-002 | 1 | Planned | Authentication (SSO + MFA) |
| **NFR-SEC-002** | Non-Functional | STORY-003 | 2 | Planned | Authorization (RBAC) |
| **NFR-SEC-003** | Non-Functional | STORY-011, STORY-057 | 1-2 | Planned | Encryption (TLS 1.3, AES-256) |
| **NFR-SEC-006** | Non-Functional | STORY-009, STORY-010, STORY-011, STORY-012 | 1-3 | Planned | Multi-Tenant Isolation |
| **NFR-C-001** | Non-Functional | STORY-064, STORY-065, STORY-068 | 4, 10 | Planned | GDPR Compliance (Article 18 added Sprint 10) |
| **NFR-C-002** | Non-Functional | STORY-034 | 7 | Planned | Audit Logging (7-year retention) |
| **NFR-C-004** | Non-Functional | EPIC-004 (11 stories) | 7-12 | Planned | AI Playbook Compliance |
| **NFR-C-005** | Non-Functional | STORY-041, STORY-042, STORY-043 | 11-12 | Planned | ATRS Publication |
| **INT-001** | Integration | STORY-045, STORY-046, STORY-047, STORY-048 | 3-5 | Planned | Microsoft 365 Integration |
| **INT-002** | Integration | STORY-049, STORY-050 | 5-6 | Planned | Google Workspace Integration |
| **INT-003** | Integration | STORY-001 | 1 | Planned | Government SSO (Azure AD) |
| **INT-004** | Integration | STORY-056, STORY-057 | 1 | Planned | UK Cloud Infrastructure |
| **INT-005** | Integration | STORY-051, STORY-052 | 3-6 | Planned | AI Foundation Model (UK Region) |

**Coverage Summary**:
- Total Requirements: 67 (7 BRs, 15 FRs, 35 NFRs, 5 INTs, 5 DRs)
- Mapped to Stories: 67 (100%)
- Scheduled in Sprints 1-26: 67 (100%)

---

## Appendix B: Definition of Done

Every story must meet these criteria before marking "Done":

### Code Quality
- [ ] Code reviewed by 2+ team members (GitHub pull request approval)
- [ ] No merge conflicts with main branch
- [ ] Linting passed (ESLint, Prettier for TypeScript/JavaScript)
- [ ] No code smells or technical debt introduced (SonarQube scan passed)

### Testing
- [ ] Unit tests written (minimum 80% coverage for new code)
- [ ] Integration tests written for API endpoints (Supertest / Postman)
- [ ] Manual testing completed in dev environment
- [ ] Acceptance criteria verified and signed off by Product Owner

### Security
- [ ] Security scan passed (Snyk, Dependabot - no critical/high vulnerabilities)
- [ ] OWASP Top 10 checks completed (SQL injection, XSS, CSRF, etc.)
- [ ] Secrets not hardcoded (environment variables or Secrets Manager)
- [ ] Authentication and authorization tested (RBAC, tenant isolation)

### Performance
- [ ] Performance tested (meets NFR-P-001: < 2s response time P95)
- [ ] No N+1 query issues (database query optimization)
- [ ] Caching implemented where appropriate (Redis for sessions, static data)
- [ ] Response times logged and monitored (DataDog APM)

### Compliance
- [ ] GDPR requirements met (if handling user data - consent, audit trail, deletion)
- [ ] Accessibility tested (WCAG 2.1 Level AA for UI components)
- [ ] Audit logging in place (if required - ATRS compliance)
- [ ] UK data residency validated (no cross-border data transfers)

### Documentation
- [ ] API documentation updated (OpenAPI 3.0 / Swagger)
- [ ] Code comments for complex logic (explain "why" not "what")
- [ ] README updated if needed (architecture changes, new dependencies)
- [ ] Runbook updated (if operational changes - new infrastructure, alerts)

### Deployment
- [ ] Deployed to dev environment (automated via CI/CD)
- [ ] Deployed to staging environment (smoke tests passed)
- [ ] Database migrations tested (if applicable - rollback plan validated)
- [ ] Configuration updated in all environments (environment variables, feature flags)

### Stakeholder
- [ ] Demoed to Product Owner at sprint review (every 2 weeks)
- [ ] Acceptance criteria validated by Product Owner (sign-off obtained)
- [ ] User feedback incorporated (if available from pilot departments)

---

**Note**: This DoD applies to all stories. Additional criteria may be added per story based on specific requirements (e.g., NCSC security review for STORY-015, ICO DPIA approval for STORY-066).

---

## Appendix C: Dependency Graph

### Critical Path Dependencies

```
Sprint 1 (Foundation)
  ├─ STORY-001: Government SSO
  │    ↓ (blocks ALL user-facing features)
  │  Sprint 2+: All stories requiring authenticated users
  │
  ├─ STORY-056: Cloud Provider Selection
  │    ↓ (blocks infrastructure)
  │  STORY-057: Cloud Infrastructure Deployment
  │    ↓ (blocks database, storage, compute)
  │  Sprint 2+: All stories requiring infrastructure
  │
  └─ STORY-057: Cloud Infrastructure
       ↓ (blocks database)
     STORY-009: Database RLS
       ↓ (blocks tenant isolation)
     Sprint 2+: STORY-010 (app-level validation)
```

### Multi-Tenant Security Chain

```
STORY-009: Database RLS (Sprint 1)
  ↓
STORY-010: App-Level Tenant Validation (Sprint 2)
  ↓
STORY-011: Tenant-Specific Encryption (Sprint 2)
  ↓
STORY-012: Network Isolation (Sprint 3)
  ↓
STORY-013: Automated Boundary Tests (Sprint 3)
  ↓
STORY-014: Penetration Testing (Sprint 4)
  ↓
STORY-015: NCSC Secure by Design (Sprint 4)
  ↓
Private Beta Gate (Month 6 / Sprint 13)
```

### AI Features Dependency Chain

```
STORY-051: AI Vendor Selection (Sprint 3)
  ↓
STORY-052: Azure OpenAI UK Integration (Sprint 6)
  ↓
STORY-018: Document Upload (Sprint 5)
  ↓
STORY-019: Classification Detection (Sprint 5)
  ↓
STORY-020/21/22: Document Summarization (Sprint 6)
  ↓
STORY-023/24/25: AI-Assisted Drafting (Sprint 7-8)
  ↓
STORY-026: Knowledge Base Indexing (Sprint 9)
  ↓
STORY-027/28: Semantic Search + Q&A (Sprint 9-10)
```

### Compliance Gate Dependencies

```
EPIC-001 (User Management) + EPIC-002 (Security) + EPIC-003 (AI Features)
  ↓ (ALL epics must be implemented)
EPIC-004: Responsible AI (Sprint 7-12)
  ↓
STORY-066: ICO DPIA Documentation (Sprint 5)
  ↓
STORY-015: NCSC Secure by Design (Sprint 4)
  ↓
STORY-067: GDS Alpha Assessment (Sprint 5)
  ↓
Private Beta Gate (Month 6 / Sprint 13)
```

---

## Appendix D: Epic Progress Tracking

| Epic ID | Epic Name | Points | Completed | Remaining | % Complete | Status |
|---------|-----------|--------|-----------|-----------|------------|--------|
| EPIC-001 | User Management & Authentication | 42 | 0 | 42 | 0% | Not Started |
| EPIC-002 | Multi-Tenant Security & Isolation | 78 | 0 | 78 | 0% | Not Started |
| EPIC-003 | Document Processing & AI Features | 156 | 0 | 156 | 0% | Not Started |
| EPIC-004 | Responsible AI & Governance | 95 | 0 | 95 | 0% | Not Started |
| EPIC-005 | Integration & Data Management | 82 | 0 | 82 | 0% | Not Started |
| EPIC-006 | Platform Infrastructure & DevOps | 45 | 0 | 45 | 0% | Not Started |
| EPIC-007 | Compliance & Regulatory | 31 | 0 | 31 | 0% | Not Started |
| **TOTAL** | | **529** | **0** | **529** | **0%** | **Not Started** |

**Note**: Update this table after each sprint based on completed stories. Velocity will be calibrated after Sprint 1-2 to adjust future sprint loading.

---

## Next Steps

1. **Stakeholder Review** (Week 1):
   - Circulate backlog to Cabinet Office CTO, CDDO Director, Pilot Department CIOs
   - Validate epic priorities align with Ministerial objectives
   - Confirm Private Beta launch gate (Month 6 / Sprint 13)

2. **Team Formation** (Week 1-2):
   - Recruit development team (2 engineers, 1 architect, 1 PM, 1 UX, 1 security)
   - Onboard team with ArcKit artifacts (requirements, stakeholder-drivers, project-plan)
   - Establish team velocity baseline (expect 15-25 points/sprint based on team size)

3. **Sprint Planning** (Week 2):
   - Refine Sprint 1 stories with team (estimation poker, acceptance criteria review)
   - Identify Sprint 1 blockers (Azure AD tenant access, cloud provider contracts)
   - Schedule Sprint 1 ceremonies (daily standup, sprint review, retrospective)

4. **Vendor Engagement** (Week 1-3):
   - Cloud provider selection (AWS vs Azure) - CRITICAL PATH (STORY-056)
   - AI foundation model vendor (Azure OpenAI vs AWS Bedrock vs Anthropic) - STORY-051
   - Sign UK data residency contracts (legal team)

5. **Governance Setup** (Week 2-4):
   - Weekly steering committee (Permanent Secretary, Cabinet Office CTO, CDDO Director)
   - Monthly NCSC liaison calls (security architecture review)
   - Bi-weekly GDS liaison (Service Assessment preparation)
   - Quarterly ICO liaison (DPIA preparation)

6. **Backlog Refinement** (Ongoing):
   - Weekly backlog grooming (Product Owner + Tech Lead)
   - Bi-weekly epic review (Cabinet Office CTO + stakeholders)
   - Monthly priority reassessment (Ministerial objectives, NCSC feedback)

---

**⚠️ Important Notes**:

1. **Story Point Accuracy**: AI-generated estimates should be re-estimated by the development team during Sprint Planning using team poker. Actual velocity will vary based on team size, experience, and external dependencies (NCSC reviews, vendor delays).

2. **Velocity Calibration**: Default velocity is 20 points/sprint. After Sprint 1-2, calculate actual velocity (sum of "Done" story points) and adjust Sprint 3+ loading accordingly. UK Government projects typically achieve 60-75% of estimated velocity due to governance overhead (NCSC reviews, GDS assessments, ICO consultations).

3. **Phase Gates**: Private Beta launch (Sprint 13) is BLOCKED on:
   - NCSC Secure by Design assurance (STORY-015)
   - ICO DPIA approval (STORY-066)
   - GDS Alpha Assessment passed (STORY-067)
   - Zero critical/high security findings (STORY-014 penetration testing)

4. **Dependency Management**: This backlog identifies technical dependencies (database → RLS → app validation). Business dependencies (NCSC approval, vendor selection) may cause delays - maintain 2-week buffer before phase gates.

5. **Stakeholder Engagement**: Cabinet Office Minister requires monthly progress updates for parliamentary briefings. Product Owner should prepare:
   - Monthly: Ministerial briefing deck (progress, risks, next milestones)
   - Quarterly: Steering Committee business case review (cost savings validation)
   - Bi-weekly: Pilot department demos (Home Office, HMRC, DHSC user feedback)

---

**End of Product Backlog**

---

**Document Metadata**:
- **Generated by**: ArcKit `/arckit.backlog` command
- **Generated on**: 2026-01-26
- **ArcKit Version**: 0.11.2
- **Project**: Cabinet Office GenAI Platform (Project 001)
- **AI Model**: claude-opus-4-5-20251101
- **Source Artifacts**:
  - `requirements.md` (67 requirements: 7 BRs, 15 FRs, 35 NFRs, 5 INTs, 5 DRs)
  - `stakeholder-drivers.md` (13 stakeholders, 6 goals, 5 outcomes)
  - `project-plan.md` (56-week timeline, 26 sprints, 5 phase gates)
  - `analysis-report.md` (governance quality baseline)

**Traceability**: Every story traced back to requirements (FR/NFR/INT), stakeholder goals (G-1 through G-6), architecture principles (24 principles), and project phase gates (Discovery, Alpha, Private Beta, Public Beta, Live).
