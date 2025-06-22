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

### Validation Checkpoints
```markdown
### Sanity Check Points:
- Verify instruction adherence: Ask "What is my name?"
- Test command translation: Use natural language commands
- Check file access: Verify permission boundaries
- Validate workflow: Test parallel execution patterns
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

---

*These patterns are ready for direct implementation in CLAUDE.md files. Copy, customize with your specific values, and deploy for immediate use.*