# Git Learning and Practice Guide

Welcome to your Git learning journey! This comprehensive guide will help you understand Git fundamentals and become proficient with version control.

## Table of Contents
1. [Introduction to Git](#introduction-to-git)
2. [Basic Commands](#basic-commands)
3. [Creating a Repository](#creating-a-repository)
4. [Making Changes](#making-changes)
5. [Branching](#branching)
6. [Merging](#merging)
7. [Remote Repositories](#remote-repositories)
8. [Advanced Topics](#advanced-topics)
9. [Best Practices](#best-practices)
10. [Useful Resources](#useful-resources)

## Introduction to Git

Git is a distributed version control system designed to handle projects of any size with speed and efficiency. It was created by Linus Torvalds in 2005 for Linux kernel development.

### Key Concepts

- **Repository (Repo)**: A directory containing your project and its version history
- **Commit**: A snapshot of your files at a specific point in time
- **Branch**: An independent line of development
- **Remote**: A repository hosted on the internet or network
- **Working Directory**: Your local project directory
- **Staging Area**: A intermediate area where changes are prepared for commit

## Basic Commands

Essential Git commands for daily use:

```bash
# Repository Setup
git init                    # Initialize a new Git repository
git clone <url>             # Clone an existing repository
git remote add origin <url> # Add a remote repository

# Basic Operations
git status                  # Check status of working directory
git add <file>             # Stage file(s) for commit
git add .                  # Stage all changes
git commit -m "message"    # Commit staged changes
git push                   # Push commits to remote repository
git pull                   # Fetch and merge changes from remote

# History and Differences
git log                    # View commit history
git log --oneline         # Compact view of history
git diff                  # Show unstaged changes
git diff --staged         # Show staged changes
git blame <file>          # Show who changed what and when
```

## Creating a Repository

### Starting a New Project

1. Create a new directory for your project:
```bash
mkdir my-project
cd my-project
```

2. Initialize Git repository:
```bash
git init
```

3. Add your first files:
```bash
git add README.md
git commit -m "Initial commit"
```

### Cloning an Existing Repository

```bash
git clone https://github.com/username/repository.git
cd repository
```

## Making Changes

### Basic Workflow

1. Check status of your working directory:
```bash
git status
```

2. Stage your changes:
```bash
git add <file>      # Stage specific file
git add .           # Stage all changes
```

3. Commit changes:
```bash
git commit -m "Descriptive message about changes"
```

4. Push to remote:
```bash
git push origin main
```

### Undoing Changes

```bash
git checkout -- <file>     # Discard changes in working directory
git reset HEAD <file>      # Unstage changes
git revert <commit>        # Create new commit that undoes changes
git reset --hard <commit>  # Reset to specific commit (dangerous!)
```

## Branching

### Branch Management

```bash
# Create and Switch Branches
git branch <branch-name>      # Create new branch
git checkout <branch-name>    # Switch to branch
git checkout -b <branch-name> # Create and switch in one command

# Branch Operations
git branch                  # List branches
git branch -d <branch-name> # Delete branch
git branch -m <new-name>    # Rename current branch
```

### Branch Workflow

1. Create feature branch:
```bash
git checkout -b feature/new-feature
```

2. Make changes and commit:
```bash
git add .
git commit -m "Add new feature"
```

3. Push branch to remote:
```bash
git push origin feature/new-feature
```

## Merging

### Basic Merge

```bash
git checkout main             # Switch to main branch
git merge feature/new-feature # Merge feature branch into main
```

### Handling Merge Conflicts

1. When conflicts occur:
   - Open conflicted files
   - Look for conflict markers (<<<<<<, =======, >>>>>>>)
   - Resolve conflicts manually
   - Stage resolved files
   - Complete the merge with commit

```bash
git add <resolved-files>
git commit -m "Resolve merge conflicts"
```

## Remote Repositories

### Managing Remotes

```bash
git remote -v                     # List remote repositories
git remote add origin <url>       # Add remote
git remote rename origin upstream # Rename remote
git remote remove origin          # Remove remote
```

### Synchronizing with Remote

```bash
git fetch origin           # Download objects and refs
git pull origin main       # Fetch and merge changes
git push origin main       # Push local changes
git push --force           # Force push (use with caution!)
```

## Advanced Topics

### Stashing Changes

```bash
git stash                 # Stash changes
git stash list            # List stashes
git stash pop             # Apply and remove stash
git stash apply           # Apply but keep stash
```

### Tagging

```bash
git tag v1.0.0                       # Create lightweight tag
git tag -a v1.0.0 -m "Release 1.0.0" # Create annotated tag
git push origin --tags               # Push tags to remote
```

### Rebasing

```bash
git rebase main           # Rebase current branch onto main
git rebase -i HEAD~3      # Interactive rebase last 3 commits
```

## Best Practices

1. **Commit Messages**
   - Write clear, concise commit messages
   - Use present tense ("Add feature" not "Added feature")
   - First line should be under 50 characters
   - Include detailed description if needed

2. **Branching Strategy**
   - Use feature branches for new work
   - Keep main/master branch stable
   - Delete merged branches
   - Use descriptive branch names

3. **Regular Updates**
   - Pull changes frequently
   - Keep local repository up to date
   - Resolve conflicts promptly

4. **Security**
   - Don't commit sensitive information
   - Use .gitignore for private files
   - Regularly audit repository contents

## Useful Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Learn Git Branching](https://learngitbranching.js.org/)
