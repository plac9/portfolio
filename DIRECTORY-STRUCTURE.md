# Development Portfolio - Directory Structure

**Last Updated**: 2025-11-09
**Structure Version**: v2.0.0

---

## Overview

The `~/dev/` directory is organized by **brand** and **project type** for clear separation and easy navigation.

```
~/dev/
├── .portfolio/             # Master portfolio documentation
├── .claude/                # Claude Code global configuration
├── .dotfiles/              # Shell configuration (zsh, etc.)
│
├── infrastructure/         # Infrastructure & DevOps projects
├── laclair/                # LaClair Technologies projects
├── rtis/                   # Real Time Information Services projects
├── ios/                    # iOS-specific projects
├── archived/               # Archived/completed projects
└── experiments/            # Experimental/POC projects
```

---

## Directory Purposes

### `.portfolio/` - Master Documentation

**Purpose**: Portfolio-level documentation and cross-project information

**Contents**:
- README.md - Portfolio overview
- STANDARDIZATION-PROJECT.md - Documentation standardization record
- DIRECTORY-STRUCTURE.md - This file
- CONVENTIONS.md - Cross-project standards
- PROJECT-INDEX.md - Quick project reference
- ALIASES-AND-TOOLS.md - Shell alias documentation
- WORKFLOWS.md - Common development workflows
- sessions/ - Portfolio-level session notes

**When to use**: Looking for cross-project information or portfolio overview

---

### `.claude/` - Claude Code Configuration

**Purpose**: Global Claude Code configuration and monitoring

**Contents**:
- settings.json - Global Claude Code settings
- statusline-command.sh - Custom status line
- monitor-switcher.sh - Homelab monitoring (Prefix+M)
- monitor-views/ - Specialized monitoring views (1-5)
- session-status/ - Current session tracking

**When to use**: Configuring Claude Code globally or accessing monitoring

---

### `.dotfiles/` - Shell Configuration

**Purpose**: Shell configuration, aliases, and environment setup

**Contents**:
- zsh/ - Zsh configuration
  - homelab-functions.zsh - Homelab management functions
- Various dotfile configurations

**When to use**: Customizing shell environment or adding new aliases

---

### `infrastructure/` - Infrastructure Projects

**Purpose**: Infrastructure as Code, DevOps, and server management projects

**Projects**:
- **homelab-iac** - Docker Compose for 52+ containers
  - Authentication (Authentik)
  - Monitoring systems
  - Databases
  - DNS services
  - Utilities

**Characteristics**:
- Infrastructure-focused
- Production servers
- Multi-service deployments
- Critical systems

**When to add here**: Projects managing infrastructure, servers, or multi-service deployments

---

### `laclair/` - LaClair Technologies Projects

**Purpose**: Personal and LaClair Technologies consulting projects

**Projects** (10):
1. **xander-dashboard** - Production dashboard (React, Node.js)
2. **ai-device-setup** - Emergency recovery toolkit
3. **powershell** - Enterprise PowerShell automation
4. **patrick-laclair-me** - Personal portfolio website
5. **laclair-family-us** - Family portal application
6. **laclair-terminal** - Terminal application
7. **netcalc** - iOS subnet calculator
8. **xanban** - Windows parental controls
9. **ai-workspace** - macOS deployment toolkit
10. **repo-standardization-tools** - Documentation tools

**Characteristics**:
- Personal projects
- LaClair Technologies brand
- Cloud AI allowed
- Standard security

**When to add here**: Personal projects, LaClair Technologies consulting work, or internal tools

---

### `rtis/` - Real Time Information Services Projects

**Purpose**: Real Time (MSP) client work with enhanced privacy

**Projects** (2):
1. **ih-onboard-form** - IHMG employee onboarding (Node.js, production)
2. **powershell** - MSP PowerShell automation

**Characteristics**:
- Client work for Real Time MSP
- **Privacy requirement**: Cloud AI blocked by default
- Enhanced security controls
- Local AI models preferred
- RTIS branding

**When to add here**: Real Time client projects or MSP work

---

### `ios/` - iOS-Specific Projects

**Purpose**: iOS, iPadOS, and macOS-specific native applications

**Projects**:
- Currently houses iOS-specific work
- Native Swift/SwiftUI projects may be placed here

**Characteristics**:
- Native Apple platform development
- Xcode projects
- Swift/SwiftUI/Objective-C

**When to add here**: iOS/macOS native applications (alternatively, can go in laclair/ or rtis/ based on brand)

**Note**: `netcalc` is currently in `laclair/` but could fit here

---

### `archived/` - Archived Projects

**Purpose**: Completed, deprecated, or inactive projects

**Usage**:
- Move completed projects here when no longer actively developed
- Preserve for reference
- Free up main directories

**When to add here**: Projects that are complete, deprecated, or no longer maintained

---

### `experiments/` - Experimental Projects

**Purpose**: Proof-of-concept, learning, and experimental work

**Usage**:
- Quick POCs
- Technology exploration
- Learning new frameworks
- Temporary test projects

**Characteristics**:
- Not production
- May not follow full standards
- Temporary or exploratory

**When to add here**: POCs, experiments, or learning projects that aren't production-ready

---

## Navigation Patterns

### By Brand

```bash
# LaClair Technologies work
cd ~/dev/laclair/

# Real Time (RTIS) client work
cd ~/dev/rtis/

# Infrastructure projects
cd ~/dev/infrastructure/
```

### By Project Type

```bash
# Web applications
cd ~/dev/laclair/xander-dashboard
cd ~/dev/laclair/patrick-laclair-me

# Automation tools
cd ~/dev/laclair/powershell
cd ~/dev/rtis/powershell

# Infrastructure
cd ~/dev/infrastructure/homelab-iac

# Mobile apps
cd ~/dev/laclair/netcalc
```

### By Status

```bash
# Production systems
cd ~/dev/laclair/xander-dashboard      # Production
cd ~/dev/rtis/ih-onboard-form          # Production
cd ~/dev/infrastructure/homelab-iac    # Production

# Development
cd ~/dev/laclair/netcalc               # In development

# Tools
cd ~/dev/laclair/ai-device-setup       # Emergency tool
cd ~/dev/laclair/repo-standardization-tools  # Documentation tool
```

---

## Decision Tree: Where to Place New Projects

```
Is it infrastructure/DevOps?
├─ YES → infrastructure/
└─ NO
    ├─ Is it for Real Time (MSP client)?
    │   ├─ YES → rtis/
    │   └─ NO
    │       ├─ Is it personal or LaClair Technologies?
    │       │   ├─ YES → laclair/
    │       │   └─ NO
    │       │       ├─ Is it iOS/macOS specific?
    │       │       │   ├─ YES → ios/ (or laclair/ if LaClair brand)
    │       │       │   └─ NO
    │       │       │       ├─ Is it experimental/POC?
    │       │       │       │   ├─ YES → experiments/
    │       │       │       │   └─ NO
    │       │       │       │       └─ Is it complete/deprecated?
    │       │       │       │           ├─ YES → archived/
    │       │       │       │           └─ NO → Default to laclair/
```

---

## Standards Per Directory

### All Project Directories (laclair/, rtis/, infrastructure/, ios/)

**Required**:
- Follow standard repository structure (.ai/, docs/, scripts/, releases/)
- README.md at root
- SESSION_CONTEXT.md in .ai/
- session_brand.json for brand detection

**Run Standardization**:
```bash
~/dev/laclair/repo-standardization-tools/scripts/apply-standards.sh /path/to/new/project
```

### Special Directories (.portfolio/, .claude/, .dotfiles/)

**Exempt from standardization**:
- These are configuration/meta directories
- Follow their own organizational patterns
- Do not require .ai/ structure

---

## Examples

### Example 1: New LaClair Technologies Web App

```bash
# Create project
cd ~/dev/laclair
mkdir new-webapp
cd new-webapp

# Initialize repository
git init

# Apply standardization
~/dev/laclair/repo-standardization-tools/scripts/apply-standards.sh .

# Customize
vim .ai/SESSION_CONTEXT.md  # Add project details
vim .ai/session_brand.json  # {"brand": "laclair", ...}
```

### Example 2: New RTIS Client Project

```bash
# Create project
cd ~/dev/rtis
mkdir client-project
cd client-project

# Initialize repository
git init

# Apply standardization
~/dev/laclair/repo-standardization-tools/scripts/apply-standards.sh .

# Customize with RTIS brand
vim .ai/SESSION_CONTEXT.md  # Add project details
vim .ai/session_brand.json  # {"brand": "rtis", ...}
```

### Example 3: New Infrastructure Service

```bash
# Create project
cd ~/dev/infrastructure
mkdir new-service-stack
cd new-service-stack

# Initialize repository
git init

# Apply standardization
~/dev/laclair/repo-standardization-tools/scripts/apply-standards.sh .

# Customize
vim .ai/SESSION_CONTEXT.md  # Infrastructure-specific details
```

---

## Validation

### Check Structure Compliance

```bash
# Validate all repositories
~/dev/laclair/repo-standardization-tools/scripts/validate-all-repos.sh

# Check specific project
cd ~/dev/laclair/project-name
ls -la                      # Should see only README.md at root
ls .ai/                     # Should see SESSION_CONTEXT.md, ARCHITECTURE.md, etc.
ls docs/                    # Should see organized docs
ls scripts/                 # Should see dev/, deploy/, troubleshoot/, maintenance/
```

---

## Migration Guide

### Moving Project to Different Directory

**Example**: Moving project from laclair/ to rtis/

```bash
# Move directory
mv ~/dev/laclair/project-name ~/dev/rtis/project-name

# Update brand
cd ~/dev/rtis/project-name
vim .ai/session_brand.json  # Change to {"brand": "rtis", ...}
vim .ai/SESSION_CONTEXT.md  # Update brand references

# Update remote if needed
git remote set-url origin https://github.com/plac9/new-url
```

---

## Summary

| Directory | Purpose | Brand | Privacy | Projects |
|-----------|---------|-------|---------|----------|
| `.portfolio/` | Master docs | N/A | N/A | Meta |
| `.claude/` | Claude config | N/A | N/A | Config |
| `.dotfiles/` | Shell config | N/A | N/A | Config |
| `infrastructure/` | IaC/DevOps | Mixed | Standard | 1 |
| `laclair/` | Personal/consulting | LaClair Tech | Standard | 10 |
| `rtis/` | MSP client work | Real Time | Enhanced | 2 |
| `ios/` | Native Apple apps | Mixed | Standard | 0 |
| `archived/` | Completed projects | Mixed | N/A | Various |
| `experiments/` | POC/learning | Mixed | Standard | Various |

---

**Last Updated**: 2025-11-09
**Structure Version**: v2.0.0
**Total Projects**: 13 (12 active + 1 meta)

For more information, see [Master Portfolio README](README.md).
