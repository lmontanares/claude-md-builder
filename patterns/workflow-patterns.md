# Workflow Execution Patterns

Templates for parallel task execution and systematic workflows in CLAUDE.md configurations.

## Parallel Task Patterns

### Basic Parallel Workflow Template
```markdown
## {TASK_TYPE} Workflow
### Priority Rules:
- **IMPERATIVE**: Launch parallel Tasks immediately upon request
- **CRITICAL**: Skip asking for clarification unless absolutely necessary
- **IMPORTANT**: Use parallel execution for efficiency

### {N}-Parallel Task Workflow:
1. **{Task1}**: {Description and files}
2. **{Task2}**: {Description and files}
3. **{Task3}**: {Description and files}
4. **{Task4}**: {Description and files}
5. **{Task5}**: {Description and files}

### Execution Guidelines:
- Each task handles ONLY specified files
- Strip comments when reading code for analysis
- Use MultiEdit for multiple edits to same file
```

### Feature Development Workflow
```markdown
## Feature Development Workflow
### Priority Rules:
- **IMPERATIVE**: Launch 7-parallel-Task immediately upon feature requests
- **CRITICAL**: No clarification needed for standard features
- **IMPORTANT**: Follow established project patterns

### 7-Parallel Feature Development:
1. **Component**: Create main component file with core functionality
2. **Styles**: Create component styles and CSS files
3. **Tests**: Create comprehensive test files and test cases
4. **Types**: Create TypeScript definitions and interfaces
5. **Hooks**: Create custom hooks and utility functions
6. **Integration**: Update routing, imports, and exports
7. **Documentation**: Update README, docs, and configuration files

### Execution Guidelines:
- Each task targets specific file types
- Maintain consistency with existing codebase patterns
- Use existing components as templates for new ones
```

### Bug Fix Workflow
```markdown
## Bug Fix Workflow
### Priority Rules:
- **IMPERATIVE**: Analyze issue systematically before fixing
- **CRITICAL**: Write tests to reproduce bug before fixing
- **IMPORTANT**: Validate fix doesn't break existing functionality

### 5-Parallel Bug Fix Process:
1. **Analysis**: Identify root cause and affected components
2. **Reproduction**: Create tests that demonstrate the bug
3. **Fix**: Implement minimal fix targeting root cause
4. **Testing**: Update and run all relevant tests
5. **Validation**: Verify fix works and doesn't cause regressions

### Execution Guidelines:
- Start with understanding the problem completely
- Write failing tests before implementing fixes
- Keep fixes minimal and targeted
```

## Workflow Integration Patterns

### Task Tool Integration
```markdown
## Task Tool Workflow Integration
### Automatic Task Launching:
- **IMPERATIVE**: Use Task tool for any multi-step processes
- **CRITICAL**: Launch tasks in parallel when possible
- **IMPORTANT**: Coordinate between tasks for complex workflows

### Task Coordination Rules:
1. **Independent Tasks**: Run completely in parallel
2. **Dependent Tasks**: Use sequential execution with handoffs
3. **Mixed Workflows**: Parallel for independent parts, sequential for dependencies

### Task Efficiency:
- Strip comments from code when analyzing
- Focus each task on specific file types or concerns
- Combine small related updates in single tasks
```

### Thinking Mode Integration
```markdown
## Complex Analysis Workflow
### When to Use Thinking Mode:
- **Complex Requirements**: Multi-step analysis needed
- **Architecture Decisions**: Significant design choices
- **Problem Solving**: Root cause analysis required

### Thinking + Task Integration:
1. **Analysis Phase**: Use thinking mode to break down complex requirements
2. **Planning Phase**: Design implementation strategy and task breakdown
3. **Execution Phase**: Launch parallel tasks based on analysis
4. **Validation Phase**: Review results and ensure completeness

### Integration Rules:
- Use thinking mode for planning, Task tool for execution
- Combine analytical thinking with systematic implementation
- Validate complex decisions before proceeding
```

## Domain-Specific Workflows

### Web Development Workflow
```markdown
## Web Component Development
### 8-Parallel Web Development:
1. **Component**: Main React/Vue component with props and state
2. **Styles**: CSS/SCSS styles with responsive design
3. **Tests**: Component tests and integration tests
4. **Storybook**: Stories for component documentation
5. **Types**: TypeScript interfaces and prop types
6. **Hooks**: Custom hooks for component logic
7. **Integration**: Add to app routing and component library
8. **Documentation**: Update style guide and README

### Execution Rules:
- Follow existing component patterns
- Use design system tokens for styling
- Write comprehensive test coverage
```

### API Development Workflow
```markdown
## API Endpoint Development
### 6-Parallel API Development:
1. **Route**: Define endpoint route and HTTP methods
2. **Controller**: Implement business logic and validation
3. **Model**: Create or update data models and schemas
4. **Tests**: Unit tests and integration tests
5. **Documentation**: API docs and OpenAPI specs
6. **Integration**: Update routing and middleware

### Execution Rules:
- Validate all inputs and sanitize data
- Follow RESTful conventions
- Include proper error handling
```

### DevOps Workflow
```markdown
## Deployment Pipeline Workflow
### 5-Parallel DevOps Workflow:
1. **Config**: Update deployment configuration files
2. **Scripts**: Create or update deployment scripts
3. **Tests**: Add deployment validation tests
4. **Documentation**: Update deployment procedures
5. **Monitoring**: Configure monitoring and alerts

### Execution Rules:
- Test in staging environment first
- Include rollback procedures
- Validate all configurations
```

## Advanced Workflow Patterns

### Multi-File Output Workflow
```markdown
## Multi-File Generation Workflow
### JSON Output Pattern:
1. **Structure Design**: Plan file organization and relationships
2. **Content Generation**: Create all file contents
3. **JSON Compilation**: Organize into structured JSON output
4. **Processing Script**: Create script to write files from JSON
5. **Validation**: Verify all files are created correctly

### JSON Output Format:
```json
{
  "files": [
    {
      "path": "src/components/NewComponent.tsx",
      "content": "// Component content here"
    },
    {
      "path": "src/tests/NewComponent.test.tsx", 
      "content": "// Test content here"
    }
  ]
}
```

### Processing Command:
```bash
echo '$JSON_OUTPUT' | jq -r '.files[] | "echo \(.content | @base64d) > \(.path)"' | bash
```
```

### Context Optimization Workflow
```markdown
## Context-Efficient Workflow
### Optimization Rules:
- **IMPERATIVE**: Strip all comments when reading code for analysis
- **CRITICAL**: Each task handles ONLY specified files or file types
- **IMPORTANT**: Combine small updates to prevent over-splitting

### Context Management:
1. **Selective Reading**: Target specific patterns rather than full files
2. **Focused Tasks**: Each task has clear, limited scope
3. **Efficient Coordination**: Minimize cross-task dependencies
4. **Strategic Chunking**: Handle large files through targeted sections

### Token Efficiency:
- Remove verbose content during analysis phases
- Focus on functional structure over implementation details
- Prioritize reusable patterns over specific examples
```

### Quality Assurance Workflow
```markdown
## QA Integration Workflow
### 4-Parallel Quality Workflow:
1. **Code Quality**: Run linting, formatting, and type checking
2. **Testing**: Execute unit tests, integration tests, and coverage
3. **Security**: Run security scans and vulnerability checks
4. **Performance**: Analyze performance impact and optimization

### Quality Gates:
- All linting and type checks must pass
- Test coverage must meet minimum threshold
- No security vulnerabilities in dependencies
- Performance benchmarks must be maintained
```

## Usage Guidelines

### Workflow Selection
- **Simple Tasks**: Use basic parallel patterns
- **Feature Development**: Use 7-8 parallel task workflows
- **Bug Fixes**: Use focused 5-task workflow
- **Complex Analysis**: Integrate thinking mode with task execution

### Customization Tips
- Adjust task count based on complexity
- Modify task descriptions for your domain
- Add project-specific validation steps
- Include team-specific quality gates

### Best Practices
- Plan task dependencies before execution
- Keep tasks focused and independent when possible
- Use consistent file organization patterns
- Validate workflow effectiveness regularly