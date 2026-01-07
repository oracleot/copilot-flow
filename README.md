# CopilotFlow

> 🚀 **Looking for the latest?** This workflow has evolved into [Spec Flow](https://github.com/oracleot/spec-flow) — a streamlined, spec-first toolkit built on GitHub's Spec Kit. Check it out for improved prompts, memory files, and a leaner workflow.

A comprehensive GitHub Copilot workflow system that guides you from initial product idea to ready-to-implement development tasks. This system ensures consistent, high-quality product development artifacts through structured AI-assisted workflows.

## 🎯 What This Does

This repository provides a complete product development pipeline using GitHub Copilot prompt files. It transforms rough product ideas into:

- **Business Requirements** through structured consultation
- **Technical Architecture** aligned with business needs  
- **Agile Epics and User Stories** ready for sprint planning
- **Development Tasks** with story point estimation
- **Consistent Documentation** across the entire product lifecycle

## 🚀 Key Benefits

- **End-to-End Consistency**: Every team member follows the same structured process
- **No Information Loss**: Business context is preserved from concept to implementation
- **Sprint-Ready Output**: Generates Agile tasks with proper estimation and dependencies
- **Team Alignment**: Standardized artifacts ensure everyone works from the same blueprint
- **Scalable Process**: Works for any project size with human-in-the-loop for complex projects

## 📋 Prerequisites

### Required
- **VS Code** with GitHub Copilot extension
- **GitHub Copilot subscription (optional, but better for using premium models)** (Individual, Business, or Enterprise)

### Highly Recommended
- **Sequential Thinking MCP**: For complex problem breakdown and enhanced reasoning
  - Significantly improves workflow quality and thoroughness
  - Essential for the consultation and architecture phases

## 🏗️ Setup

1. **Clone this repository** to your project workspace:
   ```bash
   git clone https://github.com/oracleot/copilot-flow.git your-project-name
   
   cd your-project-name
   ```

2. **Ensure GitHub Copilot is active** in VS Code

3. **Optional: Set up Sequential Thinking MCP** for enhanced capabilities

## 🔄 Workflow Overview

This system follows a **sequential workflow** where each stage builds upon the previous:

```
📝 Consultation → 📋 Requirements → � Design → �🏗️ Architecture → 📊 Tasks → 💻 Implementation
```

### Stage Dependencies
- **Requirements** depends on **Consultation** artifacts
- **Design** depends on **Consultation + Requirements** artifacts
- **Architecture** depends on **Consultation + Requirements + Design** artifacts  
- **Tasks** depends on **Consultation + Requirements + Design + Architecture** artifacts
- **Implementation** works with individual **Task** specifications

**Important**: Stages must be executed in sequence as later stages automatically reference artifacts created by earlier stages.

## 📖 How to Use

### 1. Start a Product Consultation (`/consult`)

Begin any new product with a structured business discovery session:

```
/consult
```

**What it does**:
- Conducts a natural conversation to understand your product vision
- Extracts business requirements, user needs, and technical constraints
- Creates structured handoff documentation for development teams

**Outputs** (saved to `docs/consultation/`):
- `[client-name]-consultation-brief-[date].md` - Business context and requirements
- `[client-name]-product-description-[date].md` - Formal product specification
- `[client-name]-conversation-history-[date].md` - Complete consultation record

### 2. Generate Product Requirements (`/requirements`)

Transform consultation insights into comprehensive Agile requirements:

```
/requirements  
```

**What it does**:
- Automatically reads consultation artifacts
- Structures features as Agile Epics with user stories
- Creates acceptance criteria and success metrics
- Prioritizes MVP vs future features

**Outputs** (saved to `docs/requirements/`):
- `product-requirements-comprehensive.md` - Complete PRD with Epic structure
- Or multiple `epic-[number]-[name].md` files for complex products

### 3. Create UI/UX Design Specifications (`/design`) [OPTIONAL]

Generate comprehensive UI/UX design specifications with modern component libraries:

```
/design
```

**When to use**:
- Frontend applications, mobile apps, web interfaces
- User-facing features requiring visual design
- Products needing component libraries and design systems

**Skip for**:
- Backend APIs, data processing, infrastructure projects
- CLI tools, internal services, database-only features

**What it does**:
- Automatically reads consultation and requirements artifacts
- Researches current UI component libraries for the target platform
- Creates detailed layout specifications and component selection
- Provides visual design guidelines and responsive patterns
- Plans design system integration with technical implementation

**Outputs** (saved to `docs/design/`):
- `[project-identifier]-ui-components-[date].md` - Component library specifications
- `[project-identifier]-layout-design-[date].md` - Layout designs and patterns
- `[project-identifier]-design-system-[date].md` - Visual design guidelines

### 4. Create System Architecture (`/architecture`)

Generate technical architecture supporting all identified features:

```
/architecture
```

**What it does**:
- Analyzes consultation business context, requirements Epics, and design specifications (when available)
- Designs system architecture supporting all features and UI components (for user-facing features)
- Maps Epics to technical components and aligns with design system choices (when applicable)
- Provides implementation guidance for development teams
- Ensures technical stack supports design library and component requirements (for frontend features)

**Outputs**:
- `docs/architecture.md` - Comprehensive system architecture documentation

### 5. Break Down into Development Tasks (`/tasks`)

Convert the complete product context into sprint-ready Agile tasks:

```
/tasks
```

**What it does**:
- Processes consultation, requirements, design (when available), and architecture artifacts
- Creates detailed task breakdown with story point estimation
- Organizes tasks by Epic with clear dependencies
- Includes design implementation and UI component development tasks (for frontend features)
- Generates sprint planning guidance

**Outputs** (saved to `docs/tasks/`):
- `epic-[number]-[name].md` - Individual Epic task files
- `epic-index.md` - Complete Epic overview and sprint planning guide

### 6. Implement Specific Tasks (`/implement`)

Execute individual development tasks with structured guidance:

```
/implement {add task to context}
```

**What it does**:
- Takes a specific task from the Epic files (added to Context)
- Provides structured implementation workflow
- Ensures quality standards, design compliance (when applicable), and testing
- Follows design system guidelines for frontend implementation (when relevant)
- Generates proper documentation and commit messages

**Outputs**:
- Implementation code and files
- Updated documentation
- Test coverage
- Structured commit messages

## 📁 Expected Project Structure

After running through the workflows, your project will have:

```
copilot-flow/
├── .github/
│   └── prompts/           # Workflow prompt files (from this repo)
├── docs/
│   ├── consultation/      # Business discovery artifacts
│   ├── requirements/      # Agile Epic and user story documentation
│   ├── design/           # UI/UX specifications and design system docs
│   ├── tasks/            # Sprint-ready development tasks
│   └── architecture.md   # System architecture documentation
├── src/                  # Your implementation code
└── README.md            # Project documentation
```

## 🎯 Usage Examples

### Starting a New Product
```
1. /consult             → Discover business requirements
2. /requirements        → Generate Agile Epic structure  
3. /design              → Create UI/UX specifications (optional for backend-only features)
4. /architecture        → Design technical foundation
5. /tasks               → Create development backlog
6. /implement           → Build individual features
```

### Adding Features to Existing Product
```
1. /consult             → Understand new feature requirements
2. /requirements        → Update existing docs with new consultation
3. /design              → Create/update UI/UX specifications (skip for backend APIs)
4. /architecture        → Evolve architecture for new features
5. /tasks               → Generate tasks for new Epics
6. /implement           → Build new functionality
```

### Backend API Development
```
1. /consult             → Discover API requirements
2. /requirements        → Generate API Epic structure
3. /architecture        → Design API architecture (skip /design)
4. /tasks               → Create API development tasks
5. /implement           → Build API endpoints
```

### Team Collaboration
```
1. Product Manager runs /consult + /requirements
2. UX Designer runs /design for UI/UX specifications (when needed)
3. Tech Lead runs /architecture  
4. Scrum Master runs /tasks for backlog creation
5. Developers use /implement for individual tasks
```

## 🛠️ Supporting Tools

### Documentation Lookup (`/lookup-doc`)
Search and retrieve relevant documentation using Context7 MCP:
```
/lookup-doc on how to install shadcn/ui for this project
```

### Complex Problem Solving (`/think`)  
Use sequential thinking for breaking down complex challenges:
```
/think of the best way to debug and fix this error: {DETAILED_ERROR_DESC}
```

## ⚠️ Important Notes

### Sequential Execution Required
- Each workflow stage depends on artifacts from previous stages
- Always run `/consult` first for new products
- **Design stage is optional** for backend APIs, CLI tools, data processing, and infrastructure projects
- Don't skip stages - later workflows will fail without proper artifacts

### Human Review Recommended
- For complex projects, review AI-generated artifacts
- Validate business requirements before proceeding to architecture
- Ensure technical decisions align with organizational constraints

### Team Consistency
- All team members should use the same workflow system
- Version control all generated artifacts
- Regular review and refinement of workflow outputs

## 📚 Additional Resources

- [Awesome Copilot](https://github.com/github/awesome-copilot)
- [Supercharge VSCode GitHub Copilot using Model Context Protocol (MCP) - Easy Setup Guide](https://dev.to/pwd9000/supercharge-vscode-github-copilot-using-model-context-protocol-mcp-easy-setup-guide-371e)
- [Instructions and Prompt Files to supercharge VS Code with GitHub Copilot](https://dev.to/pwd9000/supercharge-vscode-github-copilot-using-instructions-and-prompt-files-2p5e)

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

**Ready to streamline your product development?** Clone this repo and start with `/consult` to transform your next product idea into a structured development plan! 🚀
