# Project Portfolio Cheat Sheet

**Last Updated**: 2025-11-09
**Total Projects**: 12
**Purpose**: Quick reference for all aliases, commands, and project information

---

## Shell Aliases Reference

### Project Documentation Aliases

These aliases help you navigate and manage project documentation quickly:

| Alias | Command | Description |
|-------|---------|-------------|
| `pdocs` | `cd docs && ls -la` | Navigate to docs/ directory and list contents |
| `pcontext` | `cat .ai/SESSION_CONTEXT.md \| less` | View current project context for AI |
| `parch` | `cat .ai/ARCHITECTURE.md \| less` | View architecture documentation |
| `phandoff` | `cat .ai/HANDOFF.md \| less` | View session handoff notes |
| `pscripts` | `cd scripts && tree -L 2` | View scripts organization |

**Usage Example**:
```bash
cd ~/dev/laclair/xander-dashboard
pcontext                    # Read current project state
parch                       # Review architecture
```

### Project Documentation Functions

| Function | Usage | Description |
|----------|-------|-------------|
| `pnote` | `pnote "message"` | Add timestamped note to .ai/session_notes/YYYY-MM-DD.md |
| `ptouch` | `ptouch` | Update "Last Updated" timestamp in SESSION_CONTEXT.md |

**Usage Example**:
```bash
pnote "Fixed authentication bug"         # Adds timestamped note
pnote "Deployed to staging"              # Adds another note
ptouch                                    # Updates SESSION_CONTEXT timestamp
```

**Note Storage**:
- Notes saved to: `.ai/session_notes/YYYY-MM-DD.md`
- These files are gitignored (ephemeral session logs)
- Useful for daily work tracking without cluttering git history

---

### Git Aliases

| Alias | Command | Description |
|-------|---------|-------------|
| `gs` | `git status` | Show git status |
| `gp` | `git pull` | Pull from remote |
| `gc` | `git commit` | Commit changes |
| `gco` | `git checkout` | Checkout branch |

**Usage Example**:
```bash
gs                          # Check status
git add .
gc -m "Update feature"
gp
```

---

### Docker Aliases

| Alias | Command | Description |
|-------|---------|-------------|
| `dps` | `docker ps` | List running containers |
| `dpsa` | `docker ps -a` | List all containers |
| `dlog` | `docker logs` | View container logs |
| `dlogf` | `docker logs -f` | Follow container logs |
| `dexec` | `docker exec -it` | Execute command in container |

**Usage Example**:
```bash
dps                                      # See running containers
dlog xander-dashboard-backend            # View logs
dlogf xander-dashboard-backend           # Follow logs (Ctrl+C to stop)
dexec xander-dashboard-backend /bin/sh   # Open shell in container
```

---

### Tmux Aliases

| Alias | Command | Description |
|-------|---------|-------------|
| `ta` | `tmux attach` | Attach to existing session |
| `tl` | `tmux list-sessions` | List all sessions |
| `tn` | `tmux new -s` | Create new named session |

| Function | Usage | Description |
|----------|-------|-------------|
| `tmon` | `tmon [session]` | Attach with monitoring pane |

**Usage Example**:
```bash
tn dev                      # Create session named "dev"
ta                          # Attach to last session
tl                          # List all sessions
tmon dev                    # Attach to "dev" with monitor pane
```

**Tmux Keybindings**:
- `Prefix + M`: Open monitor pane (Prefix is usually Ctrl+B)
- `Prefix + 1-5`: Switch monitor views (1=Full, 2=Infra, 3=AI, 4=Session, 5=Compact)

---

### Homelab Aliases

| Alias | Command | Description |
|-------|---------|-------------|
| `ssh-homelab` | `ssh placlair-admin@docker.home.laclair.us` | SSH to homelab |
| `ssh-homelab-tmux` | `ssh ... -t tmux a` | SSH to homelab with tmux |

**Homelab Functions**:
- `homelab-health` - Check homelab container health
- `homelab-ssh` - Interactive SSH to homelab
- `homelab-validate` - Validate homelab services
- `homelab-logs` - View homelab logs

**Homelab Servers**:
- **docker.home.laclair.us**: Main Docker host (52 containers)
- **yoda.home.laclair.us:2222**: NAS (placlair-admin)
- **thebrain.home.laclair.us:2222**: OPNsense router (root)

**Usage Example**:
```bash
ssh-homelab                            # Connect to homelab
homelab-health                         # Check container health
homelab-logs xander-dashboard          # View app logs
```

---

### Claude Code Alias

| Alias | Command | Description |
|-------|---------|-------------|
| `cc` | `claude --dangerously-bypass-permissions` | Launch Claude Code with auto-approval |

**Usage Example**:
```bash
cc                          # Start Claude Code in current directory
```

**Note**: Uses `--dangerously-bypass-permissions` for streamlined workflow. Only use in trusted environments.

---

## Project Quick Reference

### Complex Projects (4)

#### 1. xander-dashboard
- **Path**: `~/dev/laclair/xander-dashboard`
- **Type**: Production React Dashboard
- **Tech**: React 18, Node.js 22, Express, SQLite, WebSocket, Docker
- **URL**: https://xander.home.laclair.us
- **Purpose**: Gaming latency monitor, typing tests, kid-safe shell for Xander
- **Commands**:
  ```bash
  cd ~/dev/laclair/xander-dashboard
  pcontext                              # View status
  cd backend && npm run dev             # Run backend
  cd frontend && npm run dev            # Run frontend
  ```

#### 2. ai-device-setup
- **Path**: `~/dev/laclair/ai-device-setup`
- **Type**: Emergency Recovery Tool
- **Tech**: Bash, PowerShell, GitHub CLI
- **Purpose**: Restore dev environment after OS crash
- **Commands**:
  ```bash
  cd ~/dev/laclair/ai-device-setup
  ./setup.sh --universal                # Run universal setup
  ./setup.sh --universal --dry-run      # Check current structure
  ```

#### 3. homelab-iac
- **Path**: `~/dev/infrastructure/homelab-iac`
- **Type**: Infrastructure as Code
- **Tech**: Docker, Dockge, GitHub Actions
- **Purpose**: Homelab infrastructure automation
- **Commands**:
  ```bash
  cd ~/dev/infrastructure/homelab-iac
  pcontext                              # View infrastructure state
  ```

#### 4. ih-onboard-form
- **Path**: `~/dev/rtis/ih-onboard-form`
- **Type**: Production Employee Onboarding System
- **Tech**: Node.js, Express, SQLite, HTML5/CSS3/JS
- **Brand**: Real Time (RTIS)
- **URLs**:
  - Production: https://onboarding.ccfmg.org
  - Internal: https://ccfmg-apps05.ccfmg.org
- **Purpose**: IHMG employee onboarding multi-process platform
- **Commands**:
  ```bash
  cd ~/dev/rtis/ih-onboard-form/ihmg-onboarding
  node server.js                        # Run server
  npm test                              # Run tests
  ```

---

### PowerShell Projects (2)

#### 5. laclair/powershell
- **Path**: `~/dev/laclair/powershell`
- **Type**: Automation Scripts
- **Tech**: PowerShell
- **Brand**: LaClair Technologies
- **Purpose**: Enterprise PowerShell automation for system admin, development, consulting
- **Commands**:
  ```bash
  cd ~/dev/laclair/powershell
  pscripts                              # View available scripts
  ```

#### 6. rtis/powershell
- **Path**: `~/dev/rtis/powershell`
- **Type**: Automation Scripts
- **Tech**: PowerShell
- **Brand**: Real Time (RTIS)
- **Purpose**: PowerShell scripts for RealTime operations
- **Commands**:
  ```bash
  cd ~/dev/rtis/powershell
  pscripts                              # View available scripts
  ```

---

### Web Apps (3)

#### 7. patrick-laclair-me
- **Path**: `~/dev/laclair/patrick-laclair-me`
- **Type**: Personal Portfolio Website
- **Tech**: React 18, TypeScript 5, Vite 7
- **Purpose**: Personal website/portfolio
- **Commands**:
  ```bash
  cd ~/dev/laclair/patrick-laclair-me
  npm install
  npm run dev                           # Development server
  npm run build                         # Build for production
  ```

#### 8. laclair-family-us
- **Path**: `~/dev/laclair/laclair-family-us`
- **Type**: Family Website
- **Tech**: React 18, TypeScript 5, Vite 7
- **Purpose**: Family website
- **Commands**:
  ```bash
  cd ~/dev/laclair/laclair-family-us
  npm install
  npm run dev                           # Development server
  npm run build                         # Build for production
  ```

#### 9. laclair-terminal
- **Path**: `~/dev/laclair/laclair-terminal`
- **Type**: Interactive Terminal Website
- **Tech**: React 18, TypeScript 5, Vite 7, CSS3 animations
- **Purpose**: Retro-styled terminal telling LaClair family story through Unix commands
- **Features**: Full CLI emulation, virtual file system, tab autocomplete, CRT effects, Easter eggs
- **Commands**:
  ```bash
  cd ~/dev/laclair/laclair-terminal
  npm install
  npm run dev                           # Development server
  npm run build                         # Build to dist/
  ```

---

### Tools (3)

#### 10. netcalc
- **Path**: `~/dev/laclair/netcalc`
- **Type**: iOS Subnet Calculator
- **Tech**: Swift 6.0, SwiftUI, iOS 18+
- **Purpose**: Modern subnet calculator and network designer for iOS/iPadOS/macOS
- **Features**: IPv4/IPv6 CIDR, VLSM, supernetting, topology visualization
- **Commands**:
  ```bash
  cd ~/dev/laclair/netcalc
  swift build                           # Build project
  swift test                            # Run tests
  open netcalc.xcodeproj                # Open in Xcode
  ```

#### 11. xanban
- **Path**: `~/dev/laclair/xanban`
- **Type**: Windows Parental Controls
- **Tech**: PowerShell, Windows Task Scheduler
- **Purpose**: Time-based local account enforcement for parental controls
- **Features**: Daily usage windows, warning notifications, auto-disable/enable
- **Config**: `C:\ProgramData\XanBan\config.json`
- **Commands**:
  ```bash
  cd ~/dev/laclair/xanban
  pcontext                              # View documentation
  ```

#### 12. ai-workspace
- **Path**: `~/dev/laclair/ai-workspace`
- **Type**: macOS + AI Workspace Deployment
- **Tech**: Bash, Homebrew, Node.js, Ollama, VS Code
- **Purpose**: Fresh macOS deployment with brand-aware privacy controls
- **Features**: Dual-account setup, brand detection (LaClair/RTIS), local AI models, Continue.dev
- **Commands**:
  ```bash
  cd ~/dev/laclair/ai-workspace
  ./ai-detect-brand.sh                  # Detect project brand
  ./switch-continue-config.sh           # Switch Continue.dev config
  ./ollama-bootstrap.sh                 # Install Ollama + models
  ```

---

### Standardization Tools (Bonus)

#### 13. repo-standardization-tools
- **Path**: `~/dev/laclair/repo-standardization-tools`
- **Type**: Documentation Standardization System
- **Tech**: Bash scripts, Templates
- **Purpose**: Universal documentation structure for all repositories
- **Commands**:
  ```bash
  cd ~/dev/laclair/repo-standardization-tools
  ./scripts/apply-standards.sh /path/to/repo      # Standardize a repository
  ./scripts/validate-all-repos.sh                 # Validate all 12 repos
  ```

---

## Common Workflows

### Starting Work on a Project

```bash
# Navigate to project
cd ~/dev/laclair/some-project

# Read context
pcontext                    # Current state
phandoff                    # Last session notes
parch                       # Architecture

# Start work
# ... do your work ...

# Document progress
pnote "Completed feature X"
pnote "Fixed bug Y"

# End session
ptouch                      # Update timestamp
vim .ai/HANDOFF.md          # Add handoff notes for next session
```

### Deploying to Production

```bash
# Navigate to project
cd ~/dev/laclair/some-project

# Check status
gs                          # Git status
pcontext                    # Current state

# Run tests
npm test

# Build
npm run build

# Commit
git add .
gc -m "Prepare production release"

# Deploy (project-specific)
# ... follow deployment guide ...

# Document
pnote "Deployed version X.Y.Z to production"
ptouch
```

### Troubleshooting

```bash
# Navigate to project
cd ~/dev/laclair/some-project

# View troubleshooting docs
cat docs/TROUBLESHOOTING.md

# Check logs (Docker projects)
dlogf container-name

# Check homelab (if deployed there)
ssh-homelab
homelab-health
homelab-logs app-name

# Document solution
pnote "Fixed issue: <description>"
# Add to docs/TROUBLESHOOTING.md for future reference
```

---

## Directory Structure Quick Reference

Every standardized project has this structure:

```
project-root/
├── README.md                           # Only file at root
├── .ai/                                # AI session context
│   ├── SESSION_CONTEXT.md              # Current state (pcontext)
│   ├── ARCHITECTURE.md                 # Design decisions (parch)
│   ├── HANDOFF.md                      # Session transitions (phandoff)
│   ├── CHANGELOG.md                    # Change log
│   ├── session_brand.json              # Brand detection
│   └── session_notes/                  # Daily logs (gitignored)
├── docs/                               # Human documentation
│   ├── README.md
│   ├── GETTING_STARTED.md
│   ├── ARCHITECTURE.md
│   ├── DEPLOYMENT.md
│   ├── TROUBLESHOOTING.md
│   ├── CONFIGURATION.md
│   ├── maintenance/                    # Dated maintenance logs
│   └── guides/                         # User/developer guides
├── scripts/                            # Utility scripts
│   ├── README.md
│   ├── dev/                            # Development
│   ├── deploy/                         # Deployment
│   ├── troubleshoot/                   # Diagnostics
│   └── maintenance/                    # Maintenance
└── releases/                           # Build artifacts (gitignored)
```

---

## Git Operations

### Standard Commit Flow

```bash
gs                          # Check status
git add .                   # Stage all changes
git add file.js             # Stage specific file
gc -m "Commit message"      # Commit
gp                          # Pull latest
git push                    # Push to remote
```

### Branch Operations

```bash
gco -b feature/new-thing    # Create and checkout new branch
gco main                    # Switch to main
git merge feature/new-thing # Merge branch
git branch -d feature/new-thing  # Delete branch
```

---

## Best Practices

### Daily Workflow

1. **Start of Day**:
   ```bash
   cd ~/dev/laclair/current-project
   pcontext                 # Read where you left off
   phandoff                 # Check handoff notes
   ```

2. **During Work**:
   ```bash
   pnote "Implemented X"
   pnote "Fixed Y"
   pnote "Deployed Z"
   ```

3. **End of Day**:
   ```bash
   ptouch                   # Update timestamp
   vim .ai/HANDOFF.md       # Add handoff notes
   gs                       # Check git status
   gc -m "Daily progress"   # Commit work
   git push                 # Push to remote
   ```

### Documentation Maintenance

- **SESSION_CONTEXT.md**: Update weekly or after major changes
- **ARCHITECTURE.md**: Update when design decisions are made
- **HANDOFF.md**: Update at end of each work session
- **TROUBLESHOOTING.md**: Add solutions as you discover them
- **session_notes/**: Use `pnote` throughout the day

### Git Hygiene

- Commit frequently with descriptive messages
- Pull before starting work each day
- Push at end of each day
- Create feature branches for new work
- Keep main/master branch stable

---

## Brand Awareness

### LaClair Technologies Projects
- xander-dashboard, ai-device-setup, homelab-iac
- laclair/powershell
- patrick-laclair-me, laclair-family-us, laclair-terminal
- netcalc, xanban, ai-workspace

**Standards**: LaClair Technologies coding standards apply

### Real Time (RTIS) Projects
- ih-onboard-form
- rtis/powershell

**Standards**: Real Time coding standards apply
**Privacy**: Cloud models may be restricted for RTIS projects

---

## Emergency Contacts

### Homelab
- **Main Host**: docker.home.laclair.us (placlair-admin)
- **NAS**: yoda.home.laclair.us:2222 (placlair-admin)
- **Router**: thebrain.home.laclair.us:2222 (root)

### Production Systems
- **Xander Dashboard**: https://xander.home.laclair.us
- **IHMG Onboarding**: https://onboarding.ccfmg.org

---

## Quick Tips

1. **Use `pcontext` first** when starting work on any project
2. **Use `pnote`** throughout the day to track progress
3. **Use `ptouch`** before committing to update timestamps
4. **Check `docs/TROUBLESHOOTING.md`** before asking for help
5. **Update `.ai/HANDOFF.md`** at end of sessions for smooth transitions
6. **Standardize new projects** with `repo-standardization-tools`

---

**Last Updated**: 2025-11-09
**Maintained By**: Patrick LaClair
**Purpose**: Quick reference for all development workflows

**Note**: This cheat sheet covers all 12 repositories plus the standardization tools. Keep it handy!
