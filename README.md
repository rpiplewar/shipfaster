# Rapid Shipping - Claude Code Plugin Collection

A comprehensive plugin collection designed to accelerate product development through AI-driven automation, context engineering, and systematic validation.

## Overview

**Rapid Shipping** provides a powerful plugin for Claude Code:

**PRP (Product Requirement Prompt)** - Transform user stories into executable implementation plans with one-pass success rates

The plugin emphasizes **context completeness**, **deterministic validation**, and **parallel processing** to achieve rapid, high-quality output.

## Table of Contents

- [Installation](#installation)
- [PRP Plugin](#prp-plugin)
- [Quick Start](#quick-start)
- [Documentation](#documentation)
- [Contributing](#contributing)

## Installation

### Prerequisites

- Claude Code installed and running
- Git installed
- Basic familiarity with command-line interfaces

### Add the Marketplace

```bash
/plugin marketplace add rpiplewar/rapid-shipping
```

### Install Plugin

```bash
/plugin install prp@rapid-shipping
```

### Verify Installation

Check available commands:
```bash
/help
```

You should see new commands prefixed with `/prp-`.

## PRP Plugin

**Agentic coding framework that bridges Product Requirements Documents (PRDs) and prompt engineering.**

### Key Features

- **Context Engineering**: Precise file paths, library versions, code snippets, and AI_docs references
- **Task Decomposition**: Break down user stories into executable tasks with dependency ordering
- **Implementation Strategies**: Multiple PRP types for different development scenarios
- **Validation Gates**: Deterministic checks with pytest, ruff, type checking
- **Multi-Agent Coordination**: Parallel analysis with specialized sub-agents

### Available Commands (15)

| Command | Description |
|---------|-------------|
| `/prp-base-create` | Create comprehensive PRP for major features |
| `/prp-base-execute` | Execute base PRP with full implementation |
| `/prp-story-create` | Convert user stories to tactical PRPs |
| `/prp-story-execute` | Execute story-based PRPs |

### Specialized Agents (2)

- **@codebase-analyst** - Deep pattern analysis and convention discovery
- **@library-researcher** - External documentation and best practices research

### Example Workflow

```
User Story: "Add OAuth authentication to the login page"
    ↓
/prp-story-create
    ├─ @codebase-analyst analyzes auth patterns
    ├─ @library-researcher fetches OAuth library docs
    └─ Generates Story PRP with context + tasks
    ↓
/prp-story-execute
    ├─ Task 1: CREATE OAuth provider config
    ├─ Task 2: UPDATE login component
    ├─ Task 3: ADD integration tests
    └─ Validation: pytest + type checks
    ↓
✓ Feature implemented with passing tests
```

### PRP Templates

Located in `prp/PRPs/templates/`:
- `prp_base.md` - Major features
- `prp_base_typescript.md` - TypeScript projects
- `prp_planning.md` - Planning phase
- `prp_poc_react.md` - React POCs
- `prp_spec.md` - Technical specifications
- `prp_story_task.md` - Sprint stories
- `prp_task.md` - Granular tasks

## Quick Start

**For a user story:**
```bash
/prp-story-create
# Provide your user story when prompted
# Review the generated PRP

/prp-story-execute
# Implementation with validation
```

**For a major feature:**
```bash
/prp-base-create
# Provide feature requirements
# Review comprehensive PRP

/prp-base-execute
# Full implementation
```

## Documentation

- **Concept Guide**: `prp/PRPs/README.md`
- **Story Workflow**: `prp/PRPs/STORY_WORKFLOW_GUIDE.md`
- **Templates**: `prp/PRPs/templates/`
- **AI Reference Docs**: `prp/PRPs/ai_docs/` (13 Claude Code reference documents)

## Key Concepts

### Context Engineering
Provide Claude with precise context to eliminate guesswork:
- Exact file paths and line numbers
- Library versions and documentation
- Integration points and patterns
- Testing strategies

### Task Decomposition
Break down complex features into clear, executable tasks:
- **CREATE**: Brand new functionality
- **UPDATE**: Modify existing code
- **ADD**: Extend current features
- **REMOVE**: Delete obsolete code
- **REFACTOR**: Improve without changing behavior
- **MIRROR**: Replicate existing patterns

## Directory Structure

```
shipfaster/
├── .claude-plugin/
│   └── marketplace.json          # Main plugin manifest
└── prp/                           # PRP Plugin
    ├── .claude-plugin/
    │   └── plugin.json
    ├── agents/                    # 2 specialized agents
    ├── commands/                  # 15 command definitions
    └── PRPs/
        ├── README.md
        ├── templates/             # 7 PRP templates
        ├── scripts/
        └── ai_docs/               # 13 Claude Code reference docs
```

## Requirements

- Claude Code with agent support
- Python (for pytest validation)
- Optional: TypeScript/Node.js (for TS PRPs)

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch
3. Test your changes thoroughly
4. Submit a pull request with clear description

### Development Setup

```bash
# Clone the repository
git clone https://github.com/rpiplewar/rapid-shipping.git
cd shipfaster

# Add as local marketplace for development
/plugin marketplace add file:///path/to/shipfaster

# Install plugin
/plugin install prp@rapid-shipping
```

## License

See LICENSE file for details.

## Author

**Rajat Piplewar**
- GitHub: [@rpiplewar](https://github.com/rpiplewar)

## Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Check the documentation in `prp/PRPs/README.md`
- Review Claude Code docs in `prp/PRPs/ai_docs/`

## Acknowledgments

- Built with [Claude Code](https://claude.com/claude-code)
- Inspired by systematic software engineering

---

**Ship faster. Build better.**
