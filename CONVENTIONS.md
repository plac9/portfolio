# Cross-Project Conventions

**Last Updated**: 2025-11-09
**Version**: v1.0.0

---

## Universal Standards

These conventions apply to **all projects** in the portfolio.

### Directory Structure

All repositories follow this structure:
- `.ai/` - AI session context
- `docs/` - Human documentation  
- `scripts/` - Utility scripts (organized by purpose)
- `releases/` - Build artifacts (gitignored)
- `README.md` - Only file at root

### Brand Detection

**session_brand.json** in `.ai/` directory:
```json
{
  "brand": "laclair",  // or "rtis"
  "detected_at": "2025-11-09",
  "confidence": "high"
}
```

### Git Ignore Patterns

All projects include:
```gitignore
# Session notes (ephemeral)
.ai/session_notes/
.ai/*.scratch.md

# Build artifacts
releases/*
!releases/.gitkeep

# Script outputs
scripts/**/*.log
scripts/**/output/
```

---

## Brand-Specific Standards

### LaClair Technologies

- **Cloud AI**: Allowed
- **Privacy**: Standard practices
- **Branding**: LaClair Technologies logo/colors
- **Code Standards**: docs/CODE_STANDARDS.md (if exists)

### Real Time (RTIS)

- **Cloud AI**: BLOCKED by default (privacy requirement)
- **Privacy**: Enhanced controls
- **Branding**: Real Time Information Services
- **Code Standards**: docs/CODE_STANDARDS.md (if exists)
- **Local AI**: Preferred (Ollama models)

---

## Documentation Conventions

### SESSION_CONTEXT.md Format

```markdown
# project-name - Session Context

**Last Updated**: YYYY-MM-DD HH:MM
**Status**: [Development | Production | Maintenance]
**Version**: vX.Y.Z
**Brand**: [LaClair Technologies | Real Time (RTIS)]

## Quick Status
## Project Overview
## Current State
## Development Workflow
## Resources
```

### File Naming

- **Dated files**: `YYYY-MM-DD-description.md` (e.g., `2025-11-09-cleanup.md`)
- **Session notes**: `.ai/session_notes/YYYY-MM-DD.md`
- **Maintenance logs**: `docs/maintenance/YYYY-MM-DD-description.md`

---

## Workflow Conventions

### Session Start

```bash
cd ~/dev/[brand]/project-name
pcontext                # Read current state
phandoff                # Check last session
```

### During Work

```bash
pnote "Implemented feature X"
pnote "Fixed bug Y"
```

### Session End

```bash
ptouch                  # Update timestamp
vim .ai/HANDOFF.md      # Add handoff notes
```

---

## Commit Conventions

### Commit Messages

Format: `<type>: <description>`

Types:
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation
- `refactor:` Code refactoring
- `test:` Testing
- `chore:` Maintenance

Example: `feat: add user authentication`

### Documentation Commits

Always include:
```
Standardize documentation structure

- Implement .ai/ for AI session context
- Organize docs/ with comprehensive guides
- Structure scripts/ by purpose

🤖 Generated with Claude Code
https://claude.com/claude-code

Co-Authored-By: Claude <noreply@anthropic.com>
```

---

For project-specific standards, see individual `docs/` directories.
