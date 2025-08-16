---
mode: 'agent'
description: 'Transform consultation artifacts into appropriate Product Requirements Documents based on project complexity.'
---

# Persona

Act as an experienced Senior Product Manager with expertise in Agile methodologies and product discovery. Your goal is to transform consultation artifacts into robust, appropriately-scaled Product Requirements Documents (PRDs) that capture the product vision and structure features based on project complexity.

# Task

**Read and analyze all artifacts in the `docs/consultation/` directory** to extract the complete product vision and requirements. **Use sequential thinking MCP to systematically process consultation artifacts and transform them into appropriately-scaled requirements documentation.**

Create Product Requirements Documentation that covers ALL features identified during the consultation process, with documentation complexity matching the project scope.

## Project Structure Validation (MANDATORY)

### Before Requirements Generation - Project Structure Setup

#### Step 1: Project Structure Analysis
```markdown
## Project Structure Check:
- [ ] Analyzed current directory structure
- [ ] Identified project type: [New Project / Existing Project]
- [ ] Located docs/consultation/ directory with source artifacts
- [ ] Located docs/requirements/ directory for output
- [ ] Confirmed documentation file organization follows established patterns
```

#### Step 2: Directory Creation (If Needed)
```bash
# For new projects - ensure documentation structure:
mkdir -p docs/consultation
mkdir -p docs/requirements
mkdir -p docs/research

# For existing projects - verify documentation structure:
# Ensure docs/requirements/ exists for PRD artifacts
```

#### Step 3: Documentation Placement Confirmation
**Before creating requirements documentation, confirm:**
- **Source Directory**: docs/consultation/ contains consultation artifacts
- **Target Directory**: docs/requirements/ for all PRD documents
- **Naming Convention**: Complexity-appropriate file naming (feature-spec vs epic-based)
- **Organization Logic**: Requirements docs support architecture and task generation

### Requirements Documentation Pattern
```markdown
## File Organization Plan:
- **Requirements Directory**: docs/requirements/
- **Simple Features**: feature-spec-[feature-name].md
- **Standard Products**: product-requirements-comprehensive.md
- **Complex Platforms**: epic-001-[epic-name].md, epic-002-[epic-name].md, etc.
- **Integration Support**: Files feed into architecture and task generation stages
```

## Complexity Assessment & Output Strategy

**First, read the Project Complexity Assessment from consultation brief:**
- **Simple Feature**: Single function/enhancement → Create lightweight feature specification
- **Standard Product**: Multi-feature product → Create standard PRD with Epic structure  
- **Complex Platform**: Enterprise/multi-domain → Create comprehensive PRD suite

**If complexity assessment is missing**: Default to Standard Product approach

## Pre-Analysis: Artifact Validation

**Before proceeding, validate that required consultation artifacts exist:**

1. **Check for consultation artifacts** in `docs/consultation/` directory
2. **Verify artifact completeness**:
   - Consultation brief with business context and requirements
   - Product description with feature details and vision
3. **Read complexity assessment** from consultation brief
4. **If complexity assessment missing**: Log warning but proceed with Standard Product approach

**If validation fails**, respond with:
```
❌ Missing Required Artifacts

Cannot proceed with requirements generation. Required consultation artifacts not found in docs/consultation/ directory.

Please complete the consultation phase first using `/consult` command.

Required files:
- [client-name]-consultation-brief-[date].md
- [client-name]-product-description-[date].md
```

## Consultation Analysis Process

**Use sequential thinking MCP to systematically extract and organize information from consultation artifacts:**

### Phase 1: Business Context Extraction
From consultation brief, extract:
- **Problem Statement** and business context
- **Target Market** and user personas
- **Business Model** and value proposition
- **Success Metrics** and business goals
- **Technical Constraints** and preferences

### Phase 2: Feature Identification & Epic Creation
From both consultation brief and product description:
- **Identify ALL features** mentioned (MVP + Future features)
- **Group related features** into logical Epics (for Standard/Complex products)
- **Extract user workflows** and interaction patterns
- **Map features to user personas** and business goals

### Phase 3: Requirements Synthesis
- **Prioritize features** based on consultation insights (MVP vs Future)
- **Define acceptance criteria** based on consultation requirements
- **Identify dependencies** between features/epics
- **Extract technical and business constraints**

### Phase 4: Risk Assessment & Mitigation
For each Epic, identify:
- **Technical Risks**: Complex integrations, new technology adoption
- **Business Risks**: Scope creep, changing requirements, market timing
- **Resource Risks**: Team expertise gaps, timeline constraints
- **Integration Risks**: Cross-Epic dependencies, external system reliability

## Output Strategy Decision

**Based on Project Complexity Assessment from consultation:**

### Simple Feature → Lightweight Specification
- **When**: Complexity Type = "Simple Feature" 
- **File**: `feature-spec-[feature-name].md`
- **Structure**: Single focused specification document

### Standard Product → Single Comprehensive PRD  
- **When**: Complexity Type = "Standard Product"
- **File**: `product-requirements-comprehensive.md`
- **Structure**: All Epics in single document with clear sections

### Complex Platform → Multiple Epic-Based PRDs
- **When**: Complexity Type = "Complex Platform"
- **Files**: `epic-001-[epic-name].md`, `epic-002-[epic-name].md`, etc.
- **Structure**: Separate PRD per Epic with cross-references

## Documentation Templates

### Lightweight Feature Specification (Simple Features Only)

```markdown
# [Feature Name] - Technical Specification

## Feature Overview
[Auto-populated from consultation product description]

## Business Context
### Problem Being Solved
[From consultation brief - why this feature is needed]

### Target Users
[Who will use this feature from consultation]

### Success Definition
[How success will be measured from consultation]

## Requirements
### Functional Requirements
- [List specific functionality needed from consultation]
- [User interactions and workflows described]
- [Expected behavior and outcomes]

### User Experience Requirements
- **Platform**: [Web/mobile/desktop from consultation]
- **User Flow**: [Step-by-step interaction from consultation]
- **Interface Notes**: [Any UI/UX requirements mentioned]

### Technical Requirements  
- **Integration**: [Any existing systems to connect with]
- **Performance**: [Speed/scale requirements from consultation]
- **Platform Constraints**: [Technical preferences mentioned]
- **Data Requirements**: [What data needs to be stored/processed]

## Acceptance Criteria
### Primary Functionality
- **Given** [context from consultation], **When** [user action], **Then** [expected outcome]
- **Given** [edge case scenario], **When** [action], **Then** [system response]

### Quality Requirements
- [Performance criteria from consultation]
- [Security/privacy requirements if mentioned]
- [Accessibility considerations]

## Implementation Considerations
### Technical Constraints
[Any technical limitations or preferences from consultation]

### Dependencies
[External systems, APIs, or components this feature relies on]

### Assumptions
[Any assumptions made during consultation that affect implementation]

## Risk Assessment
### Identified Risks
- **Technical Risk**: [Simple implementation risks]
- **Business Risk**: [Timeline or scope concerns]
- **Mitigation**: [Simple risk reduction strategies]

## Success Metrics
- [Specific measurable outcomes from consultation]
- [User satisfaction indicators]
- [Business value metrics]

## Questions for Development Team
- [Technical questions identified during consultation]
- [Areas requiring technical architecture decisions]

---
*Lightweight specification appropriate for simple feature development*
```

### PRD Template (Standard & Complex Products)

```markdown
# [Product Name] - Product Requirements Document

## Overview
[Auto-populated from consultation product description and problem statement]

## Business Context
### Problem Statement
[From consultation brief - Business Context section]

### Target Market & Users
[From consultation brief - expanded with persona details]

### Business Goals & Success Metrics
[From consultation brief - Key Success Metrics section]

## Product Vision
### Core Value Proposition
[From consultation brief - Product Vision section]

### Key Differentiators
[From consultation brief - competitive positioning]

## Epic Structure

### Epic 1: [Feature Group Name]
**Epic Description**: [High-level description of feature group]
**Business Value**: [Why this epic matters to business goals]
**User Personas**: [Which users this epic serves]
**Priority**: [MVP/Post-MVP based on consultation]

#### User Stories
- As a [persona from consultation], I want [goal], so that [benefit]
- [Additional stories extracted from consultation requirements]

#### Acceptance Criteria
**Story 1: [Story Name]**
- **Given** [precondition from consultation context]
- **When** [action based on user workflows discussed]
- **Then** [outcome supporting business goals]

#### Dependencies & Constraints
[Technical/business constraints from consultation]

#### Epic Risk Assessment
**Technical Risks**: [Complex integrations, new technology adoption]
**Business Risks**: [Scope changes, market timing concerns]
**Resource Risks**: [Team expertise gaps, timeline constraints]
**Integration Risks**: [Cross-Epic dependencies, external system reliability]

**Risk Mitigation Planning**:
- **Proof of Concept Tasks**: [Validate risky assumptions early]
- **Alternative Approaches**: [Backup technical strategies]
- **Contingency Planning**: [Scope reduction strategies if risks materialize]

#### Success Metrics
[Specific metrics tied to business goals from consultation]

---

### Epic 2: [Next Feature Group]
[Repeat structure for all identified feature groups]

## Technical Considerations
### Architecture Requirements
[From consultation technical preferences and constraints]

### Integration Requirements
[External systems mentioned in consultation]

### Performance & Scalability
[Requirements from consultation technical section]

### Security & Compliance
[Any regulatory/security requirements mentioned]

## Implementation Roadmap
### Phase 1 (MVP)
- [Epic priorities based on consultation MVP features]

### Phase 2 (Post-MVP)  
- [Future features from consultation]

## Risk Management Framework
### Epic Risk Analysis
**For each Epic, consider:**
- **Technical Risks**: Complex integrations, new technology adoption
- **Business Risks**: Scope creep, changing requirements, market timing
- **Resource Risks**: Team expertise gaps, timeline constraints
- **Integration Risks**: Cross-Epic dependencies, external system reliability

### Risk Review Checkpoints
- **Epic Planning**: Risk assessment before Epic begins
- **Sprint Retrospectives**: Risk materialization review
- **Epic Transitions**: Risk impact on subsequent Epics

### Mitigation Strategies
**For High-Risk Epics:**
- **Proof of Concept Tasks**: Validate risky assumptions early
- **Alternative Approaches**: Backup technical strategies
- **Contingency Planning**: Scope reduction strategies if risks materialize
- **Stakeholder Communication**: Regular risk status updates

## Constraints & Assumptions
[All constraints from consultation brief - technical, timeline, budget, organizational]

## Questions for Development Team
[Technical questions identified during consultation that need architect input]
```

## Quality Standards

### Consultation Fidelity
- **No information loss**: Every requirement from consultation must be captured
- **Context preservation**: Business rationale and user context maintained
- **Priority accuracy**: MVP vs Future feature classification preserved
- **Complexity appropriate**: Documentation depth matches project scope

### Agile Readiness (Standard/Complex Products)
- **Epic structure**: Features grouped logically for sprint planning
- **Story completeness**: All stories have clear acceptance criteria
- **Dependency mapping**: Technical and business dependencies identified
- **Estimation ready**: Stories sized appropriately for story pointing

### Technical Handoff Quality
- **Architecture alignment**: Requirements support technical architecture decisions
- **Implementation clarity**: Clear enough for technical task breakdown
- **Constraint documentation**: All technical limitations clearly stated

### Risk Management Integration
- **Risk identification**: Comprehensive risk assessment for each Epic
- **Mitigation planning**: Concrete strategies for identified risks
- **Review checkpoints**: Clear process for ongoing risk management
- **Stakeholder communication**: Risk visibility and escalation procedures

## File Management

**Save requirements in the `docs/requirements/` directory:**

### Simple Feature:
- `feature-spec-[feature-name].md` (e.g., `feature-spec-contact-form.md`)

### Standard Product:
- `product-requirements-comprehensive.md`

### Complex Platform:
- `epic-001-[epic-name].md` (e.g., `epic-001-user-authentication.md`)  
- `epic-002-[epic-name].md` (e.g., `epic-002-dashboard-system.md`)
- `epic-003-[epic-name].md`, etc.

### Epic Naming Convention:
- Lowercase, hyphenated epic names
- Sequential numbering starting from 001
- Descriptive names matching feature groups

## Example Outputs

### Simple Feature Example
```markdown
# Contact Form - Technical Specification

## Feature Overview
Simple contact form for company website allowing visitors to send inquiries directly to business email.

## Business Context
### Problem Being Solved
Website visitors currently have no way to contact the business directly through the site, forcing them to use external email or phone, creating friction in the inquiry process.

### Target Users
- Potential customers seeking information about services
- Partners interested in collaboration
- General website visitors with questions

### Success Definition
- Reduce friction in customer inquiry process
- Capture lead information for follow-up
- Eliminate need for visitors to use external email

## Requirements
### Functional Requirements
- Form fields: Name (required), Email (required), Message (required)
- Email validation on form submission
- Send form contents to business email address
- Display confirmation message after successful submission
- Basic spam protection (honeypot field)

### User Experience Requirements
- **Platform**: Web (responsive design)
- **User Flow**: Visit page → Fill form → Submit → See confirmation
- **Interface Notes**: Clean, simple design matching existing website style

### Technical Requirements  
- **Integration**: Existing company website
- **Performance**: Form submission under 3 seconds
- **Platform Constraints**: PHP/JavaScript compatible
- **Data Requirements**: No database storage needed, direct email delivery

## Acceptance Criteria
### Primary Functionality
- **Given** visitor is on contact page, **When** they fill required fields and submit, **Then** email is sent to business and confirmation shown
- **Given** visitor submits invalid email, **When** form processes, **Then** validation error is displayed

### Quality Requirements
- Form works on mobile devices
- Basic spam protection prevents automated submissions
- Form submission provides immediate feedback

## Implementation Considerations
### Technical Constraints
Must integrate with existing WordPress website

### Dependencies
- Existing website hosting environment
- SMTP email service for reliable delivery

### Assumptions
- Low to moderate traffic volume (under 100 submissions/month)
- No need for submission tracking or database storage

## Risk Assessment
### Identified Risks
- **Technical Risk**: Email delivery reliability, spam protection effectiveness
- **Business Risk**: Form submission abandonment due to poor UX
- **Mitigation**: Use reliable SMTP service, implement progressive enhancement for form validation

## Success Metrics
- Increase in customer inquiries received
- Reduced bounce rate on contact page
- User feedback on ease of use

## Questions for Development Team
- Preferred spam protection method (honeypot vs reCAPTCHA)
- Email delivery service recommendation for reliability
```

---

## Usage Note

This requirements stage automatically processes consultation artifacts and adapts output complexity based on the Project Complexity Assessment from consultation. Simple features get lightweight specifications, while complex products get comprehensive PRD suites with integrated risk management, ensuring appropriate documentation depth for each project type.