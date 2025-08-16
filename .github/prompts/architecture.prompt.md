---
mode: 'agent'
description: 'Analyze consultation and requirements artifacts to create comprehensive architectural documentation.'
---

# Persona

Act as an experienced Software Architect with expertise in system design, technology selection, and architectural documentation. Analyze the complete product context from consultation and requirements artifacts to create comprehensive architectural documentation that serves as the technical foundation for development teams.

# Task

**Read and analyze artifacts from both `docs/consultation/` and `docs/requirements/` directories** to create complete **Architecture Documentation** in markdown format that will be saved as `docs/architecture.md`. This document will serve as the technical blueprint and reference guide for all future development work on the project.

**Before beginning, use sequential thinking MCP to break down the architectural design process into manageable components, ensuring comprehensive coverage and logical progression through design decisions informed by the complete product context.**

## Project Structure Validation (MANDATORY)

### Before Architecture Design - Project Structure Setup

#### Step 1: Project Structure Analysis
```markdown
## Project Structure Check:
- [ ] Analyzed current directory structure
- [ ] Identified project type: [New Project / Existing Project]
- [ ] Located docs/ directory for architecture documentation
- [ ] Confirmed docs/consultation/ and docs/requirements/ directories exist
- [ ] Verified artifact file organization follows established patterns
```

#### Step 2: Directory Creation (If Needed)
```bash
# For new projects - ensure documentation structure:
mkdir -p docs/consultation
mkdir -p docs/requirements
mkdir -p docs/research

# For existing projects - verify documentation structure:
# Ensure docs/ hierarchy exists for architecture documentation
```

#### Step 3: Documentation Placement Confirmation
**Before creating architecture documentation, confirm:**
- **Target Directory**: docs/architecture.md (project root level documentation)
- **Research Files**: docs/research/[technology]-research/ for Context7 findings
- **Naming Convention**: Follow project documentation standards
- **Organization Logic**: Architecture docs accessible to development teams

### Architecture Documentation Pattern
```markdown
## File Organization Plan:
- **Architecture Document**: docs/architecture.md
- **Research Documentation**: docs/research/[tech]-research/
- **Context Integration**: Links to docs/consultation/ and docs/requirements/
- **Development Access**: Architecture serves as central technical reference
```

## Complexity-Responsive Architecture Approach

**First, read the Project Complexity Assessment from consultation brief to determine architecture scope:**

### Simple Feature Architecture (5-15 minutes)
**When consultation shows "Simple Feature":**
- **Skip comprehensive system design**
- **Focus on integration points** with existing systems
- **Create lightweight technical specification** instead of full architecture
- **Document only affected components** and integration patterns

### Standard Product Architecture (60-90 minutes)
**When consultation shows "Standard Product":**
- **Create comprehensive system architecture** supporting all Epics
- **Design scalable component structure**
- **Plan full technology stack and deployment strategy**
- **Include Epic-to-component mapping**

### Complex Platform Architecture (2-4 hours)
**When consultation shows "Complex Platform":**
- **Design enterprise-grade architecture**
- **Include advanced patterns** (microservices, event sourcing, etc.)
- **Plan for high availability and disaster recovery**
- **Design comprehensive security and compliance frameworks**

## Context7 Research Requirements (MANDATORY)

**⚠️ CRITICAL: Execute Context7 MCP research for ALL suggested technologies before making architectural decisions**

### Pre-Architecture Research
**Execute Context7 research for identified technologies based on project type (examples below - adapt based on actual project needs):**
- **Application Frameworks** (Web: Next.js/React, Mobile: React Native/Flutter, Desktop: Electron/Tauri, API: Express/FastAPI)
- **Data Storage** (Relational: PostgreSQL/MySQL, NoSQL: MongoDB/DynamoDB, Cache: Redis/Memcached, Files: S3/MinIO)
- **Authentication & Security** (Web: Auth0/NextAuth, Mobile: Firebase Auth, API: JWT/OAuth2, Enterprise: SAML/LDAP)
- **Infrastructure Platforms** (Cloud: AWS/GCP/Azure, Edge: Vercel/Netlify, Containers: Docker/Kubernetes, Serverless: Lambda/Functions)
- **Client Technologies** (Web: React/Vue, Mobile: Native/Cross-platform, Desktop: Native/Electron, CLI: Python/Go)

**Research Documentation Structure:**
```
docs/research/
├── [tech-name]-research/
│   ├── [tech]-architecture-patterns-YYYY-MM-DD.md
│   ├── [tech]-integration-patterns-YYYY-MM-DD.md
│   └── [tech]-deployment-practices-YYYY-MM-DD.md
```

**Each research document must include:**
1. **Filtered Best Practices** from Context7 responses
2. **Implementation Code Examples** showing architectural patterns
3. **Architecture Compliance Notes** ensuring consistency with project requirements

### Project Bootstrapping Priority (MANDATORY)

**Architecture must specify bootstrapping sequence based on project type:**

**Web Applications:** Initialize Framework → Dependencies → Database → Authentication → Business Logic
**Mobile Applications:** Initialize Platform → UI Framework → State Management → API Integration → Platform Services
**API/Backend Services:** Initialize Runtime → Database/Storage → Authentication → API Layer → Integration
**Desktop Applications:** Initialize Framework → UI Layer → Data Storage → System Integration → Distribution
**Data Platforms:** Initialize Infrastructure → Data Ingestion → Processing Pipeline → Storage → Analytics Layer
**Infrastructure Projects:** Initialize IaC → Network/Security → Compute Resources → Monitoring → Deployment Pipeline

## Pre-Analysis: Multi-Artifact Validation

**Before proceeding, validate required artifacts exist:**

### Required Artifacts
- **Consultation Artifacts** (`docs/consultation/`): Business context, technical considerations
- **Requirements Artifacts** (`docs/requirements/`): PRDs with Epic structure, user stories

**If any artifacts are missing**, respond with:
```
❌ Missing Required Artifacts
Cannot proceed with architecture design. Required artifacts not found.
Missing: [List missing files]
Please complete consultation and requirements phases first.
```

## Comprehensive Analysis Process

**Use sequential thinking MCP to systematically extract and synthesize information from all artifacts:**

### Phase 1: Business Context & Vision Analysis
From **consultation artifacts**:
- Business objectives and success metrics
- Target market and user behavior patterns
- Scale expectations and growth projections
- Budget, timeline, and organizational constraints

### Phase 2: Functional Requirements Analysis
From **requirements artifacts**:
- All Epics and features requiring architectural support
- User workflows and interaction patterns
- Data flow requirements between features
- Integration points and external system needs

### Phase 3: Technical Constraints Synthesis
From **both artifact sets**:
- Technology preferences and constraints
- Technical dependencies between Epics
- Scalability, security, and compliance needs
- Infrastructure requirements

### Phase 4: Architectural Decision Framework
Based on **complete product context**:
- Choose architectural patterns supporting all Epics
- Select technology stack meeting constraints and Epic requirements
- Design component structure supporting feature scalability
- Plan deployment strategy matching organizational capabilities

## Architecture Document Structure

**Before creating documentation, use sequential thinking MCP to plan document structure ensuring logical flow from business context through technical implementation.**

### Simple Feature Integration Architecture Template

```markdown
# Feature Integration Architecture - [Feature Name]

## Integration Context
**Existing System**: [Where feature integrates]
**Affected Components**: [Specific system parts that change]
**Technology Alignment**: [How feature uses existing tech stack]

## Implementation Approach
**Architecture Pattern**: [Simple pattern - usually follows existing system patterns]
**Integration Points**: [APIs, databases, services affected]
**Security Considerations**: [Auth, validation, data protection for this feature]

## Development Guidance
**File Structure**: [Where code should live in existing project]
- **Source Files**: src/[feature-area]/[specific-files]
- **Component Files**: src/components/[feature-components]
- **Utility Files**: src/lib/[feature-utilities]
- **Test Files**: tests/[feature-tests]
- **Documentation**: docs/[feature-documentation]

**Project Structure Compliance**:
- Follow existing project organization patterns
- Place source code in appropriate src/ subdirectories
- Never place implementation files in project root
- Maintain separation between components, utilities, and tests

**Testing Strategy**: [Minimal testing approach for feature]
**Deployment Notes**: [How feature deploys with existing system]

## Context7 Research Required
- [Specific technology patterns needed for integration]
- [Security best practices for feature type]
- [Performance considerations for existing system impact]

---
*Lightweight architecture appropriate for simple feature development*
```

### Standard/Complex Product Architecture Template

### Document Sections

1. **Project Overview** - Business objectives, key features, target users, platform/deployment context
2. **Requirements Summary** - Epic architecture map, cross-Epic dependencies, non-functional requirements, platform constraints
3. **System Architecture** - High-level architecture, pattern rationale, technology stack, Epic-to-component mapping
4. **Technical Specifications** - Data architecture, integration design, security architecture, performance considerations
5. **Infrastructure & Deployment** - Deployment architecture, development environment, CI/CD pipeline, platform-specific considerations
6. **Epic Implementation Strategy** - Development order, component reuse, integration points, scaling strategy
7. **Development Guidelines** - Code organization, Epic development patterns, testing strategy, platform best practices
8. **Operational Considerations** - Maintenance, scalability plan, risk assessment, platform evolution, future considerations
9. **Architecture Evolution Framework** - Evolution checkpoints, versioning, controlled evolution process

## Code Organization & Project Structure Template

**Include this section in all architecture documents as "Development Guidelines > Code Organization":**

```markdown
## Code Organization & Project Structure

### Recommended Project Structure
```
project-name/
├── README.md                  # Project overview and setup instructions
├── docs/                      # All project documentation
│   ├── consultation/         # Business requirements and consultation artifacts
│   ├── requirements/         # Product requirements documents
│   ├── research/             # Context7 research findings
│   └── architecture.md       # This document
├── src/                      # All source code (or app/ for Next.js)
│   ├── components/           # Reusable UI components
│   ├── pages/               # Page components (if applicable)
│   ├── lib/                 # Utility functions and configurations
│   ├── hooks/               # Custom React hooks (if React)
│   ├── types/               # Type definitions
│   └── styles/              # Styling files
├── tests/                   # Test files
├── public/                  # Static assets
├── .gitignore              # Git ignore patterns
├── package.json            # Dependencies and scripts (Node.js)
├── [framework config]      # next.config.js, vite.config.js, etc.
└── [environment files]     # .env.local, .env.example
```

### File Placement Rules
1. **Never place source code in project root** - Always use src/ or app/
2. **Follow framework conventions** - Next.js uses app/, React uses src/
3. **Group related functionality** - Components, hooks, utilities in dedicated directories
4. **Separate concerns** - Tests, docs, and source code in different directories
5. **Configuration at root** - Package.json, config files, environment files

### Component Organization Pattern
```
src/components/
├── ui/                      # Basic UI components (buttons, inputs)
├── forms/                   # Form components
├── layout/                  # Layout components (header, footer, sidebar)
└── feature-specific/        # Components specific to business features
```

### Implementation Directory Guidelines
**When implementing Epic tasks:**
- **Epic 1 (Auth)**: src/components/auth/, src/lib/auth/, src/types/auth.ts
- **Epic 2 (Dashboard)**: src/components/dashboard/, src/lib/dashboard/
- **Epic 3 (API)**: src/lib/api/, src/types/api.ts (or separate API project)

### Project Initialization Commands
```bash
# Create project structure
mkdir project-name
cd project-name

# Initialize with framework (choose one):
npx create-next-app@latest . --typescript --tailwind --app
npx create-react-app . --template typescript
npm init -y && mkdir src tests docs

# Create directory structure
mkdir -p src/{components,lib,hooks,types,styles}
mkdir -p docs/{consultation,requirements,research}
mkdir -p tests
```

## Architecture Evolution Framework

### Evolution Checkpoints
**Epic Completion Reviews**: After each Epic, evaluate:
- Architecture assumptions vs. implementation reality
- Performance characteristics vs. projections
- Integration complexity vs. design
- Technology stack effectiveness vs. requirements

### Evolution Process
1. **Document Learnings**: What worked/didn't work during Epic implementation
2. **Impact Assessment**: How changes affect remaining Epics
3. **Stakeholder Review**: Business impact of proposed architecture changes
4. **Controlled Evolution**: Update architecture.md with versioning and migration notes

### Architecture Versioning
```markdown
## Architecture History
- **v1.0** (Initial): [Date] - Original architecture based on consultation requirements
- **v1.1** (Epic 2 learnings): [Date] - Updated auth patterns based on implementation findings
- **v2.0** (Major revision): [Date] - Technology stack change due to scale requirements discovered
```

### Evolution Decision Matrix
**When to evolve architecture:**
- **Minor Updates**: Pattern improvements, configuration changes
- **Major Updates**: Technology changes, scaling requirements, security enhancements
- **Complete Redesign**: Fundamental business model changes, platform shifts

## Quality Standards

### Artifact Integration Fidelity
- **Complete Epic Support** - Architecture accommodates ALL identified Epics
- **Constraint Compliance** - All consultation constraints respected in design decisions
- **Requirements Traceability** - Every Epic requirement has architectural support
- **Context Preservation** - Business rationale maintained in technical decisions

### Technical Excellence
- **Pattern Consistency** - Architectural patterns applied consistently across Epics
- **Scalability Alignment** - Architecture scales with business projections
- **Technology Optimization** - Stack choices optimize for Epic complexity and team capabilities
- **Integration Coherence** - All Epic integration points clearly defined

### Development Team Readiness
- **Implementation Clarity** - Clear guidance for Epic development teams
- **Project Structure Definition** - Comprehensive code organization and file placement rules
- **Directory Organization** - Epic-specific file organization and component placement guidelines
- **Decision Documentation** - Rationale for all major architectural choices
- **Evolution Planning** - Clear path for post-MVP Epic integration

### Evolution Preparedness
- **Change Management** - Clear process for architectural evolution
- **Version Control** - Architectural decision history and rationale
- **Impact Assessment** - Tools for evaluating architectural changes
- **Stakeholder Communication** - Process for architectural change approval

## Final Validation

**Before completing architecture document, use sequential thinking MCP for systematic review:**

1. **Epic Coverage Validation** - Every Epic has architectural support
2. **Consultation Constraint Verification** - All business/technical constraints addressed
3. **Integration Coherence** - All Epic interaction points architecturally sound
4. **Project Structure Completeness** - Code organization and file placement guidelines included
5. **Implementation Readiness** - Architecture provides clear development guidance
6. **Evolution Framework** - Clear process for architectural evolution established

## Output Format

**Save as `docs/architecture.md`** with comprehensive markdown formatting:
- **Epic References** - Clear mapping between requirements and architectural decisions
- **Consultation Citations** - Reference specific business decisions and constraints
- **Implementation Guidance** - Concrete direction for development teams
- **Visual Diagrams** - Text-based diagrams showing Epic-component relationships
- **Evolution Framework** - Process for architectural change management

---

## Integration Examples

### Technology Stack Selection
```markdown
**Primary Platform**: [Technology] with [Framework]
- *Rationale*: Aligns with team expertise and project requirements (from consultation)
- *Epic Support*: Handles specific requirements for [Epic Name]
- *Scale Alignment*: Supports projected usage patterns (consultation requirement)
- *Platform Fit*: Matches deployment and operational constraints
- *Evolution Readiness*: Can adapt to growth requirements identified in consultation
```

### Epic-Architecture Mapping
```markdown
### Epic 1: [Epic Name]
**Primary Components**:
- [Component Name] ([Technology], supports consultation [requirement type])
- [Integration Layer] (handles [Epic requirement] from user stories)
- [Data Layer] ([Storage solution], supports consultation compliance needs)

**File Organization**:
- **Source Directory**: src/[epic-specific-directory]/
- **Component Files**: src/components/[epic-name]/
- **Utility Functions**: src/lib/[epic-name]/
- **Type Definitions**: src/types/[epic-name].ts
- **Test Files**: tests/[epic-name]/

**Integration Points**:
- [Integration description with other Epics]
- [Data flow and API contracts]
- [Cross-platform considerations if applicable]

**Evolution Considerations**:
- [How this Epic might change based on user feedback]
- [Scaling considerations for this Epic]
- [Integration impact on future Epics]
```

### Architecture Evolution Planning
```markdown
## Future Architecture Considerations

### Anticipated Evolution Areas
**Based on consultation growth projections:**
- **Scale Evolution**: [How architecture will adapt to user growth]
- **Feature Evolution**: [How new features will integrate]
- **Technology Evolution**: [Planned technology upgrades or migrations]

### Evolution Readiness
- **Modular Design**: Components can be upgraded independently
- **API Versioning**: Backward compatibility strategy for integrations
- **Data Migration**: Plans for data schema evolution
- **Monitoring**: Metrics to trigger architectural evolution decisions
```

---

This architecture stage automatically processes both consultation business context and requirements Epic structure to generate technically sound, business-aligned architecture documentation with built-in evolution framework, ready for Epic-based development planning that can adapt and grow with the product over time.