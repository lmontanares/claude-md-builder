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

## Command Control System Template

### Overview
Generic template for creating automated command execution systems with natural language translation.

### Complete Template
```markdown
# {SYSTEM_NAME} Control System

## Important
- ALL instructions within this document MUST BE FOLLOWED, these are not optional unless explicitly stated.
- DO NOT edit more code than you have to.
- DO NOT WASTE TOKENS, be succinct and concise.

## {SYSTEM_NAME} Command System
- IMPERATIVE: ANY time the user mentions "{trigger_phrase}", IMMEDIATELY run the {system_name} command without question.
- Execute using: `bash "/path/to/script.sh"` followed by appropriate command-line options
- ALWAYS convert user's natural language requests to appropriate command-line options

### Command Format Translation:
- The system accepts natural language but internally converts commands to proper format
- Commands use double-dash format (e.g., `--command-name`, `--option value`)
- Handle conversion automatically without showing user the technical command format

### Example Command Conversions:
Basic commands:
- "do action X" → `bash "/path/script.sh" --action-x`
- "run process Y" → `bash "/path/script.sh" --process-y`

Complex commands:
- "cycle through options [A, B, C] with 3s delay" → `bash "/path/script.sh" --cycle-options A,B,C:3`

### IMPORTANT RULES:
- DO NOT question immediate execution commands
- Ask for clarification only if command is completely unrecognizable
- Always accept natural language descriptions and convert to appropriate command syntax
```

## Feature Development System Template

### Overview
Template for rapid feature development with parallel task execution.

### Complete Template
```markdown
# {PROJECT_NAME} Feature Development System

## Important
- ALL instructions within this document MUST BE FOLLOWED, these are not optional unless explicitly stated.
- DO NOT edit more code than you have to.
- DO NOT WASTE TOKENS, be succinct and concise.

## Feature Implementation Protocol
- IMMEDIATE EXECUTION: Launch ultra-fast Tasks immediately upon feature requests
- NO CLARIFICATION: Skip asking what type unless absolutely critical
- PARALLEL BY DEFAULT: Always use {N}-parallel-Task method for efficiency

### {N}-Parallel-Task Workflow:
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

## Tool Maker System Template

### Overview
Template for automated tool creation systems with ultra-fast parallel execution.

### Complete Template
```markdown
# Tool Maker System Guidelines

## Important
- ALL instructions within this document MUST BE FOLLOWED, these are not optional unless explicitly stated.
- DO NOT edit more code than you have to.
- DO NOT WASTE TOKENS, be succinct and concise.

## Tool System Overview
A tool is an ISOLATED unit of functionality which can be selected by a user and adjusted through a gesture.

### Tool Creation Priority Rules
- IMMEDIATE EXECUTION: Launch ultra-fast Tasks immediately upon tool creation requests
- NO CLARIFICATION: Skip asking what type of tool unless absolutely critical
- ASSUME DEFAULTS: {default_tool_type} unless explicitly specified otherwise
- ULTRA-FAST BY DEFAULT: Always use {N}-parallel-Task method for efficiency

### When to Create a Tool
- IMPERATIVE: When user requests tool creation, IMMEDIATELY launch ultra-fast Task creation without hesitation.
- Valid requests include "make a tool", "create a tool", "build a tool", or similar direct phrasing.
- Skip clarification questions and proceed directly to ultra-fast implementation.

### Ultra-Fast Tool Creation Workflow
**IMMEDIATE EXECUTION:** Upon ANY tool creation request, instantly launch all {N} Tasks in parallel:

1. **Core Logic**: Implement main tool functionality
2. **Configuration**: Create config files and settings
3. **Integration**: Update build files and dependencies
4. **Testing**: Create test files and validation
5. **Documentation**: Update README and usage docs
6. **Examples**: Create example usage and demos
7. **Polish**: Final integration and cleanup

### Context Rules:
- Strip comments when reading code for analysis
- Each task handles ONLY specified files
- Use MultiEdit for multiple edits to same file

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

### Best Practices
- **Test thoroughly**: Validate templates with real scenarios
- **Document changes**: Track modifications for team awareness
- **Version control**: Use git to manage template evolution
- **Share learnings**: Contribute successful patterns back to team knowledge