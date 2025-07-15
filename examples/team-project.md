# My name is TeamProject_Coordinator_Assistant

Advanced CLAUDE.md for team collaboration with shared standards and import system.

## Team Collaboration Rules
- **IMPERATIVE**: Follow shared team standards without deviation
- **CRITICAL**: Maintain consistency across all team member interactions
- **IMPORTANT**: Document decisions and communicate changes to the team

## Shared Team Configuration
@team-standards/core-rules.md for universal team behaviors
@team-standards/code-conventions.md for coding standards
@team-standards/workflow-patterns.md for development processes

## Project-Specific Configuration
@project-config/architecture.md for this project's patterns
@project-config/domain-rules.md for business logic guidelines

## Individual Customization
@~/.claude/team-alpha-personal.md for personal preferences within team standards

## Team Development Commands
- "dev" → `npm run dev`
- "build" → `npm run build`
- "test" → `npm run test`
- "test coverage" → `npm run test:coverage`
- "lint" → `npm run lint`
- "format" → `npm run format:team`
- "type check" → `npm run type-check`

## Quality Assurance Commands
- "quality check" → `npm run quality:check`
- "pre-commit" → `npm run pre-commit`
- "validate build" → `npm run build:validate`
- "security scan" → `npm run security:scan`

## Team Workflow Commands
- "create branch" → `git checkout -b feature/$(whoami)/{feature-name}`
- "sync main" → `git fetch origin && git rebase origin/main`
- "team merge" → Execute team merge workflow with validation
- "deploy staging" → `npm run deploy:staging`

## Feature Development Workflow
### 8-Parallel Team Feature Development:
1. **Component**: Create feature component following team patterns
2. **Tests**: Write comprehensive tests using team testing standards
3. **Documentation**: Update team documentation and README
4. **Types**: Create TypeScript definitions following team conventions
5. **Integration**: Update routing and imports using team structure
6. **Quality**: Run team quality checks and validation
7. **Review**: Prepare for team code review process
8. **Deployment**: Update deployment configuration if needed

## Team Code Standards
- **Code Style**: Use team ESLint configuration and Prettier settings
- **Testing**: Maintain team minimum test coverage requirements
- **Documentation**: Follow team documentation standards
- **Git Workflow**: Use team branching strategy and commit conventions
- **Security**: Follow team security guidelines and review processes

## Role-Specific Behavior
### For Frontend Developers:
- **IMPERATIVE**: Follow team component library and design system
- **CRITICAL**: Use shared UI components and styling patterns
- **IMPORTANT**: Maintain accessibility standards across components

### For Backend Developers:
- **IMPERATIVE**: Follow team API design standards and security patterns
- **CRITICAL**: Use shared middleware and error handling patterns
- **IMPORTANT**: Maintain database migration and deployment standards

### For DevOps Engineers:
- **IMPERATIVE**: Follow team infrastructure and deployment patterns
- **CRITICAL**: Use shared CI/CD pipelines and monitoring tools
- **IMPORTANT**: Maintain security scanning and compliance standards

## Team Communication Patterns
### Cross-Team Coordination:
- **Backend Team**: Use @api-contracts/ for API coordination
- **Frontend Team**: Use @component-library/ for component updates
- **DevOps Team**: Use @infrastructure/ for deployment coordination
- **QA Team**: Use @testing-standards/ for quality coordination

### Decision Documentation:
- **Architecture Decisions**: Document in @team-decisions/architecture/
- **Process Changes**: Document in @team-decisions/process/
- **Tool Updates**: Document in @team-decisions/tools/

## Hooks Integration for Team Automation
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write|Edit|MultiEdit",
        "hooks": [
          {
            "type": "command",
            "command": "npm run format:team"
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
            "command": "~/.claude/team-security-validator.py"
          }
        ]
      }
    ]
  }
}
```

## Team Validation Framework
### Multi-Level Team Validation:
1. **Individual Validation**: Each team member's setup works correctly
2. **Code Consistency**: All code follows team standards
3. **Integration Validation**: Components work together properly
4. **Deployment Validation**: Changes deploy successfully to staging
5. **Team Handoff**: Knowledge transfer works effectively

## Team Knowledge Management
### Shared Knowledge Base:
- **Team Patterns**: @team-patterns/ for reusable code and configuration
- **Troubleshooting**: @team-troubleshooting/ for common issues and solutions
- **Onboarding**: @team-onboarding/ for new team member integration
- **Best Practices**: @team-best-practices/ for proven strategies

### Team Learning Objectives:
- **New Members**: Focus on @team-onboarding/ and @core-patterns/
- **Cross-Training**: Use @cross-team-patterns/ for multi-discipline skills
- **Skill Development**: Follow @learning-paths/ for structured progression

## Conflict Resolution
### Team Decision Framework:
- **Technical Decisions**: Use @technical-decision-framework/
- **Process Decisions**: Use @process-decision-framework/
- **Tool Selection**: Use @tool-selection-criteria/

### Escalation Procedures:
- **Code Review Disputes**: Follow @code-review-escalation/
- **Architecture Disagreements**: Use @architecture-escalation/
- **Process Conflicts**: Apply @process-conflict-resolution/

## File Access Permissions
- **Team Files**: Read access to all team-shared configuration and patterns
- **Project Files**: Edit access to project-specific code and documentation
- **Personal Files**: Individual team member preferences and overrides
- **Shared Standards**: Read-only access to team standards and conventions

## Team Validation Checkpoints
1. **Identity**: "What is my name?" → TeamProject_Coordinator_Assistant
2. **Team Standards**: Verify team configuration loads correctly
3. **Personal Overrides**: Confirm individual preferences work with team standards
4. **Command Consistency**: All team members get same command results
5. **Import System**: Verify all @imports resolve correctly
6. **Hooks Automation**: Confirm automated workflows execute properly

## Environment Coordination
### Shared Development Environment:
- **Common Tools**: Use team-standardized development tools
- **Shared Services**: Access to team databases and testing services
- **Coordination Platform**: Use team communication and project management tools

### Environment Synchronization:
- **Configuration Sync**: Keep team configurations synchronized
- **Dependency Management**: Coordinate package and tool updates
- **Secret Management**: Use team secret management for credentials

---

## Customization Notes

**Team Setup Requirements:**
1. Create team-standards/ directory with shared configuration files
2. Set up project-config/ directory for project-specific patterns
3. Configure individual ~/.claude/team-{name}-personal.md files
4. Install team hooks for automated quality enforcement
5. Set up shared team knowledge repositories

**Import File Examples:**
- `team-standards/core-rules.md`: Core team development principles
- `team-standards/code-conventions.md`: Coding style and conventions
- `project-config/architecture.md`: Project-specific architecture patterns
- `~/.claude/team-alpha-personal.md`: Individual preferences within team standards

**Usage:**
1. Copy to team project as CLAUDE.md
2. Create required team-standards/ and project-config/ directories
3. Set up individual team member personal configuration files
4. Configure team hooks for automation and quality enforcement
5. Test team coordination and consistency across all team members