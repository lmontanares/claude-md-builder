# Token Optimization Patterns for CLAUDE.md

## Overview
Cost-aware patterns for creating efficient CLAUDE.md files that minimize token usage while maximizing instruction effectiveness and maintaining Claude Code performance.

**Reference**: Combine with @patterns/comprehensive-template.md for full-featured setups, @patterns/team-collaboration.md for multi-user efficiency, and @patterns/validation.md for cost-effective validation strategies.

## Core Optimization Principles

### Token Efficiency Framework
```markdown
## Token Optimization Rules
- **IMPERATIVE**: Prioritize high-impact instructions over verbose explanations
- **CRITICAL**: Use condensed syntax without sacrificing clarity
- **IMPORTANT**: Front-load essential context to prevent token waste on discovery
```

### Condensed Instruction Pattern
```markdown
# My name is {PROJECT}_AI

## Core Rules
- **IMPERATIVE**: {PRIMARY_BEHAVIOR}
- **CRITICAL**: {SECONDARY_BEHAVIOR}
- **IMPORTANT**: {TERTIARY_BEHAVIOR}

## Commands
- "{TRIGGER}" → `{COMMAND}`
- "{TRIGGER2}" → `{COMMAND2}`

## Context
@{ESSENTIAL_FILE1} @{ESSENTIAL_FILE2}
```

## High-Impact Instruction Patterns

### Essential-Only Context Loading
```markdown
## Context Strategy
**Front-load Critical Files**:
@package.json for deps and scripts
@tsconfig.json for type rules
@README.md for project overview

**On-Demand Context**:
- Code patterns: Use Glob tool when needed
- Documentation: Reference specific sections only
- Dependencies: Check package.json before assumptions
```

### Compressed Command Translation
```markdown
## Command Shortcuts
- "test" → `npm test`
- "build" → `npm run build`
- "dev" → `npm run dev`
- "lint" → `npm run lint`
- "fmt" → `npm run format`
- "check" → `npm run typecheck`
```

### Efficient Validation Points
```markdown
## Checkpoints
1. **Identity**: "What is my name?" → {EXPECTED_NAME}
2. **Commands**: Test "build" → Should run npm run build
3. **Context**: Verify essential files are accessible
```

## Token-Saving Techniques

### Condensed Architecture Documentation
```markdown
## Architecture
**Stack**: {FRONTEND}/{BACKEND}/{DB}
**Pattern**: {ARCH_PATTERN}
**Structure**: 
```
src/{domain}/{layer}/{feature}
tests/{type}/{feature}
docs/{category}
```
**Rules**: Follow existing patterns, test everything, document changes
```

### Abbreviated Workflow Instructions
```markdown
## Workflow
**Dev**: Make changes → test → lint → commit
**Deploy**: build → test → deploy to {ENV}
**Review**: Code review required for main branch
**Quality**: {COVERAGE}% test coverage minimum
```

### Compact Error Handling
```markdown
## Error Strategy
**API**: Centralized error handling via {ERROR_SERVICE}
**Validation**: Client + server validation required
**Logging**: Use {LOGGER} with level {LOG_LEVEL}
**Monitoring**: {MONITORING_TOOL} integration required
```

## Memory Hierarchy Optimization

### Strategic Import Usage
```markdown
# Lightweight Main CLAUDE.md
@core-rules.md for essential project behavior
@commands.md for command translations
@~/.claude/personal-prefs.md for individual settings

## Context-Specific Imports
Development tasks: @dev-patterns.md
Testing tasks: @test-patterns.md
Deployment tasks: @deploy-patterns.md
```

### Conditional Context Loading
```markdown
## Smart Context Loading
- **Always Available**: @package.json @README.md
- **Development Mode**: @dev-patterns.md when coding
- **Testing Mode**: @test-patterns.md when testing
- **Deployment Mode**: @deploy-patterns.md when deploying
```

## Efficiency-Focused Templates

### Minimal Viable CLAUDE.md
```markdown
# My name is {PROJECT}_AI

## Rules
- **IMPERATIVE**: Follow {MAIN_PATTERN}
- **CRITICAL**: Run {TEST_COMMAND} after changes
- **IMPORTANT**: Use existing patterns in codebase

## Commands
- "test" → `{TEST_CMD}`
- "build" → `{BUILD_CMD}`
- "dev" → `{DEV_CMD}`

## Context
@package.json @README.md

## Validation
"What is my name?" → {PROJECT}_AI
```

### Domain-Specific Optimization
```markdown
# {DOMAIN} Specialist

## {DOMAIN} Rules
- **IMPERATIVE**: {PRIMARY_DOMAIN_RULE}
- **CRITICAL**: {SECONDARY_DOMAIN_RULE}

## {DOMAIN} Commands
{COMPACT_COMMAND_LIST}

## {DOMAIN} Context
@{DOMAIN_CONFIG_FILE}
@{DOMAIN_DOCS_FILE}
```

### Team-Optimized Pattern
```markdown
# Team {TEAM_NAME} Assistant

## Shared Standards
- **IMPERATIVE**: Follow @team-standards.md
- **CRITICAL**: Use @code-conventions.md
- **IMPORTANT**: Document in @team-docs.md

## Personal Overrides
@~/.claude/team-{TEAM_NAME}-prefs.md

## Quick Commands
{ESSENTIAL_TEAM_COMMANDS_ONLY}
```

## Performance Monitoring Patterns

### Token Usage Tracking
```markdown
## Performance Metrics
- **Target Context Size**: Under {TOKEN_LIMIT} tokens
- **Essential Instructions**: {CORE_INSTRUCTION_COUNT} commands
- **Import Count**: Maximum {IMPORT_LIMIT} files
- **Validation Time**: Under {VALIDATION_TIME} seconds
```

### Efficiency Validation
```markdown
## Efficiency Checks
1. **Token Count**: Verify CLAUDE.md + imports under budget
2. **Response Speed**: Test common commands for quick execution
3. **Memory Load**: Monitor context window usage patterns
4. **Success Rate**: Track instruction adherence percentage
```

### Optimization Metrics
```markdown
## Success Indicators
- **Fast Recognition**: Name/identity confirmed in <3 tokens
- **Quick Commands**: Common tasks execute without clarification
- **Efficient Discovery**: Essential context loaded proactively
- **Minimal Waste**: No redundant file reads or searches
```

## Advanced Optimization Strategies

### Context Window Management
```markdown
## Context Strategy
**Phase 1 (Essential)**: Core rules + commands + key files
**Phase 2 (On-Demand)**: Domain-specific patterns when needed
**Phase 3 (Deep Context)**: Full documentation only when required
```

### Adaptive Instruction Density
```markdown
## Instruction Density Levels
**High Density**: New projects or complex domains
**Medium Density**: Established projects with clear patterns  
**Low Density**: Simple projects or experienced team members
```

### Smart Import Patterns
```markdown
## Import Optimization
**Always Load**: @package.json @README.md @CHANGELOG.md
**Conditional Load**: @{ENV}-config.md based on deployment target
**Lazy Load**: @detailed-docs.md only when explicitly needed
```

## Cost-Benefit Analysis Patterns

### Instruction Value Assessment
```markdown
## Value-Based Prioritization
**High Value (Always Include)**:
- Core behavior rules
- Essential command translations
- Critical file references

**Medium Value (Conditional)**:
- Detailed architecture docs
- Extended command lists
- Optional workflow patterns

**Low Value (Exclude)**:
- Verbose explanations
- Redundant examples
- Historical context
```

### ROI-Focused Template Design
```markdown
## ROI Optimization
**High ROI Instructions**: Prevent common mistakes, speed up frequent tasks
**Medium ROI Instructions**: Improve code quality, reduce review cycles
**Low ROI Instructions**: Nice-to-have preferences, edge case handling
```

## Implementation Guidelines

### Step-by-Step Optimization
1. **Baseline Measurement**: Count tokens in current CLAUDE.md
2. **Priority Identification**: List must-have vs nice-to-have instructions
3. **Condensation Pass**: Compress verbose instructions without losing meaning
4. **Import Strategy**: Move secondary content to imported files
5. **Validation Test**: Verify optimized version maintains effectiveness

### Optimization Workflow
```markdown
## Optimization Process
1. **Audit Current Token Usage**: Measure total context size
2. **Identify High-Impact Instructions**: Core behaviors and commands
3. **Compress Secondary Content**: Use abbreviated patterns
4. **Implement Smart Imports**: Modular context loading
5. **Validate Performance**: Test effectiveness metrics
6. **Iterate Based on Usage**: Adjust based on real-world performance
```

### Maintenance Strategy
```markdown
## Ongoing Optimization
- **Monthly Reviews**: Check token usage and effectiveness
- **Usage Analytics**: Track which instructions are most/least used
- **Team Feedback**: Gather input on instruction clarity and usefulness
- **Performance Monitoring**: Watch for context window issues
```

This token optimization guide helps create CLAUDE.md files that deliver maximum value while minimizing cost and maintaining high performance across different project types and team sizes.