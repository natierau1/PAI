# Git Workflow for PAI Repository

## Repository Configuration

This repository is configured with two remotes:

- **origin** - `https://github.com/natierau1/PAI.git` (Your primary repository)
- **upstream** - `https://github.com/danielmiessler/Personal_AI_Infrastructure.git` (Source for updates)

## Daily Operations (Your Repository)

All standard git commands automatically use your `natierau1/PAI` repository:

```bash
# Check status
git status

# Add and commit changes
git add .
git commit -m "Your commit message"

# Push to your repository
git push

# Pull from your repository
git pull

# Create and push a new branch
git checkout -b feature-branch
git push -u origin feature-branch
```

## Getting Updates from Original Repository

When danielmiessler releases updates to the original Personal_AI_Infrastructure:

### Option 1: Merge Updates (Recommended)

```bash
# Fetch updates from upstream
git fetch upstream

# Make sure you're on your main branch
git checkout main

# Merge upstream changes into your main branch
git merge upstream/main

# Push merged changes to your repository
git push origin main
```

### Option 2: Rebase Updates (Advanced)

```bash
# Fetch updates from upstream
git fetch upstream

# Make sure you're on your main branch
git checkout main

# Rebase your changes on top of upstream
git rebase upstream/main

# Push to your repository (may require force push)
git push origin main --force-with-lease
```

## Verify Remote Configuration

To check your remote setup anytime:

```bash
git remote -v
```

Expected output:
```
origin    https://github.com/natierau1/PAI.git (fetch)
origin    https://github.com/natierau1/PAI.git (push)
upstream  https://github.com/danielmiessler/Personal_AI_Infrastructure.git (fetch)
upstream  https://github.com/danielmiessler/Personal_AI_Infrastructure.git (push)
```

## Common Workflows

### Updating Your Fork with Upstream Changes

```bash
# 1. Fetch from upstream
git fetch upstream

# 2. Checkout your main branch
git checkout main

# 3. Merge upstream changes
git merge upstream/main

# 4. Resolve any conflicts if they occur
# Edit conflicted files, then:
git add .
git commit -m "Merge upstream updates"

# 5. Push to your repository
git push origin main
```

### Checking for Available Updates

```bash
# Fetch upstream without merging
git fetch upstream

# Compare your main with upstream main
git log main..upstream/main --oneline
```

If this shows commits, there are updates available.

## Important Notes

- **Default behavior**: All git operations use `origin` (your natierau1/PAI repository) by default
- **Upstream is read-only**: You cannot push to danielmiessler's repository (and shouldn't need to)
- **Check regularly**: Periodically check upstream for updates using `git fetch upstream`
- **Backup before merging**: Always commit your local changes before merging upstream updates

## Quick Reference

| Action | Command |
|--------|---------|
| Push to your repo | `git push` |
| Pull from your repo | `git pull` |
| Get upstream updates | `git fetch upstream` |
| Merge upstream | `git merge upstream/main` |
| Check for updates | `git log main..upstream/main` |
| View remotes | `git remote -v` |
