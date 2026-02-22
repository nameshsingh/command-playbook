# Git Basics

Essential git commands for learning version control.

## Initial Setup

```bash
# Configure git user
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Check configuration
git config --global --list

# Configure default editor
git config --global core.editor "vim"

# Configure default branch name
git config --global init.defaultBranch main
```

## Repository Setup

```bash
# Initialize a new repository
git init

# Clone a repository
git clone <repository-url>

# Clone into specific directory
git clone <repository-url> <directory>

# Clone with depth (shallow clone)
git clone --depth 1 <repository-url>

# Get repository information
git remote -v
```

## Basic Workflow

```bash
# Check repository status
git status

# See what changed
git diff

# See staged changes
git diff --staged

# Add files to staging area
git add <file>

# Add all changes
git add .

# Add all changes interactively
git add -p

# Commit changes
git commit -m "Commit message"

# Commit with detailed message
git commit

# Amend last commit (don't push if already pushed)
git commit --amend

# View commit history
git log

# View compact log
git log --oneline

# View log with graph
git log --graph --oneline --all
```

## Working with Changes

```bash
# Unstage file
git reset <file>

# Discard changes in working directory
git checkout -- <file>

# Discard all changes
git reset --hard

# See what was changed in a commit
git show <commit-hash>

# See differences between commits
git diff <commit1> <commit2>

# Revert a commit (creates new commit)
git revert <commit-hash>

# Remove file from git (keep local copy)
git rm --cached <file>

# Remove file from git and filesystem
git rm <file>

# Rename file
git mv <old-name> <new-name>
```

## Branching

```bash
# List local branches
git branch

# List all branches (local and remote)
git branch -a

# Create new branch
git branch <branch-name>

# Create and switch to new branch
git checkout -b <branch-name>

# Create and switch to new branch (modern syntax)
git switch -c <branch-name>

# Switch to branch
git checkout <branch-name>

# Switch to branch (modern syntax)
git switch <branch-name>

# Delete branch (safe)
git branch -d <branch-name>

# Delete branch (force)
git branch -D <branch-name>

# Delete remote branch
git push origin --delete <branch-name>

# Rename branch
git branch -m <old-name> <new-name>

# View branch history
git branch -v
```

## Merging

```bash
# Merge branch into current branch
git merge <branch-name>

# Merge without fast-forward
git merge --no-ff <branch-name>

# Abort merge
git merge --abort

# See which branches are merged
git branch --merged

# See which branches are not merged
git branch --no-merged
```

## Remote Operations

```bash
# List remotes
git remote

# List remotes with URLs
git remote -v

# Add remote
git remote add <name> <url>

# Remove remote
git remote remove <name>

# Rename remote
git remote rename <old> <new>

# Show remote information
git remote show <remote-name>

# Fetch from remote (doesn't merge)
git fetch

# Fetch from specific remote
git fetch <remote-name>

# Pull from remote (fetch + merge)
git pull

# Pull with rebase
git pull --rebase

# Push to remote
git push

# Push to specific remote and branch
git push <remote> <branch>

# Push all branches
git push --all

# Push with tags
git push --follow-tags

# Delete remote branch via push
git push <remote> --delete <branch>
```

## Tagging

```bash
# List tags
git tag

# Create lightweight tag
git tag <tag-name>

# Create annotated tag
git tag -a <tag-name> -m "message"

# Show tag information
git show <tag-name>

# Push tag to remote
git push origin <tag-name>

# Push all tags
git push --tags

# Delete tag locally
git delete-tag <tag-name>

# Delete tag on remote
git push origin --delete <tag-name>
```

## Stashing

```bash
# Stash current changes
git stash

# Stash with message
git stash save "message"

# List stashes
git stash list

# Apply last stash (keeps it)
git stash apply

# Apply specific stash
git stash apply stash@{0}

# Pop stash (applies and removes)
git stash pop

# Drop stash
git stash drop

# Drop all stashes
git stash clear
```

## Undoing Changes

```bash
# Undo last commit (keep changes staged)
git reset --soft HEAD~1

# Undo last commit (keep changes unstaged)
git reset --mixed HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Undo multiple commits
git reset --hard HEAD~3

# Go back to specific commit
git reset --hard <commit-hash>

# Revert changes (creates new commit)
git revert <commit-hash>

# Revert multiple commits
git revert <commit1>..<commit2>

# View reflog (all movements)
git reflog
```

## Inspecting History

```bash
# View detailed commit history
git log

# View commit history with changes
git log -p

# View specific number of commits
git log -n 5

# View commits since date
git log --since="2 weeks ago"

# View commits by author
git log --author="Name"

# View commits matching message
git log --grep="message"

# View commits affecting file
git log -- <file>

# Show blame (who changed what)
git blame <file>

# Show specific commit
git show <commit-hash>

# Show changes in file at commit
git show <commit-hash>:<file>
```

## Comparing Code

```bash
# Compare working directory with staging
git diff

# Compare staging with last commit
git diff --cached

# Compare working directory with last commit
git diff HEAD

# Compare two commits
git diff <commit1> <commit2>

# Compare two branches
git diff <branch1> <branch2>

# Show stat (summary of changes)
git diff --stat

# Show files changed
git diff --name-only
```

## Useful Aliases

```bash
# Create shortcuts
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual 'log --graph --oneline --all'
```

## Tips

- Commit early and often with clear messages
- Use branches for features and fixes
- Pull before pushing to avoid conflicts
- Use `.gitignore` to exclude files
- Use meaningful branch names (feature/, bugfix/, etc.)
- Review changes before committing (git diff)
- Write descriptive commit messages
