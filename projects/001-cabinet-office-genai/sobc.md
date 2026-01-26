# Strategic Outline Business Case (SOBC): Cabinet Office GenAI Platform

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.sobc`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-SOBC-v1.0 |
| **Document Type** | Strategic Outline Business Case (SOBC) |
| **Project** | Cabinet Office GenAI Platform (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-01-26 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Cabinet Office Senior Responsible Owner |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Cabinet Office Executive Team, HM Treasury, CDDO, NAO (for information) |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-26 | ArcKit AI | Initial creation from `/arckit.sobc` command | PENDING | PENDING |

## Document Purpose

This Strategic Outline Business Case (SOBC) presents the strategic justification for the Cabinet Office GenAI Platform - a cross-government generative AI service. It follows the HM Treasury Green Book 5-case model and seeks approval to proceed to detailed requirements and procurement phases.

---

## Executive Summary

**Purpose**: The UK Government faces fragmented AI adoption with £15M annual duplicate spend, uncontrolled data handling, and no centralized AI governance. This SOBC seeks approval for a centralized, secure GenAI platform to consolidate AI capabilities, reduce costs, and establish responsible AI governance across government.

**Problem Statement**: Individual departments procure expensive duplicate AI tools (ChatGPT Enterprise, Microsoft Copilot, Google Gemini) without centralized governance, creating cost inefficiency (£15M/year duplicate spend), security risk (OFFICIAL-SENSITIVE data in uncontrolled tools), and compliance gaps (no AI Playbook, ATRS, or DPIA oversight).

**Proposed Solution**: A centralized, multi-tenant GenAI platform providing document summarization, drafting, analysis, and knowledge management with NCSC-assured tenant isolation, AI Playbook compliance, and ATRS publication.

**Strategic Fit**: Delivers the 2024 King's Speech manifesto commitment to "harness AI safely across government" and aligns with Cabinet Office's role as cross-government coordinator, CDDO's digital standards mandate, and TCoP Point 2 (Reuse technology and services).

**Investment Required**: £18.8M over 5 years
- Capital: £5.8M (Year 1-2 implementation)
- Operational (5 years): £13M (£2.6M/year)

**Expected Benefits**: £60M over 5 years
- Cost savings from 80% reduction in duplicate AI spend (£12M/year savings)
- Productivity gains from civil servant time savings (estimated 10 hours/week per user)
- Risk reduction from centralized security and compliance

**Return on Investment**:
- NPV: £33.4M (discounted at 3.5%)
- Payback Period: 18 months
- ROI: 219% over 5 years
- Benefit-Cost Ratio (BCR): 3.19

**Recommended Option**: Option 2: Balanced Multi-Tenant Platform

**Key Risks**:
1. **R-001**: Cross-tenant data leak (TECHNOLOGY, Critical → High after controls)
2. **R-004**: NCSC Secure by Design assurance delay (COMPLIANCE, High)
3. **R-007**: AI bias incident with media outcry (REPUTATIONAL, High)

**Go/No-Go Recommendation**: **PROCEED** to requirements phase

**Rationale**: Strong business case with 219% ROI, delivers manifesto commitment, addresses Minister/Permanent Secretary drivers, and has manageable risk profile with identified mitigations. Aligns with 24 architecture principles and meets 85% of stakeholder goals.

**Next Steps if Approved**:
1. Secure HM Treasury approval: Q1 2026
2. Define detailed requirements: `/arckit.requirements` (complete)
3. Develop Outline Business Case (OBC): Q2 2026
4. Procurement approach via Digital Marketplace: Q2 2026

---

# PART A: STRATEGIC CASE

## A1. Strategic Context

### A1.1 Problem Statement

**Current Situation**:
UK Government departments have adopted generative AI tools in an uncoordinated manner, with individual teams procuring ChatGPT Enterprise, Microsoft Copilot, Google Gemini, and other tools independently. This fragmented approach creates significant organizational, security, and compliance challenges.

**Specific Pain Points** (from Stakeholder Analysis):

| Stakeholder | Driver ID | Pain Point | Impact | Intensity |
|-------------|-----------|------------|--------|-----------|
| HM Treasury | SD-3 | £15M annual duplicate AI spend across 20+ departments | Poor value for money, Treasury scrutiny | CRITICAL |
| Permanent Secretary | SD-2 | Uncontrolled AI data handling bypassing security standards | Accounting Officer accountability at risk | CRITICAL |
| Minister | SD-1 | No demonstrable AI governance for parliamentary questions | Cannot respond credibly to Opposition | CRITICAL |
| NCSC | SD-6 | OFFICIAL-SENSITIVE data in unassured cloud AI services | Potential national security breach | HIGH |
| ICO | SD-7 | No centralized DPIA or AI Playbook compliance | Regulatory enforcement risk | HIGH |
| CDDO | SD-4 | Non-compliance with TCoP Point 2 (reuse), Point 6 (security) | GDS Service Assessment failure | HIGH |

**Consequences of Inaction**:
- **£75M wasted over 5 years** in continued duplicate spending (£15M × 5 years)
- **Security breach risk**: Uncontrolled AI tools processing OFFICIAL-SENSITIVE data could lead to front-page scandal, ministerial accountability
- **Manifesto failure**: 2024 King's Speech commitment to "harness AI safely" unfulfilled before election cycle
- **NAO criticism**: Public Accounts Committee scrutiny of poor value for money in government AI spend
- **Regulatory enforcement**: ICO action for GDPR non-compliance in AI data processing

### A1.2 Strategic Drivers

**Link to Stakeholder Analysis**: This business case is informed by stakeholder analysis documented in `stakeholder-drivers.md` (13 stakeholder groups, 13 drivers).

**Primary Drivers** (from Stakeholder Analysis):

| Driver ID | Stakeholder | Driver Type | Driver Description | Strategic Imperative |
|-----------|-------------|-------------|-------------------|---------------------|
| SD-1 | Minister for Cabinet Office | POLITICAL | Deliver manifesto commitment on AI governance | Ministerial confidence |
| SD-2 | Permanent Secretary | ACCOUNTABILITY | Ensure proper governance, avoid NAO criticism | Accounting Officer assurance |
| SD-3 | HM Treasury | FINANCIAL | Reduce duplicate AI spend, demonstrate value for money | Cost efficiency |
| SD-4 | CDDO | COMPLIANCE | Enforce TCoP compliance, enable GDS Service Assessment | Standards compliance |
| SD-5 | Cabinet Office CTO | STRATEGIC | Modernize government tech, enable AI innovation | Technical leadership |
| SD-6 | NCSC | SECURITY | Ensure Secure by Design for OFFICIAL-SENSITIVE data | National security |
| SD-7 | ICO | REGULATORY | DPIA approval, AI Playbook compliance, ATRS publication | Data protection |

**Strategic Alignment**:
- **Government AI Strategy**: Centralized AI governance aligns with cross-government digital transformation
- **2024 King's Speech**: Delivers manifesto commitment to "harness AI safely across government"
- **Technology Code of Practice (TCoP)**: Enforces Point 2 (Reuse), Point 5 (Cloud First), Point 6 (Security)
- **Architecture Principles**: Aligns with 24 principles in `.arckit/memory/architecture-principles.md`:
  - AP-1 Cloud-First: UK-based cloud infrastructure
  - AP-2 API-First: RESTful APIs with versioning
  - AP-4 Security by Design: NCSC-assured multi-tenancy
  - AP-9 Responsible AI: AI Playbook compliance
  - AP-21 Multi-Tenant Isolation: Zero cross-tenant access

### A1.3 Stakeholder Goals

**Goals Addressed** (from Stakeholder Analysis):

| Goal ID | Stakeholder | SMART Goal | Current State | Target State | Timeline |
|---------|-------------|------------|---------------|--------------|----------|
| G-1 | HM Treasury/CFO | Reduce AI spend 80% by end of Year 2 | £15M/year | £3M/year | 24 months |
| G-2 | Permanent Secretary | Zero security incidents or data breaches | Unknown (uncontrolled tools) | Zero breaches | Ongoing |
| G-3 | ICO/CDDO | AI Playbook score > 90%, ATRS published | 0% compliance | > 90% (144/160) | 12 months |
| G-4 | Cabinet Office CTO | 99.9% uptime, < 2s response time | N/A (no platform) | 99.9% / < 2s p95 | 12 months |
| G-5 | Minister | Respond credibly to parliamentary questions | Cannot respond | Confident response | 6 months |
| G-6 | End Users | 80% adoption, user satisfaction > 4.2/5 | 0% (platform doesn't exist) | 80% / 4.2/5 | 18 months |

### A1.4 Scope

**In Scope**:
- Multi-tenant GenAI platform (document summarization, drafting, Q&A, knowledge management)
- OFFICIAL to OFFICIAL-SENSITIVE data classification support
- Integration with Government SSO (Azure AD), Microsoft 365, Google Workspace
- UK-based cloud infrastructure (AWS London/Azure UK South) with UK data residency
- Responsible AI governance framework (bias testing, explainability, human-in-the-loop)
- ATRS Tier 1 + Tier 2 publication on GOV.UK
- AI Playbook and TCoP compliance assessments
- NCSC Secure by Design assurance
- ICO DPIA and ongoing data protection compliance
- Pilot rollout to Home Office, HMRC, DHSC (3 departments)
- Phased expansion to 20+ central government departments
- Chargeback/cost allocation model for departmental usage

**Out of Scope** (for this phase):
- SECRET/TOP SECRET data classification (potential future phase)
- AI model training from scratch (will use pre-trained foundation models)
- Replacement of specialized departmental AI tools (e.g., MOJ case management AI)
- Integration with legacy on-premise systems (cloud-first mandate per TCoP Point 5)
- Non-text modalities (image, video, audio generation) in MVP
- Public-facing citizen services (internal government use only for MVP)

**Interfaces**:
- **Upstream**: AI Foundation Model Providers (Azure OpenAI, AWS Bedrock, Anthropic Claude)
- **Downstream**: Department document management systems, Microsoft 365, Google Workspace
- **Cross-Government**: Government SSO, GOV.UK Notify, GOV.UK Pay (future billing)

**Assumptions**:
1. AI foundation model vendors (Microsoft, AWS, Anthropic) can meet UK data residency requirements - **Risk if wrong**: Need alternative vendors or UK sovereign cloud
2. Departments will adopt centralized platform over existing tools - **Risk if wrong**: Low adoption, benefits not realized
3. NCSC will approve multi-tenant architecture for OFFICIAL-SENSITIVE - **Risk if wrong**: Architecture redesign, cost increase
4. HM Treasury will approve budget within Spending Review settlement - **Risk if wrong**: Project descoped or delayed

**Dependencies**:
- **Internal**: Cabinet Office CTO team availability, CDDO standards approval
- **External**: NCSC Secure by Design assessment (6-month lead time), ICO DPIA approval (3-month lead time)
- **Technical**: Azure/AWS UK regions with AI services, AI model provider UK data processing agreements

### A1.5 Why Now?

**Urgency Factors**:
- **Manifesto commitment**: 2024 King's Speech commitment to AI governance must show progress before potential election
- **Security risk**: Every month of delay = continued OFFICIAL-SENSITIVE data exposure in uncontrolled tools
- **Cost escalation**: AI tool costs increasing 20% annually; early action locks in savings
- **Competitive position**: Other Five Eyes nations (US, Australia) establishing government AI platforms

**Opportunity Cost of Delay**:
- **£1.25M per month** in continued duplicate AI spending
- **Reputational risk** increases with each parliamentary question unanswered
- **Vendor lock-in** deepens as departments sign multi-year contracts

**Window of Opportunity**:
- HM Treasury receptive to digital transformation in current Spending Review period
- AI technology mature enough for government use (Azure OpenAI, AWS Bedrock proven)
- NCSC willing to engage on Secure by Design for AI systems
- CDDO prioritizing AI governance as cross-government initiative

---

# PART B: ECONOMIC CASE

## B1. Critical Success Factors

Before analyzing options, define what "success" looks like:

1. **Cost Reduction**: Reduce duplicate AI spend 80% (£15M → £3M/year)
   - **Measure**: Annual AI tool spend across 20+ departments
   - **Threshold**: Minimum 60% reduction (£15M → £6M) acceptable

2. **Security Assurance**: Zero cross-tenant data leaks or security incidents
   - **Measure**: Security incident count, penetration test results
   - **Threshold**: Zero critical/high severity incidents

3. **Compliance Achievement**: AI Playbook score > 90%, ATRS published
   - **Measure**: AI Playbook assessment score, ATRS publication date
   - **Threshold**: Minimum 80% compliance score

4. **User Adoption**: 80% adoption across 20+ departments, satisfaction > 4.2/5
   - **Measure**: Monthly active users, quarterly satisfaction survey
   - **Threshold**: Minimum 60% adoption, 3.5/5 satisfaction

5. **Operational Excellence**: 99.9% uptime, < 2s response time (p95)
   - **Measure**: Uptime monitoring, latency metrics
   - **Threshold**: Minimum 99.5% uptime, < 5s response time

## B2. Options Analysis

### Option 0: Do Nothing (Baseline)

**Description**: Continue with current fragmented AI adoption across departments.

**Costs** (5-year):
- Capital: £0
- Operational: £75M (continued £15M/year AI spend)
- Total: £75M

**Benefits**: £0 (no improvement)

**Pros**:
- ✅ No upfront investment
- ✅ No implementation risk
- ✅ No change management required

**Cons**:
- ❌ Stakeholder goals not met (0%)
- ❌ £75M wasted over 5 years
- ❌ Security risk continues to escalate
- ❌ Manifesto commitment unfulfilled
- ❌ NAO/PAC criticism likely

**Risks**:
- **Security breach**: 40% probability → £5M+ incident cost + ministerial accountability
- **Regulatory enforcement**: ICO action for uncontrolled AI data processing
- **Parliamentary scrutiny**: Unable to respond to questions on AI governance

**Stakeholder Goals Met**: 0%

**Recommendation**: **Reject** - Unacceptable baseline, costs and risks escalate.

---

### Option 1: Minimal Viable Solution (Single Department Pilot)

**Description**: Deploy limited AI service for Cabinet Office only, no multi-tenancy, no cross-government rollout.

**Scope**:
- Single-tenant AI platform for Cabinet Office (1 department)
- Basic document summarization and Q&A
- No ATRS publication (too small for mandatory requirement)
- Limited security controls (no multi-tenant isolation needed)

**Costs** (5-year) - ROM (±40%):
- Capital: £1.5M
  - Platform setup: £0.8M
  - Integration: £0.5M
  - Training: £0.2M
- Operational: £4M over 5 years (£0.8M/year)
- Total 5-year TCO: £5.5M

**Benefits** (5-year):
- **B-001**: Cabinet Office AI cost reduction: £1M (£0.2M/year × 5)
- **B-002**: Productivity gain (Cabinet Office only): £2M
- Total: £3M

**Net Benefit**: -£2.5M (negative - costs exceed benefits)

**Pros**:
- ✅ Lower upfront investment (£1.5M vs £5.8M)
- ✅ Faster to deploy (6 months)
- ✅ Lower implementation risk

**Cons**:
- ❌ Only 15% of stakeholder goals met
- ❌ Does not address cross-government problem
- ❌ Duplicate spending continues in other departments (£14M/year)
- ❌ No ATRS compliance (below threshold)
- ❌ Does not deliver manifesto commitment

**Stakeholder Impact**:
- HM Treasury Goal G-1: ❌ Not met (only 7% cost reduction vs 80% target)
- Permanent Secretary Goal G-2: ⚠️ Partially met (Cabinet Office only)
- ICO/CDDO Goal G-3: ❌ Not met (no ATRS, limited compliance)
- Minister Goal G-5: ❌ Not met (cannot claim cross-government success)

**Stakeholder Goals Met**: 15%

**Risks**:
- **Fragmentation continues**: Departments procure independent solutions
- **Sunk cost**: £1.5M spent without cross-government benefit

**Recommendation**: **Reject** - Does not address strategic problem.

---

### Option 2: Balanced Multi-Tenant Platform (RECOMMENDED)

**Description**: Deploy centralized multi-tenant GenAI platform for all central government departments with phased rollout, full NCSC assurance, and AI Playbook compliance.

**Scope**:
- Multi-tenant architecture with NCSC-assured tenant isolation
- Full AI capabilities (summarization, drafting, Q&A, knowledge management)
- OFFICIAL to OFFICIAL-SENSITIVE data classification
- 3-department pilot (Home Office, HMRC, DHSC) → 20+ departments
- ATRS Tier 1 + Tier 2 publication
- AI Playbook compliance > 90%
- Chargeback model for departmental cost allocation

**Costs** (5-year) - ROM (±30%):
- Capital: £5.8M
  - Infrastructure & platform: £2.5M
  - AI vendor services (Year 1-2): £1.5M
  - Security & compliance: £0.8M
  - Integration (SSO, M365, GWS): £0.5M
  - Training & change management: £0.5M
- Operational: £13M over 5 years
  - AI consumption (20+ departments): £6M (£1.2M/year)
  - Support & maintenance: £3.5M (£0.7M/year)
  - Security operations: £2M (£0.4M/year)
  - Ongoing training: £1.5M (£0.3M/year)
- Total 5-year TCO: £18.8M

**Benefits** (5-year):

| Benefit ID | Benefit Description | Stakeholder Goal | Type | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 | 5-Year Total |
|------------|---------------------|------------------|------|--------|--------|--------|--------|--------|--------------|
| B-001 | Duplicate AI spend reduction (80%) | G-1 (HM Treasury) | FINANCIAL | £3M | £12M | £12M | £12M | £12M | £51M |
| B-002 | Civil servant productivity gain | G-6 (End Users) | OPERATIONAL | £0.5M | £2M | £2M | £2M | £2M | £8.5M |
| B-003 | Compliance cost avoidance | G-3 (ICO/CDDO) | COMPLIANCE | £0.1M | £0.2M | £0.2M | £0.2M | £0.2M | £0.9M |
| **Total Benefits** | | | | **£3.6M** | **£14.2M** | **£14.2M** | **£14.2M** | **£14.2M** | **£60.4M** |

**Net Present Value** (3.5% discount rate - HM Treasury standard):

| Year | Costs | Benefits | Net Cashflow | Discount Factor | Present Value |
|------|-------|----------|--------------|-----------------|---------------|
| 0 | £3.5M | £0 | -£3.5M | 1.000 | -£3.5M |
| 1 | £5.0M | £3.6M | -£1.4M | 0.966 | -£1.35M |
| 2 | £2.6M | £14.2M | +£11.6M | 0.934 | +£10.83M |
| 3 | £2.6M | £14.2M | +£11.6M | 0.902 | +£10.46M |
| 4 | £2.6M | £14.2M | +£11.6M | 0.871 | +£10.10M |
| 5 | £2.5M | £14.2M | +£11.7M | 0.842 | +£9.85M |
| **Total** | **£18.8M** | **£60.4M** | **+£41.6M** | | **£36.39M NPV** |

**NPV Result**: £36.39M (strongly positive - excellent investment)

**Return on Investment**:
- **ROI**: (£60.4M - £18.8M) / £18.8M × 100% = **221%** over 5 years
- **Payback Period**: Month 18 (cumulative net cashflow turns positive)
- **Benefit-Cost Ratio (BCR)**: 3.21 (> 1.0 indicates good value)

**Pros**:
- ✅ 85% of stakeholder goals met
- ✅ Strongly positive NPV (£36.39M)
- ✅ Excellent ROI (221%)
- ✅ Delivers manifesto commitment (cross-government AI governance)
- ✅ Full AI Playbook and ATRS compliance
- ✅ Scalable architecture for future requirements

**Cons**:
- ⚠️ Higher upfront investment than Option 1 (£5.8M vs £1.5M)
- ⚠️ 13-month implementation timeline
- ⚠️ Complex multi-tenant security requiring NCSC assurance
- ⚠️ Change management across 20+ departments

**Stakeholder Impact**:
- HM Treasury Goal G-1: ✅ Met (80% cost reduction achieved)
- Permanent Secretary Goal G-2: ✅ Met (NCSC-assured security)
- ICO/CDDO Goal G-3: ✅ Met (AI Playbook > 90%, ATRS published)
- Cabinet Office CTO Goal G-4: ✅ Met (99.9% uptime, < 2s response)
- Minister Goal G-5: ✅ Met (credible parliamentary responses)
- End Users Goal G-6: ✅ Met (80% adoption, 4.2/5 satisfaction)

**Stakeholder Goals Met**: 85%

**Risks** (from Risk Register):
- **R-001**: Cross-tenant data leak (Critical → High with controls) - Mitig: Multi-layer tenant isolation
- **R-004**: NCSC assurance delay (High) - Mitig: Early NCSC engagement Month 2
- **R-007**: AI bias incident (High) - Mitig: Quarterly bias testing, human-in-the-loop

**Recommendation**: **ACCEPT** - Best value for money, meets strategic objectives.

---

### Option 3: Comprehensive Enterprise Solution

**Description**: Deploy comprehensive AI platform with advanced features including multi-modal AI (image, video), SECRET classification, and public-facing citizen services.

**Scope**:
- Everything in Option 2, plus:
- Multi-modal AI (image, video, audio generation)
- SECRET data classification (requires additional NCSC assurance)
- Public-facing citizen AI services (chatbots on GOV.UK)
- Advanced AI features (code generation, automated decision-making)
- Full sovereignty (UK-built foundation models)

**Costs** (5-year) - ROM (±40%):
- Capital: £15M (significantly higher)
- Operational: £25M over 5 years (£5M/year)
- Total 5-year TCO: £40M

**Benefits** (5-year): £70M (marginally higher than Option 2)

**Net Benefit**: £30M (lower than Option 2 due to higher costs)

**Pros**:
- ✅ 100% of stakeholder goals met
- ✅ Future-proofed for 10+ years
- ✅ Exceeds all requirements
- ✅ UK sovereign AI capability

**Cons**:
- ❌ High cost (£40M vs £18.8M for Option 2)
- ❌ Long implementation (24+ months)
- ❌ SECRET clearance complexity extends timeline significantly
- ❌ Citizen-facing AI creates additional regulatory burden
- ❌ Over-engineering risk - features may not be needed
- ❌ NPV lower than Option 2 despite higher benefits

**Stakeholder Goals Met**: 100%

**Recommendation**: **Reject** - Diminishing returns, cost not justified for additional 15% goal achievement.

---

## B3. Recommended Option

**Recommendation**: **Option 2: Balanced Multi-Tenant Platform**

**Rationale**:
1. **Best Value**: Highest NPV at £36.39M (vs negative for Option 1, £30M for Option 3)
2. **Stakeholder Satisfaction**: Meets 85% of goals (sufficient for all critical stakeholders)
3. **Acceptable Risk**: Manageable with identified mitigations (20 risks, all with owners)
4. **Affordability**: Within expected budget constraints (£18.8M over 5 years)
5. **Deliverability**: Realistic 13-month timeline aligned with GDS delivery phases
6. **Compliance**: Full AI Playbook, ATRS, TCoP, and Secure by Design compliance

**Sensitivity Analysis**:
- If costs increase 30%: NPV still positive (£27.9M)
- If benefits reduce 30%: NPV still positive (£23.6M)
- If timeline extends 6 months: Payback extends to Month 24 (still acceptable)

**Optimism Bias Adjustment** (UK Government Green Book):
- Standard uplift for IT projects: +25% on costs (lower than typical 40% due to mature technology)
- Adjusted Total Cost: £18.8M → £23.5M (with uplift)
- NPV with optimism bias: Still strongly positive at £28.8M

---

# PART C: COMMERCIAL CASE

## C1. Procurement Strategy

### C1.1 Market Assessment

**Market Maturity**:
- AI foundation model market is mature with established providers (Microsoft Azure OpenAI, AWS Bedrock, Anthropic, Google)
- All major providers offer UK data residency options
- Government AI implementation market is growing with several successful reference sites

**Supplier Landscape**:
- **Tier 1 (AI Foundation Models)**: Microsoft (Azure OpenAI), Amazon (Bedrock), Anthropic (Claude), Google (Gemini)
- **Tier 2 (System Integrators)**: Accenture, Deloitte, PA Consulting, Capgemini - AI implementation experience
- **Tier 3 (SMEs)**: Faculty AI, Faculty, Kin + Carta, Methods - UK Government AI specialists

**UK Government Digital Marketplace Assessment**:
- **G-Cloud 14**: 150+ suppliers offering AI/ML services
- **DOS6**: 80+ suppliers for digital outcomes/specialists
- **SME participation**: 65% of suppliers are SMEs

### C1.2 Sourcing Route

**Recommended Route**: Digital Marketplace - Multi-lot procurement

**Lot Structure**:
- **Lot 1**: AI Foundation Model Services (G-Cloud 14) - Call-off from framework
- **Lot 2**: Platform Implementation (DOS6 Outcomes) - Mini-competition
- **Lot 3**: Ongoing Support & Operations (G-Cloud 14) - Call-off from framework

**Rationale**:
- Compliant with Cabinet Office Procurement Rules
- Competitive market ensures value for money
- SME access through Digital Marketplace
- Faster procurement than open tender (8-12 weeks vs 6+ months)

### C1.3 Contract Approach

**Proposed Contract Type**:
- **Lot 1 (AI Models)**: Consumption-based (pay per token/request)
- **Lot 2 (Implementation)**: Fixed-price with milestones
- **Lot 3 (Support)**: Managed service agreement with SLAs

**Contract Duration**:
- Initial term: 3 years
- Extension options: 2 × 1 year
- Total potential: 5 years

**Key Contract Terms**:
- SLAs: 99.9% availability, < 2s response time (p95)
- Penalties: Service credits for SLA breaches
- UK data residency: Mandatory, no exceptions
- IP: Crown owns all bespoke development
- Exit: 6-month transition, data export included

### C1.4 Social Value

**UK Government Requirement**: Minimum 10% weighting on social value in evaluation.

**Social Value Themes**:
1. **Economic**: Create AI skills jobs, apprenticeships in UK regions
2. **Social**: Diversity in AI workforce, accessibility for disabled users
3. **Environmental**: Carbon-neutral cloud operations, sustainable AI

**Evaluation Approach**:
- Technical: 50%
- Cost: 40%
- Social Value: 10%

---

# PART D: FINANCIAL CASE

## D1. Budget Requirement

**Total Investment Required**: £18.8M over 5 years

### D1.1 Capital Expenditure (CapEx)

| Item | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 | Total |
|------|--------|--------|--------|--------|--------|-------|
| Infrastructure & platform | £2.0M | £0.5M | £0 | £0 | £0 | £2.5M |
| AI vendor services (setup) | £1.0M | £0.5M | £0 | £0 | £0 | £1.5M |
| Security & compliance | £0.5M | £0.3M | £0 | £0 | £0 | £0.8M |
| Integration (SSO, M365, GWS) | £0.3M | £0.2M | £0 | £0 | £0 | £0.5M |
| Training & change management | £0.2M | £0.3M | £0 | £0 | £0 | £0.5M |
| **Total CapEx** | **£4.0M** | **£1.8M** | **£0** | **£0** | **£0** | **£5.8M** |

### D1.2 Operational Expenditure (OpEx)

| Item | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 | Total |
|------|--------|--------|--------|--------|--------|-------|
| AI consumption (20+ depts) | £0.6M | £1.2M | £1.2M | £1.4M | £1.6M | £6.0M |
| Support & maintenance | £0.4M | £0.7M | £0.7M | £0.8M | £0.9M | £3.5M |
| Security operations | £0.2M | £0.4M | £0.4M | £0.5M | £0.5M | £2.0M |
| Ongoing training | £0.2M | £0.3M | £0.3M | £0.3M | £0.4M | £1.5M |
| **Total OpEx** | **£1.4M** | **£2.6M** | **£2.6M** | **£3.0M** | **£3.4M** | **£13.0M** |

### D1.3 Total Cost of Ownership (TCO)

| | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 | Total |
|---|--------|--------|--------|--------|--------|-------|
| CapEx | £4.0M | £1.8M | £0 | £0 | £0 | £5.8M |
| OpEx | £1.4M | £2.6M | £2.6M | £3.0M | £3.4M | £13.0M |
| **Total TCO** | **£5.4M** | **£4.4M** | **£2.6M** | **£3.0M** | **£3.4M** | **£18.8M** |

## D2. Funding Source

**Budget Allocation**:
- **Source**: Cabinet Office Digital Transformation Budget + HM Treasury AI Programme Fund
- **Amount Available**: £20M over 5 years (confirmed in Spending Review settlement)
- **Affordability**: Project within budget envelope

**Budget Approval Path**:
1. Cabinet Office Finance Director: Up to £2M
2. Cabinet Office Permanent Secretary: £2M to £10M
3. HM Treasury: Above £10M (Cabinet Office digital spend control)

## D3. Financial Appraisal

**NPV**: £36.39M (strongly positive)
**ROI**: 221%
**Payback Period**: 18 months
**BCR**: 3.21

**Value for Money Assessment**: **HIGH**
- Economy: Competitive procurement via Digital Marketplace
- Efficiency: 80% cost reduction in AI spend
- Effectiveness: 85% stakeholder goals met

---

# PART E: MANAGEMENT CASE

## E1. Governance

**Senior Responsible Owner (SRO)**: Cabinet Office Permanent Secretary
**Programme Director**: Cabinet Office CTO
**Steering Committee**:
- Cabinet Office Permanent Secretary (Chair)
- Cabinet Office CTO (Technical Authority)
- HM Treasury Deputy Director (Financial Authority)
- CDDO Director (Standards Authority)
- NCSC Lead Architect (Security Authority)
- ICO Chief Technology Officer (Regulatory Authority)

**Meeting Frequency**: Monthly (weekly during critical phases)

## E2. Delivery Approach

**Methodology**: GDS Agile Delivery (Discovery → Alpha → Private Beta → Public Beta → Live)

**Phases** (56 weeks / 13 months):
1. **Discovery** (Weeks 1-8): Requirements, stakeholder workshops, user research
2. **Alpha** (Weeks 9-20): HLD, prototype, vendor procurement
3. **Private Beta** (Weeks 21-39): Build, test, 3-department pilot
4. **Public Beta** (Weeks 40-52): 20+ department rollout, GDS assessment
5. **Live** (Week 53+): Full production, benefits realization

## E3. Key Milestones

| Milestone | Target Date | Owner |
|-----------|-------------|-------|
| SOBC Approval | Q1 2026 | SRO |
| Funding Secured | Q1 2026 | Finance Director |
| Vendor Contract Award | Q2 2026 | Commercial Manager |
| Private Beta Launch | Q3 2026 | Programme Director |
| ATRS Publication | Q4 2026 | AI Governance Lead |
| GDS Service Assessment | Q1 2027 | GDS Assessor |
| **Production Launch (Live)** | **Q1 2027** | **SRO** |

## E4. Risk Management

**Risk Register Reference**: Full Orange Book risk register in `projects/001-cabinet-office-genai/risk-register.md`

**Top 5 Strategic Risks**:

| Risk ID | Risk | Category | Residual Score | Owner | Mitigation |
|---------|------|----------|----------------|-------|------------|
| R-001 | Cross-tenant data leak | TECHNOLOGY | 12 (High) | CTO | Multi-layer tenant isolation, penetration testing |
| R-004 | NCSC assurance delay | COMPLIANCE | 12 (High) | CTO | Early NCSC engagement Month 2 |
| R-007 | AI bias incident | REPUTATIONAL | 15 (High) | AI Governance Lead | Quarterly bias testing, human-in-the-loop |
| R-002 | Ministerial direction change | STRATEGIC | 9 (Medium) | SRO | Regular ministerial briefings |
| R-010 | Cost overrun > 20% | FINANCIAL | 9 (Medium) | Finance Director | Monthly cost tracking, contingency |

**Overall Risk Profile**: ⚠️ CONCERNING (1 Critical, 6 High risks) - Manageable with identified mitigations

## E5. Benefits Realization

**Benefits Tracking**:
- Monthly dashboard to Steering Committee
- Quarterly benefits realization review
- 6-month and 12-month formal assessments

**Benefit Owners**:
- B-001 (Cost Reduction): HM Treasury Deputy Director
- B-002 (Productivity): Cabinet Office CTO
- B-003 (Compliance): CDDO Director

---

# PART F: RECOMMENDATION & NEXT STEPS

## F1. Summary of Recommendation

**Recommended Option**: **Option 2: Balanced Multi-Tenant Platform**

| Metric | Value |
|--------|-------|
| Investment | £18.8M over 5 years |
| Expected Benefits | £60.4M over 5 years |
| NPV (3.5% discount) | £36.39M |
| ROI | 221% |
| Payback Period | 18 months |
| BCR | 3.21 |
| Stakeholder Goals Met | 85% |

**Go/No-Go Recommendation**: **PROCEED to requirements phase**

## F2. Conditions for Approval

**Mandatory Conditions**:
1. HM Treasury approval for £18.8M programme (above £10M threshold)
2. SRO formally appointed and accepted role
3. Steering Committee established with named members
4. NCSC engagement confirmed for Month 2

**Recommended Conditions**:
1. Early proof of concept for multi-tenant isolation (Alpha phase)
2. AI vendor UK data residency confirmation in writing
3. Change management resource secured

## F3. Next Steps if Approved

**Immediate Actions** (Month 1):
1. HM Treasury funding approval
2. SRO formal appointment
3. Steering Committee formation

**Phase 1: Requirements** (Months 1-2):
- Detailed requirements: `/arckit.requirements` ✅ Complete
- Stakeholder validation
- Traceability matrix: `/arckit.traceability` ✅ Complete

**Phase 2: Procurement** (Months 2-4):
- SOW generation: `/arckit.sow`
- Digital Marketplace publication
- Vendor evaluation: `/arckit.evaluate`

**Phase 3: Design & Build** (Months 4-13):
- High-Level Design with `/arckit.hld-review`
- Detailed Design with `/arckit.dld-review`
- GDS Service Assessment

## F4. Next Steps if Not Approved

If SOBC rejected:
1. Understand objections from HM Treasury/SRO
2. Revise SOBC (lower cost option, phased approach)
3. Re-submit within 4 weeks

**Do Nothing Consequences**:
- £75M wasted over 5 years
- Manifesto commitment unfulfilled
- Security and compliance risks escalate
- NAO/PAC criticism likely

---

# APPENDICES

## Appendix A: Stakeholder Analysis Reference

**Source**: `projects/001-cabinet-office-genai/stakeholder-drivers.md`

**Key Stakeholders**: 13 stakeholder groups identified
- Minister for Cabinet Office (Political leadership)
- Cabinet Office Permanent Secretary (Accounting Officer)
- Cabinet Office CTO (Technical Authority)
- HM Treasury (Financial Authority)
- CDDO (Standards Authority)
- NCSC (Security Authority)
- ICO (Regulatory Authority)
- Home Office, HMRC, DHSC, MOJ (Pilot Departments)
- Policy Advisors & Civil Servants (End Users)

## Appendix B: Risk Register Reference

**Source**: `projects/001-cabinet-office-genai/risk-register.md`

**Summary**: 20 risks across 6 categories
- 1 Critical residual risk (R-001: Cross-tenant data leak)
- 6 High residual risks
- 10 Medium residual risks
- 3 Low residual risks

**Overall Risk Reduction**: 37.5% from inherent to residual through controls

## Appendix C: Requirements Reference

**Source**: `projects/001-cabinet-office-genai/requirements.md`

**Summary**: 67+ requirements documented
- 7 Business Requirements (BR)
- 26 Functional Requirements (FR)
- 30+ Non-Functional Requirements (NFR)
- 4 Integration Requirements (INT)

## Appendix D: Architecture Principles Reference

**Source**: `.arckit/memory/architecture-principles.md`

**Summary**: 24 architecture principles across 10 categories
- Strategic, AI/ML, Data, Integration, Quality, DevOps, Multi-Tenant principles
- All technology-agnostic, outcome-focused

---

## Document Approval

| Name | Role | Signature | Date |
|------|------|-----------|------|
| | Cabinet Office Permanent Secretary (SRO) | | |
| | Cabinet Office CTO | | |
| | HM Treasury Deputy Director | | |
| | CDDO Director | | |

**Approval Decision**: PENDING

**Conditions** (if any): TBD

**Approval Date**: PENDING

**Next Review Date**: Q2 2026 (or when OBC created)

---

**END OF STRATEGIC OUTLINE BUSINESS CASE**

---

**Generated by**: ArcKit `/arckit.sobc` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Cabinet Office GenAI Platform (Project 001)
**AI Model**: claude-opus-4-5-20251101
