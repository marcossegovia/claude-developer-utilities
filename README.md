# Claude Developer Utilities

A collection of foundational developer utilities powered by Claude Code, designed for extensibility and automation of common development tasks.

## Overview

This repository serves as a comprehensive toolkit for developers, featuring intelligent automation tools built on Claude Code's agent system. Currently focused on API development workflows, with plans to expand into additional development utilities.

### Current Tools

- **OpenAPI Swagger Merge Tool**: Sophisticated merging of OpenAPI/Swagger specifications with intelligent conflict resolution and backward compatibility preservation

## Architecture

This toolkit is built on Claude Code's extensible agent system, allowing for:

- **Modular Design**: Each utility is self-contained with its own agents and commands
- **Extensible Framework**: Easy addition of new tools and utilities
- **Intelligent Automation**: AI-powered decision making for complex development tasks
- **Integration Ready**: Seamless integration with existing development workflows

## Current Features

### OpenAPI Swagger Merge Tool
- **Intelligent Merge Resolution**: Automatically resolves conflicts between OpenAPI specifications
- **Backward Compatibility**: Ensures existing API clients continue to work after merges
- **Conflict Detection**: Identifies duplicate endpoints, schemas, and parameter conflicts
- **Detailed Reporting**: Generates comprehensive merge reports and change summaries
- **Schema Validation**: Validates merged specifications against OpenAPI 3.0.3 standards

## Project Structure

```
.
├── .claude/                    # Claude Code configuration
│   ├── agents/                 # Specialized AI agents
│   │   ├── swagger-duplicate-detector.md  # Conflict detection agent
│   │   └── swagger-merge-resolver.md       # Merge resolution agent
│   └── commands/               # Custom commands
│       └── merge-swagger.md    # OpenAPI merge command
├── tests/                      # Test data and examples
│   └── merge-swagger/          # OpenAPI merge tool examples
│       ├── main-swagger.yaml          # Primary OpenAPI specification
│       ├── candidate-swagger.yaml     # Candidate changes to merge
│       └── output/                     # Generated outputs
│           ├── merged-swagger.yaml    # Final merged specification
│           ├── merge-report.json      # Technical merge analysis
│           └── changes-summary.md     # Human-readable summary
├── LICENSE                     # MIT License
├── README.md                   # This file
└── .gitignore                  # Git ignore rules
```

## Getting Started

### Prerequisites
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and configured
- Access to Claude API

### MCP Server Requirements

#### OpenAPI Swagger Merge Tool
- **Filesystem MCP Server**: ⚠️ **Required** - For reading/writing swagger files and generating reports
  - Functions used: `read_file`, `write_file`, `create_directory`, `list_directory`
- **Memory MCP Server**: 🔧 **Recommended** - For maintaining context during complex merge operations
  - Functions used: `create_entities`, `create_relations`, `read_graph`

#### Future Tools
As new utilities are added, their specific MCP server requirements will be documented here.

### Installation
1. Clone this repository
2. Navigate to the project directory
3. Ensure required MCP servers are configured in your Claude Code setup
4. The tools are ready to use with Claude Code

## Usage

### OpenAPI Swagger Merge Tool

The OpenAPI merge tool uses specialized Claude agents for intelligent specification merging:

### Merge Process

1. **Detection Phase**: The duplicate detector agent analyzes both specifications for conflicts
2. **Resolution Phase**: The merge resolver agent applies intelligent merging strategies
3. **Validation Phase**: Final specification is validated for correctness
4. **Reporting Phase**: Detailed reports are generated

### Merge Strategies

- **Backward Compatible Union**: Preserves existing functionality while adding new features
- **Legacy Field Support**: Maintains deprecated fields for compatibility
- **Optional Extensions**: Adds new parameters and fields as optional
- **Conflict Resolution**: Handles schema conflicts with intelligent defaults

## Example Output

The merge process generates:

- **merged-swagger.yaml**: Complete merged OpenAPI specification
- **merge-report.json**: Technical analysis with severity ratings
- **changes-summary.md**: Human-readable summary of changes and impacts

## Contributing

We welcome contributions that expand the utility collection! When adding new tools:

1. Follow the modular design pattern established by existing tools
2. Create dedicated agents and commands in the `.claude/` directory
3. Include comprehensive examples and test data
4. Update this README with your new utility
5. Ensure backward compatibility for existing tools

### Adding New Utilities

1. Create agent definitions in `.claude/agents/`
2. Add command definitions in `.claude/commands/`
3. Include test/example data in appropriate subdirectories
4. Update project documentation

## License

MIT License - see [LICENSE](LICENSE) file for details