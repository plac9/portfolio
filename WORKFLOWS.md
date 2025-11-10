# Common Workflows

**Last Updated**: 2025-11-09

---

## Starting a New Project

```bash
# 1. Create project directory
cd ~/dev/[laclair|rtis|infrastructure]/
mkdir new-project
cd new-project

# 2. Initialize git
git init

# 3. Apply standardization
~/dev/laclair/repo-standardization-tools/scripts/apply-standards.sh .

# 4. Customize SESSION_CONTEXT.md
vim .ai/SESSION_CONTEXT.md

# 5. Set brand
vim .ai/session_brand.json

# 6. Initial commit
git add .
git commit -m "feat: initialize project with standard structure

🤖 Generated with Claude Code

Co-Authored-By: Claude <noreply@anthropic.com>"
```

---

## Daily Development Workflow

```bash
# Morning - Start session
cd ~/dev/laclair/project-name
pcontext                    # Read current state
phandoff                    # Review last session

# During work - Log progress
pnote "Implemented authentication"
pnote "Fixed responsive layout bug"

# Evening - End session
ptouch                      # Update timestamp
vim .ai/HANDOFF.md          # Add handoff notes for next session
git add .
git commit -m "feat: complete authentication flow"
git push
```

---

## Deploying to Production

```bash
# Pre-deployment
cd ~/dev/laclair/project-name
pcontext                    # Review status
npm test                    # Run tests
npm run build              # Build

# Deploy
# (project-specific deployment)

# Post-deployment
pnote "Deployed version X.Y.Z to production"
ptouch
git tag vX.Y.Z
git push --tags
```

---

## Troubleshooting Workflow

```bash
# 1. Check project docs
cd ~/dev/laclair/project-name
cat docs/TROUBLESHOOTING.md

# 2. Log issue
pnote "Issue: <description>"

# 3. Debug
# ... troubleshoot ...

# 4. Document solution
vim docs/TROUBLESHOOTING.md  # Add solution
pnote "Fixed: <description of fix>"
```

---

## Portfolio Maintenance

### Monthly Review

```bash
# Validate all repositories
~/dev/laclair/repo-standardization-tools/scripts/validate-all-repos.sh

# Update portfolio docs
cd ~/dev/.portfolio/
vim README.md              # Update stats
```

---

For more workflows, see [ALIASES-AND-TOOLS.md](ALIASES-AND-TOOLS.md).
