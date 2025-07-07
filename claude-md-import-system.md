# CLAUDE.md Import System Reference

## Overview
CLAUDE.md files can import additional files using `@path/to/import` syntax, enabling modular configuration and team collaboration.

## Import Syntax

### Basic Usage
```markdown
@README for project overview and @package.json for available npm commands for this project.

# Additional Instructions
- git workflow @docs/git-instructions.md
```

### Individual Preferences
```markdown
# Individual Preferences
- @~/.claude/my-project-instructions.md
```

## Import Rules

### Path Types
- **Relative paths**: `@docs/git-instructions.md`
- **Absolute paths**: `@/home/user/project/config.md`
- **Home directory**: `@~/.claude/my-project-instructions.md`

### Processing Rules
- Imported files can recursively import additional files (max-depth of 5 hops)
- Imports are not evaluated inside markdown code spans and code blocks
- @ file references add CLAUDE.md in the file's directory and parent directories to context

### Safety Features
```markdown
This code span will not be treated as an import: `@anthropic-ai/claude-code`
```

## Memory Discovery System

### Automatic File Discovery
Claude Code reads memories recursively:
1. Starting in current working directory
2. Recurses up to (but not including) root directory `/`
3. Reads any CLAUDE.md or CLAUDE.local.md files found
4. Discovers CLAUDE.md nested in subtrees on demand

### Memory Type Hierarchy

| Memory Type | Location | Purpose | Use Case Examples |
|-------------|----------|---------|------------------|
| **Project memory** | `./CLAUDE.md` | Team-shared instructions | Project architecture, coding standards |
| **User memory** | `~/.claude/CLAUDE.md` | Personal preferences for all projects | Code styling preferences, tooling shortcuts |
| **Project memory (local)** | `./CLAUDE.local.md` | Personal project-specific preferences | *(Deprecated - use imports instead)* |

## Advanced Import Patterns

### Team Collaboration
```markdown
# Team Configuration
@team-standards.md

# Individual Overrides
@~/.claude/personal-preferences.md
```

### Modular System Design
```markdown
# Core Rules
@core-rules.md

# Domain-Specific Extensions
@frontend-patterns.md
@backend-patterns.md
@testing-guidelines.md
```

### Conditional Imports
```markdown
# Development Environment
@dev-environment.md

# Production Deployment  
@production-config.md
```

## Management Commands

### View Loaded Memories
```
/memory
```
Shows all currently loaded memory files and their sources.

### Quick Memory Addition
```
# Always use descriptive variable names
```
Starting input with `#` prompts for memory file selection.

### Direct Editing
```
/memory
```
Opens memory files in system editor for extensive modifications.

## Best Practices

### Import Organization
- **Be specific**: Import only what's needed for the current context
- **Use hierarchy**: Organize imports from general to specific
- **Document purpose**: Comment why each import is included

### File Structure
- **Modular design**: Break large configurations into focused modules
- **Clear naming**: Use descriptive filenames that indicate content
- **Version control**: Check team imports into git, keep personal imports local

### Performance Considerations
- **Token efficiency**: Monitor total context size from all imports
- **Selective loading**: Use imports strategically to avoid context bloat
- **Regular cleanup**: Remove unused imports and outdated configurations

## Migration from CLAUDE.local.md

Previously `CLAUDE.local.md` served for personal project preferences, but imports are now preferred:

### Old Approach
```
./CLAUDE.md          # Team shared
./CLAUDE.local.md    # Personal (gitignored)
```

### New Approach
```
./CLAUDE.md                        # Team shared with imports
@~/.claude/my-project-prefs.md    # Personal preferences
```

### Benefits of Import Approach
- Works better across multiple git worktrees
- More flexible organization
- Better team collaboration support
- Cleaner separation of concerns