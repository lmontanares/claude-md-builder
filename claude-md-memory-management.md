# CLAUDE.md Memory Management & Location Guide

## Memory Location Strategy

### Where to Place CLAUDE.md Files

**The root of your repo** (most common)
- Name it `CLAUDE.md` and check into git for team sharing (recommended)
- Name it `CLAUDE.local.md` and `.gitignore` it for personal use *(deprecated - use imports instead)*

**Parent directories** (monorepos)
- Run `claude` from `root/foo`, have CLAUDE.md in both `root/CLAUDE.md` and `root/foo/CLAUDE.md`
- Both are automatically pulled into context

**Child directories** (subtree discovery)
- Claude pulls in CLAUDE.md files on demand when working with files in those subtrees
- Enables project-wide and component-specific configurations

**Home folder** (`~/.claude/CLAUDE.md`)
- Applies to all your claude sessions across all projects
- Perfect for personal preferences and global configurations

## Memory Type Hierarchy

### Project Memory (`./CLAUDE.md`)
**Purpose**: Team-shared instructions for the project
**Use Cases**:
- Project architecture documentation
- Coding standards and style guidelines
- Common workflows and commands
- Repository-specific conventions

**Example Structure**:
```markdown
# Project: MyApp
## Architecture
- Frontend: React + TypeScript
- Backend: Node.js + Express
## Common Commands
- npm run dev: Start development server
- npm run build: Build for production
- npm test: Run test suite
## Code Style
- Use 2-space indentation
- Prefer const over let
- Use destructuring imports
```

### User Memory (`~/.claude/CLAUDE.md`)
**Purpose**: Personal preferences for all projects
**Use Cases**:
- Code styling preferences
- Personal tooling shortcuts
- Workflow preferences
- Global development environment setup

**Example Structure**:
```markdown
# My Personal Claude Preferences
## Code Style Preferences
- Always use trailing commas
- Prefer single quotes over double quotes
- Use explicit return types in TypeScript
## Tooling
- Default test framework: Jest
- Preferred linter: ESLint with Prettier
- Git workflow: feature branches with rebase
```

### Project Memory (Local) - DEPRECATED
**Legacy Location**: `./CLAUDE.local.md`
**Modern Alternative**: Use imports with `@~/.claude/project-specific-prefs.md`

## Memory Discovery Process

### Recursive Loading Behavior
1. **Start**: Current working directory
2. **Recurse Up**: To (but not including) root directory `/`
3. **Auto-Load**: Any CLAUDE.md or CLAUDE.local.md files found
4. **Subtree Discovery**: CLAUDE.md files in child directories loaded on demand

### Context Separation Strategy
**Problem**: Ensure strict separation of context between projects
**Solution**: Keep project directory `CLAUDE.md` lightweight and non-specific

**Example - Lightweight Project CLAUDE.md**:
```markdown
# Project Configuration
See @project-details.md for specific architecture
See @team-conventions.md for coding standards
See @~/.claude/my-preferences.md for personal settings
```

## Advanced Memory Patterns

### Dynamic Memory Pattern
**Concept**: Temporarily modify CLAUDE.md for specific contexts, then revert

**Backup Strategies**:
- **Git versioning**: Use `git stash` or commit before changes
- **File duplication**: Copy to `CLAUDE.md.backup` before modifications

**Refresh Techniques**:
- **Quick Memory**: Use `#` commands to temporarily change persisted information
- **Memory refresh commands**: Explicitly ask Claude to re-read modified CLAUDE.md
- **Session restart**: Start new Claude Code session to pick up changes
- **Explicit file reads**: Use read commands to load updated content

### Context Separation via Spawning
**Technique**: Spawn new Claude instances in directories with different CLAUDE.md files

**Benefits**:
- **Cleaner context separation**: Each instance operates with its own specific context
- **No memory reload issues**: New instances automatically load their directory's CLAUDE.md
- **Parallel processing**: Multiple contexts can run simultaneously without interference
- **Reduced context pollution**: Previous session context doesn't bleed into new specialized tasks

**Implementation**:
```bash
# Terminal 1: General development
cd /project/main
claude

# Terminal 2: Specialized tooling context  
cd /project/tools-context
claude
```

## Memory Management Best Practices

### Modular Design Principles
**Why Modular Works**:
- Clear boundaries prevent instruction bleeding
- Easier maintenance and updates
- Better context management
- Reduced cognitive load when reading

**Implementation Strategy**:
```markdown
# CLAUDE.md - Main Configuration
@core-rules.md
@project-architecture.md
@team-workflows.md
@personal-preferences.md
```

### Token Efficiency Management
**Context Window Strategy**: Front-load the context rather than having Claude randomly read files

**Optimization Techniques**:
- **Selective imports**: Only import what's needed for current task
- **Priority organization**: Most critical details first
- **Compact examples**: Use representative patterns efficiently
- **Strategic file restrictions**: Denote which files Claude can/cannot read

### Performance Monitoring
**Warning Signs**:
- CLAUDE.md size warnings affecting performance
- Context window depletion
- Instruction adherence degradation

**Solutions**:
- **Modular refactoring**: Break large CLAUDE.md into focused modules
- **Aggressive filtering**: Remove irrelevant details
- **Import optimization**: Use conditional imports based on task type

## Quality Assurance

### Sanity Check Protocol
**Simple Test**: Add your name at the top of CLAUDE.md
```markdown
# My name is {NAME}
This file provides guidance to Claude Code when working with this repository.
```

**Validation**: Ask Claude "What is my name?"

**Troubleshooting Common Issues**:
- Forgetting to set a CLAUDE.md
- Putting CLAUDE.md in wrong folder
- Accidentally deleting part of CLAUDE.md
- Misspelling `CLAUSE.md`
- Running out of context window

### Advanced Sanity Checks
**Multiple Checkpoints**: Distribute sanity check points across CLAUDE.md
```markdown
# Checkpoint 1: Identity
# My name is {NAME}

## Core Rules
# Checkpoint 2: Priority system active

### Advanced Workflows  
# Checkpoint 3: Parallel execution enabled
```

**Usage**: Test integrity as context window fills up by asking about specific checkpoints

## Migration Strategies

### From Legacy Approach
**Old Structure**:
```
./CLAUDE.md          # Team configuration
./CLAUDE.local.md    # Personal overrides
```

**New Structure**:
```
./CLAUDE.md                          # Team configuration with imports
@~/.claude/personal-preferences.md   # Personal settings
@~/.claude/project-specific.md       # Project-specific personal settings
```

### For Large Teams
**Centralized Team Standards**:
```markdown
# Team CLAUDE.md
@team-standards/architecture.md
@team-standards/coding-conventions.md
@team-standards/workflows.md

# Individual Developer Imports
@~/.claude/personal-dev-preferences.md
```

### For Monorepos
**Hierarchical Configuration**:
```
/monorepo/CLAUDE.md              # Global standards
/monorepo/frontend/CLAUDE.md     # Frontend-specific rules
/monorepo/backend/CLAUDE.md      # Backend-specific rules
/monorepo/shared/CLAUDE.md       # Shared utilities rules
```