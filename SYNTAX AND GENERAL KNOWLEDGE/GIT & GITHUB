# Git Complete Reference Guide

A comprehensive reference covering Git concepts, commands, workflows, and best practices.

---

## Table of Contents

1. [Core Concepts](#core-concepts)
2. [Configuration](#configuration)
3. [Repository Setup](#repository-setup)
4. [Staging & Committing](#staging--committing)
5. [Branching](#branching)
6. [Merging & Rebasing](#merging--rebasing)
7. [Remote Repositories](#remote-repositories)
8. [Viewing History & Diffs](#viewing-history--diffs)
9. [Undoing Changes](#undoing-changes)
10. [Stashing](#stashing)
11. [Tagging](#tagging)
12. [Cherry-Picking](#cherry-picking)
13. [Searching & Filtering](#searching--filtering)
14. [Submodules](#submodules)
15. [Git Hooks](#git-hooks)
16. [Aliases](#aliases)
17. [The .gitignore File](#the-gitignore-file)
18. [Workflows](#workflows)
19. [Best Practices](#best-practices)

---

## Core Concepts

| Concept | Description |
|---------|-------------|
| **Repository (repo)** | A folder tracked by Git, containing your project and its full history |
| **Working directory** | Your local files as you see them on disk |
| **Staging area (index)** | A holding area where you prepare changes before committing |
| **Commit** | A saved snapshot of staged changes, permanently recorded in history |
| **Branch** | A lightweight movable pointer to a commit — enables parallel work |
| **HEAD** | A pointer to the currently checked-out commit or branch |
| **Remote** | A version of the repo hosted elsewhere (e.g., GitHub) |
| **Clone** | A full local copy of a remote repository |
| **Merge** | Combines two branches into one |
| **Rebase** | Replays commits on top of another branch for a linear history |
| **Detached HEAD** | HEAD points directly to a commit, not a branch |

### The Three States

```
Working Directory  →  Staging Area (Index)  →  Repository (.git)
     (edit)               (git add)                (git commit)
```

---

## Configuration

### Identity (required before first commit)

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### Editor & Tools

```bash
# Set default editor (VS Code, vim, nano, etc.)
git config --global core.editor "code --wait"
git config --global core.editor "vim"

# Set default merge tool
git config --global merge.tool vimdiff

# Set default diff tool
git config --global diff.tool vscode
```

### Behaviour Settings

```bash
# Default branch name for new repos
git config --global init.defaultBranch main

# Always rebase on pull instead of merge
git config --global pull.rebase true

# Line ending handling
git config --global core.autocrlf input    # macOS/Linux
git config --global core.autocrlf true     # Windows

# Color output
git config --global color.ui auto

# Credential caching (avoid re-entering password)
git config --global credential.helper cache
git config --global credential.helper "cache --timeout=3600"
```

### Viewing & Editing Config

```bash
git config --list                     # Show all settings
git config --list --show-origin       # Show settings with their source file
git config --global --edit            # Open global config in editor
git config user.name                  # View a specific setting

# Config scopes (local overrides global overrides system)
git config --local  ...               # This repo only (.git/config)
git config --global ...               # Your user (~/.gitconfig)
git config --system ...               # All users on machine
```

---

## Repository Setup

```bash
# Initialize a new repo in the current directory
git init

# Initialize with a specific branch name
git init -b main

# Initialize a bare repo (no working directory — used for servers/remotes)
git init --bare my-repo.git

# Clone a remote repo
git clone https://github.com/user/repo.git

# Clone into a specific folder name
git clone https://github.com/user/repo.git my-folder

# Clone a specific branch only
git clone -b develop https://github.com/user/repo.git

# Shallow clone (only latest N commits — faster for large repos)
git clone --depth 1 https://github.com/user/repo.git

# Clone including all submodules
git clone --recurse-submodules https://github.com/user/repo.git
```

---

## Staging & Committing

### Checking Status

```bash
git status                   # Full status (verbose)
git status -s                # Short/compact status
git status -sb               # Short + branch info
```

**Short status symbols:**
| Symbol | Meaning |
|--------|---------|
| `??` | Untracked file |
| `A` | New file staged |
| `M` | Modified |
| `D` | Deleted |
| `R` | Renamed |
| `C` | Copied |
| `U` | Merge conflict |

### Staging (git add)

```bash
git add filename.txt          # Stage a specific file
git add src/                  # Stage all files in a directory
git add .                     # Stage all changes in current directory
git add -A                    # Stage all changes (including deletions) everywhere
git add -u                    # Stage modifications and deletions (no new files)
git add *.js                  # Stage by pattern

# Interactive staging (lets you pick hunks)
git add -p                    # Patch mode — stage parts of a file
git add -i                    # Full interactive mode
```

### Committing

```bash
# Commit with inline message
git commit -m "feat: add login form validation"

# Commit with multi-line message (opens editor)
git commit

# Stage all tracked files and commit in one step
git commit -am "fix: correct typo in header"

# Amend the last commit (message or staged changes)
git commit --amend
git commit --amend -m "corrected commit message"
git commit --amend --no-edit   # Keep same message, add staged changes

# Empty commit (useful for triggering CI)
git commit --allow-empty -m "chore: trigger pipeline"
```

### Conventional Commit Types

A widely-used format: `type(scope): description`

| Type | When to use |
|------|------------|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only |
| `style` | Formatting, no logic change |
| `refactor` | Code restructure, no feature/fix |
| `test` | Adding or fixing tests |
| `chore` | Build process, tooling |
| `perf` | Performance improvement |
| `ci` | CI/CD config changes |

```bash
# Examples
git commit -m "feat(auth): add JWT refresh token support"
git commit -m "fix(api): handle null response from endpoint"
git commit -m "docs: update README with setup instructions"
```

---

## Branching

```bash
# List branches
git branch                    # Local branches
git branch -r                 # Remote-tracking branches
git branch -a                 # All branches (local + remote)
git branch -v                 # Local branches with last commit

# Create a branch
git branch feature/login      # Create (don't switch)
git checkout -b feature/login # Create and switch (classic)
git switch -c feature/login   # Create and switch (modern)

# Switch branches
git checkout main             # Classic
git switch main               # Modern

# Switch to previous branch
git switch -                  # or: git checkout -

# Rename a branch
git branch -m old-name new-name              # Rename local branch
git branch -m new-name                       # Rename current branch

# Delete a branch
git branch -d feature/login   # Safe delete (only if merged)
git branch -D feature/login   # Force delete (even if not merged)

# Delete a remote branch
git push origin --delete feature/login

# Track a remote branch
git branch --track main origin/main
git branch -u origin/main main             # Set upstream

# See which branches are merged into current
git branch --merged
git branch --no-merged

# Create branch from a specific commit or tag
git branch hotfix abc1234
git checkout -b release/1.0 v1.0-tag
```

---

## Merging & Rebasing

### Merging

```bash
# Merge a branch into current branch
git merge feature/login

# Merge with a commit message always created (no fast-forward)
git merge --no-ff feature/login

# Fast-forward only (fails if not possible)
git merge --ff-only feature/login

# Squash all commits from branch into one staged change
git merge --squash feature/login
git commit -m "feat: add login feature"

# Abort an in-progress merge
git merge --abort

# After resolving conflicts, complete the merge
git merge --continue
```

### Rebase

```bash
# Rebase current branch onto main
git rebase main

# Rebase a specific branch
git rebase main feature/login

# Interactive rebase (last 3 commits)
git rebase -i HEAD~3

# Interactive rebase from a specific commit
git rebase -i abc1234

# Abort rebase
git rebase --abort

# Continue after resolving conflicts
git rebase --continue

# Skip a conflicting commit
git rebase --skip
```

### Interactive Rebase Commands

When `git rebase -i` opens, each line starts with a command:

| Command | Shorthand | Action |
|---------|-----------|--------|
| `pick` | `p` | Keep commit as-is |
| `reword` | `r` | Keep commit, edit message |
| `edit` | `e` | Pause to amend commit |
| `squash` | `s` | Merge into previous commit |
| `fixup` | `f` | Merge into previous, discard message |
| `drop` | `d` | Remove the commit entirely |
| `exec` | `x` | Run a shell command |

### Resolving Merge Conflicts

```bash
# After a conflict, files have conflict markers:
<<<<<<< HEAD
  Your changes
=======
  Their changes
>>>>>>> feature/login

# 1. Edit the file to resolve
# 2. Stage the resolved file
git add resolved-file.js

# 3. Complete the merge or rebase
git merge --continue
# or
git rebase --continue

# Open the merge tool
git mergetool

# See which files have conflicts
git diff --name-only --diff-filter=U
```

---

## Remote Repositories

```bash
# View remotes
git remote -v

# Add a remote
git remote add origin https://github.com/user/repo.git

# Add a second remote (e.g., upstream for forks)
git remote add upstream https://github.com/original/repo.git

# Rename a remote
git remote rename origin old-origin

# Remove a remote
git remote remove upstream

# Change a remote's URL
git remote set-url origin https://github.com/user/new-repo.git

# Inspect a remote
git remote show origin
```

### Fetching, Pulling & Pushing

```bash
# Fetch (download changes, don't apply them)
git fetch origin               # Fetch all branches from origin
git fetch origin main          # Fetch a specific branch
git fetch --all                # Fetch from all remotes
git fetch --prune              # Fetch + remove deleted remote branches

# Pull (fetch + merge/rebase)
git pull                       # Pull current branch
git pull origin main           # Pull specific branch
git pull --rebase              # Pull with rebase instead of merge
git pull --ff-only             # Only pull if fast-forward is possible

# Push
git push origin main           # Push to remote branch
git push -u origin main        # Push and set upstream (first push)
git push                       # Push after upstream is set
git push --all                 # Push all local branches
git push --tags                # Push all tags
git push origin --delete feature/login  # Delete remote branch

# Force push (DANGEROUS on shared branches)
git push --force               # Overwrite remote history
git push --force-with-lease    # Safer: only force if no new commits from others
```

### Working with Upstream (Forks)

```bash
# Sync your fork with the original repo
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

---

## Viewing History & Diffs

### git log

```bash
git log                         # Full log
git log --oneline               # One line per commit
git log --oneline --graph       # ASCII branch graph
git log --oneline --graph --all # All branches in graph
git log --stat                  # Show files changed per commit
git log --patch                 # Show full diff for each commit
git log -n 5                    # Last 5 commits
git log --since="2 weeks ago"
git log --until="2024-01-01"
git log --author="Kwame"
git log --grep="fix:"           # Search commit messages
git log main..feature           # Commits in feature not in main
git log --follow -- filename.js # History of a specific file (follows renames)
git log --no-merges             # Exclude merge commits
git log --merges                # Only merge commits

# Pretty formatting
git log --pretty=format:"%h %ad | %s%d [%an]" --date=short
git log --pretty=format:"%Cred%h%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset"
```

### git diff

```bash
git diff                        # Unstaged changes (working dir vs index)
git diff --staged               # Staged changes (index vs last commit)
git diff HEAD                   # All changes since last commit
git diff main..feature          # Difference between two branches
git diff abc1234..def5678       # Between two commits
git diff HEAD~1                 # Between HEAD and one commit back
git diff -- filename.js         # Diff a specific file
git diff --stat                 # Summary: files changed, insertions, deletions
git diff --word-diff            # Show changes at word level
git diff --name-only            # Only show changed filenames
```

### Inspecting Commits

```bash
git show                        # Show last commit + diff
git show abc1234                # Show a specific commit
git show abc1234:path/file.js   # Show file as it was at that commit
git show HEAD~2                 # Two commits before HEAD

git blame filename.js           # Show who last changed each line
git blame -L 10,25 filename.js  # Blame specific lines
git blame -w filename.js        # Ignore whitespace changes

# Find which commit introduced a specific line
git log -S "search string" --patch
git log -G "regex pattern" --patch
```

---

## Undoing Changes

### Before Staging (Working Directory)

```bash
# Discard changes in a file (restore to last commit)
git restore filename.js                  # Modern
git checkout -- filename.js             # Classic

# Discard all unstaged changes
git restore .
git checkout -- .

# Remove untracked files
git clean -n                            # Dry run (see what would be removed)
git clean -f                            # Remove untracked files
git clean -fd                           # Remove untracked files + directories
git clean -fx                           # Remove untracked + ignored files
```

### After Staging (Index)

```bash
# Unstage a file (keep changes in working dir)
git restore --staged filename.js        # Modern
git reset HEAD filename.js             # Classic

# Unstage everything
git restore --staged .
```

### After Committing

```bash
# Undo last commit, keep changes staged
git reset --soft HEAD~1

# Undo last commit, keep changes unstaged
git reset --mixed HEAD~1   # (default)

# Undo last commit, DISCARD all changes (DESTRUCTIVE)
git reset --hard HEAD~1

# Reset to a specific commit
git reset --hard abc1234

# Safe undo — creates a new reverting commit (good for shared branches)
git revert HEAD
git revert abc1234
git revert HEAD~3..HEAD   # Revert a range of commits
git revert --no-commit abc1234  # Revert without auto-committing

# Recover a deleted branch or lost commit
git reflog                  # Shows all recent HEAD movements
git checkout -b recovered abc1234  # Re-create branch from reflog hash
```

### Reset Reference

| Command | Working Dir | Staging Area | Commits |
|---------|-------------|--------------|---------|
| `--soft HEAD~1` | Unchanged | Unchanged | Moved back |
| `--mixed HEAD~1` | Unchanged | Cleared | Moved back |
| `--hard HEAD~1` | **Cleared** | **Cleared** | Moved back |

---

## Stashing

Stash saves your uncommitted work temporarily so you can switch context.

```bash
# Save current changes to stash
git stash                       # Stash tracked file changes
git stash push -m "WIP: login form"  # Stash with a message
git stash -u                    # Include untracked files
git stash -a                    # Include untracked + ignored files

# List stashes
git stash list

# Apply a stash (keep it in stash list)
git stash apply                 # Apply most recent
git stash apply stash@{2}       # Apply specific stash

# Apply and remove from stash list
git stash pop                   # Pop most recent
git stash pop stash@{1}

# View stash contents
git stash show                  # Summary
git stash show -p               # Full diff
git stash show stash@{1} -p

# Create a branch from a stash
git stash branch feature/new stash@{0}

# Drop (delete) a stash
git stash drop stash@{0}

# Clear all stashes
git stash clear
```

---

## Tagging

Tags mark specific points in history — typically used for releases.

```bash
# List tags
git tag
git tag -l "v1.*"              # Filter by pattern

# Lightweight tag (just a pointer)
git tag v1.0.0

# Annotated tag (recommended — includes metadata)
git tag -a v1.0.0 -m "Release version 1.0.0"

# Tag a specific past commit
git tag -a v0.9.0 abc1234 -m "Beta release"

# Show tag details
git show v1.0.0

# Push tags to remote
git push origin v1.0.0         # Push a specific tag
git push origin --tags         # Push all tags

# Delete a tag
git tag -d v1.0.0              # Delete locally
git push origin --delete v1.0.0  # Delete remotely

# Checkout at a tag (enters detached HEAD)
git checkout v1.0.0

# Create branch from a tag
git checkout -b hotfix/1.0.1 v1.0.0
```

---

## Cherry-Picking

Apply specific commits from one branch to another.

```bash
# Apply a single commit to current branch
git cherry-pick abc1234

# Apply multiple commits
git cherry-pick abc1234 def5678

# Apply a range of commits
git cherry-pick abc1234..def5678   # Excludes abc1234
git cherry-pick abc1234^..def5678  # Includes abc1234

# Cherry-pick without auto-committing (stage only)
git cherry-pick -n abc1234

# Abort cherry-pick
git cherry-pick --abort

# Continue after conflict resolution
git cherry-pick --continue
```

---

## Searching & Filtering

```bash
# Search for a string across all tracked files
git grep "search term"
git grep -n "search term"        # Show line numbers
git grep -i "search term"        # Case-insensitive
git grep "pattern" -- "*.js"     # In specific file types
git grep "term" v1.0.0           # Search at a specific tag/commit

# Find which commit introduced a bug (binary search)
git bisect start
git bisect bad                   # Current commit is bad
git bisect good v1.0.0           # Known good commit
# Git checks out a midpoint — test it, then:
git bisect good                  # If this commit is OK
git bisect bad                   # If this commit is broken
# Repeat until Git identifies the first bad commit
git bisect reset                 # Exit bisect mode

# Automate bisect with a test script
git bisect start HEAD v1.0.0
git bisect run npm test

# Find who changed a specific function
git log -L :functionName:file.js

# Search commit messages
git log --all --grep="keyword"

# Find a deleted file in history
git log --all --full-history -- "**/filename.js"
git show abc1234:path/to/filename.js  # View the deleted file
```

---

## Submodules

Submodules let you embed one Git repo inside another.

```bash
# Add a submodule
git submodule add https://github.com/user/lib.git libs/lib

# Initialize submodules after cloning
git submodule init
git submodule update

# Both in one step
git submodule update --init

# Recursive (for nested submodules)
git submodule update --init --recursive

# Pull latest changes for all submodules
git submodule update --remote

# Run a command in each submodule
git submodule foreach git pull origin main

# Remove a submodule
git submodule deinit libs/lib
git rm libs/lib
rm -rf .git/modules/libs/lib
```

---

## Git Hooks

Hooks are scripts that run automatically at specific Git events. Located in `.git/hooks/`.

### Common Hooks

| Hook | Trigger | Use case |
|------|---------|----------|
| `pre-commit` | Before commit is created | Run linter, tests |
| `commit-msg` | After commit message is typed | Validate message format |
| `post-commit` | After commit is created | Notifications |
| `pre-push` | Before push | Run full test suite |
| `post-merge` | After merge | Install dependencies |
| `pre-rebase` | Before rebase | Safety checks |

### Example: `pre-commit` hook

```bash
#!/bin/sh
# .git/hooks/pre-commit
npm run lint
if [ $? -ne 0 ]; then
  echo "Linting failed. Fix errors before committing."
  exit 1
fi
```

```bash
# Make it executable
chmod +x .git/hooks/pre-commit
```

> **Tip:** Use [Husky](https://typicode.github.io/husky/) to manage hooks in a project and share them via version control.

---

## Aliases

Add shortcuts for common commands.

```bash
# Set aliases via command line
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.lg "log --oneline --graph --all"
git config --global alias.last "log -1 HEAD"
git config --global alias.unstage "restore --staged"
git config --global alias.undo "reset --soft HEAD~1"

# Or add directly to ~/.gitconfig:
[alias]
  st  = status -sb
  co  = checkout
  sw  = switch
  br  = branch
  ci  = commit
  lg  = log --oneline --graph --all --decorate
  ll  = log --pretty=format:"%C(yellow)%h%Creset %s %C(cyan)(%cr)%Creset" --all
  df  = diff --staged
  wip = commit -am "WIP"
  oops = commit --amend --no-edit
  aliases = config --get-regexp alias
```

---

## The .gitignore File

Tells Git which files and directories to ignore.

```gitignore
# ── Dependencies ──────────────────────────────────────
node_modules/
vendor/
.venv/
__pycache__/

# ── Build outputs ─────────────────────────────────────
dist/
build/
out/
*.min.js
*.min.css

# ── Environment & secrets (NEVER commit these) ────────
.env
.env.local
.env.*.local
*.pem
*.key
secrets.json

# ── OS files ──────────────────────────────────────────
.DS_Store         # macOS
Thumbs.db         # Windows
desktop.ini

# ── Editor files ──────────────────────────────────────
.vscode/
.idea/
*.sublime-workspace
*.swp             # Vim swap files

# ── Logs & temp files ─────────────────────────────────
*.log
logs/
tmp/
*.tmp
*.cache

# ── Test coverage ─────────────────────────────────────
coverage/
.nyc_output/

# ── Compiled/binary files ─────────────────────────────
*.exe
*.dll
*.so
*.class
*.pyc

# ── Patterns ──────────────────────────────────────────
*.log             # Any .log file
!important.log    # Exception: track this one
doc/**/*.pdf      # PDFs inside doc/ (any depth)
/config.local.js  # Only at repo root
```

### Useful Commands

```bash
# Check if a file is being ignored and why
git check-ignore -v filename.txt

# Force-add an ignored file
git add -f filename.txt

# Stop tracking a file already in the repo (after adding to .gitignore)
git rm --cached filename.txt
git rm --cached -r node_modules/

# Global gitignore (applies to all repos on your machine)
git config --global core.excludesfile ~/.gitignore_global
```

---

## Workflows

### Feature Branch Workflow

The most common workflow for teams.

```bash
# 1. Start from an up-to-date main
git switch main
git pull origin main

# 2. Create a feature branch
git switch -c feature/user-profile

# 3. Work, commit often
git add .
git commit -m "feat: add profile avatar upload"

# 4. Keep up to date with main
git fetch origin
git rebase origin/main

# 5. Push and open a Pull Request
git push -u origin feature/user-profile

# 6. After PR is merged, clean up
git switch main
git pull origin main
git branch -d feature/user-profile
```

### Gitflow (for release-based projects)

```
main       ← stable, production releases only
develop    ← integration branch, always ahead of main
feature/*  ← branches off develop
release/*  ← branches off develop when ready to release
hotfix/*   ← branches off main to fix production bugs
```

```bash
# Start a feature
git switch -c feature/checkout develop

# Finish a feature (merge back to develop)
git switch develop
git merge --no-ff feature/checkout
git branch -d feature/checkout

# Start a release
git switch -c release/1.2.0 develop

# Finish a release (merge to main AND develop)
git switch main
git merge --no-ff release/1.2.0
git tag -a v1.2.0 -m "Release 1.2.0"
git switch develop
git merge --no-ff release/1.2.0
git branch -d release/1.2.0

# Hotfix
git switch -c hotfix/fix-login main
# ... fix the bug ...
git switch main
git merge --no-ff hotfix/fix-login
git tag -a v1.2.1
git switch develop
git merge --no-ff hotfix/fix-login
git branch -d hotfix/fix-login
```

### Trunk-Based Development (for CI/CD)

```bash
# Everyone commits directly to main (or very short-lived branches)
git switch main
git pull
# Make small change
git commit -m "fix: correct email validation regex"
git push

# Short-lived branches only (merged within 1–2 days)
git switch -c fix/null-pointer
# Fix it, then:
git switch main
git merge fix/null-pointer
git push
git branch -d fix/null-pointer
```

---

## Best Practices

### Commits
- Commit **early and often** — small, focused commits are easier to review and revert.
- Write commit messages in the **imperative mood**: "Add feature" not "Added feature".
- Use a **conventional commit** format for automatic changelogs and versioning.
- **Never commit secrets** — API keys, tokens, passwords. Use `.gitignore` and environment variables.
- Avoid committing **generated files** (compiled output, `node_modules`).

### Branching
- Keep **`main` (or `master`) always deployable** — only merge tested, reviewed code.
- **Delete branches** after merging to keep the repo clean.
- Use **descriptive branch names**: `feature/payment-gateway`, `fix/cart-null-error`, `docs/api-reference`.
- Use `--force-with-lease` instead of `--force` when force-pushing is necessary.

### History
- **Do not rewrite public history** — never rebase or force-push to shared branches.
- Use `git revert` to undo changes on shared branches (it's non-destructive).
- Reserve `git reset --hard` for local, private branches only.
- Use `git reflog` to recover from mistakes — it keeps a full local history.

### Collaboration
- **Pull before you push** — always fetch/pull to integrate others' work first.
- Use **Pull Requests / Merge Requests** for code review before merging to main.
- Review `git diff --staged` before every commit to check exactly what you're committing.
- Write a meaningful **README** and keep a **CHANGELOG**.

### Performance & Maintenance
- Use `git fetch --prune` regularly to remove stale remote-tracking branches.
- For large repos, use `git clone --depth 1` for faster shallow clones in CI.
- Use `.gitattributes` to handle line endings and binary files consistently across OS.

```bash
# .gitattributes examples
* text=auto                   # Auto line ending normalization
*.sh text eol=lf             # Force LF for shell scripts
*.bat text eol=crlf          # Force CRLF for Windows scripts
*.png binary                  # Mark as binary (no diff/merge)
*.pdf binary
```

---

## Quick Reference Cheatsheet

```bash
# ── Setup ──────────────────────────────
git init                         # New repo
git clone <url>                  # Clone repo

# ── Snapshot ───────────────────────────
git status                       # What changed?
git add .                        # Stage all
git commit -m "message"          # Commit
git commit --amend               # Fix last commit

# ── Branch ─────────────────────────────
git switch -c <name>             # New branch
git switch <name>                # Switch branch
git branch -d <name>             # Delete branch
git merge <branch>               # Merge into current

# ── Remote ─────────────────────────────
git remote add origin <url>      # Add remote
git push -u origin main          # First push
git pull                         # Fetch + merge
git fetch --prune                # Fetch, clean up

# ── Undo ───────────────────────────────
git restore <file>               # Discard changes
git restore --staged <file>      # Unstage
git reset --soft HEAD~1          # Undo commit (keep staged)
git revert <hash>                # Safe undo (new commit)

# ── Inspect ────────────────────────────
git log --oneline --graph --all  # Visual history
git diff --staged                # What's staged?
git blame <file>                 # Who changed what?
git reflog                       # Full local history

# ── Stash ──────────────────────────────
git stash                        # Save WIP
git stash pop                    # Restore WIP
```

---

*Reference compiled for learning and development use. Official Git documentation: [git-scm.com/docs](https://git-scm.com/docs)*
