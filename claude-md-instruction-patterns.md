# CLAUDE.md Instruction Patterns - Ready-to-Use Templates

*Copy-pasteable patterns and templates for actual CLAUDE.md files*

## Essential Patterns

### Sanity Check Pattern
```markdown
# My name is {YOUR_NAME}
```

### Basic CLAUDE.md Template
```markdown
# My name is {YOUR_NAME}

## Important Instructions
- ALL instructions within this document MUST BE FOLLOWED
- ASK FOR CLARIFICATION if uncertain of anything
- DO NOT edit more code than necessary
- DO NOT WASTE TOKENS, be succinct and concise

## Project-Specific Rules
[Your specific domain rules here]

## Workflow Guidelines
[Your workflow patterns here]

## File Access Permissions
[Your file access rules here]
```

## Priority Markers & Execution Patterns

### Priority Indicator Formats
```markdown
- **IMPERATIVE**: Non-negotiable, must be followed
- **CRITICAL**: High priority, essential rules
- **IMPORTANT**: Significant guidelines
- Regular text: Standard instructions
```

### Immediate Execution Patterns
```markdown
- IMPERATIVE: ANY time the user mentions "X", IMMEDIATELY run Y without question
- IMMEDIATE EXECUTION: Launch Z immediately upon request
- NO CLARIFICATION: Skip asking what type unless absolutely critical
```

### Prohibition Lists
```markdown
### DO NOT:
- Edit more code than necessary
- Waste tokens on verbose responses
- Question immediate execution commands
- Create tools when using existing commands
- Read files outside specified permissions
```

## Command Translation Systems

### Basic Command Translation Template
```markdown
### Command Translation:
- "switch to X tool" → `bash "/path/script.sh" --switch-tool X`
- "take a screenshot" → `bash "/path/script.sh" --screenshot`
- "preview current tool" → `bash "/path/script.sh" --tool-preview true`
```

### Complex Command System Template
```markdown
## {SYSTEM_NAME} Control System
- IMPERATIVE: ANY time user mentions "{trigger_phrase}", IMMEDIATELY run {command} without question
- Execute using: `{exact_command_syntax}`

### Command Translation:
- "{natural_language}" → `{technical_command}`
- "{another_example}" → `{technical_syntax}`

### Execution Rules:
1. Convert user requests to proper command format
2. Execute immediately without clarification
3. Handle all variations of the trigger phrase
```

### Multi-Step Workflow Pattern
```markdown
### Complete Testing Sequence:
```
bash "/path/script.sh" \
  --enable-accessibility \
  --go-home \
  --delay 2 \
  --tool-preview \
  --delay 3 \
  --cycle-tools watchface,wearfx,scroll:3
```
```

## Rule Structure Templates

### Structured Rule Lists
```markdown
### Execution Rules:
1. **Analysis**: Understand requirements completely
2. **Planning**: Use appropriate thinking tools  
3. **Implementation**: Execute with specified tools
4. **Validation**: Verify results meet criteria
```

### Priority Rule System
```markdown
### Feature Implementation Priority Rules:
- IMMEDIATE EXECUTION: Launch parallel Tasks immediately upon feature requests
- NO CLARIFICATION: Skip asking what type unless absolutely critical  
- PARALLEL BY DEFAULT: Always use 7-parallel-Task method for efficiency
```

## File Access Control Patterns

### Basic File Permissions
```markdown
### Permitted Reference Files:
- `adjustCurrentTool()` in `adjustCurrentTool.kt`
- `LoadTools()` in `loadTools.kt`

### DO NOT Read Unless Explicitly Asked:
- `singleOptionBroadcast.kt`
- `multipleOptionBroadcast.kt`
```

### Context Optimization Rules
```markdown
### Context Optimization Rules:
- Strip out all comments when reading code files for analysis
- Each task handles ONLY specified files or file types
- Task 7 combines small config/doc updates to prevent over-splitting
```

## Workflow Execution Templates

### Parallel Task Template
```markdown
## {TASK_TYPE} Workflow
### Priority Rules:
- IMMEDIATE EXECUTION: Launch ultra-fast Tasks immediately upon request
- NO CLARIFICATION: Skip asking what type unless absolutely critical
- ULTRA-FAST BY DEFAULT: Always use {N}-parallel-Task method

### {N}-Parallel Task Workflow:
1. **{Task1}**: {Description}
2. **{Task2}**: {Description}
3. **{Task3}**: {Description}
4. **{Task4}**: {Description}
5. **{Task5}**: {Description}
6. **{Task6}**: {Description}
7. **{Task7}**: {Description}

### Execution Guidelines:
- Each task handles ONLY specified files
- Strip comments when reading code for analysis
- Use MultiEdit for multiple edits to same file
```

### 9-Parallel-Task Workflow Example
```markdown
### 9-Parallel-Task Workflow:
1. **Component**: Create main component file
2. **Styles**: Create component styles/CSS  
3. **Tests**: Create test files
4. **Types**: Create type definitions
5. **Hooks**: Create custom hooks/utilities
6. **Integration**: Update routing, imports, exports
7. **Remaining**: Update config files, documentation
8. **Review**: Coordinate integration and validation
```

## Permission System Configurations

### AllowedTools Configuration Examples
```markdown
### Recommended AllowedTools Setup:
- Research tasks: Read(*), Grep(*), LS(*)
- Development: Edit(*), Write(*) with specific file patterns
- Automation: Bash(*) for trusted scripts only
```

### Permission Mode Integration
```markdown
### When to Use Each Mode:
- **Plan Mode**: Research, analysis, planning before execution
- **Auto-Accept**: Trusted workflows, repetitive tasks
- **Normal Mode**: Default for careful execution
```

## Specific Implementation Patterns

### Watch Control System Example
```markdown
### Watch Control System
- IMPERATIVE: ANY time user mentions "watch control", IMMEDIATELY run the watch-control command without question
- Execute using: `bash "/path/to/script.sh"` followed by appropriate options
- ALWAYS convert natural language to proper command format

### Example Conversions:
Basic commands:
- "switch to wearfx tool" → `bash "/path/script.sh" --switch-tool wearfx`
- "take a screenshot" → `bash "/path/script.sh" --watch-screenshot`

Complex commands:
- "cycle through tools [A, B, C] with 3s delay" → `bash "/path/script.sh" --cycle-tools A,B,C:3`
```

### Tool Maker Pattern
```markdown
### Tool Creation Workflow
- IMMEDIATE EXECUTION: Launch parallel Tasks immediately upon tool requests
- NO CLARIFICATION: Skip asking what type unless absolutely critical
- PARALLEL BY DEFAULT: Always use 7-parallel-Task method for efficiency

### 7-Parallel-Task Workflow:
1. **Core Logic**: Implement main tool functionality
2. **Configuration**: Create config files and settings
3. **Integration**: Update build files and dependencies
4. **Testing**: Create test files and validation
5. **Documentation**: Update README and usage docs
6. **Examples**: Create example usage and demos
7. **Polish**: Final integration and cleanup
```

## Advanced Rule Patterns

### Context Management Rules
```markdown
### Token Optimization Rules:
- Remove all comments (block, inline, KDoc/Javadoc) when analyzing code
- Filter out logging statements and debug information
- Ignore formatting whitespace in large files
- Focus only on functional code structure
```

### Dynamic Memory Patterns
```markdown
### Memory Refresh Commands:
- Quick Memory: Using # commands
- Explicit file reads: Re-reading updated content
- Session restart: New Claude Code session
- Spawn new instances: Different directories with different CLAUDE.md
```

### Import System Patterns
```markdown
### CLAUDE.md Import System:
- Basic imports: @README for project overview
- Relative paths: @docs/git-instructions.md
- Home directory: @~/.claude/my-project-instructions.md
- Recursive imports: Max-depth of 5 hops allowed
- Import safety: Not evaluated in code spans or blocks

### Import Rules:
- Imported files can recursively import additional files
- Use /memory command to see loaded files
- @ file references add CLAUDE.md from directory and parents to context
```

### Memory Hierarchy Patterns
```markdown
### Memory Type Configuration:
- Project memory (./CLAUDE.md): Team-shared instructions
- User memory (~/.claude/CLAUDE.md): Personal preferences for all projects
- Local memory (./CLAUDE.local.md): DEPRECATED - use imports instead

### Memory Discovery Behavior:
- Recursive loading: Start in cwd, recurse up to root
- Auto-load: Any CLAUDE.md or CLAUDE.local.md files found
- Subtree discovery: Load child CLAUDE.md files on demand
- Context separation: Keep project CLAUDE.md lightweight for strict separation
```

### CLAUDE.md Supremacy Patterns
```markdown
### Adherence Hierarchy Implementation:
- CLAUDE.md instructions: Treated as immutable system rules
- User prompts: Interpreted as flexible requests within established rules
- Behavioral design: CLAUDE.md steps followed sequentially
- Persistence: CLAUDE.md context maintained throughout session
- Override prevention: User prompts rarely override CLAUDE.md directives

### Supremacy Optimization:
- Tactically flood CLAUDE.md with process context
- Use user prompts only for parameters or steering
- Front-load context rather than random file reading
- Provide multiple examples and file access restrictions
```

### Validation Checkpoints
```markdown
### Sanity Check Points:
- Verify instruction adherence: Ask "What is my name?"
- Test command translation: Use natural language commands
- Check file access: Verify permission boundaries
- Validate workflow: Test parallel execution patterns
- Progressive testing: Check integrity as context window fills
- Reference validation: Verify imported content accessibility
```

## Complete System Templates

### Feature Development System
```markdown
# My name is {PROJECT_NAME}_Developer

## Feature Implementation Protocol
- IMMEDIATE EXECUTION: Launch ultra-fast Tasks immediately upon feature requests
- NO CLARIFICATION: Skip asking what type unless absolutely critical
- PARALLEL BY DEFAULT: Always use 9-parallel-Task method for efficiency

### 9-Parallel-Task Workflow:
1. **Component**: Create main component file
2. **Styles**: Create component styles/CSS  
3. **Tests**: Create test files
4. **Types**: Create type definitions
5. **Hooks**: Create custom hooks/utilities
6. **Integration**: Update routing, imports, exports
7. **Config**: Update configuration files
8. **Docs**: Update documentation
9. **Review**: Final integration and validation

### Context Rules:
- Strip comments when reading code for analysis
- Each task handles ONLY specified files or file types
- Use MultiEdit for multiple edits to same file

### DO NOT:
- Edit more code than necessary
- Question immediate execution commands
- Create tools when following established patterns
```

### Command Control System
```markdown
# My name is {SYSTEM_NAME}_Controller

## {SYSTEM_NAME} Control System
- IMPERATIVE: ANY time user mentions "{trigger_phrase}", IMMEDIATELY run control command without question
- Execute using: `bash "{script_path}"` followed by appropriate options

### Command Translation Table:
- "{natural_command_1}" → `bash "{script_path}" --option-1`
- "{natural_command_2}" → `bash "{script_path}" --option-2`
- "{natural_command_3}" → `bash "{script_path}" --option-3`

### Multi-Step Sequences:
```
bash "{script_path}" \
  --step-1 \
  --delay 2 \
  --step-2 \
  --step-3
```

### Execution Rules:
1. Convert all user requests to proper command format
2. Execute immediately without asking for clarification
3. Handle all variations and combinations of trigger phrases
4. Report command execution status briefly

### DO NOT:
- Question immediate execution commands
- Ask for clarification unless command is completely unrecognizable
- Create new tools when using existing command system
```

### Multi-File Output System
```markdown
# Multi-File Output System

## Overview
This system enables Claude to deliver multiple files in a single JSON payload processed by a bash script.

## How to Use
When user needs multiple files generated:
1. Understand the user's request for multiple files
2. Format response as valid JSON object following schema below
3. Inform user to save output and process with write_files.sh script

## JSON Schema
```json
{
  "files": [
    {
      "file_name": "path/to/file.extension",
      "file_type": "text",
      "file_content": "The content of the file"
    }
  ]
}
```

## Important Rules
1. ALWAYS validate JSON before providing
2. ALWAYS ensure file paths are properly escaped
3. For binary files, use base64 encoding and "binary" file_type
4. NEVER include explanatory text outside JSON structure
5. When asked for multiple files, ALWAYS use this format

## Processing Instructions
Users save JSON to file and run: `./write_files.sh files.json`
```

### Import-Based Modular System
```markdown
# {PROJECT_NAME} Modular Configuration

## Core Configuration
@core-rules.md
@project-architecture.md

## Domain-Specific Extensions
@frontend-patterns.md
@backend-patterns.md
@testing-guidelines.md

## Personal Preferences
@~/.claude/personal-preferences.md
@~/.claude/project-specific-prefs.md

## Important Rules
- ALL imported instructions MUST BE FOLLOWED
- Import hierarchy: Core → Domain → Personal
- Use /memory to view all loaded configurations
- Imports recursively load up to 5 levels deep

## Workflow
- Modular design prevents instruction bleeding
- Clear separation of concerns
- Team-shared vs personal configurations
- Easy maintenance and updates
```

### Research System Template
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
2. **Source Identification**: Identify relevant documentation, code, references
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

---

*These patterns are ready for direct implementation in CLAUDE.md files. Copy, customize with your specific values, and deploy for immediate use.*