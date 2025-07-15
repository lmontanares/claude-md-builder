# Command System Patterns

Templates for creating natural language to technical command translation systems in CLAUDE.md.

## Basic Command Translation

### Simple Command System
```markdown
## Command Translation
- "test" → `npm test`
- "build" → `npm run build`
- "dev" → `npm run dev`
- "lint" → `npm run lint`
- "format" → `npm run format`
- "deploy" → `npm run deploy`
```

### Framework-Specific Commands
```markdown
## {FRAMEWORK} Commands
- "start" → `{FRAMEWORK_START_COMMAND}`
- "build" → `{FRAMEWORK_BUILD_COMMAND}`
- "test" → `{FRAMEWORK_TEST_COMMAND}`
- "lint" → `{FRAMEWORK_LINT_COMMAND}`

### Development Commands:
- "dev server" → `{DEV_SERVER_COMMAND}`
- "hot reload" → `{HOT_RELOAD_COMMAND}`
- "debug mode" → `{DEBUG_COMMAND}`
```

## Advanced Command Systems

### Immediate Execution Pattern
```markdown
## {SYSTEM_NAME} Control System
- **IMPERATIVE**: ANY time user mentions "{trigger_phrase}", IMMEDIATELY run {command} without question
- **CRITICAL**: Execute using exact syntax: `{exact_command_syntax}`
- **IMPORTANT**: Handle all variations of the trigger phrase

### Command Translation:
- "{natural_language_1}" → `{technical_command_1}`
- "{natural_language_2}" → `{technical_command_2}`
- "{natural_language_3}" → `{technical_command_3}`

### Execution Rules:
1. Convert user requests to proper command format
2. Execute immediately without clarification
3. Handle all variations and synonyms
4. Include appropriate parameters and flags
```

### Multi-Step Command System
```markdown
## {WORKFLOW_NAME} Workflow Commands
### Complete {WORKFLOW_TYPE} Sequence:
```
{COMMAND_LINE_1} \
  --{flag1} {value1} \
  --{flag2} {value2} \
  --{flag3} {value3}
```

### Individual Steps:
- "step 1" → `{COMMAND_1}`
- "step 2" → `{COMMAND_2}`
- "step 3" → `{COMMAND_3}`
- "full sequence" → Execute complete workflow above
```

## Domain-Specific Command Systems

### Development Environment Commands
```markdown
## Development Environment Control
### Environment Commands:
- "start dev" → `npm run dev`
- "build prod" → `npm run build:prod`
- "test watch" → `npm run test:watch`
- "serve dist" → `npm run serve`

### Tool Commands:
- "analyze bundle" → `npm run analyze`
- "check types" → `npm run type-check`
- "update deps" → `npm run update-deps`
- "clean build" → `npm run clean && npm run build`
```

### Testing Command System
```markdown
## Testing Command System
### Test Execution:
- "test all" → `npm test`
- "test unit" → `npm run test:unit`
- "test integration" → `npm run test:integration`
- "test e2e" → `npm run test:e2e`

### Test Coverage:
- "coverage" → `npm run test:coverage`
- "coverage report" → `npm run coverage:report`
- "coverage open" → `npm run coverage:open`

### Test Development:
- "test watch" → `npm run test:watch`
- "test debug" → `npm run test:debug`
- "test update" → `npm run test:update-snapshots`
```

### Deployment Command System
```markdown
## Deployment Command System
### Environment Deployment:
- "deploy dev" → `npm run deploy:dev`
- "deploy staging" → `npm run deploy:staging` 
- "deploy prod" → `npm run deploy:prod`

### Deployment Verification:
- "verify deploy" → `npm run deploy:verify`
- "health check" → `npm run health-check`
- "rollback" → `npm run deploy:rollback`

### Deployment Preparation:
- "pre-deploy" → `npm run pre-deploy`
- "build deploy" → `npm run build:deploy`
- "validate deploy" → `npm run validate:deploy`
```

## Scripting and Automation Commands

### Bash Script Integration
```markdown
## {TOOL_NAME} Script Commands
### Tool Control:
- "switch to {tool}" → `bash "/path/script.sh" --switch-tool {tool}`
- "take screenshot" → `bash "/path/script.sh" --screenshot`
- "preview tool" → `bash "/path/script.sh" --tool-preview true`

### Automation Sequences:
- "full cycle" → `bash "/path/script.sh" --full-cycle`
- "test sequence" → `bash "/path/script.sh" --test-mode`
- "demo mode" → `bash "/path/script.sh" --demo`
```

### Complex Script Workflow
```markdown
## {SYSTEM_NAME} Automation
### Complete Workflow Command:
```
bash "/path/automation.sh" \
  --enable-feature \
  --environment {env} \
  --delay 2 \
  --verify-status \
  --delay 3 \
  --execute-sequence tool1,tool2,tool3:5
```

### Individual Operations:
- "enable feature" → `bash "/path/script.sh" --enable-feature`
- "set environment {env}" → `bash "/path/script.sh" --environment {env}`
- "verify status" → `bash "/path/script.sh" --verify-status`
- "run sequence" → `bash "/path/script.sh" --execute-sequence`
```

## Error Handling and Validation

### Command Validation Pattern
```markdown
## Command Validation System
### Validation Rules:
- **IMPERATIVE**: Validate command syntax before execution
- **CRITICAL**: Check for required parameters and flags
- **IMPORTANT**: Provide helpful error messages for invalid commands

### Error Handling:
- Invalid command → Show available commands list
- Missing parameters → Request specific parameter values
- Permission errors → Explain access requirements
- Execution failures → Provide troubleshooting steps
```

### Fallback Command System
```markdown
## Command Fallback System
### Primary Commands:
- "{primary_trigger}" → `{primary_command}`

### Fallback Commands:
- "{alternative_trigger}" → `{primary_command}` (same as primary)
- "{synonym_trigger}" → `{primary_command}` (same as primary)

### Unknown Command Handling:
- Unrecognized commands → Display available command list
- Partial matches → Suggest closest matching commands
- Invalid syntax → Provide correct syntax examples
```

## Context-Aware Commands

### File-Context Commands
```markdown
## File-Aware Command System
### File Type Commands:
- "test this file" → `{TEST_COMMAND} {current_file}`
- "lint this file" → `{LINT_COMMAND} {current_file}`
- "format this file" → `{FORMAT_COMMAND} {current_file}`

### Directory Commands:
- "test directory" → `{TEST_COMMAND} {current_directory}`
- "build project" → `{BUILD_COMMAND}` (from project root)
- "install here" → `{INSTALL_COMMAND}` (in current directory)
```

### State-Aware Commands
```markdown
## State-Aware Command System
### Development State Commands:
- "continue development" → Resume last development task
- "switch to testing" → Execute test preparation workflow
- "prepare deployment" → Execute deployment preparation sequence

### Project State Commands:
- "project status" → `git status && npm run health-check`
- "project health" → `npm run test && npm run lint`
- "project build" → `npm run clean && npm run build`
```

## Advanced Integration Patterns

### Parameterized Commands
```markdown
## Parameterized Command System
### Template Commands:
- "deploy to {environment}" → `npm run deploy:{environment}`
- "test {component}" → `npm run test -- --testNamePattern={component}`
- "build for {target}" → `npm run build:{target}`

### Dynamic Parameter Handling:
- Extract parameters from natural language
- Validate parameter values against allowed options
- Provide parameter suggestions for incomplete commands
```

### Conditional Command Execution
```markdown
## Conditional Command System
### Environment-Based Commands:
- "deploy" → Execute `{DEV_DEPLOY}` if in development, `{PROD_DEPLOY}` if in production
- "test" → Execute `{UNIT_TESTS}` for small changes, `{FULL_TESTS}` for major changes

### Context-Based Commands:
- "format" → Format current file if single file context, format project if multiple files
- "lint" → Lint current file or directory based on current context
```

## Usage Guidelines

### Command System Design
1. **Start Simple**: Begin with basic command translations
2. **Add Complexity Gradually**: Introduce advanced features as needed
3. **Test Thoroughly**: Validate all command variations work correctly
4. **Document Clearly**: Provide examples and usage guidelines

### Best Practices
- Use consistent naming patterns for similar commands
- Include both short and descriptive command variations
- Provide helpful error messages and suggestions
- Test commands in actual development environment
- Keep command mappings up to date with project changes

### Common Pitfalls
- Avoid conflicting command names or triggers
- Don't make commands too complex or hard to remember
- Ensure commands work in the actual project environment
- Keep command documentation synchronized with implementation