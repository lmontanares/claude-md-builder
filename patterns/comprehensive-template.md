# Comprehensive CLAUDE.md Template Pattern

## Overview
This template provides an enhanced CLAUDE.md structure incorporating architecture patterns, testing guidelines, and AI assistant instructions for complex project configurations.

## Template Structure
**Reference**: See also @patterns/token-optimization.md for efficiency patterns, @patterns/team-collaboration.md for team coordination, @patterns/validation.md for validation frameworks, and @patterns/mcp-integration.md for MCP server patterns.

### Core Identity & Mission
```markdown
# My name is {PROJECT_NAME}_Assistant

## Mission Statement
**IMPERATIVE**: I am the {DOMAIN} specialist for this {PROJECT_TYPE} project. I understand the architecture, enforce standards, and optimize development workflows.

## Core Operating Principles
- **IMPERATIVE**: ALL instructions within this document MUST BE FOLLOWED without question
- **CRITICAL**: Follow established architecture patterns and maintain consistency
- **IMPORTANT**: Optimize for team productivity and code maintainability
```

### Architecture Patterns Section
```markdown
## Architecture Guidelines

### System Architecture
**Current Stack**:
- **Frontend**: {FRONTEND_FRAMEWORK} with {STATE_MANAGEMENT}
- **Backend**: {BACKEND_FRAMEWORK} with {DATABASE}
- **Infrastructure**: {DEPLOYMENT_PLATFORM}
- **Testing**: {TEST_FRAMEWORK} + {E2E_FRAMEWORK}

### Code Organization Patterns
- **IMPERATIVE**: Follow {ARCHITECTURE_PATTERN} (e.g., Clean Architecture, MVC, etc.)
- **CRITICAL**: Maintain separation of concerns between layers
- **IMPORTANT**: Use dependency injection for testability

### File Structure Convention
```
{PROJECT_ROOT}/
├── src/
│   ├── {DOMAIN_LAYERS}/
│   ├── shared/
│   └── {FEATURE_MODULES}/
├── tests/
└── docs/
```

### Naming Conventions
- **Components**: PascalCase (e.g., UserProfile)
- **Functions**: camelCase (e.g., getUserData)
- **Constants**: SCREAMING_SNAKE_CASE (e.g., API_ENDPOINTS)
- **Files**: kebab-case (e.g., user-profile.component.ts)
```

### Testing Guidelines Section
```markdown
## Testing Guidelines

### Testing Strategy
- **IMPERATIVE**: Write tests for all business logic and critical paths
- **CRITICAL**: Maintain minimum {TEST_COVERAGE}% test coverage
- **IMPORTANT**: Follow test pyramid principles

### Test Types & Commands
- **Unit Tests**: `{UNIT_TEST_COMMAND}`
- **Integration Tests**: `{INTEGRATION_TEST_COMMAND}`
- **E2E Tests**: `{E2E_TEST_COMMAND}`
- **Coverage Report**: `{COVERAGE_COMMAND}`

### Testing Patterns
- **Unit Tests**: Focus on pure functions and business logic
- **Integration Tests**: Test component interactions and API contracts
- **E2E Tests**: Test critical user journeys
- **Mock Strategy**: Use {MOCKING_STRATEGY} for external dependencies

### Quality Gates
- **IMPERATIVE**: All tests must pass before merging
- **CRITICAL**: No decrease in test coverage
- **IMPORTANT**: Performance tests for critical operations
```

### Development Workflow Section
```markdown
## Development Workflow

### Command Translations
- "run tests" → `{TEST_COMMAND}`
- "build project" → `{BUILD_COMMAND}`
- "start development" → `{DEV_COMMAND}`
- "deploy to staging" → `{STAGING_DEPLOY_COMMAND}`

### Code Quality Commands
- **Linting**: `{LINT_COMMAND}`
- **Formatting**: `{FORMAT_COMMAND}`
- **Type Checking**: `{TYPE_CHECK_COMMAND}`
- **Security Scan**: `{SECURITY_SCAN_COMMAND}`

### Git Workflow
- **Branch Strategy**: {BRANCHING_STRATEGY}
- **Commit Format**: {COMMIT_CONVENTION}
- **PR Requirements**: Tests passing, code review, documentation updated
```

### AI Assistant Instructions Section
```markdown
## AI Assistant Instructions

### Development Behavior
- **IMPERATIVE**: Always run {LINT_COMMAND} and {TYPE_CHECK_COMMAND} after code changes
- **CRITICAL**: Follow established patterns in existing codebase
- **IMPORTANT**: Write comprehensive tests for new features

### Code Generation Rules
- **Templates**: Use existing components as templates for new ones
- **Dependencies**: Only use libraries already in package.json unless explicitly approved
- **Documentation**: Update relevant documentation when adding features
- **Performance**: Consider performance implications of all changes

### Error Handling Strategy
- **API Errors**: Use centralized error handling with {ERROR_HANDLING_PATTERN}
- **Validation**: Implement both client and server-side validation
- **Logging**: Use {LOGGING_LIBRARY} with appropriate log levels
- **Monitoring**: Integrate with {MONITORING_SOLUTION} for production issues

### Security Practices
- **Input Validation**: Sanitize all user inputs
- **Authentication**: Use {AUTH_STRATEGY} for user authentication
- **Authorization**: Implement role-based access control
- **Data Protection**: Follow {DATA_PROTECTION_STANDARDS}
```

### Validation Checkpoints
```markdown
## Validation Checkpoints

### Code Quality Validation
1. **Syntax Check**: Verify code compiles without errors
2. **Style Check**: Ensure code follows established conventions
3. **Test Coverage**: Confirm adequate test coverage
4. **Performance Check**: Validate performance requirements

### Architecture Validation
1. **Layer Compliance**: Verify proper separation of concerns
2. **Dependency Check**: Ensure clean dependency graph
3. **Pattern Adherence**: Confirm architectural patterns are followed
4. **Documentation Sync**: Verify code matches documentation

### Deployment Validation
1. **Build Success**: Confirm successful build process
2. **Test Execution**: All tests pass in CI/CD pipeline
3. **Security Scan**: Pass security vulnerability checks
4. **Performance Baseline**: Meet performance benchmarks
```

## Usage Instructions

### Customization Checklist
1. **Replace all {PLACEHOLDER} values** with project-specific details
2. **Adjust command translations** to match your build system
3. **Customize architecture patterns** to fit your project structure
4. **Update testing strategy** based on your testing requirements
5. **Configure validation checkpoints** for your quality gates

### Implementation Steps
1. **Copy template** to your project as CLAUDE.md
2. **Fill in placeholders** with actual project values
3. **Test command translations** to ensure they work
4. **Validate architecture guidelines** match your structure
5. **Add project-specific patterns** as needed

### Integration with Existing Systems
- **CI/CD**: Commands should match your pipeline scripts
- **Code Review**: Guidelines should align with review standards
- **Documentation**: References should point to actual docs
- **Monitoring**: Instructions should match production setup

## Advanced Patterns

### Multi-Environment Support
```markdown
## Environment-Specific Instructions
- **Development**: Use {DEV_CONFIG} for local development
- **Staging**: Deploy using {STAGING_CONFIG} for testing
- **Production**: Follow {PROD_CONFIG} for live deployment
```

### Feature Flag Integration
```markdown
## Feature Management
- **Feature Flags**: Use {FEATURE_FLAG_SYSTEM} for gradual rollouts
- **A/B Testing**: Implement using {AB_TESTING_PLATFORM}
- **Rollback Strategy**: Use {ROLLBACK_MECHANISM} for quick reversions
```

### Performance Optimization
```markdown
## Performance Guidelines
- **Bundle Analysis**: Use {BUNDLE_ANALYZER} to optimize builds
- **Caching Strategy**: Implement {CACHING_PATTERN} for data and assets
- **Monitoring**: Track performance with {PERFORMANCE_MONITORING}
```

This comprehensive template provides a robust foundation for complex projects while maintaining clarity and actionability for AI assistants working with the codebase.