# Patrick LaClair - Development Portfolio

**Last Updated**: 2025-11-10
**Total Projects**: 16 active repositories
**Documentation Standard**: v1.0.0 (standardized 2025-11-09)
**Environment**: Windows 11 WSL2 (Ubuntu)
**Location**: `/mnt/d/dev/` (WSL-accessible Windows D: drive)

---

## Overview

This is the master documentation for Patrick LaClair's complete development portfolio, covering all active projects across LaClair Technologies and Real Time Information Services (RTIS).

**Platform**: Windows 11 with WSL2 (Ubuntu Linux) running from `/mnt/d/dev/`

### Portfolio Statistics

- **Total Repositories**: 16 active
- **Brands**: 2 (LaClair Technologies, Real Time Information Services)
- **Technology Stacks**: 6+ (React/TypeScript, Node.js, PowerShell, Swift, Docker, Bash)
- **Production Systems**: 3 (xander-dashboard, ih-onboard-form, homelab-iac)
- **Infrastructure Projects**: 2 (homelab-iac, thebrain)
- **Documentation Files**: 150+ across all projects
- **Standardization Date**: 2025-11-09
- **WSL Setup Date**: 2025-11-10

---

## Quick Navigation

### Master Documentation

- **[Standardization Project](STANDARDIZATION-PROJECT.md)** - What we accomplished on 2025-11-09
- **[Directory Structure](DIRECTORY-STRUCTURE.md)** - How ~/dev/ is organized
- **[Conventions](CONVENTIONS.md)** - Cross-project standards and patterns
- **[Project Index](PROJECT-INDEX.md)** - Quick reference for all 12 projects
- **[Aliases & Tools](ALIASES-AND-TOOLS.md)** - All shell aliases and commands
- **[Workflows](WORKFLOWS.md)** - Common development workflows

### Session Notes

- **[sessions/](sessions/)** - Portfolio-level session notes and project history

---

## Directory Structure

```
/mnt/d/dev/ (~/dev/ on WSL)
├── .portfolio/                 # THIS DIRECTORY - Master documentation
├── .claude/                    # Claude Code configuration
│
├── infrastructure/             # Infrastructure & IaC projects (2)
│   ├── homelab-iac/           # Homelab Docker Compose (52+ containers)
│   └── thebrain/              # OPNsense router infrastructure
│
├── laclair/                    # LaClair Technologies projects (12)
│   ├── xander-dashboard/      # Production dashboard for Xander
│   ├── ai-device-setup/       # Emergency recovery toolkit
│   ├── claude-code-system-prompt/  # Claude Code system prompt docs
│   ├── dev-root/              # Master dev documentation
│   ├── portfolio/             # Portfolio documentation (source)
│   ├── powershell-laclairtech/ # Enterprise PowerShell automation
│   ├── patrick-laclair-me/    # Personal portfolio website
│   ├── laclair-family-os/     # Family OS project
│   ├── laclair-terminal/      # Terminal application
│   ├── netcalc/               # iOS subnet calculator
│   ├── xanban/                # Windows parental controls
│   └── repo-standardization-tools/  # Documentation tools
│
├── rtis/                       # Real Time Information Services projects (2)
│   ├── realtime_ih-onboard_form/  # IHMG employee onboarding (production)
│   └── powershell-realtime/   # MSP PowerShell automation
│
├── ios/                        # iOS-specific projects (0)
├── archived/                   # Archived/completed projects (0)
└── experiments/                # Experimental/proof-of-concept projects (0)
```

---

## Projects by Category

### Production Systems (3)

1. **xander-dashboard** - Production dashboard with gaming latency monitoring
   - URL: https://xander.home.laclair.us
   - Tech: React 18, Node.js 22, WebSocket, Docker

2. **ih-onboard-form** - IHMG employee onboarding system
   - URL: https://onboarding.ccfmg.org
   - Tech: Node.js, Express, SQLite
   - Brand: Real Time (RTIS)

3. **homelab-iac** - Infrastructure as Code for homelab
   - Server: docker.home.laclair.us
   - Tech: Docker Compose, 52+ containers

### Development Tools (3)

4. **ai-device-setup** - Emergency environment recovery
5. **ai-workspace** - macOS + AI deployment system
6. **repo-standardization-tools** - Documentation automation

### Web Applications (3)

7. **patrick-laclair-me** - Personal portfolio
8. **laclair-family-us** - Family portal
9. **laclair-terminal** - Terminal application

### Automation & Tools (3)

10. **laclair/powershell** - LaClair Technologies automation
11. **rtis/powershell** - Real Time automation
12. **xanban** - Windows parental controls

### Mobile Applications (1)

13. **netcalc** - iOS subnet calculator (in development)

---

## Brands

### LaClair Technologies

**Projects**: 11 of 12
- Primary brand for personal and consulting work
- Cloud AI allowed
- Standard security practices

### Real Time Information Services (RTIS)

**Projects**: 2 of 12 (ih-onboard-form, rtis/powershell)
- MSP client work
- **Privacy requirement**: Cloud AI blocked by default
- Enhanced security controls
- Local AI models preferred

---

## Documentation Standard

As of 2025-11-09, all repositories follow this structure:

```
repository/
├── .ai/                        # AI session context
│   ├── SESSION_CONTEXT.md      # Current state (use: pcontext)
│   ├── ARCHITECTURE.md         # Technical decisions (use: parch)
│   ├── HANDOFF.md             # Session transitions (use: phandoff)
│   ├── CHANGELOG.md           # Change history
│   ├── session_brand.json     # Brand detection
│   └── session_notes/         # Daily logs (gitignored)
│
├── docs/                       # Human documentation
│   ├── README.md
│   ├── GETTING_STARTED.md
│   ├── ARCHITECTURE.md
│   ├── DEPLOYMENT.md
│   ├── TROUBLESHOOTING.md
│   ├── CONFIGURATION.md
│   ├── maintenance/           # Dated logs
│   └── guides/                # How-to guides
│
├── scripts/                    # Utility scripts
│   ├── dev/
│   ├── deploy/
│   ├── troubleshoot/
│   └── maintenance/
│
└── releases/                   # Build artifacts (gitignored)
```

---

## Shell Aliases

Quick access to project documentation:

- **`pcontext`** - View current project state
- **`pnote "msg"`** - Add timestamped session note
- **`ptouch`** - Update timestamp
- **`parch`** - View architecture
- **`phandoff`** - View session handoffs
- **`pdocs`** - Navigate to docs/
- **`pscripts`** - View scripts

See [ALIASES-AND-TOOLS.md](ALIASES-AND-TOOLS.md) for complete reference.

---

## Getting Started

### New to This Portfolio?

1. **Read this file** (you are here)
2. **Review [DIRECTORY-STRUCTURE.md](DIRECTORY-STRUCTURE.md)** - Understand organization
3. **Check [PROJECT-INDEX.md](PROJECT-INDEX.md)** - Find specific projects
4. **Learn [ALIASES-AND-TOOLS.md](ALIASES-AND-TOOLS.md)** - Use shell aliases
5. **Study [WORKFLOWS.md](WORKFLOWS.md)** - Common tasks

### Starting Work on a Project

```bash
# Navigate to project
cd ~/dev/laclair/project-name

# Read current state
pcontext

# Read last session notes
phandoff

# Start work...
pnote "Starting work on feature X"

# End session
ptouch
vim .ai/HANDOFF.md  # Add notes for next session
```

---

## Key Resources

### Tools

- **Standardization**: `~/dev/laclair/repo-standardization-tools/`
- **Homelab Management**: SSH to docker.home.laclair.us
- **Claude Code**: Configured with auto-approval
- **Monitoring**: Tmux with specialized views (Prefix + M, then 1-5)

### External Services

- **GitHub**: github.com/plac9
- **Production Systems**:
  - https://xander.home.laclair.us
  - https://onboarding.ccfmg.org
- **Homelab**:
  - docker.home.laclair.us (Docker host)
  - yoda.home.laclair.us:2222 (NAS)
  - thebrain.home.laclair.us:2222 (OPNsense)

---

## Recent Major Work

### 2025-11-09: Documentation Standardization Project

Complete standardization of all 12 repositories:
- Created universal `.ai/` structure for AI session management
- Organized `docs/` with comprehensive guides
- Structured `scripts/` by purpose
- Added 7 shell aliases for quick documentation access
- Eliminated 50+ scattered documentation files
- Created repo-standardization-tools for future projects

See [sessions/2025-11-09-standardization.md](sessions/2025-11-09-standardization.md) for details.

---

## Portfolio Health

### Status (2025-11-09)

- ✅ All 12 repositories standardized
- ✅ All repositories validated and passing
- ✅ Documentation comprehensive and accurate
- ✅ Tools and automation in place
- ✅ Clean root directories (only README.md)
- ✅ Consistent structure across all projects

### Metrics

- **Documentation Quality**: High (comprehensive SESSION_CONTEXT.md in all repos)
- **Organization**: Excellent (consistent structure, no scattered files)
- **Automation**: Good (standardization scripts, validation tools)
- **Maintainability**: Excellent (clear locations, documented processes)

---

## Maintenance

### Daily

- Use `pnote` to log work in session notes
- Update SESSION_CONTEXT.md when status changes (`ptouch`)
- Keep HANDOFF.md updated for AI transitions

### Weekly

- Review session notes
- Update project statuses
- Archive old documentation

### Monthly

- Review all SESSION_CONTEXT.md files
- Update this master documentation
- Validate all repositories

---

## Contributing New Projects

When adding a new project:

1. Create in appropriate directory (laclair/, rtis/, infrastructure/, etc.)
2. Run standardization:
   ```bash
   ~/dev/laclair/repo-standardization-tools/scripts/apply-standards.sh /path/to/new/project
   ```
3. Customize SESSION_CONTEXT.md with project details
4. Update this portfolio documentation
5. Add to PROJECT-INDEX.md

---

**Portfolio Owner**: Patrick LaClair
**Documentation Standard**: v1.0.0
**Last Major Update**: 2025-11-09 (Standardization Project)
**Next Review**: 2025-12-09

For detailed information, see individual documentation files in this directory.
