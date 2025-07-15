# MCP Integration Patterns for CLAUDE.md

## Overview
Patterns for integrating Model Context Protocol (MCP) servers into CLAUDE.md configurations, enabling dynamic tool access, external data integration, and extensible AI capabilities.

**Reference**: Combine with @patterns/comprehensive-template.md for MCP-enhanced project templates, @patterns/team-collaboration.md for team MCP coordination, @patterns/token-optimization.md for efficient MCP usage, and @patterns/validation.md for MCP validation strategies.

## Core MCP Integration Principles

### MCP-Aware CLAUDE.md Design
```markdown
## MCP Integration Rules
- **IMPERATIVE**: Verify MCP tool availability before using specialized patterns
- **CRITICAL**: Gracefully degrade when MCP servers are unavailable
- **IMPORTANT**: Document MCP dependencies for team setup consistency
```

### MCP Server Configuration Template
```markdown
# {PROJECT_NAME} with MCP Integration

## MCP Dependencies
**Required MCP Servers**:
- `{MCP_SERVER_1}`: {PURPOSE_DESCRIPTION}
- `{MCP_SERVER_2}`: {PURPOSE_DESCRIPTION}

**Optional MCP Servers**:
- `{OPTIONAL_MCP}`: {ENHANCED_CAPABILITY_DESCRIPTION}

## MCP Validation
**Setup Check**: Verify MCP servers are configured and accessible
**Tool Availability**: Confirm required MCP tools are functioning
**Fallback Strategy**: Use standard tools when MCP unavailable
```

## Database Integration Patterns

### Database-Aware Development Pattern
```markdown
## Database Operations with MCP
**Schema Management**: Use mcp_database tools for schema queries and validation
**Data Analysis**: Leverage database MCP for development insights
**Migration Support**: Use MCP tools for database migration assistance

## Database Commands
- "check schema" → Use mcp_database to validate current schema
- "analyze data" → Use mcp_database for data insights
- "validate migration" → Use mcp_database to check migration safety

## Fallback Strategy
If mcp_database unavailable:
- Use direct SQL files in @database/
- Reference schema documentation in @docs/database/
- Use manual validation against @database/schema.sql
```

### Schema-Driven Development
```markdown
## MCP Database Integration
**Schema Validation**: 
- **IMPERATIVE**: Validate all database changes against live schema via MCP
- **CRITICAL**: Use MCP database tools to check constraint compatibility
- **IMPORTANT**: Generate migration scripts using MCP insights

**Data Modeling**:
- Use mcp_database for relationship analysis
- Validate foreign key constraints via MCP
- Check performance implications with MCP query analysis

**Development Workflow**:
1. Query current schema via MCP database tools
2. Design changes using schema insights
3. Validate changes against live database
4. Generate migration scripts with MCP assistance
```

## External API Integration Patterns

### API-Enhanced Development
```markdown
## External API Integration via MCP
**API Documentation**: Use MCP web tools to fetch current API docs
**Service Integration**: Leverage MCP tools for external service communication
**Real-time Data**: Use MCP for live data during development

## API Commands
- "check api docs" → Use mcp_web to fetch latest API documentation
- "test endpoint" → Use MCP tools to validate API responses
- "validate integration" → Use MCP to test external service connectivity

## Configuration
**API Endpoints**: @config/api-endpoints.json
**Authentication**: @config/api-auth.json
**MCP Integration**: @config/mcp-api-config.json
```

### Service Discovery Pattern
```markdown
## MCP Service Discovery
**Service Catalog**: Use MCP tools to discover available services
**Health Monitoring**: MCP integration for service health checks
**Configuration Management**: MCP-driven configuration updates

**Discovery Workflow**:
1. Use MCP tools to scan available services
2. Validate service compatibility
3. Update configuration based on discovery
4. Test integration using MCP tools
```

## File System and Code Analysis Patterns

### Enhanced Code Analysis
```markdown
## MCP-Enhanced Code Analysis
**Code Insights**: Use MCP tools for advanced code analysis beyond basic grep/glob
**Dependency Analysis**: Leverage MCP for complex dependency mapping
**Pattern Recognition**: Use MCP tools for architectural pattern detection

## Analysis Commands
- "analyze codebase" → Use MCP tools for comprehensive code analysis
- "map dependencies" → Use MCP for dependency visualization
- "detect patterns" → Use MCP for architectural pattern recognition

## Standard Tool Fallbacks
- Basic file operations: Use Read, Write, Edit, MultiEdit
- Simple searches: Use Grep, Glob tools
- Basic bash operations: Use Bash tool
```

### Repository Intelligence
```markdown
## MCP Repository Analysis
**Git Integration**: Use MCP git tools for advanced repository analysis
**History Analysis**: MCP tools for commit pattern analysis
**Branch Strategy**: MCP-assisted branch management insights

**Intelligence Workflow**:
1. Use MCP git tools to analyze repository health
2. Identify code quality trends via MCP
3. Suggest improvements based on MCP insights
4. Track progress using MCP analytics
```

## Memory and Context Enhancement

### MCP Memory Integration
```markdown
## Enhanced Memory with MCP
**Persistent Context**: Use MCP memory tools for cross-session context
**Knowledge Graphs**: MCP integration for relationship mapping
**Learning Patterns**: MCP tools for pattern recognition and learning

## Memory Commands
- "save context" → Use MCP memory tools for persistent storage
- "load context" → Use MCP memory for context restoration
- "map relationships" → Use MCP for relationship analysis

## Traditional Memory Fallback
- Standard CLAUDE.md memory hierarchy
- File-based context with @imports
- Session-local context management
```

### Dynamic Context Loading
```markdown
## MCP Dynamic Context
**Adaptive Loading**: Use MCP tools to determine optimal context
**Smart Prioritization**: MCP-driven context priority management
**Resource Optimization**: MCP tools for token usage optimization

**Context Strategy**:
1. Use MCP tools to analyze current task requirements
2. Dynamically load relevant context via MCP
3. Optimize token usage with MCP insights
4. Adapt strategy based on MCP feedback
```

## Testing and Quality Assurance Patterns

### MCP-Enhanced Testing
```markdown
## Testing Integration with MCP
**Test Generation**: Use MCP tools for intelligent test generation
**Coverage Analysis**: MCP integration for advanced coverage insights
**Quality Metrics**: MCP tools for comprehensive quality analysis

## Testing Commands
- "generate tests" → Use MCP tools for test generation
- "analyze coverage" → Use MCP for coverage insights
- "quality check" → Use MCP for quality metrics

## Standard Testing Fallback
- Use configured test framework: {TEST_FRAMEWORK}
- Run standard commands: {TEST_COMMANDS}
- Use basic coverage tools: {COVERAGE_TOOLS}
```

### Continuous Quality Monitoring
```markdown
## MCP Quality Monitoring
**Real-time Metrics**: MCP integration for live quality metrics
**Trend Analysis**: MCP tools for quality trend monitoring
**Predictive Insights**: MCP-driven quality predictions

**Monitoring Workflow**:
1. Use MCP tools to collect quality metrics
2. Analyze trends via MCP analytics
3. Predict issues using MCP insights
4. Recommend improvements via MCP analysis
```

## Deployment and DevOps Integration

### MCP-Enhanced DevOps
```markdown
## DevOps Integration via MCP
**Infrastructure Monitoring**: MCP tools for infrastructure insights
**Deployment Analytics**: MCP integration for deployment analysis
**Performance Optimization**: MCP tools for performance insights

## DevOps Commands
- "check infrastructure" → Use MCP tools for infrastructure status
- "analyze deployment" → Use MCP for deployment insights
- "optimize performance" → Use MCP for performance analysis

## Traditional DevOps Fallback
- Use standard monitoring: {MONITORING_TOOLS}
- Standard deployment: {DEPLOYMENT_COMMANDS}
- Basic performance tools: {PERFORMANCE_TOOLS}
```

### Environment Management
```markdown
## MCP Environment Management
**Multi-Environment Coordination**: MCP tools for environment synchronization
**Configuration Drift Detection**: MCP analysis for configuration inconsistencies
**Automated Reconciliation**: MCP-driven environment alignment

**Environment Workflow**:
1. Use MCP tools to scan environment configurations
2. Detect drift via MCP analysis
3. Generate reconciliation plans with MCP
4. Apply changes using MCP automation
```

## Advanced MCP Patterns

### Conditional MCP Usage
```markdown
## Smart MCP Integration
**Capability Detection**: Automatically detect available MCP servers
**Feature Flags**: Enable/disable MCP features based on availability
**Progressive Enhancement**: Use MCP when available, fallback gracefully

**Detection Pattern**:
```python
# Example capability detection
if mcp_database_available():
    use_database_mcp_tools()
else:
    use_standard_database_files()
```
```

### MCP Tool Chaining
```markdown
## MCP Workflow Orchestration
**Tool Coordination**: Chain multiple MCP tools for complex workflows
**Cross-Server Integration**: Coordinate between different MCP servers
**Workflow Optimization**: Use MCP insights to optimize tool usage

**Chaining Example**:
1. Use mcp_database to analyze schema
2. Use mcp_web to fetch API documentation  
3. Use mcp_memory to store integration patterns
4. Use mcp_git to track implementation changes
```

### Custom MCP Server Integration
```markdown
## Project-Specific MCP Servers
**Domain-Specific Tools**: Integrate custom MCP servers for project needs
**Business Logic Integration**: MCP servers for domain-specific operations
**Custom Analytics**: Project-specific MCP tools for specialized analysis

**Custom Server Configuration**:
- **Server Name**: {CUSTOM_MCP_SERVER}
- **Purpose**: {DOMAIN_SPECIFIC_PURPOSE}
- **Tools**: {CUSTOM_TOOL_LIST}
- **Setup**: @config/custom-mcp-setup.md
```

## Implementation Guidelines

### MCP Setup Checklist
1. **Verify MCP Configuration**: Ensure Claude Code has MCP servers configured
2. **Test Tool Availability**: Validate required MCP tools are accessible
3. **Create Fallback Patterns**: Design graceful degradation strategies
4. **Document Dependencies**: List all MCP requirements for team setup
5. **Validate Integration**: Test MCP workflows in development environment

### Progressive MCP Adoption
```markdown
## MCP Migration Strategy
**Phase 1**: Identify MCP opportunities in existing CLAUDE.md
**Phase 2**: Add MCP integration with fallbacks
**Phase 3**: Optimize workflows using MCP capabilities
**Phase 4**: Leverage advanced MCP features for enhanced productivity
```

### Team MCP Coordination
```markdown
## Team MCP Standards
**Shared MCP Config**: @team-config/mcp-servers.json
**MCP Tool Standards**: @team-standards/mcp-usage.md
**Capability Matrix**: @team-docs/mcp-capability-matrix.md
**Setup Guide**: @team-onboarding/mcp-setup.md
```

## Troubleshooting and Maintenance

### MCP Diagnostics
```markdown
## MCP Health Monitoring
**Server Status**: Regular health checks for MCP servers
**Tool Validation**: Periodic validation of MCP tool functionality
**Performance Monitoring**: Track MCP tool response times and reliability

## Diagnostic Commands
- "check mcp status" → Validate all configured MCP servers
- "test mcp tools" → Run functionality tests on MCP tools
- "mcp performance" → Analyze MCP tool performance metrics
```

### Common MCP Issues
```markdown
## MCP Troubleshooting Guide
**Connection Issues**: Check MCP server configuration and network connectivity
**Tool Failures**: Validate MCP tool permissions and dependencies
**Performance Issues**: Monitor MCP tool resource usage and optimize calls
**Integration Conflicts**: Resolve conflicts between different MCP servers

## Resolution Strategies
- Always maintain fallback options for critical workflows
- Use standard tools when MCP fails
- Document MCP-specific troubleshooting steps
- Regular MCP server maintenance and updates
```

This MCP integration guide enables CLAUDE.md configurations to leverage advanced MCP capabilities while maintaining reliability through appropriate fallback strategies and team coordination.