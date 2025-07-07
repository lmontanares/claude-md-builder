# Complete CLAUDE.md Examples & Templates

## Multi-File Output System Template

### Overview
Template for enabling Claude to deliver multiple files in a single JSON payload, processed by a bash script with stylized output.

### Complete Template
```markdown
# Multi-File Output System

## Overview
This system enables Claude to deliver multiple files in a single JSON payload. The JSON is processed by a bash script that writes all files in parallel with stylized output.

## How to Use
When the user needs multiple files generated as a single output, follow these instructions:

1. Understand the user's request for multiple files
2. Format your response as a valid JSON object following the schema below
3. Inform the user they can save this output to a file and process it with the write_files.sh script

## JSON Schema for Multi-File Output
```json
{
  "files": [
    {
      "file_name": "path/to/file1.extension",
      "file_type": "text",
      "file_content": "The content of the first file"
    },
    {
      "file_name": "path/to/file2.extension",
      "file_type": "text", 
      "file_content": "The content of the second file"
    },
    {
      "file_name": "path/to/binary_file.bin",
      "file_type": "binary",
      "file_content": "base64_encoded_content_here"
    }
  ]
}
```

## Field Definitions
- `file_name`: The path where the file should be written (including filename and extension)
- IMPORTANT: Always use project-relative paths (e.g., "src/main/java/...") or absolute paths
- Files will be written to exactly the location specified - no test directories are used
- For tool creation, always use actual project paths, not test directories
- `file_type`: Either "text" (default) or "binary" for base64-encoded content
- `file_content`: The actual content of the file (base64 encoded for binary files)

## Important Rules
1. ALWAYS validate the JSON before providing it to ensure it's properly formatted
2. ALWAYS ensure all file paths are properly escaped
3. For binary files, encode the content as base64 and specify "binary" as the file_type
4. NEVER include explanatory text or markdown outside the JSON structure
5. When asked to generate multiple files, ALWAYS use this format unless explicitly directed otherwise

## How Users Can Process the Output
Instruct users to:
1. Save the JSON output to a file (e.g., `files.json`)
2. Run the write_files.sh script:
```bash
./write_files.sh files.json
```

## Command to Add to CLAUDE.md
```markdown
## Multi-File Output System
- When the user mentions "multi-file output", "generate files as json", or similar requests for bundled file generation, use the multi-file output system
- Execute using: `./write_files.sh <json_file>`
- Provide output as a single JSON object following the schema in `./multi_file_instructions.md`
- The JSON must include an array of files, each with file_name, file_type, and file_content fields
- For binary files, encode content as base64 and set file_type to "binary"
- NEVER include explanatory text or markdown outside the JSON structure
```
```

## Task Stats System Template

### Overview
Template for automated task cost and usage information retrieval system.

### Complete Template
```markdown
# Task Cost and Usage Information Retrieval

## Important
- ALL instructions within this document MUST BE FOLLOWED, these are not optional unless explicitly stated.
- ASK FOR CLARIFICATION If you are uncertain of any of thing within the document.
- DO NOT edit more code than you have to.
- DO NOT WASTE TOKENS, be succinct and concise.

## Task Stats System
- IMPERATIVE: ANY time the user mentions "task stats", "get task stats", "last task stats", or similar variations, IMMEDIATELY use the automated task stats script without question.

### Task Stats Script Usage:
**Primary Command**: `bash "/path/to/project/.claude/functions/task/task_stats.sh"`

**Script Options:**
- `bash .claude/functions/task/task_stats.sh` - Auto-detects and analyzes most recent Task session
- `bash .claude/functions/task/task_stats.sh session_id.jsonl` - Analyzes specific session file

### IMPORTANT RULES:
- Execute the task_stats.sh script immediately when task stats are requested
- The script auto-detects the most recent Task session or accepts a specific session file
```

## Slash Command System Template

### Overview
Template for creating automated command execution systems using both slash commands and natural language with automatic translation.

### Complete Template
```markdown
# {SYSTEM_NAME} Slash Command System

## Important
- ALL instructions within this document MUST BE FOLLOWED, these are not optional unless explicitly stated.
- DO NOT edit more code than you have to.
- DO NOT WASTE TOKENS, be succinct and concise.

## Slash Command Integration
- IMPERATIVE: Slash commands execute immediately with highest priority
- CRITICAL: Natural language automatically translates to slash commands when no direct match
- IMPORTANT: Use project commands for team workflows, personal commands for individual preferences

## Project Commands (Team-Shared)
Location: `.claude/commands/`

### Core System Commands:
- `/project:{system_name}:execute $ARGUMENTS` → Execute primary system function
- `/project:{system_name}:validate` → Run system validation
- `/project:{system_name}:optimize` → Optimize system performance
- `/project:{system_name}:status` → Check system status

### Workflow Commands (Namespaced):
- `/project:{system_name}:workflow:start $ARGUMENTS` → Start system workflow
- `/project:{system_name}:workflow:stop` → Stop system workflow
- `/project:{system_name}:workflow:monitor` → Monitor workflow execution

## Personal Commands (Individual)
Location: `~/.claude/commands/`

### Quick Actions:
- `/user:{system_name}:quick-action $ARGUMENTS` → Personal quick action
- `/user:{system_name}:custom-config` → Personal configuration
- `/user:{system_name}:debug` → Personal debugging workflow

## Command Implementation Examples

### Primary Command (`.claude/commands/{system_name}/execute.md`):
```markdown
---
allowed-tools: Bash, Read, Write, Task
description: Execute {system_name} with parameters
---

# {SYSTEM_NAME} Execution: $ARGUMENTS

## Context
- System status: !`systemctl status {system_name} 2>/dev/null || echo "Service not found"`
- Current configuration: @config/{system_name}.conf
- Recent logs: !`tail -10 /var/log/{system_name}.log 2>/dev/null || echo "No logs found"`

## Execution
Execute {system_name} with parameters: $ARGUMENTS
- Validate input parameters
- Run system command with proper options
- Monitor execution and report status
```

### Command Translation Rules:
**Primary Path (Slash Commands):**
- `/project:{system_name}:execute $ARGUMENTS` → Direct execution
- `/project:{system_name}:status` → Direct status check
- `/project:{system_name}:workflow:start $ARGUMENTS` → Direct workflow start
- `/user:{system_name}:quick-action $ARGUMENTS` → Direct quick action

**Secondary Path (Natural Language → Slash Commands):**
- "execute system function" → `/project:{system_name}:execute $ARGUMENTS`
- "check system status" → `/project:{system_name}:status`
- "start workflow" → `/project:{system_name}:workflow:start $ARGUMENTS`
- "run quick action" → `/user:{system_name}:quick-action $ARGUMENTS`

### IMPORTANT RULES:
- DO NOT question immediate execution commands
- Slash commands execute directly without interpretation
- Natural language automatically translates to slash commands
- Use `$ARGUMENTS` placeholder for dynamic values
- Include context via `!` (bash) and `@` (file references)
```

## Feature Development Slash Command System Template

### Overview
Template for rapid feature development using slash commands with parallel task execution.

### Complete Template
```markdown
# {PROJECT_NAME} Feature Development with Slash Commands

## Important
- ALL instructions within this document MUST BE FOLLOWED, these are not optional unless explicitly stated.
- DO NOT edit more code than you have to.
- DO NOT WASTE TOKENS, be succinct and concise.

## Slash Command Integration
- IMMEDIATE EXECUTION: Slash commands execute {N}-parallel-Task workflow directly
- NATURAL LANGUAGE: Automatically translates to slash commands for accessibility
- CONTEXT OPTIMIZATION: Commands strip comments during analysis

## Feature Development Commands

### Primary Commands:
- `/project:feature:create $ARGUMENTS` → Create complete feature with parallel execution
- `/project:feature:test $ARGUMENTS` → Generate comprehensive tests
- `/project:feature:deploy $ARGUMENTS` → Deploy feature to environment
- `/project:feature:validate $ARGUMENTS` → Validate feature implementation

### Component Commands:
- `/project:component:create $ARGUMENTS` → Create component files
- `/project:component:style $ARGUMENTS` → Create component styles
- `/project:component:test $ARGUMENTS` → Create component tests
- `/project:component:integrate $ARGUMENTS` → Integrate component into project

## Command Implementation

### Feature Creation (`.claude/commands/feature/create.md`):
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

## {N}-Parallel-Task Execution:
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

### Component Creation (`.claude/commands/component/create.md`):
```markdown
---
allowed-tools: Write, Edit, MultiEdit, Task
description: Create component with associated files
---

# Component Creation: $ARGUMENTS

## Context
- Component patterns: !`find src/components -name "*.tsx" | head -5 | xargs head -10`
- Style patterns: !`find src/styles -name "*.css" | head -5`
- Test patterns: !`find src/tests -name "*.test.tsx" | head -5`

## Component Creation Tasks:
1. **Main Component**: Create React component file
2. **Styles**: Create CSS/styled-components
3. **Tests**: Create unit tests
4. **Types**: Create TypeScript definitions
5. **Story**: Create Storybook story (if applicable)
6. **Integration**: Update component index exports

Create component: $ARGUMENTS
```

### Command Translation Rules:
**Primary Path (Slash Commands):**
- `/project:feature:create dashboard` → Direct execution
- `/project:feature:create auth` → Direct execution
- `/project:component:create button` → Direct execution

**Secondary Path (Natural Language → Slash Commands):**
- "create new dashboard" → `/project:feature:create dashboard`
- "add user authentication" → `/project:feature:create auth`
- "build shopping cart" → `/project:feature:create cart`
- "make button component" → `/project:component:create button`
- "test feature X" → `/project:feature:test X`

### Context Rules:
- Strip comments when reading code for analysis
- Each task handles ONLY specified files or file types
- Use MultiEdit for multiple edits to same file
- Include relevant context via `!` (bash) and `@` (file references)

### DO NOT:
- Edit more code than necessary
- Question immediate execution commands
- Create tools when following established patterns
```

## Tool Maker Slash Command System Template

### Overview
Template for automated tool creation systems using slash commands with ultra-fast parallel execution.

### Complete Template
```markdown
# Tool Maker Slash Command System

## Important
- ALL instructions within this document MUST BE FOLLOWED, these are not optional unless explicitly stated.
- DO NOT edit more code than you have to.
- DO NOT WASTE TOKENS, be succinct and concise.

## Tool System Overview
A tool is an ISOLATED unit of functionality which can be selected by a user and adjusted through a gesture.

## Slash Command Integration
- IMMEDIATE EXECUTION: Slash commands execute {N}-parallel-Task workflow directly
- NATURAL LANGUAGE: Automatically translates to slash commands for accessibility
- ULTRA-FAST BY DEFAULT: Always use parallel execution for efficiency

## Tool Creation Commands

### Primary Commands:
- `/project:tool:create $ARGUMENTS` → Create complete tool with parallel execution
- `/project:tool:test $ARGUMENTS` → Generate comprehensive tool tests
- `/project:tool:deploy $ARGUMENTS` → Deploy tool to environment
- `/project:tool:validate $ARGUMENTS` → Validate tool implementation

### Tool Type Commands:
- `/project:tool:ui $ARGUMENTS` → Create UI-based tool
- `/project:tool:cli $ARGUMENTS` → Create command-line tool
- `/project:tool:api $ARGUMENTS` → Create API-based tool
- `/project:tool:widget $ARGUMENTS` → Create widget tool

## Command Implementation

### Tool Creation (`.claude/commands/tool/create.md`):
```markdown
---
allowed-tools: Write, Edit, MultiEdit, Task
description: Create complete tool with parallel task execution
---

# Tool Creation: $ARGUMENTS

## Context
- Existing tools: !`find tools -name "*.js" -o -name "*.ts" | head -10`
- Tool patterns: !`find tools -name "*.json" | head -5 | xargs head -10`
- Build config: @build.config.js
- Package dependencies: @package.json

## {N}-Parallel-Task Execution:
1. **Core Logic**: Implement main tool functionality
2. **Configuration**: Create config files and settings
3. **Integration**: Update build files and dependencies
4. **Testing**: Create test files and validation
5. **Documentation**: Update README and usage docs
6. **Examples**: Create example usage and demos
7. **Polish**: Final integration and cleanup

Execute all tasks in parallel for tool: $ARGUMENTS
Strip comments when reading code for analysis.
```

### UI Tool Creation (`.claude/commands/tool/ui.md`):
```markdown
---
allowed-tools: Write, Edit, MultiEdit, Task
description: Create UI-based tool with interface
---

# UI Tool Creation: $ARGUMENTS

## Context
- UI patterns: !`find src/components -name "*.tsx" | head -5 | xargs head -10`
- Style patterns: @src/styles/tools.css
- Tool registry: @src/tools/registry.ts

## UI Tool Tasks:
1. **Interface**: Create tool UI component
2. **Logic**: Create tool functionality
3. **Styles**: Create tool-specific styles
4. **Integration**: Register tool in system
5. **Tests**: Create UI interaction tests
6. **Documentation**: Create usage documentation

Create UI tool: $ARGUMENTS
```

### Command Translation Rules:
**Primary Path (Slash Commands):**
- `/project:tool:create $ARGUMENTS` → Direct tool creation
- `/project:tool:ui $ARGUMENTS` → Direct UI tool creation
- `/project:tool:cli $ARGUMENTS` → Direct CLI tool creation

**Secondary Path (Natural Language → Slash Commands):**
- "make a tool" → `/project:tool:create $ARGUMENTS`
- "create UI tool" → `/project:tool:ui $ARGUMENTS`
- "build CLI tool" → `/project:tool:cli $ARGUMENTS`
- "make widget" → `/project:tool:widget $ARGUMENTS`
- "test tool X" → `/project:tool:test X`

### When to Create a Tool
- IMPERATIVE: When user requests tool creation, IMMEDIATELY execute slash command
- Valid requests include "make a tool", "create a tool", "build a tool", or similar direct phrasing
- Skip clarification questions and proceed directly to ultra-fast implementation

### Context Rules:
- Strip comments when reading code for analysis
- Each task handles ONLY specified files
- Use MultiEdit for multiple edits to same file
- Include relevant context via `!` (bash) and `@` (file references)

### DO NOT:
- Edit more code than necessary
- Question immediate execution commands
- Ask for clarification unless absolutely critical
```

## Minimal Project Template

### Overview
Basic template for simple project configurations.

### Complete Template
```markdown
# {PROJECT_NAME}

## Important
- ALL instructions within this document MUST BE FOLLOWED
- DO NOT edit more code than you have to
- DO NOT WASTE TOKENS, be succinct and concise

## Project Overview
{Brief description of project}

## Common Commands
- {command1}: {description}
- {command2}: {description}
- {command3}: {description}

## Code Style
- {style_rule_1}
- {style_rule_2}
- {style_rule_3}

## Workflow
- {workflow_step_1}
- {workflow_step_2}
- {workflow_step_3}
```

## Advanced Research System Template

### Overview
Template for research-intensive projects with systematic information gathering.

### Complete Template
```markdown
# {PROJECT_NAME} Research System

## Important
- ALL instructions within this document MUST BE FOLLOWED
- ASK FOR CLARIFICATION if uncertain about research scope
- DO NOT WASTE TOKENS, be succinct and focused

## Research Protocol
- SYSTEMATIC APPROACH: Use structured research methodology
- PARALLEL INFORMATION GATHERING: Leverage multiple sources simultaneously
- VALIDATION REQUIRED: Cross-reference findings across sources

### Research Workflow:
1. **Scope Definition**: Clarify research objectives and boundaries
2. **Source Identification**: Identify relevant documentation, code, and references
3. **Parallel Analysis**: Simultaneously examine multiple information sources
4. **Pattern Extraction**: Identify common themes and important insights
5. **Synthesis**: Combine findings into actionable recommendations
6. **Validation**: Verify conclusions against project requirements

### Information Sources:
- Official documentation
- Existing codebase patterns
- Community best practices
- Performance benchmarks
- Security considerations

### Output Format:
- Executive summary with key findings
- Detailed analysis with supporting evidence
- Actionable recommendations with implementation steps
- Risk assessment and mitigation strategies
```

## Usage Guidelines

### Template Customization
1. **Replace placeholders**: All `{PLACEHOLDER}` text should be customized
2. **Adjust task counts**: Modify parallel task numbers based on project complexity
3. **Customize commands**: Update command examples to match your project
4. **Add domain specifics**: Include project-specific rules and conventions

### Integration Strategies
- **Start minimal**: Begin with basic template and add complexity gradually
- **Modular approach**: Use imports to combine multiple templates
- **Team collaboration**: Share templates via git for consistency
- **Regular updates**: Refine templates based on real-world usage

## Hooks Integration Slash Command Template

### Overview
Template for integrating Claude Code hooks system with slash commands for automated workflow enforcement and security validation.

### Complete Template
```markdown
# Hooks Integration Slash Command System

## Important
- ALL instructions within this document MUST BE FOLLOWED
- DO NOT edit more code than you have to
- DO NOT WASTE TOKENS, be succinct and focused

## Slash Command Integration
- IMPERATIVE: Slash commands execute hook configuration directly
- CRITICAL: Natural language automatically translates to slash commands
- IMPORTANT: Configure hooks to match your specific tool usage patterns

## Hooks Commands

### Primary Commands:
- `/project:hooks:enable $ARGUMENTS` → Enable specific hook configurations
- `/project:hooks:disable $ARGUMENTS` → Disable specific hook configurations
- `/project:hooks:validate` → Validate hook setup and security
- `/project:hooks:audit` → Review hook execution logs

### Hook Type Commands:
- `/project:hooks:code-quality` → Enable code formatting and linting hooks
- `/project:hooks:security` → Enable security validation hooks
- `/project:hooks:workflow` → Enable build/test/deploy automation hooks
- `/project:hooks:notifications` → Enable custom notification hooks

## Command Implementation

### Hook Enablement (`.claude/commands/hooks/enable.md`):
```markdown
---
allowed-tools: Write, Edit, MultiEdit, Bash
description: Enable hook configurations with security validation
---

# Hook Enablement: $ARGUMENTS

## Context
- Current hooks: @.claude/hooks.json
- Security patterns: @claude-md-hooks-integration.md
- Tool usage patterns: !`grep -r "tool_use" .claude/ | head -10`

## Hook Configuration Strategy:
1. **Code Quality Enforcement**: Automatic formatting and linting on file modifications
2. **Security Validation**: Block dangerous operations and validate file paths
3. **Workflow Automation**: Trigger build, test, and deployment processes
4. **Notification Systems**: Custom alerts for important events
5. **Audit Logging**: Track all operations for compliance and debugging

Enable hooks for: $ARGUMENTS
```

### Security Validation (`.claude/commands/hooks/validate.md`):
```markdown
---
allowed-tools: Bash, Read
description: Validate hook security and configuration
---

# Hook Security Validation

## Context
- Hook configuration: @.claude/hooks.json
- Security scripts: !`find .claude -name "*security*" -type f`
- Recent executions: !`tail -20 .claude/hook-logs.txt 2>/dev/null || echo "No logs found"`

## Security Validation Checklist:
- **Input Validation**: Verify hook inputs are sanitized
- **Path Sanitization**: Check for path traversal prevention
- **Permission Checks**: Verify file access controls
- **Command Whitelisting**: Confirm only approved commands
- **Audit Trail**: Validate logging mechanisms

Run comprehensive security validation of hook configurations.
```

### Sample Hook Patterns:
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write|Edit|MultiEdit",
        "hooks": [
          {
            "type": "command",
            "command": "~/.claude/hooks/format-code.sh"
          }
        ]
      }
    ],
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "~/.claude/hooks/validate-security.py"
          }
        ]
      }
    ]
  }
}
```

### Hook Command Translation:
**Primary Path (Slash Commands):**
- `/project:hooks:code-quality` → Direct code quality hook setup
- `/project:hooks:security` → Direct security validation setup
- `/project:hooks:audit` → Direct audit logging setup

**Secondary Path (Natural Language → Slash Commands):**
- "enable code formatting" → `/project:hooks:code-quality`
- "add security validation" → `/project:hooks:security`
- "setup audit logging" → `/project:hooks:audit`
- "enable notifications" → `/project:hooks:notifications`

### Security Patterns:
- **Input Validation**: Always validate and sanitize hook inputs
- **Path Sanitization**: Check for path traversal attempts
- **Permission Checks**: Verify file access permissions
- **Command Whitelisting**: Allow only approved commands
- **Audit Trail**: Log all hook executions

### Context Rules:
- Include hook configuration via `@.claude/hooks.json`
- Check security patterns via `@claude-md-hooks-integration.md`
- Monitor execution via `!` bash commands for logs
- Validate permissions via system checks
```

### Best Practices
- **Test thoroughly**: Validate templates with real scenarios
- **Document changes**: Track modifications for team awareness
- **Version control**: Use git to manage template evolution
- **Share learnings**: Contribute successful patterns back to team knowledge