# CopilotFlow

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
   git clone https://github.com/your-username/copilot-flow.git your-project-name
   cd your-project-name
   ```

2. **Ensure GitHub Copilot is active** in VS Code

3. **Enable prompt files** in VS Code settings (usually enabled by default):
   - The prompt files in `.github/prompts/` will be automatically detected
   - No additional configuration needed

4. **Optional: Set up Sequential Thinking MCP** for enhanced capabilities

## 🔄 Workflow Overview

This system follows a **sequential workflow** where each stage builds upon the previous:

```
📝 Consultation → 📋 Requirements → 🏗️ Architecture → 📊 Tasks → 💻 Implementation
```

### Stage Dependencies
- **Requirements** depends on **Consultation** artifacts
- **Architecture** depends on **Consultation + Requirements** artifacts  
- **Tasks** depends on **Consultation + Requirements + Architecture** artifacts
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

### 3. Create System Architecture (`/architecture`)

Generate technical architecture supporting all identified features:

```
/architecture
```

**What it does**:
- Analyzes consultation business context and requirements Epics
- Designs system architecture supporting all features
- Maps Epics to technical components
- Provides implementation guidance for development teams

**Outputs**:
- `docs/architecture.md` - Comprehensive system architecture documentation

### 4. Break Down into Development Tasks (`/tasks`)

Convert the complete product context into sprint-ready Agile tasks:

```
/tasks
```

**What it does**:
- Processes consultation, requirements, and architecture artifacts
- Creates detailed task breakdown with story point estimation
- Organizes tasks by Epic with clear dependencies
- Generates sprint planning guidance

**Outputs** (saved to `docs/tasks/`):
- `epic-[number]-[name].md` - Individual Epic task files
- `epic-index.md` - Complete Epic overview and sprint planning guide

### 5. Implement Specific Tasks (`/implement`)

Execute individual development tasks with structured guidance:

```
/implement
```

**What it does**:
- Takes a specific task from the Epic files
- Provides structured implementation workflow
- Ensures quality standards and testing
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
│   ├── tasks/            # Sprint-ready development tasks
│   └── architecture.md   # System architecture documentation
├── src/                  # Your implementation code
└── README.md            # Project documentation
```

## 🎯 Usage Examples

### Starting a New Product
```
1. /consult              → Discover business requirements
2. /requirements         → Generate Agile Epic structure  
3. /architecture         → Design technical foundation
4. /tasks               → Create development backlog
5. /implement           → Build individual features
```

### Adding Features to Existing Product
```
1. /consult              → Understand new feature requirements
2. Update existing docs with new consultation
3. /architecture         → Evolve architecture for new features
4. /tasks               → Generate tasks for new Epics
5. /implement           → Build new functionality
```

### Team Collaboration
```
1. Product Manager runs /consult + /requirements
2. Tech Lead runs /architecture  
3. Scrum Master runs /tasks for backlog creation
4. Developers use /implement for individual tasks
```

## 🛠️ Supporting Tools

### Documentation Lookup (`/lookup-doc`)
Search and retrieve relevant documentation using Context7 MCP:
```
/lookup-doc on how do I install shadcn/ui
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
- Don't skip stages - later workflows will fail without proper artifacts

### Human Review Recommended
- For complex projects, review AI-generated artifacts
- Validate business requirements before proceeding to architecture
- Ensure technical decisions align with organizational constraints

### Team Consistency
- All team members should use the same workflow system
- Version control all generated artifacts
- Regular review and refinement of workflow outputs

## 🤝 Contributing

This is an open-source workflow system designed for the community:

1. **Fork the repository**
2. **Improve prompt files** based on your experience
3. **Share examples** of successful workflows
4. **Submit pull requests** with enhancements

### Areas for Contribution
- Additional workflow stages (e.g., testing, deployment)
- Industry-specific prompt variations
- Integration with other development tools
- Example projects demonstrating the full workflow

## 📚 Additional Resources

- [Awesome Copilot](https://github.com/github/awesome-copilot)
- [Supercharge VSCode GitHub Copilot using Model Context Protocol (MCP) - Easy Setup Guide](https://dev.to/pwd9000/supercharge-vscode-github-copilot-using-model-context-protocol-mcp-easy-setup-guide-371e)
- [Instructions and Prompt Files to supercharge VS Code with GitHub Copilot](https://dev.to/pwd9000/supercharge-vscode-github-copilot-using-instructions-and-prompt-files-2p5e)

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

**Ready to streamline your product development?** Clone this repo and start with `/consult` to transform your next product idea into a structured development plan! 🚀
