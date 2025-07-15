# Team Collaboration Patterns for CLAUDE.md

## Overview
Patterns for creating CLAUDE.md configurations that enable effective team collaboration, shared standards, and seamless handoff protocols across different team members and project phases.

**Reference**: Integrate with @patterns/comprehensive-template.md for full team setups, @patterns/token-optimization.md for cost-effective team configurations, @patterns/validation.md for team consistency validation, and @patterns/mcp-integration.md for team MCP coordination.

## Core Collaboration Principles

### Team-First Design Philosophy
```markdown
## Team Collaboration Rules
- **IMPERATIVE**: Shared standards override individual preferences
- **CRITICAL**: Maintain consistency across all team member interactions
- **IMPORTANT**: Document decisions and patterns for team knowledge sharing
```

### Layered Configuration Strategy
```markdown
# Team {TEAM_NAME} Standards

## Shared Foundation
@team-standards/core-rules.md for universal team behaviors
@team-standards/code-conventions.md for coding standards
@team-standards/workflow-patterns.md for process guidelines

## Project-Specific Layer
@project-config/architecture.md for this project's specific patterns
@project-config/domain-rules.md for business logic guidelines

## Individual Customization
@~/.claude/team-{TEAM_NAME}-personal.md for personal preferences within team standards
```

## Shared Standards Patterns

### Universal Team Behavior Template
```markdown
# Team {TEAM_NAME} Assistant

## Team Identity
- **IMPERATIVE**: I follow {TEAM_NAME} development standards without deviation
- **CRITICAL**: I maintain consistency with team patterns and conventions
- **IMPORTANT**: I prioritize team productivity and code maintainability

## Code Standards
**Language**: {PRIMARY_LANGUAGE} following {STYLE_GUIDE}
**Framework**: {FRAMEWORK} with {ARCHITECTURE_PATTERN}
**Testing**: {TEST_FRAMEWORK} with minimum {COVERAGE}% coverage
**Documentation**: {DOCUMENTATION_STANDARD} for all public APIs

## Workflow Standards
**Git Strategy**: {BRANCHING_STRATEGY}
**Code Review**: {REVIEW_REQUIREMENTS}
**Deployment**: {DEPLOYMENT_PROCESS}
**Quality Gates**: {QUALITY_REQUIREMENTS}
```

### Multi-Role Support Pattern
```markdown
## Role-Specific Behavior
**For Developers**:
- **IMPERATIVE**: Follow established patterns in existing codebase
- **CRITICAL**: Write tests for all new features
- **IMPORTANT**: Update documentation for API changes

**For DevOps Engineers**:
- **IMPERATIVE**: Use approved infrastructure patterns
- **CRITICAL**: Validate security configurations
- **IMPORTANT**: Monitor deployment metrics

**For QA Engineers**:
- **IMPERATIVE**: Follow test strategy guidelines
- **CRITICAL**: Validate test coverage requirements
- **IMPORTANT**: Document test scenarios and edge cases
```

### Domain Expertise Distribution
```markdown
## Domain Expert Patterns
**Frontend Specialists**:
@team-standards/frontend-patterns.md
@team-standards/ui-component-library.md

**Backend Specialists**:
@team-standards/backend-patterns.md
@team-standards/api-design-guidelines.md

**Full-Stack Generalists**:
@team-standards/full-stack-patterns.md
@team-standards/integration-patterns.md
```

## Handoff Protocol Patterns

### Context Transfer Template
```markdown
## Project Handoff Context
**Current State**: {CURRENT_PROJECT_PHASE}
**Active Features**: {FEATURES_IN_DEVELOPMENT}
**Known Issues**: {OUTSTANDING_ISSUES}
**Dependencies**: {EXTERNAL_DEPENDENCIES}
**Deployment Status**: {DEPLOYMENT_STATE}

## Immediate Priorities
1. **CRITICAL**: {URGENT_TASK_1}
2. **IMPORTANT**: {URGENT_TASK_2}
3. **MEDIUM**: {MEDIUM_PRIORITY_TASK}

## Knowledge Transfer Points
**Architecture Decisions**: @docs/architecture-decisions.md
**Business Logic**: @docs/domain-model.md
**Integration Points**: @docs/external-integrations.md
**Troubleshooting**: @docs/troubleshooting-guide.md
```

### Cross-Team Communication Pattern
```markdown
## Team Interface Protocols
**Backend Team Communication**:
- API contract changes: Use @api-contracts/ for coordination
- Database changes: Follow @db-migration-standards.md
- Service dependencies: Document in @service-dependencies.md

**Frontend Team Communication**:
- Component API changes: Update @component-library/
- Design system updates: Follow @design-system-guidelines.md
- User experience flows: Document in @ux-patterns/

**DevOps Team Communication**:
- Infrastructure changes: Use @infrastructure/ for coordination
- Deployment requirements: Follow @deployment-requirements.md
- Monitoring needs: Document in @monitoring-requirements.md
```

### Knowledge Sharing Template
```markdown
## Team Knowledge Base
**Decision Log**: @team-decisions/ for architectural and process decisions
**Pattern Library**: @team-patterns/ for reusable code and configuration patterns
**Troubleshooting Guide**: @team-troubleshooting/ for common issues and solutions
**Onboarding Guide**: @team-onboarding/ for new team member integration

## Learning Objectives
**New Team Members**: Focus on @team-onboarding/ and @core-patterns/
**Cross-Training**: Use @cross-team-patterns/ for multi-discipline understanding
**Skill Development**: Follow @learning-paths/ for structured skill progression
```

## Consistency Enforcement Patterns

### Code Style Harmonization
```markdown
## Universal Code Standards
**Formatting**: Use {FORMATTER_TOOL} with @team-config/{FORMATTER_CONFIG}
**Linting**: Use {LINTER_TOOL} with @team-config/{LINTER_CONFIG}
**Type Checking**: {TYPE_CHECKER} with @team-config/{TYPE_CONFIG}

## Enforcement Commands
- "format all" → `{TEAM_FORMAT_COMMAND}`
- "lint project" → `{TEAM_LINT_COMMAND}`
- "type check" → `{TEAM_TYPE_CHECK_COMMAND}`
- "run all checks" → `{TEAM_QUALITY_COMMAND}`
```

### Architecture Consistency Pattern
```markdown
## Architectural Constraints
**Layer Dependencies**: {DEPENDENCY_RULES}
**Module Boundaries**: {MODULE_BOUNDARIES}
**External Integrations**: {INTEGRATION_PATTERNS}
**Data Flow**: {DATA_FLOW_CONSTRAINTS}

## Validation Commands
- "validate architecture" → `{ARCHITECTURE_VALIDATION_COMMAND}`
- "check dependencies" → `{DEPENDENCY_CHECK_COMMAND}`
- "verify patterns" → `{PATTERN_VALIDATION_COMMAND}`
```

### Process Standardization
```markdown
## Standard Workflows
**Feature Development**:
1. Create feature branch from {BASE_BRANCH}
2. Implement feature following @team-patterns/
3. Write tests using @test-patterns/
4. Submit PR with @pr-template/
5. Address review feedback
6. Merge after approval

**Bug Fixes**:
1. Reproduce issue following @debug-patterns/
2. Create fix following @hotfix-patterns/
3. Test thoroughly using @regression-patterns/
4. Deploy using @hotfix-deployment/
```

## Multi-Environment Coordination

### Environment-Specific Team Patterns
```markdown
## Environment Coordination
**Development**: Individual developer environments with shared @dev-standards/
**Staging**: Shared staging environment with @staging-protocols/
**Production**: Production environment with @production-standards/

## Environment Transitions
**Dev → Staging**: Follow @dev-to-staging-checklist/
**Staging → Production**: Follow @staging-to-prod-checklist/
**Rollback Procedures**: Use @rollback-protocols/
```

### Release Management Pattern
```markdown
## Team Release Process
**Release Planning**: Use @release-planning/ for coordination
**Feature Freeze**: Follow @feature-freeze-protocols/
**Release Testing**: Use @release-testing-patterns/
**Deployment Coordination**: Follow @deployment-coordination/
**Post-Release**: Use @post-release-protocols/

## Release Roles
**Release Manager**: @release-manager-responsibilities/
**QA Lead**: @qa-release-responsibilities/
**DevOps Lead**: @devops-release-responsibilities/
**Product Owner**: @product-release-responsibilities/
```

## Conflict Resolution Patterns

### Decision Making Framework
```markdown
## Team Decision Patterns
**Technical Decisions**: Use @technical-decision-framework/
**Process Decisions**: Use @process-decision-framework/
**Tool Selection**: Use @tool-selection-criteria/

## Escalation Paths
**Code Review Disputes**: @code-review-escalation/
**Architecture Disagreements**: @architecture-escalation/
**Process Conflicts**: @process-conflict-resolution/
```

### Consensus Building Template
```markdown
## Consensus Mechanisms
**RFC Process**: Use @rfc-templates/ for significant changes
**Voting Protocols**: Follow @team-voting-procedures/
**Pilot Programs**: Use @pilot-program-guidelines/
**Feedback Collection**: Use @feedback-collection-patterns/
```

## Advanced Collaboration Patterns

### Distributed Team Support
```markdown
## Remote Team Coordination
**Async Communication**: Use @async-communication-patterns/
**Documentation Standards**: Follow @remote-documentation-standards/
**Meeting Protocols**: Use @remote-meeting-guidelines/
**Time Zone Coordination**: Follow @timezone-coordination-patterns/
```

### Skill Development Coordination
```markdown
## Team Learning Patterns
**Mentorship Programs**: Use @mentorship-guidelines/
**Knowledge Sharing Sessions**: Follow @knowledge-sharing-protocols/
**Cross-Training**: Use @cross-training-patterns/
**Certification Tracking**: Follow @certification-standards/
```

### Quality Assurance Integration
```markdown
## QA Integration Patterns
**Test Strategy Alignment**: Use @qa-integration-patterns/
**Automated Testing**: Follow @automated-testing-standards/
**Manual Testing**: Use @manual-testing-protocols/
**Quality Metrics**: Track using @quality-metrics-standards/
```

## Implementation Guide

### Team Onboarding Checklist
1. **Setup Team Configuration**: Install @team-config/ in home directory
2. **Import Team Standards**: Add team imports to project CLAUDE.md
3. **Configure Personal Overrides**: Setup @~/.claude/team-{TEAM_NAME}-personal.md
4. **Validate Integration**: Test team command translations work
5. **Review Team Patterns**: Study @team-patterns/ library
6. **Practice Workflows**: Complete @onboarding-exercises/

### Maintenance Responsibilities
```markdown
## Team CLAUDE.md Maintenance
**Team Lead**: Maintain @team-standards/ and coordinate updates
**Senior Developers**: Contribute to @team-patterns/ and review changes
**All Members**: Suggest improvements and report issues
**DevOps**: Maintain deployment and infrastructure patterns
**QA**: Maintain testing patterns and quality standards
```

### Migration Strategy
```markdown
## Team Migration Process
1. **Assessment**: Evaluate current individual CLAUDE.md files
2. **Common Patterns**: Identify shared patterns across team
3. **Standards Definition**: Create team standards from common patterns
4. **Gradual Migration**: Move individual patterns to team standards
5. **Validation**: Test team standards across all projects
6. **Full Adoption**: Complete migration and remove individual overrides
```

This team collaboration guide ensures CLAUDE.md configurations support effective teamwork while maintaining individual productivity and project flexibility.