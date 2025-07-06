# CLAUDE.md Hooks Integration Patterns

## Overview
Comprehensive guide to integrating Claude Code hooks system with CLAUDE.md configurations for automated workflow enforcement and security validation.

## Core Integration Principles

### Hooks vs CLAUDE.md Instructions
- **CLAUDE.md**: Provides suggestions and guidance that Claude follows
- **Hooks**: Provides deterministic automation that always executes
- **Integration**: Use hooks to enforce CLAUDE.md rules automatically

### When to Use Hooks in CLAUDE.md Templates
- **Code Quality**: Automatic formatting and linting enforcement
- **Security**: Block dangerous operations and validate inputs
- **Workflow**: Trigger builds, tests, and deployments
- **Audit**: Log operations for compliance and debugging
- **Notifications**: Custom alerts for important events

## Hook Configuration Patterns

### Basic Hook Structure
```json
{
  "hooks": {
    "EventName": [
      {
        "matcher": "ToolPattern",
        "hooks": [
          {
            "type": "command",
            "command": "your-script.sh",
            "timeout": 30
          }
        ]
      }
    ]
  }
}
```

### Code Quality Enforcement
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write|Edit|MultiEdit",
        "hooks": [
          {
            "type": "command",
            "command": "prettier --write \"$(echo '$tool_input' | jq -r '.file_path')\" || true"
          }
        ]
      }
    ]
  }
}
```

### Security Validation
```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "python3 ~/.claude/security-validator.py"
          }
        ]
      }
    ]
  }
}
```

### Workflow Automation
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write|Edit|MultiEdit",
        "hooks": [
          {
            "type": "command",
            "command": "npm run build && npm test"
          }
        ]
      }
    ]
  }
}
```

## CLAUDE.md Integration Patterns

### Template Structure with Hooks
```markdown
# Project Name

## Important
- ALL instructions within this document MUST BE FOLLOWED
- Hooks are configured to enforce these rules automatically

## Code Quality Rules
- IMPERATIVE: All code must be formatted with Prettier
- CRITICAL: All TypeScript files must pass type checking
- IMPORTANT: All functions must have JSDoc comments

## Hooks Configuration
See @claude-md-hooks-integration.md for comprehensive hook patterns and automated enforcement of these rules.

## Security Rules
- IMPERATIVE: Never commit secrets or API keys
- CRITICAL: Validate all file paths for traversal attempts
- IMPORTANT: Log all file operations for audit trail

## Workflow Rules
- IMPERATIVE: Run tests after any code changes
- CRITICAL: Build must succeed before committing
- IMPORTANT: Notify team of deployment-ready changes
```

### Command Translation with Hooks
```markdown
## Command Translation System

### Quality Commands:
- "format code" → Triggers PostToolUse hooks for Write/Edit operations
- "run tests" → Triggers workflow automation hooks
- "validate security" → Triggers PreToolUse hooks for Bash operations

### Automation Commands:
- "enforce formatting" → Configure PostToolUse hooks with formatting tools
- "block dangerous commands" → Configure PreToolUse hooks with security validation
- "enable notifications" → Configure Notification hooks with custom alerting
```

## Security Patterns

### Input Validation Hook
```python
#!/usr/bin/env python3
import json
import sys
import re

def validate_bash_command(command):
    """Validate bash commands for security issues"""
    dangerous_patterns = [
        r'rm\s+-rf\s+/',  # Dangerous rm commands
        r'chmod\s+777',   # Overly permissive permissions
        r'curl.*\|\s*sh', # Piping downloads to shell
        r'wget.*\|\s*sh', # Piping downloads to shell
    ]
    
    for pattern in dangerous_patterns:
        if re.search(pattern, command):
            return False, f"Dangerous command pattern detected: {pattern}"
    
    return True, "Command validated"

try:
    input_data = json.load(sys.stdin)
    tool_input = input_data.get("tool_input", {})
    command = tool_input.get("command", "")
    
    is_valid, message = validate_bash_command(command)
    
    if not is_valid:
        print(f"Security validation failed: {message}", file=sys.stderr)
        sys.exit(2)  # Block the command
    
    print(f"Security validation passed: {message}")
    sys.exit(0)
    
except Exception as e:
    print(f"Security validation error: {e}", file=sys.stderr)
    sys.exit(1)
```

### Path Sanitization Hook
```bash
#!/bin/bash
# Validate file paths for security issues

INPUT=$(cat)
FILE_PATH=$(echo "$INPUT" | jq -r '.tool_input.file_path // empty')

if [[ -z "$FILE_PATH" ]]; then
    exit 0  # No file path to validate
fi

# Check for path traversal attempts
if [[ "$FILE_PATH" =~ \.\./|\.\. ]]; then
    echo "Path traversal detected in: $FILE_PATH" >&2
    exit 2  # Block the operation
fi

# Check for access to sensitive directories
if [[ "$FILE_PATH" =~ ^/etc/|^/root/|^/var/log/ ]]; then
    echo "Access to sensitive directory blocked: $FILE_PATH" >&2
    exit 2  # Block the operation
fi

echo "Path validation passed: $FILE_PATH"
exit 0
```

## Advanced Integration Patterns

### Conditional Hook Execution
```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Write",
        "hooks": [
          {
            "type": "command",
            "command": "if [[ \"$(echo '$tool_input' | jq -r '.file_path')\" == *.ts ]]; then tsc --noEmit; fi"
          }
        ]
      }
    ]
  }
}
```

### Multi-Stage Validation
```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "~/.claude/hooks/validate-security.py"
          },
          {
            "type": "command",
            "command": "~/.claude/hooks/validate-syntax.py"
          },
          {
            "type": "command",
            "command": "~/.claude/hooks/log-operation.py"
          }
        ]
      }
    ]
  }
}
```

### MCP Tool Integration
```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "mcp__.*__write.*",
        "hooks": [
          {
            "type": "command",
            "command": "~/.claude/hooks/validate-mcp-write.py"
          }
        ]
      }
    ]
  }
}
```

## Template Generation Patterns

### Hooks-Enabled Template Structure
```markdown
# {PROJECT_NAME} with Hooks Integration

## Important
- ALL instructions within this document MUST BE FOLLOWED
- Hooks are configured to enforce these rules automatically

## Automation Rules
- IMPERATIVE: Code quality rules are enforced by PostToolUse hooks
- CRITICAL: Security validation is enforced by PreToolUse hooks
- IMPORTANT: Workflow automation is triggered by file changes

## Hooks Configuration
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write|Edit|MultiEdit",
        "hooks": [
          {
            "type": "command",
            "command": "{FORMATTER_COMMAND}"
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
            "command": "{SECURITY_VALIDATOR_COMMAND}"
          }
        ]
      }
    ]
  }
}
```

## Command Translation System with Hooks
- "enforce code quality" → Configure PostToolUse hooks for formatting
- "validate security" → Configure PreToolUse hooks for command validation
- "automate workflow" → Configure hooks for build/test/deploy processes
- "enable audit logging" → Configure hooks for operation tracking
```

## Best Practices

### Development Workflow
1. **Design CLAUDE.md rules first**: Define what should be enforced
2. **Create hooks for automation**: Implement deterministic enforcement
3. **Test in safe environment**: Validate hook behavior before production
4. **Document hook behavior**: Explain what each hook does and why
5. **Monitor and adjust**: Refine hooks based on real-world usage

### Security Considerations
- **Validate all inputs**: Never trust hook input data
- **Use safe defaults**: Fail securely when validation is uncertain
- **Log security events**: Track blocked operations for analysis
- **Regular security review**: Audit hook configurations periodically
- **Principle of least privilege**: Give hooks minimal required permissions

### Performance Optimization
- **Efficient matchers**: Use specific patterns to avoid unnecessary executions
- **Timeout configuration**: Set appropriate timeouts for hook operations
- **Parallel execution**: Design hooks to run efficiently in parallel
- **Resource limits**: Consider system resource usage of hook operations
- **Caching strategies**: Cache validation results when appropriate

### Team Collaboration
- **Shared hook libraries**: Create reusable hook scripts for the team
- **Version control**: Track hook configurations in git
- **Documentation**: Maintain clear documentation of hook behavior
- **Testing strategies**: Include hook testing in CI/CD pipelines
- **Rollback procedures**: Have plans for disabling problematic hooks

## Troubleshooting

### Common Issues
- **Hook not executing**: Check matcher patterns and event types
- **Security blocks**: Review validation logic and error messages
- **Performance issues**: Check hook timeouts and resource usage
- **Permission errors**: Verify file access permissions for hook scripts
- **JSON parsing errors**: Validate hook configuration syntax

### Debugging Commands
```bash
# Check hook configuration
claude --debug

# Test hook execution
echo '{"tool_name": "Bash", "tool_input": {"command": "ls"}}' | ~/.claude/hooks/test-hook.py

# View hook logs
tail -f ~/.claude/hook-logs.txt
```

### Testing Strategies
- **Unit tests**: Test individual hook scripts in isolation
- **Integration tests**: Test hook behavior with actual Claude Code usage
- **Security tests**: Verify that security hooks block dangerous operations
- **Performance tests**: Measure hook execution times and resource usage
- **Regression tests**: Ensure new hook changes don't break existing functionality