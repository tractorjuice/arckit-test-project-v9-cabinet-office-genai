# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an **ArcKit project repository** for the Cabinet Office GenAI Platform - a cross-government generative AI service for UK Government departments. It uses the ArcKit toolkit to generate architecture governance artifacts through AI-assisted slash commands.

**Project**: Centralized, secure GenAI platform providing document summarization, drafting, analysis, and knowledge management across UK Government with multi-tenant architecture, OFFICIAL to OFFICIAL-SENSITIVE data classification, and responsible AI governance.

## Using ArcKit Commands

Run slash commands to generate architecture artifacts:

```bash
# Foundation
/arckit.principles         # Create/update enterprise architecture principles
/arckit.plan               # Generate project plan with timeline, phases, gates

# Strategic Context
/arckit.stakeholders       # Analyze stakeholder drivers, goals, outcomes
/arckit.risk               # Create risk register (HM Treasury Orange Book)
/arckit.sobc               # Create Strategic Outline Business Case (Green Book 5-case model)

# Requirements & Data
/arckit.requirements       # Document comprehensive requirements (BR/FR/NFR/INT/DR)
/arckit.data-model         # Create data model with ERD, GDPR compliance
/arckit.dpia               # Generate Data Protection Impact Assessment (UK GDPR Article 35)

# Research & Strategy
/arckit.research           # Technology research with build vs buy analysis
/arckit.wardley            # Create Wardley Maps for strategic positioning
/arckit.adr                # Document Architecture Decision Records

# Procurement
/arckit.sow                # Generate Statement of Work / RFP
/arckit.gcloud-search      # Search G-Cloud services on Digital Marketplace
/arckit.evaluate           # Create vendor evaluation framework

# Design & Review
/arckit.diagram            # Generate Mermaid architecture diagrams (C4, deployment, sequence)
/arckit.hld-review         # Review High-Level Design
/arckit.dld-review         # Review Detailed Design

# Operations
/arckit.backlog            # Convert requirements to user stories and sprints
/arckit.servicenow         # Generate ServiceNow service design (CMDB, SLAs)
/arckit.traceability       # Generate requirements traceability matrix

# UK Government Compliance
/arckit.tcop               # Technology Code of Practice assessment (13 points)
/arckit.secure             # Secure by Design assessment (NCSC CAF, Cyber Essentials)
/arckit.ai-playbook        # AI Playbook compliance for responsible AI
/arckit.atrs               # Algorithmic Transparency Recording Standard
/arckit.service-assessment # GDS Service Standard assessment (14 points)

# Quality & Reporting
/arckit.analyze            # Comprehensive governance quality analysis
/arckit.story              # Generate project story with timeline and achievements
/arckit.pages              # Generate GitHub Pages documentation site
```

## Repository Structure

```
.arckit/
├── memory/architecture-principles.md    # Global architecture principles
├── templates/                           # Document templates (40+ templates)
└── scripts/bash/                        # Helper scripts (create-project.sh, etc.)

.claude/commands/                        # Slash commands (arckit.*.md)

projects/
└── 001-cabinet-office-genai/            # Project artifacts
    ├── requirements.md                  # BR/FR/NFR/INT/DR requirements
    ├── stakeholder-drivers.md           # Stakeholder analysis
    ├── risk-register.md                 # Orange Book risk register
    ├── data-model.md                    # ERD, GDPR compliance
    ├── tcop-review.md                   # Technology Code of Practice
    ├── ai-playbook-assessment.md        # Responsible AI assessment
    ├── atrs-record.md                   # Algorithmic transparency
    ├── ukgov-secure-by-design.md        # Security assessment
    ├── backlog.md                       # User stories and sprints
    └── traceability-matrix.md           # Requirements traceability
```

## Key Patterns

**Traceability Chain**: Stakeholders → Goals → Requirements (BR/FR/NFR/INT/DR) → Data Model → Components → User Stories

**Requirement ID Prefixes**:
- BR-xxx: Business Requirements
- FR-xxx: Functional Requirements
- NFR-xxx: Non-Functional (NFR-P-xxx Performance, NFR-SEC-xxx Security, NFR-A-xxx Availability)
- INT-xxx: Integration Requirements
- DR-xxx: Data Requirements

**Workflow Order**: principles → stakeholders → risk → sobc → requirements → data-model → research → wardley → diagram → sow → evaluate → hld-review → backlog → servicenow → traceability → analyze

**Token Limit Handling**: Commands use Write tool for large documents to avoid 32K output token limit. Only summaries are shown to user.

**Template-Driven**: All artifacts use templates from `.arckit/templates/`. Never generate freeform documents.

## UK Government Context

This project targets UK public sector with specific compliance requirements:

- **GDS Service Standard** (14 points): Mandatory for digital services
- **Technology Code of Practice** (13 points): Cloud First, open standards, responsible AI
- **HM Treasury Green Book**: Strategic Outline Business Case (5-case model)
- **HM Treasury Orange Book**: Risk management framework
- **NCSC CAF**: Cyber Assessment Framework
- **UK GDPR / DPA 2018**: Data protection, DPIA for high-risk processing
- **AI Playbook**: Responsible AI principles for government
- **ATRS**: Algorithmic Transparency Recording Standard (Tier 1 + Tier 2)

## Helper Scripts

```bash
# Create new numbered project directory
.arckit/scripts/bash/create-project.sh --name "project-name" --json

# Generate document ID (e.g., ARC-001-REQ-v1.0)
.arckit/scripts/bash/generate-document-id.sh PROJECT_ID DOC_TYPE VERSION

# List all projects
.arckit/scripts/bash/list-projects.sh
```
