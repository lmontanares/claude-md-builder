# CLAUDE.md Slash Command Integration Reference

## Overview
Comprehensive guide to integrating Claude Code's slash command system with CLAUDE.md configurations for immediate execution and automated workflows.

## Core Integration Principles

### Slash Commands vs Natural Language
- **Natural Language**: Requires interpretation but provides accessibility
- **Slash Commands**: Direct execution with standardized syntax and maximum efficiency
- **Slash Command Integration**: Use both approaches with automatic translation layer

### Command Structure
```
/prefix:command-name [arguments]
```

**Components:**
- `prefix`: Command scope (`project` for team-shared, `user` for personal)
- `command-name`: Derived from markdown filename (supports namespacing)
- `arguments`: Optional parameters passed via `$ARGUMENTS` placeholder

## Command Categories

### Project Commands (Team-Shared)
**Location**: `.claude/commands/`
**Prefix**: `/project:`
**Purpose**: Team workflows and shared automation

#### Pattern Analysis Commands:
- `/project:analyze-patterns` → 5-Parallel-Analysis workflow execution
- `/project:extract-template $ARGUMENTS` → Template creation with domain focus
- `/project:optimize-context` → Token efficiency analysis
- `/project:validate-claude-md` → Sanity check protocol execution

#### Template Generation Commands:
- `/project:create-template $ARGUMENTS` → Domain-specific template generation
- `/project:design-command-system $ARGUMENTS` → Slash command pattern creation
- `/project:build-workflow $ARGUMENTS` → Parallel task sequence design

#### Development Commands:
- `/project:feature:create $ARGUMENTS` → Complete feature with parallel execution
- `/project:component:create $ARGUMENTS` → Component with associated files
- `/project:tool:create $ARGUMENTS` → Tool creation with parallel tasks

### Personal Commands (Individual)
**Location**: `~/.claude/commands/`
**Prefix**: `/user:`
**Purpose**: Personal preferences and individual workflows

#### Quick Actions:
- `/user:quick-template $ARGUMENTS` → Personal template shortcuts
- `/user:context-strip` → Advanced context optimization
- `/user:pattern-library` → Personal pattern management
- `/user:validate-performance` → Effectiveness testing

## Command Implementation Patterns

### Basic Command Structure
```markdown
---
allowed-tools: Write, Edit, MultiEdit, Task, Bash
description: Brief description of command purpose
---

# Command Title: $ARGUMENTS

## Context
- Project info: !`relevant bash command`
- File references: @path/to/file.ext
- Dynamic context: !`bash command with $ARGUMENTS`

## Execution
Command-specific instructions and workflow.
Use $ARGUMENTS for dynamic content.
```

### Advanced Command Features

#### Bash Command Integration (`!`)
```markdown
## Context
- Project structure: !`find src -name "*.ts" | head -10`
- Git status: !`git status --porcelain`
- Package info: !`npm list --depth=0`
- System info: !`uname -a`
```

#### File Reference Integration (`@`)
```markdown
## Context
- Configuration: @package.json
- Documentation: @README.md
- Templates: @templates/component.tsx
- Scripts: @scripts/build.sh
```

#### Dynamic Context with Arguments
```markdown
## Context
- Target analysis: !`find . -name "*$ARGUMENTS*" | head -10`
- Related files: !`grep -r "$ARGUMENTS" src/ | head -5`
```

## CLAUDE.md Integration Patterns

### Slash Command Translation System
Implement dual-path execution supporting both slash commands and natural language:

**Primary Path (Direct Slash Commands):**
```markdown
## Enhanced Slash Command System
- `/project:analyze-patterns` → Immediate execution
- `/project:create-template $ARGUMENTS` → Direct template creation
- `/project:feature:create $ARGUMENTS` → Instant feature development
```

**Secondary Path (Natural Language → Slash Commands):**
```markdown
## Natural Language Translation
- "analyze patterns" → `/project:analyze-patterns`
- "create template for e-commerce" → `/project:create-template e-commerce`
- "build user dashboard" → `/project:feature:create dashboard`
```

### Priority-Based Command Organization
```markdown
## Slash Command Integration
- **IMPERATIVE**: Slash commands execute immediately with highest priority
- **CRITICAL**: Natural language automatically translates to slash commands when no direct match
- **IMPORTANT**: Use project commands for team workflows, personal commands for individual preferences
```

### Context Optimization Rules
```markdown
## Command Execution Rules
- **PRIMARY PATH**: Slash commands execute immediately without interpretation
- **SECONDARY PATH**: Natural language triggers automatic slash command translation
- **CONTEXT OPTIMIZATION**: Commands include built-in context via `!` and `@`
- **PARALLEL BY DEFAULT**: Commands execute multiple tasks simultaneously
```

## Sample Command Implementations

### Pattern Analysis Command
**File**: `.claude/commands/analyze-patterns.md`
```markdown
---
allowed-tools: Read, Glob, Grep, Task, mcp__serena__*
description: Execute 5-Parallel-Analysis workflow on CLAUDE.md patterns
---

# Pattern Analysis Workflow

## Current Context
- Project CLAUDE.md files: !`find . -name "CLAUDE*.md" -type f`
- Pattern examples: @claude-md-complete-examples.md
- Memory management: @claude-md-memory-management.md
- Import system: @claude-md-import-system.md

## Execute 5-Parallel-Analysis
Launch 5 parallel tasks:
1. **Structure Extraction**: Identify modular components and organizational patterns
2. **Command Translation Mining**: Extract command mappings and automation patterns
3. **Context Optimization Analysis**: Catalog token-saving techniques
4. **Workflow Integration Analysis**: Identify Task tool and parallel execution patterns
5. **Template Synthesis**: Generate reusable components with implementation guidelines

Strip all comments and verbose content during analysis. Focus only on functional patterns.
```

### Template Creation Command
**File**: `.claude/commands/create-template.md`
```markdown
---
allowed-tools: Write, Edit, MultiEdit, Task, mcp__serena__*
description: Generate domain-specific CLAUDE.md template
---

# Template Creation for: $ARGUMENTS

## Context Analysis
- Domain requirements: $ARGUMENTS
- Existing patterns: @claude-md-complete-examples.md
- Reference files: @claude-md-import-system.md @claude-md-memory-management.md
- Hooks integration: @claude-md-hooks-integration.md

## Template Generation Workflow
1. **Domain Analysis**: Understand $ARGUMENTS requirements and constraints
2. **Pattern Selection**: Choose appropriate frameworks from proven patterns
3. **Rule Prioritization**: Organize by IMPERATIVE > CRITICAL > IMPORTANT
4. **Slash Command Integration**: Create project-specific slash commands
5. **Validation Integration**: Include sanity check mechanisms
6. **Documentation**: Generate usage guidelines with examples

Create complete template with:
- Core rules and priority system
- Slash command definitions
- Context optimization patterns
- Validation protocols
```

### Feature Creation Command
**File**: `.claude/commands/feature/create.md`
```markdown
---
allowed-tools: Write, Edit, MultiEdit, Task
description: Create complete feature with parallel task execution
---

# Feature Creation: $ARGUMENTS

## Context
- Project structure: !`find src -type f -name "*.{js,ts,jsx,tsx}" | head -20`
- Existing components: !`find src/components -name "*.tsx" | head -10`
- Current routing: @src/routes/index.ts
- Package dependencies: @package.json
- Style patterns: !`find src/styles -name "*.css" | head -5`

## 8-Parallel-Task Execution:
1. **Component**: Create main component @src/components/
2. **Styles**: Create component styles @src/styles/
3. **Tests**: Create test files @src/tests/
4. **Types**: Create type definitions @src/types/
5. **Hooks**: Create custom hooks @src/hooks/
6. **Utils**: Create utility functions @src/utils/
7. **Integration**: Update routing and exports
8. **Validation**: Final integration check

Execute all tasks in parallel for feature: $ARGUMENTS
Strip comments when reading code for analysis.
```

## Namespacing Patterns

### Hierarchical Organization
```
.claude/commands/
├── feature/
│   ├── create.md       → /project:feature:create
│   ├── test.md         → /project:feature:test
│   └── deploy.md       → /project:feature:deploy
├── component/
│   ├── create.md       → /project:component:create
│   ├── style.md        → /project:component:style
│   └── test.md         → /project:component:test
├── tool/
│   ├── create.md       → /project:tool:create
│   ├── ui.md           → /project:tool:ui
│   └── cli.md          → /project:tool:cli
└── template/
    ├── create.md       → /project:template:create
    ├── validate.md     → /project:template:validate
    └── optimize.md     → /project:template:optimize
```

### Command Naming Conventions
- **Action-focused**: `create`, `test`, `deploy`, `validate`
- **Domain-specific**: `feature`, `component`, `tool`, `template`
- **Consistent hierarchy**: `category:action` or `category:subcategory:action`

## Slash Command Integration Patterns

### Dual-Path Implementation Strategy
1. **Primary Path Setup**: Create slash command files in `.claude/commands/`
2. **Secondary Path Setup**: Add natural language translation mappings to CLAUDE.md
3. **Testing Both Paths**: Verify both slash commands and natural language work
4. **User Education**: Document both approaches for team adoption
5. **Progressive Enhancement**: Start with natural language, evolve to slash commands

### Translation Layer Design
```markdown
### Command Translation Rules:
**Primary Path (Slash Commands):**
- `/project:feature:create $ARGUMENTS` → Direct execution
- `/project:tool:create $ARGUMENTS` → Direct execution

**Secondary Path (Natural Language → Slash Commands):**
- "create feature [name]" → `/project:feature:create [name]`
- "build tool [name]" → `/project:tool:create [name]`
- "analyze patterns" → `/project:analyze-patterns`
```


## Best Practices

### Command Design
- **Single responsibility**: Each command has one clear purpose
- **Contextual awareness**: Include relevant context via `!` and `@`
- **Error handling**: Design for graceful failure and recovery
- **Documentation**: Clear descriptions and usage examples

### Performance Optimization
- **Efficient context**: Only include necessary information
- **Parallel execution**: Use Task tool for concurrent operations
- **Context stripping**: Remove comments and verbose content during analysis
- **Selective file access**: Target specific files rather than broad scans

### Team Collaboration
- **Shared commands**: Use project commands for team workflows
- **Personal customization**: Use user commands for individual preferences
- **Version control**: Check project commands into git
- **Documentation**: Maintain clear usage guidelines

### Slash Command Benefits
- **Accessibility**: New users can use natural language
- **Efficiency**: Experienced users can use direct slash commands
- **Flexibility**: Teams can choose their preferred interaction style
- **Backward Compatibility**: Existing patterns continue to work
- **Progressive Enhancement**: Users naturally evolve from natural language to slash commands

### Security Considerations
- **Input validation**: Sanitize `$ARGUMENTS` in bash commands
- **Path restrictions**: Validate file paths and prevent traversal
- **Tool permissions**: Use `allowed-tools` to restrict command capabilities
- **Audit logging**: Track command usage for security monitoring

## Troubleshooting

### Common Issues
- **Command not found**: Check file location and naming
- **Permission errors**: Verify `allowed-tools` configuration
- **Context failures**: Validate bash commands and file references
- **Argument handling**: Ensure proper `$ARGUMENTS` usage

### Debugging Techniques
- **Test commands**: Use simple commands to verify functionality
- **Context inspection**: Check bash command output independently
- **File validation**: Verify file references exist and are accessible
- **Incremental development**: Build commands progressively

## Integration Examples

### Multi-File Output System
```markdown
## Multi-File Output Commands
- `/project:output:multi-file $ARGUMENTS` → Generate multiple files as JSON
- `/project:output:process $ARGUMENTS` → Process JSON with write_files.sh
```

### Hooks Integration
```markdown
## Hooks Command Integration
- `/project:hooks:enable $ARGUMENTS` → Enable specific hook configurations
- `/project:hooks:validate` → Validate hook setup and security
```

### MCP Integration
```markdown
## MCP Command Integration
- `/project:mcp:setup $ARGUMENTS` → Configure MCP server connections
- `/project:mcp:validate` → Validate MCP tool availability
```

This comprehensive integration transforms CLAUDE.md from a passive configuration system into an active automation platform powered by Claude Code's slash command functionality.